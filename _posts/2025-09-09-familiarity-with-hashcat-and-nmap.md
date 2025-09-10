# [2025-09-09 :: Lab Notes]

## Title: Familiarity with Hashcat and Nmap

### Security+ Exam Simulation
- Reviewed results from the **SY0-701 Exam Simulation**.
- Key takeaway: Focus areas should include missed questions, error log tracking, and reinforcing weak domains.
- Action: Add all missed Security+ questions to the error log for targeted review.

### Hashcat Exploration
- Experimented with `hashcat -m 1800` using SHA-based password hashes.
- Confirmed that `.gz` wordlists must be decompressed before use with Hashcat.
- Clarified the difference between **built-in candidate generation** and **wordlist-only attacks**.
- Observed hybrid attack behavior when combining wordlists with Hashcat’s rules.

### System Fundamentals
- Practiced Zsh command to display all file contents in the current directory: `cat *`.
- Clarified that **NSE (Nmap Scripting Engine) scripts** are Lua-based automation scripts for tasks like vulnerability scanning, discovery, and exploitation.
