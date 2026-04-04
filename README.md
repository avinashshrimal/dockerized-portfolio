# \# Dockerized Portfolio Website

# 

# A personal portfolio website containerized using Docker and deployed on an AWS EC2 cloud virtual machine.

# 

# \## Technologies Used

# \- Docker \& Nginx

# \- AWS EC2 (Ubuntu 22.04)

# \- Git \& GitHub

# 

# \## Project Structure

dockerized-portfolio/

├── index.html

├── styles.css

├── Dockerfile

├── screenshots/

│   ├── docker-ps.png

│   └── live-website.png

└── README.md



\## Dockerfile

```dockerfile

FROM nginx:alpine

COPY . /usr/share/nginx/html

EXPOSE 80

```



\## Deployment Steps



\### 1. Build Docker image locally

```bash

docker build -t dockerized-portfolio .

```



\### 2. Run container locally

```bash

docker run -d -p 8080:80 dockerized-portfolio

```

Visit: http://localhost:8080



\### 3. Launch AWS EC2 instance

\- Ubuntu Server 22.04 LTS

\- Instance type: t2.micro (Free Tier)

\- Allow inbound HTTP (port 80) and SSH (port 22)



\### 4. Install Docker on EC2

```bash

sudo apt update

sudo apt install docker.io -y

sudo systemctl start docker

sudo usermod -aG docker ubuntu

```



\### 5. Clone repo and deploy

```bash

git clone https://github.com/avinashshrimal/dockerized-portfolio.git

cd dockerized-portfolio

sudo docker build -t dockerized-portfolio .

sudo docker run -d -p 80:80 dockerized-portfolio

```



\### 6. Access live website

Visit: http://YOUR\_EC2\_IP



\## Key Learnings

\- Containerization ensures consistent behavior across environments

\- Docker images package the app with all its dependencies

\- Manual cloud deployment is the foundation before CI/CD automation

