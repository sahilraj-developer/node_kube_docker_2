# Node.js Kubernetes App

A simple Node.js Express application containerized with Docker and deployed to Kubernetes with GitHub Actions CI/CD.

## Local Development

1. Install dependencies:
   ```bash
   npm install
   ```

2. Run the app:
   ```bash
   npm start
   ```

3. Run tests:
   ```bash
   npm test
   ```

## Docker

Build the Docker image:
```bash
docker build -t node-k8s-app .
```

Run the container:
```bash
docker run -p 3000:3000 node-k8s-app
```

## Kubernetes

Deploy to Kubernetes:
```bash
kubectl apply -f k8s/
```

Access the app at: http://localhost:30001 (NodePort)

## GitHub Actions

The CI/CD pipeline will:
- Run tests on push/PR
- Build and push Docker image
- Deploy to Kubernetes

Make sure to set the following secrets in your GitHub repo:
- DOCKER_USERNAME
- DOCKER_PASSWORD
- KUBE_CONFIG

Update the image in k8s/deployment.yaml to your Docker registry.

## Current Status

- ✅ Node.js app created and tested
- ✅ Docker image built and tested
- ✅ Kubernetes deployment running
- ✅ GitHub Actions workflow configured