# 🐧 Linux Architecture, Processes, and systemd

## 🔹 Linux Architecture

### Hardware
- Base layer of the system  
- Includes CPU, Memory, Disk, Network, and Devices  

### Kernel
- Heart of the Linux system  
- Interacts directly with hardware  
- Manages CPU, memory, and processes  
- Executes user tasks  

### Shell
- Interface between user and kernel  
- Accepts user commands and sends them to kernel  

### Applications / User Space
- Applications are launched by the shell  
- Run in user space and interact with kernel  

---

## 🔹 Process & Process Management

- Everything in Linux is a **process**  
- Even a command executed by user is a process  

### Process Flow
1. User enters command in shell  
2. Shell calls `fork()` → creates child process  
3. Child process calls `exec()`  
4. Kernel schedules process for execution  

### Process States

- **Running (R):** Process is executing on CPU  
- **Sleeping (S):** Waiting for I/O or resource  
- **Stopped (T):** Process paused manually  
- **Zombie (Z):** Process finished but not cleaned  

---

## 🔹 Process Management Commands

- `top` → Shows running processes (real-time monitoring)  
- `htop` → Advanced process viewer (scrollable UI)  
- `ps -a` → Display running processes  
- `ps aux` → Detailed list of all running processes
- `kill -9 PID` → Forcefully terminate a process  

---

## 🔹 systemd / init Process

- First process started by kernel (**PID = 1**)  
- Responsible for managing system services and boot process  

### systemd Commands

- `systemctl status ssh` → Check service status  
- `systemctl start ssh` → Start service  
- `systemctl stop ssh` → Stop service  
- `systemctl restart ssh` → Restart service  
- `systemctl enable ssh` → Enable service at boot  
- `systemctl list-units` → List active services  
- `journalctl -u ssh` → View service logs  

---

## 🔥 Summary

- Kernel controls hardware and system operations  
- Shell connects user with kernel  
- Processes are created using fork & exec  
- systemd manages services and system lifecycle  