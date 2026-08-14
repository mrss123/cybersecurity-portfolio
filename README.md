# 🛡️ Cybersecurity Portfolio

### Yishak Abrham · Offensive Security · Application Security · Network Security · Security Engineering

> A living technical record of security research, penetration-testing practice, security tooling, CTFs, labs, vulnerability analysis, and defensive engineering.

This repository documents **what I have actually investigated, built, tested, broken, and learned** while developing as a cybersecurity engineer.

It is not intended to be a collection of copied commands or generic cybersecurity notes.

The objective is to preserve the **reasoning behind security work**:

```text
RECON
  ↓
ENUMERATION
  ↓
THREAT MODEL
  ↓
HYPOTHESIS
  ↓
TEST
  ↓
EXPLOIT / VALIDATE
  ↓
IMPACT
  ↓
REMEDIATION
  ↓
RETEST
  ↓
DOCUMENT
```

---

# 01 · What This Repository Is

This repository is my **security engineering laboratory and evidence archive**.

It contains practical work across:

* Offensive security
* Web application security
* Network security
* Vulnerability analysis
* Security automation
* Linux security
* CTFs and security labs
* Reconnaissance
* Authentication and authorization testing
* Security tooling
* Defensive concepts
* Security research notes
* Lessons learned from failed experiments

The emphasis is on **hands-on understanding**.

A tool command is not considered the result.

Understanding **why the command matters, what it reveals, what can be attacked, and how the exposure can be mitigated** is the result.

---

# 02 · Repository Map

```text
cybersecurity-portfolio/
│
├── tools/
│   ├── nmap/
│   ├── burp-suite/
│   ├── wireshark/
│   └── hydra/
│
├── labs/
│   ├── tryhackme/
│   └── hackthebox/
│
├── scripts/
│   ├── bash/
│   └── python/
│
├── writeups/
│   ├── reconnaissance/
│   ├── web-security/
│   ├── network-security/
│   ├── privilege-escalation/
│   └── exploitation/
│
└── blog-style-learnings/
```

The repository will evolve as the scope of my security work expands.

---

# 03 · Security Domains

## 🌐 Web Application Security

Areas explored include:

* Authentication
* Authorization
* Session management
* Input validation
* SQL injection
* Access-control vulnerabilities
* API security
* HTTP request manipulation
* Security headers
* Parameter tampering
* Information disclosure
* Business-logic vulnerabilities
* File and path handling
* Client/server trust boundaries

Primary tooling:

```text
Burp Suite
SQLmap
Browser DevTools
Python
curl
```

---

## 🖧 Network Security

Practical work includes:

* Network reconnaissance
* Host discovery
* Port scanning
* Service enumeration
* Traffic inspection
* Protocol analysis
* Network interception
* ARP-based attacks in controlled environments
* DNS analysis
* Network exposure assessment

Primary tooling:

```text
Nmap
Wireshark
Bettercap
Netcat
Linux networking utilities
```

---

## 🐧 Linux Security

Areas of investigation include:

* File permissions
* Users and groups
* Processes
* Services
* Network sockets
* SSH
* SUID/SGID
* Cron jobs
* Environment variables
* Privilege boundaries
* Misconfiguration
* Enumeration methodology

The objective is to understand Linux from both an **administrator's and attacker's perspective**.

---

# 04 · Tooling

Tools are organized by the problem they help solve rather than treated as a checklist of technologies.

| Category                 | Tools              |
| ------------------------ | ------------------ |
| Reconnaissance           | Nmap, theHarvester |
| Web Security             | Burp Suite, SQLmap |
| Network Analysis         | Wireshark          |
| Network Testing          | Bettercap          |
| Credential Testing       | Hydra              |
| Vulnerability Assessment | Nessus             |
| Operating System         | Kali Linux / Linux |
| Automation               | Python, Bash       |
| Version Control          | Git / GitHub       |

### Important distinction

Knowing how to execute:

```bash
nmap -sV target
```

is basic tool usage.

Being able to explain:

```text
What did I discover?
Why is the service exposed?
What version is running?
Is the version vulnerable?
Can the vulnerability actually be exploited?
What privileges would exploitation provide?
What is the business impact?
How should it be remediated?
How can I verify the remediation?
```

is security analysis.

This repository focuses on the second.

---

# 05 · Penetration Testing Methodology

For practical assessments, I use a structured lifecycle.

## Reconnaissance

Understand the target before interacting aggressively with it.

```text
Scope
 ↓
Assets
 ↓
Attack Surface
 ↓
Technologies
 ↓
Potential Entry Points
```

Typical questions:

* What exists?
* What is exposed?
* What technologies are present?
* What services are reachable?
* What information is publicly available?
* What should not be exposed?

---

## Enumeration

Move from discovery to understanding.

Examples:

```text
Open port
    ↓
Service
    ↓
Version
    ↓
Configuration
    ↓
Potential weakness
```

Enumeration is where broad reconnaissance becomes a concrete attack hypothesis.

---

## Vulnerability Analysis

A scanner finding is treated as a **lead**, not automatically as a confirmed vulnerability.

For each interesting finding:

```text
Finding
 ↓
Reproduce
 ↓
Understand Root Cause
 ↓
Determine Preconditions
 ↓
Determine Impact
 ↓
Validate Exploitability
```

---

## Exploitation

Where authorized and appropriate, exploitation is used to demonstrate the practical security impact.

The objective is **controlled validation**, not unnecessary damage.

---

## Remediation

Every meaningful vulnerability should answer:

> How can this actually be fixed?

Possible remediation layers include:

* Application code
* Configuration
* Authentication
* Authorization
* Network segmentation
* Access controls
* Secrets management
* Patch management
* Monitoring
* Architectural changes

---

## Retesting

A vulnerability is not considered closed simply because a configuration changed.

The final step is:

```text
Original Finding
       ↓
Remediation
       ↓
Repeat Original Test
       ↓
Expected Secure Behavior
```

---

# 06 · Writeup Standard

Security writeups in this repository aim to follow a consistent structure.

```text
# Finding

## Executive Summary

What was discovered?

## Environment

What system/lab was tested?

## Scope

What was authorized?

## Attack Surface

What was exposed?

## Enumeration

What was discovered?

## Vulnerability

What security property failed?

## Exploitation

How was the vulnerability validated?

## Evidence

What proves the finding?

## Impact

What could an attacker achieve?

## Root Cause

Why did the vulnerability exist?

## Remediation

How should it be fixed?

## Retest

Does the remediation work?

## Lessons Learned

What changed in my understanding?
```

This structure is designed to make a writeup useful to someone who has to **defend the system**, not just reproduce the attack.

---

# 07 · Evidence Over Claims

A central principle of this portfolio is:

> **Show the evidence.**

Instead of writing:

```text
The server was vulnerable.
```

I want the writeup to show:

```text
1. What was observed
2. How it was reproduced
3. Why it represents a vulnerability
4. What privileges or data were affected
5. What an attacker would need
6. How it can be mitigated
7. Whether the mitigation was retested
```

Where appropriate, evidence may include:

* Terminal output
* HTTP requests/responses
* Packet captures
* Screenshots
* Source-code snippets
* Logs
* Reproduction steps
* Vulnerability timelines
* Architecture diagrams

Sensitive credentials, tokens, personal information, or unauthorized system data will not be published.

---

# 08 · Security Research Mindset

I approach security problems using several questions.

### Asset

**What are we protecting?**

### Trust Boundary

**Where does trusted data become untrusted?**

### Entry Point

**Where can an attacker interact with the system?**

### Assumption

**What does the developer or administrator assume cannot happen?**

### Violation

**Can that assumption be broken?**

### Impact

**What happens if it is broken?**

### Control

**What security mechanism should prevent it?**

### Verification

**Can the control actually be bypassed?**

This turns vulnerability hunting from:

```text
"Which exploit should I try?"
```

into:

```text
"What security assumption exists here,
and can I violate it?"
```

---

# 09 · Security Automation

Manual testing does not scale.

The `scripts/` directory contains security-oriented automation written primarily in:

```text
Python
Bash
```

Typical automation goals include:

* Reconnaissance
* Enumeration
* Log processing
* Repetitive testing
* Data extraction
* Security checks
* Result normalization
* Reporting

The purpose is not to automate everything.

It is to automate **repeatable work**, allowing more time for analysis.

---

# 10 · Labs

The laboratory section contains controlled environments used to develop practical skills.

### TryHackMe

Used for structured hands-on learning across:

* Networking
* Linux
* Web security
* Enumeration
* Privilege escalation
* Security fundamentals

### Hack The Box

Used for deeper offensive-security practice involving:

* Reconnaissance
* Enumeration
* Web exploitation
* Network services
* Privilege escalation
* Attack-chain reasoning

Writeups prioritize **methodology and understanding** rather than simply publishing answers.

---

# 11 · Learning Record

The `blog-style-learnings/` directory exists for something that is often missing from technical portfolios:

## What went wrong?

Security engineering involves failed assumptions, incomplete enumeration, incorrect hypotheses, broken scripts, unexpected behavior, and dead ends.

Those are valuable.

A learning entry may document:

```text
Initial assumption
        ↓
Attempt
        ↓
Failure
        ↓
Investigation
        ↓
Correct understanding
        ↓
Improved methodology
```

The purpose is to demonstrate **technical growth**, not pretend every experiment succeeded on the first attempt.

---

# 12 · Security Engineering Beyond Offensive Security

Offensive testing is only one side of security.

My broader security interests include:

```text
                    SECURITY
                       │
        ┌──────────────┼──────────────┐
        │              │              │
        ▼              ▼              ▼
     OFFENSE        DEFENSE         ENGINEERING
        │              │              │
   Pentesting      Detection       Secure APIs
   Recon           Monitoring      Authentication
   Exploitation    Logging         Authorization
   Research        Response        Architecture
        │              │              │
        └──────────────┼──────────────┘
                       ▼
                SECURITY ENGINEERING
```

The long-term objective is to understand the complete lifecycle:

**How systems are built → how they are attacked → how attacks are detected → how systems are hardened.**

---

# 13 · AI / LLM Security

Modern applications introduce another attack surface:

```text
User
 │
 ▼
Application
 │
 ▼
LLM
 │
 ├── System instructions
 ├── User instructions
 ├── Retrieved context
 ├── Tools
 └── External data
```

This creates security questions around:

* Prompt injection
* Instruction conflicts
* Context manipulation
* Indirect prompt injection
* Jailbreak behavior
* Tool abuse
* Trust boundaries
* Agent security
* Input classification
* Security policy enforcement

This area is particularly interesting to me because it combines:

```text
Application Security
        +
Artificial Intelligence
        +
Adversarial Thinking
        +
Software Engineering
```

My related work includes experimentation with **prompt-injection detection and security middleware**.

---

# 14 · Responsible Security

Everything published here is intended for:

* Authorized testing
* Personal systems
* Security laboratories
* CTF platforms
* Educational environments
* Open-source research

I do not publish:

* Stolen credentials
* Private keys
* Authentication tokens
* Personal information
* Sensitive organizational information
* Unauthorized access data
* Exploitation details that would expose a real victim without authorization

Security research should improve security rather than create additional victims.

---

# 15 · What This Repository Is Becoming

This repository is intentionally **not finished**.

The goal is to gradually transform it from a collection of tool notes into a structured security engineering record.

Planned expansion:

```text
                    PORTFOLIO
                       │
       ┌───────────────┼────────────────┐
       │               │                │
       ▼               ▼                ▼
   OFFENSIVE        DEFENSIVE       ENGINEERING
       │               │                │
   Web Pentest      Detection       Secure APIs
   Network         Threat Hunt     Security Tools
   Exploitation    Incident IR     Automation
   CTF             Analysis        AI Security
       │               │                │
       └───────────────┼────────────────┘
                       ▼
                SECURITY RESEARCH
```

Future areas include:

* More complete web application assessments
* API security testing
* Network security labs
* Security automation
* Vulnerability research
* Threat detection
* Incident-response exercises
* AI security research
* Secure application architecture
* Reproducible security labs

---

# 16 · Portfolio Quality Standard

Before adding a project, I want it to answer at least one of these questions:

> **What did I discover?**

> **What did I build?**

> **What did I break?**

> **Why did it break?**

> **How did I prove it?**

> **How would I fix it?**

> **What did I learn?**

If a project cannot answer any of these, it probably does not belong in the portfolio.

---

# 17 · Current Repository

### 🔎 Tools

Practical notes and experimentation with security tools.

**[Explore →](./tools)**

### 🧪 Labs

Hands-on security environments and exercises.

**[Explore →](./labs)**

### ⚙️ Scripts

Security-focused Python and Bash automation.

**[Explore →](./scripts)**

### 📝 Writeups

Technical security investigations and CTF documentation.

**[Explore →](./writeups)**

### 🧠 Learning

Lessons, mistakes, concepts, and security research notes.

**[Explore →](./blog-style-learnings)**

---

# 18 · Author

**Yishak Abrham**

Cybersecurity-focused software engineer interested in:

```text
Offensive Security
Application Security
Network Security
AI Security
Security Automation
Secure Software Engineering
```

GitHub:

**[@mrss123](https://github.com/mrss123)**

---

<p align="center">

### 🛡️ BUILD · BREAK · ANALYZE · HARDEN

<sub>This repository documents the process, not just the result.</sub>

</p>
