# Day 29 – Introduction to Docker

## Task

### Task 1: What is Docker?

- Docker is an open-source containerization platform that allows you to package an application along with all its dependencies, libraries, and configurations into a container. This ensures the application runs consistently across different environments.

**What is a container and why do we need them?**
- A container is a lightweight, isolated package that contains an application along with all its dependencies, libraries, and configurations needed to run.

**Why do we need Containers?**
- Ensure applications run consistently across environments.
- Eliminate "it works on my machine" issues.
- Simplify deployment and scaling.
- Use fewer resources compared to virtual machines.
- Enable faster CI/CD and DevOps workflows.

**Containers vs Virtual Machines (VMs)**
|Feature	|Containers	|Virtual Machines|
|:-----------|:-----------|:----------------|
|Virtualization Level	|OS-level virtualization	|Hardware-level virtualization|
OS Included	Share host OS kernel	Each VM has its own OS|
|Size	|MBs	|GBs|
|Startup Time	|Seconds	|Minutes|
|Resource Usage	|Lightweight	|Heavy|
|Performance	|Near-native	|Slight overhead|
|Isolation	|Process-level	|Full OS-level|
|Use Case	|Microservices, CI/CD, DevOps	|Running multiple OSs, legacy apps|