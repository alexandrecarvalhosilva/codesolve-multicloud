# Matriz MVP vs Produção — Multi-Cloud

## Infraestrutura

| Item | MVP | Produção |
|----|----|----|
| Alta disponibilidade | Opcional | Obrigatória |
| Private networking | Parcial | Completa |
| Backup | Manual | Automatizado |
| Multi-AZ | Não | Sim |

---

## Kubernetes

| Item | MVP | Produção |
|----|----|----|
| Node pools | 1 | System + Apps |
| Autoscaler | Básico | Customizado |
| RBAC | Simples | Integrado a IdP |

---

## Multi-Cloud

| Item | MVP | Produção |
|----|----|----|
| Cloud única | Sim | Não |
| XRD única | Opcional | Obrigatória |
| Custos segregados | Básico | Completo |
