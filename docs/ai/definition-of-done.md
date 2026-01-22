# Definition of Done (DoD) — Plataforma Cloud-Native

Este documento define **quando um entregável é considerado PRONTO**.
Nada é considerado concluído se **qualquer item abaixo estiver pendente**.

---

## 1. Arquitetura

- [ ] Visão geral documentada
- [ ] Arquitetura detalhada documentada
- [ ] Separação clara entre:
  - Control Plane
  - Infraestrutura
  - Kubernetes
  - CI
  - CD
- [ ] Decisões arquiteturais justificadas
- [ ] Diferença entre MVP e Produção explicitada

---

## 2. Azure / Infraestrutura

- [ ] Landing Zone definida por tenant
- [ ] Recursos privados por padrão
- [ ] Ordem de provisionamento documentada
- [ ] Sem hardcode de IDs ou segredos
- [ ] Custos estimados documentados
- [ ] Tags obrigatórias aplicadas

---

## 3. Kubernetes / Crossplane

- [ ] Versões declaradas (K8s, Crossplane, Providers)
- [ ] Managed Resources completos e válidos
- [ ] Nenhum recurso provisionado fora do Crossplane
- [ ] Separação clara de infra (rede, cluster, dados)
- [ ] Caminho de evolução para XRD + Composition documentado

---

## 4. GitOps (ArgoCD)

- [ ] Git como única fonte de verdade
- [ ] Applications/ApplicationSets definidos
- [ ] AppProjects configurados (produção)
- [ ] Multi-tenant isolado
- [ ] Sem deploy manual
- [ ] Rollback possível e documentado

---

## 5. CI (Tekton)

- [ ] CI separado de CD
- [ ] Pipelines declarativas
- [ ] Build de imagens imutáveis
- [ ] Tags rastreáveis (commit SHA)
- [ ] Secrets seguros
- [ ] Integração com registry validada

---

## 6. Observabilidade

- [ ] Métricas básicas coletadas
- [ ] Logs centralizados
- [ ] Alertas críticos definidos
- [ ] Dashboards com objetivo claro
- [ ] SLO definido (produção)

---

## 7. Segurança & Compliance

- [ ] RBAC restritivo
- [ ] Isolamento entre tenants
- [ ] Secrets protegidos
- [ ] Auditoria habilitada
- [ ] Anti-padrões inexistentes

---

## 8. FinOps

- [ ] Custos visíveis
- [ ] Tags aplicadas
- [ ] Requests/Limits definidos
- [ ] Autoscaling configurado
- [ ] Responsável pelo custo definido

---

## 9. Operação

- [ ] Passo a passo executável
- [ ] Validações documentadas
- [ ] Runbooks iniciais criados
- [ ] Evidências de funcionamento

---

👉 **Se qualquer item falhar, o trabalho NÃO está concluído.**
