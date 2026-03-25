# 🐧 Linux Commands Cheat Sheet

## 🔹 Process Management

- `ps aux` → Show all running processes  
- `ps -a`   → is used to display all process 
- `pstree`  → it will showing running process in tree format
- `top` → Real-time process monitoring  
- `htop` → you can horizontally & vertically scroll all process  
- `kill PID` → Gracefully stop process  
- `kill -9 PID` → Force kill process  
- `pkill name` → Kill process by name  
- `pgrep name` → Get PID by process name  

---

## 🔹 File System Commands

- `ls -l` → List files with details  
- `cd /path` → Change directory  
- `pwd` → Show current directory  
- `mkdir dir` → Create directory 
- `tree`  → it will show current directory structure in the form of tree 
- `rm -rf dir` → Delete directory  
- `cp file1 file2` → to copy from file1 to file2  
- `mv file1 file2` → Move/rename file  
- `touch file` → Create empty file  

---

## 🔹 File Viewing & Logs

- `cat file` → View file content  
- `less file` → Scroll file content  
- `head file` → First 10 lines  
- `tail file` → Last 10 lines  
- `tail -f file` → Live log monitoring  
- `grep "text" file` → Search text in file  

---

## 🔹 Networking Commands

- `ping google.com` → Check connectivity 
- `hostname`  → to check a server ip/hostname 
- `ip addr` → Show IP address  
- `curl http://example.com` → Test API/URL response  
- `netstat -tulnp` → Show open ports  
- `dig`   → to check dns info
- `ss -tulnp` → Modern netstat alternative 
- `netstat -a` - Show listening tcp and udp ports and corresponding programs.
- `traceroute` host - Traces network path
- `wget url` - Download files from internet
- `whois domain` - Displays whois information for domain
- `host domain` - Displays DNS IP address for domain
- `nslookup domain` - Display IP address of domain

---

## 🔹 Permissions & Disk

- `chmod 755 file` → Change permissions  
- `chown user:group file` → Change ownership  
- `df -h` → Disk usage  
- `du -sh dir` → Folder size  