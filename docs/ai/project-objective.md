# Objetivo do Projeto — Plataforma Multi-Cloud Kubernetes

Este projeto tem como objetivo criar uma **plataforma cloud-native multi-cloud**, capaz de provisionar **stacks Kubernetes completas por tenant**, de forma **padronizada, auditável e escalável**, utilizando:

- **Azure** (AKS)
- **AWS** (EKS)

O provisionamento será realizado de forma **declarativa**, usando:
- **Crossplane** como motor de infraestrutura
- **ArgoCD** como mecanismo GitOps
- **Tekton** como CI cloud-native
- **Observabilidade, Segurança e FinOps integrados desde o início**

---

## Escopo do Projeto

Este projeto cobre:

- Provisionamento de infraestrutura Kubernetes em Azure e AWS
- Criação de ambientes isolados por tenant
- Padronização de rede, segurança e observabilidade
- Base para workloads containerizados e aplicações enterprise
- Preparação para evolução futura (UI, Backstage, catálogo)

---

## Fora do Escopo

Este projeto NÃO cobre:
- Desenvolvimento de aplicações de negócio
- Pipelines específicos de aplicação
- Customizações específicas de clientes fora do contrato padrão
