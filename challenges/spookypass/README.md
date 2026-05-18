# SpookyPass — HTB Challenge Writeup

- **Difficulty:** Very Easy
- **Category:** Reverse Engineering
- **Date:** May 2026

---

## Summary
A binary file with a hardcoded password stored in plain 
text, recoverable using the strings command.

---

## Solution

Extracted readable strings from the binary:
strings pass

Found hardcoded password:
s3cr3t_p455_f0r_gh05t5_4nd_gh0ul5

Ran the binary and entered the password to get the flag.

---

## Flag
HTB{un0bfu5c4t3d_5tr1ng5}

---

## Lessons Learned
- Never hardcode passwords in binaries
- strings command reveals plain text in executables
- Always obfuscate sensitive strings in compiled code
