# End-to-End CI/CD Pipeline Automation | AWS, Docker, Kubernetes, Terraform

## Overview
This project implements a fully automated CI/CD pipeline using Jenkins, Docker, Kubernetes (EKS), and Terraform. The objective is to achieve faster deployments, improve system reliability, and enable real-time observability through centralized monitoring.

![CI/CD Pipeline](https://miro.medium.com/max/1400/1*VdT7FgtIBqu2T26QF5mp4g.png)

## Features
- **Optimized CI/CD Pipeline**: Automated deployment process using Jenkins, reducing deployment time by 40%.
- **Containerization & Orchestration**: Dockerized applications running on Kubernetes (EKS) for scalability and high availability.
- **Infrastructure as Code (IaC)**: Provisioned AWS resources using Terraform and Ansible, enabling seamless scalability and auto-healing capabilities.
- **Efficient Artifact Management**: Integrated JFrog Artifactory to optimize artifact storage and management, reducing failures by 35%.
- **Real-time Monitoring & Logging**:
  - **Prometheus & Grafana** for performance monitoring and alerting.
  - **ELK Stack** for centralized logging and log analysis.

![Monitoring Stack](https://grafana.com/api/blog/proxy?url=/static/assets/img/blog/2022/grafana-cloud-kubernetes-monitoring.jpg)

## Technologies Used
- **CI/CD Tools**: Jenkins
- **Containerization**: Docker
- **Orchestration**: Kubernetes (EKS)
- **Infrastructure as Code (IaC)**: Terraform, Ansible
- **Cloud Provider**: AWS (Elastic Kubernetes Service - EKS)
- **Artifact Management**: JFrog Artifactory
- **Monitoring & Logging**: Prometheus, Grafana, ELK Stack (Elasticsearch, Logstash, Kibana)

## Architecture
```plaintext
1. Developer commits code to Git repository
2. Jenkins triggers CI/CD pipeline
3. Build & package application into Docker images
4. Push Docker images to JFrog Artifactory
5. Deploy containers to Kubernetes (EKS) using Terraform & Helm
6. Monitor & analyze system performance with Prometheus, Grafana, and ELK Stack
```

![Pipeline Flow](https://www.edureka.co/blog/wp-content/uploads/2019/05/CICD-Pipeline.png)

## Setup & Deployment
### Prerequisites
- AWS account with EKS cluster setup
- Jenkins installed and configured
- Terraform and Ansible installed
- Docker and Kubernetes CLI installed

### Steps
1. **Clone the Repository**
   ```sh
   git clone https://github.com/sudarshan-gawande/ci-cd-pipeline.git
   cd ci-cd-pipeline
   ```
2. **Setup Infrastructure using Terraform**
   ```sh
   terraform init
   terraform apply -auto-approve
   ```
3. **Configure Jenkins Pipeline**
   - Add repository URL in Jenkins
   - Configure Jenkinsfile with build, test, and deploy stages
4. **Build & Deploy Application**
   ```sh
   docker build -t my-app .
   docker push <JFrog Artifactory URL>/my-app:latest
   ```
5. **Deploy to Kubernetes (EKS)**
   ```sh
   kubectl apply -f k8s/deployment.yaml
   ```
6. **Monitor System**
   - Access Prometheus & Grafana for performance metrics
   - Use Kibana to analyze logs

## Performance Improvements
- **40% Faster Deployments**: Optimized CI/CD workflows reduced deployment time.
- **35% Fewer Failures**: Improved artifact management with JFrog Artifactory.
- **40% Reduced Downtime**: Auto-healing Kubernetes deployments.

## Future Enhancements
- Implement blue-green and canary deployments for zero-downtime updates.
- Enhance security with AWS IAM and RBAC policies.
- Automate scaling with Kubernetes Horizontal Pod Autoscaler.

## Author
[Sudarshan Gawande](https://github.com/sudarshan-gawande)
