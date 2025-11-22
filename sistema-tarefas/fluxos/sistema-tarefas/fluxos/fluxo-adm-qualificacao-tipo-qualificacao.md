# Fluxo – Papel ADM Qualificação / Tipo de Tarefa: Qualificação

Este diagrama representa exatamente as transições permitidas conforme configurado no Redmine para:

- **Papel:** ADM Qualificação  
- **Tipo de tarefa:** Qualificação

As transições abaixo são baseadas diretamente na matriz de estados marcada no Redmine.

---

## Diagrama Mermaid

```mermaid
flowchart TD

    %% Estados
    NovaTarefa["Nova tarefa"]
    Nova["Nova"]
    Pronta["Pronta"]
    Fechada["Fechada"]
    Pausada["Pausada"]
    Cancelada["Cancelada"]
    Conferindo["Conferindo"]
    Conferir["Conferir"]
    Devolvida["Devolvida"]
    Analisando["Analisando"]
    Recebida["Recebida"]
    Incompleta["Incompleta"]
    Complementada["Complementada"]
    Entregue["Entregue"]
    Solicitação["Solicitação"]

    %% Transições da imagem

    %% Nova
    Nova --> Cancelada
    Nova --> Recebida

    %% Pronta
    Pronta --> Analisando
    Pronta --> Recebida
    Pronta --> Incompleta
    Pronta --> Complementada
    Pronta --> Entregue
    Pronta --> Solicitação

    %% Pausada
    Pausada --> Analisando

    %% Conferindo
    Conferindo --> Pronta
    Conferindo --> Incompleta

    %% Conferir
    Conferir --> Conferindo

    %% Analisando
    Analisando --> Pausada
    Analisando --> Conferir
    Analisando --> Incompleta

    %% Recebida
    Recebida --> Fechada
    Recebida --> Analisando
    Recebida --> Incompleta

    %% Incompleta
    Incompleta --> Cancelada
    Incompleta --> Recebida
    Incompleta --> Complementada

    %% Complementada
    Complementada --> Recebida

    %% Entregue
    Entregue --> Pronta
    Entregue --> Fechada

    %% Solicitação
    Solicitação --> Pronta
```