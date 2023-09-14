# Automated Web Deployment and Monitoring Project
![Web-App-Architecture](https://github.com/Ab-D-ev/test-monitor-devops/assets/88940690/63e2b8c9-bd98-4c74-8d2a-936fd21d53da)

A simple static website deployment with Continuous Integration, Continuous Deployment, Testing and Monitoring All-in-one (Using Jenkins, Docker, Git , Python, Loki and Grafana)
## Usage
### **1. Version Control (GitHub):**

1. **Create a GitHub Repository:**
    - Create a new GitHub repository to host your web application code.
    - Push your web application code (HTML, CSS, JavaScript) to this repository.

### **2. Continuous Integration (CI) with Jenkins:**

1. **Set Up Jenkins:**
    - Install and configure Jenkins on a server or a cloud-based machine.
    - Install necessary plugins such as Git, Docker, and any additional plugins you may need.
2. **Create a Jenkins Job:**
    - Create a new Jenkins job for your web application CI process.
    - Configure the job to pull code from your GitHub repository.
3. **Build and Test:**
    - In your Jenkins job configuration, define build steps to:
        - Clone the repository.
        - Build the web application (e.g., copying files to a build directory).
        - Run basic tests (e.g., HTML/CSS validation) using relevant tools (e.g., HTML Validator, CSSLint).
        - Archive build artifacts (e.g., ZIP or tar.gz files).
4. **Configure Post-Build Actions:**
    - In Jenkins, configure post-build actions to archive and publish the build artifacts.
    - Optionally, trigger deployments to specific environments if all tests pass.

### **3. Continuous Deployment (CD) with Docker:**

1. **Create a Dockerfile:**
    - In your web application code repository, create a **`Dockerfile`** to define how your application should be packaged into a Docker container.
    - Install a simple web server like Nginx to serve your static website.
2. **Automate Docker Build:**
    - Configure your CI/CD pipeline to automatically build a Docker image whenever changes are pushed to the main branch.
    - Push the Docker image to a container registry (e.g., Docker Hub).
3. **Deploy with Docker:**
    - Deploy the Docker container to a simple web server (e.g., AWS EC2, DigitalOcean Droplet) or cloud storage (e.g., AWS S3) whenever changes are pushed to the main branch.
    - Use a deployment script or a CI/CD tool's deployment functionality to automate this process.

### **4. Monitoring with Loki and Grafana:**

1. **Install Loki and Grafana:**
    - Set up Loki, a log aggregation system, and Grafana, a monitoring and visualization platform, on your server or a cloud-based instance.
2. **Configure Logging:**
    - In your web application and deployment scripts, incorporate logging statements.
    - Configure your web server (e.g., Nginx) to log access and error information.
3. **Integrate Loki and Grafana:**
    - Configure your applications and deployment scripts to send logs to Loki.
    - Set up Grafana dashboards to visualize and analyze logs and deployment metrics.
    - Grafana can be configured to query logs from Loki and display them in a user-friendly way.
4. **Alerting (Optional):**
    - Configure alerts in Grafana to notify you of specific events or issues, such as deployment failures or abnormal application behavior.

### **5. Final Steps:**

1. **Test Your CI/CD Pipeline:**
    - Push changes to your GitHub repository's main branch and observe the Jenkins CI/CD pipeline in action.
    - Monitor the logs and metrics in Grafana to ensure everything is functioning as expected.
2. **Documentation:**
    - Document your CI/CD pipeline setup, including GitHub repository, Jenkins job configurations, Dockerfile, and Loki/Grafana setup.
    - This documentation will help your team understand and maintain the pipeline.
3. **Ongoing Maintenance:**
    - Regularly review and update your CI/CD pipeline as your web application evolves.
    - Monitor and fine-tune your Loki and Grafana configurations to meet your monitoring needs.
