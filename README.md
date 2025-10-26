# 🚀 HNG13 DevOps Internship — Stage 2 Task

## 📌 Task Overview
This project implements a Blue/Green deployment architecture using Docker Compose and NGINX. Two pre-built Node.js services (Blue and Green) are deployed behind NGINX with automatic failover and retry logic. The setup ensures zero downtime and seamless client experience during simulated failures.

## 👨‍💻 Author
**Full Name:** Solomon  
**Slack Display Name:** @ASOCODE

## 🛠️ Features
- Blue/Green Node.js services with health endpoints
- NGINX reverse proxy with upstream failover
- Docker Compose orchestration
- Parameterized environment via `.env`
- Chaos testing via `/chaos/start` and `/chaos/stop`
- Header forwarding (`X-App-Pool`, `X-Release-Id`)

## 📂 Project Structure
