# Docker Installation Guide for RHEL 9

This guide will explains you how to install Docker on **Red Hat Enterprise Linux 9 (RHEL 9)** using the official Docker repository.

## Prerequisites

* A system running **RHEL 9**
* User with **sudo privileges**
* Internet connectivity
* `dnf` package manager available

---

## Step 1: Update the System

Update all installed packages to the latest versions.

```bash
sudo dnf update -y
```

---

## Step 2: Add Docker Repository

Install the dnf-plugins-core package (which provides the commands to manage your DNF repositories) and set up the repository.

```bash
sudo dnf -y install dnf-plugins-core
sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

---

## Step 3: Install Docker Engine

Install Docker packages.

```bash
sudo dnf install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
```

---

## Step 4: Start Docker Service

Start and enable Docker service so that it starts automatically during system boot.

```bash
sudo systemctl start docker
sudo systemctl enable docker
```

Verify the status:

```bash
sudo systemctl status docker
```

---

## Step 5: Verify Docker Installation

Run the test container to verify the installation.

```bash
sudo docker run hello-world
```

If Docker is installed correctly, a **welcome message** will appear.

---

## Step 6: Run Docker Without sudo (Optional)

Add your user to the docker group.

```bash
sudo usermod -aG docker $USER
```

Apply the changes:

```bash
newgrp docker
```

Now you can run Docker commands without `sudo`.

Example:

```bash
docker ps
```

---

## Step 7: Verify Docker Version

```bash
docker --version
```

Example output:

```
Docker version 29.3.1
```

---

## Useful Docker Commands

| Command                        | Description                      |
| ------------------------------ | ---------------------------------|
| `docker ps`                    | List running containers          |
| `docker ps -a`                 | List all containers              |
| `docker images`                | List downloaded images           |
| `docker pull nginx`            | Download nginx image             |
| `docker create nginx`          | Creates the nginx container      |
| `docker start <container-id>`  | Start nginx container            |
| `docker rm <container-id>`     | Removes container                |
| `docker rmi <image-id>`        | Removes image                    |
| `docker run nginx`             | It will Pull, create & Run nginx |

---

## Troubleshooting

### Docker Service Not Starting

Check logs:

```bash
sudo journalctl -u docker
```

Restart Docker:

```bash
sudo systemctl restart docker
```

---

## References

* Docker Official Documentation
* RHEL 9 Administration Guide

---


