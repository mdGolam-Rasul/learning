# 🔍 Day 03 — WAF Detection & Fingerprinting Mastery

> **Part of:** 30-Day WAF Bypass & Payload Crafting Journey  
> **Date:** _Add your date_  
> **Difficulty:** ⭐⭐☆☆☆ Beginner-Intermediate  
> **Time Required:** 3.5–4 hours  

![Day](https://img.shields.io/badge/Day-03%2F30-blue)
![Status](https://img.shields.io/badge/Status-In%20Progress-yellow)
![Focus](https://img.shields.io/badge/Focus-WAF%20Detection-orange)
![Difficulty](https://img.shields.io/badge/Difficulty-Beginner%2B-yellowgreen)

> ⚠️ **Ethical Use Only:**  
> Ei note shudhu educational purpose, personal lab, CTF, PortSwigger labs, DVWA/Juice Shop, or authorized bug bounty / pentest scope er jonno. Unauthorized target e active testing korba na.

---

## 📑 Table of Contents

- [🎯 Objectives](#-objectives)
- [⏰ Time Breakdown](#-time-breakdown)
- [📚 Session 1: Fingerprinting Theory](#-session-1-fingerprinting-theory)
- [🔧 Session 2: Tool-Based Detection](#-session-2-tool-based-detection)
- [🕵️ Session 3: Manual Fingerprinting](#️-session-3-manual-fingerprinting)
- [🐍 Session 4: Build Custom Python Scanner](#-session-4-build-custom-python-scanner)
- [🌐 Session 5: Origin Exposure Assessment](#-session-5-origin-exposure-assessment)
- [🏆 Day 3 Challenge](#-day-3-challenge)
- [📋 Cheat Sheet](#-cheat-sheet)
- [⚠️ Common Mistakes](#️-common-mistakes-to-avoid)
- [📚 Resources](#-resources)
- [❓ Self-Check Questions](#-self-check-questions)
- [🚀 What’s Next](#-whats-next)
- [📝 My Day 3 Notes](#-my-day-3-notes)

---

## 🎯 Objectives

End of this day, I will be able to:

- [ ] Fingerprint WAFs using **passive and active** techniques
- [ ] Use `wafw00f`, `whatwaf`, and Nmap scripts effectively
- [ ] Identify WAF type by analyzing **headers, cookies, and status codes**
- [ ] Write a **custom Python script** for automated WAF detection
- [ ] Understand basics of **origin exposure assessment**
- [ ] Build a personal **WAF Atlas** / fingerprint database

---

## ⏰ Time Breakdown

| Session | Topic | Duration |
|---|---|---:|
| 1 | Fingerprinting Theory | 30 min |
| 2 | Tool-Based Detection | 60 min |
| 3 | Manual Fingerprinting | 45 min |
| 4 | Build Custom Python Scanner | 60 min |
| 5 | Origin Exposure Assessment | 45 min |
| **Total** |  | **~4 hours** |

---

## 📚 Session 1: Fingerprinting Theory

### What is WAF Fingerprinting?

**WAF fingerprinting** means identifying:

- Which WAF protects a target
- What visible fingerprints it exposes
- What behavior changes happen during suspicious requests
- What rules or detection logic may be active

Ideally, fingerprinting should start with **passive analysis** before any active testing.

---

## Why It Matters

> 🎯 Knowing the WAF helps you understand how traffic is inspected, blocked, challenged, or logged.

Each WAF has different:

- Headers
- Cookies
- Block pages
- Status code behavior
- Rule sets
- Detection models
- False positive patterns

---

## Two Approaches

### 🟢 Passive Fingerprinting

Passive fingerprinting does **not** send attack payloads.

It analyzes normal responses only.

**Signals:**

- `Server` header
- `X-*` headers
- Cookies
- DNS records
- TLS certificate details
- CDN/WAF provider hints

**Pros:**

- Safer
- Less noisy
- Good for first-stage recon

---

### 🔴 Active Fingerprinting

Active fingerprinting sends test payloads and observes behavior changes.

**Signals:**

- Status code changes
- Block pages
- New headers
- Request drops
- Challenge pages
- Rate-limit behavior

> ⚠️ Active testing must be done only on authorized targets.

---

## Detection Vectors

```text
┌─────────────────────────────────────────┐
│ WAF Fingerprinting Signals              │
├─────────────────────────────────────────┤
│ 1. Response headers                     │
│ 2. Cookies                              │
│ 3. Status codes                         │
│ 4. Block page HTML/title                │
│ 5. Response time anomalies              │
│ 6. TLS certificate information          │
│ 7. DNS records                          │
│ 8. Known CDN/WAF IP ranges              │
└─────────────────────────────────────────┘
```

---

## Fingerprinting Workflow

```text
1. Passive recon
      ↓
2. Header and cookie analysis
      ↓
3. Tool-based confirmation
      ↓
4. Authorized active probing
      ↓
5. Block response study
      ↓
6. Document findings in WAF Atlas
```

---

## 🔧 Session 2: Tool-Based Detection

## Tool 1: `wafw00f`

`wafw00f` is one of the most popular WAF detection tools.

### Installation

```bash
pip3 install wafw00f
```

Or from source:

```bash
git clone https://github.com/EnableSecurity/wafw00f
cd wafw00f
python3 setup.py install
```

### Basic Usage

```bash
# Single target
wafw00f https://example.com

# Check for all known WAFs
wafw00f -a https://example.com

# List detectable WAFs
wafw00f -l

# Verbose mode
wafw00f -v https://example.com

# Save output
wafw00f https://example.com -o result.txt

# Read targets from file
wafw00f -i targets.txt
```

### Sample Output

```text
[*] Checking https://example.com
[+] The site https://example.com is behind Cloudflare WAF.
[~] Number of requests: 2
```

---

## Tool 2: `whatwaf`

```bash
git clone https://github.com/Ekultek/whatwaf
cd whatwaf
pip3 install -r requirements.txt
python3 whatwaf.py -u https://example.com
```

With tamper checks:

```bash
python3 whatwaf.py -u https://example.com --tamper
```

> ⚠️ Use only on authorized targets.

---

## Tool 3: Nmap WAF Scripts

```bash
# Detect WAF presence
nmap -p80,443 --script http-waf-detect example.com

# Fingerprint WAF
nmap -p80,443 --script http-waf-fingerprint example.com
```

Combined:

```bash
nmap -p80,443 \
  --script=http-waf-detect,http-waf-fingerprint \
  example.com -v
```

---

## Tool 4: Burp Suite Extensions

Install from **BApp Store**:

- WAF Cookie Fetcher
- Active Scan++
- Backslash Powered Scanner
- Hackvertor

---

## Tool Comparison

| Tool | Speed | Accuracy | WAF Coverage | Stealth |
|---|---|---|---|---|
| `wafw00f` | Fast | High | 150+ | Medium |
| `whatwaf` | Slow | High | 40+ | Noisy |
| Nmap scripts | Fast | Medium | 30+ | Medium |
| Manual `curl` | Slow | High | Unlimited | High |

---

## 🕵️ Session 3: Manual Fingerprinting

## Step 1: Baseline Request

```bash
curl -sI https://target.com | tee baseline.txt
```

Look for:

- `Server`
- `X-Powered-By`
- Custom `X-*` headers
- `Set-Cookie`
- Redirect behavior
- CDN/WAF hints

---

## Step 2: Cookie Analysis

| Cookie Pattern | Possible WAF |
|---|---|
| `__cf_bm`, `cf_clearance` | Cloudflare |
| `incap_ses_*`, `visid_incap_*` | Imperva Incapsula |
| `TS01*`, `TS######` | F5 BIG-IP ASM |
| `barra_counter_session` | Barracuda |
| `FORTIWAFSID` | Fortinet FortiWeb |
| `ak_bmsc`, `bm_sz`, `_abck` | Akamai Bot Manager |
| `AWSALB`, `AWSALBCORS` | AWS / AWS WAF related |
| `citrix_ns_id` | Citrix NetScaler |

---

## Step 3: Header Fingerprints

| Header / Indicator | Possible WAF |
|---|---|
| `Server: cloudflare` | Cloudflare |
| `CF-RAY` | Cloudflare |
| `Server: AkamaiGHost` | Akamai |
| `X-Iinfo` | Imperva |
| `X-Sucuri-ID`, `X-Sucuri-Cache` | Sucuri |
| `Server: BigIP` | F5 BIG-IP |
| `X-denied-reason` | WebKnight |
| `X-Mod-Security` | ModSecurity |
| `Server: Wallarm` | Wallarm |

---

## Step 4: Authorized Active Probing

Send mild test payloads and compare with baseline.

```bash
# XSS probe
curl -v "https://target.com/?test=<script>alert(1)</script>"

# SQLi probe
curl -v "https://target.com/?id=1' OR '1'='1"

# Path traversal probe
curl -v "https://target.com/../../etc/passwd"

# Command injection probe
curl -v "https://target.com/?cmd=;cat /etc/passwd"

# Suspicious User-Agent probe
curl -v -A "() { :;}; echo vulnerable" https://target.com/
```

> ⚠️ Run these only on local labs, CTFs, or targets where active testing is allowed.

Compare with baseline:

- Did status code change?
- Did new headers appear?
- Did block page appear?
- Did response time change?
- Did the request get dropped?

---

## Step 5: Block Page Analysis

Save block pages for your WAF Atlas.

<details>
<summary>Example block page indicators</summary>

### Cloudflare

```html
<title>Attention Required! | Cloudflare</title>
<h1>Sorry, you have been blocked</h1>
<!-- Ray ID: ... -->
```

### Akamai

```text
Reference #18.xxxxxxxx.xxxxxxxx.xxxxxxxx
```

### ModSecurity

```text
Mod_Security Action
406 Not Acceptable
```

### AWS WAF

```html
<title>403 Forbidden</title>
<h1>403 ERROR</h1>
The request could not be satisfied.
Request blocked.
```

### Imperva Incapsula

```text
_Incapsula_Resource
```

### Sucuri

```html
<title>Access Denied - Sucuri Website Firewall</title>
```

</details>

---

## Manual Detection Workflow

```bash
# 1. Baseline
curl -sI https://target.com > baseline.txt

# 2. Authorized test probe
curl -sI "https://target.com/?q=<script>alert(1)</script>" > probe.txt

# 3. Compare
diff baseline.txt probe.txt
```

---

## 🐍 Session 4: Build Custom Python Scanner

### Goal

Build a lightweight WAF fingerprinter to understand detection logic.

This scanner:

- Checks headers
- Checks cookies
- Checks page body
- Assigns confidence score
- Supports passive mode by default
- Supports active mode only with explicit `--active`

---

## Script: `waf_detector.py`

```python
#!/usr/bin/env python3
"""
Custom WAF Fingerprinter
Day 03 of 30-Day WAF Bypass & Payload Crafting Journey

Use only on authorized targets.
Default mode is passive.
Active probing requires --active.
"""

import argparse
import json
import re
import sys
from typing import Dict, List, Tuple

import requests
from requests import Response

requests.packages.urllib3.disable_warnings()


WAF_SIGNATURES: Dict[str, Dict[str, List[str]]] = {
    "Cloudflare": {
        "headers": [r"cloudflare", r"cf-ray", r"cf-cache-status"],
        "cookies": [r"__cf_bm", r"cf_clearance"],
        "body": [r"cloudflare", r"attention required"],
    },
    "AWS WAF": {
        "headers": [r"x-amz-cf-id", r"x-amz-cf-pop", r"awselb"],
        "cookies": [r"awsalb", r"awsalbcors"],
        "body": [r"aws", r"request blocked"],
    },
    "Akamai": {
        "headers": [r"akamai", r"x-akamai", r"akamaighost"],
        "cookies": [r"ak_bmsc", r"bm_sz", r"_abck"],
        "body": [r"reference #\d+"],
    },
    "Imperva Incapsula": {
        "headers": [r"x-iinfo", r"x-cdn.*incapsula"],
        "cookies": [r"incap_ses", r"visid_incap"],
        "body": [r"incapsula", r"_incapsula_resource"],
    },
    "Sucuri": {
        "headers": [r"x-sucuri-id", r"x-sucuri-cache", r"sucuri"],
        "cookies": [],
        "body": [r"sucuri", r"access denied"],
    },
    "ModSecurity": {
        "headers": [r"mod_security", r"modsecurity"],
        "cookies": [],
        "body": [r"mod_security", r"not acceptable"],
    },
    "F5 BIG-IP": {
        "headers": [r"bigip", r"x-wa-info"],
        "cookies": [r"ts[0-9a-f]{8}", r"bigipserver"],
        "body": [r"the requested url was rejected"],
    },
    "Fortinet FortiWeb": {
        "headers": [r"fortiweb", r"fortigate"],
        "cookies": [r"fortiwafsid"],
        "body": [r"fortinet", r"blocked by fortiweb"],
    },
    "Barracuda": {
        "headers": [r"barracuda", r"barra"],
        "cookies": [r"barra_counter_session"],
        "body": [r"barracuda"],
    },
    "Wallarm": {
        "headers": [r"nginx-wallarm", r"wallarm"],
        "cookies": [],
        "body": [r"wallarm"],
    },
}


ACTIVE_PAYLOADS = [
    "?test=<script>alert(1)</script>",
    "?id=1' OR '1'='1",
    "?file=../../etc/passwd",
]


def fetch(url: str, timeout: int = 10) -> Response | None:
    try:
        return requests.get(
            url,
            timeout=timeout,
            verify=False,
            allow_redirects=True,
            headers={"User-Agent": "Mozilla/5.0 (WAF-Detector/1.0)"},
        )
    except requests.RequestException as error:
        print(f"[!] Error fetching {url}: {error}", file=sys.stderr)
        return None


def match_signatures(response: Response | None) -> List[Tuple[str, int, List[str]]]:
    if not response:
        return []

    matches = []
    headers_str = str(response.headers).lower()
    cookies_str = str(response.cookies).lower()
    body_str = response.text.lower()[:5000]

    for waf_name, signatures in WAF_SIGNATURES.items():
        score = 0
        evidence = []

        for pattern in signatures["headers"]:
            if re.search(pattern, headers_str, re.IGNORECASE):
                score += 2
                evidence.append(f"header:{pattern}")

        for pattern in signatures["cookies"]:
            if re.search(pattern, cookies_str, re.IGNORECASE):
                score += 2
                evidence.append(f"cookie:{pattern}")

        for pattern in signatures["body"]:
            if re.search(pattern, body_str, re.IGNORECASE):
                score += 1
                evidence.append(f"body:{pattern}")

        if score > 0:
            matches.append((waf_name, score, evidence))

    return sorted(matches, key=lambda item: item[1], reverse=True)


def detect_waf(target: str, active: bool = False, timeout: int = 10) -> Dict:
    print(f"\n{'=' * 60}")
    print(f"🎯 Target: {target}")
    print("=" * 60)

    print("\n[1] Sending baseline request...")
    baseline = fetch(target, timeout=timeout)

    if not baseline:
        return {"target": target, "error": "Request failed"}

    print(f"    Status: {baseline.status_code}")
    print(f"    Server: {baseline.headers.get('Server', 'N/A')}")

    all_matches = match_signatures(baseline)

    if active:
        print("\n[2] Active probing enabled...")
        for payload in ACTIVE_PAYLOADS:
            test_url = target.rstrip("/") + "/" + payload
            response = fetch(test_url, timeout=timeout)

            if response and response.status_code != baseline.status_code:
                print(f"    ⚠️ Status change with {payload}: {response.status_code}")
                all_matches.extend(match_signatures(response))
    else:
        print("\n[2] Active probing skipped. Use --active only on authorized targets.")

    unique = {}

    for waf_name, score, evidence in all_matches:
        if waf_name not in unique or unique[waf_name]["score"] < score:
            unique[waf_name] = {
                "score": score,
                "evidence": sorted(set(evidence)),
            }

    print("\n[3] Detection Results:")

    if unique:
        for waf_name, data in sorted(unique.items(), key=lambda item: -item[1]["score"]):
            print(f"    ✅ {waf_name} | confidence: {data['score']}")
            for evidence in data["evidence"]:
                print(f"       └─ {evidence}")
    else:
        print("    ❓ No WAF fingerprint detected")

    return {
        "target": target,
        "status_code": baseline.status_code,
        "server": baseline.headers.get("Server", "N/A"),
        "active_mode": active,
        "matches": unique,
    }


def main() -> None:
    parser = argparse.ArgumentParser(description="Custom WAF Fingerprinter")
    parser.add_argument("url", help="Target URL, e.g. https://example.com")
    parser.add_argument("--active", action="store_true", help="Enable active probing")
    parser.add_argument("--json", action="store_true", help="Print JSON output")
    parser.add_argument("--timeout", type=int, default=10, help="Request timeout")

    args = parser.parse_args()

    result = detect_waf(args.url, active=args.active, timeout=args.timeout)

    if args.json:
        print(json.dumps(result, indent=2))


if __name__ == "__main__":
    main()
```

---

## Run It

Passive mode:

```bash
python3 waf_detector.py https://example.com
```

Active mode for authorized targets only:

```bash
python3 waf_detector.py https://example.com --active
```

JSON output:

```bash
python3 waf_detector.py https://example.com --json
```

---

## Exercises

- [ ] Add 3 new WAF signatures
- [ ] Add multi-target scanning from a file
- [ ] Add proxy support for Burp integration
- [ ] Add CSV export
- [ ] Add rate limiting between requests

---

## 🌐 Session 5: Origin Exposure Assessment

> Goal: Understand how cloud WAF deployments can fail when the origin server is exposed directly.

---

## Why Origin Exposure Matters

Cloud WAF protected flow:

```text
[Client]
   ↓
[Cloud WAF / CDN]
   ↓
[Origin Server]
```

If the origin server accepts traffic directly from the internet, then traffic may reach the app without passing through the WAF.

This is a **defensive configuration issue**.

---

## Defensive Questions to Ask

- Is the origin server publicly reachable?
- Does the origin only allow CDN/WAF IP ranges?
- Are old DNS records leaking real origin IPs?
- Are subdomains bypassing the WAF?
- Do mail or staging servers reveal infrastructure?

---

## Discovery Techniques

### 1. Historical DNS Records

Look for old A records that may reveal previous origin IPs.

Free tools:

- ViewDNS.info
- DNSdumpster
- CompleteDNS
- SecurityTrails

---

### 2. Certificate Transparency Logs

Find related subdomains:

```bash
curl "https://crt.sh/?q=example.com&output=json" | jq
```

---

### 3. Subdomain Enumeration

```bash
subfinder -d example.com -all -silent | httpx -silent -status-code -ip
```

Alternative tools:

- `amass`
- `assetfinder`
- `findomain`

Look for hosts not routed through the expected WAF/CDN.

---

### 4. Internet Asset Search Engines

Use asset search engines for defensive exposure review:

- Shodan
- Censys
- ZoomEye

Example search ideas:

```text
ssl.cert.subject.cn:example.com
http.title:"Target Site"
```

---

### 5. Email Header Review

Email headers may expose infrastructure.

Look for `Received:` headers:

```text
Received: from mail.example.com (203.0.113.45)
```

---

### 6. DNS Misconfiguration Checks

```bash
dig MX example.com
dig TXT example.com
dig A mail.example.com
dig A direct.example.com
dig A origin.example.com
```

---

## Safe Verification

If you are testing your own infrastructure or an authorized target, confirm whether the origin is reachable:

```bash
curl -k -H "Host: example.com" https://ORIGIN_IP/
```

If the same application loads directly from the origin, document it as an exposure and fix the configuration.

---

## Recommended Fixes

- Allow inbound traffic only from CDN/WAF IP ranges
- Block direct internet access to origin
- Rotate exposed origin IP if needed
- Remove old DNS records
- Avoid exposing staging/admin subdomains publicly
- Monitor certificate transparency logs
- Review mail, SPF, and MX records for IP leaks

---

## 🏆 Day 3 Challenge

Complete all tasks to mark Day 3 done:

- [ ] Run `wafw00f -a` on authorized or lab targets and log results
- [ ] Run `whatwaf` and compare with `wafw00f`
- [ ] Execute Nmap WAF scripts on authorized targets
- [ ] Manually fingerprint 3 WAFs using `curl` + header analysis
- [ ] Build and run the custom Python scanner
- [ ] Add 3 new WAF signatures to the Python scanner
- [ ] Perform origin exposure assessment on your own lab/domain
- [ ] Save 5 block page screenshots for your WAF Atlas
- [ ] Push `Day-03.md` + `waf_detector.py` to GitHub repo

---

## 📋 Cheat Sheet

## Quick WAF Detection Commands

```bash
# Passive
curl -sI https://target.com

# Headers and cookies
curl -sv https://target.com 2>&1 | grep -iE "server|cookie|x-"

# Tool-based detection
wafw00f -a https://target.com

# Manual active check — authorized targets only
curl "https://target.com/?q=<script>alert(1)</script>" -I

# Nmap scripts — authorized targets only
nmap --script http-waf-detect,http-waf-fingerprint target.com

# Custom script
python3 waf_detector.py https://target.com
```

---

## WAF Identification Matrix

| Indicator | Possible WAF |
|---|---|
| `cf-ray`, `cf_clearance`, `__cf_bm` | Cloudflare |
| `X-Iinfo`, `incap_ses` | Imperva |
| `AkamaiGHost`, `ak_bmsc` | Akamai |
| `X-Sucuri-ID` | Sucuri |
| `AWSALB`, AWS-style 403 | AWS WAF |
| `Mod_Security` | ModSecurity |
| `BigIP`, `TS01xxxx` | F5 BIG-IP |
| `FORTIWAFSID` | Fortinet |
| `barra_counter_session` | Barracuda |

---

## Origin Exposure Quick Commands

```bash
# Certificate transparency subdomain discovery
curl "https://crt.sh/?q=example.com&output=json" | jq '.[].name_value' | sort -u

# Subdomain enumeration with IP visibility
subfinder -d example.com | httpx -ip

# Safe origin reachability check for authorized targets
curl -k -H "Host: example.com" https://ORIGIN_IP/
```

---

## ⚠️ Common Mistakes to Avoid

1. Only trusting one tool — always cross-verify
2. Active scanning on unauthorized targets
3. Ignoring manual fingerprinting
4. Not saving block pages
5. Treating origin exposure as “normal”
6. Running noisy scans that trigger rate limits
7. Forgetting to document evidence

---

## 📚 Resources

### Essential Repositories

- [EnableSecurity/wafw00f](https://github.com/EnableSecurity/wafw00f)
- [Ekultek/whatwaf](https://github.com/Ekultek/whatwaf)
- [0xInfection/Awesome-WAF](https://github.com/0xInfection/Awesome-WAF)
- [m0rtem/CloudFail](https://github.com/m0rtem/CloudFail)
- [christophetd/CloudFlair](https://github.com/christophetd/CloudFlair)

### Reading

- [Cloudflare — What is a WAF?](https://www.cloudflare.com/learning/ddos/glossary/web-application-firewall-waf/)
- [OWASP — WAF Evaluation Criteria](https://owasp.org/www-pdf-archive/WASC-WAFEC-2006-v1.0.pdf)
- HackerOne Hacktivity: Search “WAF bypass” writeups

### Practice Targets

- Your own ModSecurity Docker lab
- DVWA
- OWASP Juice Shop
- PortSwigger Web Security Academy labs
- Bug bounty targets only within valid scope

---

## ❓ Self-Check Questions

1. Passive vs active WAF fingerprinting — difference ki?
2. `wafw00f` kon techniques use kore WAF identify korte?
3. Cloudflare detect korar top 3 fingerprints ki?
4. Origin exposure cloud WAF deployment e keno risky?
5. Nmap er kon scripts WAF fingerprint kore?
6. `403` vs `406` vs `501` — WAF context e ki indicate kore?
7. Certificate transparency logs theke kivabe related subdomain khuja jay?
8. Custom Python scanner e confidence score kivabe calculate hocche?

✅ All 8 answered correctly? **Day 3 complete!**

---

## 🚀 What’s Next?

**Day 4 Preview:** OWASP Top 10 Quick Review + Root Cause Analysis

- XSS, SQLi, SSRF, RCE recap
- PortSwigger Academy intro labs
- Vulnerability → Payload mapping
- Building mental model of web vulnerabilities

---

## 📝 My Day 3 Notes

<!-- Fill in after completion -->

### WAFs Detected Today

| Target | WAF | Tool Used | Confidence |
|---|---|---|---|
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

---

### Custom Scanner Results

- Total signatures added: ______
- WAFs detected successfully: ______
- False positives: ______

---

### Block Pages Saved

- [ ] Cloudflare
- [ ] Akamai
- [ ] ModSecurity
- [ ] AWS WAF
- [ ] Imperva

---

### Origin Exposure Assessment

| Domain | Method | Result |
|---|---|---|
|  |  |  |

---

### Key Learnings

- 
- 
- 

---

### Challenges Faced

- 
- 

---

### Tomorrow’s Prep

- [ ] Review OWASP Top 10
- [ ] PortSwigger account ready
- [ ] DVWA/Juice Shop installed
- [ ] ModSecurity lab ready

---

<p align="center">
  <strong>🎓 Day 3 Status:</strong> ⬜ In Progress / ✅ Complete<br>
  <em>“Know your enemy and know yourself; in a hundred battles you will never be defeated.” — Sun Tzu</em>
</p>

<p align="center">
  <a href="./Day-02.md">← Previous: Day 02</a> |
  <a href="./Day-04.md">Next: Day 04 →</a>
</p>
