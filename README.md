# CTS Monitoring

This repository provides a comprehensive monitoring solution that utilizes Prometheus and Grafana to collect, store, and visualize metrics from Kubernetes.

The monitoring configuration comes with 2 pre-configured Grafana dashboards. You can access them under the General folder after setup.
## Prerequisites

Before proceeding with the installation, ensure that you have the following prerequisites:

Kubernetes cluster is set up and configured.
The kubectl command-line tool is installed and configured to access your Kubernetes cluster.

## Monitoring Architecture

![Monitoring Design](./Images/monitoring.png?raw=true)

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/Ilievski-Daniel/cts-monitoring
   ```

2. Change your directory to acess Prometheus configuration files:

   ```bash
   cd cts-backend/Prometheus
   ```

3. Apply Kube State Metrics and Prometheus:

    ```
    kubectl apply -f kube-state-metrics.yaml -f prometheus.yaml
    ```

    - Kube State Metrics objects are required to obtain more in-depth metrics for the Kubernetes cluster.
    
    - The Prometheus server has all the necessary configurations and is ready to scrape data from the Kubernetes cluster.

4. Change your directory to acess Grafana configuration files:

    ```
    cd ../Grafana
    ```

5. Apply Grafana Server:

    ```
    kubectl apply -f grafana.yaml
    ```

6. Check if all the resources are created:

    ```sh
    kubectl get all -n monitoring
    ```

- You can then obtain the EXTERNAL-IP for the Grafana Server that you can access.

- To access the Grafana server, simply use the credentials "admin" for both the email and password fields. Make sure to change these credentials when prompted to do so.

- Make sure to check the 2 pre-defined Grafana Dashboards: one for general monitoring of the Kubernetes cluster and the second one for all the pods in the Kubernetes cluster (including the CTS Backend Application pods). 

- <b>These pre-defined dashboards are located under the General folder.</b>

## Contact
For any questions or inquiries, please contact: [Daniel Ilievski](https://www.linkedin.com/in/danielilievski/)