# 🏗️ Day 02 — WAF Architecture, Types & Detection Models

> **Part of:** 30-Day WAF Bypass & Payload Crafting Journey  
> **Date:** _Add your date_  
> **Difficulty:** ⭐⭐☆☆☆ Beginner-Intermediate  
> **Time Required:** 3.5–4 hours  

![Day](https://img.shields.io/badge/Day-02%2F30-blue)
![Status](https://img.shields.io/badge/Status-In%20Progress-yellow)
![Focus](https://img.shields.io/badge/Focus-WAF%20Architecture-orange)
![Difficulty](https://img.shields.io/badge/Difficulty-Beginner%2B-green)

> Ethical learning only. Test only on authorized targets, labs, CTFs, or bug bounty programs with valid scope.

---

## 📑 Table of Contents

- [🎯 Objectives](#-objectives)
- [⏰ Time Breakdown](#-time-breakdown)
- [🏗️ Session 1: WAF Architecture Deep Dive](#️-session-1-waf-architecture-deep-dive)
- [🌐 Session 2: WAF Types & Deployment Models](#-session-2-waf-types--deployment-models)
- [🔍 Session 3: Detection Mechanisms](#-session-3-detection-mechanisms)
- [🧪 Session 4: Hands-on Lab — WAF Behavior Analysis](#-session-4-hands-on-lab--waf-behavior-analysis)
- [🗺️ Session 5: Mind-Map & Notes](#️-session-5-mind-map--notes)
- [🏆 Day 2 Challenge](#-day-2-challenge)
- [📋 Cheat Sheet](#-cheat-sheet)
- [⚠️ Common Mistakes](#️-common-mistakes-to-avoid)
- [📚 Resources](#-resources)
- [❓ Self-Check Questions](#-self-check-questions)
- [🚀 What’s Next](#-whats-next)
- [📝 My Day 2 Notes](#-my-day-2-notes)

---

## 🎯 Objectives

End of this day, I will be able to:

- [ ] Understand **WAF internal architecture** and request lifecycle
- [ ] Classify WAFs by **deployment model**
- [ ] Explain **Positive vs Negative** security models
- [ ] Identify common WAFs by their fingerprints
- [ ] Understand **Signature / Anomaly / ML-based** detection models
- [ ] Set up **ModSecurity + OWASP CRS** Docker lab for hands-on practice

---

## ⏰ Time Breakdown

| Session | Topic | Duration |
|---|---|---:|
| 1 | WAF Architecture Deep Dive | 45 min |
| 2 | WAF Types & Deployment Models | 45 min |
| 3 | Detection Mechanisms | 45 min |
| 4 | Hands-on Lab — WAF Behavior Analysis | 60 min |
| 5 | Mind-Map Creation + Notes | 30 min |
| **Total** |  | **~3.5 hours** |

---

## 🏗️ Session 1: WAF Architecture Deep Dive

### What is a WAF?

Ekta **WAF** ba **Web Application Firewall** holo web application er samne boshano ekta security layer.  
Eta incoming HTTP/HTTPS request inspect kore suspicious or malicious traffic detect, block, challenge, or log korte pare.

```text
[User / Tester]
      ↓
[Internet]
      ↓
[WAF Layer]  ← Inspects request
      ↓
[Web Server]
      ↓
[Application]
      ↓
[Database]
```

---

## WAF Decision Flow

```text
Request arrives
      ↓
1. Parse HTTP request
   - Headers
   - Body
   - URL
   - Cookies
      ↓
2. Normalize request
   - URL decode
   - Lowercase
   - Unescape characters
      ↓
3. Apply rules
   - Signature matching
   - Keyword lists
   - Behavioral analysis
   - Anomaly scoring
      ↓
4. Make decision
   - Allow
   - Block
   - Challenge
   - Log
      ↓
5. Forward to origin or return block page
```

> 💡 **Critical Insight:** WAF request er different parts parse kore rules apply kore. Tai request parsing, normalization, and backend behavior bujha important.

---

## Core Components of a Modern WAF

| Component | Function | Testing Focus |
|---|---|---|
| **Parser** | HTTP request decode kore | Parser differences |
| **Normalizer** | Encoding/case standardize kore | Normalization behavior |
| **Rule Engine** | Signature match kore | Rule behavior analysis |
| **Scoring Engine** | Anomaly score calculate kore | Threshold behavior |
| **Decision Module** | Block/Allow decide kore | Decision outcome |
| **Logging Module** | Events record kore | Rule ID and logs analysis |

---

## Rule Evaluation Order

Most WAFs generally follow this type of order:

1. **Whitelist rules** — trusted IPs, paths, or known safe traffic
2. **Blacklist rules** — known bad patterns
3. **Custom rules** — customer-defined rules
4. **Default OWASP CRS** — Core Rule Set
5. **Anomaly scoring threshold** check

> 🎯 Rule ordering bujhle kon request kon rule e trigger hocche seta better analyze kora jay.

---

## 🔑 Key Concept: Impedance Mismatch

```text
WAF decodes request
      ↓
WAF applies rules
      ↓
WAF forwards request to origin
      ↓
Origin server decodes request
      ↓
Application processes request
```

Jodi WAF and origin server request differently parse or decode kore, tahole behavior mismatch create hote pare.  
Ei concept ke bola hoy **Impedance Mismatch**.

---

## 🌐 Session 2: WAF Types & Deployment Models

---

## Classification 1: By Deployment

### 1. 🖥️ Network-Based WAF

Network-based WAF usually hardware appliance hisebe on-premise deploy kora hoy.

**Examples:**

- F5 BIG-IP ASM
- Citrix NetScaler
- Fortinet FortiWeb
- Barracuda

**Pros:**

- Low latency
- High performance
- Enterprise-grade control

**Cons:**

- Expensive
- Hard to scale
- Firmware and maintenance overhead

---

### 2. 💾 Host-Based WAF

Host-based WAF web server er sathe directly install kora hoy.

**Examples:**

- ModSecurity
- NAXSI
- Wallarm

**Pros:**

- Cheap or free
- Highly customizable
- Good for labs and self-hosted apps

**Cons:**

- Server resources consume kore
- Per-server configuration lagte pare

---

### 3. ☁️ Cloud-Based WAF

Cloud-based WAF third-party managed service hisebe kaj kore.

**Examples:**

- Cloudflare
- AWS WAF
- Akamai Kona
- Imperva Incapsula
- Sucuri
- Azure WAF

**Pros:**

- Easy deployment
- Auto-updates
- DDoS protection included
- Very common in real-world apps

**Cons:**

- Less low-level control
- Data privacy concern thakte pare
- Origin exposure risk thakte pare

---

## Classification 2: By Security Model

### 🟢 Positive Security Model

> “Only allow what I explicitly define as good.”

Example:

```text
Username field accepts only:
[a-zA-Z0-9]
```

**Pros:**

- More strict
- Lower false negatives

**Cons:**

- Higher false positives
- Legit traffic accidentally block hote pare

---

### 🔴 Negative Security Model

> “Block what I define as bad.”

Example:

```text
Block requests containing:
<script>
```

**Pros:**

- Easier to deploy
- Flexible for general traffic

**Cons:**

- Known-pattern based
- Unknown variations miss korte pare

---

### 🟡 Hybrid Security Model

Modern WAFs usually positive + negative model combine kore.

Example:

- Critical endpoints e strict allowlist
- General traffic e blacklist/signature rules
- Extra anomaly scoring layer

---

## Classification 3: By Intelligence Level

| Type | How It Works | Difficulty |
|---|---|---|
| **Signature-based** | Regex or pattern matching | Easy-Medium |
| **Anomaly-based** | Normal behavior theke deviation detect kore | Medium |
| **Heuristic-based** | Rule combinations + scoring | Medium |
| **ML/AI-based** | Classifier/model diye detect kore | Hard |

---

## Quick Comparison Matrix

| Feature | Network WAF | Host WAF | Cloud WAF |
|---|---|---|---|
| Cost | High | Low | Medium |
| Deployment | Complex | Medium | Easy |
| Scalability | Limited | Per-server | High |
| Updates | Manual | Manual | Automatic |
| Customization | Medium | High | Low-Medium |
| Common in Bug Bounty | Rare | Sometimes | Very Common |

> 🎯 Bug bounty te Cloud WAFs beshi dekha jay — Cloudflare, AWS WAF, Akamai, Imperva, Sucuri etc.

---

## 🔍 Session 3: Detection Mechanisms

---

## A. Signature-Based Detection

Signature-based WAF known attack patterns er database maintain kore.

```text
Incoming payload:
<script>alert(1)</script>

Rule:
Detect "<script>" pattern

Decision:
Block or log
```

### Example Variations for Lab Testing

```text
<script>alert(1)</script>
<svg onload=alert(1)>
<img src=x onerror=alert(1)>
```

> Use only local labs or authorized testing environments.

---

## B. Anomaly-Based Detection

Anomaly-based detection scoring model use kore.  
Request er suspicious element er upor score add hoy. Score threshold cross korle block hote pare.

### Example Scoring

```text
Request:
/search?q=' OR 1=1--

Possible scoring:
Single quote present       +2
SQL keyword "OR"           +3
Numeric comparison         +2
SQL comment "--"           +3
--------------------------------
Total                      10

Threshold                   5
Decision                    Block
```

### Key Idea

Payload or request behavior joto suspicious hobe, anomaly score toto increase korbe.

---

## C. ML/AI-Based Detection

ML/AI-based WAF traffic patterns classify korte trained models use kore.

**Examples:**

- AWS WAF Bot Control
- Cloudflare Bot Management
- Fastly Next-Gen WAF

**Strengths:**

- Unknown attack pattern detect korte pare
- Bot and behavior detection e strong

**Weaknesses:**

- False positives possible
- Model quality training data er upor depend kore
- Explainability sometimes hard

---

## OWASP Core Rule Set — CRS

OWASP CRS holo ekta widely used open-source WAF rule set.  
ModSecurity er sathe commonly use hoy.

---

## CRS Paranoia Levels

| PL | Description | False Positives | Strictness |
|---|---|---|---|
| **PL1** | Basic/default rules | Low | Low |
| **PL2** | More aggressive | Medium | Medium |
| **PL3** | Strict | High | High |
| **PL4** | Very strict | Very High | Very High |

---

## CRS Rule Categories

| Rule ID Range | Category |
|---|---|
| `911` | Method enforcement |
| `913` | Scanner detection |
| `920` | Protocol enforcement |
| `921` | Protocol attacks |
| `930` | LFI |
| `931` | RFI |
| `932` | RCE |
| `933` | PHP injection |
| `941` | XSS |
| `942` | SQLi |
| `943` | Session fixation |

---

## 🧪 Session 4: Hands-on Lab — WAF Behavior Analysis

> Lab activity gulo authorized local lab, test environment, or explicitly allowed targets e korba.

---

## Lab 1: WAF Fingerprinting with wafw00f

**Time:** 20 min

### Install wafw00f

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
wafw00f https://www.cloudflare.com
wafw00f -a https://example.com
wafw00f -l
wafw00f -v https://example.com
```

> ⚠️ Public websites e active testing korar age permission/scope check koro.

---

## Lab 2: Manual WAF Detection

**Time:** 20 min

### Test 1: Baseline

```bash
curl -v https://target.com/
```

Note:

- Server header
- Cookies
- Response time
- Status code

---

### Test 2: Lab Payload Response Analysis

```bash
curl -v "https://target.com/?q=<script>alert(1)</script>"
curl -v "https://target.com/?id=1' OR '1'='1"
curl -v "https://target.com/?cmd=;cat /etc/passwd"
```

Analyze response changes:

- Status code change?
- New headers?
- Block page HTML pattern?
- Response time anomaly?
- Cookie changes?
- Challenge page?

> Use these only on your local lab or authorized targets.

---

## Lab 3: Setup ModSecurity + OWASP CRS Locally

**Time:** 20 min

ModSecurity + OWASP CRS = personal WAF learning lab.

### Quick Docker Setup

```bash
docker run -d -p 8080:80 \
  -e PARANOIA=1 \
  -e BACKEND=http://example.com \
  --name modsec \
  owasp/modsecurity-crs:nginx
```

---

## Test It

### Should Pass

```bash
curl http://localhost:8080/
```

### Should Be Blocked

```bash
curl "http://localhost:8080/?test=<script>alert(1)</script>"
curl "http://localhost:8080/?id=1' OR '1'='1"
```

---

## Check Logs

```bash
docker logs modsec | grep "ModSecurity"
```

Detailed audit log:

```bash
docker exec modsec cat /var/log/modsec_audit.log
```

Logs e kon rule match holo, rule ID ki, and request er kon part trigger korlo — egulo note koro.

---

## Experiment: Change Paranoia Level

```bash
docker stop modsec && docker rm modsec
```

```bash
docker run -d -p 8080:80 \
  -e PARANOIA=3 \
  -e BACKEND=http://example.com \
  --name modsec \
  owasp/modsecurity-crs:nginx
```

Now same requests abar test koro and PL1 vs PL3 behavior compare koro.

---

## 📊 Top 10 WAF Fingerprint Reference

| # | WAF | Fingerprint Indicators |
|---:|---|---|
| 1 | **Cloudflare** | `Server: cloudflare`, `cf-ray`, `cf-cache-status` |
| 2 | **AWS WAF** | `x-amzn-*`, CloudFront headers |
| 3 | **Akamai Kona** | `AkamaiGHost`, `X-Akamai-*` |
| 4 | **Imperva Incapsula** | `X-Iinfo`, `incap_ses_*` |
| 5 | **Sucuri** | `X-Sucuri-ID`, `X-Sucuri-Cache` |
| 6 | **F5 BIG-IP ASM** | `BIGipServer`, `X-WA-Info` |
| 7 | **ModSecurity** | Generic `403/406`, audit log rule IDs |
| 8 | **Barracuda** | `barra_counter_session` |
| 9 | **Fastly / Signal Sciences** | Fastly-specific headers |
| 10 | **Azure WAF** | `x-azure-ref`, Azure-specific headers |

---

## 🗺️ Session 5: Mind-Map & Notes

### Create Your Master WAF Mind-Map

**Tool suggestions:**

- XMind
- Obsidian Canvas
- draw.io
- Miro

```text
                        [WAF LANDSCAPE]
                              |
        ------------------------------------------------
        |                      |                       |
  [Deployment]          [Security Model]          [Detection]
        |                      |                       |
   ------------          ----------------        ----------------
   |    |     |          |       |      |        |      |       |
 Cloud Host Network  Positive Negative Hybrid Signature Anomaly ML
   |
   ---------------------------
   |      |      |      |     |
Cloudflare AWS Akamai Imperva Sucuri
```

---

## Day 2 Notes Template

```markdown
# Day 02 — WAF Architecture & Detection

## Core Concepts Mastered

- [ ] WAF decision flow: parse → normalize → match → decide
- [ ] Deployment types: Network / Host / Cloud
- [ ] Security models: Positive / Negative / Hybrid
- [ ] Detection models: Signature / Anomaly / ML
- [ ] OWASP CRS paranoia levels

## Top WAFs Studied

Cloudflare — Fingerprint: _______  
ModSecurity — Fingerprint: _______  
AWS WAF — Fingerprint: _______  

## Lab Results

wafw00f detected WAFs on: _______  
ModSecurity Docker running: ✓ / ✗  
First blocked payload: _______  
CRS rules triggered: _______  

## Key Insight of the Day

The gap between WAF normalization and backend parsing can create different behavior.

## Questions for Further Research

- 
- 
- 
```

---

## 🏆 Day 2 Challenge

Complete all tasks to mark Day 2 done:

- [ ] Detect WAF on **5 different public websites** using passive methods
- [ ] Run ModSecurity Docker container locally with OWASP CRS
- [ ] Trigger at least **3 different CRS rules** and document rule IDs from logs
- [ ] Create WAF comparison table for minimum **5 WAFs**
- [ ] Build a mind-map covering architecture, types, and detection methods
- [ ] Experiment with **Paranoia Levels** — compare PL1 vs PL3
- [ ] Write a **200-word summary**: “How a WAF processes a malicious request”
- [ ] Push `Day-02.md` + mind-map screenshot to GitHub repo

---

## 📋 Cheat Sheet

---

## Quick WAF Detection Commands

```bash
# Passive fingerprinting
curl -sI https://target.com

# Headers and cookies
curl -sv https://target.com 2>&1 | grep -iE "server|cookie|x-"

# Tool-based detection
wafw00f -a https://target.com

# Manual response check — authorized targets only
curl "https://target.com/?q=<script>alert(1)</script>" -I

# Nmap WAF scripts — authorized targets only
nmap --script http-waf-detect,http-waf-fingerprint target.com
```

---

## ModSecurity Docker Commands

```bash
# Start with specific paranoia level
docker run -d -p 8080:80 \
  -e PARANOIA=1 \
  -e BACKEND=http://httpbin.org \
  --name modsec \
  owasp/modsecurity-crs:nginx
```

```bash
# Watch live logs
docker logs -f modsec
```

```bash
# Stop and remove
docker stop modsec && docker rm modsec
```

---

## WAF Identification Matrix

| Indicator | Possible WAF |
|---|---|
| `cf-ray`, `cf-cache-status` | Cloudflare |
| `X-Iinfo`, `incap_ses` | Imperva |
| `AkamaiGHost`, `ak_bmsc` | Akamai |
| `X-Sucuri-ID` | Sucuri |
| `AWSALB` + AWS-style 403 | AWS WAF |
| ModSecurity audit logs | ModSecurity |
| `BIGipServer`, `TS01xxxx` | F5 BIG-IP |

---

## CRS Rule Categories Quick Reference

| ID | Category |
|---|---|
| `941` | XSS |
| `942` | SQLi |
| `932` | RCE |
| `930` | LFI |
| `931` | RFI |

---

## ⚠️ Common Mistakes to Avoid

1. Only reading theory — hands-on with ModSecurity is mandatory
2. Using tools on out-of-scope targets
3. Ignoring block page details
4. Not saving CRS rule logs
5. Assuming all WAFs work the same
6. Skipping paranoia level experiments

---

## 📚 Resources

### Must-Read Repositories

- [0xInfection/Awesome-WAF](https://github.com/0xInfection/Awesome-WAF)
- [EnableSecurity/wafw00f](https://github.com/EnableSecurity/wafw00f)
- [Ekultek/WhatWaf](https://github.com/Ekultek/WhatWaf)
- [Bo0oM/WAF-bypass-Cheat-Sheet](https://github.com/Bo0oM/WAF-bypass-Cheat-Sheet)
- [coreruleset/coreruleset](https://github.com/coreruleset/coreruleset)

### Documentation

- [Cloudflare — What is a WAF?](https://www.cloudflare.com/learning/ddos/glossary/web-application-firewall-waf/)
- [OWASP CRS Documentation](https://coreruleset.org/docs/)
- [AWS WAF Developer Guide](https://docs.aws.amazon.com/waf/latest/developerguide/)

### Video

- Bypassing Modern WAFs — DEF CON talks
- Ivan Ristic’s ModSecurity talks

### Book

- _Web Application Defender’s Cookbook_ by Ryan Barnett

---

## ❓ Self-Check Questions

1. WAF request process korar time main steps ki ki?
2. Positive vs Negative security model — difference ki?
3. OWASP CRS paranoia level increase korle advantage and disadvantage ki?
4. Cloudflare vs ModSecurity architectural difference ki?
5. Ekta request e kivabe bujhbe kon WAF running ache?
6. Anomaly scoring model e threshold concept ki?
7. ML-based WAF signature-based WAF theke kivabe different?
8. Impedance mismatch behavior difference kivabe create kore?

✅ All 8 answered correctly? **Day 2 complete!**

---

## 🚀 What’s Next?

**Day 3 Preview:** WAF Detection & Fingerprinting Mastery

- Advanced fingerprinting techniques beyond wafw00f
- Nmap scripts for WAF detection
- Custom Python script for WAF profiling
- Cloud WAF behavior analysis
- Legal practice targets and lab workflow

---

## 📝 My Day 2 Notes

<!-- Fill in after completion -->

### WAFs Studied Today

| WAF | Type | Fingerprint | Confidence |
|---|---|---|---|
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

---

### ModSecurity Lab Results

| Payload | PL1 Result | PL3 Result | Rule ID |
|---|---|---|---|
|  |  |  |  |
|  |  |  |  |

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

- [ ] Install `wafw00f`
- [ ] Install `whatwaf`
- [ ] Keep ModSecurity Docker ready
- [ ] Review Day 1 and Day 2 notes

---

<p align="center">
  <strong>🎓 Day 2 Status:</strong> ⬜ In Progress / ✅ Complete<br>
  <em>“Know your enemy and know yourself; in a hundred battles you will never be defeated.” — Sun Tzu</em>
</p>

<p align="center">
  <a href="./Day-01.md">← Previous: Day 01</a> |
  <a href="./Day-03.md">Next: Day 03 →</a>
</p>
