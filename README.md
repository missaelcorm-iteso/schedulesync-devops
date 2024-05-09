# ScheduleSync - DevOps


## Introduction

This repository provides a structured approach for managing the CI/CD (Continuous Integration/Continuous Delivery) pipeline for a Node.js application along with its monitoring and infrastructure deployments using:

* **Node.js Application:** Your Node.js application code resides in a separate repository [`ScheduleSync`](https://github.com/missaelcorm-iteso/ScheduleSync) for clarity.
* **DevOps and Infrastructure:** A dedicated repository (`schedulesync-devops`) houses configuration files for CI/CD pipelines, Kubernetes deployments, and monitoring tools:
    * **Prometheus Operator:** Leverages the Prometheus Operator for easier Prometheus deployment and management.
    * **Service Monitor (kubernetes/)**: Defines which services your deployed Prometheus instance should scrape metrics from using a Service Monitor YAML file within the `kubernetes/manifests` directory.
* **Grafana (Optional):** Configuration files for Grafana dashboards (`grafana/` - optional) are included for monitoring your application's performance.
* **CI with GitHub Actions:** GitHub Actions are used to build Docker images and potentially run tests within the CI pipeline. A dedicated directory (`github-actions/`) stores the workflow definitions.
* **CD with Argo CD:** Argo CD is used to manage Kubernetes deployments and keep your cluster in sync with the desired state defined in Git (using the `kubernetes/manifests` directory).

This structure promotes separation of concerns, facilitates clear documentation, and streamlines the development, deployment, and monitoring process for your Node.js application.

**Getting Started:**

This README provides an overview of the project structure, instructions on using GitHub Actions and Argo CD, and details on managing the infrastructure components, including the Service Monitor for Prometheus.

**Benefits:**

* **Improved Workflow:** Clear separation of application code, CI/CD pipelines, and infrastructure.
* **Automated Deployments:** Argo CD automatically deploys your application and Prometheus Operator to Kubernetes.
* **Streamlined Monitoring:** Prometheus Operator simplifies Prometheus management, and the Service Monitor ensures your application metrics are scraped.  (Optional) Grafana dashboards help you visualize the collected metrics.
* **Version Control:** GitOps principles ensure your deployments are traceable and reproducible.

By leveraging GitHub Actions for CI, Argo CD for CD, and the Prometheus Operator with Service Monitors, this project offers a modern and efficient approach to managing your Node.js application's development lifecycle and monitoring.

### Pipeline Workflow:
![alt text](attachments/pipeline.png)