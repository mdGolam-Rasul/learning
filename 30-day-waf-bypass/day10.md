# ☁️ Day 10 — Cloud WAF Bypass Mastery + Origin IP Discovery

> **Part of:** 15-Day WAF Bypass & Payload Crafting Mastery  
> **Date:** _Add your date_  
> **Difficulty:** ⭐⭐⭐⭐⭐ Elite  
> **Time Required:** 7–8 hours  
> **Bounty Potential:** $10K–$100K+  
> **Focus:** Cloud WAF Recon, Origin Exposure, CDN Misconfiguration & Responsible Reporting  

![Day](https://img.shields.io/badge/Day-10%2F15-blue)
![Status](https://img.shields.io/badge/Status-Week%202%20Finale-red)
![Focus](https://img.shields.io/badge/Focus-Cloud%20WAF%20Bypass-critical)
![Bounty](https://img.shields.io/badge/Bounty-%2410K--%24100K%2B-gold)

> ⚠️ **Ethical Use Only:**  
> Ei guide shudhu legal lab, authorized bug bounty scope, approved pentest, private infrastructure, or defensive validation er jonno. Unauthorized testing, origin abuse, data access, credential extraction, destructive payload, or rate-limit abuse kora jabe na.

---

## 📑 Table of Contents

- [☁️ Why Cloud WAFs Are the Ultimate Target](#️-why-cloud-wafs-are-the-ultimate-target)
- [🎯 Objectives](#-objectives)
- [⏰ Time Breakdown](#-time-breakdown)
- [🔍 Session 1: Cloud WAF Landscape & Recon](#-session-1-cloud-waf-landscape--recon)
- [🎯 Session 2: Origin IP Discovery](#-session-2-origin-ip-discovery)
- [🛡️ Session 3: Cloudflare Deep Dive](#️-session-3-cloudflare-deep-dive)
- [🏢 Session 4: Akamai Bypass Concepts](#-session-4-akamai-bypass-concepts)
- [⚡ Session 5: AWS WAF & CloudFront](#-session-5-aws-waf--cloudfront)
- [🏦 Session 6: Imperva, Sucuri, F5 & Others](#-session-6-imperva-sucuri-f5--others)
- [📖 Session 7: Real $10K+ Bug Bounty Chains](#-session-7-real-10k-bug-bounty-chains)
- [🎯 Session 8: Live Hunting Methodology](#-session-8-live-hunting-methodology)
- [🔁 Micro-Habits Continuation](#-micro-habits-continuation)
- [🏆 Day 10 Challenge](#-day-10-challenge)
- [📋 Master Cheat Sheets](#-master-cheat-sheets)
- [📚 Resources](#-resources)
- [❓ Self-Check Questions](#-self-check-questions)
- [🎉 Week 2 Complete](#-week-2-complete)
- [🚀 What’s Next](#-whats-next)
- [📝 My Day 10 Notes](#-my-day-10-notes)
- [🚀 Commit Workflow](#-commit-workflow)
- [📊 Progress Update](#-progress-update)

---

# ☁️ Why Cloud WAFs Are the Ultimate Target

```text
┌─────────────────────────────────────────────────────────────┐
│                CLOUD WAF LANDSCAPE                          │
├─────────────────────────────────────────────────────────────┤
│ Cloudflare      → Mass internet coverage                    │
│ Akamai          → Enterprise, banks, Fortune 500             │
│ AWS WAF         → AWS-hosted applications                    │
│ Imperva         → Banking, government, enterprise            │
│ Fastly          → Media, SaaS, high-performance apps         │
│ Sucuri          → WordPress ecosystem                        │
└─────────────────────────────────────────────────────────────┘
```

## Why Elite Hunters Care

- **Scope:** Most modern bug bounty targets use a cloud WAF or CDN.
- **Complexity:** More layers create more misconfiguration opportunities.
- **Impact:** Origin exposure can bypass WAF rules entirely.
- **Competition:** Fewer hunters deeply understand cloud WAF behavior.

---

## The Two Main Paths

```text
         [Cloud WAF-Protected Target]
                    |
          ┌─────────┴─────────┐
          ↓                   ↓
    PATH 1: BYPASS        PATH 2: AVOID
    Defeat WAF rules      Find origin / skip WAF
          ↓                   ↓
    Encoding tricks       Origin IP discovery
    Payload mutation      Historical DNS
    HTTP desync           Subdomain enumeration
    Parser confusion      Certificate logs
```

> Today’s goal: understand both paths safely and responsibly.

---

# 🎯 Objectives

By the end of Day 10, I will be able to:

- [ ] Fingerprint major cloud WAFs confidently
- [ ] Understand origin exposure risks
- [ ] Use 8+ origin discovery methodologies in legal contexts
- [ ] Understand Cloudflare, Akamai, AWS WAF, Imperva, Sucuri, and F5 patterns
- [ ] Verify origin candidates safely
- [ ] Build a personal cloud WAF recon toolkit
- [ ] Analyze real-world bug bounty chains
- [ ] Write professional reports for origin exposure and WAF misconfiguration
- [ ] Continue daily hunter micro-habits

---

# ⏰ Time Breakdown

| Session | Topic | Duration |
|---|---|---:|
| 1 | Cloud WAF Landscape & Recon | 60 min |
| 2 | Origin IP Discovery Mastery | 90 min |
| 3 | Cloudflare Deep Dive | 90 min |
| 4 | Akamai Bypass Concepts | 75 min |
| 5 | AWS WAF & CloudFront | 75 min |
| 6 | Imperva, Sucuri, F5 & Others | 60 min |
| 7 | Real $10K+ Bug Bounty Chains | 90 min |
| 8 | Live Hunting Methodology | 60 min |
| **Total** |  | **~8 hours** |

---

# 🔍 Session 1: Cloud WAF Landscape & Recon

## Cloud WAF Architecture

```text
[User]
  ↓
[DNS: CNAME → target.cdn.com]
  ↓
[Cloud WAF Edge Node]
  ↓
[Request inspection + rules + caching]
  ↓
[Origin Server]
```

## Key Insight

```text
If the origin server accepts traffic directly from the internet,
the cloud WAF can become irrelevant.
```

---

## 1. DNS-Based Detection

```bash
dig target.com
dig CNAME target.com
dig A target.com
```

Common patterns:

| DNS Pattern | Possible Provider |
|---|---|
| `*.cloudflare.net` | Cloudflare |
| `*.edgekey.net` / `*.akamaiedge.net` | Akamai |
| `*.cloudfront.net` | AWS CloudFront |
| `*.fastly.net` | Fastly |
| `*.incapdns.net` | Imperva |
| `*.sucuri.net` | Sucuri |

---

## 2. HTTP Response Header Detection

```bash
curl -sI https://target.com
```

| Header / Cookie | Possible WAF |
|---|---|
| `Server: cloudflare` | Cloudflare |
| `CF-RAY` | Cloudflare |
| `CF-Cache-Status` | Cloudflare |
| `Server: AkamaiGHost` | Akamai |
| `X-Akamai-*` | Akamai |
| `X-Amz-Cf-Id` | AWS CloudFront |
| `Via: ...CloudFront` | AWS CloudFront |
| `X-Iinfo` | Imperva |
| `X-CDN: Incapsula` | Imperva |
| `X-Sucuri-ID` | Sucuri |
| `X-Sucuri-Cache` | Sucuri |
| `X-Served-By: cache-*` | Fastly |
| `BIGipServer*` cookie | F5 BIG-IP |

---

## 3. ASN Check

```bash
IP=$(dig +short target.com | head -1)
whois "$IP" | grep -iE "origin|originas|netname|descr"
```

Common ASNs:

| ASN | Provider |
|---|---|
| AS13335 | Cloudflare |
| AS16625 | Akamai |
| AS20940 | Akamai |
| AS16509 | Amazon |
| AS54113 | Fastly |
| AS19551 | Imperva / Incapsula |

---

## 4. Automated Fingerprinting

```bash
wafw00f https://target.com -a
nmap --script http-waf-detect,http-waf-fingerprint target.com
```

---

## Custom Script: `cloud_waf_recon.py`

Save as:

```text
scripts/cloud_waf_recon.py
```

```python
#!/usr/bin/env python3
"""
Cloud WAF fingerprinter and initial recon helper.

Use only for:
- Your own assets
- Labs
- Explicitly authorized bug bounty / pentest targets
"""

import socket
import sys
from urllib.parse import urlparse

import requests
import urllib3


urllib3.disable_warnings()


WAF_SIGNATURES = {
    "Cloudflare": {
        "headers": ["cf-ray", "cf-cache-status", "server: cloudflare", "__cf_bm"],
        "ip_ranges": ["104.16.", "104.17.", "104.18.", "172.67.", "162.158.", "131.0.72."],
    },
    "Akamai": {
        "headers": ["akamaighost", "x-akamai", "x-akamai-transformed", "ak_bmsc"],
        "ip_ranges": ["2.16.", "23.32.", "23.64.", "96.6."],
    },
    "AWS CloudFront": {
        "headers": ["x-amz-cf-id", "x-amz-cf-pop", "cloudfront"],
        "ip_ranges": ["13.32.", "13.224.", "52.84.", "54.192."],
    },
    "Fastly": {
        "headers": ["x-served-by", "fastly-debug", "x-fastly"],
        "ip_ranges": ["151.101.", "199.232."],
    },
    "Imperva": {
        "headers": ["x-iinfo", "x-cdn: incapsula", "incap_ses"],
        "ip_ranges": ["149.126.", "192.230."],
    },
    "Sucuri": {
        "headers": ["x-sucuri-id", "x-sucuri-cache"],
        "ip_ranges": ["192.124."],
    },
}


def get_ip(domain: str) -> str | None:
    try:
        return socket.gethostbyname(domain)
    except socket.gaierror:
        return None


def identify_waf(url: str) -> None:
    parsed = urlparse(url)
    domain = parsed.hostname

    if not domain:
        print("[!] Invalid URL. Example: https://example.com")
        return

    ip_address = get_ip(domain)

    print(f"\n{'=' * 70}")
    print(f"Target: {url}")
    print(f"Resolved IP: {ip_address or 'N/A'}")
    print("=" * 70)

    try:
        response = requests.get(url, timeout=10, verify=False)
    except requests.RequestException as error:
        print(f"[!] Request failed: {error}")
        return

    headers_text = str(response.headers).lower()
    cookies_text = str(response.cookies).lower()
    combined_text = headers_text + cookies_text

    print("\nResponse Headers:")
    for key, value in response.headers.items():
        print(f"  {key}: {str(value)[:120]}")

    print("\nWAF Detection:")
    detected = []

    for waf_name, signatures in WAF_SIGNATURES.items():
        score = 0
        evidence = []

        for signature in signatures["headers"]:
            if signature in combined_text:
                score += 3
                evidence.append(f"header/cookie: {signature}")

        if ip_address:
            for ip_range in signatures["ip_ranges"]:
                if ip_address.startswith(ip_range):
                    score += 5
                    evidence.append(f"ip_range: {ip_range}*")

        if score > 0:
            detected.append((waf_name, score, evidence))

    detected.sort(key=lambda item: item[1], reverse=True)

    if not detected:
        print("  No obvious cloud WAF detected.")
    else:
        for waf_name, score, evidence in detected:
            print(f"  {waf_name} | confidence score: {score}")
            for item in evidence:
                print(f"    - {item}")

    print("\nOrigin Hint:")
    known_ranges = [
        ip_range
        for signatures in WAF_SIGNATURES.values()
        for ip_range in signatures["ip_ranges"]
    ]

    if ip_address and not any(ip_address.startswith(prefix) for prefix in known_ranges):
        print("  Resolved IP does not match known CDN/WAF ranges.")
        print("  This may be a direct origin or another provider. Verify carefully.")
    else:
        print("  Resolved IP appears consistent with a known CDN/WAF range.")


def main() -> None:
    if len(sys.argv) < 2:
        print("Usage: python3 cloud_waf_recon.py https://target.com")
        sys.exit(1)

    identify_waf(sys.argv[1])


if __name__ == "__main__":
    main()
```

Run:

```bash
python3 scripts/cloud_waf_recon.py https://target.com
```

---

# 🎯 Session 2: Origin IP Discovery

## Why Origin IP Discovery Matters

```text
Normal:
[Attacker] → [Cloud WAF] → [Origin]

Origin exposed:
[Attacker] ─────────────→ [Origin]
```

If the origin is directly reachable, WAF protections such as XSS rules, SQLi rules, bot protection, rate limits, and caching controls may be bypassed.

> Responsible note: If you discover origin exposure, prove minimal impact and report. Do not attack the origin.

---

## Technique 1: Historical DNS Records

Before a CDN/WAF was configured, DNS may have pointed directly to the origin.

Useful sources:

- SecurityTrails
- ViewDNS.info
- DNSdumpster
- CompleteDNS
- DNS history tools

Example workflow:

```bash
# Example with a DNS history tool or service output
# Look for old A records that differ from current CDN IPs.
```

Verification:

```bash
CANDIDATE_IP="203.0.113.10"
TARGET="target.com"

curl -k -H "Host: $TARGET" "https://$CANDIDATE_IP/"
```

If the same application loads, the IP may be the origin.

---

## Technique 2: Certificate Transparency Logs

Certificate logs can reveal subdomains and infrastructure.

```bash
curl -s "https://crt.sh/?q=%25.target.com&output=json" \
  | jq -r '.[].name_value' \
  | sort -u
```

Resolve discovered subdomains:

```bash
for sub in $(cat subdomains.txt); do
  ip=$(dig +short "$sub" | head -1)
  if [ -n "$ip" ]; then
    echo "$sub -> $ip"
  fi
done
```

Look for:

- Non-CDN IPs
- Staging domains
- Legacy services
- Direct admin or API hosts

---

## Technique 3: Subdomain Enumeration

```bash
subfinder -d target.com -all -silent -o subs.txt
httpx -l subs.txt -silent -status-code -ip -tech-detect
```

Common origin-leaking patterns:

```text
direct.target.com
origin.target.com
cpanel.target.com
webmail.target.com
ftp.target.com
mail.target.com
vpn.target.com
git.target.com
jenkins.target.com
staging.target.com
dev.target.com
api-dev.target.com
```

---

## Origin Finder Script: `find_origin.sh`

Save as:

```text
scripts/find_origin.sh
```

```bash
#!/bin/bash

TARGET="$1"

if [ -z "$TARGET" ]; then
  echo "Usage: ./find_origin.sh target.com"
  exit 1
fi

echo "[*] Finding potential origin candidates for $TARGET..."

subfinder -d "$TARGET" -silent | while read -r sub; do
  ip=$(dig +short "$sub" @8.8.8.8 2>/dev/null | grep -E '^[0-9]' | head -1)

  if [ -n "$ip" ]; then
    if [[ ! "$ip" =~ ^(104\.|172\.67\.|162\.158\.|13\.32\.|13\.224\.|151\.101\.|23\.32\.) ]]; then
      echo "[+] POTENTIAL ORIGIN: $sub -> $ip"
    fi
  fi
done
```

Run:

```bash
chmod +x scripts/find_origin.sh
./scripts/find_origin.sh target.com
```

---

## Technique 4: Shodan & Censys Search

Search by:

- Favicon hash
- TLS certificate names
- HTTP title
- Unique response strings
- Organization name
- Server banners

Favicon hash helper:

```python
#!/usr/bin/env python3

import base64
import sys

import mmh3
import requests


if len(sys.argv) < 2:
    print("Usage: python3 favicon_hash.py https://target.com/favicon.ico")
    sys.exit(1)

url = sys.argv[1]
response = requests.get(url, timeout=10)
favicon_hash = mmh3.hash(base64.encodebytes(response.content))
print(favicon_hash)
```

Search ideas:

```text
http.favicon.hash:<hash>
ssl.cert.subject.cn:target.com
http.title:"Target Corp"
http.html:"Copyright Target"
```

---

## Technique 5: Email Header Analysis

Outgoing emails can expose infrastructure.

Steps:

1. Register on the target if allowed.
2. Trigger a password reset or notification email.
3. View full email headers.
4. Inspect `Received:` lines.

Example:

```text
Received: from mail.target.com (203.0.113.25)
```

That IP may reveal related infrastructure.

---

## Technique 6: DNS Misconfiguration

Check all common DNS records:

```bash
for type in A AAAA MX TXT NS SOA CAA; do
  echo "=== $type ==="
  dig "$type" target.com +short
done
```

TXT/SPF records may leak IPs:

```text
v=spf1 ip4:203.0.113.10 include:_spf.example.com ~all
```

---

## Technique 7: Web Application Leaks

Some responses leak backend details:

```bash
curl https://target.com/nonexistent-page-12345
curl -I https://target.com/
```

Check:

```text
Redirect Location headers
Debug pages
Error pages
Server banners
X-Real-IP style headers
Health endpoints
Robots and sitemap files
```

Safe metadata checks:

```bash
for path in \
  /robots.txt \
  /sitemap.xml \
  /.well-known/security.txt \
  /server-status \
  /api/health; do
  echo "=== $path ==="
  curl -s "https://target.com$path" | head -20
done
```

---

## Technique 8: SSRF-Induced Origin Clues

If an authorized lab or program has an SSRF, it may reveal internal routing or backend behavior.

Safe lab idea:

```text
Fetch localhost or internal test service in a controlled environment.
Compare response behavior with the public endpoint.
```

> Never use SSRF to access metadata credentials, private customer data, or internal systems outside explicit authorization.

---

## Automated Origin Discovery Tools

```bash
# CloudFail
git clone https://github.com/m0rtem/CloudFail
cd CloudFail
pip install -r requirements.txt
python3 cloudfail.py -t target.com
```

```bash
# CloudFlair
git clone https://github.com/christophetd/CloudFlair
cd CloudFlair
pip install -r requirements.txt
python3 cloudflair.py target.com
```

```bash
# DNS history based tooling
git clone https://github.com/vincentcox/bypass-firewalls-by-DNS-history
```

---

## Verifying an Origin IP

```bash
CANDIDATE_IP="203.0.113.10"
TARGET="target.com"
```

### Test 1: Same Content

```bash
curl -k -H "Host: $TARGET" "https://$CANDIDATE_IP/"
curl "https://$TARGET/"
```

Compare:

- Page title
- Cookies
- Response size
- Unique strings
- Headers
- Static asset paths

---

### Test 2: Same TLS Certificate

```bash
openssl s_client -connect "$CANDIDATE_IP:443" -servername "$TARGET" < /dev/null 2>/dev/null \
  | openssl x509 -noout -subject -issuer
```

---

### Test 3: Same App Identifiers

```bash
curl -k -H "Host: $TARGET" -I "https://$CANDIDATE_IP/" \
  | grep -iE "set-cookie|x-request-id|server|cache|powered"
```

If multiple indicators match, document carefully and report.

---

# 🛡️ Session 3: Cloudflare Deep Dive

## Cloudflare Architecture

```text
[User]
  ↓
[Cloudflare Edge]
  ├── DDoS Protection
  ├── WAF Rules
  ├── Bot Management
  ├── Rate Limiting
  ├── Cache Layer
  ↓
[Origin Server]
```

---

## Cloudflare Rule Categories

- Managed rules
- Cloudflare managed ruleset
- Exposed credential checks
- Bot protection
- WAF custom rules
- Rate limiting
- Geo-blocking
- Cache rules
- Workers-based logic

---

## Cloudflare Bypass Concepts

> Use these only in labs or with explicit authorization.

### 1. Origin IP Exposure

Most reliable cloud WAF bypass class.

```text
Find origin
    ↓
Verify same app
    ↓
Report direct-origin exposure
```

---

### 2. Subdomain Takeover

```bash
subfinder -d target.com | httpx -silent -status-code
```

Look for:

- Dangling CNAME
- Deleted Heroku app
- Unclaimed S3 bucket
- Unclaimed GitHub Pages
- Unclaimed Azure / Netlify / Vercel resource

Tool:

```bash
go install github.com/haccer/subjack@latest
```

---

### 3. Exotic Payload Parsing

Lab-only examples:

```html
<svg><animate onbegin=alert(1) attributeName=x dur=1s>
<xss onauxclick=alert(1)>
<a href="java&#09;script:alert(1)">click</a>
<math><maction actiontype=statusline xlink:href=javascript:alert(1)>x</maction>
<form><button formaction=javascript:alert(1)>X</button></form>
```

---

### 4. HTTP Parameter Pollution

```text
?q=safe&q=<payload>
```

Different layers may parse duplicate parameters differently.

---

### 5. Content-Type Confusion

```http
POST /api/search HTTP/1.1
Host: target.com
Content-Type: application/xml

<payload>{"q":"test"}</payload>
```

Risk appears when WAF and backend parse body differently.

---

### 6. Workers Logic Bugs

Cloudflare Workers can introduce custom routing bypasses.

Example pattern:

```javascript
if (url.searchParams.get("debug") === "true") {
  return fetch(request);
}
```

Check for:

```text
debug=true
preview=true
bypass=true
cache=false
internal=true
```

---

### 7. Cache Poisoning

```http
GET /static/app.js HTTP/1.1
Host: target.com
X-Forwarded-Host: attacker.example
```

If backend reflects unkeyed headers and cache stores the response, impact can become persistent.

---

### 8. WebSocket Routes

WebSocket traffic may be inspected differently.

```javascript
const ws = new WebSocket("wss://target.com/ws");
ws.send(JSON.stringify({ action: "test", payload: "lab-value" }));
```

---

### 9. Legacy Paths

```text
/wp-admin/admin-ajax.php
/api/v1/../../admin
/%2e%2e/admin
/admin;jsessionid=x
```

---

# 🏢 Session 4: Akamai Bypass Concepts

## Akamai Products

- Kona Site Defender
- Bot Manager
- Prolexic
- EdgeWorkers
- CDN caching and routing

---

## Akamai Fingerprinting

```bash
curl -sI https://target.com | grep -iE "akamai|x-akamai|akamaighost|ak_bmsc|bm_sz|_abck"
```

Common indicators:

```text
Server: AkamaiGHost
X-Akamai-Transformed
X-Akamai-Edgescape
ak_bmsc
bm_sz
_abck
```

---

## Akamai Bypass Concepts

### 1. Unicode Normalization

```html
<img src＝x onerror＝alert(1)>
```

Full-width and lookalike characters may be normalized differently by layers.

---

### 2. Parser Confusion

```html
<svg/><svg onload=alert(1)>
<svg><svg onload=alert(1)></svg>
```

---

### 3. Encoding Chains

```text
Single encode:
%3Cscript%3E

Double encode:
%253Cscript%253E
```

Risk:

```text
WAF decodes once
Backend decodes twice
```

---

### 4. HTTP/2 Translation Issues

Akamai-heavy stacks often support HTTP/2.

```text
HTTP/2 front-end
    ↓
HTTP/1.1 backend
```

Translation bugs can create desync risk.

---

### 5. Bot Manager Testing

For labs and authorized targets only:

- Use a real browser
- Observe challenge cookies
- Compare browser vs CLI behavior
- Document challenge flows

Common cookies:

```text
_abck
bm_sz
ak_bmsc
```

---

### 6. Path Normalization

```text
/api/users/../admin
/api/users/%2e%2e/admin
/api/users/..%2fadmin
/api/users/..;/admin
```

---

# ⚡ Session 5: AWS WAF & CloudFront

## AWS WAF Architecture

```text
[User]
  ↓
[CloudFront + AWS WAF]
  ↓
[ALB / API Gateway + optional WAF]
  ↓
[Backend: EC2 / Lambda / ECS / EKS]
```

---

## AWS WAF Rule Groups

- Core rule set
- Known bad inputs
- SQL database rules
- Linux / Windows / PHP / WordPress rules
- IP reputation lists
- Bot Control
- Admin protection

---

## AWS WAF Bypass Concepts

### 1. Body Inspection Size Limits

Some WAF configurations inspect only part of large request bodies.

Lab concept:

```text
Large padding
    ↓
Payload placed after inspected portion
    ↓
Backend still reads full body
```

Safe lab example:

```bash
python3 - << 'PY'
padding = "A" * 8192
print(f"junk={padding}&q=test")
PY
```

---

### 2. Header Size Limits

Large headers can affect inspection behavior.

```bash
python3 - << 'PY'
print("A" * 7000)
PY
```

Use only in lab or explicitly allowed testing.

---

### 3. Content-Type Confusion

```http
POST /api/search HTTP/1.1
Host: target.com
Content-Type: application/xml

<payload>test</payload>
```

Risk appears when backend accepts/parses a body differently than WAF.

---

### 4. Deep JSON Nesting

```json
{
  "a": {
    "b": {
      "c": {
        "d": {
          "e": "test"
        }
      }
    }
  }
}
```

Goal: understand parsing depth and inspection differences.

---

### 5. Unicode Normalization

```text
′ OR 1=1--
```

This uses a Unicode prime character, not a standard apostrophe.

---

### 6. CloudFront Origin Access Misconfiguration

Check whether a backing S3 bucket or origin is accessible directly.

```bash
curl -I https://target-bucket.s3.amazonaws.com/
```

Report only exposure. Do not access private data.

---

### 7. Rule Group Gaps

Lab-only payload examples:

```html
<svg/onload=alert`1`>
<details open ontoggle=alert`1`>
<video><source onerror=alert`1`>
```

---

# 🏦 Session 6: Imperva, Sucuri, F5 & Others

## Imperva Incapsula

### Fingerprints

```text
incap_ses_*
visid_incap_*
X-Iinfo
X-CDN: Incapsula
```

### Concepts

- Challenge cookies
- Session reuse behavior
- Underscore-prefixed parameters
- Origin exposure through subdomains
- Cache/routing anomalies

---

## Sucuri

### Fingerprints

```text
X-Sucuri-ID
X-Sucuri-Cache
```

### Concepts

```text
/wp-admin/../admin-ajax.php
/wp-admin/%2e%2e/admin-ajax.php
```

Common origin hints:

```text
direct.target.com
origin.target.com
server.target.com
cpanel.target.com
```

---

## F5 BIG-IP ASM

### Fingerprints

```text
BIGipServer* cookie
TS01* cookie
Server: BigIP
```

---

## BIG-IP Cookie Decoder

Save as:

```text
scripts/bigip_decode.py
```

```python
#!/usr/bin/env python3
"""
Decode common F5 BIG-IP cookie formats.

Use for defensive analysis and authorized testing only.
"""

import sys


def decode_bigip(cookie: str) -> tuple[str | None, int | None]:
    # Classic format: numeric_ip.numeric_port
    if "." in cookie and cookie.count(".") == 1:
        try:
            ip_int_text, port_int_text = cookie.split(".")
            ip_int = int(ip_int_text)
            port_int = int(port_int_text)

            ip = ".".join(
                [
                    str((ip_int >> 0) & 0xFF),
                    str((ip_int >> 8) & 0xFF),
                    str((ip_int >> 16) & 0xFF),
                    str((ip_int >> 24) & 0xFF),
                ]
            )

            port = ((port_int >> 8) & 0xFF) | ((port_int & 0xFF) << 8)
            return ip, port
        except ValueError:
            return None, None

    # rd format: rd5o00000000000000000000ffff0a000001
    if "rd" in cookie and "ffff" in cookie:
        try:
            index = cookie.index("ffff") + 4
            ip_hex = cookie[index:index + 8]
            ip = ".".join(str(int(ip_hex[i:i + 2], 16)) for i in range(0, 8, 2))
            return ip, None
        except ValueError:
            return None, None

    return None, None


def main() -> None:
    if len(sys.argv) < 2:
        print("Usage: python3 bigip_decode.py <cookie_value>")
        print("Example: python3 bigip_decode.py rd5o00000000000000000000ffff0a000001")
        sys.exit(1)

    ip, port = decode_bigip(sys.argv[1])

    if not ip:
        print("[!] Could not decode cookie format.")
        sys.exit(1)

    print(f"[+] Decoded backend IP: {ip}")

    if port:
        print(f"[+] Decoded port: {port}")


if __name__ == "__main__":
    main()
```

Run:

```bash
python3 scripts/bigip_decode.py "rd5o00000000000000000000ffff0a000001"
```

---

## Fastly

### Fingerprints

```text
X-Served-By: cache-*.fastly.net
X-Cache: HIT
X-Cache: MISS
```

### Concepts

- Aggressive caching
- Unkeyed header influence
- Signal Sciences / Fastly Next-Gen WAF behavior
- Cache poisoning risk

Example test pattern:

```http
GET / HTTP/1.1
Host: target.com
X-Forwarded-Host: attacker.example
Fastly-SSL: 1
```

---

# 📖 Session 7: Real $10K+ Bug Bounty Chains

> These are chain patterns for learning. In real programs, prove minimal impact and avoid accessing sensitive data.

---

## Chain 1: Subdomain Takeover → Cloud WAF Bypass

```text
Dangling subdomain
    ↓
Claim third-party resource
    ↓
Control trusted subdomain
    ↓
Impact: phishing, cookie scope risk, brand abuse
```

---

## Chain 2: Historical DNS → Origin Exposure

```text
Cloud WAF-protected target
    ↓
Historical DNS reveals old IP
    ↓
Origin still serves production app
    ↓
Direct-origin exposure report
```

---

## Chain 3: BIG-IP Cookie Decode → Backend Discovery

```text
F5 BIG-IP cookie
    ↓
Decode backend IP
    ↓
Verify exposure safely
    ↓
Report internal routing information leak
```

---

## Chain 4: AWS WAF Body Limit → Backend Parsing Gap

```text
Large request body
    ↓
WAF inspects limited portion
    ↓
Backend reads full body
    ↓
Possible validation gap
```

---

## Chain 5: Cloudflare Workers Debug Logic

```text
Worker route
    ↓
Debug/preview parameter
    ↓
Different cache/security behavior
    ↓
Auth or routing bypass risk
```

---

## Chain 6: Akamai Unicode + Cache Poisoning

```text
Unicode parsing difference
    ↓
Payload reflected
    ↓
Response cached
    ↓
Persistent user impact
```

---

## Chain 7: Dev Subdomain → Shared Origin

```text
Forgotten dev host
    ↓
Not behind WAF
    ↓
Same backend or database as production
    ↓
High-impact exposure
```

---

## Chain 8: HTTP/2 Downgrade on CDN Stack

```text
HTTP/2 edge
    ↓
HTTP/1.1 backend
    ↓
Translation mismatch
    ↓
Desync or routing bypass
```

---

## Chain 9: Email Header Leak → Infrastructure Discovery

```text
Password reset email
    ↓
Received headers reveal IP/subnet
    ↓
Related origin found
    ↓
Report exposure safely
```

---

## Chain 10: Imperva Challenge Cookie Reuse

```text
Challenge solved once
    ↓
Cookie behavior analyzed
    ↓
Session or rate-limit logic weakness
    ↓
Report bypass condition responsibly
```

---

## Add Chains to Your Vault

```bash
mkdir -p payload-vault/hunter-chains/cloud-waf-bypass

for i in $(seq 1 10); do
  touch "payload-vault/hunter-chains/cloud-waf-bypass/chain-$i.md"
done
```

Template:

```markdown
# Chain Title

## Source / Inspiration

-

## Components

-

## Root Cause

-

## Impact

-

## Safe Proof

-

## Remediation

-
```

---

# 🎯 Session 8: Live Hunting Methodology

## Elite Hunter Workflow

```text
┌─────────────────────────────────────────────┐
│ PHASE 1: RECON                              │
│ - Identify WAF/CDN                          │
│ - Enumerate subdomains                      │
│ - Historical DNS                            │
│ - Certificate transparency                  │
│ - Shodan/Censys search                      │
├─────────────────────────────────────────────┤
│ PHASE 2: ORIGIN HUNT                        │
│ - Try all 8 techniques                      │
│ - Verify candidates                         │
│ - Document evidence                         │
├─────────────────────────────────────────────┤
│ PHASE 3: WAF PROBING                        │
│ - Fingerprint behavior                      │
│ - Test safe payloads in scope               │
│ - Identify parser gaps                      │
├─────────────────────────────────────────────┤
│ PHASE 4: EXPLOITATION                       │
│ - Prove minimal impact                      │
│ - Avoid sensitive data access               │
│ - Preserve evidence                         │
├─────────────────────────────────────────────┤
│ PHASE 5: REPORT                             │
│ - Clear steps                               │
│ - Strong impact                             │
│ - Safe remediation                          │
└─────────────────────────────────────────────┘
```

---

## Target Selection

Good practice sources:

- PortSwigger labs
- YesWeHack Dojo
- Intigriti challenges
- HackerOne public programs
- Bugcrowd public programs

---

## Example Daily Hunting Schedule

```text
06:00 — Morning micro-habits
06:35 — Pick legal target and read scope
07:00 — Recon
08:00 — Origin discovery attempts
09:00 — WAF behavior notes
10:00 — Controlled testing
11:00 — Write notes
14:00 — Report draft or pivot
17:00 — Evening journal
```

---

## Report Template: Origin Exposure

```markdown
# WAF Bypass via Exposed Origin IP

## Summary

The origin server for `www.target.com` appears to be directly accessible, allowing requests to reach the backend without passing through the configured cloud WAF/CDN layer.

## Affected Asset

- Domain: `www.target.com`
- Candidate origin IP: `X.X.X.X`
- WAF/CDN: Cloudflare / Akamai / AWS CloudFront / Other

## Steps to Reproduce

1. Identify current CDN-protected IP using DNS.
2. Discover historical or related origin candidate using authorized recon.
3. Verify the candidate safely:

   ```bash
   curl -k -H "Host: www.target.com" https://X.X.X.X/
   ```

4. Compare the direct-origin response with the CDN response.
5. Confirm matching application identifiers such as title, cookies, or unique headers.

## Impact

Direct origin access may bypass:

- WAF inspection
- Bot protection
- Rate limiting
- CDN cache controls
- IP reputation rules

This may expose the application to attacks that the WAF/CDN was intended to block.

## Remediation

- Restrict origin firewall to accept traffic only from CDN/WAF IP ranges.
- Enable authenticated origin pulls where supported.
- Rotate exposed origin IP if needed.
- Remove stale DNS records.
- Monitor certificate transparency and DNS history exposure.
- Avoid exposing staging/dev/admin hosts publicly.

## References

- Cloudflare origin protection documentation
- AWS CloudFront origin access control documentation
- OWASP guidance on secure deployment
```

---

# 🔁 Micro-Habits Continuation

From Day 9, continue the habit system.

## Today’s Additions

### Morning

- Read 5 minutes of WAF bypass or CDN security research.

### Afternoon

- Pick one legal program and spend 15 minutes on origin discovery methodology.

### Evening

- Read one cloud WAF or CDN misconfiguration writeup.

---

## Weekly Review Template

```markdown
# Week Review

## Habit Completion

| Habit | Completed |
|---|---:|
| Daily writeup | __ / 7 |
| X gem collection | __ / 7 |
| Payload variation | __ / 7 |
| PortSwigger lab | __ / 7 |
| Journal | __ / 7 |

## Progress

- New bypass concepts learned:
- Payloads added to vault:
- Reports filed:
- Biggest lesson:

## Next Week Goals

-
-
-
```

---

# 🏆 Day 10 Challenge

Mark Day 10 complete after:

- [ ] Document all 10 cloud WAF chain patterns in the vault
- [ ] Identify WAF/CDN for 5 authorized or lab targets
- [ ] Test `cloud_waf_recon.py` on 5 targets
- [ ] Run `find_origin.sh` only against legal targets
- [ ] Install CloudFail or CloudFlair
- [ ] Understand 10+ Cloudflare bypass concepts
- [ ] Document 5+ Akamai bypass concepts
- [ ] Replicate AWS WAF body-size limit behavior in a lab
- [ ] Decode a sample BIG-IP cookie
- [ ] Write full methodology notes
- [ ] Log daily micro-habits for 2+ days
- [ ] Select one legal bug bounty program for Week 3 hunting
- [ ] Push `Day-10.md`, scripts, and vault notes to GitHub

---

# 📋 Master Cheat Sheets

## Cheat Sheet 1: WAF Fingerprinting

```bash
curl -sI https://target.com | grep -iE "cf-ray|akamai|x-amz|incap|sucuri|fastly|bigip"

dig CNAME target.com
dig A target.com

IP=$(dig +short target.com | head -1)
whois "$IP" | grep -iE "origin|netname|descr"

wafw00f -a https://target.com
python3 scripts/cloud_waf_recon.py https://target.com
```

---

## Cheat Sheet 2: Origin IP Discovery

```bash
# Certificate transparency
curl -s "https://crt.sh/?q=%25.target.com&output=json" \
  | jq -r '.[].name_value' \
  | sort -u

# Subdomain enumeration
subfinder -d target.com -all -silent | httpx -ip -silent

# Verify candidate origin
curl -k -H "Host: target.com" https://CANDIDATE_IP/
```

---

## Cheat Sheet 3: Cloud WAF Headers

| Header / Cookie | WAF |
|---|---|
| `cf-ray` | Cloudflare |
| `Server: cloudflare` | Cloudflare |
| `AkamaiGHost` | Akamai |
| `X-Akamai-*` | Akamai |
| `X-Amz-Cf-Id` | AWS CloudFront |
| `Via: CloudFront` | AWS CloudFront |
| `X-Served-By` | Fastly |
| `X-Iinfo` | Imperva |
| `X-Sucuri-ID` | Sucuri |
| `BIGipServer*` | F5 BIG-IP |

---

## Cheat Sheet 4: Cloudflare Concepts

```text
Origin IP exposure
Subdomain takeover
Exotic parser behavior
HTTP parameter pollution
Content-Type confusion
Workers logic bugs
Cache poisoning
WebSocket route testing
Legacy path normalization
```

---

## Cheat Sheet 5: AWS WAF Concepts

```text
Body inspection size limits
Header size limits
Content-Type parsing differences
JSON nesting behavior
Unicode normalization
Origin access misconfiguration
Managed rule group gaps
CloudFront origin exposure
```

---

# 📚 Resources

## Essential Repositories

- [CloudFail](https://github.com/m0rtem/CloudFail)
- [CloudFlair](https://github.com/christophetd/CloudFlair)
- [bypass-firewalls-by-DNS-history](https://github.com/vincentcox/bypass-firewalls-by-DNS-history)
- [Awesome-WAF](https://github.com/0xInfection/Awesome-WAF)

## Origin Discovery Services

- [SecurityTrails](https://securitytrails.com)
- [DNSdumpster](https://dnsdumpster.com)
- [Shodan](https://www.shodan.io)
- [Censys](https://search.censys.io)
- [crt.sh](https://crt.sh)

## Research Blogs

- [Assetnote](https://blog.assetnote.io)
- [PortSwigger Research](https://portswigger.net/research)
- [Detectify Labs](https://labs.detectify.com)
- [Cloudflare Security](https://blog.cloudflare.com/tag/security/)
- [AWS Security Blog](https://aws.amazon.com/blogs/security/)

## Researchers to Follow

- [@infosec_au](https://x.com/infosec_au)
- [@albinowax](https://x.com/albinowax)
- [@tomnomnom](https://x.com/tomnomnom)
- [@regilero_info](https://x.com/regilero_info)
- [@samwcyo](https://x.com/samwcyo)

## Practice Platforms

- HackerOne public programs
- Bugcrowd public programs
- YesWeHack Dojo
- Intigriti challenges
- PortSwigger Academy

---

# ❓ Self-Check Questions

1. Cloud WAF bypass er 2 main path ki?
2. Origin IP discovery er 8 ta technique bolo.
3. Historical DNS kivabe origin reveal korte pare?
4. Certificate Transparency logs keno useful?
5. Cloudflare bypass concepts er top 5 ki?
6. Akamai unicode normalization issue kivabe kaj korte pare?
7. AWS WAF body inspection limit concept ki?
8. F5 BIG-IP cookie theke backend info kivabe leak hote pare?
9. Subdomain takeover → WAF bypass chain explain koro.
10. Origin IP verification er 3 ta safe method ki?
11. HTTP/2 downgrade cloud context e keno risky?
12. Cache poisoning + cloud WAF combo impact ki?
13. Imperva challenge cookie behavior keno important?
14. Elite hunter methodology er 5 phase ki?
15. Origin exposure report e remediation ki hobe?

✅ All 15 answered confidently? **Day 10 & Week 2 complete!** 🎉

---

# 🎉 Week 2 Complete

You have now covered:

- ✅ Encoding & obfuscation
- ✅ SQLi + NoSQLi
- ✅ SSRF + RCE + LFI + XXE + cloud metadata security
- ✅ Request smuggling + cache poisoning
- ✅ Cloud WAF bypass + origin IP discovery

```text
Week 2 = Core Mastery Complete
```

---

# 🚀 What’s Next?

## Day 11 Preview — Real Hunter Writeups Deep-Dive

- Analyze 20+ top hunter writeups
- Extract methodology
- Adapt payloads into your toolkit
- Learn from high-impact public reports

## Day 12–15 Preview

| Day | Focus |
|---|---|
| Day 12 | Advanced polyglots + custom tooling |
| Day 13 | Live bug bounty recon → exploitation workflow |
| Day 14 | End-to-end practice + report writing |
| Day 15 | Portfolio publication + next 30 days roadmap |

---

# 📝 My Day 10 Notes

## WAFs Identified

| Target | WAF | Fingerprint | Origin Found? |
|---|---|---|---|
|  |  |  |  |
|  |  |  |  |

---

## Origin Discovery Success

```text
Target 1:
Origin IP:
Method:
Verification evidence:

Target 2:
Origin IP:
Method:
Verification evidence:
```

---

## Cloudflare Concepts Tested

1. 
2. 
3. 

---

## Akamai Concepts Documented

1. 
2. 
3. 

---

## Best Writeup of the Day

```text
Source:
Technique:
Impact:
Key takeaway:
```

---

## Scripts Running

- [ ] `cloud_waf_recon.py`
- [ ] `find_origin.sh`
- [ ] `bigip_decode.py`
- [ ] `smuggle_detect.py`
- [ ] `encoder.py`

---

## Micro-Habits Today

- [ ] Morning writeup
- [ ] X feed scan
- [ ] Payload variation
- [ ] HTTP header inspection
- [ ] Parameter miner
- [ ] PortSwigger lab
- [ ] Terminal journal

---

## Week 2 Final Reflection

```text
Biggest learning:
Favorite technique:
Most-used tool:
Next week goal:
```

---

<p align="center">
  <strong>🎓 Day 10 Status:</strong> ⬜ In Progress / ✅ Complete<br>
  <strong>🏆 Week 2 Status:</strong> ⬜ In Progress / ✅ Complete<br>
  <em>“The best hunters do not just bypass WAFs. They find where WAFs were never enforced.”</em>
</p>

<p align="center">
  <a href="./Day-09.md">← Previous: Day 09</a> |
  <a href="../Week-03/Day-11.md">Next: Day 11 →</a>
</p>

---

# 🚀 Commit Workflow

```bash
cd ~/WAF-Bypass-30-Days/

# Save Day 10
nano Week-02/Day-10.md

# Save scripts
nano scripts/cloud_waf_recon.py
nano scripts/find_origin.sh
nano scripts/bigip_decode.py

# Make scripts executable
chmod +x scripts/find_origin.sh
chmod +x scripts/bigip_decode.py

# Commit everything
git add Week-02/Day-10.md scripts/
git commit -m "☁️ Day 10: Cloud WAF bypass and origin discovery notes"
git push origin main
```

---

# 🎯 Key Actions for Today

- [ ] Complete cloud WAF recon on 5 authorized or lab targets
- [ ] Practice origin verification safely
- [ ] Test Cloudflare concepts in your lab
- [ ] Decode a BIG-IP cookie sample
- [ ] Replicate AWS WAF body-size behavior in local testing
- [ ] Read 3 cloud WAF research posts
- [ ] Set up recon pipeline for ongoing learning
- [ ] Document 10 chain patterns in payload vault

---

# 📊 Progress Update

![Progress](https://img.shields.io/badge/Progress-Day%2010%2F15-brightgreen)
![Week](https://img.shields.io/badge/Week%202-COMPLETE-success)

## Week 1: Foundation ✅

- [x] Day 01 — HTTP + Burp Setup
- [x] Day 02 — WAF Architecture
- [x] Day 03 — WAF Detection
- [x] Day 04 — OWASP Top 10 + Hunters
- [x] Day 05 — Expert Lab Setup

## Week 2: Core Mastery ✅

- [x] Day 06 — XSS WAF Bypass Mastery 🎭
- [x] Day 07 — SQLi + NoSQLi Deep 💣
- [x] Day 08 — SSRF, RCE, LFI, XXE 🔥
- [x] Day 09 — Request Smuggling 🚨
- [x] Day 10 — Cloud WAF Bypass ☁️

## Week 3: Real-World Application 🔜

- [ ] Day 11 — Real Hunter Writeups Deep-Dive
- [ ] Day 12 — Advanced Polyglots + Custom Tooling
- [ ] Day 13 — Live Bug Bounty Workflow
- [ ] Day 14 — End-to-End Practice + Reports
- [ ] Day 15 — Portfolio + Next 30 Days
