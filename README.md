# CI/CD End-to-End Jenkins Project (with AWS EC2)

This project demonstrates a complete CI/CD pipeline deployed on AWS EC2, using Jenkins, Maven, Nexus, Tomcat, SonarQube, and GitHub. It automates building, testing, code analysis, artifact storage, and deployment for Java applications, leveraging AWS EC2 for scalable and reliable infrastructure.

## Tools & Technologies

- **AWS EC2**: Cloud servers hosting Jenkins, Tomcat, SonarQube, Nexus, and other tools.
- **Jenkins**: Orchestrates the CI/CD pipeline.
- **Maven**: Manages build lifecycle and dependencies.
- **Nexus**: Stores build artifacts and dependencies.
- **Tomcat**: Deploys Java web applications.
- **SonarQube**: Performs code quality analysis.
- **GitHub**: Source code repository and version control.

## Pipeline Flow

1. **Source Code Management**
   - Developers push code to GitHub.

2. **Continuous Integration (Jenkins on EC2)**
   - Jenkins (running on AWS EC2) detects changes and triggers the pipeline.

3. **Build & Test (Maven)**
   - Maven compiles the code, runs tests, and packages the application.

4. **Code Analysis (SonarQube on EC2)**
   - Jenkins triggers SonarQube analysis for code quality checks.

5. **Artifact Storage (Nexus on EC2)**
   - Maven uploads build artifacts to Nexus hosted on EC2.

6. **Deployment (Tomcat on EC2)**
   - Jenkins deploys the packaged artifact to Tomcat running on EC2.

## Prerequisites

- AWS account and EC2 setup (AMAZON LINUX preferred)
- Security groups configured for access to required ports (Jenkins: 8080, SonarQube: 9000, Nexus: 8081, Tomcat: 8080)
- Jenkins, Maven, Nexus, SonarQube, Tomcat installed on EC2
- GitHub repository
- Java installed on all EC2 instances

## Setup Instructions

### 1. Launch AWS EC2 Instances

- Create EC2 instances for each tool or combine as needed.
- Assign elastic IPs for reliable access.
- Configure security groups to allow SSH and tool-specific ports.

### 2. Install Tools

- SSH into EC2 instances and install Jenkins, Maven, Nexus, SonarQube, and Tomcat.
- Refer to official documentation for installation steps.

### 3. Configure Jenkins (on EC2)

- Install required plugins (GitHub, Maven, SonarQube, Nexus).
- Set up credentials for GitHub, Nexus, SonarQube.
- Create pipeline jobs and integrate with your GitHub repository.

### 4. Configure Maven

- Ensure `pom.xml` contains Nexus and SonarQube plugins.
- Configure Maven settings.xml for Nexus repository.

### 5. Configure SonarQube & Nexus (on EC2)

- Set up projects, tokens, and repositories.
- Add integration tokens to Jenkins.

### 6. Configure Tomcat (on EC2)

- Deploy war/jar files via Jenkins.
- Secure Tomcat with strong credentials.

