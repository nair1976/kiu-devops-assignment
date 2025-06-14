# kiu-devops-assignment
Desafío técnico DevOps para Kiu
# Kiu DevOps Assignment

##  Objetivo

Este repositorio contiene una implementación simplificada del desafío DevOps solicitado por Kiu: el despliegue y escalado de una aplicación en Kubernetes utilizando Terraform en Microsoft Azure. Eljo Azure porque es la nube con la que estoy trabajando actualmente.

##  Arquitectura

- **Cloud Provider:** Azure
- **Infraestructura creada con Terraform:**
  - Azure Kubernetes Service (AKS)
  - Networking (VNet + Subnets)
- **Aplicación:** NGINX desplegado en Kubernetes como ejemplo
- **Base de datos:** PostgreSQL simulado dentro del clúster como Deployment
- **Exposición pública:** Ingress + LoadBalancer
- **Escalado:** Horizontal Pod Autoscaler para la aplicación

---

## Despliegue

### 1. Infraestructura (Terraform), Esto crea el clúster AKS en Azure y genera un archivo kubeconfig que permite conectarse al clúster con kubectl

```bash
cd terraform
terraform init
terraform apply

### 2. Conecta el cluster con kubectl y verfica la conexión 

export KUBECONFIG=./kubeconfig
kubectl get nodes

### 3. Aplica los yaml, con los manifiestos de Kubernetes

cd ../k8s
kubectl apply -f .


