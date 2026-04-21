# 📄 RUNBOOK: SSH Service Troubleshooting

This runbook provides quick troubleshooting steps if the SSH service goes down.

---

## 🔹 Environment Basics

**System Info**  
Command: `uname -a`  
Output: Linux ip-172-31-18-81 6.17.0-1007-aws x86_64 GNU/Linux  
Observation: Ubuntu Linux kernel running on AWS EC2 instance  

**OS Details**  
Command: `cat /etc/os-release`  
Output: Ubuntu 24.04.4 LTS (Noble Numbat)  
Observation: Confirmed Ubuntu OS version  

---

## 🔹 Filesystem Sanity

**Create directory & file**  
Command: `mkdir /tmp/runbook-demo`  
Observation: Directory created successfully  

Command: `cp /etc/hosts /tmp/runbook-demo/hosts-copy && ls -l /tmp/runbook-demo`  
Observation: Filesystem is writable and file copied successfully  

**Verify file**  
Command: `cat /tmp/runbook-demo/hosts-copy`  
Observation: No filesystem corruption  

---

## 🔹 Snapshot: CPU & Memory

**Check SSH process**  
Command: `ps -o pid,pcpu,pmem,comm -p $(pidof sshd)`  
Observation: SSH processes running with negligible CPU & memory usage  

**Memory usage**  
Command: `free -h`  
Observation: Sufficient memory available  

---

## 🔹 Snapshot: Disk & IO

**Disk usage**  
Command: `df -h`  
Observation: Disk usage within safe limits  

**Logs size**  
Command: `du -sh /var/log`  
Observation: Logs are minimal (~39MB)  

**IO stats**  
Command: `iostat`  
Observation: CPU idle ~99%, negligible I/O wait → system healthy  

---

## 🔹 Snapshot: Network

**Check port**  
Command: `sudo ss -tulpn | grep sshd`  
Observation: SSH listening on port 22  

**Test connectivity**  
Command: `nc -zv localhost 22`  
Observation: Connection successful  

---

## 🔹 Logs Reviewed

**SSH logs**  
Command: `journalctl -u ssh -n 50`  
Observation: Normal authentication activity, no errors  

**Auth logs**  
Command: `tail -n 50 /var/log/auth.log`  
Observation: Login activity recorded, no suspicious behavior  

---

## 🔹 Quick Findings

- SSH service running normally  
- CPU & memory usage low  
- Disk and logs healthy  
- Port 22 open and accessible  
- No errors in logs  

---

## 🔹 If This Worsens

- Check logs again (`journalctl -u ssh -f`)  
- Monitor CPU/Disk usage (`top`, `df -h`)  
- Restart service (`sudo systemctl restart ssh`)  
- Check port conflicts (`ss -tulpn | grep 22`)  

---

## ✅ Key Takeaway

Structured troubleshooting (CPU → Memory → Disk → Network → Logs) helps quickly identify issues and avoid guesswork.