# 🧪 Day 05 — Expert-Grade Lab Environment

> **Part of:** 30-Day WAF Bypass & Payload Crafting Journey  
> **Date:** _Add your date_  
> **Difficulty:** ⭐⭐⭐⭐☆ Advanced  
> **Time Required:** 5–6 hours  

![Day](https://img.shields.io/badge/Day-05%2F30-blue)
![Status](https://img.shields.io/badge/Status-In%20Progress-yellow)
![Focus](https://img.shields.io/badge/Focus-Expert%20Lab%20Setup-red)
![Difficulty](https://img.shields.io/badge/Difficulty-Advanced-red)

> ⚠️ **Ethical Use Only:**  
> Ei lab setup shudhu personal learning, local testing, CTF, PortSwigger labs, Juice Shop, WebGoat, Vulhub, or authorized bug bounty / pentest scope er jonno. Unauthorized target e kono testing korba na.

---

## 📑 Table of Contents

- [❌ Why We Are Skipping Beginner Labs](#-why-we-are-skipping-beginner-labs)
- [🎯 Objectives](#-objectives)
- [⏰ Time Breakdown](#-time-breakdown)
- [🏗️ Expert Lab Stack Architecture](#️-expert-lab-stack-architecture)
- [🎓 Session 1: PortSwigger Academy + Burp Workflow](#-session-1-portswigger-academy--burp-workflow)
- [🐳 Session 2: Vulhub — Real CVE Reproductions](#-session-2-vulhub--real-cve-reproductions)
- [🧃 Session 3: Juice Shop + WebGoat Advanced](#-session-3-juice-shop--webgoat-advanced)
- [🛡️ Session 4: Multi-Paranoia WAF Lab](#️-session-4-multi-paranoia-waf-lab)
- [🎯 Session 5: Bug Bounty Scope Preparation](#-session-5-bug-bounty-scope-preparation)
- [🏆 Day 5 Challenge](#-day-5-challenge)
- [🆘 Troubleshooting](#-troubleshooting)
- [📋 Cheat Sheet](#-cheat-sheet)
- [📚 Resources](#-resources)
- [❓ Self-Check Questions](#-self-check-questions)
- [🚀 What’s Next](#-whats-next)
- [📝 My Day 5 Notes](#-my-day-5-notes)

---

# ❌ Why We Are Skipping Beginner Labs

> Realistic practice matters. Beginner labs are useful for fundamentals, but this journey needs environments that feel closer to production apps.

| Beginner Lab | Why Skip | Expert Alternative |
|---|---|---|
| DVWA | Old PHP-style examples, limited realism | PortSwigger Academy |
| bWAPP | Outdated, unrealistic payload behavior | Vulhub real CVE labs |
| Mutillidae | Old attack surface | Juice Shop + WebGoat Advanced |

---

## Expert Stack

- ✅ Real CVE reproductions with Vulhub
- ✅ Modern SPA + REST API with Juice Shop
- ✅ Advanced OWASP lessons with WebGoat
- ✅ Curated hands-on labs with PortSwigger Academy
- ✅ Multi-paranoia WAF lab with ModSecurity CRS
- ✅ Custom Python WAF for controlled rule testing
- ✅ Legal bug bounty scope preparation

---

# 🎯 Objectives

End of this day, I will be able to:

- [ ] Use **PortSwigger Web Security Academy**
- [ ] Deploy **Vulhub** real CVE-based vulnerable environments
- [ ] Set up **ModSecurity CRS PL1, PL2, PL3, PL4** simultaneously
- [ ] Write a **custom Python WAF** for controlled testing
- [ ] Configure **Burp Suite workflow** with extensions and match/replace rules
- [ ] Prepare **legal bug bounty scope** for future practice
- [ ] Build a professional local lab for the next phase

---

# ⏰ Time Breakdown

| Session | Topic | Duration |
|---|---|---:|
| 1 | PortSwigger Academy + Burp Workflow | 60 min |
| 2 | Vulhub — Real CVE Reproductions | 60 min |
| 3 | Juice Shop + WebGoat Advanced | 45 min |
| 4 | Multi-Paranoia WAF Lab | 90 min |
| 5 | Bug Bounty Scope Preparation | 60 min |
| **Total** |  | **~5.5 hours** |

---

# 🏗️ Expert Lab Stack Architecture

```text
┌─────────────────────────────────────────────────────────┐
│                  EXPERT HUNTING LAB                     │
└─────────────────────────────────────────────────────────┘

[Browser]
    │
    ▼
[Burp Suite + Extensions]
    │
    ├──► PortSwigger Academy
    │       ├── Cloud-hosted labs
    │       ├── XSS
    │       ├── SQLi
    │       ├── SSRF
    │       ├── HTTP Request Smuggling
    │       └── Web Cache Poisoning
    │
    ├──► Local Lab Stack
    │       ├── Juice Shop
    │       ├── WebGoat
    │       ├── Vulhub CVEs
    │       ├── Custom Python WAF
    │       └── ModSecurity WAF Matrix
    │              ├── PL1 → Port 9001
    │              ├── PL2 → Port 9002
    │              ├── PL3 → Port 9003
    │              └── PL4 → Port 9004
    │
    └──► Legal Bug Bounty Scope
            ├── HackerOne
            ├── Bugcrowd
            ├── YesWeHack
            └── Intigriti
```

---

# 🎓 Session 1: PortSwigger Academy + Burp Workflow

## Why PortSwigger Web Security Academy?

PortSwigger Web Security Academy is one of the best free resources for practical web security learning. It includes real hands-on labs across OWASP categories and advanced web attacks.

### Setup

1. Visit: [portswigger.net/web-security](https://portswigger.net/web-security)
2. Create a free account
3. Open any lab
4. Proxy the lab through Burp Suite
5. Solve and document learnings

---

## Recommended Learning Path

### Priority 1 — WAF Bypass Focus

```text
Cross-site scripting
SQL injection
HTTP Host header attacks
HTTP request smuggling
Server-side request forgery
Web cache poisoning
```

### Priority 2

```text
OS command injection
XXE injection
Authentication vulnerabilities
CORS
JWT attacks
Access control vulnerabilities
```

---

## Burp Suite Extensions

Install from **BApp Store**:

| Extension | Purpose |
|---|---|
| Hackvertor | Real-time encoding and obfuscation |
| Turbo Intruder | Fast payload fuzzing |
| Param Miner | Hidden parameter discovery |
| Active Scan++ | Extended scanning checks |
| HTTP Request Smuggler | Request smuggling testing |
| Backslash Powered Scanner | Advanced parser fuzzing |
| Logger++ | Better request logging |
| Autorize | Access control testing |
| Collaborator Everywhere | OOB interaction testing |
| WAF Cookie Fetcher | WAF-related cookie inspection |

---

## Match & Replace Rules

Burp path:

```text
Burp Suite → Proxy → Options → Match and Replace
```

Add these rules for lab testing:

| Type | Match | Replace | Purpose |
|---|---|---|---|
| Request header | `User-Agent: .*` | `User-Agent: Mozilla/5.0 Hunter` | Custom user agent |
| Request header | Add | `X-Forwarded-For: 127.0.0.1` | Header behavior testing |
| Request header | Add | `X-Real-IP: 127.0.0.1` | Header behavior testing |
| Request header | Add | `X-Originating-IP: 127.0.0.1` | Header behavior testing |

> Use these only in labs or authorized scopes.

---

## Multi-Tab Burp Workflow

```text
Tab 1: Target       → Site map + scope
Tab 2: Proxy        → Intercept + HTTP history
Tab 3: Repeater     → Manual payload crafting
Tab 4: Intruder     → Automated fuzzing
Tab 5: Collaborator → OOB testing
Tab 6: Sequencer    → Token analysis
Tab 7: Decoder      → Encoding / decoding
```

---

# 🐳 Session 2: Vulhub — Real CVE Reproductions

## What is Vulhub?

Vulhub is a collection of pre-built vulnerable Docker environments for real CVEs. It helps you safely reproduce and study real-world vulnerabilities locally.

---

## Setup

```bash
cd ~/waf-lab
git clone https://github.com/vulhub/vulhub.git
cd vulhub
ls
```

Common categories:

```text
apache
nginx
struts2
spring
tomcat
wordpress
log4j
php
confluence
```

---

## Recommended CVE Labs

> Run only locally. Read each Vulhub `README.md` before testing.

### 1. Log4Shell — CVE-2021-44228

```bash
cd ~/waf-lab/vulhub/log4j/CVE-2021-44228
docker compose up -d
```

Target example:

```text
http://localhost:8983
```

---

### 2. Spring4Shell — CVE-2022-22965

```bash
cd ~/waf-lab/vulhub/spring/CVE-2022-22965
docker compose up -d
```

---

### 3. Apache Struts2 S2-045

```bash
cd ~/waf-lab/vulhub/struts2/s2-045
docker compose up -d
```

---

### 4. Confluence Lab

```bash
cd ~/waf-lab/vulhub/confluence/CVE-2022-26134
docker compose up -d
```

---

### 5. PHP Deserialization Lab

```bash
cd ~/waf-lab/vulhub/php/unserialize-bypass
docker compose up -d
```

---

## Vulhub Workflow

```bash
# Start a lab
cd ~/waf-lab/vulhub/<category>/<cve>
docker compose up -d

# Read instructions
cat README.md

# Stop when done
docker compose down
```

> 💡 Every Vulhub lab has its own README. Read it carefully and document what you learn.

---

# 🧃 Session 3: Juice Shop + WebGoat Advanced

## OWASP Juice Shop

Juice Shop is a modern vulnerable web application with SPA architecture and REST APIs.

### Run Juice Shop

```bash
docker run -d -p 8083:3000 --name juiceshop bkimminich/juice-shop
```

Open:

```text
http://localhost:8083
```

### Why It Is Useful

- Angular SPA architecture
- REST API attack surface
- JWT authentication flows
- GraphQL endpoint
- 100+ challenges
- NoSQL injection, SSRF, prototype pollution, XSS, access control

### Focus Challenges

```text
6-star challenges
JWT manipulation
XXE via document upload
SSRF via image URL
NoSQL injection in login
Prototype pollution
API authorization issues
```

---

## WebGoat Advanced

Run WebGoat:

```bash
docker run -d -p 8084:8080 -p 8085:9090 --name webgoat webgoat/goatandwolf
```

Open:

```text
http://localhost:8084/WebGoat
```

### Focus Modules

```text
HTTP Request Smuggling
JWT Tokens
Path Traversal
XXE
SSRF
WebWolf OOB testing
Authentication flaws
Access control
```

---

# 🛡️ Session 4: Multi-Paranoia WAF Lab

This is your main WAF dojo.

You will run the same backend behind 4 ModSecurity CRS instances:

| Port | WAF Level | Use Case |
|---:|---|---|
| `9001` | PL1 | Easy / baseline |
| `9002` | PL2 | Realistic |
| `9003` | PL3 | Strict |
| `9004` | PL4 | Paranoid |
| `8084` | WebGoat | Advanced lessons |
| `8085` | WebWolf | OOB helper |

---

## Create Expert Lab Compose File

```bash
mkdir -p ~/waf-lab/expert-stack
cd ~/waf-lab/expert-stack
nano docker-compose.yml
```

Paste:

```yaml
version: "3.8"

services:
  backend:
    image: bkimminich/juice-shop
    container_name: backend-app
    networks:
      - waflab

  waf-pl1:
    image: owasp/modsecurity-crs:nginx
    container_name: waf-pl1
    ports:
      - "9001:80"
    environment:
      - PARANOIA=1
      - ANOMALY_INBOUND=5
      - BACKEND=http://backend:3000
    depends_on:
      - backend
    networks:
      - waflab

  waf-pl2:
    image: owasp/modsecurity-crs:nginx
    container_name: waf-pl2
    ports:
      - "9002:80"
    environment:
      - PARANOIA=2
      - ANOMALY_INBOUND=5
      - BACKEND=http://backend:3000
    depends_on:
      - backend
    networks:
      - waflab

  waf-pl3:
    image: owasp/modsecurity-crs:nginx
    container_name: waf-pl3
    ports:
      - "9003:80"
    environment:
      - PARANOIA=3
      - ANOMALY_INBOUND=5
      - BACKEND=http://backend:3000
    depends_on:
      - backend
    networks:
      - waflab

  waf-pl4:
    image: owasp/modsecurity-crs:nginx
    container_name: waf-pl4
    ports:
      - "9004:80"
    environment:
      - PARANOIA=4
      - ANOMALY_INBOUND=5
      - BACKEND=http://backend:3000
    depends_on:
      - backend
    networks:
      - waflab

  webgoat:
    image: webgoat/goatandwolf
    container_name: webgoat
    ports:
      - "8084:8080"
      - "8085:9090"
    networks:
      - waflab

networks:
  waflab:
    driver: bridge
```

---

## Launch Your Dojo

```bash
docker compose up -d
docker compose ps
```

---

## Test the WAF Matrix

```bash
for port in 9001 9002 9003 9004; do
  echo "=== PL$((port - 9000)) ==="
  curl -s -o /dev/null -w "Status: %{http_code}\n" \
    "http://localhost:$port/?q=<script>alert(1)</script>"
done
```

Expected:

```text
PL1: likely blocked
PL2: likely blocked
PL3: likely blocked
PL4: likely blocked
```

---

## Custom Python Test WAF

Sometimes you need a simple WAF where you know every rule.

Create folder:

```bash
mkdir -p ~/waf-lab/expert-stack/custom-waf
cd ~/waf-lab/expert-stack/custom-waf
nano waf.py
```

Paste:

```python
#!/usr/bin/env python3
"""
Minimal test WAF for local lab learning.
Use only in your Docker lab.
"""

import re

import requests
from flask import Flask, Response, request

app = Flask(__name__)

BACKEND = "http://backend:3000"

RULES = [
    (r"<script", 941100, 5),
    (r"javascript:", 941110, 4),
    (r"onerror\s*=", 941120, 4),
    (r"onload\s*=", 941130, 4),
    (r"'\s*or\s*'?\s*1\s*=\s*1", 942100, 5),
    (r"union\s+select", 942180, 5),
    (r"\.\./\.\.", 930100, 5),
    (r";\s*(cat|ls|whoami|id)\b", 932100, 5),
]

THRESHOLD = 5


@app.route("/", defaults={"path": ""}, methods=["GET", "POST", "PUT", "DELETE"])
@app.route("/<path:path>", methods=["GET", "POST", "PUT", "DELETE"])
def proxy(path):
    full_request = request.url + str(request.data) + str(request.headers)

    score = 0
    triggered = []

    for pattern, rule_id, weight in RULES:
        if re.search(pattern, full_request, re.IGNORECASE):
            score += weight
            triggered.append(f"Rule {rule_id}")

    if score >= THRESHOLD:
        return Response(
            f"403 Forbidden\nBlocked by Custom WAF\nRules: {triggered}\nScore: {score}\n",
            status=403,
        )

    response = requests.request(
        method=request.method,
        url=f"{BACKEND}/{path}",
        headers={key: value for key, value in request.headers if key.lower() != "host"},
        data=request.get_data(),
        params=request.args,
        allow_redirects=False,
        timeout=10,
    )

    return Response(
        response.content,
        status=response.status_code,
        headers=dict(response.headers),
    )


if __name__ == "__main__":
    app.run(host="0.0.0.0", port=80)
```

Create Dockerfile:

```bash
nano Dockerfile
```

Paste:

```dockerfile
FROM python:3.11-slim

RUN pip install flask requests

COPY waf.py /app/waf.py
WORKDIR /app

CMD ["python", "waf.py"]
```

Add this service to your `docker-compose.yml`:

```yaml
  custom-waf:
    build: ./custom-waf
    container_name: custom-waf
    ports:
      - "9005:80"
    depends_on:
      - backend
    networks:
      - waflab
```

Rebuild:

```bash
docker compose up -d --build
```

Test:

```bash
curl -i "http://localhost:9005/?q=<script>alert(1)</script>"
```

---

# 🎯 Session 5: Bug Bounty Scope Preparation

Labs teach mechanics. Real programs teach reality. Today, prepare your legal hunting ground.

---

## Register on Major Platforms

| Platform | URL | Focus |
|---|---|---|
| HackerOne | [hackerone.com](https://hackerone.com) | Large public programs |
| YesWeHack | [yeswehack.com](https://yeswehack.com) | European programs |
| Bugcrowd | [bugcrowd.com](https://bugcrowd.com) | Diverse programs |
| Intigriti | [intigriti.com](https://intigriti.com) | European quality programs |

---

## Build Your Target List

Create:

```text
bug-bounty-targets.md
```

Template:

```markdown
# My Legal Hunting Ground

## Tier 1 — Public Programs

| Program | Scope | WAF/CDN | Notes |
|---|---|---|---|
| Example Program | `*.example.com` | Cloudflare | Read scope first |
|  |  |  |  |
|  |  |  |  |

---

## YesWeHack Public Programs

| Program | Scope | WAF/CDN | Notes |
|---|---|---|---|
|  |  |  |  |

---

## Bugcrowd Public Programs

| Program | Scope | WAF/CDN | Notes |
|---|---|---|---|
|  |  |  |  |

---

## VDP Programs

| Program | Scope | Notes |
|---|---|---|
|  |  |  |

---

## Rules

- Always verify scope before testing
- Always follow program policy
- Never test out-of-scope assets
- Never perform destructive testing
- Report responsibly
```

---

## Daily Writeup Reading Habit

Read 15 minutes per day:

1. [HackerOne Hacktivity](https://hackerone.com/hacktivity)
2. [YesWeHack Dojo](https://dojo-yeswehack.com/)
3. [InfoSec Write-ups](https://infosecwriteups.com)
4. [Pentester Land](https://pentester.land)
5. [PortSwigger Research](https://portswigger.net/research)

---

## Recon Tool Setup

Install these for later days:

```bash
# ProjectDiscovery tools
go install github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
go install github.com/projectdiscovery/httpx/cmd/httpx@latest
go install github.com/projectdiscovery/nuclei/v3/cmd/nuclei@latest

# Tomnomnom tools
go install github.com/tomnomnom/waybackurls@latest
go install github.com/tomnomnom/gf@latest
go install github.com/tomnomnom/assetfinder@latest

# Python tools
pip install arjun paramspider
```

Verify:

```bash
subfinder -version
httpx -version
nuclei -version
```

---

# 🏆 Day 5 Challenge

Complete all to mark Day 5 done:

- [ ] PortSwigger Academy account created
- [ ] 1 PortSwigger lab solved
- [ ] Vulhub cloned
- [ ] One Vulhub lab launched locally
- [ ] Juice Shop running
- [ ] First Juice Shop challenge solved
- [ ] WebGoat running
- [ ] One advanced WebGoat lesson completed
- [ ] Multi-paranoia WAF stack running
- [ ] Same payload tested across PL1–PL4
- [ ] Custom Python WAF running at port `9005` optional
- [ ] HackerOne account created
- [ ] YesWeHack account created
- [ ] Bugcrowd account created
- [ ] Intigriti account created
- [ ] Legal target list created with 10+ programs
- [ ] Burp Suite 10+ extensions installed
- [ ] Burp Match & Replace rules configured
- [ ] Recon tools installed
- [ ] Read 3 WAF bypass or bug bounty writeups
- [ ] Commit and push everything to GitHub

---

# 🆘 Troubleshooting

## Vulhub Container Does Not Start

```bash
docker compose down
docker compose up -d
```

For old Docker Compose:

```bash
docker-compose up -d
```

---

## Multi-WAF Stack Eating RAM

Stop unused levels:

```bash
docker stop waf-pl1 waf-pl3
```

Keep realistic + challenge levels:

```text
PL2 → realistic
PL4 → strict challenge
```

---

## PortSwigger Lab Does Not Load in Burp

Check:

```text
Burp → Proxy → Options → Response modification
```

Disable anything that modifies lab responses unexpectedly.

---

## Burp Extensions Not Loading

If an extension needs Jython:

```text
Burp → Extender → Options → Python Environment
```

Download Jython standalone JAR and configure it in Burp.

---

## Custom Python WAF 502 Errors

Check Docker network:

```bash
docker network ls
docker network inspect expert-stack_waflab
```

Check containers:

```bash
docker compose ps
docker logs custom-waf
docker logs backend-app
```

---

# 📋 Cheat Sheet

## Daily Lab Start

```bash
cd ~/waf-lab/expert-stack
docker compose up -d
docker compose ps
```

---

## Verify All Lab Ports

```bash
for port in 9001 9002 9003 9004 8084; do
  echo -n "Port $port: "
  curl -s -o /dev/null -w "%{http_code}\n" "http://localhost:$port"
done
```

---

## Lab URLs

| URL | Purpose |
|---|---|
| `http://localhost:9001` | PL1 WAF |
| `http://localhost:9002` | PL2 WAF |
| `http://localhost:9003` | PL3 WAF |
| `http://localhost:9004` | PL4 WAF |
| `http://localhost:9005` | Custom Python WAF |
| `http://localhost:8083` | Juice Shop standalone |
| `http://localhost:8084/WebGoat` | WebGoat |
| `http://localhost:8085/WebWolf` | WebWolf |
| `https://portswigger.net/web-security` | PortSwigger Academy |

---

## Payload Testing Across PL Levels

Save as:

```text
test-payload.sh
```

```bash
#!/bin/bash

PAYLOAD="$1"

for pl in 1 2 3 4; do
  port=$((9000 + pl))
  status=$(curl -s -o /dev/null -w "%{http_code}" \
    "http://localhost:$port/?q=$PAYLOAD")
  echo "PL$pl: $status"
done
```

Usage:

```bash
chmod +x test-payload.sh
./test-payload.sh "<script>alert(1)</script>"
```

Example output:

```text
PL1: 403
PL2: 403
PL3: 403
PL4: 403
```

---

# 📚 Resources

## Gold-Standard Learning

- [PortSwigger Web Security Academy](https://portswigger.net/web-security)
- [HackTricks](https://book.hacktricks.xyz/)
- [YesWeHack Dojo](https://dojo-yeswehack.com/)

## Lab Repositories

- [Vulhub](https://github.com/vulhub/vulhub)
- [OWASP Juice Shop](https://github.com/juice-shop/juice-shop)
- [WebGoat](https://github.com/WebGoat/WebGoat)
- [OWASP CRS](https://github.com/coreruleset/coreruleset)

## Bug Bounty Platforms

- [HackerOne](https://hackerone.com)
- [Bugcrowd](https://bugcrowd.com)
- [YesWeHack](https://yeswehack.com)
- [Intigriti](https://intigriti.com)

## Daily Reading

- [HackerOne Hacktivity](https://hackerone.com/hacktivity)
- [Pentester Land](https://pentester.land)
- [InfoSec Write-ups](https://infosecwriteups.com)
- [PortSwigger Research](https://portswigger.net/research)

## Research Blogs

- [Assetnote Research](https://www.assetnote.io/resources/research)
- [Detectify Labs](https://labs.detectify.com/)
- [Gareth Heyes Research](https://portswigger.net/research)

---

# ❓ Self-Check Questions

1. Beginner labs skip kore expert labs use korar reason ki?
2. Vulhub er main advantage real-world learning e ki?
3. OWASP CRS er 4 ta paranoia level er use case ki?
4. PortSwigger Academy registration keno important?
5. Bug bounty scope verify kora keno critical?
6. Burp Match & Replace rule keno useful?
7. Custom Python WAF build kore ki shikha jay?
8. HackerOne, YesWeHack, Bugcrowd, Intigriti — key difference ki?

✅ All 8 answered confidently? **Day 5 complete!**

---

# 🚀 What’s Next?

**Day 6 Preview:** Encoding, Obfuscation & XSS WAF Bypass Mastery

- URL encoding
- Unicode escaping
- HTML entities
- Base64
- Hex encoding
- XSS payload variations across contexts
- CRS `941xxx` rule study
- Polyglot XSS payloads
- Real hunter XSS breakdowns
- Hands-on testing across PL1–PL4

---

# 📝 My Day 5 Notes

<!-- Fill in after completion -->

## Lab Stack Status

- [ ] PortSwigger Academy account
- [ ] Vulhub cloned
- [ ] Vulhub lab tested
- [ ] Juice Shop running
- [ ] WebGoat running
- [ ] WAF PL1 running on `9001`
- [ ] WAF PL2 running on `9002`
- [ ] WAF PL3 running on `9003`
- [ ] WAF PL4 running on `9004`
- [ ] Custom Python WAF running on `9005` optional

---

## Platforms Registered

| Platform | Username |
|---|---|
| HackerOne |  |
| YesWeHack |  |
| Bugcrowd |  |
| Intigriti |  |

---

## Burp Extensions Installed

- [ ] Hackvertor
- [ ] Turbo Intruder
- [ ] Param Miner
- [ ] Active Scan++
- [ ] HTTP Request Smuggler
- [ ] Backslash Powered Scanner
- [ ] Logger++
- [ ] Autorize
- [ ] Collaborator Everywhere
- [ ] WAF Cookie Fetcher

---

## Initial Test Results

| Payload | PL1 | PL2 | PL3 | PL4 |
|---|---|---|---|---|
| `<script>alert(1)</script>` | ❌ | ❌ | ❌ | ❌ |
| `<svg/onload=alert(1)>` |  |  |  |  |
| `<img src=x onerror=alert(1)>` |  |  |  |  |

---

## Writeups Read Today

```text
1.
2.
3.
```

---

## Key Insight of the Day

```text
A real hunter's lab is ready for real payloads, not textbook exercises.
```

---

## Challenges Faced

```text
-
-
-
```

---

## Tomorrow’s Prep

- [ ] Review Day 5 notes
- [ ] Keep WAF matrix ready
- [ ] Install Hackvertor
- [ ] Prepare Day 6 XSS testing notes

---

<p align="center">
  <strong>🎓 Day 5 Status:</strong> ⬜ In Progress / ✅ Complete<br>
  <em>“The quality of your tools determines the ceiling of your craft.”</em>
</p>

<p align="center">
  <a href="./Day-04.md">← Previous: Day 04</a> |
  <a href="./Day-06.md">Next: Day 06 →</a>
</p>
