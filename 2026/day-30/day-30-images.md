# Day 30 – Docker Images & Container Lifecycle

## Task

### Task 1: Docker Images

- dokcer pull nginx
- docker pull ubuntu
- docker pull alpine
- docker images

**Compare Ubuntu vs Alpine — Why Is Alpine Much Smaller?**
|Ubuntu	|Alpine|
|:-------|:------|
|Full-featured Linux distribution	|Minimal Linux distribution|
|Includes many utilities and packages	|Includes only essential packages|
|Larger image size (~70–80 MB)	|Very small image (~5–10 MB)|
|Easier for beginners	|Optimized for containers|
|Uses glibc	|Uses musl libc|

- dokcer inspect nginx
- docker rmi ubuntu

![alt text](image.png)

### Task 2: Image Layers

**Run Image History**

- docker image history nginx
```text
IMAGE          CREATED        CREATED BY                      SIZE
abcd1234       2 weeks ago    CMD ["nginx" "-g" ...]          0B
abcd1234       2 weeks ago    EXPOSE 80                       0B
abcd1234       2 weeks ago    COPY docker-entrypoint.sh       4KB
abcd1234       2 weeks ago    RUN apt-get install ...         120MB
abcd1234       2 weeks ago    ADD rootfs.tar.xz               80MB
```

**Why Do Some Layers Show Sizes and Others Show 0B?**

Layers that add, modify, or delete files consume storage and show a size:

- RUN apt-get install nginx
- COPY app/ /app
- ADD file.tar.gz /

**Example:**
```text
120MB
5MB
20KB
```

**What Are Docker Layers and Why Does Docker Use Them?**
**What are Layers?**

A Docker image is made up of multiple read-only layers stacked on top of each other.

Each Dockerfile instruction creates a new layer.

Example:
```text
FROM ubuntu
RUN apt update
RUN apt install nginx
COPY index.html /usr/share/nginx/html
```
Creates:
```text
Layer 1 → Ubuntu Base Image
Layer 2 → apt update
Layer 3 → nginx installation
Layer 4 → index.html copied
```