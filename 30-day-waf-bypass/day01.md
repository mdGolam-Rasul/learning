# 🌐 Day 01 — Web Security Fundamentals & Environment Setup

**Part of:** 30-Day WAF Bypass & Payload Crafting Journey  
**Date:** `Add your date`  
**Difficulty:** ⭐☆☆☆☆ Beginner  
**Time Required:** 3–4 hours  

> Ethical learning only. Test only on authorized targets, labs, or intentionally vulnerable applications.

---

## 📌 Day Status

| Day | Focus | Difficulty | Status |
|---|---|---|---|
| 01 | Web Security Fundamentals & Environment Setup | Beginner | ⬜ In Progress |

---

## 📑 Table of Contents

- [🎯 Objectives](#-objectives)
- [⏰ Time Breakdown](#-time-breakdown)
- [📚 Session 1: HTTP/HTTPS Deep Dive](#-session-1-httphttps-deep-dive)
- [🔧 Session 2: Burp Suite Setup](#-session-2-burp-suite-setup)
- [🧪 Session 3: Hands-on Lab](#-session-3-hands-on-lab)
- [🌐 Session 4: Browser DevTools Mastery](#-session-4-browser-devtools-mastery)
- [📝 Session 5: Notes + Mini Challenge](#-session-5-notes--mini-challenge)
- [🏆 Day 1 Challenge](#-day-1-challenge)
- [📋 Cheat Sheet](#-cheat-sheet)
- [⚠️ Common Mistakes](#️-common-mistakes-to-avoid)
- [📚 Resources](#-resources)
- [❓ Self-Check](#-self-check-questions)
- [🚀 What’s Next](#-whats-next)
- [📝 My Day 1 Notes](#-my-day-1-notes)

---

## 🎯 Objectives

End of this day, I will be able to:

- [ ] Understand HTTP/HTTPS protocol deeply
- [ ] Understand the request/response cycle
- [ ] Configure Burp Suite and intercept browser traffic
- [ ] Use Browser DevTools for request analysis
- [ ] Map a target website’s request-response flow
- [ ] Identify which HTTP elements matter for WAF bypass

---

## ⏰ Time Breakdown

| Session | Topic | Duration |
|---|---|---:|
| 1 | HTTP/HTTPS Theory Deep Dive | 45 min |
| 2 | Burp Suite Installation & Setup | 45 min |
| 3 | Hands-on Lab: Intercepting Traffic | 60 min |
| 4 | Browser DevTools Mastery | 30 min |
| 5 | Notes + Mini Challenge | 30 min |
| **Total** |  | **~3.5 hours** |

---

## 📚 Session 1: HTTP/HTTPS Deep Dive

### Why HTTP Matters for WAF Bypass?

WAF basically HTTP requests inspect kore.  
Jodi tumi HTTP er prottekta component na bojho, bypass korte parbe na.

You need to know:

- Where to inject
- What to modify
- How WAF sees the data
- Which part of the request is being filtered

---

## HTTP Request Anatomy

```http
POST /login HTTP/1.1
Host: example.com
User-Agent: Mozilla/5.0
Cookie: session=abc123
Content-Type: application/x-www-form-urlencoded
Content-Length: 29
X-Forwarded-For: 127.0.0.1

username=admin&password=test
```

### 3 Main Components

1. **Request Line** — Method + Path + Version  
2. **Headers** — Metadata  
3. **Body** — Actual submitted data  

---

## HTTP Methods — Bypass Context

| Method | Use Case | WAF Bypass Angle |
|---|---|---|
| `GET` | Data fetch | Query params injection |
| `POST` | Data submit | Body injection |
| `PUT` | Upload/update | Sometimes missed by WAF rules |
| `DELETE` | Remove resource | Rarely filtered |
| `OPTIONS` | Preflight | Info disclosure |
| `TRACE` | Debug | XST attacks |
| `PATCH` | Partial update | Often overlooked |

> 💡 **Pro Insight:** Onek WAF shudhu `GET`/`POST` strictly inspect kore. Sometimes same payload `PUT`/`PATCH` method e different behavior dite pare.

---

## Critical Headers for WAF Bypass

| Header | Bypass Angle |
|---|---|
| `Host` | Virtual host confusion |
| `X-Forwarded-For` | IP spoofing, rate-limit bypass |
| `X-Real-IP` | Origin detection bypass |
| `X-Originating-IP` | Trust-header bypass |
| `Content-Type` | Parser confusion |
| `Transfer-Encoding` | Request smuggling related behavior |
| `User-Agent` | Whitelist abuse |
| `Referer` | Origin-based rule bypass |
| `Cookie` | Session + injection point |

---

## HTTP Status Codes — WAF Relevant

| Code | Meaning | WAF Context |
|---|---|---|
| `200` | OK | Success or silent filtering |
| `301/302` | Redirect | Challenge page or redirect |
| `403` | Forbidden | Classic WAF block |
| `406` | Not Acceptable | WAF rejection |
| `419/429` | Too Many Requests | Rate limit / throttle |
| `501` | Not Implemented | Possible ModSecurity signature |
| `503` | Service Unavailable | Origin down or WAF issue |

---

## 🔧 Session 2: Burp Suite Setup

Burp Suite = tomar primary tool for next 29 days.  
Aaj setup perfectly koro.

---

## Step-by-Step Installation

### 1. Download Burp Suite Community

Official download:

```text
https://portswigger.net/burp/communitydownload
```

Java 11+ required if using standalone JAR.

```bash
# Linux
wget "https://portswigger.net/burp/releases/download?product=community&type=Jar"
java -jar burpsuite_community.jar
```

---

## 2. Browser Configuration

Firefox recommended.

```text
Firefox → Settings → Network Settings → Manual Proxy

HTTP Proxy: 127.0.0.1
Port: 8080

✓ Also use this proxy for HTTPS
```

> 💡 **Pro Tip:** FoxyProxy extension use korle proxy on/off easily toggle kora jay.

---

## 3. Install Burp CA Certificate

1. Start Burp Suite
2. Visit `http://burp` in your proxied browser
3. Click **CA Certificate**
4. Download `cacert.der`
5. Firefox → Settings → Privacy & Security → Certificates
6. View Certificates → Authorities → Import
7. Check: **Trust this CA to identify websites**

---

## 4. Test Setup

1. Burp → Proxy tab
2. Intercept ON
3. Browser e visit:

```text
https://example.com
```

4. Request Burp e capture hole setup complete.

✅ Setup complete!

---

## Essential Burp Shortcuts

| Action | Shortcut |
|---|---|
| Send to Repeater | `Ctrl + R` |
| Send to Intruder | `Ctrl + I` |
| Forward request | `Ctrl + F` |
| Drop request | `Ctrl + D` |
| Toggle intercept | `Ctrl + T` |
| Search in history | `Ctrl + S` |

---

## 🧪 Session 3: Hands-on Lab

> Use only legal testing targets or your own lab.

---

## Lab 1: Intercept & Modify Request

**Target:** `http://testphp.vulnweb.com`  
**Time:** 20 min

### Steps

1. Burp Intercept ON
2. Browser e site visit koro
3. Login form e random credentials submit koro
4. Burp e intercepted request observe koro:
   - Method
   - Body parameters
   - Headers
5. `username` field modify koro
6. Forward request
7. Response observe koro

<details>
<summary>🔍 Expected Observations</summary>

- Server responds with error/success based on modified input
- Session cookie may be set
- Response headers may reveal server tech

</details>

---

## Lab 2: Repeater Practice

**Time:** 20 min

1. Intercepted request → Send to Repeater
2. Try different test inputs:

```text
Normal:     admin
XSS test:   <script>alert(1)</script>
SQLi test:  ' OR '1'='1
LFI test:   ../../../../etc/passwd
Cmd inj:    ;whoami
```

3. Document how server reacts to each payload.

> 💡 Goal: Aaj shudhu baseline behavior bujha. Unauthorized testing kora jabe na.

---

## Lab 3: WAF Detection Prep

**Time:** 20 min

Passive observation only.

```bash
curl -sI https://www.cloudflare.com | grep -i "server\|cf-"
curl -sI https://www.hackerone.com | grep -i "server\|x-"
```

### What to Look For

- `Server` header
- `X-Powered-By`
- WAF-specific cookies:
  - `cf_clearance` → Cloudflare
  - `incap_ses_*` → Imperva
  - `X-Sucuri-ID` → Sucuri

---

## 🌐 Session 4: Browser DevTools Mastery

---

## Must-Know Tabs

### 1. Network Tab

Use for:

- Capturing every request
- Filtering XHR, JS, CSS, Doc, Img
- Copying request as cURL

```bash
curl 'https://example.com/api' \
  -H 'Cookie: session=xxx' \
  -H 'User-Agent: Mozilla/5.0'
```

---

## 2. Console Tab

Useful JavaScript commands:

```javascript
document.cookie
document.domain
document.querySelectorAll('input')
fetch('/api/user').then(r => r.json())
```

---

## 3. Application Tab

Use for checking:

- Cookies
- LocalStorage
- SessionStorage
- IndexedDB
- Service Workers

---

## 4. Sources Tab

Client-side JS code review.

Search for:

- Hidden API endpoints
- Hardcoded credentials
- Debug routes

---

## Mini Exercise

1. Visit `example.com`
2. Open DevTools → Network tab
3. Reload page
4. Count total requests
5. Identify biggest resource
6. Copy one request as cURL
7. Replay it in terminal

---

## 📝 Session 5: Notes + Mini Challenge

## Day 1 Notes Template

```markdown
# Day 01 — HTTP & Burp Suite Foundation

## Key Learnings

- [ ] HTTP request structure: request line, headers, body
- [ ] Important headers for WAF bypass
- [ ] HTTP methods bypass potential
- [ ] Status codes interpretation

## Burp Suite Setup

Version: _______

- [ ] CA Certificate installed
- [ ] Browser proxy configured

## Observations

Biggest learning today: _______

Questions to research: _______

## Tomorrow's Focus

WAF types and architectures
```

---

## 🏆 Day 1 Challenge

Complete all tasks to mark Day 1 done:

- [ ] Burp Suite diye minimum **10 requests** intercept koro
- [ ] Ekta request er **all headers** identify + document koro
- [ ] Repeater e **5 different payloads** test koro
- [ ] Browser DevTools diye **API endpoint** discover koro
- [ ] **3 public sites** er HTTP response headers analyze koro
- [ ] Ekta request **Copy as cURL** kore terminal e replay koro
- [ ] Day 1 Notes complete koro
- [ ] Push this `Day-01.md` to your GitHub repo

---

## 📋 Cheat Sheet

### Quick Commands

```bash
# Inspect headers
curl -sI https://target.com

# Full response with headers
curl -sv https://target.com 2>&1 | less

# Specific method
curl -X PUT https://target.com/api

# Custom headers
curl -H "X-Forwarded-For: 127.0.0.1" https://target.com

# POST with body
curl -X POST -d "user=admin&pass=test" https://target.com/login

# Include cookies
curl -b "session=xxx" https://target.com
```

---

## Burp Workflow

```text
Intercept ON
→ Browse
→ Capture request
→ Right-click
→ Send to Repeater
→ Modify payload
→ Send
→ Analyze response
→ Review Proxy HTTP history
```

---

## HTTP Method Bypass Quick Reference

| If blocked on... | Try... |
|---|---|
| `GET` | `POST` with same params |
| `POST` | `PUT` or `PATCH` |
| Body inspection | Move payload to headers |
| Header inspection | URL-encode the value |
| Standard params | HTTP Parameter Pollution |

---

## ⚠️ Common Mistakes to Avoid

1. Burp CA certificate install na kore HTTPS errors dekha
2. Intercept always ON rekhe browsing frustrate hoya
3. Only theory reading, no hands-on practice
4. Notes na neya
5. HTTP basics skip kore advanced topics e jump kora
6. Unauthorized targets e testing

---

## 📚 Resources

### Must-Read

- [MDN — HTTP Overview](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)
- [PortSwigger Web Security Academy](https://portswigger.net/web-security)
- [OWASP HTTP Headers Cheat Sheet](https://owasp.org/www-project-secure-headers/)

### Video

- HTTP Crash Course — Traversy Media
- Burp Suite Basics — PortSwigger Official Channel

### Practice Playgrounds

- [httpbin.org](http://httpbin.org)
- [testphp.vulnweb.com](http://testphp.vulnweb.com)
- [hack.me](https://hack.me)

### Tools

- [Burp Suite Community](https://portswigger.net/burp/communitydownload)
- [OWASP ZAP](https://www.zaproxy.org/)
- [Postman](https://www.postman.com/)

---

## ❓ Self-Check Questions

1. HTTP request er 3 ta main component ki?
2. `X-Forwarded-For` header kivabe WAF bypass e help kore?
3. Burp Repeater vs Intruder er difference ki?
4. Kon status code gulo WAF block indicate kore?
5. Ekta POST request er body te payload kothay inject kora jay?
6. `Content-Type` header change kore bypass kivabe possible?
7. Browser DevTools Network tab er “Copy as cURL” keno useful?

✅ All 7 answered correctly? **Day 1 complete!**

---

## 🚀 What’s Next?

**Day 2 Preview:** WAF Architecture, Types & Detection Models

- How WAFs work internally
- Cloud vs Host vs Network WAFs
- Positive vs Negative security models
- Top 10 WAF vendor fingerprints

---

## 📝 My Day 1 Notes

<!-- Fill in after completion -->

### Tools Installed

- [ ] Burp Suite Community — Version: ______
- [ ] Firefox with proxy config
- [ ] CA Certificate imported

### Sites Analyzed

| Site | Server Header | WAF Suspected |
|---|---|---|
|  |  |  |
|  |  |  |
|  |  |  |

### Interesting Payloads Tested

- 
- 
- 

### Challenges Faced

- 

### Tomorrow’s Prep

- 

---

<p align="center">
  <strong>🎓 Day 1 Status:</strong> ⬜ In Progress / ✅ Complete<br>
  <em>“The expert in anything was once a beginner.” — Helen Hayes</em>
</p>

<p align="center">
  <a href="./Day-02.md">Next: Day 02 →</a>
</p>
