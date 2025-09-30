# DevOps Projects

This repository contains two sample projects to demonstrate CI/CD, Docker, and Kubernetes skills.

---

## 📌 Project 1: CI/CD Pipeline with GitHub, Jenkins, Maven, and Tomcat

### Files:
- `pom.xml` → Maven build configuration
- `Jenkinsfile` → Jenkins pipeline definition
- `src/main/webapp/index.jsp` → Sample Java web app

### Steps to Run:
1. Clone the repo:
   ```bash
   git clone https://github.com/your-username/devops_projects.git
   cd devops_projects/cicd_project
   ```

2. Build with Maven:
   ```bash
   mvn clean package
   ```

3. Deploy WAR file manually to Tomcat:
   Copy `target/demo-app.war` to Tomcat's `webapps/` folder.

4. Jenkins Pipeline:
   - Configure Maven & JDK in Jenkins Global Tools.
   - Set up a Jenkins pipeline using the `Jenkinsfile`.
   - Trigger build on GitHub commits (enable Webhooks).

---

## 📌 Project 2: Kubernetes Mini Project (Docker + Minikube)

### Files:
- `Dockerfile` → Container image for the Java app
- `deployment.yaml` → Kubernetes Deployment
- `service.yaml` → Kubernetes Service
- `ingress.yaml` → Kubernetes Ingress

### Steps to Run:
1. Build Docker image:
   ```bash
   docker build -t your-dockerhub-username/demo-app:latest .
   docker push your-dockerhub-username/demo-app:latest
   ```

2. Start Minikube:
   ```bash
   minikube start
   kubectl apply -f deployment.yaml
   kubectl apply -f service.yaml
   kubectl apply -f ingress.yaml   # optional
   ```

3. Check running pods & service:
   ```bash
   kubectl get pods
   kubectl get svc
   ```

4. Access the app:
   - Using NodePort → `http://<minikube-ip>:30080`
   - Using Ingress (after enabling addon) → `http://demo.local`

---

## ✅ Tools & Technologies Used:
- Jenkins
- GitHub
- Maven
- Apache Tomcat
- Docker
- Kubernetes (Minikube)
- SonarQube (optional for code analysis)

---

This setup will help you **showcase end-to-end CI/CD and container orchestration skills** during interviews.
