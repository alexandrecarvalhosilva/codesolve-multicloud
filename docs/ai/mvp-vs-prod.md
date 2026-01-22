# MVP vs Produção — Matriz de Decisão

Este documento elimina ambiguidade e opinião.
Ele define **o que muda de MVP para Produção**.

---

## Azure

| Item | MVP | Produção |
|----|----|----|
| Resource Group | Único | Segregado |
| Rede | Básica | Segmentada |
| Private Link | Parcial | Obrigatório |
| Backup | Básico | Automatizado |
| Alta Disponibilidade | Opcional | Obrigatória |

---

## AKS

| Item | MVP | Produção |
|----|----|----|
| Node Pools | 1 ou 2 | System + User |
| Autoscaler | Default | Customizado |
| RBAC | Básico | Integrado a IdP |
| Outbound | Padrão | Controlado |

---

## Crossplane

| Item | MVP | Produção |
|----|----|----|
| Managed Resources | Diretos | XRD + Composition |
| Parâmetros | Limitados | Contrato formal |
| Reuso | Baixo | Alto |

---

## ArgoCD

| Item | MVP | Produção |
|----|----|----|
| Application | Simples | ApplicationSet |
| AppProjects | Opcional | Obrigatório |
| RBAC | Básico | Restritivo |

---

## Tekton

| Item | MVP | Produção |
|----|----|----|
| Pipeline | Simples | Completa |
| Triggers | Manual | Git Webhook |
| Segurança | Básica | Chains / Assinatura |

---

## Observabilidade

| Item | MVP | Produção |
|----|----|----|
| Métricas | Básicas | SLOs |
| Logs | Centralizados | Retenção definida |
| Alertas | Críticos | Por sintoma |

---

## Segurança

| Item | MVP | Produção |
|----|----|----|
| RBAC | Básico | Mínimo privilégio |
| NetworkPolicy | Opcional | Obrigatória |
| Auditoria | Parcial | Completa |

---

## FinOps

| Item | MVP | Produção |
|----|----|----|
| Visibilidade | Global | Por tenant |
| Otimização | Manual | Contínua |
| Alertas de custo | Não | Sim |
