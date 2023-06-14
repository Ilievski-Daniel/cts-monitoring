# CTS Monitoring

This repository provides a comprehensive monitoring solution that utilizes Prometheus and Grafana to collect, store, visualize metrics from Kubernetes.

This solution comes with 2 already configured Grafana dashboards, you can access them under the General folder after setup.

## Prerequisites

Before proceeding with the installation, ensure that you have the following prerequisites:

Kubernetes cluster is set up and configured.
kubectl command-line tool is installed and configured to access your Kubernetes cluster.

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

    - This will first create Kube State Metrics objects that are required so we can get more in-depth metrics for the Kubernetes cluster.
    - And then it will deploy the Prometheus server that has all the configurations already completed.

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

- You can then get EXTERNAL-IP for the Grafana Server that you can access.

- You can simply access the Grafana server by typing: ```admin``` ```admin``` in both email and password fields, make sure to change it when you will get asked to do so.

- Make sure to check the 2 already pre-defined Grafana Dashboards, one for general monitoring of the Kubernetes cluster and the second one for all the pods that are in the Kubernetes cluster (including the CTS Backend Application pods), these pre-defined dashboards are located under the General folder.

## Contact
For any questions or inquiries, please contact: [Daniel Ilievski](https://www.linkedin.com/in/danielilievski/)