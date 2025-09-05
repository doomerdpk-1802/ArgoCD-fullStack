# ArgoCD-fullStack

A complete full-stack application template with GitOps deployment using ArgoCD. This repository demonstrates how to structure, containerize, and deploy a web application using modern DevOps practices and continuous delivery to Kubernetes clusters.

## Features

- **Full-Stack Application**: Contains both frontend (`public/`) and backend (`src/`) source code.
- **Multiple Dockerfiles**: Provides Dockerfiles for building both the source (development) and production-ready (public) images.
- **GitOps-Ready**: Designed for use with ArgoCD for automated, declarative deployment to Kubernetes.
- **CI/CD Friendly**: Includes configuration and folder structure compatible with modern CI/CD pipelines.
- **Best Practices**: Uses `.dockerignore` and `.gitignore` for clean builds and version control.

## Repository Structure

- `src/` - Source code for the backend service(s)
- `public/` - Static files or frontend assets
- `.github/` - GitHub Actions and workflow configuration
- `Dockerfile-src` - Dockerfile for backend/source development
- `Dockerfile-public` - Dockerfile for production/public deployment
- `.dockerignore`, `.gitignore` - Ignore patterns for Docker and Git

## Getting Started

### Prerequisites

- [Docker](https://www.docker.com/)
- [Kubernetes](https://kubernetes.io/)
- [ArgoCD](https://argo-cd.readthedocs.io/en/stable/)
- (Optional) [Node.js](https://nodejs.org/) for local development

### Build & Run Locally

1. Clone the repository:
    ```bash
    git clone https://github.com/doomerdpk-1802/ArgoCD-fullStack.git
    cd ArgoCD-fullStack
    ```
2. Build and run using Docker:
    ```bash
    docker build -f Dockerfile-src -t myapp-dev .
    docker run -p 3000:3000 myapp-dev
    ```
    Or for production:
    ```bash
    docker build -f Dockerfile-public -t myapp-prod .
    docker run -p 80:80 myapp-prod
    ```

### Deploy with ArgoCD

1. Push your desired image to a registry.
2. Create/update your Kubernetes manifests to reference the image.
3. Connect your repo to ArgoCD and create an Application CRD pointing to the manifests.
4. ArgoCD will sync and deploy your application automatically.

> For more details, see the [ArgoCD documentation](https://argo-cd.readthedocs.io/en/stable/).
