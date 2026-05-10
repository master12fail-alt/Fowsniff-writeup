# Fowsniff - TryHackMe Writeup

**Author:** [P1st0ler0](https://tryhackme.com/p/P1st0ler0)  
**Platform:** TryHackMe  
**Room:** [Fowsniff](https://tryhackme.com/room/fowsniff)  
**Difficulty:** Easy  
**Date:** May 10, 2026

---

## Objective
Exploit a data breach at Fowsniff Corporation to gain initial access and escalate to root.

---

## Reconnaissance

### Nmap Scan
![Nmap Scan](images/1-nmap..png)

### Web Enumeration
![Fowsniff Website](images/8-website-breach.png)

---

## OSINT - Credential Leak

### GitHub Leak
![fowsniff.txt](images/2-fowsniff-txt.png)

### Twitter OSINT
![Twitter Search](images/3-osint-twitter.png)

---

## Password Cracking

![Hash File](images/4-hash-file..png)

![John Cracking](images/5-john-crack.png)

**Cracked Credentials (redacted):**
- `seina` → `scooby*****`
- `baksteen` → `S1ck3nBluff********`

---

## Initial Access via POP3

![POP3 Access](images/6-pop3-email.png)

---

## SSH Access

![SSH Login](images/7-ssh-baksteen.png)

---

## Privilege Escalation & Root

After successful privilege escalation, we gained a **root shell**:

![Root Shell](images/9-root-flag.png)

**Flag Captured!**

---

**Writeup by:** [P1st0ler0](https://tryhackme.com/p/P1st0ler0)
