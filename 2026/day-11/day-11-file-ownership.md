# Day 11 – File Ownership Challenge (chown & chgrp)

## Task

### Task 1: Understanding Ownership

- ls -l
- I have identified that some files are owned by ubuntu & some files are owned by root
**What's the difference between owner and group?**

- **Owner:** The main user who owns the file
- **Group:** A collection of users who can share access to the file

### Task 2: Basic chown Operations 

- touch devops-file.txt
- ls -l (Checked current owner is root)
- chown tokyo devops-file.txt(Changed owner to tokyo)
- chown berlin devops-file.txt(Changed owner to berlin)

![alt text](image.png)

### Task 3: Basic chgrp Operations

- touch team-notes.txt
- ls -l (Checked current owner is root)
- groupadd heist-team (Group added)
-  chgrp heist-team team-notes.txt
- ls -l

![alt text](image-1.png)

### Task 4: Combined Owner & Group Change

- touch project-config.yaml
- chown professor:heist-team project-config.yaml
- mkdir app-logs/
- chown berlin:heist-team app-logs/
- ls -l

![alt text](image-2.png)

