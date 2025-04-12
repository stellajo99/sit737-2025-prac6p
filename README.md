# Kubernetes Deployment (Docker Desktop)

## Docker Image
[https://hub.docker.com/r/stellajo99/sit737-2025-prac5p](https://hub.docker.com/r/stellajo99/sit737-2025-prac5p)

## Kubernetes Setup
Using Docker Desktop with Kubernetes enabled.

### File Descriptions
| File / Folder | Description |
|---------------|-------------|
| `deployment.yaml` | Kubernetes deployment configuration for the Node.js app. |
| `service.yaml` | Exposes the app externally using a NodePort service on port 30080. |
| `Dockerfile` | Used to build the Node.js app image (reference only, image is already on Docker Hub for this task). |
| `README.md` | Documentation outlining setup, deployment steps, and project details. |
| `docker-compose.yaml` | Defines multi-container app setup for local Docker testing or development. |
| `screenshots/` | Folder containing evidence of successful deployment and app access. |
| ├ `kubectl-get-pods.png` | Screenshot showing pod status via `kubectl get pods`. |
| ├ `kubectl-get-services.png` | Screenshot showing service status via `kubectl get services`. |
| └ `app-ui-screenshot.png` | Screenshot showing the app running at `localhost:30080`. |

## How to Deploy

### Prerequisites
- Docker Desktop installed with Kubernetes enabled
- kubectl installed and configured to use Docker Desktop's Kubernetes

### Deployment Steps

1. Clone the repository:
```bash
git clone https://github.com/stellajo99/sit737-2025-prac6p.git
cd sit737-2025-prac6p
```

2. Apply the deployment and service YAML files:
```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

3. Check the status:
```bash
kubectl get pods
kubectl get services
```

4. Open your browser and visit:
```
http://localhost:30080
```
Example: http://localhost:30080/divide?num1=20&num2=4

You should see the application running (e.g., text output or UI).

## Screenshots
Screenshots demonstrating the deployment and interaction with the application are included in the `screenshots/` folder:

- `kubectl-get-pods.png`: Shows running pods
- `kubectl-get-services.png`: Shows service with NodePort exposed
- `app-ui-screenshot.png`: Shows the application accessed in the browser

## Notes
- The application uses a Node.js image hosted on Docker Hub
- No additional configuration (e.g., secrets or config maps) required for this deployment


