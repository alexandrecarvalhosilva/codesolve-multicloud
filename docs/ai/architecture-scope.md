# Arquitetura Geral

## Visão
- Cluster de controle local (Minikube)
- Clusters AKS por tenant
- Clusters AWS por tenant
- Git central como fonte de verdade
- GitOps full com ArgoCD
- Infra reconciliada continuamente via Crossplane

## Conceito
1 tenant = 1 caixinha Kubernetes isolada

## Responsabilidades
- Control Plane: provisionamento e governança
- Tenant: execução de workloads
