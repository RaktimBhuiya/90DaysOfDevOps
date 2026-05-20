# The core components of Linux (kernel, user space, init/systemd)

**Kernel** → The core part of Linux that directly manages hardware, CPU, memory, devices, and system resources.
**User Space** → The area where user applications and commands run without direct hardware access.
**Init/Systemd** → The first process started during boot that manages system startup, services, and background processes.

# How processes are created and managed

In Linux, processes are created when a program is executed. The system usually uses fork() to create a new child process from an existing parent process, and exec() to load and run a new program inside that process. Each process is assigned a unique PID (Process ID). The Linux kernel manages processes through scheduling, allocating CPU time and controlling process states such as running, waiting, sleeping, or stopped. Administrators can monitor and manage processes using commands like **ps**, top, kill, and systemctl.

# What systemd does and why it matters

systemd is the init and service management system in Linux that starts and manages system processes and services during boot. It handles tasks like starting services, monitoring them, restarting failed services, managing dependencies, logging, and controlling background processes. It matters because it improves boot speed, automates service management, and provides centralized control over the Linux system.

 # What is a command-line interface ?

Text-based interface to talk to a computer

# What is a prompt in Linux ?

Prompt: user@ubuntu:~$

user - Who you're logged in as

ubuntu - What computer you're on

~ - Your current directory (~ means home directory)

$ - You're a normal user (# means root/admin)


# Linux day to day commands?

- ssh -i private_key username@ip_address
- whoami
- hostname
- pwd
- ls
- cat
- date
- uptime
- echo
- touch
- rm <file-name>
- history
