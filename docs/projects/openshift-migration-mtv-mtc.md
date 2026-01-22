Abaixo está uma **DOCUMENTAÇÃO ESPECÍFICA, COMPLETA e ENTERPRISE** para **criação de um novo projeto fictício** cujo objetivo é **implantar Red Hat OpenShift e migrar workloads virtualizados e containers** usando **MTV (Migration Toolkit for Virtualization)** e **MTC (Migration Toolkit for Containers)**.

O texto foi escrito **para guiar um ESTAGIÁRIO**, mas com **rigor técnico de arquiteto sênior**, explicando:

* o que é o projeto
* quais arquivos alterar
* como criar/ajustar agentes
* como seguir o processo correto
* com referências **oficiais Red Hat**

👉 Salve como:
`docs/projects/openshift-migration-mtv-mtc.md`

---

````md
# Projeto Exemplo — OpenShift + Migração com MTV e MTC (Red Hat)

## 1. Objetivo deste documento

Este documento guia a criação de um **novo projeto padrão**, usando este framework, para um **cenário realista enterprise**:

> Implantação de um **cluster Red Hat OpenShift** e **migração de workloads**:
> - Máquinas Virtuais (VMs) → OpenShift Virtualization (KubeVirt)
> - Containers → OpenShift Kubernetes  
> utilizando ferramentas oficiais da Red Hat:
> - **MTV (Migration Toolkit for Virtualization)**
> - **MTC (Migration Toolkit for Containers)**

O objetivo é ensinar um **estagiário/júnior** a:
- iniciar corretamente um projeto
- ajustar o framework
- criar/estender agentes
- seguir boas práticas Red Hat
- NÃO pular etapas críticas

---

## 2. Contexto do projeto fictício

### Cenário
Empresa fictícia: **ACME Telecom**

Situação atual:
- Datacenter on-premises
- VMware vSphere com dezenas de VMs
- Aplicações containerizadas rodando em:
  - OpenShift 3
  - Kubernetes vanilla
- Necessidade de:
  - Consolidar tudo em OpenShift 4
  - Modernizar sem reescrever aplicações
  - Reduzir risco de migração

---

## 3. Ferramentas oficiais envolvidas

### 3.1 OpenShift Container Platform (OCP)
Plataforma Kubernetes enterprise da Red Hat.

📚 Docs:
- https://docs.openshift.com/container-platform/latest/

---

### 3.2 OpenShift Virtualization
Permite rodar VMs dentro do OpenShift usando KubeVirt.

📚 Docs:
- https://docs.openshift.com/container-platform/latest/virt/about-virt.html

---

### 3.3 MTV — Migration Toolkit for Virtualization
Ferramenta para migrar VMs (ex: VMware) para OpenShift Virtualization.

📚 Docs:
- https://access.redhat.com/documentation/en-us/migration_toolkit_for_virtualization/

---

### 3.4 MTC — Migration Toolkit for Containers
Ferramenta para migrar workloads Kubernetes/OpenShift entre clusters.

📚 Docs:
- https://access.redhat.com/documentation/en-us/migration_toolkit_for_containers/

---

## 4. Passo 1 — Criar o projeto no framework

### 4.1 Criar diretório do projeto

```bash
docs/projects/openshift-migration-mtv-mtc.md
````

### 4.2 Ajustar arquivos obrigatórios

Você DEVE editar:

#### `docs/ai/project-objective.md`

Exemplo:

```md
Objetivo: Implantar OpenShift 4.x e migrar workloads
virtualizados e containers usando MTV e MTC.
```

---

#### `docs/ai/architecture-scope.md`

Definir:

* OpenShift como plataforma alvo
* Migração como foco (não desenvolvimento)
* Ambientes: lab / homologação / produção

---

#### `docs/ai/references.md`

Adicionar:

* Docs OpenShift
* Docs MTV
* Docs MTC
* Docs KubeVirt

---

## 5. Passo 2 — Ajustar ou criar agentes específicos

Neste projeto, **novos agentes são obrigatórios**.

---

## 6. Agentes novos necessários (OBRIGATÓRIO)

### 6.1 `openshift-platform.md`

📍 `.claude/agents/openshift-platform.md`

Responsabilidade:

* OpenShift OCP 4
* Operadores
* Cluster lifecycle
* Day-1 / Day-2

Base oficial:

* [https://docs.openshift.com/container-platform/latest/](https://docs.openshift.com/container-platform/latest/)

---

### 6.2 `openshift-virtualization.md`

Responsabilidade:

* KubeVirt
* OpenShift Virtualization
* VMs como workloads
* Storage para VMs

Base oficial:

* [https://docs.openshift.com/container-platform/latest/virt/](https://docs.openshift.com/container-platform/latest/virt/)

---

### 6.3 `mtv-migration.md`

Responsabilidade:

* MTV
* Migração VMware → OpenShift
* Planos de migração
* Cutover e rollback

Base oficial:

* [https://access.redhat.com/documentation/en-us/migration_toolkit_for_virtualization/](https://access.redhat.com/documentation/en-us/migration_toolkit_for_virtualization/)

---

### 6.4 `mtc-migration.md`

Responsabilidade:

* MTC
* Migração namespaces
* PVs
* Migração incremental

Base oficial:

* [https://access.redhat.com/documentation/en-us/migration_toolkit_for_containers/](https://access.redhat.com/documentation/en-us/migration_toolkit_for_containers/)

---

## 7. Exemplo de definição de agente (MTV)

```md
---
name: mtv-migration
description: >
  Especialista sênior em migração de máquinas virtuais
  para OpenShift Virtualization usando MTV.
tools: [read, grep, glob]
permissionMode: readonly
---

# Papel
Você atua como ARQUITETO DE MIGRAÇÃO MTV.

# Responsável por:
- Analisar ambiente VMware
- Planejar migração
- Configurar providers
- Criar planos de migração
- Definir estratégia de cutover

# NÃO é responsável por:
- Deploy de aplicações
- CI/CD
- Infra cloud

# Regras:
- Sempre usar documentação Red Hat oficial
- Nunca migrar direto para produção sem teste
- Sempre prever rollback
```

---

## 8. Passo 3 — Atualizar checklists para migração

Criar:

```text
docs/ai/checklists/
├── mtv.md
├── mtc.md
├── openshift.md
└── virtualization.md
```

### Exemplo `checklists/mtv.md`

```md
- [ ] Ambiente VMware mapeado
- [ ] Credenciais testadas
- [ ] Storage compatível
- [ ] Rede validada
- [ ] Migração em lab executada
- [ ] Plano de rollback definido
```

---

## 9. Passo 4 — Fluxo correto do projeto (IMPORTANTE)

Um estagiário DEVE seguir esta ordem:

1. Entender o objetivo
2. Ler documentação oficial
3. Desenhar arquitetura (sem ferramenta)
4. Instalar OpenShift
5. Instalar operadores (MTV, MTC, ODF)
6. Migrar primeiro:

   * workloads simples
7. Depois:

   * workloads críticos
8. Validar
9. Só então ir para produção

---

## 10. O que NÃO fazer (ANTI-PADRÕES)

🚫 Migrar direto para produção
🚫 Ignorar storage
🚫 Ignorar rede
🚫 Ignorar rollback
🚫 Usar scripts fora do padrão
🚫 “Testar em produção”

---

## 11. Como adaptar este projeto para OUTRO cliente

Trocar apenas:

* `project-objective.md`
* `architecture-scope.md`
* checklists específicos
* versões de OpenShift

Você NÃO muda:

* estrutura
* DoD
* Orchestrator
* método

---

## 12. Resultado esperado

Ao final, o estagiário:

* entende OpenShift
* entende migração
* segue processo
* não improvisa
* trabalha como time enterprise

---

## 13. Referências Oficiais (OBRIGATÓRIAS)

* OpenShift:
  [https://docs.openshift.com/container-platform/latest/](https://docs.openshift.com/container-platform/latest/)

* OpenShift Virtualization:
  [https://docs.openshift.com/container-platform/latest/virt/](https://docs.openshift.com/container-platform/latest/virt/)

* MTV:
  [https://access.redhat.com/documentation/en-us/migration_toolkit_for_virtualization/](https://access.redhat.com/documentation/en-us/migration_toolkit_for_virtualization/)

* MTC:
  [https://access.redhat.com/documentation/en-us/migration_toolkit_for_containers/](https://access.redhat.com/documentation/en-us/migration_toolkit_for_containers/)

---

## Conclusão

Este documento transforma um **projeto complexo de migração** em um **processo guiado, seguro e profissional**.

👉 **Não é ferramenta. É método.**

```


