# Day 12 Revision — Mini Self-Check

**1. Which 3 commands save you the most time right now, and why?**  
- `ls -l` → Quickly lists files permissions
- `systemctl status <service>` → Instantly checks if a service is running.  
- `chmod` / `chown` → Fast way to fix permissions and ownership issues without manually editing files.  

**2. How do you check if a service is healthy? List the exact 2–3 commands you’d run first.**  
- `systemctl status <service>` → Check if the service is active and running.  
- `journalctl -u <service> -n 50` → View the latest logs for errors or warnings.  
- `curl -I localhost` → This confirms the service is actually responding to requests.

**3. How do you safely change ownership and permissions without breaking access? Give one example command.** 

I have practiced creating/modifying/permission of Linux file/folder.
Here is how to safely change ownership and permissions:

- Check current ownership and permissions

`ls -l /path/to/file`

- Change ownership (user and group)
  
`sudo chown user:group /path/to/file`

- Change permissions (least privilege principle)
  
 `chmod 755 /path/to/file`

- Example: `sudo chown -R professor:planners heist-project/`, `sudo chmod 755 project` 

**4. What will you focus on improving in the next 3 days?**  
- Better troubleshooting with logs (`journalctl`) and system monitoring.  
- Streamlining Linux commands for faster daily tasks.
* I want to focus on networking now and complete Linux Volume Management.
* Also I will practice users & group management.
* And if time allows I will also watch AWS videos.