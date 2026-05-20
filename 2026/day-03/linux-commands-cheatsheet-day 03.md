# Day 03 – Linux Commands Cheat Sheet

# Commands in Linux:
# Files:

# 1. Process Management Commands

| Command                     | Purpose                      |
| :---------------------------| :--------------------------  |
| `ps`                        | Show current processes       |  
| `ps -ef`                    | List all running processes   |
| `ps aux`                    | Detailed process information |
| `top`                       | Real-time process monitoring |
| `htop`                      | Interactive process viewer   |
| `pgrep process_name`        | Find PID by process name     |
| `pidof process_name`        | Get process ID               |
| `kill PID`                  | Stop a process gracefully    |
| `kill -9 PID`               | Force kill a process         |
| `pkill process_name`        | Kill process by name         |
| `killall process_name`      | Kill all matching processes  |
| `jobs`                      | Show background jobs         |
| `bg`                        | Run job in background        |
| `fg`                        | Bring job to foreground      |
| `nice -n 10 command`        | Start process with priority  |
| `renice 5 PID`              | Change process priority      |
| `systemctl status service`  | Check service status         |
| `systemctl start service`   | Start service                |
| `systemctl stop service`    | Stop service                 |
| `systemctl restart service` | Restart service              |
| `journalctl -u service`     | View service logs            |


# 2. File system

| Command                 | Purpose                      |
| :-----------------------| :----------------------------|
| `pwd`                   | Show current directory       |
| `ls`                    | List files/directories       |
| `ls -la`                | Detailed hidden files list   |
| `cd directory`          | Change directory             |
| `mkdir dir_name`        | Create directory             |
| `rmdir dir_name`        | Remove empty directory       |
| `rm file`               | Delete file                  |
| `rm -rf dir`            | Delete directory recursively |
| `cp source dest`        | Copy files/directories       |
| `mv source dest`        | Move/rename file             |
| `touch file`            | Create empty file            |
| `cat file`              | View file content            |
| `less file`             | Read large files             |
| `head file`             | View first lines             |
| `tail file`             | View last lines              |
| `tail -f logfile`       | Monitor live logs            |
| `find / -name file`     | Search files                 |
| `locate file`           | Quick file search            |
| `grep "text" file`      | Search text in file          |
| `chmod 755 file`        | Change permissions           |
| `chown user:user file`  | Change ownership             |
| `df -h`                 | Disk usage                   |
| `du -sh folder`         | Folder size                  |
| `mount`                 | Show mounted disks           |
| `umount /dev/sdb1`      | Unmount disk                 |
| `ln -s source link`     | Create symbolic link         |
| `tar -cvf file.tar dir` | Create tar archive           |
| `tar -xvf file.tar`     | Extract tar archive          |
| `zip file.zip file`     | Compress file                |
| `unzip file.zip`        | Extract zip file             |

# 3. Networking troubleshooting

| Command | Usage |
|:---|:---|
| `ip addr show` | Display IP addresses |
| `ping google.com` | Test network connectivity |
| `traceroute google.com` | Trace network path |
| `curl -I https://example.com` | Check website response headers |
| `wget <url>` | Download files from internet |
| `netstat -tulnp` | Check listening ports |
| `ss -tulnp` | View active network connections |
| `lsof -i :80` | Check process using a port |

# Manual:
(a) man: detailed information of a command

**Usage:**
- man (command)

(b) which: location of a command

**Usage:**
- which (command)
- command -v (command)

(c) type: shows the type of a command

**Usage:**
- type (command)

# Processes:
- top/htop: shows live processes