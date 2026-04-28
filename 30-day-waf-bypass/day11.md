
# 📖 Day 11 — Real Hunter Writeups Deep-Dive & Methodology Extraction

> **Part of:** 15-Day WAF Bypass & Payload Crafting Mastery — Week 3  
> **Date:** Tuesday, April 28, 2026  
> **Difficulty:** ⭐⭐⭐⭐⭐ Expert — Methodology  
> **Time Required:** 7–8 hours  
> **Focus:** Learning from elite hunters, extracting methodology, and applying it to real hunting workflows  

![Day](https://img.shields.io/badge/Day-11%2F15-purple)
![Status](https://img.shields.io/badge/Status-Week%203%20Start-red)
![Focus](https://img.shields.io/badge/Focus-Hunter%20Methodology-gold)
![Week](https://img.shields.io/badge/Week-3%20Real%20World-orange)

> ⚠️ **Ethical Use Only:**  
> Ei note shudhu legal bug bounty, authorized pentest, private lab, CTF, PortSwigger labs, YesWeHack Dojo, or defensive learning er jonno. Unauthorized target e testing, exploitation, credential access, data exfiltration, destructive testing, or abuse kora jabe na.

---

## 📑 Table of Contents

- [🎯 Week 3 Opening — Why Writeups Matter](#-week-3-opening--why-writeups-matter)
- [🎯 Objectives](#-objectives)
- [⏰ Time Breakdown](#-time-breakdown)
- [📚 Session 1: The Art of Reading Writeups](#-session-1-the-art-of-reading-writeups)
- [🔥 Session 2: 5 HackerOne Top Writeups](#-session-2-5-hackerone-top-writeups)
- [🌍 Session 3: 5 YesWeHack & Intigriti Writeups](#-session-3-5-yeswehack--intigriti-writeups)
- [🐦 Session 4: 5 X.com Hunter Threads](#-session-4-5-xcom-hunter-threads)
- [📰 Session 5: 5 Elite Research Blogs](#-session-5-5-elite-research-blogs)
- [🧠 Session 6: Methodology Extraction → Your Playbook](#-session-6-methodology-extraction--your-playbook)
- [👤 Session 7: Building Your Hunter Profile](#-session-7-building-your-hunter-profile)
- [🔁 Micro-Habits Day 11 Additions](#-micro-habits-day-11-additions)
- [🏆 Day 11 Challenge](#-day-11-challenge)
- [📋 Master Cheat Sheets](#-master-cheat-sheets)
- [📚 Resources](#-resources)
- [❓ Self-Check Questions](#-self-check-questions)
- [🚀 What’s Next](#-whats-next)
- [📝 My Day 11 Notes](#-my-day-11-notes)
- [🚀 Commit Workflow](#-commit-workflow)
- [🎯 Key Actions for Today](#-key-actions-for-today)
- [💡 Pro Tips for Day 11](#-pro-tips-for-day-11)
- [📊 Week 3 Roadmap Preview](#-week-3-roadmap-preview)

---

# 🎯 Week 3 Opening — Why Writeups Matter

> **“Reading one great writeup = 10 hours of trial and error saved.”**

In **Weeks 1–2**, I learned **what to do**.  
In **Week 3**, I will learn **how elite hunters actually think and operate**.

```text
┌──────────────────────────────────────────────────────┐
│  THE LEARNING LADDER                                 │
├──────────────────────────────────────────────────────┤
│  1. Tutorials                                        │
│     → Week 1–2 foundation                            │
│                                                      │
│  2. Writeups                                         │
│     → Day 11 methodology extraction                  │
│                                                      │
│  3. Mentorship                                       │
│     → Rare but powerful                              │
│                                                      │
│  4. Original Research                                │
│     → Day 12+ custom tooling and discovery           │
│                                                      │
│  5. Publishing Research                              │
│     → Day 15 portfolio and public identity           │
└──────────────────────────────────────────────────────┘
```

---

## What Writeups Teach

| Writeup Teaches | Why It Matters |
|---|---|
| Real reconnaissance flow | Shows how hunters actually start |
| Hunter thinking process | Reveals decision-making, not only payloads |
| Tools used in real hunts | Separates practical tools from hype |
| Dead ends and pivots | Teaches what not to waste time on |
| Impact demonstration | Shows how to turn bugs into accepted reports |
| Report writing style | Helps improve triage success |

---

# 🎯 Objectives

By the end of Day 11, I will be able to:

- [ ] Read any writeup and extract **methodology**, not just payloads
- [ ] Identify **patterns across 15+ elite writeups**
- [ ] Follow major hacktivity and research feeds systematically
- [ ] Understand reconnaissance approaches of top hunters
- [ ] Build a personal **bug bounty playbook**
- [ ] Build a public **hunter profile document**
- [ ] Create a writeup reading tracker
- [ ] Apply methodology learned to my own hunting sessions

---

# ⏰ Time Breakdown

| Session | Topic | Duration |
|---|---|---:|
| 1 | The Art of Reading Writeups | 45 min |
| 2 | 5 HackerOne Top Writeups | 90 min |
| 3 | 5 YesWeHack & Intigriti Writeups | 90 min |
| 4 | 5 X.com Hunter Threads | 75 min |
| 5 | 5 Elite Research Blogs | 75 min |
| 6 | Methodology Extraction → Playbook | 75 min |
| 7 | Building Your Hunter Profile | 60 min |
| **Total** |  | **~8 hours** |

---

# 📚 Session 1: The Art of Reading Writeups

## How Beginners Read Writeups

```text
1. See title: “Found $50K XSS”
2. Scroll directly to payload
3. Copy payload
4. Paste into random target
5. Payload does not work
6. Get frustrated
```

### Result

```text
Nothing meaningful learned.
```

---

## How Elite Hunters Read Writeups

```text
1. Read the introduction and understand context
2. Note the target type and application category
3. Study the recon path
4. Identify the discovery moment
5. Follow the failed attempts
6. Understand why the payload worked
7. Study the impact demonstration
8. Observe report writing style
9. Extract repeatable patterns
10. Add lessons to personal knowledge base
```

### Result

```text
Methodology absorbed.
```

---

## 5W-1H Writeup Template

Use this for every writeup.

```markdown
# Writeup: [Title]

## Source

URL:
Date Published:
Bounty:
Platform:

---

## WHO

Researcher handle:
Target organization:
Program platform:

---

## WHAT

Vulnerability class:
Attack vector:
Impact severity:

---

## WHERE

Endpoint:
Parameter / field:
Asset type: Web / API / Mobile / Cloud / Other

---

## WHEN

Discovery date:
Report date:
Disclosure date:

---

## WHY

Root cause:
Why protection failed:
Why impact mattered:

---

## HOW

Step 1 — Recon:
Step 2 — Discovery:
Step 3 — Exploitation:
Step 4 — Impact demonstration:
Step 5 — Report:

---

## MY LEARNINGS

New technique:
Tool discovered:
Payload pattern:
Methodology to adopt:
Mistake to avoid:
```

---

## Where to Find Elite Writeups

| Platform | URL | Specialty |
|---|---|---|
| HackerOne Hacktivity | [hackerone.com/hacktivity](https://hackerone.com/hacktivity) | Disclosed reports |
| YesWeHack Dojo | [dojo-yeswehack.com](https://dojo-yeswehack.com) | Labs + writeups |
| Intigriti Blog | [blog.intigriti.com](https://blog.intigriti.com) | Weekly challenges |
| Bugcrowd Blog | [bugcrowd.com/blog](https://bugcrowd.com/blog) | Public disclosures |
| Pentester Land | [pentester.land](https://pentester.land) | Aggregated feed |
| InfoSec Writeups | [infosecwriteups.com](https://infosecwriteups.com) | Medium aggregator |
| PortSwigger Research | [portswigger.net/research](https://portswigger.net/research) | Advanced web security research |
| X / Twitter | Security researchers | Real-time methodology and payload ideas |

---

## Writeup Tracker Template

Save as:

```text
writeups-tracker.md
```

```markdown
# My Writeup Reading Log

## 2026-04-28

### Writeup 1

Title:
Source:
Platform:
Bounty:
Bug Class:
Key Technique:
Added to Vault: ✅ / ❌
Main Lesson:

---

### Writeup 2

Title:
Source:
Platform:
Bounty:
Bug Class:
Key Technique:
Added to Vault: ✅ / ❌
Main Lesson:
```

---

# 🔥 Session 2: 5 HackerOne Top Writeups

> Goal: learn methodology from real disclosed or public research-style cases.  
> Do not blindly copy payloads. Extract hunting process.

---

## 📘 Writeup #1 — Sam Curry: Hacking Starbucks

| Field | Details |
|---|---|
| Researcher | Sam Curry |
| Target Type | Gift card / API system |
| Impact | Sensitive financial-style gift card data exposure |
| Core Lesson | Hidden APIs + weak authorization can create massive impact |

### Methodology Breakdown

#### Step 1: Recon

```text
- Started from target’s public bug bounty scope
- Enumerated subdomains
- Looked for APIs and microservices
- Reviewed JavaScript for hidden endpoints
```

#### Step 2: Discovery

```text
- Found obscure API endpoints
- Noticed user/resource identifiers
- Tested access control with different accounts
```

#### Step 3: Root Cause

```text
API trusted object identifiers without proper authorization checks.
```

#### Step 4: Impact Demonstration

```text
- Demonstrated read-only access
- Avoided destructive actions
- Explained business impact clearly
```

### Lessons

- ✅ JS files often reveal hidden APIs
- ✅ IDOR/BOLA still works on modern apps
- ✅ Authorization must be tested with multiple accounts
- ✅ Ethical impact demonstration matters

Add to vault:

```text
payload-vault/methodology/sam-curry-starbucks.md
```

---

## 📘 Writeup #2 — NahamSec: SSRF Chain Methodology

| Field | Details |
|---|---|
| Researcher | NahamSec |
| Bug Class | SSRF chain |
| Target Type | Image / URL fetch feature |
| Core Lesson | SSRF becomes high impact when chained |

### Methodology Breakdown

#### Step 1: Feature Identification

```text
- Image upload
- Avatar URL import
- Link preview
- Webhook or PDF generator
```

#### Step 2: SSRF Confirmation

```text
- Use safe OOB callback
- Confirm DNS or HTTP interaction
- Avoid accessing sensitive internal data
```

#### Step 3: Internal Behavior Mapping

```text
- Check response differences
- Identify internal service behavior
- Document safely
```

#### Step 4: Chain Thinking

```text
SSRF → internal service exposure → higher-impact report
```

### Lessons

- ✅ Image URL import features are common SSRF candidates
- ✅ Burp Collaborator / OOB testing is essential
- ✅ High impact comes from chaining, not only confirming callback
- ✅ Report minimal safe proof

---

## 📘 Writeup #3 — Jack Cable: CSP Bypass via Script Gadget

| Field | Details |
|---|---|
| Researcher | Jack Cable |
| Bug Class | XSS + CSP bypass |
| Target Type | SaaS application |
| Core Lesson | CSP can be bypassed through trusted gadgets |

### Methodology Breakdown

#### Step 1: Initial XSS

```text
- Reflected XSS found
- Basic execution blocked by CSP
```

#### Step 2: CSP Analysis

```http
Content-Security-Policy: default-src 'self'; script-src 'self' https://cdn.company.com
```

#### Step 3: Gadget Hunting

```text
- Enumerated allowed script sources
- Looked for JSONP or callback-style endpoints
- Tested trusted domains for controllable JavaScript
```

#### Step 4: Impact

```text
CSP did not fully mitigate XSS because allowed domains contained unsafe script gadgets.
```

### Lessons

- ✅ CSP is not an automatic fix
- ✅ Allowed domains must be audited
- ✅ JSONP-style endpoints are classic gadgets
- ✅ `self` can be dangerous if uploads or dynamic scripts exist

---

## 📘 Writeup #4 — Frans Rosén: IDOR Chain

| Field | Details |
|---|---|
| Researcher | Frans Rosén |
| Bug Class | IDOR / Broken Access Control |
| Target Type | E-commerce / SaaS |
| Core Lesson | Low-severity IDOR can become critical when chained |

### Methodology Breakdown

#### Step 1: Multi-Account Setup

```text
- Create User A
- Create User B
- Capture requests from both
- Swap IDs and tokens carefully
```

#### Step 2: Authorization Testing

```http
GET /api/users/123/orders
GET /api/users/456/orders
```

#### Step 3: Privilege Escalation

```text
- Try low IDs carefully in authorized scope
- Look for admin-only endpoints
- Test whether role checks exist server-side
```

#### Step 4: Impact

```text
Access to other users’ data can become full account or admin compromise if chained.
```

### Lessons

- ✅ Always test with 2+ accounts
- ✅ Object-level authorization matters
- ✅ API docs and JS files often reveal hidden admin endpoints
- ✅ Clear impact turns IDOR into a strong report

---

## 📘 Writeup #5 — Orange Tsai: SSRF + Internal Service Research

| Field | Details |
|---|---|
| Researcher | Orange Tsai |
| Bug Class | SSRF / parser abuse / internal service access |
| Target Type | Large-scale web infrastructure |
| Core Lesson | SSRF impact depends on reachable internal services |

### Methodology Breakdown

```text
SSRF found
  ↓
Internal services identified
  ↓
Protocol behavior studied
  ↓
High-impact internal access demonstrated safely
```

### Lessons

- ✅ SSRF should be treated as a gateway vulnerability
- ✅ Internal services dramatically increase severity
- ✅ Protocol smuggling and parser behavior matter
- ✅ Keep proof safe and non-destructive

---

# 🌍 Session 3: 5 YesWeHack & Intigriti Writeups

---

## 📗 Writeup #6 — YesWeHack Dojo: XXE Chain

| Field | Details |
|---|---|
| Platform | YesWeHack Dojo |
| Bug Class | XXE |
| Target Type | Document / XML processing |
| Core Lesson | File upload parsers can become SSRF and data exposure vectors |

### Chain Pattern

```text
XML upload
  ↓
External entity processing
  ↓
Server-side request
  ↓
Cloud or internal metadata risk
```

### Safe Learning Payload Concept

```xml
<?xml version="1.0"?>
<!DOCTYPE root [
  <!ENTITY test SYSTEM "http://your-lab-callback.example/test">
]>
<root>&test;</root>
```

### Lessons

- ✅ XML document upload is high-value attack surface
- ✅ Blind XXE requires OOB testing
- ✅ XXE can become SSRF
- ✅ Cloud metadata proof must be handled responsibly

---

## 📗 Writeup #7 — Intigriti: GraphQL Introspection Leak

| Field | Details |
|---|---|
| Platform | Intigriti |
| Bug Class | GraphQL misconfiguration |
| Target Type | API |
| Core Lesson | GraphQL schema exposure can reveal hidden functionality |

### Methodology

#### Step 1: Find Endpoint

```text
/graphql
/api/graphql
/v1/graphql
```

#### Step 2: Test Introspection

```graphql
query {
  __schema {
    types {
      name
    }
  }
}
```

#### Step 3: Look for Dangerous Mutations

```text
setUserRole
updateUser
deleteUser
createAdmin
changeEmail
resetPassword
```

#### Step 4: Authorization Testing

```text
Schema visibility alone is not always a bug.
Missing authorization on sensitive mutations is high impact.
```

### Lessons

- ✅ GraphQL introspection can expose hidden attack surface
- ✅ Mutations are often more sensitive than queries
- ✅ Test authorization, not only schema exposure
- ✅ InQL and graphql-cop are useful tools

---

## 📗 Writeup #8 — YesWeHack: Prototype Pollution Chain

| Field | Details |
|---|---|
| Platform | YesWeHack |
| Bug Class | Prototype pollution |
| Target Type | Node.js / client-side app |
| Core Lesson | Prototype pollution becomes impactful when a gadget exists |

### Chain Pattern

```text
Prototype pollution
  ↓
Application reads polluted property
  ↓
DOM or template gadget
  ↓
XSS or privilege logic impact
```

### Test Concept

```text
?__proto__[test_property]=test_value
```

### Lessons

- ✅ Pollution alone may not be enough
- ✅ Gadget hunting is the hard part
- ✅ Client-side JS review is essential
- ✅ Param Miner / PPScan can help

---

## 📗 Writeup #9 — Intigriti: JWT Algorithm Confusion

| Field | Details |
|---|---|
| Platform | Intigriti |
| Bug Class | JWT authentication flaw |
| Target Type | API |
| Core Lesson | Token validation must enforce expected algorithm and signature |

### Methodology

```text
1. Capture JWT
2. Decode header and claims
3. Identify algorithm
4. Test safe validation weaknesses in lab or authorized scope
5. Verify role/identity enforcement server-side
```

### Lessons

- ✅ JWT bugs often become account takeover
- ✅ Always check `alg`, `kid`, expiry, issuer, audience
- ✅ Use `jwt_tool` and Burp JWT extensions
- ✅ Never tamper outside allowed scope

---

## 📗 Writeup #10 — YesWeHack: OAuth Redirect URI Bypass

| Field | Details |
|---|---|
| Platform | YesWeHack |
| Bug Class | OAuth misconfiguration |
| Target Type | SaaS login flow |
| Core Lesson | Weak redirect URI validation can leak tokens |

### Common Test Cases

```text
https://target.com.attacker.com/callback
https://target.com@attacker.com/callback
https://attacker.com#target.com
https://target.com/callback/../redirect
```

### Lessons

- ✅ OAuth bugs often mean account takeover
- ✅ `redirect_uri` validation must be exact
- ✅ URL parser confusion is common
- ✅ Always test safely with your own accounts

---

# 🐦 Session 4: 5 X.com Hunter Threads

---

## 🐦 Thread #1 — @garethheyes: Novel XSS Techniques

| Field | Details |
|---|---|
| Handle | @garethheyes |
| Specialty | XSS, DOM, browser parser behavior |
| Lesson | Browser parsing knowledge creates new payloads |

### Takeaways

- SVG and MathML are rich XSS surfaces
- Browser behavior matters more than payload memorization
- WAFs often miss unusual but valid browser features

### Action

```text
Screenshot interesting payload ideas.
Recreate only in local lab.
Document context and browser behavior.
```

---

## 🐦 Thread #2 — @NahamSec: Methodology

| Field | Details |
|---|---|
| Handle | @NahamSec |
| Specialty | Bug bounty workflow, recon, education |
| Lesson | Methodology beats random testing |

### Signature Flow

```text
Recon
  ↓
Content discovery
  ↓
Authentication mapping
  ↓
API enumeration
  ↓
Authorization testing
  ↓
Injection testing
  ↓
Business logic review
```

### Takeaways

- Spend serious time on recon
- Business logic often pays more than basic bugs
- Test boring bugs deeply

---

## 🐦 Thread #3 — @infosec_au: Source Code Review

| Field | Details |
|---|---|
| Handle | @infosec_au |
| Specialty | Source code review, 0-days, Assetnote research |
| Lesson | Source-assisted hunting increases bug yield |

### Approach

```text
1. Identify tech stack
2. Search public repos and leaks
3. Review routing files
4. Review auth middleware
5. Look for missing authorization
6. Validate through black-box testing
```

### Tools

```text
gitleaks
trufflehog
GitHub dorks
```

---

## 🐦 Thread #4 — @samwcyo: Chain Thinking

| Field | Details |
|---|---|
| Handle | @samwcyo |
| Specialty | Critical vulnerability chains |
| Lesson | One bug is useful. A chain is powerful. |

### Chain Questions

```text
XSS found?
→ Can it become account takeover?

IDOR found?
→ Can it reach admin or sensitive data?

SSRF found?
→ Can it reach internal services?

Subdomain takeover found?
→ Can it affect trusted cookies or OAuth?
```

---

## 🐦 Thread #5 — @d0nutptr: Live Hunting

| Field | Details |
|---|---|
| Handle | @d0nutptr |
| Specialty | Live bug bounty methodology |
| Lesson | Watching dead ends teaches real hunting |

### Why Live Streams Help

- You see failures
- You see pivots
- You learn tool timing
- You learn realistic expectations
- You hear the hunter’s thought process

---

# 📰 Session 5: 5 Elite Research Blogs

---

## 🌐 Blog #1 — PortSwigger Research

**URL:** [portswigger.net/research](https://portswigger.net/research)

### Must-Read Topics

- HTTP Desync Attacks
- Web Cache Poisoning
- Browser-Powered Desync Attacks
- State Machine Attacks
- Advanced XSS research

### Why It Matters

```text
PortSwigger research often creates entire new bug classes.
```

---

## 🌐 Blog #2 — Assetnote

**URL:** [blog.assetnote.io](https://blog.assetnote.io)

### Must-Read Topics

- AWS WAF bypass research
- Contextual content discovery
- SSRF research
- Out-of-band resource loading
- Source-code-based vulnerability discovery

### Why It Matters

```text
Assetnote posts are usually practical, modern, and high-impact.
```

---

## 🌐 Blog #3 — Detectify Labs

**URL:** [labs.detectify.com](https://labs.detectify.com)

### Focus Areas

- Subdomain takeover
- SaaS vulnerabilities
- Cloud misconfigurations
- Token leaks
- Real-world bug bounty trends

---

## 🌐 Blog #4 — Orange Tsai Blog

**URL:** [blog.orange.tw](https://blog.orange.tw)

### Focus Areas

- SSRF
- Parser logic
- Enterprise 0-days
- Internal service exploitation
- Advanced attack chains

---

## 🌐 Blog #5 — HackTricks

**URL:** [book.hacktricks.xyz](https://book.hacktricks.xyz)

### Use It For

- Attack checklists
- Web pentesting references
- Cloud pentesting notes
- Payload variations
- Quick syntax recall

---

# 🧠 Session 6: Methodology Extraction → Your Playbook

## Pattern 1: Recon-First Mentality

Elite hunters start with:

```text
Subdomain enumeration
HTTP probing
Content discovery
JavaScript analysis
Historical URL mining
WAF identification
Origin discovery
```

---

## Pattern 2: Context-Specific Payloads

Elite hunters do not use generic payloads blindly.

They:

```text
1. Identify injection context
2. Understand parser behavior
3. Craft context-specific payload
4. Test encoding/normalization differences
5. Document what worked and what failed
```

---

## Pattern 3: Chain Thinking

Always ask:

```text
What else can I do with this bug?
Can I escalate severity?
Can I reach admin functionality?
Can I access another user’s data?
Can I bypass a security control?
Can I turn this into account takeover?
```

---

## Pattern 4: Source Code Beats Blind Guessing

Source-assisted hunting includes:

```text
GitHub dorking
Leaked repo review
Mobile app decompilation
JavaScript bundle review
Public package review
Auth middleware review
Route mapping
```

---

## Pattern 5: Report Writing Is a Skill

Great reports include:

```text
Clear title
Specific affected asset
Numbered reproduction steps
Screenshots or video
Impact explanation
Safe proof
Remediation
Professional tone
```

---

## Build Your Personal Playbook

Save as:

```text
my-playbook.md
```

```markdown
# My Bug Bounty Playbook

## Phase 1: Recon

- [ ] Read program scope carefully
- [ ] Enumerate subdomains
- [ ] Probe live hosts
- [ ] Collect archived URLs
- [ ] Analyze JavaScript files
- [ ] Identify WAF/CDN
- [ ] Check historical DNS
- [ ] Look for origin exposure

## Phase 2: Attack Surface Mapping

- [ ] Identify authentication flow
- [ ] Map API endpoints
- [ ] List user roles
- [ ] Find upload features
- [ ] Find URL-fetching features
- [ ] Find redirect features
- [ ] Find webhook features
- [ ] Find admin or support panels

## Phase 3: Vulnerability Testing Checklist

- [ ] XSS
- [ ] SQL injection
- [ ] SSRF
- [ ] IDOR / BOLA
- [ ] Auth bypass
- [ ] CSRF
- [ ] XXE
- [ ] Prototype pollution
- [ ] Race conditions
- [ ] Business logic flaws
- [ ] OAuth / SSO issues
- [ ] JWT issues

## Phase 4: Chain Thinking

- [ ] Can I escalate severity?
- [ ] Can I reach another role?
- [ ] Can I access another user’s data?
- [ ] Can I bypass payment or workflow?
- [ ] Can I combine with another bug?
- [ ] Can I demonstrate impact safely?

## Phase 5: Reporting

- [ ] Title includes vulnerability + location + impact
- [ ] Summary is short and clear
- [ ] Steps are reproducible
- [ ] Evidence is attached
- [ ] Impact is business-relevant
- [ ] Remediation is practical
- [ ] Report is professional
```

---

# 👤 Session 7: Building Your Hunter Profile

## Why Build a Hunter Identity?

A public profile helps with:

- Trust
- Networking
- Private invitations
- Job opportunities
- Collaboration
- Accountability

---

## Step 1: Choose a Professional Handle

Good examples:

```text
@yourname_sec
@yourhandle_hunts
@yourname_security
```

Avoid:

```text
@l33th4x0r420
@evil_attacker
@blackhat_something
```

---

## Step 2: Choose a Specialization

Pick 1–2 areas:

```text
XSS and client-side security
SSRF and cloud security
Authentication and OAuth
API security
Business logic
Request smuggling
Cloud WAF bypass
Mobile app security
```

---

## Step 3: Build Public Presence

Create or improve:

- GitHub profile
- X / Twitter account
- LinkedIn
- HackerOne / Bugcrowd / Intigriti / YesWeHack profile
- Blog or notes repository

---

## Hunter Profile Template

Save as:

```text
hunter-profile.md
```

```markdown
# [Your Name] — Bug Bounty Hunter Profile

## About

Started hunting:
Focus areas:
Country / timezone:
Current learning goal:

## Goals — Next 6 Months

- [ ] Submit first valid report
- [ ] Earn first bounty
- [ ] Publish 5 writeups
- [ ] Build 3 tools
- [ ] Reach reputation milestone
- [ ] Join private programs

## Stats Tracker

| Month | Reports | Valid | Duplicates | Informative | Bounties |
|---|---:|---:|---:|---:|---:|
| May 2026 | 0 | 0 | 0 | 0 | $0 |
| June 2026 |  |  |  |  |  |

## Public Profiles

GitHub:
X / Twitter:
HackerOne:
Bugcrowd:
Intigriti:
YesWeHack:
Blog:

## My Methodology

See: `my-playbook.md`

## My Toolkit

- Burp Suite
- subfinder
- httpx
- nuclei
- ffuf
- waybackurls
- gau
- custom scripts

## Writeups Published

- None yet

## Mentors / Inspiration

- @garethheyes
- @NahamSec
- @samwcyo
- @infosec_au
- @albinowax
```

---

# 🔁 Micro-Habits Day 11 Additions

Continue habits from Day 9–10 and add these.

## Morning — 5 Minutes

- Read one post from a top hunter
- Save one interesting methodology point
- Add it to your notes or vault

## Afternoon

- Extract one methodology pattern from a writeup
- Test the concept in a lab within 24 hours

## Evening

- Update `hunter-profile.md`
- Update `writeups-tracker.md`
- Share one thing learned publicly if comfortable

## Weekly

- Pick one hunter
- Read multiple public writeups from that person
- Summarize their methodology in your own words

---

# 🏆 Day 11 Challenge

Mark Day 11 complete after:

- [ ] Read all 15 writeups or research items listed in this document
- [ ] Document each with the 5W-1H template
- [ ] Extract 5+ methodology patterns
- [ ] Build `my-playbook.md`
- [ ] Build `hunter-profile.md`
- [ ] Create `writeups-tracker.md`
- [ ] Follow 15+ hunters on X from this document and Day 4
- [ ] Subscribe to 5 research blogs
- [ ] Read at least 2 PortSwigger Research papers
- [ ] Push all notes to GitHub

---

# 📋 Master Cheat Sheets

## Cheat Sheet 1: Writeup Reading Formula

```text
Time per writeup: 20 minutes

0–5 min:
Skim title, target, bounty, platform

5–15 min:
Deep-read using 5W-1H template

15–20 min:
Extract methodology pattern into vault
```

---

## Cheat Sheet 2: Top Hunters to Follow

### XSS / Client-Side

```text
@garethheyes
@brutelogic
@renniepak
@kinugawamasato
@SecurityMB
```

### Methodology / Education

```text
@NahamSec
@stokfredrik
@Jhaddix
@zseano
@d0nutptr
```

### Research / 0-Days

```text
@albinowax
@orange_8361
@infosec_au
@fransrosen
```

### Chains / Critical Bugs

```text
@samwcyo
@defparam
@Rhynorater
```

### Platforms

```text
@intigriti
@yeswehack
@Hacker0x01
```

---

## Cheat Sheet 3: Blog RSS Feeds

```text
https://portswigger.net/research/rss
https://blog.assetnote.io/feed
https://labs.detectify.com/feed
https://blog.orange.tw/feed
https://pentester.land/feed
https://infosecwriteups.com/feed
```

---

# 📚 Resources

## Daily Reading Checklist

### Morning — 15 Minutes

- [ ] HackerOne Hacktivity
- [ ] Pentester Land daily digest
- [ ] X list: “BB Hunters”

### Evening — 15 Minutes

- [ ] One deep writeup
- [ ] Update tracker
- [ ] Add one pattern to playbook

---

## Book Recommendations

1. **The Web Application Hacker’s Handbook** — Dafydd Stuttard  
2. **Bug Bounty Bootcamp** — Vickie Li  
3. **Real-World Bug Hunting** — Peter Yaworski  
4. **The Tangled Web** — Michal Zalewski  

---

## Video Resources

- [NahamSec YouTube](https://youtube.com/c/NahamSec)
- [STÖK YouTube](https://youtube.com/c/STOKfredrik)
- [InsiderPhD YouTube](https://youtube.com/c/InsiderPhD)
- [LiveOverflow YouTube](https://youtube.com/c/LiveOverflow)

---

## Communities

- X / Twitter security community
- HackerOne community
- Bugcrowd community
- YesWeHack community
- Intigriti community
- Reddit `r/netsec`
- Reddit `r/bugbounty`
- Local DEF CON groups

---

# ❓ Self-Check Questions

1. What is the 5W-1H writeup template used for?
2. Why do elite hunters spend significant time on recon?
3. What is the difference between black-box and source-assisted hunting?
4. How does chain thinking multiply bounty value?
5. Name 3 patterns common across top writeups.
6. What tools are commonly used for content discovery?
7. What is the XXE → SSRF → cloud metadata chain concept?
8. Why are GraphQL introspection endpoints useful for methodology?
9. What is the difference between CSP-allowed and CSP-bypassable?
10. What specialization paths can a hunter choose?
11. Why is report writing a skill?
12. Why are live hunting streams useful?

✅ All 12 answered confidently? **Day 11 complete!**

---

# 🚀 What’s Next?

## Day 12 Preview — Advanced Polyglots + Custom Tooling

- Build polyglot payload generators
- Create custom Python tools
- Learn Burp extension basics
- Build optimized wordlists
- Create personal recon automation
- Turn methodology into repeatable tooling

---

# 📝 My Day 11 Notes

## Writeups Read Today

| # | Title | Source | Bounty | Key Takeaway |
|---:|---|---|---:|---|
| 1 |  |  |  |  |
| 2 |  |  |  |  |
| 3 |  |  |  |  |
| 4 |  |  |  |  |
| 5 |  |  |  |  |
| 6 |  |  |  |  |
| 7 |  |  |  |  |
| 8 |  |  |  |  |
| 9 |  |  |  |  |
| 10 |  |  |  |  |
| 11 |  |  |  |  |
| 12 |  |  |  |  |
| 13 |  |  |  |  |
| 14 |  |  |  |  |
| 15 |  |  |  |  |

---

## Methodology Patterns Extracted

1. 
2. 
3. 
4. 
5. 

---

## My Playbook Created

- [ ] Phase 1: Recon
- [ ] Phase 2: Attack surface mapping
- [ ] Phase 3: Vulnerability testing
- [ ] Phase 4: Chain thinking
- [ ] Phase 5: Report writing

---

## Hunter Profile Setup

- [ ] GitHub profile polished
- [ ] X account set up
- [ ] HackerOne profile created
- [ ] `hunter-profile.md` committed

---

## Blogs Subscribed

- [ ] PortSwigger Research
- [ ] Assetnote
- [ ] Detectify Labs
- [ ] Orange Tsai
- [ ] Pentester Land

---

## Micro-Habits Today

- [ ] Morning writeup
- [ ] Hunter of the day
- [ ] X feed scan
- [ ] Payload variation
- [ ] HTTP header inspection
- [ ] Parameter miner
- [ ] PortSwigger lab
- [ ] Terminal journal
- [ ] Profile update

---

## Week 3 Goal Set

```text
Main focus area:
6-month goal:
First report target:
```

---

## Reflection

```text
Good hunters learn payloads.
Elite hunters learn how hunters think.
```

---

<p align="center">
  <strong>🎓 Day 11 Status:</strong> ⬜ In Progress / ✅ Complete<br>
  <em>“Good hunters learn payloads. Elite hunters learn how hunters think.”</em>
</p>

<p align="center">
  <a href="../Week-02/Day-10.md">← Previous: Day 10</a> |
  <a href="./Day-12.md">Next: Day 12 →</a>
</p>

---

# 🚀 Commit Workflow

```bash
cd ~/WAF-Bypass-30-Days/

# Save Day 11
nano Week-03/Day-11.md

# Create supporting files
touch writeups-tracker.md
touch my-playbook.md
touch hunter-profile.md

# Create writeups directory
mkdir -p writeups/{hackerone,yeswehack,intigriti,x-threads,blogs}

# Commit everything
git add Week-03/Day-11.md writeups-tracker.md my-playbook.md hunter-profile.md writeups/
git commit -m "📖 Day 11: Real hunter writeups and methodology extraction"
git push origin main
```

---

# 🎯 Key Actions for Today

- [ ] Read all 15 writeups or research items
- [ ] Document each with 5W-1H template
- [ ] Build `my-playbook.md`
- [ ] Create `hunter-profile.md`
- [ ] Subscribe to 5 research blogs
- [ ] Follow 20 hunters on X and create a private list
- [ ] Start writeup habit: 1 writeup per day minimum

---

# 💡 Pro Tips for Day 11

- Do not read all writeups in one sitting.
- Use a timer: 20 minutes per writeup.
- Take notes in your own words.
- Extract methodology, not just payloads.
- Copy workflows from elite hunters until they become natural.
- Specialize early: XSS, SSRF, IDOR, auth, cloud, or API security.

---

# 📊 Week 3 Roadmap Preview

```text
Week 3: Real-World Application

Day 11 ✅ — Hunter Writeups Deep-Dive
Day 12 🔜 — Advanced Polyglots + Custom Tools
Day 13 🔜 — Live Recon → Exploitation Workflow
Day 14 🔜 — End-to-End Practice + Pro Reports
Day 15 🔜 — Portfolio, Publication + Next 30 Days
```
