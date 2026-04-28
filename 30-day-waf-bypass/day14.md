# 📝 Day 14 — End-to-End Practice + Professional Report Writing

> **Part of:** 15-Day WAF Bypass & Payload Crafting Mastery — Week 3  
> **Date:** Tuesday, April 28, 2026  
> **Difficulty:** ⭐⭐⭐⭐⭐ Professional  
> **Time Required:** 6–8 hours  
> **Focus:** Transform findings into accepted reports  

![Day](https://img.shields.io/badge/Day-14%2F15-purple)
![Status](https://img.shields.io/badge/Status-Professional-gold)
![Focus](https://img.shields.io/badge/Focus-Reports%20%2B%20Communication-critical)
![Skill](https://img.shields.io/badge/Skill-Bug%20Bounty%20Reporting-blue)

> ⚠️ **Ethical Use Only:**  
> This guide is for authorized bug bounty programs, legal penetration testing, private labs, and professional report-writing practice only.

---

## 📑 Table of Contents

- [💎 Why Reports Are Everything](#-why-reports-are-everything)
- [🎯 Objectives](#-objectives)
- [⏰ Time Breakdown](#-time-breakdown)
- [🎯 Session 1: Second Hunting Session](#-session-1-second-hunting-session)
- [📐 Session 2: Report Writing Architecture](#-session-2-report-writing-architecture)
- [📊 Session 3: CVSS Scoring Mastery](#-session-3-cvss-scoring-mastery)
- [🎬 Session 4: Creating Professional PoC](#-session-4-creating-professional-poc)
- [💬 Session 5: Triager Communication](#-session-5-triager-communication)
- [📖 Session 6: Real Report Analysis](#-session-6-real-report-analysis)
- [📋 Session 7: Report Templates Library](#-session-7-report-templates-library)
- [🏆 Day 14 Challenge](#-day-14-challenge)
- [📋 Master Cheat Sheets](#-master-cheat-sheets)
- [📚 Resources](#-resources)
- [❓ Self-Check Questions](#-self-check-questions)
- [🚀 What’s Next](#-whats-next)
- [📝 My Day 14 Notes](#-my-day-14-notes)

---

# 💎 Why Reports Are Everything

```text
┌────────────────────────────────────────────────────────┐
│  THE HIDDEN TRUTH OF BUG BOUNTY                        │
├────────────────────────────────────────────────────────┤
│  Two hunters find the SAME bug:                        │
│                                                        │
│  Hunter A: Bad report                                  │
│    → Rejected / Informative / $50                      │
│                                                        │
│  Hunter B: Professional report                         │
│    → Accepted as Critical / $5,000                     │
│                                                        │
│  SAME BUG. 100x DIFFERENCE. REPORT QUALITY.            │
└────────────────────────────────────────────────────────┘
```

## What Makes Reports Critical

| Factor | Impact on Outcome |
|---|---|
| Clarity | Triager understands the issue faster |
| Impact demonstration | Higher severity and stronger business case |
| Professional tone | Builds credibility and trust |
| Reproducibility | Easier triage and faster validation |
| Remediation suggestions | Shows expertise and helps engineering teams |

---

# 🎯 Objectives

By the end of this day, I will be able to:

- [ ] Conduct a **second full hunting session** using Day 13 lessons
- [ ] Write **professional-grade vulnerability reports**
- [ ] Calculate **accurate CVSS 3.1 scores**
- [ ] Create **clear PoC screenshots and videos**
- [ ] Handle **triager communication** professionally
- [ ] Build a reusable **report template library**
- [ ] Analyze **accepted public reports** for patterns

---

# ⏰ Time Breakdown

| Session | Topic | Duration |
|---|---|---:|
| 1 | Second Hunting Session | 90 min |
| 2 | Report Writing Architecture | 75 min |
| 3 | CVSS Scoring Mastery | 60 min |
| 4 | Creating Professional PoC | 60 min |
| 5 | Triager Communication | 60 min |
| 6 | Real Report Analysis | 60 min |
| 7 | Report Templates Library | 60 min |
| **Total** |  | **~7.5 hours** |

---

# 🎯 Session 1: Second Hunting Session

## Apply Day 13 Lessons

Use your Day 13 debrief to improve today’s hunt.

```markdown
## Day 13 Lessons → Day 14 Actions

Lesson 1: [What went wrong yesterday]
→ Today's adjustment: [What to do differently]

Lesson 2: [What worked well]
→ Today's amplification: [Do more of this]

Lesson 3: [New technique noticed]
→ Today's test: [Apply this technique]
```

---

## Quick Hunt Approach

Today is a focused **90-minute blitz**.

| Time | Task |
|---:|---|
| 0–15 min | Scope re-read + target selection |
| 15–30 min | Quick recon |
| 30–60 min | Deep dive into one feature |
| 60–75 min | Exploitation attempts |
| 75–90 min | Document findings or non-findings |

---

## Pick a Different Target

If Day 13 target was `X`, today try target `Y`.

Why:

- Fresh perspective
- Different tech stack
- Prevents tunnel vision
- Builds hunting breadth

---

## Focus on One Vulnerability Class

Pick one class for the full session.

Examples:

```text
Monday: XSS everywhere
Tuesday: IDOR everywhere
Wednesday: SSRF everywhere
Thursday: Auth issues everywhere
Friday: Business logic everywhere
```

> Specialists often find more bugs than generalists.

---

# 📐 Session 2: Report Writing Architecture

## Anatomy of a Perfect Report

Every strong report has **10 sections**.

```text
┌──────────────────────────────────────┐
│  1.  Title                           │
│  2.  Summary                         │
│  3.  Affected Asset                  │
│  4.  Severity / CVSS                 │
│  5.  Steps to Reproduce              │
│  6.  Proof of Concept                │
│  7.  Impact                          │
│  8.  Suggested Remediation           │
│  9.  References                      │
│  10. Timeline / Metadata             │
└──────────────────────────────────────┘
```

---

## 1. Title

### Formula

```text
[Vulnerability Type] in [Component] leads to [Impact]
```

### Weak Titles

```text
XSS found
Security issue
Critical bug
```

### Strong Titles

```text
Stored XSS in user profile bio field leads to account takeover
IDOR in /api/orders/{id} exposes all users' order history
SSRF via avatar URL parameter enables AWS metadata access
```

---

## 2. Summary

Keep the summary short: **2–3 sentences max**.

### Formula

```text
What happened + Where it happened + Why it matters
```

### Example

```text
A reflected XSS vulnerability exists in the search functionality at /search?q= due to improper output encoding of the q parameter. This allows an attacker to execute JavaScript in a victim’s browser through a crafted URL, potentially leading to session hijacking, phishing, or account takeover.
```

---

## 3. Affected Asset

Be specific and complete.

```markdown
## Affected Asset

URL: https://target.com/search  
Parameter: q  
Parameter Type: GET  
HTTP Method: GET  
Authentication Required: No  
Affected User Roles: All users who open a crafted link
```

---

## 4. Severity / CVSS

```markdown
## Severity

Severity: Medium  
CVSS 3.1 Score: 6.1  
CVSS Vector: CVSS:3.1/AV:N/AC:L/PR:N/UI:R/S:C/C:L/I:L/A:N  
CWE: CWE-79 — Cross-Site Scripting  
OWASP Top 10: A03:2021 — Injection
```

---

## 5. Steps to Reproduce

Steps should be:

- Numbered
- Specific
- Testable
- Easy to follow

```markdown
## Steps to Reproduce

1. Navigate to `https://target.com/`.
2. In the top navigation bar, locate the search input.
3. Enter the following payload:

   ```html
   <svg/onload=alert(document.domain)>
   ```

4. Press Enter or click the Search button.
5. Observe the browser alert displaying the target domain.

Alternative direct URL:

```text
https://target.com/search?q=%3Csvg%2Fonload%3Dalert(document.domain)%3E
```
```

---

## 6. Proof of Concept

Include as many of these as possible:

- Screenshots
- Short video recording
- Raw HTTP request and response
- Working PoC URL
- Clear notes explaining expected behavior

---

## 7. Impact

Do not only say:

```text
This is XSS.
```

Explain the real-world damage.

```markdown
## Impact

This reflected XSS vulnerability may allow:

### Immediate Impact

- Session hijacking if sensitive cookies are accessible
- Credential phishing through injected fake forms
- CSRF token theft if tokens are exposed in the DOM
- Page manipulation and social engineering attacks

### Attack Scenario

1. Attacker crafts a malicious URL.
2. Attacker sends the URL to a logged-in victim.
3. Victim opens the URL.
4. JavaScript executes in the victim’s browser.
5. Attacker performs actions in the victim’s session.

### Business Impact

- Customer trust damage
- Potential compliance concerns
- Account compromise risk
- Reputation loss
```

---

## 8. Suggested Remediation

Always include remediation.

```markdown
## Suggested Remediation

### Short-Term Fix

- Apply context-aware output encoding to the affected parameter.
- Add a restrictive Content Security Policy.
- Set session cookies with `HttpOnly`, `Secure`, and `SameSite` attributes.

Example CSP:

```http
Content-Security-Policy: default-src 'self'; script-src 'self'
```

### Long-Term Fix

- Use template engines with auto-escaping.
- Implement allowlist-based input validation.
- Add security tests to CI/CD.
- Train developers on secure output encoding.

### Code Example

Vulnerable:

```javascript
document.getElementById("results").innerHTML = searchQuery;
```

Safe:

```javascript
document.getElementById("results").textContent = searchQuery;
```
```

---

## 9. References

```markdown
## References

- OWASP XSS Prevention Cheat Sheet
- PortSwigger Web Security Academy — Reflected XSS
- CWE-79
- Content Security Policy documentation
```

---

## 10. Timeline

```markdown
## Timeline

2026-04-28 14:32 UTC — Vulnerability discovered  
2026-04-28 15:00 UTC — Report submitted  
[To be updated] — Triage status  
[To be updated] — Resolution status
```

---

# 📊 Session 3: CVSS Scoring Mastery

## What is CVSS?

CVSS means **Common Vulnerability Scoring System**.

```text
0.0     → None
0.1–3.9 → Low
4.0–6.9 → Medium
7.0–8.9 → High
9.0–10  → Critical
```

---

## CVSS 3.1 Base Metrics

```text
Attack Vector:
- Network
- Adjacent
- Local
- Physical

Attack Complexity:
- Low
- High

Privileges Required:
- None
- Low
- High

User Interaction:
- None
- Required

Scope:
- Unchanged
- Changed

Confidentiality:
- None
- Low
- High

Integrity:
- None
- Low
- High

Availability:
- None
- Low
- High
```

---

## Common Vulnerability Scores

| Vulnerability | Typical CVSS | Range |
|---|---:|---:|
| Reflected XSS | 6.1 | 5.4–6.5 |
| Stored XSS | 7.4 | 6.5–8.8 |
| DOM XSS | 6.1 | 5.0–7.0 |
| SQLi unauthenticated | 9.8 | 8.5–10.0 |
| SQLi authenticated | 8.8 | 7.5–9.5 |
| SSRF internal | 7.5 | 6.5–8.5 |
| SSRF to cloud metadata | 9.8 | 8.5–10.0 |
| RCE unauthenticated | 9.8 | 9.0–10.0 |
| RCE authenticated | 8.8 | 8.0–9.5 |
| IDOR data read | 6.5 | 5.0–7.5 |
| IDOR data modify | 8.1 | 7.0–9.0 |
| Auth bypass | 9.1 | 7.5–10.0 |
| CSRF | 6.5 | 5.0–8.0 |
| Open redirect | 6.1 | 4.0–6.5 |
| Information disclosure | 5.3 | 4.0–7.5 |

---

## CVSS Calculator

Official calculator:

```text
https://www.first.org/cvss/calculator/3.1
```

---

## CVSS Script

Save as:

```text
~/waf-lab/scripts/cvss_calc.py
```

```python
#!/usr/bin/env python3
"""
Quick CVSS 3.1 calculator for learning and report drafting.
"""

from math import ceil


def round_up_1_decimal(value: float) -> float:
    return ceil(value * 10) / 10.0


def calculate_cvss(av: str, ac: str, pr: str, ui: str, s: str, c: str, i: str, a: str) -> float:
    """Calculate CVSS 3.1 base score."""

    av_w = {"N": 0.85, "A": 0.62, "L": 0.55, "P": 0.20}
    ac_w = {"L": 0.77, "H": 0.44}
    pr_u = {"N": 0.85, "L": 0.62, "H": 0.27}
    pr_c = {"N": 0.85, "L": 0.68, "H": 0.50}
    ui_w = {"N": 0.85, "R": 0.62}
    cia_w = {"N": 0.0, "L": 0.22, "H": 0.56}

    pr_w = pr_c if s == "C" else pr_u

    iss = 1 - ((1 - cia_w[c]) * (1 - cia_w[i]) * (1 - cia_w[a]))

    if s == "U":
        impact = 6.42 * iss
    else:
        impact = 7.52 * (iss - 0.029) - 3.25 * pow(iss - 0.02, 15)

    exploitability = 8.22 * av_w[av] * ac_w[ac] * pr_w[pr] * ui_w[ui]

    if impact <= 0:
        return 0.0

    if s == "U":
        base = min(impact + exploitability, 10)
    else:
        base = min(1.08 * (impact + exploitability), 10)

    return round_up_1_decimal(base)


def severity(score: float) -> str:
    if score == 0:
        return "None"
    if score < 4:
        return "Low"
    if score < 7:
        return "Medium"
    if score < 9:
        return "High"
    return "Critical"


def main() -> None:
    print("CVSS 3.1 Quick Calculator")
    print("=" * 40)

    # Example: Reflected XSS
    av = "N"
    ac = "L"
    pr = "N"
    ui = "R"
    s = "C"
    c = "L"
    i = "L"
    a = "N"

    score = calculate_cvss(av, ac, pr, ui, s, c, i, a)
    vector = f"CVSS:3.1/AV:{av}/AC:{ac}/PR:{pr}/UI:{ui}/S:{s}/C:{c}/I:{i}/A:{a}"

    print("\nExample: Reflected XSS")
    print(f"Vector:   {vector}")
    print(f"Score:    {score}")
    print(f"Severity: {severity(score)}")


if __name__ == "__main__":
    main()
```

---

# 🎬 Session 4: Creating Professional PoC

## Types of PoC

| Type | Use Case |
|---|---|
| Screenshots | Minimum proof for most reports |
| Video recording | Best for impact and reproducibility |
| Interactive PoC URL | Strong proof for browser-based issues |
| Raw HTTP | Useful for technical triagers |

---

## Screenshot Best Practices

### Do

- Capture the full browser window
- Show the URL bar clearly
- Highlight important areas
- Include timestamps when useful
- Number screenshots clearly

### Do Not

- Crop too tightly
- Show personal information
- Use low-resolution images
- Add unnecessary screenshots

---

## Video Recording Tools

| Tool | Platform | Free |
|---|---|---|
| OBS Studio | All | ✅ |
| Loom | Web | Limited free |
| ShareX | Windows | ✅ |
| Kap | Mac | ✅ |
| Peek | Linux | ✅ |
| asciinema | Terminal | ✅ |

---

## Perfect PoC Video Structure

```text
0:00–0:05  Show target URL
0:05–0:15  Show normal behavior
0:15–0:30  Inject payload / perform action
0:30–0:45  Show exploitation
0:45–0:60  Show impact
```

## Video Tips

- Keep it under 60 seconds
- Use 1080p resolution if possible
- Add text annotations if helpful
- Avoid voice unless necessary
- Keep desktop clean and private

---

## Interactive PoC URL

```markdown
## Interactive PoC

Open this URL in an incognito/private window:

```text
https://target.com/search?q=%3Csvg%2Fonload%3Dalert(%22XSS-PoC%22)%3E
```

Expected behavior:

```text
An alert box displays: XSS-PoC
```
```

---

## Raw HTTP PoC

```markdown
## Raw HTTP Request

```http
GET /search?q=%3Csvg%2Fonload%3Dalert%28document.domain%29%3E HTTP/1.1
Host: target.com
User-Agent: Mozilla/5.0
Accept: text/html,application/xhtml+xml
Cookie: session=<REDACTED>
```

## Raw HTTP Response

```http
HTTP/1.1 200 OK
Server: nginx
Content-Type: text/html; charset=UTF-8

<html>
  <body>
    <div class="search-results">
      Results for: <svg/onload=alert(document.domain)>
    </div>
  </body>
</html>
```

Note: The payload is reflected without proper encoding.
```

---

# 💬 Session 5: Triager Communication

## Professional Response Rules

- Respond within **24 hours**
- Stay polite and concise
- Provide evidence when asked
- Do not message daily for updates
- Wait at least **1 week** before a polite follow-up

---

## Scenario 1: Needs More Information

### Weak Response

```text
What more do you need? It's obvious.
```

### Strong Response

```text
Thank you for the review. I’m happy to elaborate on the impact.

Specifically, this vulnerability allows:

1. [Impact detail 1]
2. [Impact detail 2]

I’ve also added a supplementary PoC showing the issue more clearly.

Please let me know what other information would be helpful.
```

---

## Scenario 2: Marked as Duplicate

### Weak Response

```text
Prove it. Show me the original report.
```

### Strong Response

```text
Thank you for the update. I understand this is a duplicate.

If possible, could you share the approximate date of the original report so I can improve my future testing approach?

I appreciate the transparency and look forward to continuing to contribute to the program.
```

---

## Scenario 3: Marked as Informative

### Weak Response

```text
This is clearly a vulnerability. You are being unfair.
```

### Strong Response

```text
Thank you for the review.

Could you help me understand why this is not considered within bounty scope? I want to calibrate future submissions to better align with your program criteria.

I appreciate your guidance.
```

---

## Scenario 4: Severity Disagreement

### Weak Response

```text
I will disclose this publicly if you do not pay.
```

### Strong Response

```text
Thank you for the review. I’d like to respectfully request reconsideration based on the following:

1. Attack vector: [Explain]
2. Scope impact: [Explain]
3. CVSS calculation: [Show vector]
4. Similar accepted public reports: [If available]

I defer to your final decision, but I wanted to provide additional context.
```

---

## Red Lines

Never:

- Threaten public disclosure
- Use abusive language
- Spam messages
- Demand a specific bounty amount
- Compare aggressively with other programs
- Ask for status every day
- Publicly post details before permission

---

# 📖 Session 6: Real Report Analysis

## Analyze 3 Accepted Reports

Visit:

```text
https://hackerone.com/hacktivity
```

Find 3 disclosed reports with strong writeups.

---

## Analysis Framework

```markdown
# Report Analysis: [Title]

## Metadata

Program:  
Bounty:  
Severity:  

## What Made This Report Great

- 
- 
- 

## Title Analysis

Length:  
Specificity:  
Impact mentioned: yes / no  

## Summary Analysis

Length:  
Clear problem statement: yes / no  

## PoC Quality

Screenshots: yes / no  
Video: yes / no  
Raw HTTP: yes / no  
Interactive URL: yes / no  

## Impact Section

Attack scenario clear: yes / no  
Business impact mentioned: yes / no  
Quantified impact: yes / no  

## What I Will Adopt

- 
- 
- 
```

---

## Known-Good Report Sources

Search for disclosed reports by:

- `@frans`
- `@jobert`
- Sam Curry
- PortSwigger researchers
- High / Critical severity reports in Hacktivity

Patterns you should notice:

- Clear title
- Strong PoC
- Reproducible steps
- Detailed impact
- Suggested remediation
- Professional tone

---

# 📋 Session 7: Report Templates Library

## Create Your Template Folder

```bash
mkdir -p ~/WAF-Bypass-30-Days/report-templates
cd ~/WAF-Bypass-30-Days/report-templates
```

---

## Template 1: `reflected-xss.md`

```markdown
# Reflected XSS in [ENDPOINT] via [PARAMETER]

## Summary

A reflected Cross-Site Scripting vulnerability exists in [ENDPOINT] due to improper output encoding of the [PARAMETER] parameter. An attacker can craft a malicious URL that executes JavaScript in a victim’s browser context.

## Affected Asset

URL: [FULL_URL]  
Parameter: [PARAM_NAME]  
Parameter Type: [GET / POST / Header]  
HTTP Method: [METHOD]  
Authentication Required: [Yes / No]  
Affected Users: [All users / Authenticated users / Specific role]

## Severity

Severity: Medium  
CVSS 3.1: 6.1  
Vector: CVSS:3.1/AV:N/AC:L/PR:N/UI:R/S:C/C:L/I:L/A:N  
CWE: CWE-79  
OWASP: A03:2021 — Injection  

## Steps to Reproduce

1. [Step 1]
2. [Step 2]
3. [Step 3]
4. [Verification step]

## Proof of Concept

Payload:

```html
[PAYLOAD]
```

Direct URL:

```text
[FULL_POC_URL]
```

Screenshots:

```text
[Add screenshot links]
```

Video:

```text
[Add video link]
```

## Impact

An attacker may be able to:

- Execute JavaScript in a victim’s browser
- Perform phishing attacks
- Modify page content
- Access exposed tokens or data in the DOM
- Abuse authenticated user actions depending on context

## Attack Scenario

1. Attacker crafts a malicious URL.
2. Victim opens the URL while authenticated.
3. Payload executes in the victim’s browser.
4. Attacker performs actions depending on browser/session exposure.

## Remediation

### Immediate Fix

- HTML-encode the affected parameter before reflecting it.
- Implement a restrictive Content Security Policy.
- Set `HttpOnly`, `Secure`, and `SameSite` attributes on cookies.

### Long-Term Fix

- Use auto-escaping template engines.
- Add security tests in CI/CD.
- Train developers on context-aware output encoding.

## References

- OWASP XSS Prevention Cheat Sheet
- PortSwigger XSS Academy
- CWE-79

## Timeline

[DATE]: Vulnerability discovered  
[DATE]: Report submitted  
```

---

## Template 2: `idor.md`

```markdown
# IDOR in [ENDPOINT] allows [IMPACT]

## Summary

An Insecure Direct Object Reference vulnerability in [ENDPOINT] allows authenticated users to access or modify data belonging to other users by manipulating the [ID_PARAMETER] parameter. This breaks the application’s authorization model.

## Affected Asset

URL: [ENDPOINT]  
Parameter: [ID_PARAMETER]  
Method: [METHOD]  
Authentication: Required  
Access Control: Missing or broken  

## Severity

Severity: High  
CVSS 3.1: 7.5  
Vector: CVSS:3.1/AV:N/AC:L/PR:L/UI:N/S:U/C:H/I:H/A:N  
CWE: CWE-639  

## Steps to Reproduce

### Setup

1. Create two accounts: User A and User B.
2. Log in as User A.
3. Note User A’s ID: [ID_A].
4. Log in as User B.
5. Note User B’s ID: [ID_B].

### Exploitation

1. Log in as User A.
2. Navigate to [USER_A_RESOURCE].
3. Intercept the request in Burp Suite.
4. Modify [ID_PARAMETER] from [ID_A] to [ID_B].
5. Forward the request.
6. Observe that User B’s data is returned.

## Proof of Concept

```text
[Add screenshots and raw HTTP request/response]
```

## Impact

- Unauthorized access to user data
- Data modification or deletion across accounts
- PII exposure
- Compliance risk
- Loss of user trust

## Scope of Impact

Estimated affected users: [NUMBER / All users]  
Data exposed: [LIST DATA TYPES]  

## Remediation

- Implement server-side authorization checks for every resource.
- Use indirect references where appropriate.
- Apply least privilege.
- Add logging for unusual access patterns.
- Add tests for horizontal privilege escalation.

## References

- OWASP IDOR
- CWE-639
```

---

## Template 3: `ssrf.md`

```markdown
# SSRF in [ENDPOINT] allows access to [INTERNAL SERVICE / METADATA]

## Summary

A Server-Side Request Forgery vulnerability in [ENDPOINT] allows the server to issue HTTP requests to attacker-controlled destinations. Depending on network access, this may expose internal services or cloud metadata endpoints.

## Affected Asset

URL: [ENDPOINT]  
Parameter: [URL_PARAMETER]  
Method: [METHOD]  
Authentication Required: [Yes / No]  

## Severity

Severity: [High / Critical]  
CVSS 3.1: [SCORE]  
Vector: [VECTOR]  
CWE: CWE-918  

## Steps to Reproduce

1. Authenticate if required.
2. Navigate to [FEATURE].
3. Submit the URL parameter with a controlled callback URL:

```text
[PARAMETER]=http://[COLLABORATOR_URL]
```

4. Observe DNS or HTTP interaction.
5. Test access to permitted internal proof targets only.

## Proof of Concept

### Payload 1: Basic SSRF Confirmation

```text
[PARAMETER]=http://[COLLABORATOR_URL]
```

Result:

```text
HTTP/DNS interaction received.
```

### Payload 2: Internal Reachability Check

```text
[PARAMETER]=http://localhost:8080/
[PARAMETER]=http://127.0.0.1:8080/
```

### Payload 3: Metadata Endpoint Check

```text
[PARAMETER]=http://169.254.169.254/latest/meta-data/
```

> Redact sensitive information. Do not use extracted credentials.

## Impact

- Internal service exposure
- Cloud metadata exposure
- Potential credential disclosure
- Internal network reconnaissance
- Lateral movement risk

## Remediation

- Validate URLs with strict allowlists.
- Block cloud metadata endpoints from application servers.
- Use IMDSv2 where applicable.
- Restrict outbound egress.
- Apply least-privilege IAM roles.
- Log and alert on unusual outbound requests.

## References

- OWASP SSRF
- CWE-918
- AWS IMDSv2 documentation
```

---

## Build Templates For

- [ ] Reflected XSS
- [ ] Stored XSS
- [ ] DOM XSS
- [ ] SQLi time-based
- [ ] SQLi union-based
- [ ] IDOR read
- [ ] IDOR write
- [ ] SSRF
- [ ] Open Redirect
- [ ] CSRF
- [ ] XXE
- [ ] RCE
- [ ] Auth Bypass
- [ ] Information Disclosure
- [ ] Business Logic

---

# 🏆 Day 14 Challenge

Mark Day 14 complete after:

- [ ] Second 90-minute hunting session completed
- [ ] 10 report templates built
- [ ] CVSS calculator working locally
- [ ] 1 professional report drafted
- [ ] 3 accepted HackerOne reports analyzed
- [ ] Video recording tool installed and tested
- [ ] Practice PoC video created
- [ ] Response templates saved for triager scenarios
- [ ] Report templates pushed to GitHub

---

# 📋 Master Cheat Sheets

## Cheat Sheet 1: Report Quality Checklist

```text
Before submitting:

[ ] Title has vuln type + location + impact
[ ] Summary is 2–3 sentences
[ ] Steps are numbered and specific
[ ] Screenshots are included
[ ] Video PoC included for important reports
[ ] CVSS score and vector included
[ ] Impact explains real-world damage
[ ] Remediation suggestions included
[ ] References added
[ ] Professional tone throughout
[ ] No typos or grammar mistakes
[ ] Reproduced at least 3 times
```

---

## Cheat Sheet 2: CVSS Quick Guide

```text
Remote + unauthenticated + no UI + RCE        → 9.8–10.0 Critical
Remote + authenticated + no UI + RCE          → 8.8 High
Remote + unauthenticated + UI + XSS           → 6.1 Medium
Remote + authenticated + IDOR read            → 6.5 Medium
Remote + authenticated + IDOR modify          → 8.1 High
Remote + unauthenticated + SSRF cloud metadata → 9.8 Critical
Remote + unauthenticated + SQLi               → 9.8 Critical
```

---

## Cheat Sheet 3: Triager Communication

### Do

```text
Respond within 24 hours
Use professional tone
Provide more context when asked
Respect final decisions
Ask politely for clarification
```

### Do Not

```text
Threaten disclosure
Demand a specific bounty
Compare aggressively with other programs
Spam messages
Use rude language
```

---

# 📚 Resources

## Report Writing

- [HackerOne Disclosure Guidelines](https://docs.hackerone.com/hackers/disclosure-guidelines.html)
- [Bugcrowd — How to Write a Great Vulnerability Report](https://www.bugcrowd.com/blog/how-to-write-a-great-vulnerability-report/)
- [HackerOne Hacktivity](https://hackerone.com/hacktivity)

## CVSS Tools

- [CVSS Calculator](https://www.first.org/cvss/calculator/3.1)
- [CVSS Specification](https://www.first.org/cvss/specification-document)

## PoC Creation

- [OBS Studio](https://obsproject.com/)
- [asciinema](https://asciinema.org/)
- [Loom](https://loom.com/)

## Communication

- [HackerOne Bug Bounty Best Practices](https://www.hackerone.com/resources/reporting/bug-bounty-program-best-practices)

---

# ❓ Self-Check Questions

1. What are the 10 sections of a perfect report?
2. How do you structure a compelling vulnerability title?
3. What should a good Summary section contain?
4. What are the 8 CVSS base metrics?
5. What is the typical CVSS score for Reflected XSS?
6. When should you include a video PoC instead of only screenshots?
7. How should you respond to a Duplicate verdict?
8. What is the number one rule of triager communication?
9. Why should you include remediation suggestions?
10. What is the difference between Informative and Not Applicable?

✅ All 10 answered confidently? **Day 14 complete!**

---

# 🚀 What’s Next?

**Day 15 Preview:** Portfolio, Publication, Next 30 Days

- Publish your GitHub repo professionally
- Write your first public blog post
- Build your hunter brand
- Plan the next 30 days of skill development
- Explore certification pathways
- Review career opportunities

---

# 📝 My Day 14 Notes

## Second Hunting Session

```text
Target:
Duration:
Focus vulnerability class:
Findings:
Lessons:
```

---

## Templates Built

- [ ] Reflected XSS
- [ ] Stored XSS
- [ ] DOM XSS
- [ ] IDOR
- [ ] SSRF
- [ ] SQLi
- [ ] Open Redirect
- [ ] CSRF
- [ ] XXE
- [ ] RCE

---

## Reports Analyzed

| # | Source | Severity | Key Takeaway |
|---:|---|---|---|
| 1 |  |  |  |
| 2 |  |  |  |
| 3 |  |  |  |

---

## Professional Report Drafted

```text
Bug class:
CVSS calculated:
Report sections complete: __ / 10
PoC included: yes / no
Video included: yes / no
```

---

## Video PoC Practice

```text
Tool used:
Duration:
Comfortable with tool: yes / no
```

---

<p align="center">
  <strong>🎓 Day 14 Status:</strong> ⬜ In Progress / ✅ Complete<br>
  <em>“A mediocre bug with great reporting beats a great bug with mediocre reporting.”</em>
</p>

<p align="center">
  <a href="./Day-13.md">← Previous: Day 13</a> |
  <a href="./Day-15.md">Next: Day 15 →</a>
</p>
