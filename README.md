# Notes App with CI/CD Pipeline

A full-stack notes application built with React and Django, featuring automated deployment through Jenkins CI/CD pipeline.

## 🚀 Features

- **Frontend**: React-based user interface
- **Backend**: Django REST framework
- **Containerization**: Docker support
- **CI/CD**: Automated Jenkins pipeline for continuous integration and deployment
- **Reverse Proxy**: Nginx configuration for production deployment

## 📋 Requirements

- Python 3.9
- Node.js
- Docker
- Jenkins (for CI/CD pipeline)
- Nginx (for reverse proxy)

## 🛠️ Installation

### Clone the Repository
```bash
git clone https://github.com/AC12arpitChauhan/CI-CD-Pipeline.git
cd django-notes-app-dc
```

### Build the Docker Image
```bash
docker build -t notes-app .
```

### Run the Application
```bash
docker run -d -p 8000:8000 notes-app:latest
```

The application will be available at `http://localhost:8000`

## 🔄 CI/CD Pipeline

This project includes a Jenkins pipeline configuration (`Jenkinsfile`) that automates:

- Code checkout from repository
- Automated testing
- Docker image building
- Container deployment
- Health checks

### Setting Up Jenkins Pipeline

1. Create a new Pipeline job in Jenkins
2. Configure the repository URL
3. Point to the `Jenkinsfile` in the repository
4. Run the pipeline to deploy automatically

## 🌐 Nginx Reverse Proxy Setup

To make the application available through Nginx:

```bash
# Update system packages
sudo apt-get update

# Install Nginx
sudo apt install nginx

# Configure Nginx (edit the default configuration)
sudo nano /etc/nginx/sites-available/default

# Restart Nginx
sudo systemctl restart nginx
```

### Sample Nginx Configuration
```nginx
server {
    listen 80;
    server_name your_domain.com;

    location / {
        proxy_pass http://localhost:8000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }
}
```

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!
