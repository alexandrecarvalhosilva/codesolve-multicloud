# Escopo de Arquitetura — Plataforma Multi-Cloud

## Princípios Arquiteturais

1. **Tenant não conhece cloud**
2. **Contrato único, implementação múltipla**
3. **Infra como produto**
4. **Git como fonte única da verdade**
5. **Separação clara de responsabilidades**

---

## Modelo Conceitual

```

Tenant Contract (XRD)
|
v
Crossplane Composition
|             |
Azure           AWS

```

- O tenant declara **o que precisa**
- A plataforma decide **como implementar**
- Azure e AWS são apenas implementações

---

## Clouds Suportadas

| Cloud | Kubernetes | Provider |
|----|----|----|
| Azure | AKS | provider-azure |
| AWS | EKS | provider-aws |

---

## Componentes Comuns (Agnósticos)

- ArgoCD
- Tekton
- Observabilidade
- Segurança
- FinOps

Esses componentes **não mudam entre clouds**.