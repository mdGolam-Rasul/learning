# 🎯 Day 13 — Live Bug Bounty Recon → Exploitation Workflow

> **Part of:** 15-Day WAF Bypass & Payload Crafting Mastery — Week 3  
> **Date:** Tuesday, April 28, 2026  
> **Difficulty:** ⭐⭐⭐⭐⭐ Real World  
> **Time Required:** 7–10 hours  
> **Focus:** First real hunting session with legal scope, structured recon, testing, documentation, and debrief  

![Day](https://img.shields.io/badge/Day-13%2F15-purple)
![Status](https://img.shields.io/badge/Status-LIVE%20HUNTING-red)
![Focus](https://img.shields.io/badge/Focus-Real%20Bug%20Bounty-critical)
![Stakes](https://img.shields.io/badge/Stakes-FIRST%20REPORT-gold)

> ⚠️ **Ethical Use Only:**  
> This workflow is only for legal bug bounty programs, VDPs, private labs, CTFs, and explicitly authorized penetration testing.  
> Never test outside scope, never access real user data, never run destructive actions, and always follow program rules.

---

## 📑 Table of Contents

- [🎯 The Moment of Truth](#-the-moment-of-truth)
- [🎯 Objectives](#-objectives)
- [⏰ Time Breakdown](#-time-breakdown)
- [⚖️ Session 1: Ethical & Legal Foundation](#️-session-1-ethical--legal-foundation)
- [🎯 Session 2: Target Selection Strategy](#-session-2-target-selection-strategy)
- [🔎 Session 3: Deep Reconnaissance](#-session-3-deep-reconnaissance)
- [🗺️ Session 4: Attack Surface Analysis](#️-session-4-attack-surface-analysis)
- [💥 Session 5: Systematic Exploitation](#-session-5-systematic-exploitation)
- [🔄 Session 6: Dead-Ends & Pivoting](#-session-6-dead-ends--pivoting)
- [🎉 Session 7: When You Find Something](#-session-7-when-you-find-something)
- [📊 Session 8: Session Debrief](#-session-8-session-debrief)
- [🔁 Micro-Habits Day 13](#-micro-habits-day-13)
- [🏆 Day 13 Challenge](#-day-13-challenge)
- [📋 Master Cheat Sheets](#-master-cheat-sheets)
- [📚 Resources](#-resources)
- [❓ Self-Check Questions](#-self-check-questions)
- [🚀 What’s Next](#-whats-next)
- [📝 My Day 13 Notes](#-my-day-13-notes)
- [🚀 Commit Workflow](#-commit-workflow)
- [🎯 Key Actions for Today](#-key-actions-for-today)
- [⚠️ Critical Reminders](#️-critical-reminders)
- [💡 Pro Tips](#-pro-tips)
- [🌟 The Mental Game](#-the-mental-game)
- [📊 Week 3 Progress](#-week-3-progress)

---

# 🎯 The Moment of Truth

```text
┌────────────────────────────────────────────────────────┐
│  THIRTEEN DAYS OF PREPARATION                          │
├────────────────────────────────────────────────────────┤
│  Day 01–05: Foundation + Lab                           │
│  Day 06–10: Core Mastery: XSS, SQLi, SSRF, Cloud       │
│  Day 11:    Learned from elite hunters                 │
│  Day 12:    Built your own toolkit                     │
│  Day 13:    APPLY IT ALL ← YOU ARE HERE                │
└────────────────────────────────────────────────────────┘
```

Today is different:

- No simulated labs
- No fake vulnerabilities
- Real target
- Real program rules
- Real bounty potential
- Real consequences if scope is ignored

The truth:

```text
Most first hunting sessions find nothing.
That is normal.
The goal today is not only finding bugs.
The real goal is practicing professional methodology.
```

---

# 🎯 Objectives

By the end of Day 13, I will be able to:

- [ ] Select an appropriate legal bug bounty target
- [ ] Read and understand program scope thoroughly
- [ ] Execute deep reconnaissance using my custom toolkit
- [ ] Map the attack surface systematically
- [ ] Apply Week 1–2 exploitation techniques safely
- [ ] Handle dead-ends without frustration
- [ ] Document the full hunting session professionally
- [ ] Submit a report only if a valid in-scope bug is found
- [ ] Complete an honest post-session debrief

---

# ⏰ Time Breakdown

| Session | Topic | Duration |
|---|---|---:|
| 1 | Ethical & Legal Foundation | 30 min |
| 2 | Target Selection Strategy | 60 min |
| 3 | Deep Reconnaissance | 120 min |
| 4 | Attack Surface Analysis | 90 min |
| 5 | Systematic Exploitation | 120 min |
| 6 | Dead-Ends & Pivoting | 60 min |
| 7 | When You Find Something | 45 min |
| 8 | Session Debrief | 30 min |
| **Total** |  | **~9 hours** |

> 💡 You do not have to finish everything in one sitting. Quality matters more than speed.

---

# ⚖️ Session 1: Ethical & Legal Foundation

## Bug Bounty Hunter’s Oath

```text
┌──────────────────────────────────────────────────────┐
│  BUG BOUNTY HUNTER'S OATH                            │
├──────────────────────────────────────────────────────┤
│  1. NEVER test outside program scope                 │
│  2. NEVER exfiltrate data beyond minimum PoC         │
│  3. NEVER access other users' real data              │
│  4. NEVER perform destructive actions                │
│  5. NEVER run DoS/DDoS testing without permission    │
│  6. ALWAYS read scope carefully                      │
│  7. ALWAYS report responsibly                        │
│  8. ALWAYS stop testing if asked                     │
│  9. ALWAYS demonstrate impact safely                 │
│ 10. RESPECT program rules even if frustrating        │
└──────────────────────────────────────────────────────┘
```

Violating rules can cause:

- Platform bans
- Legal risk
- Permanent reputation damage
- Harm to the wider security community

---

## Scope Reading Checklist

Before testing any program, complete this checklist.

```markdown
# Scope Verification Checklist

## In-Scope Targets

- [ ] Exact domains listed:
- [ ] Wildcard scope allowed? Example: `*.target.com`
- [ ] IP ranges specified?
- [ ] APIs included?
- [ ] Mobile apps included?
- [ ] Staging/dev assets included?

## Out-of-Scope Targets

- [ ] Explicitly excluded domains:
- [ ] Explicitly excluded subdomains:
- [ ] Third-party services excluded?
- [ ] Employee accounts or internal assets excluded?

## Testing Restrictions

- [ ] Automated scanning allowed?
- [ ] Rate limits mentioned?
- [ ] DoS testing forbidden?
- [ ] Social engineering forbidden?
- [ ] Physical testing forbidden?
- [ ] Test accounts allowed?

## Bounty Information

- [ ] Minimum bounty:
- [ ] Maximum bounty:
- [ ] Severity mapping:
- [ ] Payment method:

## Disclosure Rules

- [ ] Public disclosure allowed?
- [ ] Disclosure allowed only after fix?
- [ ] NDA requirements?

## Submission Requirements

- [ ] PoC format required:
- [ ] Screenshots needed?
- [ ] Video needed?
- [ ] Raw request/response needed?
```

---

## Safe Harbor

Look for programs with safe harbor language.

Example:

```text
Security research conducted according to this policy is authorized.
```

Programs with safe harbor are safer for beginners because they clearly define acceptable testing behavior.

---

## Stop Testing Protocol

If you accidentally:

| Situation | Action |
|---|---|
| Access unintended data | Stop immediately and report minimal details |
| Cause instability | Stop testing and notify the program |
| Find critical impact | Stop exploitation and submit safe proof |
| Become unsure about scope | Stop and re-check policy |

---

# 🎯 Session 2: Target Selection Strategy

## Choose Your First Target Wisely

Bad first targets:

- Google, Facebook, Apple, Microsoft-level targets
- Extremely competitive programs
- Very narrow scopes
- Programs with unclear rules
- Programs that forbid automation when your plan depends on automation

Good first targets:

- Broad wildcard scopes
- VDP programs
- Newly launched programs
- Mid-size SaaS companies
- Products you already understand
- Programs with clear safe harbor

---

## Platforms to Explore

| Platform | URL | Notes |
|---|---|---|
| HackerOne | [hackerone.com](https://hackerone.com) | Large public and private programs |
| Bugcrowd | [bugcrowd.com](https://bugcrowd.com) | Diverse programs |
| YesWeHack | [yeswehack.com](https://yeswehack.com) | Strong European programs |
| Intigriti | [intigriti.com](https://intigriti.com) | Quality European programs |
| Open Bug Bounty | [openbugbounty.org](https://openbugbounty.org) | Coordinated disclosure |

---

## Target Evaluation Matrix

Save as:

```text
target-evaluation.md
```

```markdown
# Target Evaluation: [PROGRAM NAME]

## Program Info

| Field | Value |
|---|---|
| Platform |  |
| Program URL |  |
| Launched |  |
| Total Reports |  |
| Total Hackers |  |
| Average Bounty |  |
| Response Time |  |

---

## Scope Score

| Criteria | Score |
|---|---:|
| Broad scope | __ / 3 |
| Multiple assets | __ / 2 |
| Wildcards accepted | __ / 2 |
| VDP option | __ / 1 |
| Clear out-of-scope list | __ / 2 |
| **Total** | __ / 10 |

---

## Competition Score

| Criteria | Score |
|---|---:|
| Not Fortune 500 | __ / 3 |
| Not major tech giant | __ / 2 |
| Newer program | __ / 3 |
| Fewer resolved reports | __ / 2 |
| **Total** | __ / 10 |

---

## Personal Interest Score

| Criteria | Score |
|---|---:|
| I use this product | __ / 3 |
| I know the tech stack | __ / 3 |
| Interesting attack surface | __ / 4 |
| **Total** | __ / 10 |

---

## Final Decision

```text
Final Score: __ / 30
Decision: Hunt / Pass
Reason:
```
```

---

## Beginner-Friendly Target Ideas

Consider:

1. Large VDPs with broad scope
2. Internet Bug Bounty-style open source programs
3. Smaller SaaS programs
4. Newly launched public programs
5. Your own lab if you cannot find a safe public target today

---

# 🔎 Session 3: Deep Reconnaissance

## Start With Your Day 12 Toolkit

Use your master command from Day 12:

```bash
hunt target.com
```

This should run:

```text
target_checker.py
cloud_waf_recon.py
find_origin.sh
recon_pipeline.sh
js_endpoint_extract.py
```

---

## Workspace Setup

```bash
TARGET="target.com"
DATE=$(date +%Y%m%d)

mkdir -p ~/bb-workspace/${TARGET}-${DATE}
cd ~/bb-workspace/${TARGET}-${DATE}
```

---

## Passive Recon Checklist

### WHOIS

```bash
whois target.com > whois.txt
```

### DNS Records

```bash
for type in A AAAA MX TXT NS SOA CNAME SRV CAA; do
  echo "=== $type ===" >> dns-records.txt
  dig "$type" target.com +short >> dns-records.txt
done
```

### Google Dorks

```text
site:target.com
site:target.com filetype:pdf
site:target.com inurl:admin
site:target.com intext:password
```

### GitHub Dorks

```text
target.com password
target.com api_key
target.com secret
target.com token
target.com access_key
target.com credentials
target.com .env
target.com config.yml
target.com database.yml
```

### Wayback URLs

```bash
waybackurls target.com > wayback.txt
```

### Certificate Transparency

```bash
curl -s "https://crt.sh/?q=%25.target.com&output=json" \
  | jq -r '.[].name_value' \
  | sort -u > certs.txt
```

---

## GitHub Dorking Template

Save as:

```text
github-dorks.md
```

```markdown
# GitHub Dorks for [TARGET]

## Secrets

- `[TARGET] password`
- `[TARGET] api_key`
- `[TARGET] secret`
- `[TARGET] token`
- `[TARGET] access_key`
- `[TARGET] credentials`
- `[TARGET] AWS_SECRET`
- `[TARGET] private_key`

## Configuration Files

- `[TARGET] .env`
- `[TARGET] config.yml`
- `[TARGET] database.yml`
- `[TARGET] credentials.json`
- `[TARGET] application.properties`

## Internal Tools

- `[TARGET] internal`
- `[TARGET] debug`
- `[TARGET] dev`
- `[TARGET] staging`
- `[TARGET] admin panel`

## Hidden Endpoints

- `[TARGET] /api/`
- `[TARGET] endpoint`
- `[TARGET] backend`
```

---

## Subdomain Enumeration

```bash
subfinder -d target.com -all -silent > subs-subfinder.txt
assetfinder --subs-only target.com > subs-assetfinder.txt
amass enum -passive -d target.com > subs-amass.txt

curl -s "https://crt.sh/?q=%25.target.com&output=json" \
  | jq -r '.[].name_value' \
  | sort -u > subs-crtsh.txt

cat subs-*.txt | sort -u > subs-all.txt
echo "Total subdomains: $(wc -l < subs-all.txt)"
```

---

## Live Host Probing

```bash
cat subs-all.txt | httpx -silent \
  -status-code \
  -title \
  -tech-detect \
  -web-server \
  -content-length \
  -ip \
  -cname \
  -o live-hosts.txt
```

Flag interesting hosts:

```bash
grep -iE "admin|dev|staging|test|beta|api|internal" live-hosts.txt > interesting-hosts.txt
```

---

## Content Discovery

```bash
head -10 interesting-hosts.txt | awk '{print $1}' > top-targets.txt

while read url; do
  name=$(echo "$url" | tr '/' '_' | tr ':' '_')
  ffuf -w ~/SecLists/Discovery/Web-Content/common.txt \
    -u "$url/FUZZ" \
    -mc 200,301,302,403 \
    -ac \
    -s \
    -o "ffuf-${name}.json" \
    -of json
done < top-targets.txt
```

---

## JavaScript Analysis

```bash
python3 ~/waf-lab/scripts/js_endpoint_extract.py \
  -u https://target.com \
  -o js-findings.json
```

Manual extraction example:

```bash
curl -s https://target.com/main.js \
  | grep -oE '"/(api|v[0-9]+)/[a-zA-Z0-9/_-]+"' \
  | sort -u > endpoints-from-js.txt
```

---

## Recon Checkpoint

After recon, aim to have:

- [ ] 100+ subdomains found
- [ ] 20+ live hosts confirmed
- [ ] 50+ interesting URLs collected
- [ ] 10+ endpoints from JavaScript
- [ ] 5+ interesting hosts flagged
- [ ] GitHub dorks completed
- [ ] WAF/CDN identified
- [ ] Origin discovery attempted only where allowed

---

# 🗺️ Session 4: Attack Surface Analysis

Create:

```text
attack-surface.md
```

```markdown
# Attack Surface: [TARGET]

## Main Application

| Field | Value |
|---|---|
| URL |  |
| Frontend Tech |  |
| Backend Tech |  |
| WAF/CDN |  |
| Authentication |  |

---

## Authentication Flow

| Feature | URL / Notes |
|---|---|
| Login |  |
| Registration |  |
| Password Reset |  |
| Email Change |  |
| OAuth Providers |  |
| MFA | Yes / No |

---

## User Roles

- [ ] Anonymous
- [ ] Regular user
- [ ] Premium user
- [ ] Admin
- [ ] Support staff

---

## Key Features

### User Account

- [ ] Profile editing
- [ ] Avatar upload
- [ ] Email change
- [ ] Password change
- [ ] Account deletion

### Content Features

- [ ] Comments
- [ ] Search
- [ ] File upload
- [ ] URL preview
- [ ] Messaging

### API

- [ ] REST endpoints
- [ ] GraphQL endpoint
- [ ] WebSocket endpoint
- [ ] API docs
- [ ] Swagger/OpenAPI

### Payments

- [ ] Checkout flow
- [ ] Coupons
- [ ] Subscriptions
- [ ] Refunds
- [ ] Invoices

---

## Interesting Subdomains

| Subdomain | Reason |
|---|---|
| admin.target.com |  |
| api.target.com |  |
| dev.target.com |  |
| staging.target.com |  |

---

## Top 3 Attack Priorities

### Target 1

```text
URL / Feature:
Reason:
Attack classes:
Tools:
```

### Target 2

```text
URL / Feature:
Reason:
Attack classes:
Tools:
```

### Target 3

```text
URL / Feature:
Reason:
Attack classes:
Tools:
```
```

---

## Priority Testing Order

### Tier 1 — Highest ROI

- Authentication flows
- IDOR/BOLA
- SSRF candidates
- File upload
- Business logic
- Admin panels

### Tier 2 — Medium Priority

- Stored XSS
- Reflected XSS
- SQL injection
- API authorization
- CORS
- OAuth/JWT

### Tier 3 — Lower Priority

- Missing headers
- Clickjacking
- Verbose errors
- Low-impact information disclosure

---

# 💥 Session 5: Systematic Exploitation

For each of your top 3 targets:

```text
1. Understand normal behavior
2. Identify all inputs
3. Test vulnerability classes safely
4. Document results
5. Move deeper or pivot
```

---

## Test 1: XSS

```bash
python3 ~/waf-lab/scripts/param_fuzz.py \
  -u "https://target.com/search" \
  -p q \
  -t xss
```

Manual workflow:

```text
1. Send harmless probe: TEST123
2. Check where it reflects
3. Identify context: HTML, attribute, JS, URL, JSON
4. Craft context-specific payload
5. Confirm only with safe PoC
```

Safe lab payload examples:

```html
<svg/onload=alert(1)>
<img src=x onerror=alert(1)>
<details open ontoggle=alert(1)>
```

---

## Test 2: SQL Injection

```bash
python3 ~/waf-lab/scripts/param_fuzz.py \
  -u "https://target.com/user" \
  -p id \
  -t sqli
```

Manual probes:

```text
'
"
`
\
);
```

Look for:

```text
SQL errors
Different status codes
Different response sizes
Time delays in authorized scope
Unexpected data behavior
```

---

## Test 3: SSRF

Look for:

```text
Image URL import
Avatar from URL
Webhook URL
PDF generator
URL preview
API proxy
```

Safe workflow:

```text
1. Use Burp Collaborator or controlled callback
2. Submit callback URL
3. Check DNS/HTTP interaction
4. Do not access sensitive internal data
5. Report minimal proof
```

---

## Test 4: IDOR / BOLA

Use two test accounts.

```text
User A: account_a@example.com
User B: account_b@example.com
```

Workflow:

```text
1. Log in as User A
2. Capture request containing ID
3. Replace ID with User B’s ID
4. Check if data is returned or modified
5. Use only your own test accounts
```

Example:

```http
GET /api/users/12345/orders HTTP/1.1
Host: target.com
Cookie: session=user_a_session
```

Change:

```text
12345 → 67890
```

---

## Test 5: JWT / Auth

Check:

```text
alg value
kid header
exp claim
iss claim
aud claim
role claim
user_id claim
signature validation
```

Use only your own tokens and accounts.

---

## Test 6: Business Logic

### Payment Flow

- [ ] Can I skip a payment step?
- [ ] Can I reuse expired coupons?
- [ ] Can I change currency?
- [ ] Can I apply coupon multiple times?
- [ ] Can quantity or price become negative?

### Race Conditions

- [ ] Coupon usage
- [ ] Wallet balance
- [ ] Account creation
- [ ] Email verification
- [ ] Rate-limited actions

### Account Takeover

- [ ] Weak password reset flow
- [ ] Email change without re-authentication
- [ ] OAuth redirect issue
- [ ] Session fixation
- [ ] MFA bypass

---

## Test Log Template

```markdown
# Test Log — [TIMESTAMP]

## Test 1

| Field | Value |
|---|---|
| Vulnerability Class | XSS |
| URL |  |
| Parameter |  |
| Payload |  |
| Response Status |  |
| Result | Not vulnerable / Potential / Confirmed |

### Notes

```text

```

---

## Test 2

| Field | Value |
|---|---|
| Vulnerability Class | IDOR |
| URL |  |
| Account A |  |
| Account B |  |
| Result |  |

### Notes

```text

```
```

---

# 🔄 Session 6: Dead-Ends & Pivoting

## Signs You Are Stuck

- Same parameter tested repeatedly with no progress
- WAF blocks every attempt
- Everything returns `401` or `403`
- No useful results after 2+ hours
- You are frustrated and no longer thinking clearly

---

## Pivoting Strategy

### 1. Change Target

```text
main.target.com → dev.target.com
api.target.com → api-v1.target.com
www.target.com → old.target.com
```

### 2. Change Vulnerability Class

```text
XSS not working → IDOR
IDOR not working → business logic
SSRF not working → auth testing
```

### 3. Deep Dive One Parameter

Spend 45–60 minutes on one promising parameter:

```text
Different encodings
Different HTTP methods
Different content types
Different roles
Different user states
```

### 4. Go Passive

Stop active testing and review:

```text
Scope
Public reports
Wayback URLs
GitHub leaks
JavaScript bundles
Mobile app endpoints
```

### 5. Take a Break

```text
Walk
Drink water
Eat
Return with fresh eyes
```

---

## Dead Bug Rule

If you spend 3+ hours on one vulnerability class with no progress:

```text
Stop.
Document what you tried.
Move to a new vector.
```

---

# 🎉 Session 7: When You Find Something

## Validation Checklist

```markdown
# Finding Validation Checklist

- [ ] I reproduced it 3 times
- [ ] It works from a clean browser/session
- [ ] It is in scope
- [ ] It affects real security impact
- [ ] It does not rely on unrealistic assumptions
- [ ] I used only my own accounts/data
- [ ] I did not perform destructive actions
- [ ] I have screenshots or video
- [ ] I have raw HTTP request/response if useful
```

---

## Minimize the PoC

### XSS

Do:

```text
Show alert(document.domain)
Screenshot the result
Explain theoretical impact
```

Do not:

```text
Steal cookies
Deface pages
Create worms
Target other users
```

### IDOR

Do:

```text
Use two test accounts
Show one safe unauthorized access case
Explain broader impact
```

Do not:

```text
Download bulk user data
Access random real users
Modify real data
```

---

## Report Template

```markdown
# [Vulnerability Type] in [Feature/Endpoint] leads to [Impact]

## Summary

[One short paragraph explaining the bug, root cause, and impact.]

---

## Affected Asset

| Field | Value |
|---|---|
| URL |  |
| Parameter |  |
| Method |  |
| Authentication Required | Yes / No |
| Affected Role |  |

---

## Steps to Reproduce

1. Navigate to:
2. Log in as:
3. Open:
4. Submit:
5. Observe:

---

## Proof of Concept

### Screenshot

```text
Attach screenshot here.
```

### Video

```text
Attach short video if needed.
```

### Raw Request

```http
GET /example HTTP/1.1
Host: target.com
Cookie: session=REDACTED
```

---

## Impact

An attacker may be able to:

- 
- 
- 

Business impact:

- 
- 

---

## Remediation

- Validate authorization server-side
- Apply context-aware output encoding
- Restrict dangerous functionality
- Add security regression tests
- Log and monitor suspicious behavior

---

## References

- OWASP:
- CWE:
- PortSwigger:
```

---

## Expected Program Responses

| Response | Meaning | Action |
|---|---|---|
| Triaged | Accepted for review | Wait patiently |
| Duplicate | Already reported | Learn and move on |
| Informative | Not enough impact or known issue | Improve future reports |
| Not Applicable | Not valid or out of scope | Review scope |
| Resolved + Bounty | Accepted and rewarded | Celebrate privately until disclosure allowed |

---

# 📊 Session 8: Session Debrief

Create:

```text
day-13-debrief.md
```

```markdown
# Day 13 Session Debrief

## Time Invested

| Area | Time |
|---|---:|
| Recon |  |
| Attack surface mapping |  |
| Exploitation attempts |  |
| Reporting |  |
| Total |  |

---

## Findings

| Metric | Count |
|---|---:|
| Confirmed vulnerabilities |  |
| Potential findings |  |
| Reports submitted |  |
| Duplicates avoided |  |

---

## What Worked

- 
- 
- 

## What Did Not Work

- 
- 
- 

## Tools Used

- [ ] hunt.sh
- [ ] subfinder
- [ ] httpx
- [ ] nuclei
- [ ] Burp Suite
- [ ] Custom Python scripts
- [ ] Other:

---

## Lessons Learned

### Technical

```text

```

### Methodology

```text

```

### Mindset

```text

```

---

## Adjustments for Next Session

- 
- 
- 

## Tomorrow’s Focus

```text

```
```

---

## Reality Check

If you found nothing today:

```text
That is normal.
You practiced the workflow.
You built real experience.
Next session will be sharper.
```

If you found something today:

```text
Validate carefully.
Report professionally.
Do not disclose publicly until allowed.
```

---

# 🔁 Micro-Habits Day 13

## Before Hunting

- [ ] Review methodology playbook
- [ ] Re-read program scope
- [ ] Check energy and focus level
- [ ] Set a timer
- [ ] Open private notes workspace

## During Hunting

- [ ] Take a short break every 90 minutes
- [ ] Drink water
- [ ] Log every test
- [ ] Avoid scope drift
- [ ] Stop if unsure

## After Hunting

- [ ] Close all target tabs
- [ ] Save notes privately
- [ ] Redact sensitive details
- [ ] Write debrief
- [ ] Commit only safe public notes

---

# 🏆 Day 13 Challenge

Mark Day 13 complete after:

- [ ] Selected one legal bug bounty or VDP target
- [ ] Completed the scope checklist
- [ ] Ran `hunt.sh` on an authorized target
- [ ] Enumerated subdomains
- [ ] Identified live hosts
- [ ] Mapped attack surface
- [ ] Selected 3 priority targets
- [ ] Tested at least 5 vulnerability classes
- [ ] Used your custom toolkit
- [ ] Logged every test
- [ ] Wrote session debrief
- [ ] Submitted a report if a valid bug was found
- [ ] If no bug was found, documented why
- [ ] Re-verified that no scope violations occurred
- [ ] Pushed only safe/redacted notes to GitHub

---

# 📋 Master Cheat Sheets

## Cheat Sheet 1: Quick Hunt Start

```bash
TARGET="legal-program.com"
DATE=$(date +%Y%m%d)

mkdir -p ~/bb-workspace/${TARGET}-${DATE}
cd ~/bb-workspace/${TARGET}-${DATE}

hunt "$TARGET"
burpsuite &
```

---

## Cheat Sheet 2: Vulnerability Test Order

```text
Priority 1:
- Authentication bypass
- IDOR / BOLA
- SSRF
- Business logic
- File upload

Priority 2:
- Stored XSS
- Reflected XSS
- SQL injection
- XXE
- Open redirect
- CORS misconfiguration

Priority 3:
- Missing security headers
- Verbose error messages
- Clickjacking
- Low-impact information disclosure
```

---

## Cheat Sheet 3: When Stuck

```text
1. Switch subdomain
2. Switch vulnerability class
3. Go deeper on one parameter
4. Read program writeups
5. Check Wayback URLs
6. Search GitHub for leaked code
7. Take a 20-minute break
8. Return with fresh eyes
```

---

## Cheat Sheet 4: Before Submitting

```text
[ ] Reproduced 3+ times
[ ] In scope confirmed
[ ] Not destructive
[ ] Minimum viable PoC
[ ] Clear screenshots
[ ] Raw HTTP included if useful
[ ] Impact explained
[ ] Remediation suggested
[ ] Professional tone
[ ] Disclosure rules respected
```

---

# 📚 Resources

## Bug Bounty Platforms

- [HackerOne](https://hackerone.com)
- [Bugcrowd](https://bugcrowd.com)
- [YesWeHack](https://yeswehack.com)
- [Intigriti](https://intigriti.com)
- [Open Bug Bounty](https://openbugbounty.org)

---

## Learning Materials

- [HackerOne Reports](https://www.hackerone.com/resources/reporting/hacker-powered-security-reports)
- [Pentester Land Writeups](https://pentester.land/writeups/)
- [HackTricks](https://book.hacktricks.xyz/)
- [PortSwigger Web Security Academy](https://portswigger.net/web-security)

---

## Tools

```bash
go install -v github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
go install -v github.com/projectdiscovery/httpx/cmd/httpx@latest
go install -v github.com/projectdiscovery/nuclei/v3/cmd/nuclei@latest
go install -v github.com/tomnomnom/waybackurls@latest
go install -v github.com/tomnomnom/assetfinder@latest
go install -v github.com/ffuf/ffuf/v2@latest

pip install trufflehog3
```

---

## Videos to Watch

- NahamSec live hunting videos
- STÖK bug bounty methodology videos
- InsiderPhD beginner-friendly security videos
- PortSwigger research talks

---

# ❓ Self-Check Questions

1. What are the 10 rules of the Bug Bounty Hunter’s Oath?
2. What is the difference between a VDP and a paid bounty program?
3. Why should beginners start with smaller or newer programs?
4. What does wildcard scope like `*.target.com` mean?
5. What does `hunt.sh` automate?
6. Why do elite hunters spend most of their time on recon?
7. What should I do if I accidentally access unintended data?
8. What is the ethical way to demonstrate XSS impact?
9. What are Tier 1 priority attack vectors?
10. What should I do if I am stuck for 3+ hours?
11. What information belongs in a professional bug report?
12. How should I handle a duplicate response?

✅ All 12 answered confidently? **Day 13 complete!**

---

# 🚀 What’s Next?

## Day 14 Preview — End-to-End Practice + Professional Report Writing

- Second full hunting session
- Apply lessons from Day 13
- CVSS scoring mastery
- Video PoC creation
- Disclosure etiquette
- Handling triager questions
- Professional report templates

---

# 📝 My Day 13 Notes

## Target Selected

```text
Program name:
Platform:
Scope:
Safe harbor: yes / no
```

---

## Time Investment

```text
Start time:
End time:
Total hours:
Breaks taken:
```

---

## Recon Stats

```text
Subdomains found:
Live hosts:
Interesting URLs:
Parameters discovered:
```

---

## Attack Surface Mapped

```text
Priority 1 targets:
Priority 2 targets:
Top 3 chosen:
```

---

## Vulnerability Classes Tested

- [ ] XSS
- [ ] SQLi
- [ ] SSRF
- [ ] IDOR
- [ ] Auth bypass
- [ ] File upload
- [ ] Business logic
- [ ] Other:

---

## Findings

```text
Confirmed vulnerabilities:
Reports submitted:
Types:
```

---

## Tools Used Today

- [ ] hunt.sh
- [ ] Custom scripts:
- [ ] Burp Suite
- [ ] sqlmap
- [ ] nuclei
- [ ] Other:

---

## Key Learnings

```text
Technical:
Methodology:
Mindset:
```

---

## What I Would Do Differently

```text

```

---

## Micro-Habits Today

- [ ] Morning writeup
- [ ] Tool of the day used
- [ ] X feed scan
- [ ] Payload variation
- [ ] HTTP header inspection
- [ ] Parameter miner
- [ ] PortSwigger lab
- [ ] Terminal journal
- [ ] Tool improvement

---

## My First Real Hunting Session

```text
How I felt starting:
How I felt ending:
Proudest moment:
Most challenging moment:
```

---

<p align="center">
  <strong>🎓 Day 13 Status:</strong> ⬜ In Progress / ✅ Complete<br>
  <em>“You do not become a hunter by reading about hunting. You become one by hunting responsibly.”</em>
</p>

<p align="center">
  <a href="./Day-12.md">← Previous: Day 12</a> |
  <a href="./Day-14.md">Next: Day 14 →</a>
</p>

---

# 🚀 Commit Workflow

```bash
cd ~/WAF-Bypass-30-Days/

# Save Day 13
nano Week-03/Day-13.md

# Create private hunting workspace outside repo
mkdir -p ~/bb-workspace

# Create target evaluation template
cat > ~/bb-workspace/target-evaluation-template.md << 'EOF'
# Target Evaluation: [PROGRAM NAME]

## Program Info

- Platform:
- URL:
- Launched:

## Scope Score

- Scope breadth: __ / 10
- Competition level: __ / 10
- My interest: __ / 10

## Decision

Hunt / Pass
EOF

# IMPORTANT: exclude private workspace
echo "bb-workspace/" >> .gitignore
echo "findings/" >> .gitignore
echo "private/" >> .gitignore
echo "reports/private/" >> .gitignore

# Commit safe public notes only
git add Week-03/Day-13.md .gitignore
git commit -m "🎯 Day 13: Live bug bounty recon and exploitation workflow"
git push origin main
```

---

# 🎯 Key Actions for Today

- [ ] Pick one legal target
- [ ] Read program scope twice
- [ ] Set a 4-hour focused hunting timer
- [ ] Run `hunt.sh`
- [ ] Document everything in a private workspace
- [ ] Apply methodology without skipping steps
- [ ] Stay patient if no bugs are found
- [ ] Write an honest debrief

---

# ⚠️ Critical Reminders

```text
STAY IN SCOPE.
NO destructive actions.
MINIMIZE exploitation.
DOCUMENT privately.
REDACT before publishing.
IF UNSURE, STOP.
```

---

# 💡 Pro Tips

- First sessions often find nothing. That is normal.
- The real win is completing the full workflow.
- Do not compare yourself with senior hunters.
- Screenshots are enough for many first reports.
- Read similar reports from the same program.
- Do not tweet about a live target while hunting.

---

# 🌟 The Mental Game

Today you may feel:

```text
Excitement
Frustration
Doubt
Fatigue
Curiosity
```

All normal.

```text
The hunters you admire felt the same things.
They kept going.
```

---

# 📊 Week 3 Progress

```text
Week 3: Real-World Application

Day 11 ✅ — Hunter Writeups & Methodology
Day 12 ✅ — Custom Toolkit + Automation
Day 13 ✅ — Live Recon → Exploitation
Day 14 🔜 — End-to-End Practice + Professional Reports
Day 15 🔜 — Portfolio + Next 30 Days
```
