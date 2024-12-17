# 🚀 Deploy Netflix Clone on Cloud using Jenkins - DevSecOps Project

This project demonstrates a **Netflix Clone** deployment on the cloud with a complete **DevSecOps pipeline**. It incorporates modern CI/CD practices, container orchestration, and monitoring tools to deliver a robust, scalable, and secure application infrastructure.

---

## 🛠️ Tools & Technologies Used

- **AWS Cloud**: Cloud infrastructure to host the application and resources.
- **Docker**: Containerization of the Netflix Clone application.
- **Kubernetes**: Orchestration of Docker containers for scalability and management.
- **SolarKube**: Security validation and hardening for Kubernetes clusters.
- **Jenkins**: CI/CD pipeline automation for building, testing, and deploying the application.
- **Helm**: Kubernetes package manager for managing deployments.
- **ArgoCD**: GitOps continuous delivery tool for Kubernetes.
- **Prometheus**: Monitoring and alerting for metrics collection.
- **Grafana**: Visualization of performance metrics collected by Prometheus.

---

## 📋 Project Workflow

### 1. **Application Setup**
   - Clone the Netflix Clone repository.
   - Containerize the application using Docker.

### 2. **CI/CD Pipeline**
   - **Jenkins** is configured to:
     - Pull the source code from a Git repository.
     - Build the Docker image.
     - Run automated tests.
     - Push the Docker image to **AWS ECR** (Elastic Container Registry).

### 3. **Deployment on Kubernetes**
   - Use **Helm** charts to define and deploy the application resources on **AWS EKS** (Elastic Kubernetes Service).
   - Secure the cluster with **SolarKube** for vulnerability scans and compliance checks.

### 4. **GitOps Integration**
   - **ArgoCD** manages deployments using a GitOps approach to ensure application versions are deployed consistently across environments.

### 5. **Monitoring and Visualization**
   - **Prometheus** collects metrics from the Kubernetes cluster.
   - **Grafana** visualizes the performance metrics with pre-configured dashboards for real-time monitoring.

---

## 🔧 Project Setup and Execution

Follow these steps to deploy the Netflix Clone:

### Prerequisites
- AWS account with necessary IAM permissions.
- Docker and Kubernetes CLI installed locally.
- Jenkins server setup.
- Helm and ArgoCD installed on your cluster.
- Prometheus and Grafana installed.

### Steps
1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd netflix-clone-deploy
   ```

2. **Build Docker Image**:
   ```bash
   docker build -t netflix-clone:latest .
   ```

3. **Push Image to AWS ECR**:
   ```bash
   aws ecr create-repository --repository-name netflix-clone
   docker tag netflix-clone:latest <aws-account-id>.dkr.ecr.<region>.amazonaws.com/netflix-clone:latest
   docker push <aws-account-id>.dkr.ecr.<region>.amazonaws.com/netflix-clone:latest
   ```

4. **Deploy using Helm**:
   ```bash
   helm install netflix-clone ./helm-chart
   ```

5. **Set up ArgoCD**:
   - Connect your Git repository and deploy the application with ArgoCD.

6. **Access Monitoring Dashboards**:
   - View Prometheus metrics and Grafana dashboards.

---

## 📊 Monitoring
- **Prometheus**: Collects cluster and application metrics.
- **Grafana**: Provides dashboards for:
  - CPU/Memory usage
  - Pod health
  - Network traffic

---

## 🔐 Security
- **SolarKube** is used for scanning and securing Kubernetes configurations.
- Jenkins pipeline integrates security checks for images and cluster configurations.

---

## 🚀 Key Features
- **End-to-End CI/CD Pipeline** with Jenkins and ArgoCD.
- **Scalable and Resilient Deployment** using Kubernetes.
- **Secure Infrastructure** with SolarKube.
- **Real-Time Monitoring** with Prometheus and Grafana.
- **Helm-Managed Deployments** for simplified Kubernetes resource management.

---

## 📸 Screenshots

- *Jenkins Pipeline Output*
- *Grafana Dashboard*
- *ArgoCD Deployment Status*

*(Add relevant screenshots here)*

---

## 🤝 Contributing
Contributions are welcome! Feel free to fork this repository, open an issue, or submit a pull request.

---

## 📝 License
This project is licensed under the **MIT License**.

---

## 📧 Contact
- **Author**: [Your Name]
- **Email**: [Your Email]
- **LinkedIn**: [Your LinkedIn Profile]

---

**Happy Deploying! 🎉**
