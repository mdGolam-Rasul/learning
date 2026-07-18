# 🛡️ Authorized Bug Bounty Hunting Playbook — বাংলা Full Edition

> **৪০টি অধ্যায় + Appendices | Real-website safe testing workflow | Emoji সহ Markdown**
>
> **শেষ আপডেট:** ১৮ জুলাই ২০২৬  
> **শুধু নিজের system, training lab, অথবা explicit permission ও active bug bounty scope-এর target-এ ব্যবহার করবে।**

---


## 🆕 Practical Edition Update

এই edition-এ request/response, modified request, secure response, bug signal, hunter note ও stop condition সহ hands-on examples যোগ করা হয়েছে। সব host, account, token ও object ID কাল্পনিক।

## 📌 এই ফাইলে কী আছে

- Checklist কেন hunting-এ কাজে লাগে
- Real website-এ কীভাবে safe ও non-destructive test করবে
- Two-account IDOR/RBAC testing
- Auth, session, API, business logic, XSS, SSRF, cache, GraphQL, OAuth ও আরও অনেক area
- প্রতিটি chapter-এ expected secure behavior, bug signal, stop condition ও evidence guidance
- Ready-to-copy report, notebook ও `curl` templates
- আগের full response-analysis checklist Appendix C-তে সংরক্ষিত

## 🧭 Table of Contents

1. [🧭 অধ্যায় ১ — এই Playbook কীভাবে ব্যবহার করবে](#অধ্যায়-১-এই-playbook-কীভাবে-ব্যবহার-করবে)
2. [⚖️ অধ্যায় ২ — Scope, Permission ও Safe Harbor](#অধ্যায়-২-scope-permission-ও-safe-harbor)
3. [🧰 অধ্যায় ৩ — Safe Hunting Lab ও Test Accounts](#অধ্যায়-৩-safe-hunting-lab-ও-test-accounts)
4. [🗺️ অধ্যায় ৪ — Attack Surface Mapping](#অধ্যায়-৪-attack-surface-mapping)
5. [📨 অধ্যায় ৫ — HTTP Request/Response পড়া](#অধ্যায়-৫-http-requestresponse-পড়া)
6. [⚡ অধ্যায় ৬ — 60-Second Quick Triage](#অধ্যায়-৬-60-second-quick-triage)
7. [🔑 অধ্যায় ৭ — Authentication Testing](#অধ্যায়-৭-authentication-testing)
8. [📩 অধ্যায় ৮ — Password Reset, Email Change ও MFA](#অধ্যায়-৮-password-reset-email-change-ও-mfa)
9. [🍪 অধ্যায় ৯ — Session, Cookies ও JWT](#অধ্যায়-৯-session-cookies-ও-jwt)
10. [🪪 অধ্যায় ১০ — Authorization, IDOR ও RBAC](#অধ্যায়-১০-authorization-idor-ও-rbac)
11. [🔌 অধ্যায় ১১ — API: BOLA, BOPLA ও Mass Assignment](#অধ্যায়-১১-api-bola-bopla-ও-mass-assignment)
12. [🛡️ অধ্যায় ১২ — CSRF](#অধ্যায়-১২-csrf)
13. [🧼 অধ্যায় ১৩ — XSS ও Output Encoding](#অধ্যায়-১৩-xss-ও-output-encoding)
14. [🧪 অধ্যায় ১৪ — SQL/NoSQL Injection: Safe Detection](#অধ্যায়-১৪-sqlnosql-injection-safe-detection)
15. [🌐 অধ্যায় ১৫ — SSRF ও URL Fetch Features](#অধ্যায়-১৫-ssrf-ও-url-fetch-features)
16. [📤 অধ্যায় ১৬ — File Upload](#অধ্যায়-১৬-file-upload)
17. [📂 অধ্যায় ১৭ — Path Traversal ও Arbitrary File Read](#অধ্যায়-১৭-path-traversal-ও-arbitrary-file-read)
18. [🔄 অধ্যায় ১৮ — CORS](#অধ্যায়-১৮-cors)
19. [🧱 অধ্যায় ১৯ — Security Headers, CSP ও Clickjacking](#অধ্যায়-১৯-security-headers-csp-ও-clickjacking)
20. [🧊 অধ্যায় ২০ — Cache, CDN ও Web Cache Behavior](#অধ্যায়-২০-cache-cdn-ও-web-cache-behavior)
21. [⏱️ অধ্যায় ২১ — Rate Limiting ও Abuse Controls](#অধ্যায়-২১-rate-limiting-ও-abuse-controls)
22. [🧠 অধ্যায় ২২ — Business Logic](#অধ্যায়-২২-business-logic)
23. [🏁 অধ্যায় ২৩ — Race Conditions](#অধ্যায়-২৩-race-conditions)
24. [🛒 অধ্যায় ২৪ — E-commerce, Credits, Coupons ও Payments](#অধ্যায়-২৪-e-commerce-credits-coupons-ও-payments)
25. [↪️ অধ্যায় ২৫ — Open Redirect ও URL Handling](#অধ্যায়-২৫-open-redirect-ও-url-handling)
26. [🏠 অধ্যায় ২৬ — Host Header ও Password Reset Poisoning](#অধ্যায়-২৬-host-header-ও-password-reset-poisoning)
27. [🔁 অধ্যায় ২৭ — WebSocket](#অধ্যায়-২৭-websocket)
28. [🕸️ অধ্যায় ২৮ — GraphQL](#অধ্যায়-২৮-graphql)
29. [🔐 অধ্যায় ২৯ — OAuth, OIDC ও SAML](#অধ্যায়-২৯-oauth-oidc-ও-saml)
30. [🕵️ অধ্যায় ৩০ — Information Disclosure ও Client-Side Secrets](#অধ্যায়-৩০-information-disclosure-ও-client-side-secrets)
31. [🚨 অধ্যায় ৩১ — Error Handling, Status Code ও Routing](#অধ্যায়-৩১-error-handling-status-code-ও-routing)
32. [☁️ অধ্যায় ৩২ — Subdomain, DNS ও Cloud Storage Recon](#অধ্যায়-৩২-subdomain-dns-ও-cloud-storage-recon)
33. [📸 অধ্যায় ৩৩ — Evidence Collection](#অধ্যায়-৩৩-evidence-collection)
34. [📊 অধ্যায় ৩৪ — Severity ও Impact](#অধ্যায়-৩৪-severity-ও-impact)
35. [📝 অধ্যায় ৩৫ — Bug Report Template](#অধ্যায়-৩৫-bug-report-template)
36. [🗓️ অধ্যায় ৩৬ — Daily Hunting Workflow](#অধ্যায়-৩৬-daily-hunting-workflow)
37. [🏆 অধ্যায় ৩৭ — Hunting Priority Matrix](#অধ্যায়-৩৭-hunting-priority-matrix)
38. [🧯 অধ্যায় ৩৮ — False Positive Eliminator](#অধ্যায়-৩৮-false-positive-eliminator)
39. [🧪 অধ্যায় ৩৯ — Lab বনাম Real Website Boundary](#অধ্যায়-৩৯-lab-বনাম-real-website-boundary)
40. [📒 অধ্যায় ৪০ — Ready-to-Copy Hunting Notebook](#অধ্যায়-৪০-ready-to-copy-hunting-notebook)
41. [🧾 Appendix A — Safe `curl` Examples](#appendix-a-safe-curl-examples)
42. [📚 Appendix B — Reference Map](#appendix-b-reference-map)

---


<!-- PRACTICAL-EXAMPLES-START -->

## 🧪 Practical Example পড়ার নিয়ম

নিচের উদাহরণগুলো **বাস্তবধর্মী কিন্তু সম্পূর্ণ কাল্পনিক**। `target.example`, Account A, Account B এবং test object-এর জায়গায় শুধু authorized bug bounty program-এর in-scope asset ও নিজের test data ব্যবহার করবে।

প্রতিটি example-এ একই pattern রাখা হয়েছে:

| অংশ | অর্থ |
|---|---|
| 🎯 Goal | কোন security control যাচাই করবে |
| 📥 Baseline | স্বাভাবিক request |
| ✏️ Modify | শুধু কোন value বদলাবে |
| ✅ Secure response | নিরাপদ server কী করবে |
| 🚨 Bug signal | কী দেখলে vulnerability সন্দেহ করবে |
| 📝 Hunter note | নোটে কী লিখবে |
| 🛑 Stop | কখন আর এগোবে না |

### Test account convention

```text
Account A: researcher-a@example.test
Account B: researcher-b@example.test
Low role: viewer
Higher test role: manager
Object A: A-1001
Object B: B-2002
```

### Redaction convention

```http
Cookie: session=REDACTED_A
Authorization: Bearer REDACTED_A
```

> Request/response copied করার সময় session, reset token, API key, email, phone ও personal data অবশ্যই redact করবে।

<!-- PRACTICAL-EXAMPLES-END -->


## 🚨 Mandatory Safety Banner

এই document exploitation manual নয়। Production target-এ bulk scanning, credential attacks, data extraction, internal network probing, persistence, malware, service disruption বা অন্য user-এর data access করা যাবে না। Program policy conflict করলে program policy-ই final।

---

---

# 🧭 অধ্যায় ১ — এই Playbook কীভাবে ব্যবহার করবে

এই গাইডটি শুধু checkbox টিক দেওয়ার জন্য নয়। প্রতিটি checklist item-কে একটি **হান্টিং hypothesis** হিসেবে ব্যবহার করবে।

### ✅ পাঁচ ধাপের Hunting Loop

1. **Observe:** অ্যাপটি কী করছে—request, response, cookie, role, ID, redirect, cache।
2. **Hypothesize:** “Server কি client-এর পাঠানো ID/role/price বিশ্বাস করছে?”
3. **Safe Test:** নিজের test account ও নিজের object ব্যবহার করে একটি মাত্র variable বদলাও।
4. **Compare:** original বনাম modified response-এর status, body, length, headers ও side effect তুলনা করো।
5. **Prove Impact:** minimum proof সংগ্রহ করে সঙ্গে সঙ্গে থামো।

### 🧪 উদাহরণ

ধরো Account A-এর order endpoint:

```http
GET /api/orders/ORD-A-100
Cookie: session=A_SESSION
```

Hypothesis: order ID বদলালে অন্য account-এর order দেখা যায় কি?

Safe test:

```http
GET /api/orders/ORD-B-200
Cookie: session=A_SESSION
```

`ORD-B-200` অবশ্যই তোমার নিজের Account B-এর order হবে। কোনো real user-এর ID guess বা enumerate করবে না।

### 📝 প্রতিটি test-এর note format

```text
Feature:
Endpoint:
Account/Role:
Original request:
Single change made:
Expected secure behavior:
Actual behavior:
Impact:
Evidence:
Stopped at:
```

### 🎯 Checklist-এর আসল value

- Checklist তোমাকে coverage দেয়।
- Comparison তোমাকে signal দেয়।
- Two-account testing authorization bug বের করে।
- Business context impact বোঝায়।
- পরিষ্কার evidence report accept হওয়ার chance বাড়ায়।


---

# ⚖️ অধ্যায় ২ — Scope, Permission ও Safe Harbor

Real website-এ test করার আগে program policy-ই তোমার সর্বোচ্চ নিয়ম।

### ✅ শুরু করার আগে

- [ ] Domain, subdomain, API host ও mobile backend in-scope কি না
- [ ] Testing window বা maintenance restriction আছে কি না
- [ ] Automated scanner অনুমোদিত কি না
- [ ] Rate limit, brute force, race condition বা upload testing-এর আলাদা নিয়ম আছে কি না
- [ ] Third-party payment, support chat, analytics, CDN বা identity provider out-of-scope কি না
- [ ] Social engineering, DoS, spam, physical testing নিষিদ্ধ কি না
- [ ] Safe harbor statement আছে কি না
- [ ] Report করার official channel জানা আছে কি না

### 🚫 কখন সঙ্গে সঙ্গে থামবে

- অন্য real user-এর personal data দেখা গেলে
- Production transaction, email/SMS flood বা charge হওয়ার ঝুঁকি থাকলে
- Service slow, unstable বা error rate বাড়তে থাকলে
- Out-of-scope host-এ redirect বা callback গেলে
- Admin-level write action সম্ভব মনে হলে
- Secret/token পেয়ে গেলে—token ব্যবহার না করে exposure report করবে

### 🛡️ Minimum-impact rule

Bug প্রমাণে যতটুকু দরকার ততটুকুই করবে। Data download, deletion, persistence, lateral movement, bulk enumeration বা service disruption করবে না।


---

# 🧰 অধ্যায় ৩ — Safe Hunting Lab ও Test Accounts

### Recommended setup

- Browser profile ১: Account A
- Browser profile ২: Account B
- একটি low-privilege account
- Program দিলে একটি privileged/test-admin account
- Burp Suite বা অন্য intercepting proxy
- Browser DevTools
- `curl` বা HTTP client
- একটি note file ও timestamp convention

### 🏷️ Test marker

প্রতিটি benign input-এ unique marker ব্যবহার করো:

```text
bbtest-fahim-20260718-001
```

এতে log, response, email বা cache-এ নিজের test সহজে চিনতে পারবে।

### 🔐 Token handling

- Screenshot-এ session token redact করো
- Report attachment-এ full cookie দিও না
- Test শেষ হলে logout করো
- Password reset token ও magic link পুনরায় ব্যবহার না করে invalidate করো
- Account A/B-এর object ID আলাদা করে note করো

### 📁 Folder structure

```text
target-name/
├── scope.md
├── endpoints.md
├── accounts.md
├── requests/
├── screenshots/
├── findings/
└── report-drafts/
```


---

# 🗺️ অধ্যায় ৪ — Attack Surface Mapping

Vulnerability খোঁজার আগে feature map বানানো সবচেয়ে লাভজনক কাজগুলোর একটি।

### কোথা থেকে endpoint পাবে

- Browser Network tab
- HTML forms ও links
- JavaScript bundle
- Mobile/API traffic—শুধু scope অনুমতি দিলে
- OpenAPI/Swagger documentation
- GraphQL endpoint
- WebSocket connection
- Email links
- Password reset ও invitation flow
- Export/import, upload, webhook ও integration settings

### Feature map template

| Feature | Endpoint | Method | Auth required | Object ID | Role-sensitive | State-changing |
|---|---|---:|---|---|---|---|
| Profile | `/api/me` | GET | Yes | User ID | Low | No |
| Order | `/api/orders/{id}` | GET | Yes | Order ID | High | No |
| Team member | `/api/org/{id}/members` | POST | Yes | Org ID | High | Yes |

### High-value attack surface

1. Admin/organization/team features
2. Billing, wallet, credits, coupons
3. File upload/import/export
4. Password reset, invitation, email change
5. API endpoints with IDs
6. Webhooks, URL fetcher, PDF/image generator
7. Search, filters, report builders
8. Legacy or alternate API versions


---

# 📨 অধ্যায় ৫ — HTTP Request/Response পড়া

একটি request-কে পাঁচটি অংশে ভাঙো:

```http
POST /api/team/123/member HTTP/1.1
Host: target.example
Cookie: session=REDACTED
Content-Type: application/json

{"userId":"456","role":"viewer"}
```

### কী দেখবে

- **Method:** GET/POST/PUT/PATCH/DELETE
- **Path:** object ID, tenant ID, file name, version
- **Headers:** cookie, authorization, origin, content type, host
- **Body:** hidden fields, price, role, status, ownership
- **Response:** status, body, headers, side effect

### Single-variable rule

একবারে একটি জিনিস বদলাও:

- শুধু object ID
- শুধু HTTP method
- শুধু role field
- শুধু content type
- শুধু cookie
- শুধু origin

একাধিক পরিবর্তন একসঙ্গে করলে bug-এর root cause বোঝা কঠিন হয়।


## 🧪 Practical Example — Profile update request বিশ্লেষণ

### 🎯 Goal

Client কোন field পাঠাচ্ছে এবং server কোন field বিশ্বাস করছে—এটি বোঝা।

### 📥 Baseline request

```http
PATCH /api/v1/profile HTTP/1.1
Host: target.example
Cookie: session=REDACTED_A
Content-Type: application/json

{
  "displayName": "Fahim Test",
  "timezone": "Asia/Dhaka"
}
```

### 📤 Baseline response

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "id": "usr_A",
  "displayName": "Fahim Test",
  "timezone": "Asia/Dhaka",
  "role": "viewer"
}
```

### ✏️ Modify

একবারে শুধু একটি harmless unknown field যোগ করো:

```json
{
  "displayName": "Fahim Test",
  "timezone": "Asia/Dhaka",
  "bbNote": "bbtest-001"
}
```

### ✅ Secure response

Server unknown field ignore/reject করবে এবং security-sensitive state পরিবর্তন করবে না।

```http
HTTP/1.1 400 Bad Request

{"error":"Unknown property: bbNote"}
```

অথবা `200 OK` হলেও response/state-এ `bbNote` save হবে না।

### 🚨 Bug signal

- Request-এ না থাকা sensitive field response-এ আসে
- Unknown fields silently persist হয়
- Client-supplied `ownerId`, `role`, `status`, `price` server trust করে
- UI-তে unavailable action API request বদলে করা যায়

### 📝 Hunter note

```text
Feature: Profile update
Endpoint: PATCH /api/v1/profile
Baseline: displayName + timezone
Changed: added only bbNote
Expected: reject/ignore unknown field
Actual: [লিখবে]
Side effect checked from UI: yes/no
```


---

# ⚡ অধ্যায় ৬ — 60-Second Quick Triage

নতুন response দেখলেই:

- [ ] Status code ও body একই অর্থ প্রকাশ করছে?
- [ ] Login ছাড়া endpoint খুলছে?
- [ ] Account A থেকে Account B-এর object access করা যায়?
- [ ] Low role থেকে admin-only action করা যায়?
- [ ] Cookie নতুন করে set/rotate হচ্ছে?
- [ ] Sensitive data response-এ অতিরিক্ত এসেছে?
- [ ] User input encode না হয়ে reflect হয়েছে?
- [ ] Error message stack trace বা internal path দেখাচ্ছে?
- [ ] `Cache-Control`, `Vary`, `Age`, `X-Cache` কী বলছে?
- [ ] CORS origin validation ঠিক আছে?
- [ ] State-changing request CSRF protection ব্যবহার করছে?
- [ ] Request replay করলে action duplicate হয়?
- [ ] Client-supplied `price`, `role`, `status`, `ownerId` server বিশ্বাস করছে?
- [ ] Alternate API version বা mobile endpoint দুর্বল?


## 🧪 Practical Example — একটি response 60 সেকেন্ডে triage

### 📥 Captured response

```http
HTTP/1.1 200 OK
Content-Type: application/json
Cache-Control: public, max-age=300
Access-Control-Allow-Origin: https://random.example
Access-Control-Allow-Credentials: true
Set-Cookie: session=abc123; Path=/

{
  "userId":"usr_A",
  "email":"researcher-a@example.test",
  "plan":"pro"
}
```

### 🔎 60-second observation

```text
[!] Authenticated personal response কিন্তু Cache-Control: public
[!] Credentialed CORS untrusted origin-এ allowed
[!] Session cookie-তে Secure/HttpOnly/SameSite দেখা যাচ্ছে না
[?] CORS browser-এ বাস্তবে sensitive response readable কি?
[?] CDN shared cache-এ অন্য account response পায় কি?
```

### 🧭 এরপর কী করবে

1. প্রথমে Account A ও B দিয়ে cache isolation check।
2. Controlled origin থেকে browser CORS test।
3. Cookie flags browser storage panel-এ verify।
4. একসঙ্গে তিনটি finding report না করে প্রতিটি root cause আলাদা validate।

### 🛑 Stop

Account B-তে real user data দেখা গেলে body আর explore/download করবে না; minimum screenshot ও redacted response নিয়ে থামবে।


---

# 🔑 অধ্যায় ৭ — Authentication Testing

### Hunting value: ⭐⭐⭐⭐☆

Authentication bug account takeover-এ যেতে পারে, কিন্তু testing অত্যন্ত controlled হতে হবে।

### কোথায় test করবে

- Login
- Signup
- Magic link
- Remember-me
- Device trust
- Email/phone verification
- Alternate login channel
- SSO entry point

### Safe real-site workflow

1. নিজের valid ও invalid username দিয়ে ৩–৫টি request compare করো।
2. Status, message, response length ও timing-এ user enumeration signal আছে কি দেখো।
3. Login-এর আগে ও পরে session cookie বদলেছে কি দেখো।
4. Logout-এর পরে পুরোনো session replay করে নিশ্চিত হও invalid হয়েছে।
5. Password change-এর পরে অন্য browser-এর session invalid হয় কি দেখো।
6. কোনো rate-limit test করলে program policy অনুযায়ী খুব অল্প attempt করো।

### Secure behavior

- Generic error message
- Login-এর পরে session rotation
- Logout/password change-এর পরে relevant session invalidation
- Consistent throttling
- Sensitive token URL বা log-এ না থাকা

### Bug signals

- Valid username আলাদা message/timing দেয়
- Pre-login session login-এর পরও unchanged
- Logout করা token এখনও কাজ করে
- Disabled account alternate endpoint দিয়ে login করতে পারে
- Different channel-এ weaker authentication

### Stop conditions

Credential stuffing, password spraying, real-user account testing বা CAPTCHA bypass করবে না।


## 🧪 Practical Example ১ — Username enumeration

### 📥 Invalid username

```http
POST /login HTTP/1.1
Content-Type: application/json

{"email":"not-created-001@example.test","password":"WrongPass123!"}
```

```http
HTTP/1.1 401 Unauthorized

{"error":"Account does not exist"}
```

### 📥 Existing own test account

```http
POST /login HTTP/1.1
Content-Type: application/json

{"email":"researcher-a@example.test","password":"WrongPass123!"}
```

```http
HTTP/1.1 401 Unauthorized

{"error":"Incorrect password"}
```

### 🚨 Bug signal

Message, status, response length বা stable timing difference দিয়ে account existence জানা যাচ্ছে।

### ✅ Secure response

```http
HTTP/1.1 401 Unauthorized

{"error":"Invalid email or password"}
```

### 📝 Hunter note

```text
Only my own known account and one synthetic nonexistent address used.
No real-user email tested.
Difference is repeatable 3/3 times.
```

---

## 🧪 Practical Example ২ — Session rotation

### Login-এর আগে

```http
GET /login HTTP/1.1
Cookie: session=PRELOGIN_123
```

### Successful login

```http
POST /login HTTP/1.1
Cookie: session=PRELOGIN_123
Content-Type: application/json

{"email":"researcher-a@example.test","password":"REDACTED"}
```

### ✅ Secure response

```http
HTTP/1.1 302 Found
Set-Cookie: session=NEW_RANDOM_SESSION; Secure; HttpOnly; SameSite=Lax
```

### 🚨 Bug signal

Login-এর পরে session value একই থাকে এবং attacker-set pre-login session authenticated হয়ে যায়।

### 🛑 Stop

Session fixation impact নিজের দুই browser profile-এ প্রমাণ করবে; অন্য কাউকে crafted session link পাঠাবে না।


---

# 📩 অধ্যায় ৮ — Password Reset, Email Change ও MFA

### Hunting value: ⭐⭐⭐⭐⭐

Reset ও account recovery flow প্রায়ই high-impact bug দেয়।

### Password reset safe tests

- [ ] Token single-use কি না
- [ ] Token expiry কার্যকর কি না
- [ ] নতুন reset request পুরোনো token invalidate করে কি না
- [ ] Password বদলের পরে active sessions invalidate হয় কি না
- [ ] Reset link-এর host trusted source থেকে তৈরি হয় কি না
- [ ] Token referrer, analytics বা third-party resource-এ leak হয় কি না
- [ ] Account enumeration হয় কি না
- [ ] Reset action account identity server-side bind করে কি না

### Email change tests

নিজের Account A-তে:

1. Email change initiate করো।
2. Confirmation কোন old/new address-এ যায় note করো।
3. Request body-তে `userId`, `email`, `verified` field বদলানোর সুযোগ আছে কি দেখো।
4. Session re-authentication দরকার কি না দেখো।
5. Confirmation link অন্য account/session-এ usable কি না পরীক্ষা করো—শুধু নিজের A/B account।

### MFA tests

- পুরোনো OTP reuse হয় কি
- OTP অন্য session/account-এ কাজ করে কি
- Recovery code single-use কি
- MFA disable করতে password/re-auth দরকার কি
- Backup flow primary MFA-এর চেয়ে দুর্বল কি

### নিষিদ্ধ boundary

OTP brute force, SMS/email flooding বা অন্য ব্যক্তির reset flow trigger করবে না।


## 🧪 Practical Example — Reset token replay

### 🎯 Setup

নিজের Account A-এর password reset link নাও:

```text
https://target.example/reset?token=REDACTED_TOKEN_A
```

### 📥 First use

```http
POST /api/password/reset HTTP/1.1
Content-Type: application/json

{
  "token":"REDACTED_TOKEN_A",
  "newPassword":"New-Test-Pass-01!"
}
```

```http
HTTP/1.1 200 OK

{"message":"Password updated"}
```

### ✏️ Modify

একই token আবার নিজের Account A-তে নতুন password দিয়ে replay করো।

```http
POST /api/password/reset HTTP/1.1
Content-Type: application/json

{
  "token":"REDACTED_TOKEN_A",
  "newPassword":"New-Test-Pass-02!"
}
```

### ✅ Secure response

```http
HTTP/1.1 400 Bad Request

{"error":"Token is invalid or already used"}
```

### 🚨 Bug signal

Second request-ও `200 OK` এবং password আবার পরিবর্তিত।

### 📝 Hunter note

```text
Token issued: 01:05 UTC
First use: 01:07 UTC — success
Second use: 01:08 UTC — success
Only my Account A was affected
Old sessions after reset: valid/invalid
```

### 🛑 Stop

Reset token অন্য account-এ bind হয় কি test করতে Account B-এর নিজের token ব্যবহার করবে। Real-user reset request trigger করবে না।


---

# 🍪 অধ্যায় ৯ — Session, Cookies ও JWT

### Hunting value: ⭐⭐⭐⭐☆

### Cookie checklist

- [ ] `Secure`
- [ ] `HttpOnly`
- [ ] উপযুক্ত `SameSite`
- [ ] সীমিত `Domain`
- [ ] উপযুক্ত `Path`
- [ ] যুক্তিসঙ্গত expiry
- [ ] Login ও privilege change-এ rotation
- [ ] Logout-এ invalidation
- [ ] Sensitive role/price/ownership client-side cookie-তে trusted নয়
- [ ] Duplicate cookie ambiguity নেই
- [ ] সম্ভব হলে `__Host-`/`__Secure-` prefix

### Safe tampering workflow

1. Cookie delete করে request পাঠাও।
2. Cookie-এর একটি benign character বদলাও।
3. Account A cookie দিয়ে Account B endpoint নয়—বরং own object matrix ব্যবহার করো।
4. Server modified cookie reject করে কি দেখো।
5. Cookie decode হলে data শুধু encoded নাকি signed/encrypted বুঝো।
6. Signature brute-force করবে না।

### JWT review

- Header ও payload decode করা নিরাপদ।
- `exp`, `nbf`, `aud`, `iss`, `sub`, role/tenant claims দেখো।
- Expired token reject হয় কি।
- Logout/password change-এর পরে token policy কী।
- Algorithm-confusion বা signature bypass attempt production-এ না করে lab-এ শেখো, যদি program স্পষ্ট অনুমতি না দেয়।

### Finding example

Client-side JWT claim-এ `role: user` বদলে server যদি signature যাচাই ছাড়া admin response দেয়, সেটি critical authorization failure। Minimum proof নিয়ে থামবে।


## 🧪 Practical Example — Logout invalidation

### 📥 Login করা অবস্থায়

```http
GET /api/me HTTP/1.1
Cookie: session=REDACTED_A
```

```http
HTTP/1.1 200 OK

{"id":"usr_A","email":"researcher-a@example.test"}
```

### 📥 Logout

```http
POST /logout HTTP/1.1
Cookie: session=REDACTED_A
```

```http
HTTP/1.1 204 No Content
Set-Cookie: session=; Max-Age=0; Path=/
```

### ✏️ Modify

Browser cookie clear হওয়ার পর proxy history থেকে **পুরোনো একই cookie** দিয়ে `/api/me` replay করো।

### ✅ Secure response

```http
HTTP/1.1 401 Unauthorized

{"error":"Session expired"}
```

### 🚨 Bug signal

Old session `200 OK` দেয় এবং protected action করা যায়।

### 📝 Note

শুধু browser-side cookie deletion যথেষ্ট নয়; server-side session invalidate হয়েছে কি replay দিয়ে verify করতে হবে।

---

## 🧪 Practical Example — JWT expiry

Decoded payload:

```json
{
  "sub":"usr_A",
  "role":"viewer",
  "iat":1784332200,
  "exp":1784332500,
  "aud":"web-app",
  "iss":"https://auth.target.example"
}
```

Expiry পেরিয়ে request করলে secure server `401` দেবে। Payload edit করে role বদলে test production-এ করবে না, যদি program explicit permission না দেয়।


---

# 🪪 অধ্যায় ১০ — Authorization, IDOR ও RBAC

### Hunting value: ⭐⭐⭐⭐⭐

Bug bounty-তে সবচেয়ে ধারাবাহিক high-value area হলো broken access control।

### Three-way matrix

| Test | Session | Object/Action | Expected |
|---|---|---|---|
| Unauthenticated | None | A-এর resource | 401/redirect |
| Horizontal | A | B-এর own test resource | 403/404 |
| Vertical | Low role | Admin action | 403 |

### Safe two-account workflow

1. Account A ও B-তে একই ধরনের object তৈরি করো।
2. A-এর request capture করো।
3. শুধু object ID-টি B-এর ID দিয়ে বদলাও।
4. Read, update, delete আলাদা করে test করো।
5. Path, query, JSON body ও header-এ থাকা সব ID আলাদা করে পরীক্ষা করো।
6. Response ছাড়াও actual side effect B account থেকে verify করো।
7. Minimum evidence পেলে থামো।

### Common authorization locations

- `/users/{id}`
- `/orders/{id}`
- `/org/{orgId}/members/{memberId}`
- `ownerId`, `tenantId`, `accountId`
- Export/download links
- Invoice/PDF
- Invitation IDs
- Hidden admin endpoints
- Mobile/legacy API

### Bug signals

- 200 response-এ অন্য account-এর data
- 204/200 এবং B object পরিবর্তিত
- UI button hidden, কিন্তু direct API কাজ করে
- Low role arbitrary role assign করতে পারে
- Object ID বদলানোর পর server ownership check করে না

### False positive

Public object, shared team resource, intentionally guessable ID বা same organization access সবসময় IDOR নয়। Program model বুঝতে হবে।


## 🧪 Practical Example — Horizontal IDOR

### 🎯 Setup

- Account A creates order `ORD-A-1001`
- Account B creates order `ORD-B-2002`

### 📥 Baseline: Account A নিজের order

```http
GET /api/orders/ORD-A-1001 HTTP/1.1
Cookie: session=REDACTED_A
```

```http
HTTP/1.1 200 OK

{
  "id":"ORD-A-1001",
  "ownerId":"usr_A",
  "item":"Test Notebook"
}
```

### ✏️ Modify

শুধু path ID বদলাও; session A-ই থাকবে।

```http
GET /api/orders/ORD-B-2002 HTTP/1.1
Cookie: session=REDACTED_A
```

### ✅ Secure response

```http
HTTP/1.1 404 Not Found
```

অথবা:

```http
HTTP/1.1 403 Forbidden
```

### 🚨 Vulnerable response

```http
HTTP/1.1 200 OK

{
  "id":"ORD-B-2002",
  "ownerId":"usr_B",
  "item":"Test Mouse"
}
```

### 🔁 Write authorization test

Read IDOR confirm হলে destructive delete না করে reversible field test:

```http
PATCH /api/orders/ORD-B-2002/note HTTP/1.1
Cookie: session=REDACTED_A
Content-Type: application/json

{"note":"bbtest-owned-by-B"}
```

Account B UI থেকে note changed কি verify করে সঙ্গে সঙ্গে revert।

### 📝 Hunter note

```text
Session used: Account A
Object owner: Account B, controlled by researcher
Only changed: order ID
Expected: 403/404
Actual: 200 with B-owned order
No real-user object accessed
```


---

# 🔌 অধ্যায় ১১ — API: BOLA, BOPLA ও Mass Assignment

### Hunting value: ⭐⭐⭐⭐⭐

API-তে server প্রায়ই client-supplied object ID ও property গ্রহণ করে; এখানেই authorization ও mass-assignment bug আসে।

### BOLA test

Account A token দিয়ে Account B-এর own test object ID request করো। Path, query, body ও nested object—সব জায়গার ID দেখো।

### BOPLA / excessive properties

Response-এ UI-তে না দেখানো field আছে কি:

- internal role
- billing plan
- password-reset state
- private email/phone
- moderation flag
- secret key metadata
- tenant configuration

শুধু response দেখে report করার আগে বাস্তব sensitivity ও authorization expectation যাচাই করো।

### Mass assignment safe workflow

Original:

```json
{"displayName":"Researcher"}
```

Harmless extra field দিয়ে test:

```json
{"displayName":"Researcher","theme":"dark"}
```

তারপর request schema/response থেকে সম্ভাব্য sensitive field চিহ্নিত করো। Production-এ `role=admin`, `balance`, `verified` ইত্যাদি পরিবর্তন করে destructive proof না করে, নিজের account-এ minimum reversible test করো এবং side effect হলে সঙ্গে সঙ্গে revert করো।

### API version comparison

- `/api/v1/...`
- `/api/v2/...`
- web বনাম mobile endpoint
- GraphQL mutation বনাম REST action

এক version-এ authorization থাকলেও অন্য version-এ নাও থাকতে পারে।


## 🧪 Practical Example ১ — Nested object BOLA

### 📥 Baseline

```http
GET /api/orgs/org_A/projects/proj_A HTTP/1.1
Authorization: Bearer REDACTED_A
```

### ✏️ Modify

শুধু nested project ID Account B-এর project ID করো:

```http
GET /api/orgs/org_A/projects/proj_B HTTP/1.1
Authorization: Bearer REDACTED_A
```

Server শুধু `org_A` check করে কিন্তু `proj_B` ownership না দেখলে BOLA হতে পারে।

---

## 🧪 Practical Example ২ — Mass assignment

### Baseline

```http
PATCH /api/members/me HTTP/1.1
Authorization: Bearer REDACTED_A
Content-Type: application/json

{"displayName":"Fahim Test"}
```

### Safe discovery modification

```http
PATCH /api/members/me HTTP/1.1
Authorization: Bearer REDACTED_A
Content-Type: application/json

{
  "displayName":"Fahim Test",
  "department":"bbtest"
}
```

Response-এ server accepted properties দেখো।

### Sensitive field test boundary

নিজের isolated test organization-এ reversible role `viewer → editor` only তখনই test করবে যখন program role-testing অনুমতি দেয় এবং অন্য user/tenant impact নেই।

```json
{
  "displayName":"Fahim Test",
  "role":"editor"
}
```

### ✅ Secure behavior

```http
HTTP/1.1 403 Forbidden

{"error":"role is not client-editable"}
```

### 🚨 Bug signal

Low-privilege user sensitive property পরিবর্তন করে server-side privilege পায়।


---

# 🛡️ অধ্যায় ১২ — CSRF

### Hunting value: ⭐⭐⭐☆☆

CSRF তখন meaningful যখন victim-এর browser credential automatically পাঠায় এবং action-এর impact আছে।

### কোথায় দেখবে

- Email/password change
- Add member
- API key create/delete
- Payment method
- Profile/security settings
- OAuth link/unlink
- Account deletion

### Safe workflow

1. State-changing request capture করো।
2. CSRF token আছে কি দেখো।
3. Token session/user/action-এর সঙ্গে bind করা কি না।
4. Token বাদ দিলে request reject হয় কি।
5. Wrong token বা Account B token reject হয় কি।
6. `Origin`/`Referer` validation আছে কি।
7. Cookie `SameSite` behavior বিবেচনা করো।
8. নিজের account-এ harmless change দিয়ে browser-based proof করো।

### Not automatically a bug

- শুধু CSRF token নেই
- API `Authorization: Bearer` header ব্যবহার করে এবং cross-site form সেটি পাঠাতে পারে না
- Action idempotent/read-only
- SameSite/Origin protection বাস্তবে exploit বন্ধ করে

### Stop condition

অন্য user-কে link পাঠিয়ে test করবে না; নিজের browser/profile-এ proof করবে।


## 🧪 Practical Example — Harmless preference change

### 📥 Captured request

```http
POST /settings/language HTTP/1.1
Host: target.example
Cookie: session=REDACTED_A
Content-Type: application/x-www-form-urlencoded

language=bn
```

Request-এ CSRF token নেই।

### Safe local PoC

শুধু নিজের browser/account-এর harmless language setting-এর জন্য local file:

```html
<!doctype html>
<html lang="en">
  <body>
    <form action="https://target.example/settings/language"
          method="POST">
      <input type="hidden" name="language" value="en">
      <button type="submit">Run own-account test</button>
    </form>
  </body>
</html>
```

নিজে button click করো; auto-submit বা অন্য user-কে page পাঠাবে না।

### ✅ Secure behavior

Server `Origin`/`Referer`, SameSite cookie বা anti-CSRF token দিয়ে request reject করবে।

```http
HTTP/1.1 403 Forbidden

{"error":"Invalid CSRF token"}
```

### 🚨 Bug signal

Cross-site form নিজের authenticated session ব্যবহার করে setting change করে।

### 📝 Note

Harmless preference CSRF confirm করার পর email/password/delete-এর মতো destructive action execute করবে না; potential impact reasoning report-এ explain করবে।


---

# 🧼 অধ্যায় ১৩ — XSS ও Output Encoding

### Hunting value: ⭐⭐⭐⭐☆

### প্রথমে reflection test

```text
bb-xss-20260718<>"'
```

এটি query, form, JSON, filename, profile field বা message-এ পাঠিয়ে দেখো কোথায় reflect বা store হচ্ছে।

### Context বুঝো

- HTML text
- HTML attribute
- JavaScript string
- URL
- CSS
- JSON inside HTML
- DOM sink

### Safe workflow

1. Unique marker পাঠাও।
2. Raw response ও rendered DOM compare করো।
3. Encoding/escaping দেখো।
4. CSP ও browser console দেখো।
5. Program অনুমতি দিলে harmless browser-only proof ব্যবহার করো।
6. Cookie, localStorage, CSRF token বা user data পড়বে/পাঠাবে না।
7. Stored হলে শুধু নিজের test content ও account ব্যবহার করো।

### Secure behavior

Context-appropriate encoding, safe DOM API, sanitization এবং restrictive CSP।

### False positives

- Input source code-এ encoded
- `textContent` দিয়ে render
- JSON response কিন্তু HTML execution context নয়
- CSP সব execution বন্ধ করছে—তবু root cause ও bypass সম্ভাবনা বুঝতে হবে


## 🧪 Practical Example — Reflection context বোঝা

### 📥 Request

```http
GET /search?q=bbtest-001%3C%22%27 HTTP/1.1
Host: target.example
```

Decoded marker:

```text
bbtest-001<"'
```

### ✅ Secure HTML response

```html
<p>Search results for: bbtest-001&lt;&quot;&#x27;</p>
```

### 🚨 Suspicious response

```html
<p>Search results for: bbtest-001<"'</p>
```

Raw characters HTML context-এ ফিরেছে; এখন browser DOM inspect করে context বুঝবে।

### Safe proof rule

প্রথমে inert marker। Program explicit XSS proof অনুমতি দিলে শুধু visible, harmless effect ব্যবহার করবে; cookie/token/data exfiltration করবে না।

### 📝 Hunter note

```text
Source: q query parameter
Sink: server-rendered HTML text node
Raw response encoding: none
Rendered DOM: [লিখবে]
CSP: [লিখবে]
Stored/reflected/DOM: reflected
```

### False-positive example

Response JSON:

```json
{"query":"bbtest-001<\"'"}
```

এটি নিজে XSS নয়; JSON কোথায় unsafeভাবে DOM-এ ঢুকছে সেটি প্রমাণ করতে হবে।


---

# 🧪 অধ্যায় ১৪ — SQL/NoSQL Injection: Safe Detection

### Hunting value: ⭐⭐⭐⭐☆

Injection test production-এ সীমিত, non-destructive ও policy-compliant হতে হবে।

### Safe differential workflow

1. Baseline request save করো।
2. একটি parser-sensitive character যোগ করো, যেমন একক quote বা double quote।
3. Status, response length, error text ও timing compare করো।
4. একই input দুইবার দিয়ে consistency verify করো।
5. Numeric parameter-এ benign boundary values test করো।
6. Error বা strong differential signal পেলে further exploitation বন্ধ করে report-ready evidence নাও।
7. Automated scanner বা time-delay test শুধু program অনুমতি দিলে।

### NoSQL/API clues

- JSON operator-like object unexpectedly accepted
- String expected স্থানে array/object দিলে auth logic বদলে যায়
- Filter parameter unrestricted query behavior তৈরি করে
- Error-এ database/driver name আসে

### কখন report করবে

শুধু generic 500 যথেষ্ট নয়। Input-dependent, repeatable behavior এবং plausible impact দেখাতে হবে।

### কখন করবে না

Database enumeration, data extraction, file read/write, OS command, long sleep বা destructive query production-এ করবে না।


## 🧪 Practical Example — Error-based signal, exploitation নয়

### 📥 Baseline

```http
GET /api/products?category=books HTTP/1.1
Host: target.example
```

```http
HTTP/1.1 200 OK

{"count":12,"items":[...]}
```

### ✏️ Single-character modification

```http
GET /api/products?category=books%27 HTTP/1.1
Host: target.example
```

### 🚨 Suspicious response

```http
HTTP/1.1 500 Internal Server Error

{
  "error":"SQL syntax error near 'books'''"
}
```

### Retest

- Baseline আবার পাঠাও → 200
- Same quote request আবার পাঠাও → repeatable 500
- অন্য benign invalid input পাঠাও → generic validation কী করে দেখো

### ✅ Secure response

```http
HTTP/1.1 400 Bad Request

{"error":"Invalid category"}
```

### 🛑 Stop

Database version, table, column বা data extraction করবে না। Strong repeatable parser/database error থাকলে report করো এবং remediation suggestion দাও।


---

# 🌐 অধ্যায় ১৫ — SSRF ও URL Fetch Features

### Hunting value: ⭐⭐⭐⭐☆

### Common features

- Webhook
- Import by URL
- Image/PDF preview
- Avatar fetch
- Link unfurl
- Feed reader
- Callback/integration test
- Remote file upload

### Safe workflow

1. নিজের controlled HTTPS endpoint ব্যবহার করো।
2. Unique path/token দাও।
3. Server-side callback আসে কি log করো।
4. Request method, headers, source IP ও redirect behavior note করো।
5. Redirect chain test করলে শুধু নিজের controlled domains ব্যবহার করো।
6. DNS rebinding, localhost, cloud metadata বা internal network probe production-এ করবে না—program explicit sandbox দিলে তবেই।

### Secure behavior

URL allowlist, protocol restriction, DNS/IP validation, redirect revalidation, network egress control ও response-size/time limits।

### Report evidence

- Feature request
- Controlled server log
- Unique token
- Timing
- What security boundary is crossed
- No internal data accessed statement


## 🧪 Practical Example — Controlled callback

### 🎯 Feature

“Import image from URL”

### 📥 Request

```http
POST /api/avatar/import HTTP/1.1
Cookie: session=REDACTED_A
Content-Type: application/json

{
  "url":"https://researcher-controlled.example/bbtest-ssrf-001.png"
}
```

### Controlled server log

```text
2026-07-18T01:30:10Z
GET /bbtest-ssrf-001.png
User-Agent: TargetImageFetcher/1.4
Source-IP: 203.0.113.20
```

### Interpretation

এটি server-side fetch প্রমাণ করে, কিন্তু internal access প্রমাণ করে না।

### Next safe checks

- HTTP redirect নিজের দ্বিতীয় controlled URL-এ follow করে কি
- Non-image response reject করে কি
- Timeout/size limit আছে কি
- URL scheme allowlist আছে কি

### 🛑 Stop

`localhost`, private IP, cloud metadata, internal hostname বা port scan করবে না, যদি program dedicated SSRF sandbox না দেয়।

### 📝 Hunter note

```text
Unique callback token used.
Only researcher-controlled HTTPS hosts contacted.
No internal resource requested.
```


---

# 📤 অধ্যায় ১৬ — File Upload

### Hunting value: ⭐⭐⭐⭐☆

### Safe test files

- Plain `.txt` unique marker
- Small valid image
- Program-approved benign SVG only when allowed
- Non-sensitive dummy PDF

### Workflow

1. Allowed extension/MIME/size map করো।
2. Filename server কীভাবে বদলায় দেখো।
3. Uploaded file public/private—authorization check করো।
4. Account A upload Account B access করতে পারে কি।
5. Original content serve হয় নাকি transformed।
6. Response `Content-Type`, `Content-Disposition`, CSP ও download behavior দেখো।
7. Delete/replace authorization test করো।
8. Storage URL predictable বা permanent কি।

### Dangerous tests এড়াও

Executable web shell, malware, polyglot exploitation, decompression bomb, huge file, antivirus evasion বা third-party users-এর file access করবে না।

### Common findings

- Unauthenticated upload
- IDOR in download/delete
- Stored XSS through unsafe active content
- Public sensitive file
- Filename/path confusion
- Content-type sniffing


## 🧪 Practical Example — Upload authorization

### Account B uploads own text file

```http
POST /api/files HTTP/1.1
Cookie: session=REDACTED_B
Content-Type: multipart/form-data; boundary=BOUNDARY

--BOUNDARY
Content-Disposition: form-data; name="file"; filename="bbtest-b.txt"
Content-Type: text/plain

Owned by researcher Account B
--BOUNDARY--
```

Response:

```http
HTTP/1.1 201 Created

{"fileId":"FILE-B-2002","downloadUrl":"/api/files/FILE-B-2002"}
```

### ✏️ Account A attempts access

```http
GET /api/files/FILE-B-2002 HTTP/1.1
Cookie: session=REDACTED_A
```

### ✅ Secure response

```http
HTTP/1.1 403 Forbidden
```

### 🚨 Bug signal

```http
HTTP/1.1 200 OK
Content-Type: text/plain

Owned by researcher Account B
```

### Additional safe checks

- Delete endpoint
- Replace endpoint
- Predictable public URL
- `Content-Disposition: attachment`
- Correct content type
- File name normalization

### 🛑 Stop

Executable file, web shell, malware, huge archive বা decompression bomb upload করবে না।


---

# 📂 অধ্যায় ১৭ — Path Traversal ও Arbitrary File Read

### Hunting value: ⭐⭐⭐⭐☆

### কোথায় দেখবে

- `file=`
- `path=`
- `template=`
- `download=`
- `lang=`
- export/import
- archive extraction
- image/PDF rendering

### Safe boundary

Real production-এ operating-system secret file request করবে না। Program-provided canary file, sandbox বা নিজের uploaded file ব্যবহার করো।

### Safe workflow

1. নিজের uploaded file-এর valid identifier দিয়ে baseline।
2. Normalized path variation test।
3. URL encoding/decoding behavior observe।
4. Storage root-এর বাইরে যাওয়ার signal আছে কি।
5. Error message path leak করে কি।
6. Own canary file cross-directory পড়া গেলে minimum proof নাও।

### Secure behavior

Server-generated IDs, canonicalization, fixed storage root, allowlist এবং authorization।

### Report quality

কোন normalization boundary bypass হয়েছে ও কী ধরনের sensitive file reachable হতে পারে—স্পষ্ট করে লিখবে, কিন্তু real secrets download করবে না।


## 🧪 Practical Example — Own canary file

### Setup

নিজের authorized sandbox-এ দুইটি file:

```text
/files/account-a/report.txt
/files/account-a/archive/canary.txt
```

### 📥 Baseline

```http
GET /api/download?file=report.txt HTTP/1.1
Cookie: session=REDACTED_A
```

### ✏️ Safe traversal check

শুধু নিজের canary file target করো:

```http
GET /api/download?file=archive%2Fcanary.txt HTTP/1.1
Cookie: session=REDACTED_A
```

তারপর normalization boundary অনুমতি দিলে:

```http
GET /api/download?file=archive%2F..%2Freport.txt HTTP/1.1
Cookie: session=REDACTED_A
```

### ✅ Secure behavior

Server canonicalize করে allowed root-এর ভিতরে file ID resolve করবে অথবা invalid path reject করবে।

### 🚨 Bug signal

Path normalization ব্যবহার করে policy-restricted own canary file পড়া যায়।

### 🛑 Stop

`/etc/passwd`, environment file, source code, keys বা অন্য user-এর file request করবে না।


---

# 🔄 অধ্যায় ১৮ — CORS

### Hunting value: ⭐⭐⭐☆☆

### Safe header probe

নিজের controlled origin ব্যবহার করে:

```http
Origin: https://researcher.example
```

Response-এ দেখো:

- `Access-Control-Allow-Origin`
- `Access-Control-Allow-Credentials`
- `Vary: Origin`
- Preflight behavior
- Allowed methods/headers

### Bug condition

CORS issue meaningful যখন untrusted origin credentialed sensitive response পড়তে পারে।

### Test matrix

- Untrusted arbitrary origin
- `null` origin
- Similar-looking subdomain
- HTTP বনাম HTTPS
- Attacker-controlled allowed subdomain—শুধু scope অনুযায়ী

### False positive

- ACAO `*` কিন্তু credentials নেই এবং data public
- Origin reflect হলেও sensitive endpoint unauthenticated
- Browser credential পাঠায় না
- Preflight blocked

Victim simulation নিজের দুই browser profile-এ করবে; অন্য user-কে involve করবে না।


## 🧪 Practical Example — Credentialed arbitrary origin

### 📥 Preflight/actual request

```http
GET /api/account HTTP/1.1
Host: target.example
Origin: https://researcher-controlled.example
Cookie: session=REDACTED_A
```

### 🚨 Vulnerable headers

```http
HTTP/1.1 200 OK
Access-Control-Allow-Origin: https://researcher-controlled.example
Access-Control-Allow-Credentials: true
Vary: Origin
Content-Type: application/json

{"email":"researcher-a@example.test","balance":"10.00"}
```

### Browser proof page

```html
<!doctype html>
<script>
fetch("https://target.example/api/account", {
  credentials: "include"
})
  .then(r => r.text())
  .then(t => document.body.textContent = t)
  .catch(e => document.body.textContent = String(e));
</script>
```

নিজের Account A browser-এ controlled origin থেকে চালাও।

### ✅ Secure result

Browser response body expose করবে না এবং server untrusted origin allow করবে না।

### 📝 Note

`Access-Control-Allow-Origin: *` + credentials browser reject করে; তাই শুধু header দেখে report নয়, browser behavior verify করো।


---

# 🧱 অধ্যায় ১৯ — Security Headers, CSP ও Clickjacking

### Hunting value: ⭐⭐☆☆☆ একা; exploit chain হলে বেশি

### Headers to review

- `Content-Security-Policy`
- `X-Frame-Options`
- CSP `frame-ancestors`
- `Strict-Transport-Security`
- `X-Content-Type-Options`
- `Referrer-Policy`
- `Permissions-Policy`
- Cookie flags

### CSP review

- Broad wildcard
- Unsafe inline/eval
- Missing `object-src`
- Missing `base-uri`
- Dangerous trusted script host
- Report-only policy only

Header missing হলেই bounty-worthy নয়। বাস্তব exploitability দেখাও।

### Clickjacking safe workflow

1. Sensitive page iframe-এ load হয় কি নিজের local page-এ দেখো।
2. Frame busting নয়, header enforcement verify করো।
3. Action sensitive ও visible/usable কি।
4. নিজের account-এ harmless click proof।
5. Destructive action trigger করবে না।

### High-value combination

Clickjacking + one-click security setting change, payment confirmation বা OAuth authorization বেশি impactful।


## 🧪 Practical Example — Clickjacking on harmless setting

### Local frame page

```html
<!doctype html>
<style>
iframe { width: 1000px; height: 700px; opacity: 0.8; }
</style>
<iframe src="https://target.example/settings/theme"></iframe>
```

### Expected secure behavior

Response:

```http
Content-Security-Policy: frame-ancestors 'self'
```

অথবা:

```http
X-Frame-Options: DENY
```

Browser frame load block করবে।

### 🚨 Bug signal

Sensitive authenticated page cross-origin iframe-এ fully interactive।

### Practical validation

নিজের Account A-তে theme/light mode-এর মতো harmless setting দিয়ে click alignment demonstrate করো। Password, payment, API key বা delete action click করবে না।

### 📝 Report note

Missing header alone নয়; framed page + meaningful action + user interaction path দেখাও।


---

# 🧊 অধ্যায় ২০ — Cache, CDN ও Web Cache Behavior

### Hunting value: ⭐⭐⭐⭐☆

### কী দেখবে

- `Cache-Control`
- `Age`
- `Vary`
- `ETag`
- `X-Cache`
- CDN-specific headers
- Authenticated response shared cache হচ্ছে কি

### Safe workflow

1. Unique benign query marker ব্যবহার করো।
2. Same URL Account A ও B থেকে request করো।
3. Personalized content cross-account দেখা যায় কি।
4. Header variation cache key-তে আছে কি।
5. Logout-এর পর cached private page পাওয়া যায় কি।
6. Error/redirect cache হয় কি।
7. Harmful cache poisoning payload ব্যবহার করবে না।

### High-impact signals

- Account A-এর private response Account B পায়
- Authorization header/cookie cache key-তে নেই
- Password reset বা secret-bearing response shared cache হয়
- User-controlled host/path response persistentভাবে অন্য users-কে serve হয়

### Evidence

Headersসহ first miss ও subsequent hit capture করো; timestamps ও account context লিখো।


## 🧪 Practical Example — Cross-account private cache leak

### Step 1: Account A request

```http
GET /account/summary?bbtest=cache-001 HTTP/1.1
Cookie: session=REDACTED_A
```

```http
HTTP/1.1 200 OK
Cache-Control: public, max-age=120
X-Cache: MISS

{"name":"Researcher A","plan":"Pro"}
```

### Step 2: Account B same URL

```http
GET /account/summary?bbtest=cache-001 HTTP/1.1
Cookie: session=REDACTED_B
```

### 🚨 Vulnerable response

```http
HTTP/1.1 200 OK
Age: 8
X-Cache: HIT

{"name":"Researcher A","plan":"Pro"}
```

### ✅ Secure behavior

Private/no-store response, or cache key isolates users:

```http
Cache-Control: private, no-store
```

Account B নিজের data পাবে।

### 📝 Hunter note

```text
A response: MISS, A data
B response: HIT, A data
Both accounts researcher-controlled
No third-party data observed
```

### 🛑 Stop

একবার cross-account leak confirm হলে URL variation দিয়ে mass cache exploration করবে না।


---

# ⏱️ অধ্যায় ২১ — Rate Limiting ও Abuse Controls

### Hunting value: ⭐⭐⭐☆☆

### Safe test plan

- নিজের account
- ৫–১০টি manual attempt
- Low frequency
- No distributed IPs
- No real-user identifiers
- Stop on latency/error increase

### কোথায় দেখবে

- Login
- Password reset
- OTP
- Coupon
- Invitation
- Email/SMS send
- Search/export
- API key creation
- Expensive report generation

### কী compare করবে

- Per-IP vs per-account
- Success/failure counting
- Endpoint/version consistency
- Header-based bypass—production-এ aggressive evasion নয়
- Lockout behavior
- `Retry-After`

### Finding meaningful করতে

শুধু “rate limit নেই” নয়; realistic abuse impact দেখাও—account compromise, resource exhaustion, spam বা financial abuse। তবে abuse execute করবে না।


## 🧪 Practical Example — OTP attempts, low volume

### Controlled plan

নিজের Account A-এর OTP verification endpoint-এ মোট ৬টি manual invalid attempt:

```http
POST /api/mfa/verify HTTP/1.1
Cookie: session=REDACTED_A
Content-Type: application/json

{"code":"000001"}
```

### Expected progression

```http
Attempt 1-3: 400 Invalid code
Attempt 4:   429 Too Many Requests
Retry-After: 60
```

### 🚨 Bug signal

Attempt 1-6 সব একইভাবে accepted for processing, কোনো delay/lockout/limit নেই—কিন্তু report করার আগে practical code space, expiry ও other controls বিবেচনা করবে।

### 📝 Note table

| Attempt | Code | Status | Response time | Header |
|---:|---|---:|---:|---|
| 1 | 000001 | 400 | 210 ms | none |
| 2 | 000002 | 400 | 205 ms | none |
| 3 | 000003 | 400 | 215 ms | none |
| 4 | 000004 | 429 | 202 ms | Retry-After: 60 |

### 🛑 Stop

Brute force complete করবে না; ৫–১০ low-rate request-এর বেশি নয়, unless policy explicitly allows।


---

# 🧠 অধ্যায় ২২ — Business Logic

### Hunting value: ⭐⭐⭐⭐⭐

Business logic bug scanner কম পায়; human hunter-এর বড় advantage এখানেই।

### প্রশ্ন করো

- Step skip করা যায়?
- Order বদলানো যায়?
- One-time action replay হয়?
- Client price/quantity/status বিশ্বাস করা হয়?
- Same benefit multiple account/tenant-এ reuse হয়?
- Cancel/refund-এর পরে entitlement থাকে?
- Invitation transfer করা যায়?
- Verification-এর আগে protected feature ব্যবহার করা যায়?
- Limit শুধু UI-তে আছে?
- Negative/zero/overflow boundary কী করে?

### Safe workflow

1. Normal successful flow record করো।
2. State machine আঁকো।
3. এক ধাপ skip/reorder/replay করো।
4. নিজের account ও sandbox cart ব্যবহার করো।
5. Final charge, shipment, real refund বা third-party notification trigger করার আগে থামো।
6. Reversible low-value proof নাও।

### State machine example

```text
draft → submitted → approved → paid → fulfilled
```

Test: `draft` থেকে সরাসরি `paid` endpoint accept করে কি? Production-এ real payment না করে response/state validation পর্যন্ত সীমাবদ্ধ থাকো।


## 🧪 Practical Example — Workflow step skipping

### Normal flow

```text
DRAFT → REVIEW → APPROVED → PUBLISHED
```

### UI-generated request

```http
POST /api/articles/ART-A-1001/submit-review HTTP/1.1
Cookie: session=REDACTED_A
```

এর পরে manager approve করে।

### ✏️ Direct step test

নিজের draft object-এ publish endpoint সরাসরি call:

```http
POST /api/articles/ART-A-1001/publish HTTP/1.1
Cookie: session=REDACTED_A
```

### ✅ Secure response

```http
HTTP/1.1 409 Conflict

{"error":"Article must be approved before publishing"}
```

### 🚨 Bug signal

```http
HTTP/1.1 200 OK

{"status":"published"}
```

### 📝 Hunter note

```text
Object owned by Account A
Initial state: draft
Skipped: review + approval
Final state: published
No public audience; test workspace only
```

### 🛑 Stop

Public content, real order, payout বা external notification create না করে isolated test workspace ব্যবহার করবে।


---

# 🏁 অধ্যায় ২৩ — Race Conditions

### Hunting value: ⭐⭐⭐⭐☆

### Common targets

- Coupon redemption
- Gift/credit transfer
- Invite acceptance
- Username claim
- Password reset token
- Vote/like limit
- Inventory reserve
- One-time download
- Account deletion/restore

### Safe workflow

1. নিজের low-value object ব্যবহার করো।
2. Baseline single request।
3. ২–৫টি concurrent request—program policy মেনে।
4. Final state count করো।
5. Duplicate effect হলে থামো।
6. Cleanup/revert করো।
7. Service latency বাড়লে সঙ্গে সঙ্গে বন্ধ।

### Good report evidence

- Exact number of requests
- Concurrency method
- Expected one success
- Actual multiple successes
- Final account state
- No third-party impact


## 🧪 Practical Example — One-time coupon, 2 concurrent requests

শুধু program policy race testing allow করলে এবং low-value test coupon থাকলে।

### Python snippet

```python
import concurrent.futures
import requests

URL = "https://target.example/api/coupons/redeem"
COOKIES = {"session": "REDACTED_A"}
PAYLOAD = {"code": "TEST-ONE-TIME"}

def redeem():
    return requests.post(
        URL,
        cookies=COOKIES,
        json=PAYLOAD,
        timeout=10,
    )

with concurrent.futures.ThreadPoolExecutor(max_workers=2) as pool:
    responses = list(pool.map(lambda _: redeem(), range(2)))

for r in responses:
    print(r.status_code, r.text[:200])
```

### ✅ Secure outcome

```text
200 {"redeemed":true}
409 {"error":"Already redeemed"}
```

### 🚨 Bug signal

```text
200 {"redeemed":true}
200 {"redeemed":true}
```

এবং final account state-এ benefit দুইবার যোগ হয়েছে।

### 🛑 Stop

২–৫ request-এর বেশি নয়, real-money coupon নয়, service slow হলে সঙ্গে সঙ্গে বন্ধ।


---

# 🛒 অধ্যায় ২৪ — E-commerce, Credits, Coupons ও Payments

### Hunting value: ⭐⭐⭐⭐⭐

### Safe targets

- Cart calculation
- Coupon rules
- Quantity boundaries
- Shipping/tax calculation
- Store credits
- Trial/subscription transitions
- Refund eligibility
- Gift-card ownership
- Invoice access

### Rules

- Program-provided sandbox/test card ব্যবহার করো
- Real charge সম্পন্ন করবে না
- Real goods order করবে না
- Negative amount, huge quantity বা refund abuse production-এ execute করবে না
- Cart/preview stage পর্যন্ত proof prefer করো

### Checklist

- [ ] Price server-side recalculated?
- [ ] Coupon ownership ও expiry checked?
- [ ] One-time code replay blocked?
- [ ] Currency mismatch handled?
- [ ] Quantity zero/negative rejected?
- [ ] Discount stacking rules server-side?
- [ ] Account A gift card Account B ব্যবহার করতে পারে?
- [ ] Cancel/refund-এর পর entitlement revoke?
- [ ] Invoice ID authorization?


## 🧪 Practical Example — Client-supplied price

### 📥 Normal cart request

```http
POST /api/cart/items HTTP/1.1
Cookie: session=REDACTED_A
Content-Type: application/json

{
  "productId":"TEST-PRODUCT-1",
  "quantity":1,
  "unitPrice":"25.00"
}
```

### ✏️ Modify

নিজের sandbox cart-এ price field পরিবর্তন:

```json
{
  "productId":"TEST-PRODUCT-1",
  "quantity":1,
  "unitPrice":"1.00"
}
```

### ✅ Secure response

Server catalog থেকে price recalculates:

```http
HTTP/1.1 200 OK

{
  "productId":"TEST-PRODUCT-1",
  "quantity":1,
  "unitPrice":"25.00",
  "total":"25.00"
}
```

### 🚨 Bug signal

Cart/order preview server-signed state-এ `1.00` গ্রহণ করে।

### 🛑 Stop

Checkout submit, real payment, shipment বা refund trigger করবে না। Cart/preview proof পর্যন্ত থাকবে।


---

# ↪️ অধ্যায় ২৫ — Open Redirect ও URL Handling

### Hunting value: ⭐⭐☆☆☆; chain হলে বেশি

### Common parameters

- `next`
- `return`
- `redirect`
- `continue`
- `callback`
- `url`

### Safe workflow

1. নিজের benign HTTPS domain ব্যবহার করো।
2. Absolute URL, relative URL ও encoded URL behavior compare করো।
3. Redirect whitelist/allowlist আছে কি।
4. OAuth, login, reset বা trusted-domain phishing chain আছে কি।
5. No credential/token leak নিশ্চিত করো।

### Report-worthy when

- Trusted login/reset flow attacker domain-এ পাঠায়
- OAuth code/token leak chain
- Security control bypass
- High-confidence phishing from trusted domain

Generic marketing redirect অনেক program informational/duplicate হিসেবে দেখে।


## 🧪 Practical Example — Login redirect

### 📥 Request

```http
GET /login?next=https%3A%2F%2Fresearcher-controlled.example%2Fdone HTTP/1.1
Host: target.example
```

Login complete করার পরে:

### ✅ Secure behavior

- `next` শুধু relative path হলে accept
- Untrusted absolute URL reject
- Default dashboard-এ redirect

```http
HTTP/1.1 302 Found
Location: /dashboard
```

### 🚨 Bug signal

```http
HTTP/1.1 302 Found
Location: https://researcher-controlled.example/done
```

### Impact check

Report value বেশি যখন এটি password reset, OAuth, trusted notification বা token leakage flow-এর অংশ।

### 📝 Note

নিজের harmless domain ব্যবহার করবে; credential-collecting page বানাবে না।


---

# 🏠 অধ্যায় ২৬ — Host Header ও Password Reset Poisoning

### Hunting value: ⭐⭐⭐⭐☆

### Headers to observe

- `Host`
- `X-Forwarded-Host`
- `Forwarded`
- `X-Forwarded-Proto`

### Safe workflow

1. নিজের account-এর reset/invite trigger করো।
2. Benign invalid host marker পাঠাও।
3. Email link, redirect বা generated absolute URL-এ marker আসে কি।
4. Cache/CDN behavior check করো।
5. অন্য user-এর reset email trigger করবে না।
6. Host routing বদলে out-of-scope service hit করলে থামো।

### Secure behavior

Trusted configured origin থেকে absolute URL generation; proxy headers validated।

### Impact

Reset token attacker-controlled host-এ পাঠানো, cache poisoning, virtual-host confusion বা link generation compromise।


## 🧪 Practical Example — Own reset email link generation

### 📥 Request

```http
POST /forgot-password HTTP/1.1
Host: target.example
X-Forwarded-Host: researcher-controlled.example
Content-Type: application/x-www-form-urlencoded

email=researcher-a%40example.test
```

### Received own email

Secure:

```text
https://target.example/reset?token=REDACTED
```

Suspicious:

```text
https://researcher-controlled.example/reset?token=REDACTED
```

### ✅ Secure behavior

Application trusted configured base URL ব্যবহার করবে; untrusted proxy header ignore করবে।

### 🛑 Stop

Token link click করে controlled server-এ secret capture করবে না। Email screenshot-এ token redact করে generation flaw report করবে।


---

# 🔁 অধ্যায় ২৭ — WebSocket

### Hunting value: ⭐⭐⭐⭐☆

### Checklist

- [ ] Handshake authentication
- [ ] Origin validation
- [ ] Session logout-এর পরে socket invalid
- [ ] Message-level authorization
- [ ] Subscription/channel ownership
- [ ] Object ID tampering
- [ ] Rate limit
- [ ] Sensitive data broadcast
- [ ] Reconnect token rotation

### Safe two-account test

Account A socket থেকে Account B-এর own channel/object subscribe করার চেষ্টা করো। শুধু ID বদলাও। B-এর test data পেলে evidence নিয়ে থামো।

### Common mistake

Handshake authenticated হলেও প্রতিটি message/action authorized নয়। `subscribe`, `join`, `edit`, `delete` message আলাদা করে test করো।


## 🧪 Practical Example — Channel authorization

### Account A socket message

```json
{"action":"subscribe","channel":"notifications:user_A"}
```

Response:

```json
{"type":"subscribed","channel":"notifications:user_A"}
```

### ✏️ Modify

শুধু channel identifier Account B-এর own channel:

```json
{"action":"subscribe","channel":"notifications:user_B"}
```

### ✅ Secure response

```json
{"type":"error","code":"FORBIDDEN"}
```

### 🚨 Bug signal

```json
{"type":"subscribed","channel":"notifications:user_B"}
```

এর পরে Account B-এর researcher-generated test notification Account A socket-এ আসে।

### 📝 Note

Handshake auth থাকলেই message-level auth নিশ্চিত নয়। Subscribe, edit, delete action আলাদা test।


---

# 🕸️ অধ্যায় ২৮ — GraphQL

### Hunting value: ⭐⭐⭐⭐☆

### Map

- Endpoint
- Authentication
- Queries
- Mutations
- Object/node IDs
- Nested fields
- Error messages
- Depth/complexity controls

### Safe workflow

1. UI থেকে legitimate query capture করো।
2. Unnecessary fields remove/add করে authorization behavior দেখো।
3. Account A token দিয়ে B-এর own node ID test করো।
4. Mutation role/ownership check করো।
5. Aliases বা batching দিয়ে rate-limit bypass aggressively test করবে না।
6. Large/deep query দিয়ে DoS করবে না।
7. Introspection enabled একা vulnerability নয়।

### High-value findings

- Hidden admin mutation low role-এ চলে
- Nested field authorization missing
- Node ID horizontal access
- Sensitive field excessive exposure
- Mutation mass assignment


## 🧪 Practical Example — Node-level authorization

### Account A baseline query

```graphql
query {
  project(id: "PROJ-A-1001") {
    id
    name
    owner {
      id
    }
  }
}
```

Response:

```json
{
  "data":{
    "project":{
      "id":"PROJ-A-1001",
      "name":"A Test Project",
      "owner":{"id":"usr_A"}
    }
  }
}
```

### ✏️ Modify

শুধু ID Account B-এর project:

```graphql
query {
  project(id: "PROJ-B-2002") {
    id
    name
    owner {
      id
    }
  }
}
```

### ✅ Secure response

```json
{
  "data":{"project":null},
  "errors":[{"message":"Not found"}]
}
```

### 🚨 Bug signal

Account A session-এ B-owned node data return।

### Nested-field test

Object visible হওয়া intended হলেও sensitive nested field আলাদা authorized কি দেখো:

```graphql
query {
  project(id: "SHARED-PROJ") {
    name
    billing {
      cardLast4
      invoiceEmail
    }
  }
}
```

### 🛑 Stop

Deep-query DoS, large aliases বা schema-wide dumping করবে না।


---

# 🔐 অধ্যায় ২৯ — OAuth, OIDC ও SAML

### Hunting value: ⭐⭐⭐⭐⭐; advanced

### Safe scope

শুধু নিজের identity, নিজের test accounts এবং in-scope client/authorization server ব্যবহার করো।

### OAuth/OIDC checklist

- `state` validation
- OIDC `nonce`
- Exact redirect URI validation
- Authorization code one-time use
- PKCE where applicable
- Token audience/issuer validation
- Account-linking confirmation
- Login CSRF protection
- Token leakage in URL/referrer/log
- Unlink/relink authorization

### SAML checklist

- Response signature validation
- Audience/recipient/destination
- Replay protection
- Account mapping
- IdP-initiated flow policy
- XML parser safety

### Production boundary

Forged token/assertion exploitation, token theft, other users-এর account link বা third-party IdP attack করবে না। Strong validation gap দেখলে minimum proof ও clear reasoning দাও।


## 🧪 Practical Example — OAuth `state` binding

### Authorization request

```http
GET /oauth/authorize?
 client_id=web-client&
 redirect_uri=https%3A%2F%2Ftarget.example%2Foauth%2Fcallback&
 response_type=code&
 state=STATE_A_9f31
```

### Callback

```http
GET /oauth/callback?code=REDACTED_CODE&state=STATE_A_9f31
```

### ✏️ Safe check

নিজের Account A flow-এ callback request থেকে `state` remove বা নিজের অন্য session-এর `STATE_B` বসাও।

### ✅ Secure response

```http
HTTP/1.1 400 Bad Request

{"error":"Invalid OAuth state"}
```

### 🚨 Bug signal

Missing/mismatched state accepted এবং wrong browser session-এ account link/login complete।

### 🛑 Stop

Other users-এর identity link করবে না, authorization code intercept বা token reuse করবে না। নিজের A/B identity only।


---

# 🕵️ অধ্যায় ৩০ — Information Disclosure ও Client-Side Secrets

### Hunting value: ⭐⭐⭐☆☆

### কোথায় দেখবে

- JavaScript bundles
- Source maps
- HTML comments
- API responses
- Error pages
- Public storage
- Build metadata
- Debug endpoints
- Mobile configuration
- OpenAPI/GraphQL schema

### Secret handling

API key/token দেখলে:

1. Screenshot ও exact location capture করো।
2. Secret redact করো।
3. Third-party service-এ ব্যবহার করে validity test করবে না।
4. Scope owner-কে report করো।
5. Public/non-secret client identifier-এর সঙ্গে sensitive credential গুলিয়ে ফেলবে না।

### Meaningful impact

- Private backend credential
- Sensitive internal endpoint with unauthorized access
- Personal data exposure
- Debug console
- Source map থেকে exploitable hidden functionality

Version banner বা framework name একা সাধারণত low value।


## 🧪 Practical Example — JavaScript bundle review

Bundle snippet:

```javascript
window.__CONFIG__ = {
  apiBase: "https://api.target.example",
  analyticsKey: "public-client-id",
  adminApiToken: "sk_live_REDACTED"
};
```

### Triage

- `analyticsKey` public client identifier হতে পারে
- `adminApiToken` naming/context sensitive credential-এর signal
- Token use করে external/API action করবে না

### Safe evidence

```text
Asset: https://target.example/assets/app.abc123.js
Line/context: window.__CONFIG__
Secret redacted: sk_live_REDA...
Publicly accessible without authentication: yes
Potential privilege: inferred from variable name only; not validated
```

### Better report

“Public bundle contains a credential-shaped secret” বলবে; “full admin takeover” claim করবে না যতক্ষণ owner safely validate না করে।


---

# 🚨 অধ্যায় ৩১ — Error Handling, Status Code ও Routing

### Hunting value: ⭐⭐☆☆☆; chain signal হিসেবে useful

### Checks

- Real missing page `404` দেয়?
- Unauthorized `401/403`?
- API error `200` success body দেয়?
- Stack trace, SQL error, path, secret বা debug data leak?
- Case/trailing slash/method variation authorization বদলায়?
- Reverse proxy ও backend response mismatch?
- Unknown route session/cookie বদলায়?
- Error cache হয়?

### Safe route variants

- Case change
- Trailing slash
- Benign extra slash
- `HEAD`/`OPTIONS`
- Allowed method comparison

Authorization bypassের জন্য aggressive encoding/bypass fuzzing কেবল policy অনুমতি দিলে।

### Soft 404

Body “not found” কিন্তু status `200` হলে SEO/monitoring সমস্যা হতে পারে; security impact আলাদা করে দেখাতে হবে।


## 🧪 Practical Example — Stack trace disclosure

### 📥 Benign malformed ID

```http
GET /api/orders/not-a-valid-id HTTP/1.1
Cookie: session=REDACTED_A
```

### 🚨 Vulnerable response

```http
HTTP/1.1 500 Internal Server Error

{
  "error":"TypeError",
  "message":"Cannot read properties of undefined",
  "stack":"at OrderController.get (/srv/app/controllers/order.js:88:17)",
  "database":"postgres://app_user@db-internal:5432/prod"
}
```

### ✅ Secure response

```http
HTTP/1.1 400 Bad Request

{"error":"Invalid order ID"}
```

### Hunter action

- Exact request save
- Secret-bearing connection string redact
- Repeatability একবার verify
- Internal host access attempt করবে না
- Root cause: unhandled validation error + sensitive debug output


---

# ☁️ অধ্যায় ৩২ — Subdomain, DNS ও Cloud Storage Recon

### Hunting value: ⭐⭐⭐☆☆

### Passive-first

- In-scope subdomain list
- DNS records
- Certificate transparency
- Public app links
- Official documentation
- JavaScript-referenced hosts

### Dangling DNS safe verification

Provider error/banner ও DNS chain document করো। Resource claim বা takeover সম্পন্ন করবে না, যদি program policy স্পষ্টভাবে অনুমতি না দেয়।

### Cloud storage

- Bucket/container name public reference থেকে এসেছে কি
- Listing public কি
- Object access intended public কি
- Sensitive data sample দেখলে আর download করবে না
- Write/delete test করবে না
- Third-party/employee personal files access করবে না

### Report evidence

DNS record, provider response, in-scope ownership signal, impact explanation ও non-claim statement।


## 🧪 Practical Example — Dangling DNS observation

### DNS result

```text
old-help.target.example CNAME target-old.vendor.example
```

### HTTP response

```http
HTTP/1.1 404 Not Found

No such application: target-old
```

### Safe conclusion

Potential dangling third-party mapping। Provider resource claim করবে না।

### Evidence note

```text
In-scope subdomain: old-help.target.example
DNS chain: CNAME target-old.vendor.example
Provider-specific unclaimed response observed
No resource was claimed
No content was hosted
```

### 🛑 Stop

Takeover claim/register করা policy explicitly allow না করলে করবে না।


---

# 📸 অধ্যায় ৩৩ — Evidence Collection

একটি accepted report সাধারণত reproducible ও minimally invasive হয়।

### Save

- Full URL/path
- Method
- Redacted request
- Redacted response
- Account roles
- Object ownership
- Timestamp ও timezone
- Screenshots
- Video only when flow complex
- Before/after state
- Expected vs actual
- Cleanup performed

### Redaction

```text
Cookie: session=REDACTED
Authorization: Bearer eyJ...REDACTED
Email: f***@example.com
```

### Evidence chain

1. Account A owns Object A
2. Account B owns Object B
3. A requests B object
4. Server returns/changes B object
5. B account verifies side effect

এটি IDOR report-এর জন্য শক্ত evidence।


## 🧪 Practical Example — IDOR evidence packet

### 1. Ownership proof

```text
Screenshot A: Account B dashboard shows Order ORD-B-2002
Timestamp: 2026-07-18 01:40 UTC
```

### 2. Baseline request

```http
GET /api/orders/ORD-A-1001
Cookie: session=REDACTED_A
```

### 3. Modified request

```http
GET /api/orders/ORD-B-2002
Cookie: session=REDACTED_A
```

### 4. Vulnerable response

```http
HTTP/1.1 200 OK

{"id":"ORD-B-2002","ownerId":"usr_B","note":"B-owned-test"}
```

### 5. Comparison table

| Item | Baseline | Modified |
|---|---|---|
| Session | Account A | Account A |
| Path ID | ORD-A-1001 | ORD-B-2002 |
| Owner | A | B |
| Status | 200 | 200 |
| Expected | A data | 403/404 |
| Actual | A data | B data |

### 6. Safety statement

```text
Both accounts and objects are controlled by the researcher.
No real-user identifier was guessed or enumerated.
Testing stopped after one B-owned object was returned.
```


---

# 📊 অধ্যায় ৩৪ — Severity ও Impact

Severity শুধু vulnerability নাম দিয়ে নয়—actual impact দিয়ে নির্ধারিত হয়।

### Impact dimensions

- Confidentiality: কী data পড়া যায়?
- Integrity: কী পরিবর্তন করা যায়?
- Availability: service impact?
- Scope: এক user, এক tenant, নাকি সবাই?
- Privilege: unauthenticated, normal user, admin?
- User interaction দরকার?
- Exploit complexity?
- Repeatability?
- Financial/legal/privacy impact?

### Examples

- নিজের public profile IDOR নয়
- অন্য tenant-এর invoice read: high
- Any user role admin করা: critical
- Missing header without exploit: informational/low
- Stored XSS admin panel-এ execute: high/critical context-dependent
- Rate limit absent কিন্তু practical abuse নেই: low/informational

### রিপোর্টে বলবে

“Attacker can…” দিয়ে capability এবং “This results in…” দিয়ে business impact লিখবে।


## 🧪 Practical Example — একই endpoint, ভিন্ন impact

### Case A: Public display name

Account A অন্য user-এর already-public display name API দিয়ে পড়ে। Confidentiality impact নেই → likely informational/not applicable।

### Case B: Private invoice

Account A Account B-এর invoice PDF পড়ে:

```json
{
  "invoiceId":"INV-B-22",
  "billingEmail":"b@example.test",
  "amount":"500.00",
  "address":"REDACTED"
}
```

Cross-tenant private billing data → likely high impact।

### Case C: Role escalation

Viewer request:

```http
PATCH /api/orgs/ORG-A/members/usr_A
Content-Type: application/json

{"role":"owner"}
```

Server accepts; organization ownership gained → critical/high depending on blast radius।

### Impact sentence formula

```text
An authenticated viewer can modify the role field of their own membership
to become an organization owner, allowing access to billing, API keys, and
member administration within the affected tenant.
```

Severity claim বাস্তব reachable privileges অনুযায়ী করবে, vulnerability label অনুযায়ী নয়।


---

# 📝 অধ্যায় ৩৫ — Bug Report Template

```markdown
# [Vulnerability] in [Feature] allows [Impact]

## Summary
এক বাক্যে root cause ও impact।

## Asset
- Host:
- Endpoint:
- Method:
- Program scope reference:

## Preconditions
- Account/role:
- Own test accounts used:
- Required feature/state:

## Steps to Reproduce
1. Account A দিয়ে ...
2. Request capture করুন।
3. শুধু `objectId` পরিবর্তন করুন।
4. Modified request পাঠান।
5. Response/side effect observe করুন।

## Expected Result
Server ownership/role verify করে request reject করবে।

## Actual Result
Server request accept করে Account B-এর resource return/change করে।

## Impact
Attacker can ...

## Evidence
- Redacted request
- Redacted response
- Screenshot/video
- Timestamps

## Safety Notes
- Only researcher-controlled accounts/data used
- No real-user data accessed
- No destructive action performed
- Test data cleaned up

## Suggested Fix
Server-side authorization on every object/action; deny by default।
```


## 🧪 Filled Practical Report — IDOR Example

```markdown
# IDOR in order details API exposes another account's order

## Summary
The `GET /api/orders/{orderId}` endpoint checks that the requester is
authenticated but does not verify ownership of the requested order.

## Asset
- Host: https://target.example
- Endpoint: GET /api/orders/{orderId}
- Scope: Web application API

## Preconditions
- Two normal user accounts
- Account A session
- Account B researcher-owned order

## Steps to Reproduce
1. Log in as Account B and create order `ORD-B-2002`.
2. Log in as Account A.
3. Request Account A's own order and confirm the session works.
4. Change only the path ID to `ORD-B-2002`.
5. Send the request with Account A's unchanged session.

## Request
```http
GET /api/orders/ORD-B-2002 HTTP/1.1
Host: target.example
Cookie: session=REDACTED_A
```

## Actual Response
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "id":"ORD-B-2002",
  "ownerId":"usr_B",
  "item":"Test Mouse"
}
```

## Expected Result
The server should return `403 Forbidden` or `404 Not Found`.

## Impact
Any authenticated user who obtains an order identifier can read order data
belonging to another account. Depending on returned fields, this may expose
purchase and billing information.

## Safety
Both accounts and the order are controlled by the researcher. Testing stopped
after one controlled cross-account object was returned.
```


---

# 🗓️ অধ্যায় ৩৬ — Daily Hunting Workflow

### 90-minute session

**0–10 মিনিট:** scope ও recent policy reread  
**10–25 মিনিট:** একটি feature map  
**25–50 মিনিট:** two-account authorization tests  
**50–65 মিনিট:** business logic/state transitions  
**65–75 মিনিট:** session/cache/CORS/header triage  
**75–85 মিনিট:** evidence ও retest  
**85–90 মিনিট:** notes ও next hypothesis

### Feature-first rule

একদিনে ২০ vulnerability class ছোঁয়ার চেয়ে একটি feature গভীরভাবে বোঝা ভালো।

উদাহরণ: “Team invitation” feature-এর উপর auth, IDOR, token reuse, role escalation, CSRF, rate limit, race, email poisoning—সব test করা যায়।


## 🧪 Practical 90-minute session note

```markdown
# Session: Team Invitation Feature

## 00–10 Scope
- app.target.example in scope
- api.target.example in scope
- Email flooding forbidden
- Max 5 invitation tests

## 10–25 Mapping
- POST /api/orgs/{orgId}/invites
- GET /invite/{token}
- POST /api/invites/{token}/accept
- DELETE /api/orgs/{orgId}/invites/{inviteId}

## 25–50 Authorization
- A invite ID with B session → 403
- B org ID with A session → 403
- Viewer creates owner invite → accepted [candidate finding]

## 50–65 Logic
- Same token replay → second use rejected
- Expired token → rejected
- Email case variation → duplicate prevented

## 65–75 Triage
- Invite endpoint has CSRF token
- Rate limit after 5 attempts
- No cache issue

## 75–85 Evidence
- Reproduced viewer → owner invite twice
- Used only test org and Account B

## 85–90 Next hypothesis
- Does alternate mobile API enforce allowed invite roles?
```


---

# 🏆 অধ্যায় ৩৭ — Hunting Priority Matrix

| Area | Hunting value | Beginner-friendly | False-positive risk | Recommended priority |
|---|---:|---:|---:|---:|
| Authorization / IDOR / RBAC | 5/5 | 5/5 | Low | 1 |
| Business logic | 5/5 | 3/5 | Medium | 2 |
| API BOLA/BOPLA | 5/5 | 4/5 | Low | 3 |
| Password reset / account recovery | 5/5 | 3/5 | Medium | 4 |
| Session / cookie | 4/5 | 4/5 | Medium | 5 |
| File access/upload authorization | 4/5 | 4/5 | Medium | 6 |
| Race condition | 4/5 | 2/5 | Medium | 7 |
| XSS | 4/5 | 4/5 | Medium | 8 |
| Cache / CDN | 4/5 | 2/5 | High | 9 |
| SSRF | 4/5 | 2/5 | High | 10 |
| Injection | 4/5 | 3/5 | High | 11 |
| OAuth/OIDC/SAML | 5/5 | 1/5 | High | Advanced |
| CORS / Headers | 2–3/5 | 5/5 | High | Triage |
| Information disclosure | 3/5 | 5/5 | High | Triage |

### Beginner recommendation

প্রথম ৩০ দিন এই order অনুসরণ করো:

1. HTTP ও Burp basics
2. Two-account IDOR
3. Role/tenant authorization
4. Password reset/session
5. API fields ও mass assignment
6. Business logic
7. XSS/CORS/cache triage


---

# 🧯 অধ্যায় ৩৮ — False Positive Eliminator

Report করার আগে:

- [ ] Behavior repeatable?
- [ ] Baseline comparison আছে?
- [ ] Different account/role দিয়ে verify?
- [ ] Actual server-side side effect?
- [ ] Intended public/shared feature নয়?
- [ ] UI bug নয়?
- [ ] Browser restriction exploit আটকে দেয় কি?
- [ ] Sensitive data সত্যিই sensitive?
- [ ] Program policy এটিকে excluded বলে কি?
- [ ] Missing header ছাড়া concrete impact আছে?
- [ ] Race result normal retry behavior নয়?
- [ ] Cache result browser local cache নয়?
- [ ] Error generic/transient নয়?
- [ ] Report duplicate known issue হওয়ার সম্ভাবনা কমাতে asset/feature search করেছ?


---

# 🧪 অধ্যায় ৩৯ — Lab বনাম Real Website Boundary

### Lab-এ শেখো

- Full SQL injection exploitation
- Command injection
- Web shell
- Internal SSRF/metadata access
- JWT signature attacks
- OAuth token forgery
- Deserialization/RCE
- Complex request smuggling
- Cache poisoning payload chains
- WAF bypass
- Large-scale fuzzing

### Authorized real program-এ করো

- Scope-allowed, minimum-impact validation
- Own accounts/data
- Controlled callbacks
- Reversible state changes
- Low request volume
- Immediate stop on impact
- Clear evidence and disclosure

### Practice platforms

PortSwigger Web Security Academy, OWASP Juice Shop, WebGoat, crAPI এবং নিজের local test app ব্যবহার করে exploit mechanics শিখো। Production bounty target-এ শুধু vulnerability validate করো।


---

# 📒 অধ্যায় ৪০ — Ready-to-Copy Hunting Notebook

```markdown
# Target: 
## Policy snapshot
- In scope:
- Out of scope:
- Automation:
- Rate limits:
- Special restrictions:

## Accounts
- A role:
- B role:
- Admin/test role:

## Feature: 
### Normal flow
1.
2.
3.

### Endpoints
| Endpoint | Method | Auth | IDs | State change |
|---|---|---|---|---|

### Hypotheses
- [ ] Missing authentication
- [ ] Horizontal access
- [ ] Vertical access
- [ ] Hidden property
- [ ] Replay
- [ ] Step skipping
- [ ] CSRF
- [ ] Rate limit
- [ ] Race
- [ ] Cache leak

### Tests
| Time | Change | Expected | Actual | Evidence |
|---|---|---|---|---|

### Finding draft
- Root cause:
- Attacker capability:
- Business impact:
- Minimum PoC:
- Cleanup:
```


---

# 🧾 Appendix A — Safe `curl` Examples

সব command-এ নিজের in-scope host ও test account ব্যবহার করবে।

### Baseline response

```bash
BASE='https://target.example'
curl -i -sS "$BASE/api/me" \
  -H 'Cookie: session=REDACTED'
```

### Two-account authorization comparison

```bash
curl -i -sS "$BASE/api/orders/ORDER_B" \
  -H 'Cookie: session=ACCOUNT_A_SESSION'
```

### CORS header observation

```bash
curl -i -sS "$BASE/api/me" \
  -H 'Origin: https://researcher.example' \
  -H 'Cookie: session=REDACTED'
```

### Cache observation

```bash
curl -i -sS "$BASE/account?bbtest=20260718-001" \
  -H 'Cookie: session=REDACTED'
```

### Header-only file check

```bash
curl -I -sS "$BASE/uploads/OWN_TEST_FILE"
```

Tokens terminal history-এ রেখে দিও না; temporary environment/file ব্যবহার করে পরে clean করো।


## 🧪 Practical `curl` comparison script

```bash
#!/usr/bin/env bash
set -euo pipefail

BASE="https://target.example"
COOKIE_A="session=REDACTED_A"
ORDER_A="ORD-A-1001"
ORDER_B="ORD-B-2002"

echo "=== Baseline: Account A own object ==="
curl -sS -D /tmp/a-headers.txt \
  "$BASE/api/orders/$ORDER_A" \
  -H "Cookie: $COOKIE_A" \
  -o /tmp/a-body.json

echo "=== Modified: Account A requests researcher-owned B object ==="
curl -sS -D /tmp/b-headers.txt \
  "$BASE/api/orders/$ORDER_B" \
  -H "Cookie: $COOKIE_A" \
  -o /tmp/b-body.json

echo "--- Status/header comparison ---"
grep -E '^(HTTP/|Content-Type:|Cache-Control:|Vary:)' \
  /tmp/a-headers.txt /tmp/b-headers.txt || true

echo "--- Body sizes ---"
wc -c /tmp/a-body.json /tmp/b-body.json

echo "Review files locally and redact before reporting."
```

### Windows PowerShell equivalent

```powershell
$base = "https://target.example"
$headers = @{ Cookie = "session=REDACTED_A" }

Invoke-WebRequest `
  -Uri "$base/api/orders/ORD-A-1001" `
  -Headers $headers `
  -OutFile ".\baseline.json"

Invoke-WebRequest `
  -Uri "$base/api/orders/ORD-B-2002" `
  -Headers $headers `
  -OutFile ".\modified.json"
```

> Session value shell history-এ save না করে temporary environment variable ব্যবহার করা ভালো।


---

# 📚 Appendix B — Reference Map

এই playbook-এর structure ও terminology মিলিয়ে রাখা হয়েছে:

- OWASP Web Security Testing Guide: testing framework, authentication, authorization, session, input validation, business logic, client-side ও API testing।
- OWASP API Security Top 10 (2023): BOLA, broken authentication, property-level authorization, resource consumption, sensitive business flows এবং unsafe API consumption।
- MDN: cookie attributes ও Content Security Policy behavior।
- HackerOne safe harbor/scope guidance: explicitly in-scope asset, good-faith research ও harm avoidance।

### Official references

- [OWASP WSTG — Stable](https://owasp.org/www-project-web-security-testing-guide/stable/)
- [OWASP WSTG — Latest](https://owasp.org/www-project-web-security-testing-guide/latest/)
- [OWASP API Security Top 10 — 2023](https://owasp.org/API-Security/editions/2023/en/0x11-t10/)
- [MDN — Set-Cookie](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Set-Cookie)
- [MDN — Content-Security-Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Content-Security-Policy)
- [HackerOne — Safe Harbor Overview](https://docs.hackerone.com/en/articles/8494502-safe-harbor-overview-faq)


---

# 📚 Appendix C — Original Full Response-Analysis Checklist

নিচের অংশটি আগের checklist-এর সম্পূর্ণ সংস্করণ। উপরের ৪০টি অধ্যায়ে “কেন”, “কীভাবে”, “কখন থামবে” ও “কী evidence নেবে” ব্যাখ্যা করা হয়েছে; এই Appendix exhaustive checkbox reference হিসেবে থাকবে।

<details>
<summary><strong>▶ Original checklist খুলুন</strong></summary>

---

## Bug Bounty Web Response Analysis Checklist

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

## 1. Quick Triage

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

## 2. Scope and Safety

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

## 3. Response Status and Routing

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

## 4. Cookie Analysis

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

## 5. Authentication Testing

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

## 6. Authorization and IDOR

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

## 7. Session Management

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

## 8. CSRF

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

## 9. XSS and Output Encoding

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

## 10. CSP

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

## 11. NoSQL Injection

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

## 12. SQL Injection

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

## 13. CORS

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

## 14. Security Headers

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

## 15. Caching and CDN Behavior

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

## 16. Rate Limiting and Brute Force

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

## 17. File Upload

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

## 18. Path Traversal and File Read

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

## 19. Open Redirect

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

## 20. SSRF

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

## 21. Business Logic

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

## 22. API and JSON Testing

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

## 23. Node.js and Express Checks

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

## 24. Information Disclosure

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

## 25. Error Handling

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

## 26. Transport Security

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

## 27. Clickjacking

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

## 28. WebSocket Checks

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

## 29. GraphQL Checks

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

## 30. Evidence Collection

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

## 31. Severity and Impact

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

## 32. Bug Report Template

```markdown
## Title

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

## 33. Example Analysis of the Given Response

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

## 34. Final Testing Workflow

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


---


</details>

