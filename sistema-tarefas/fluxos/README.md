# Fluxos do Sistema de Tarefas

## Visão geral

Esta seção contém os fluxos de trabalho do sistema de tarefas da Formaz, representados em diagramas Mermaid e descrições textuais.
O objetivo é deixar claro como as demandas devem percorrer o ciclo de vida dentro do Redmine.

---

## Fluxo 01 – Atendimento de demanda de cliente

Descrição breve:

1. Cliente abre solicitação.
2. Registro da demanda no sistema de tarefas.
3. Classificação (tipo, categoria, prioridade).
4. Definição de atendimento imediato ou planejamento.
5. Execução.
6. Homologação.
7. Entrega e encerramento.

### Diagrama (Mermaid)

```mermaid
flowchart TD
    A[Cliente abre solicitação] --> B[Registro da demanda no Redmine]
    B --> C[Classificação da demanda]
    C --> D{Tipo de demanda}
    D -->|Incidente crítico| E[Atendimento imediato]
    D -->|Correção não crítica| F[Planejamento em fila]
    D -->|Melhoria/Evolução| G[Planejamento em backlog]

    E --> H[Execução]
    F --> H
    G --> H

    H --> I[Homologação interna]
    I --> J{Homologação cliente}
    J -->|Aprovado| K[Encerramento da tarefa]
    J -->|Reprovado| H
