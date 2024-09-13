# Panda App Deployment

This README provides instructions on how to deploy the Panda App using Kubernetes.

## Prerequisites

- Kubernetes cluster
- kubectl command-line tool
- Git

## Deployment Steps

1. Clone the repository:
   ```
   git clone https://github.com/panda-preworks/Helm-app
   ```

2. Navigate to the cloned directory:
   ```
   cd Helm-app
   ```

3. Apply the Kubernetes manifests:
   ```
   kubectl apply -f .
   ```
   This command will create the necessary applications and services.

4. Expose the frontend service:
   To make the frontend service accessible outside the virtual machine, use the following command:
   ```
   kubectl port-forward --address 0.0.0.0 service/pandaapp-frontend 5000:5000
   ```
   This will forward the service to port 5000 on all network interfaces.

## Accessing the Application

After completing the steps above, you should be able to access the frontend of the application by navigating to `http://<your-vm-ip>:5000` (if using minikube vagrant ip - 192.168.44.45) in your web browser.
