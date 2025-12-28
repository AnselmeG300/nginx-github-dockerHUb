# Nginx Static Website with Docker 🐳

A simple Docker project that deploys a static website with Nginx on Ubuntu. 

## 📋 Description

This project uses Docker to containerize a static web application served by Nginx. It automatically clones an example website and configures it to be accessible via Nginx. 

## 🚀 Features

- **Base Image**: Ubuntu 18.04
- **Web Server**: Nginx
- **Automated Deployment**:  Automatic static website cloning
- **Exposed Port**: 80 (HTTP)
- **Full Containerization**: Ready to deploy anywhere

## 🛠️ Prerequisites

- Docker installed on your machine ([Install Docker](https://docs.docker.com/get-docker/))
- (Optional) Docker Hub account to push the image

## 📦 Building the Docker Image

To build the Docker image locally:

```bash
docker build -t anselmeg300/nginx-static-website .
```

## ▶️ Running the Container

To run the container:

```bash
docker run -d -p 8080:80 --name my-nginx-site anselmeg300/nginx-static-website
```

**Options explained:**
- `-d`: Detached mode (background)
- `-p 8080:80`: Maps host port 8080 to container port 80
- `--name`: Custom name for the container

Then access your website at:  `http://localhost:8080`

## 🔍 Useful Docker Commands

### View running containers
```bash
docker ps
```

### View container logs
```bash
docker logs my-nginx-site
```

### Stop the container
```bash
docker stop my-nginx-site
```

### Remove the container
```bash
docker rm my-nginx-site
```

### Access container shell
```bash
docker exec -it my-nginx-site /bin/bash
```

## 🌐 Docker Hub

### Push image to Docker Hub

1. **Login to Docker Hub:**
```bash
docker login
```

2. **Tag the image:**
```bash
docker tag anselmeg300/nginx-static-website anselmeg300/nginx-static-website:v1.0
```

3. **Push the image:**
```bash
docker push anselmeg300/nginx-static-website:v1.0
```

### Pull image from Docker Hub

```bash
docker pull anselmeg300/nginx-static-website: v1.0
```

## 📁 Project Structure

```
.
├── Dockerfile          # Docker configuration file
└── README.md          # This file
```

## 🔧 Dockerfile Details

The Dockerfile performs the following operations:

1. **Ubuntu 18.04 Base**:  Uses a stable Ubuntu image
2. **Install Nginx and Git**: Installs necessary dependencies
3. **Cleanup**: Removes default Nginx HTML files
4. **Clone Website**:  Retrieves the static website from GitHub
5. **Expose Port 80**: Makes the server accessible
6. **Start Nginx**:  Launches Nginx in foreground mode

## 🐛 Troubleshooting

### Container won't start
```bash
docker logs my-nginx-site
```

### Check if port is already in use
```bash
# On Linux/Mac
lsof -i :8080

# On Windows
netstat -ano | findstr :8080
```

### Rebuild image without cache
```bash
docker build --no-cache -t anselmeg300/nginx-static-website .
```

## 📝 Possible Improvements

- [ ] Use official Nginx image (lighter)
- [ ] Add HTTPS with SSL certificates
- [ ] Use Docker Compose to orchestrate multiple services
- [ ] Update to Ubuntu 22.04 LTS
- [ ] Add health checks
- [ ] Implement multi-stage build
- [ ] Add environment variables for configuration

## 👤 Author

**AnselmeG300**
- Email: aansegildass@yahoo.fr
- GitHub: [@AnselmeG300](https://github.com/AnselmeG300)

## 📄 License

This project is open source and available to everyone.

## 🤝 Contributing

Contributions are welcome! Feel free to:
1. Fork the project
2. Create a branch for your feature
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

---

⭐ Don't forget to star this repo if it helped you! 
