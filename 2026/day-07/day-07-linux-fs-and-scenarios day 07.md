# Day 07 – Linux File System Hierarchy & Scenario-Based Practice

# Task

**Part 1: Linux File System Hierarchy (30 minutes)**
**Document the purpose of these essential directories:**

1. **Core Directories (Must Know):**

/ (root) - The starting point of everything
/home - User home directories
/root - Root user's home directory
/etc - Configuration files
/var/log - Log files (very important for DevOps!)
/tmp - Temporary files

2. **Additional Directories (Good to Know):**

/bin - Essential command binaries
/usr/bin - User command binaries
/opt - Optional/third-party applications

**Hands-on task:**
# Find the largest log file in /var/log
du -sh /var/log/* 2>/dev/null | sort -h | tail -5

# Look at a config file in /etc
cat /etc/hostname

# Check your home directory
ls -la ~

**Part 2: Scenario-Based Practice**

Example Scenario: Check if a service is running

Question: How do you check if the 'nginx' service is running?
My Solution (Step by step):

**Step 1: Check service status**
- systemctl status nginx
Why this command? It shows if the service is active, failed, or stopped

**Step 2: If service is not found, list all services**
- systemctl list-units --type=service
Why this command? To see what services exist on the system

**Step 3: Check if service is enabled on boot**
- systemctl is-enabled nginx


