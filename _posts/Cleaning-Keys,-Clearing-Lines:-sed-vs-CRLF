#[2025-09-03 :: Lab Note - Cleaning Keys, Clearing Lines: sed vs CRLF]

## Focus
Red Core grind + tool mastery. sed, CRLF cleanup, and workflow discipline.

---

## 🧰 Tools & Commands Explored
- **sed**
  - Broke down the substitution expression (`s/SEARCH/REPLACE/flags`).
  - Used `sed -i 's/\r$//' id_rsa` to strip CRLF carriage returns from SSH private keys.
  - Learned:
    - `-i` = in-place editing.
    - Flags like `g` (global), `i` (case-insensitive), `p` (print on match).
    - Anchors: `^` (start of line), `$` (end of line).
  - Verified why `\r$` targets Windows carriage returns and ensures Linux-compatible SSH keys.

---

## 🔑 Key Lessons
- **Ignorance isn’t weakness, it’s the entry fee.**  
  Each mistake opened new doors and forced real comprehension.
- In-place editing is powerful — but test first, back up before nuking.
- CRLF vs LF matters: Windows = `\r\n`, Linux = `\n`. Hidden `\r` breaks private keys.

---

## Discipline & Workflow
- Completed multiple pomodoros.
- Learned that skipping breaks drains energy — the break is part of the training, not wasted time.
- Locked in on AttackBox for efficiency (less buggy than VM).
- Posted milestone note: **first Hydra password cracked** → added to lab notes.

---

## 🎯 Milestones
- ✅ Logged method and wordlist.  
- ✅ Documented sed cleanup command for SSH key hygiene.  

---

## 🪜 Next Steps
- Verify file integrity visually after sed (e.g., `cat -v`, `od`).
- Push Hydra learnings into BruteIt box continuation.
- Keep refining workflow discipline with enforced breaks and cooldown rituals.

---
