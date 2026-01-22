# Objetivo do Projeto

Criar uma plataforma “caixinha” multi-tenant onde cada cliente recebe uma stack Kubernetes completa e isolada na Azure.

Características:
- Control Plane local com Minikube
- Infra provisionada via Crossplane
- CD GitOps com ArgoCD
- CI interno com Tekton
- Catálogo padronizado de add-ons
- Base para UI administrativa futura
