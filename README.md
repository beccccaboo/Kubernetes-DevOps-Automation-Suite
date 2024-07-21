# Advanced Cloud Project

[![Kubernetes](https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=for-the-badge&logo=kubernetes&logoColor=white)](https://kubernetes.io)
[![Apache Kafka](https://img.shields.io/badge/Apache%20Kafka-000?style=for-the-badge&logo=apachekafka)](https://kafka.apache.org)
[![Terraform](https://img.shields.io/badge/terraform-%235835CC.svg?style=for-the-badge&logo=terraform&logoColor=white)](https://www.terraform.io)
[![Packer](https://img.shields.io/badge/packer-%23E7EEF0.svg?style=for-the-badge&logo=packer&logoColor=%2302A8EF)](https://www.packer.io/)
[![Go](https://img.shields.io/badge/go-%2300ADD8.svg?style=for-the-badge&logo=go&logoColor=white)](https://golang.org/)
[![Jenkins](https://img.shields.io/badge/jenkins-%232C5263.svg?style=for-the-badge&logo=jenkins&logoColor=white)](https://www.jenkins.io/)
[![GitHub Actions](https://img.shields.io/badge/github%20actions-black.svg?style=for-the-badge&logo=githubactions&logoColor=white)](https://github.com/features/actions)
[![Google Cloud](https://img.shields.io/badge/GoogleCloud-%234285F4.svg?style=for-the-badge&logo=google-cloud&logoColor=white)](https://cloud.google.com/)
[![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)](https://aws.amazon.com/)
[![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
[![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)](https://www.python.org)
[![Helm](https://img.shields.io/badge/helm-green?style=for-the-badge&logo=helm&logoColor=purple)](https://helm.sh/)
[![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![Flyway](https://img.shields.io/badge/flyway-white?style=for-the-badge&logo=flyway&logoColor=red)](https://flywaydb.org/)
 

The Advanced Cloud project is a comprehensive solution for building, deploying, and managing cloud-native applications. It incorporates various tools and components to automate infrastructure provisioning, application deployment, health check management, database migration, and more.


## Components Overview

### 1. Web Application:
   - **Description**: The FastAPI-based web application serves as the core of the project, offering HTTP health check functionalities and health check result management.
   - **Key Features**:
     - **HTTP Health Checks**: Allows users to define, execute, and monitor HTTP health checks for various endpoints.
     - **Custom Resource Definitions (CRDs)**: Integrates with Kubernetes CRDs to dynamically configure and manage health checks within Kubernetes clusters.
     - **Database Integration**: Stores health check results in a PostgreSQL database, ensuring persistence and historical tracking of health status changes.
     - **Automation**: Seamlessly integrates with CI/CD pipelines for continuous deployment and updates.

### 2. Kubernetes Cluster on GCP:
   - **Description**: Terraform configurations facilitate the setup of a Google Cloud Platform (GCP) project, networking resources, and a Kubernetes cluster on Google Kubernetes Engine (GKE).
   - **Key Features**:
     - **Infrastructure Provisioning**: Automates the creation of GCP projects, VPCs, subnets, and other networking resources.
     - **Kubernetes Cluster Deployment**: Sets up a scalable and resilient Kubernetes cluster on GKE, leveraging GCP's managed Kubernetes service.
     - **Security Configuration**: Implements security best practices such as role-based access control (RBAC) and network policies to ensure a secure environment.
     - **Integration with Helm Charts**: Deploys applications onto the Kubernetes cluster using Helm charts, streamlining deployment and management processes.

### 3. Health Check Results Management:
   - **Description**: A Node.js application responsible for retrieving data from a Kafka topic and storing it in a PostgreSQL database, facilitating the management of health check results.
   - **Key Features**:
     - **Data Processing**: Consumes messages from a Kafka topic containing health check results and processes them for storage in the database.
     - **Database Storage**: Stores health check results in a PostgreSQL database, enabling efficient retrieval and analysis of historical health status data.
     - **Integration with Web Application**: Integrates with the web application to provide comprehensive health check management capabilities.

### 4. Database Migration Using Flyway:
   - **Description**: Flyway is utilized for managing database schema changes and version control within the project.
   - **Key Features**:
     - **Schema Migration**: Handles database schema changes across different environments, ensuring consistency and reliability.
     - **Version Control**: Tracks and manages database schema versions, enabling seamless migration between different releases of the application.
     - **Integration with CI/CD Pipeline**: Integrated into the deployment pipeline to automate database schema migration during application updates.

### 5. AMI-Jenkins Configuration:
   - **Description**: Packer configurations for creating an Amazon Machine Image (AMI) for Jenkins, coupled with Docker and Jenkins Configuration as Code.
   - **Key Features**:
     - **Automated AMI Creation**: Utilizes Packer to automate the creation of Jenkins AMIs with pre-configured Docker and Jenkins settings.
     - **Infrastructure as Code**: Implements Jenkins Configuration as Code to define and manage Jenkins configurations using code rather than manual interventions.
     - **Local Development Environment**: Enables developers to run Jenkins locally using Docker Compose for testing and development purposes.

### 6. Multi-Chart Kubernetes Helm Repository:
   - **Description**: A collection of Helm charts for deploying various components such as Kafka, PostgreSQL, Istio, and a web application with PostgreSQL.
   - **Key Features**:
     - **Modular Deployment**: Provides Helm charts for deploying individual components as well as complex multi-component applications.
     - **Configuration Flexibility**: Offers customizable values.yaml files for configuring Helm charts according to specific requirements.
     - **Infrastructure Orchestration**: Facilitates the deployment and management of Kubernetes resources using Helm charts, simplifying the orchestration of complex applications.

### 7. HealthCheckReconciler:
   - **Description**: A Kubernetes controller developed to reconcile HealthCheck objects, ensuring the creation and management of CronJobs for health checks.
   - **Key Features**:
     - **Automated Health Check Management**: Automatically creates and updates CronJobs based on HealthCheck objects to execute health checks at defined intervals.
     - **Dynamic Configuration**: Utilizes Kubernetes Custom Resource Definitions (CRDs) to dynamically configure and manage health checks within Kubernetes clusters.
     - **Real-time Status Updates**: Updates the status of HealthCheck objects based on the execution results of CronJobs, providing real-time insights into health check statuses.

### 8. Infra Jenkins:
   - **Description**: Infrastructure as Code (IaC) automation tool for managing the project's infrastructure, including provisioning, configuration, and maintenance tasks.
   - **Key Features**:
     - **Automated Infrastructure Provisioning**: Utilizes Jenkins pipelines to automate the provisioning of cloud infrastructure using Terraform.
     - **Configuration Management**: Implements Jenkins Configuration as Code (JCasC) to define and manage Jenkins configurations as code, ensuring consistency and reproducibility.
     - **Continuous Monitoring and Maintenance**: Sets up monitoring and maintenance tasks to ensure the health and performance of infrastructure resources over time.
     - **Integration with CI/CD Pipeline**: Integrates with the CI/CD pipeline to automate infrastructure deployment alongside application deployment processes.

### 9. Deployment Pipeline (Including Infra Jenkins):
   - **Description**: The deployment pipeline orchestrates the end-to-end process of building, testing, deploying, and managing both application code and infrastructure.
   - **Key Features**:
     - **Continuous Integration and Deployment (CI/CD)**: Automates the build, test, and deployment processes for application code and infrastructure changes.
     - **Infrastructure Provisioning**: Leverages Infra Jenkins to provision and configure cloud infrastructure using Terraform scripts, ensuring consistency and repeatability.
     - **Application Deployment**: Utilizes CI/CD pipelines to deploy application updates to Kubernetes clusters using Helm charts, ensuring seamless and reliable deployments.
     - **Monitoring and Maintenance**: Incorporates monitoring and maintenance tasks into the pipeline to ensure the health, performance, and security of deployed resources.
     - **Integration with Version Control**: Triggers pipeline execution upon code changes in version control systems (e.g., GitHub), ensuring automated and synchronized deployment workflows.

## Conclusion
The Advanced Cloud project encompasses a comprehensive set of components and tools designed to facilitate cloud-native development, deployment, and management. By leveraging modern technologies and best practices, the project offers scalable, resilient, and efficient solutions for building and operating cloud-based applications. It enables developers to focus on delivering value-added features while abstracting away the complexities of infrastructure management and deployment processes.
