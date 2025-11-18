---
name: devops-tools
description: Master DevOps and infrastructure tools including Docker, Kubernetes, CI/CD pipelines, cloud platforms, and infrastructure as code. Build reliable, scalable, and secure systems.
---

# DevOps Tools & Infrastructure

## Quick Start

### Docker Basics
```dockerfile
FROM node:18-alpine

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

EXPOSE 3000
CMD ["node", "server.js"]
```

### Kubernetes Deployment
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: web-app
spec:
  replicas: 3
  selector:
    matchLabels:
      app: web-app
  template:
    metadata:
      labels:
        app: web-app
    spec:
      containers:
      - name: app
        image: myapp:1.0
        ports:
        - containerPort: 3000
```

### GitHub Actions CI/CD
```yaml
name: Deploy

on:
  push:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Build Docker image
        run: docker build -t myapp:${{ github.sha }} .
      - name: Push to registry
        run: docker push myapp:${{ github.sha }}
```

## Core Technologies

| Tool | Purpose | Use Case |
|------|---------|----------|
| Docker | Containerization | Application packaging |
| Kubernetes | Orchestration | Container management at scale |
| Terraform | Infrastructure as Code | Cloud resource provisioning |
| Ansible | Configuration Management | Server configuration automation |
| Jenkins | CI/CD | Automated testing & deployment |
| GitHub Actions | CI/CD | Built-in GitHub workflows |
| Prometheus | Monitoring | Metrics collection |
| ELK Stack | Logging | Log aggregation & analysis |

## Key Topics

### Docker Mastery
- Image layers & optimization
- Multi-stage builds
- Docker Compose for orchestration
- Security best practices
- Registry management
- Performance tuning
- Dockerfile optimization

### Kubernetes Deep Dive
- Pods, Services, Deployments
- StatefulSets & DaemonSets
- Persistent volumes
- ConfigMaps & Secrets
- Ingress & networking
- Resource limits & quotas
- Health checks & auto-scaling

### CI/CD Pipelines
- Build automation
- Automated testing in pipelines
- Artifact management
- Deployment strategies (Blue-Green, Canary)
- Release automation
- Pipeline monitoring
- GitOps workflows

### Infrastructure as Code
- Terraform providers & modules
- CloudFormation templates
- Ansible playbooks
- Version control for infrastructure
- Environment parity
- Disaster recovery

### Cloud Platforms

**AWS**: EC2, RDS, S3, Lambda, CloudFormation
**GCP**: Compute Engine, Cloud Run, BigQuery
**Azure**: Virtual Machines, App Service, Cosmos DB

### Monitoring & Observability
- Metrics (Prometheus, Grafana)
- Logs (ELK, Splunk, DataDog)
- Traces (Jaeger, Zipkin)
- Alerting strategies
- SLOs & error budgets
- Performance baselines

### Security

- Container scanning
- Secret management (Vault)
- Network policies
- RBAC (Role-Based Access Control)
- Compliance & auditing
- Supply chain security

## Best Practices

1. **Container Design**
   - One process per container
   - Small, focused images
   - Health check implementation
   - Non-root user execution
   - Immutable infrastructure

2. **Kubernetes Management**
   - Namespaces for isolation
   - Resource requests & limits
   - Network policies
   - RBAC configuration
   - Regular backups

3. **CI/CD**
   - Automate everything
   - Fast feedback loops
   - Parallel testing
   - Artifact versioning
   - Deployment safety checks

4. **Infrastructure Code**
   - Modular design
   - Version control
   - Environment consistency
   - Documentation
   - Testing infrastructure code

## Advanced Resources

- Docker: https://docker.com
- Kubernetes: https://kubernetes.io
- Terraform: https://terraform.io
- GitHub Actions: https://github.com/features/actions

## Related Skills

- cloud-platforms - AWS, GCP, Azure services
- ci-cd-pipelines - Pipeline design and automation
- infrastructure-code - Terraform, CloudFormation, Ansible
- monitoring-logging - Observability and troubleshooting
