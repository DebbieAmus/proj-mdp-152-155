# Calculator Web App – Containerized Deployment

This project contains a Java web calculator app deployed using Docker and Jenkins on an EC2 instance.

## 🚀 Project Features

- Java Web Application built with Maven
- Multi-stage Docker build
- Runs on Apache Tomcat inside a container
- Jenkins pipeline to automate Docker build and container deployment

---

## 🛠️ Setup Instructions

### 1. Prerequisites

- EC2 Instance (Amazon Linux 2 or Ubuntu)
- Docker installed
- Jenkins installed and running
- GitHub repo forked and this branch: `project-1`

---

### 2. Files in This Project

- `src/` – Java source code
- `pom.xml` – Maven build file
- `Dockerfile` – Multi-stage build (Maven + Tomcat)
- `Jenkinsfile` – Jenkins pipeline for Docker build and deploy
- `.dockerignore` – Files excluded from Docker context
- `README.md` – You're reading it!

---

### 3. Build and Run Locally (Optional)

```bash
docker build -t calculator-app .
docker run -d -p 8080:8080 --name calculator-container calculator-app
