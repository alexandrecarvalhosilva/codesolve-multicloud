# Objetivo do Projeto

Criar uma plataforma “CODESOLVE - MULTI-CLOUD” multi-tenant onde cada cliente recebe uma stack Kubernetes completa e isolada nas pincipais Clauds. (Azure, AWS e GCP)

Características:
- Control Plane local com Minikube
- Infra provisionada via Crossplane
- CD GitOps com ArgoCD
- CI interno com Tekton
- Catálogo padronizado de add-ons
- Base para UI administrativa futura
