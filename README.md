# 🚀 CI/CD Flask App Deployment using Docker, GitHub Actions & AWS EC2

This project demonstrates a simple but complete DevOps pipeline that:
- Builds a Flask app with Docker.
- Pushes the code to GitHub.
- Automatically deploys the app to an AWS EC2 instance using GitHub Actions.

## 🔧 Stack Used
- **Flask** – Python web framework
- **Docker** – Containerize the app
- **GitHub Actions** – Automate CI/CD
- **AWS EC2** – Host production container

## 🛠️ Features
- CI/CD pipeline triggers on `git push` to `main`
- Uses `appleboy/scp-action` and `ssh-action` for secure file transfer and remote execution
- Docker container rebuilt on every push and deployed live on EC2
- Environment setup securely managed with GitHub Secrets

## 📦 How It Works
1. Code is pushed to `main` branch.
2. GitHub Action runs:
   - Checks out repo
   - Copies code to EC2 via SCP
   - SSHs into EC2 and:
     - Stops old container
     - Builds new Docker image
     - Runs container exposing Flask app on port 80

## 🔐 Security
- SSH key stored as GitHub Secret (`EC2_SSH_KEY`)
- Host IP stored in GitHub Secret (`EC2_HOST`)

## 🌐 Live Demo
If applicable, add your public EC2 IP here:  
**http://<your-ec2-ip>/**
