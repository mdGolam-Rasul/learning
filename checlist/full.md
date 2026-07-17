# Bug Bounty Web Response Analysis Checklist

> Beginner-friendly Banglish checklist for analyzing HTTP responses, cookies, authentication, authorization, headers, routing, caching, and common web vulnerabilities.
>
> **Use only on systems you own or targets where you have explicit permission and an active bug bounty scope.**

---

## Table of Contents

1. [Quick Triage](#1-quick-triage)
2. [Scope and Safety](#2-scope-and-safety)
3. [Response Status and Routing](#3-response-status-and-routing)
4. [Cookie Analysis](#4-cookie-analysis)
5. [Authentication Testing](#5-authentication-testing)
6. [Authorization and IDOR](#6-authorization-and-idor)
7. [Session Management](#7-session-management)
8. [CSRF](#8-csrf)
9. [XSS and Output Encoding](#9-xss-and-output-encoding)
10. [CSP](#10-csp)
11. [NoSQL Injection](#11-nosql-injection)
12. [SQL Injection](#12-sql-injection)
13. [CORS](#13-cors)
14. [Security Headers](#14-security-headers)
15. [Caching and CDN Behavior](#15-caching-and-cdn-behavior)
16. [Rate Limiting and Brute Force](#16-rate-limiting-and-brute-force)
17. [File Upload](#17-file-upload)
18. [Path Traversal and File Read](#18-path-traversal-and-file-read)
19. [Open Redirect](#19-open-redirect)
20. [SSRF](#20-ssrf)
21. [Business Logic](#21-business-logic)
22. [API and JSON Testing](#22-api-and-json-testing)
23. [Node.js and Express Checks](#23-nodejs-and-express-checks)
24. [Information Disclosure](#24-information-disclosure)
25. [Error Handling](#25-error-handling)
26. [Transport Security](#26-transport-security)
27. [Clickjacking](#27-clickjacking)
28. [WebSocket Checks](#28-websocket-checks)
29. [GraphQL Checks](#29-graphql-checks)
30. [Evidence Collection](#30-evidence-collection)
31. [Severity and Impact](#31-severity-and-impact)
32. [Bug Report Template](#32-bug-report-template)
33. [Example Analysis of the Given Response](#33-example-analysis-of-the-given-response)
34. [Final Testing Workflow](#34-final-testing-workflow)

---

# 1. Quick Triage

Kono HTTP response dekhlei first 60 seconds-e ei questions gulo korba:

- [ ] Status code logical naki?
- [ ] Body ar status code match kore?
- [ ] New cookie set hocche?
- [ ] Cookie signed/encrypted naki sudhu encoded?
- [ ] Cookie-te user ID, role, email, profile data, order ID ache?
- [ ] Cookie modify korle server accept kore?
- [ ] Authentication cookie rotate hoy?
- [ ] `Secure`, `HttpOnly`, `SameSite` flags ache?
- [ ] Sensitive response cacheable naki?
- [ ] User-controlled input response-e reflect hocche?
- [ ] Security headers ache?
- [ ] Error message internal details leak kore?
- [ ] Different user/object ID change korle unauthorized data pawa jay?
- [ ] Request replay korle same action abar hoy?
- [ ] Login chara endpoint accessible?
- [ ] Normal user admin endpoint access korte pare?
- [ ] Browser console-e CSP/CORS/error clue ache?

---

# 2. Scope and Safety

Testing start korar age:

- [ ] Program scope pora hoyeche
- [ ] Target domain/subdomain allowed
- [ ] API host allowed
- [ ] Automated scanning allowed kina check
- [ ] Rate limit policy check
- [ ] Social engineering prohibited kina check
- [ ] DoS/load testing prohibited kina check
- [ ] Third-party services test kora jabe kina check
- [ ] Real user data access avoid
- [ ] Minimum proof collect
- [ ] Data download korar age stop
- [ ] Destructive action avoid
- [ ] Test account use
- [ ] Two separate test accounts ready
- [ ] Request/response timestamps save
- [ ] Sensitive token report-e redact

Golden rule:

> Vulnerability prove korar jonno minimum impact test koro. Unnecessary data access, deletion, spam, or service disruption korba na.

---

# 3. Response Status and Routing

Example:

```http
HTTP/1.1 200 OK

<h1>404</h1>
```

Eta **soft 404**.

## Checklist

- [ ] Missing page-e actual `404 Not Found` ashe?
- [ ] Unauthorized page-e `401` ba `403` ashe?
- [ ] Server error-e `500` ashe?
- [ ] Redirect-e correct `3xx` code?
- [ ] Login failure always `200` diye body message dey?
- [ ] API error success code diye return kore?
- [ ] Unknown route cookie set kore?
- [ ] Unknown route session reset kore?
- [ ] Case variation behavior:
  - [ ] `/Admin`
  - [ ] `/admin`
  - [ ] `/ADMIN`
- [ ] Trailing slash behavior:
  - [ ] `/admin`
  - [ ] `/admin/`
- [ ] Dot segment behavior:
  - [ ] `/admin/.`
  - [ ] `/admin/../admin`
- [ ] URL encoded route behavior
- [ ] Double encoded route behavior
- [ ] Semicolon path parameter behavior
- [ ] Duplicate slash behavior
- [ ] HTTP method variation:
  - [ ] GET
  - [ ] POST
  - [ ] PUT
  - [ ] PATCH
  - [ ] DELETE
  - [ ] HEAD
  - [ ] OPTIONS
- [ ] Method override headers accepted?
- [ ] Reverse proxy and backend status mismatch?
- [ ] CDN caches error page as success?
- [ ] Search engines index fake 404 pages?
- [ ] Monitoring/security tooling status-code dependent?

## Possible findings

- Soft 404
- Route confusion
- Method-based authorization bypass
- Cache poisoning
- Reverse proxy mismatch
- Hidden endpoint exposure

---

# 4. Cookie Analysis

Given example:

```http
Set-Cookie: profile=BASE64_DATA; Max-Age=900; Path=/; HttpOnly
```

## 4.1 Decode first

Cookie values may be:

- URL encoded
- Base64 encoded
- JSON
- JWT
- Serialized object
- Signed cookie
- Encrypted blob
- Framework-specific session identifier

### Quick decode workflow

1. URL decode
2. Base64 decode
3. JSON parse
4. Check signature/encryption
5. Modify one field
6. Re-encode
7. Replay request

## 4.2 Questions to ask

- [ ] Cookie name security-sensitive?
- [ ] Cookie contains:
  - [ ] username
  - [ ] email
  - [ ] user ID
  - [ ] profile ID
  - [ ] order ID
  - [ ] organization ID
  - [ ] tenant ID
  - [ ] role
  - [ ] permissions
  - [ ] `isAdmin`
  - [ ] subscription plan
  - [ ] price
  - [ ] country
  - [ ] feature flags
- [ ] Cookie is only Base64 encoded?
- [ ] Cookie has cryptographic signature?
- [ ] Modified cookie rejected?
- [ ] Signature error different from parse error?
- [ ] Server trusts extra fields?
- [ ] Server ignores removed fields?
- [ ] Duplicate cookie names create confusion?
- [ ] Cookie shadowing possible?
- [ ] Subdomain can overwrite parent-domain cookie?
- [ ] Path-restricted cookie can be shadowed?
- [ ] Cookie prefix used?
  - [ ] `__Host-`
  - [ ] `__Secure-`
- [ ] Cookie expiration correct?
- [ ] Logout invalidates cookie?
- [ ] Password reset invalidates old sessions?
- [ ] Email/password change invalidates other sessions?

## 4.3 Security flags

- [ ] `HttpOnly`
- [ ] `Secure`
- [ ] `SameSite=Lax`
- [ ] `SameSite=Strict`
- [ ] `SameSite=None; Secure`
- [ ] Correct `Domain`
- [ ] Correct `Path`
- [ ] Reasonable `Max-Age`
- [ ] Reasonable `Expires`

## 4.4 Tampering tests

Change one field at a time:

```json
{
  "username": "admin"
}
```

```json
{
  "num": "1"
}
```

```json
{
  "role": "admin"
}
```

```json
{
  "isAdmin": true
}
```

```json
{
  "plan": "enterprise"
}
```

```json
{
  "tenantId": "OTHER_TENANT_ID"
}
```

Observe:

- [ ] UI change only?
- [ ] Server-side data change?
- [ ] Different user's data?
- [ ] Admin route unlock?
- [ ] Pricing change?
- [ ] Feature unlock?
- [ ] Authorization decision change?
- [ ] Audit log records attacker-supplied identity?

## 4.5 Duplicate cookie tests

Example:

```http
Cookie: profile=VALUE_A; profile=VALUE_B
```

Check:

- [ ] Frontend reads first but backend reads last?
- [ ] Proxy reads one value, app reads another?
- [ ] Security middleware validates different cookie than business logic?
- [ ] Path/domain collision changes selected cookie?

---

# 5. Authentication Testing

## Login

- [ ] Valid username + valid password works
- [ ] Valid username + invalid password rejected
- [ ] Invalid username + random password rejected
- [ ] Different response reveals user existence?
- [ ] Different timing reveals user existence?
- [ ] Case-sensitive username behavior?
- [ ] Unicode normalization confusion?
- [ ] Leading/trailing whitespace behavior?
- [ ] Empty password behavior?
- [ ] Null JSON value behavior?
- [ ] Boolean/number/object input behavior?
- [ ] Duplicate JSON key behavior?
- [ ] Duplicate form parameter behavior?
- [ ] Login over HTTP possible?
- [ ] MFA enforced consistently?
- [ ] Backup code reuse possible?
- [ ] Remember-me token secure?
- [ ] Account lockout present?
- [ ] Lockout can be abused for DoS?
- [ ] Rate limit IP-only?
- [ ] Rate limit account-only?
- [ ] Proxy headers bypass rate limit?

## Password reset

- [ ] Token unpredictable
- [ ] Token expires
- [ ] Token single-use
- [ ] Old token invalid after new request
- [ ] Token tied to account
- [ ] Token tied to intended action
- [ ] Host header cannot poison reset link
- [ ] Email parameter cannot target another account
- [ ] Reset response does not reveal account existence
- [ ] Password reset logs out old sessions
- [ ] Reset token not leaked in Referer
- [ ] Reset token not cached
- [ ] Reset token not exposed to analytics/third-party scripts

## MFA

- [ ] OTP rate-limited
- [ ] OTP expiration
- [ ] OTP replay blocked
- [ ] MFA bypass via direct endpoint
- [ ] MFA bypass via alternate login flow
- [ ] MFA bypass via OAuth
- [ ] MFA bypass via mobile API
- [ ] Backup code rate-limited
- [ ] Recovery flow equally secure
- [ ] Session not fully authenticated before OTP

---

# 6. Authorization and IDOR

Use two accounts:

- Account A
- Account B

## Object identifiers to test

- [ ] user ID
- [ ] profile ID
- [ ] order ID
- [ ] invoice ID
- [ ] ticket ID
- [ ] file ID
- [ ] message ID
- [ ] team ID
- [ ] tenant ID
- [ ] organization ID
- [ ] API key ID
- [ ] payment method ID
- [ ] subscription ID
- [ ] address ID

## Read operations

- [ ] A can read B's object?
- [ ] Unauthenticated user can read object?
- [ ] Deleted object still accessible?
- [ ] Draft/private object accessible?
- [ ] Object accessible through alternate endpoint?
- [ ] Export endpoint leaks object?
- [ ] Search endpoint leaks object?
- [ ] GraphQL resolver leaks object?
- [ ] Mobile API leaks object?
- [ ] Old API version leaks object?

## Write operations

- [ ] A can edit B's profile?
- [ ] A can delete B's object?
- [ ] A can cancel B's order?
- [ ] A can change B's email?
- [ ] A can add itself to B's organization?
- [ ] A can modify role/permissions?
- [ ] A can approve its own request?
- [ ] A can transfer ownership?
- [ ] A can alter hidden fields?
- [ ] A can update object using bulk endpoint?

## Horizontal vs vertical

**Horizontal privilege escalation:**

> Normal user A accesses normal user B's data.

**Vertical privilege escalation:**

> Normal user accesses admin-only functionality.

## Mass assignment fields

Check hidden/undocumented fields:

```json
{
  "role": "admin",
  "isAdmin": true,
  "verified": true,
  "emailVerified": true,
  "balance": 999999,
  "plan": "enterprise",
  "ownerId": "ATTACKER_ID",
  "tenantId": "OTHER_TENANT"
}
```

- [ ] Server ignores forbidden fields?
- [ ] Response reflects field but database does not save?
- [ ] Field persists after reload?
- [ ] Field affects authorization?
- [ ] Nested object accepted?
- [ ] Array-based roles accepted?

---

# 7. Session Management

- [ ] Session ID changes after login
- [ ] Session ID changes after privilege elevation
- [ ] Session ID changes after MFA
- [ ] Session invalid after logout
- [ ] Session invalid after password change
- [ ] Session invalid after account deletion
- [ ] Concurrent session management available
- [ ] User can revoke other sessions
- [ ] Session idle timeout exists
- [ ] Session absolute timeout exists
- [ ] Session token high entropy
- [ ] Session token not in URL
- [ ] Session token not logged
- [ ] Session token not stored in insecure browser storage
- [ ] Session fixation prevented
- [ ] Pre-auth session not reused post-auth
- [ ] Cookie not shared across unrelated subdomains
- [ ] Auth decision not based on client-editable profile cookie
- [ ] Refresh token rotated
- [ ] Refresh token reuse detected
- [ ] Access token expires reasonably
- [ ] Token audience/issuer validated
- [ ] Revoked account cannot keep using token

---

# 8. CSRF

CSRF mainly relevant when browser automatically sends authentication credentials.

## Check sensitive actions

- [ ] change email
- [ ] change password
- [ ] add phone
- [ ] disable MFA
- [ ] add payment method
- [ ] create order
- [ ] cancel order
- [ ] transfer ownership
- [ ] invite user
- [ ] change role
- [ ] delete account
- [ ] API key creation
- [ ] webhook creation

## Protection checks

- [ ] CSRF token present
- [ ] Token tied to session
- [ ] Token unpredictable
- [ ] Token required on all state-changing endpoints
- [ ] Token validated server-side
- [ ] Origin checked
- [ ] Referer checked
- [ ] SameSite cookie configured
- [ ] GET does not change state
- [ ] Form content type accepted?
- [ ] JSON endpoint accepts text/plain?
- [ ] Method override enables state change?
- [ ] CORS plus credentials enables cross-site action?
- [ ] Login CSRF possible?
- [ ] Logout CSRF meaningful?
- [ ] OAuth account-link CSRF possible?

Do not report just "SameSite missing" as CSRF. A working state-changing cross-site proof is stronger.

---

# 9. XSS and Output Encoding

## Input locations

- [ ] profile name
- [ ] order note
- [ ] support ticket
- [ ] product review
- [ ] chat message
- [ ] file name
- [ ] image metadata
- [ ] search query
- [ ] URL parameter
- [ ] HTTP header
- [ ] cookie value
- [ ] admin dashboard field
- [ ] email template field

## Context identification

User input appears inside:

- [ ] HTML body
- [ ] HTML attribute
- [ ] JavaScript string
- [ ] JSON
- [ ] CSS
- [ ] URL
- [ ] SVG
- [ ] Markdown
- [ ] template literal

## Safe initial probes

```text
TEST-12345
```

```text
<test>
```

```text
"'><test>
```

Check page source and DOM.

## Questions

- [ ] Output HTML-encoded?
- [ ] Attribute-encoded?
- [ ] JavaScript-encoded?
- [ ] URL-encoded?
- [ ] Stored or reflected?
- [ ] Admin later views it?
- [ ] CSP blocks execution?
- [ ] Sanitizer removes dangerous tags?
- [ ] Sanitizer can be bypassed by mutation?
- [ ] Markdown renderer allows raw HTML?
- [ ] SVG upload renders active content?
- [ ] File name inserted into HTML unsafely?
- [ ] Error page reflects path/header?
- [ ] Cookie value rendered into page?

## Impact considerations

- Same-user self-XSS usually low/no impact
- Admin-view stored XSS can be high impact
- XSS in sensitive origin can steal actions/data
- HttpOnly protects cookie reading but not authenticated actions
- CSP may reduce exploitability but does not fix unsafe output handling

---

# 10. CSP

Check response header:

```http
Content-Security-Policy: ...
```

## Directives

- [ ] `default-src`
- [ ] `script-src`
- [ ] `style-src`
- [ ] `img-src`
- [ ] `connect-src`
- [ ] `frame-src`
- [ ] `frame-ancestors`
- [ ] `object-src`
- [ ] `base-uri`
- [ ] `form-action`
- [ ] `report-uri`
- [ ] `report-to`

## Weak patterns

- [ ] `'unsafe-inline'`
- [ ] `'unsafe-eval'`
- [ ] wildcard `*`
- [ ] broad CDN domains
- [ ] user-content domain allowed
- [ ] JSONP endpoint allowed
- [ ] attacker-controlled subdomain allowed
- [ ] missing `object-src 'none'`
- [ ] missing `base-uri`
- [ ] missing `frame-ancestors`
- [ ] nonce reused
- [ ] predictable nonce
- [ ] nonce reflected from user input
- [ ] CSP only report mode
- [ ] different pages have weaker CSP

## Remember

> CSP is defense-in-depth. Unsafe input handling remains a bug even if a basic payload is blocked.

---

# 11. NoSQL Injection

Typical vulnerable code:

```javascript
const user = await User.findOne({ username });
```

If `username` is not forced to be a string, attacker may send an object containing query operators.

## Input type checks

- [ ] string accepted
- [ ] object accepted
- [ ] array accepted
- [ ] boolean accepted
- [ ] number accepted
- [ ] null accepted
- [ ] duplicate JSON key accepted
- [ ] nested object accepted

## Common indicators

- [ ] MongoDB/Mongoose errors
- [ ] different result when sending object
- [ ] authentication query changes
- [ ] search filters behave unexpectedly
- [ ] regex causes delay or broad results
- [ ] API accepts operators in query parameters

## Defensive expectation

```javascript
if (typeof username !== "string") {
  return res.status(400).json({ error: "Invalid input" });
}
```

Also consider:

```javascript
mongoose.set("sanitizeFilter", true);
```

Type validation is still essential.

## Impact checklist

- [ ] username enumeration
- [ ] account selection manipulation
- [ ] filter bypass
- [ ] data extraction
- [ ] login bypass
- [ ] authorization bypass
- [ ] blind behavior difference
- [ ] regex DoS risk

---

# 12. SQL Injection

## Input locations

- [ ] query parameters
- [ ] JSON body
- [ ] form fields
- [ ] cookies
- [ ] headers
- [ ] sort/order fields
- [ ] pagination
- [ ] report/export filters
- [ ] search
- [ ] numeric IDs

## Safe validation approach

Look for:

- [ ] database error changes
- [ ] response length changes
- [ ] true/false behavior differences
- [ ] unusual delays
- [ ] unauthorized rows
- [ ] different HTTP status
- [ ] WAF-specific behavior

## Server-side fixes

- Parameterized queries
- Prepared statements
- Strict type validation
- Allowlist sorting fields
- Least-privileged database account
- Generic error handling

---

# 13. CORS

Check response:

```http
Access-Control-Allow-Origin: ...
Access-Control-Allow-Credentials: true
```

## Tests

- [ ] Origin reflected?
- [ ] Arbitrary origin accepted?
- [ ] `null` origin accepted?
- [ ] Subdomain prefix/suffix confusion?
- [ ] HTTP origin trusted while HTTPS target?
- [ ] Attacker-controlled subdomain trusted?
- [ ] Credentials enabled?
- [ ] Sensitive response readable cross-origin?
- [ ] Preflight correctly enforced?
- [ ] Different endpoint has different policy?
- [ ] Error response leaks data cross-origin?
- [ ] Wildcard with credentials misconfiguration?
- [ ] Origin regex poorly anchored?

A strong CORS finding needs:

1. Attacker-controlled origin accepted
2. Browser sends credentials
3. Sensitive response is readable
4. Practical victim impact

---

# 14. Security Headers

## Recommended headers

```http
Content-Security-Policy: ...
X-Content-Type-Options: nosniff
Referrer-Policy: strict-origin-when-cross-origin
Permissions-Policy: ...
Strict-Transport-Security: max-age=...
```

For framing:

```http
Content-Security-Policy: frame-ancestors 'none'
```

or legacy:

```http
X-Frame-Options: DENY
```

## Checklist

- [ ] CSP present
- [ ] CSP effective
- [ ] `frame-ancestors` set
- [ ] `nosniff` set
- [ ] Referrer policy sensible
- [ ] HSTS on HTTPS
- [ ] HSTS includes subdomains only when safe
- [ ] Permissions Policy reasonable
- [ ] Sensitive pages use `Cache-Control: no-store`
- [ ] `X-Powered-By` removed
- [ ] Server version hidden

Missing headers alone are often informational. Show real exploitability where possible.

---

# 15. Caching and CDN Behavior

## Sensitive response checklist

- [ ] `Cache-Control: no-store`
- [ ] `Cache-Control: private`
- [ ] `Pragma: no-cache` where legacy needed
- [ ] `Vary` correct
- [ ] CDN headers present
- [ ] Personalized response cached?
- [ ] Authenticated content available after logout through browser cache?
- [ ] Another user receives cached data?
- [ ] `Set-Cookie` response cached?
- [ ] Error response cached?
- [ ] Redirect cached incorrectly?
- [ ] Cache key includes query parameters?
- [ ] Cache key includes relevant headers?
- [ ] Unkeyed headers influence response?
- [ ] Host header influences cached content?
- [ ] Origin header influences cached response?
- [ ] Method confusion in cache?

Potential issues:

- Web cache deception
- Web cache poisoning
- Cross-user data leak
- Cached redirect poisoning
- Cached security header removal

---

# 16. Rate Limiting and Brute Force

Check:

- [ ] Login attempts
- [ ] OTP attempts
- [ ] Password reset requests
- [ ] Invitation endpoint
- [ ] Coupon validation
- [ ] Username/email enumeration
- [ ] API key creation
- [ ] SMS/email sending
- [ ] Search/export
- [ ] Expensive report generation

Bypass dimensions:

- [ ] IP change
- [ ] account change
- [ ] endpoint variation
- [ ] method variation
- [ ] case variation
- [ ] trailing slash
- [ ] alternate host
- [ ] API version
- [ ] proxy headers
- [ ] duplicate headers
- [ ] batched request
- [ ] GraphQL aliases

Do not perform high-volume testing unless program explicitly allows it.

---

# 17. File Upload

## Validation

- [ ] extension allowlist
- [ ] MIME validation
- [ ] magic-byte validation
- [ ] file size limit
- [ ] filename normalization
- [ ] server-generated filename
- [ ] upload outside web root
- [ ] antivirus scanning
- [ ] image re-encoding
- [ ] SVG restrictions
- [ ] archive extraction safety
- [ ] metadata stripping

## Access control

- [ ] private file requires auth
- [ ] file ID unguessable or authorized
- [ ] deleted file inaccessible
- [ ] signed URL expires
- [ ] signed URL tied to object/user
- [ ] CDN does not cache private file publicly
- [ ] filename does not cause XSS
- [ ] content disposition safe

## Dangerous behavior

- [ ] active HTML served inline
- [ ] SVG executes script
- [ ] uploaded file interpreted server-side
- [ ] double extension accepted
- [ ] path components accepted in filename
- [ ] archive traversal
- [ ] image parser issues
- [ ] content-type confusion

---

# 18. Path Traversal and File Read

Potential parameters:

- `file`
- `path`
- `template`
- `download`
- `image`
- `document`
- `lang`
- `page`
- `folder`

Check:

- [ ] canonicalization
- [ ] encoded traversal
- [ ] double encoding
- [ ] mixed slash
- [ ] absolute path handling
- [ ] null-byte handling
- [ ] symlink behavior
- [ ] archive extraction path
- [ ] cloud storage key traversal
- [ ] file download authorization

Use harmless in-scope test files where possible. Avoid collecting unnecessary secrets.

---

# 19. Open Redirect

Parameters:

- `next`
- `url`
- `redirect`
- `return`
- `returnUrl`
- `continue`
- `callback`

Check:

- [ ] absolute external URL accepted
- [ ] protocol-relative URL accepted
- [ ] userinfo syntax confusion
- [ ] subdomain suffix confusion
- [ ] backslash normalization
- [ ] encoded URL bypass
- [ ] double encoding
- [ ] newline injection
- [ ] OAuth flow impact
- [ ] password reset impact
- [ ] phishing impact
- [ ] allowlist parsing flaws

Open redirect severity increases when chained with OAuth token leakage, trusted-domain phishing, or security-control bypass.

---

# 20. SSRF

Potential features:

- URL preview
- webhook
- image fetch
- PDF generation
- import from URL
- avatar URL
- RSS reader
- cloud integration
- callback validation

Check:

- [ ] external URL fetched server-side
- [ ] redirect followed
- [ ] DNS resolution behavior
- [ ] private IP blocked
- [ ] localhost blocked
- [ ] alternate IP formats blocked
- [ ] cloud metadata blocked
- [ ] non-HTTP schemes blocked
- [ ] response content returned
- [ ] timing reveals internal service
- [ ] blind callback possible
- [ ] DNS rebinding defenses
- [ ] allowlist properly parsed

Use only approved callback infrastructure and follow program rules.

---

# 21. Business Logic

## E-commerce

- [ ] negative quantity
- [ ] zero quantity
- [ ] decimal quantity
- [ ] price client-controlled
- [ ] currency mismatch
- [ ] coupon reuse
- [ ] coupon stacking
- [ ] expired coupon accepted
- [ ] referral self-use
- [ ] shipping bypass
- [ ] tax bypass
- [ ] payment status trusted from client
- [ ] order confirmed before payment
- [ ] refund exceeds payment
- [ ] duplicate refund
- [ ] race condition in stock/coupon

## Account workflows

- [ ] invite accepted by wrong email
- [ ] old invite reusable
- [ ] role set by invitee
- [ ] ownership transferred without confirmation
- [ ] deleted account restored improperly
- [ ] verification bypass
- [ ] email changed without re-authentication
- [ ] password changed without old password/MFA
- [ ] workflow steps skipped
- [ ] approval can be self-issued

## Multi-tenant

- [ ] tenant ID client-controlled
- [ ] search crosses tenants
- [ ] export crosses tenants
- [ ] file links cross tenants
- [ ] API keys valid across tenants
- [ ] webhook secrets cross tenants
- [ ] admin role scoped correctly
- [ ] background jobs enforce tenant boundary

---

# 22. API and JSON Testing

## Content types

- [ ] `application/json`
- [ ] form-urlencoded
- [ ] multipart/form-data
- [ ] text/plain
- [ ] XML
- [ ] missing content type
- [ ] conflicting content type

## JSON edge cases

- [ ] duplicate keys
- [ ] nested objects
- [ ] arrays instead of strings
- [ ] numbers instead of strings
- [ ] booleans
- [ ] null
- [ ] huge integers
- [ ] negative numbers
- [ ] scientific notation
- [ ] Unicode confusables
- [ ] deeply nested objects
- [ ] extra fields
- [ ] missing required fields

## API authorization

- [ ] endpoint auth required
- [ ] object-level authorization
- [ ] function-level authorization
- [ ] old API version secured
- [ ] mobile API secured
- [ ] internal endpoint exposed
- [ ] debug endpoint exposed
- [ ] bulk endpoint secure
- [ ] export endpoint secure
- [ ] schema/documentation does not reveal secrets

---

# 23. Node.js and Express Checks

Response clue:

```http
X-Powered-By: Express
```

## Checklist

- [ ] `X-Powered-By` disabled
- [ ] Express version not exposed
- [ ] Trust proxy configured safely
- [ ] `X-Forwarded-For` not blindly trusted
- [ ] Secure cookies work behind proxy
- [ ] Body size limit configured
- [ ] JSON parser errors generic
- [ ] Prototype pollution protections
- [ ] Dependency versions current
- [ ] Source maps exposed?
- [ ] Stack traces exposed?
- [ ] Development mode enabled?
- [ ] Debug routes exposed?
- [ ] Static files expose source/config?
- [ ] `.env` inaccessible
- [ ] backup files inaccessible
- [ ] package lock exposed with useful version data?
- [ ] template engine escaping enabled
- [ ] user input not passed to dynamic code execution
- [ ] child processes avoid shell interpolation
- [ ] MongoDB filters sanitized
- [ ] session secret strong
- [ ] signed cookies use strong secret
- [ ] cookie parser consistency
- [ ] raw body verification correct for webhooks

## Proxy trust risks

If Express trusts attacker-controlled proxy headers, check possible impact on:

- rate limiting
- secure cookie decisions
- IP allowlists
- audit logs
- absolute URL generation
- password reset links

---

# 24. Information Disclosure

Look for:

- [ ] stack traces
- [ ] filesystem paths
- [ ] database errors
- [ ] SQL queries
- [ ] MongoDB collection names
- [ ] internal IPs
- [ ] internal hostnames
- [ ] cloud bucket names
- [ ] API keys
- [ ] access tokens
- [ ] session secrets
- [ ] source maps
- [ ] comments
- [ ] backup files
- [ ] `.git`
- [ ] `.env`
- [ ] config files
- [ ] debug endpoints
- [ ] metrics endpoints
- [ ] health endpoints
- [ ] dependency versions
- [ ] usernames/emails
- [ ] object IDs
- [ ] private documents
- [ ] verbose GraphQL errors

Technology disclosure alone is often low impact. Combine it with a real vulnerable version or sensitive data leak.

---

# 25. Error Handling

- [ ] Invalid JSON leaks stack trace
- [ ] Missing field leaks framework details
- [ ] Wrong type causes internal error
- [ ] Oversized input causes crash
- [ ] Database timeout leaks connection info
- [ ] Template error leaks source
- [ ] File parser error leaks path
- [ ] Authentication error reveals user existence
- [ ] Authorization error reveals object existence
- [ ] Different error codes form an oracle
- [ ] Error response cached
- [ ] Error page reflects unescaped input
- [ ] Error response sets/overwrites security cookie
- [ ] Debug details differ by host/header

---

# 26. Transport Security

- [ ] HTTP redirects to HTTPS
- [ ] No sensitive endpoint over HTTP
- [ ] HSTS present
- [ ] TLS certificate valid
- [ ] Mixed content absent
- [ ] Cookies use `Secure`
- [ ] WebSocket uses `wss://`
- [ ] OAuth redirect URI uses HTTPS
- [ ] Password reset links use HTTPS
- [ ] Internal absolute links do not downgrade
- [ ] Proxy headers cannot force HTTP reset links

---

# 27. Clickjacking

Check whether sensitive pages can be framed.

- [ ] `frame-ancestors` present
- [ ] `X-Frame-Options` present
- [ ] login page frameable
- [ ] payment page frameable
- [ ] account deletion frameable
- [ ] permission approval frameable
- [ ] OAuth consent frameable
- [ ] drag-and-drop action exploitable
- [ ] one-click sensitive action exists
- [ ] frame-busting script only protection?

A meaningful report needs a sensitive action that a victim can be tricked into performing.

---

# 28. WebSocket Checks

- [ ] authentication required
- [ ] session checked during connection
- [ ] authorization checked per message
- [ ] Origin validated
- [ ] cross-site WebSocket hijacking possible
- [ ] object IDs authorized
- [ ] subscription channels private
- [ ] user can join another tenant's room
- [ ] message sender identity server-controlled
- [ ] rate limiting
- [ ] oversized message handling
- [ ] reconnect token security
- [ ] revoked user disconnected
- [ ] debug events exposed

---

# 29. GraphQL Checks

- [ ] introspection enabled in production
- [ ] schema exposes sensitive operations
- [ ] field-level authorization
- [ ] object-level authorization
- [ ] nested resolver authorization
- [ ] batching bypasses rate limits
- [ ] aliases bypass rate limits
- [ ] query depth limited
- [ ] query complexity limited
- [ ] mutation authorization
- [ ] IDOR through global IDs
- [ ] hidden/deprecated fields accessible
- [ ] verbose errors
- [ ] subscriptions authorized
- [ ] tenant isolation enforced

---

# 30. Evidence Collection

For every promising issue save:

- [ ] Original request
- [ ] Original response
- [ ] Modified request
- [ ] Modified response
- [ ] Account role used
- [ ] Object owner
- [ ] Exact timestamp
- [ ] Target host
- [ ] Endpoint
- [ ] Reproduction steps
- [ ] Screenshot
- [ ] Screen recording if workflow complex
- [ ] Browser console output
- [ ] Cookie differences
- [ ] Before/after state
- [ ] Impact explanation
- [ ] Minimal data proof
- [ ] Suggested remediation

Redact:

- session tokens
- passwords
- API keys
- personal user data
- unrelated secrets

---

# 31. Severity and Impact

## Informational / Low

- `X-Powered-By` only
- soft 404 only
- missing generic security header without exploit
- self-XSS without social/privilege impact
- Base64 cookie with no trusted security decision
- verbose but non-sensitive error

## Medium

- CSRF on meaningful account setting
- reflected XSS with user interaction
- limited IDOR
- user enumeration with practical abuse
- rate limit weakness on sensitive flow
- open redirect in trusted workflow

## High

- stored XSS viewed by privileged users
- cross-user sensitive data IDOR
- account takeover path
- authorization bypass
- privilege escalation
- payment/business logic abuse
- sensitive CORS misconfiguration
- exploitable SSRF to internal services

## Critical

- remote code execution
- full admin takeover at scale
- unrestricted sensitive database exposure
- organization-wide compromise
- authentication bypass affecting all users
- cloud credential compromise with broad access

Always describe **actual demonstrated impact**, not only theoretical possibility.

---

# 32. Bug Report Template

```markdown
# Title

[Clear vulnerability] allows [attacker type] to [impact] via [endpoint/feature]

## Summary

A concise explanation of what is vulnerable and why it matters.

## Affected Asset

- Host:
- Endpoint:
- Method:
- Parameter/Cookie:
- Tested account role:

## Preconditions

- Required account:
- Required victim interaction:
- Required permissions:

## Steps to Reproduce

1. Log in as Account A.
2. Capture the following request.
3. Change `OBJECT_ID` from A's object to B's object.
4. Replay the request.
5. Observe that B's data is returned without authorization.

## Original Request

```http
...
```

## Modified Request

```http
...
```

## Response

```http
...
```

## Impact

Explain exactly what data/action becomes available and who is affected.

## Evidence

- Screenshot:
- Video:
- Request/response:
- Timestamp:

## Recommended Fix

Perform server-side authorization for every object access and derive the user/tenant identity from the authenticated session, not client-controlled identifiers.

## Notes

Only test accounts and minimum data were used.
```

---

# 33. Example Analysis of the Given Response

Given:

```http
HTTP/1.1 200 OK
X-Powered-By: Express
Set-Cookie: profile=eyJ1c2VybmFtZSI6IkR1bW15IiwiY291bnRyeSI6IklkayBQcm9iYWJseSBTb21ld2hlcmUgRHVtYiIsImNpdHkiOiJMYW1ldG93biIsIm51bSI6IjIifQ%3D%3D; Max-Age=900; Path=/; Expires=Mon, 02 Apr 2018 00:47:44 GMT; HttpOnly
Content-Type: text/html; charset=utf-8
Content-Length: 12
ETag: W/"c-8lfvj2TmiRRvB7K+JPws1w9h6aY"
Connection: close

<h1>404</h1>
```

## Immediate observations

### 1. Soft 404

Header says:

```http
200 OK
```

Body says:

```html
<h1>404</h1>
```

Check whether this affects caching, routing, monitoring, or authentication logic.

### 2. Client-readable profile structure

After URL + Base64 decoding, the cookie contains JSON similar to:

```json
{
  "username": "Dummy",
  "country": "Idk Probably Somewhere Dumb",
  "city": "Lametown",
  "num": "2"
}
```

Base64 is encoding, not encryption.

### 3. Most promising field

```json
"num": "2"
```

Test whether it identifies:

- user
- profile
- order
- tenant
- database record

### 4. Cookie flags

Present:

- `HttpOnly`

Missing from the shown response:

- `Secure`
- `SameSite`

Do not report missing flags alone without demonstrating impact.

### 5. Express disclosure

```http
X-Powered-By: Express
```

Usually informational unless combined with an exposed vulnerable version or other weakness.

### 6. 404 response sets profile cookie

Important questions:

- Does every random path set this cookie?
- Does it overwrite an authenticated user's cookie?
- Can attacker-controlled route/query data enter the cookie?
- Is the cookie trusted after login?
- Can it cause session/profile fixation?

## Recommended test order

1. Decode cookie
2. Change only `num`
3. Re-encode and replay
4. Change only `username`
5. Add `role` or `isAdmin`
6. Compare server-side behavior
7. Test before and after login
8. Test two separate accounts
9. Check if random paths overwrite cookie
10. Check cache behavior
11. Inspect output encoding if cookie fields render in HTML
12. Check CSRF only on real state-changing actions

## What counts as a real vulnerability?

Strong examples:

- Changing `num` reveals another user's profile
- Changing `num` exposes another user's orders
- Adding `isAdmin` unlocks admin functionality
- Cookie tampering changes server-side permissions
- Unknown route overwrites an authenticated security cookie
- Cross-user cached response leaks profile data
- Cookie-rendered value causes stored XSS in an admin page

Weak observations without demonstrated impact:

- Cookie is Base64
- `X-Powered-By` exists
- `Secure` missing on an HTTP-only lab
- Body says 404 while status is 200
- Username display changes only in the attacker's own browser

---

# 34. Final Testing Workflow

Use this repeatable workflow:

```text
1. Read scope
2. Capture baseline request
3. Understand every parameter/header/cookie
4. Decode structured values
5. Identify trust boundaries
6. Change one input at a time
7. Compare status, length, body, headers, timing
8. Repeat with two accounts
9. Verify server-side impact
10. Stop after minimum proof
11. Save clean evidence
12. Explain impact clearly
13. Suggest server-side remediation
```

## Trust Boundary Questions

For every value ask:

- Who creates this value?
- Can the browser modify it?
- Does the server verify it?
- Is it signed?
- Is it encrypted?
- Is it used for identity?
- Is it used for authorization?
- Is it used for price, role, tenant, or object selection?
- Can another endpoint interpret it differently?
- Can a proxy/cache interpret it differently?

## Final Mindset

> Encoded does not mean encrypted.  
> Hidden does not mean protected.  
> Frontend restriction does not mean server-side authorization.  
> A security header does not replace secure code.  
> A bug becomes bounty-worthy when you demonstrate real, in-scope impact.

---

## Personal Notes

```text
Target:
Program:
Scope:
Date:
Account A:
Account B:
Main Host:
API Host:
Interesting Cookies:
Interesting IDs:
Interesting Headers:
Potential Findings:
Confirmed Findings:
Report Status:
```
