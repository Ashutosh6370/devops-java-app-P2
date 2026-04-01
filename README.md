# 🚀 DevOps Java App P2

## 📌 Project Overview

This project demonstrates an **end-to-end CI/CD pipeline** for a simple Java application using:

* GitHub for source code management
* Jenkins for CI/CD automation
* Maven for build
* Docker for containerization
* Docker Hub for image registry
* AWS EC2 as Docker Host

---

## 🏗️ Architecture Flow

Developer pushes code to GitHub → Jenkins pulls code → Maven builds the application → Docker image is created → Image is pushed to Docker Hub → Docker container is deployed and run on AWS EC2 (Docker Host)


---

## 📁 Project Structure

```
devops-java-app-P2/
│── src/main/java/com/demo/App.java
│── pom.xml
│── Dockerfile
│── Jenkinsfile
│── README.md
```

---

## ⚙️ Technologies Used

* Java 17
* Maven 3.8.7
* Jenkins
* Docker
* AWS EC2 (used as a host machine to run Docker containers)
* Git & GitHub

---

## 🔄 CI/CD Pipeline Stages

1. **Checkout Code** from GitHub
2. **Build Application** using Maven
3. **Create Docker Image**
4. **Push Image to Docker Hub**
5. **Docker Container on EC2 Host**

---

## 🐳 Docker Details

### Build Image

```
docker build -t ashutosh6370/devops-java-app-p2:v1 .
```

### Run Container

```
docker run ashutosh6370/devops-java-app-p2:v1
```

---

## 📦 Docker Hub Repository

Image available at:
👉 https://hub.docker.com/r/ashutosh6370/devops-java-app-p2

---

## 📊 Output

```
Hello from devops-java-app-p2
```

---

## 🧠 Key Learnings

* End-to-end CI/CD pipeline setup
* Jenkins pipeline configuration
* Docker image creation and deployment
* Debugging real-time build issues
* Importance of naming conventions and versioning

---

## 🚀 Future Enhancements

* Convert application to Spring Boot
* Deploy on Kubernetes (EKS)
* Integrate ArgoCD for GitOps
* Add security scanning using Trivy

---

## 👨💻 Author

**Ashutosh Jena**

---

