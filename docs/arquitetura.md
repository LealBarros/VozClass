# Modelagem do Canal de Comunicação

```mermaid
flowchart TD
    %% Definição de Estilos
    classDef ator fill:#2D3748,stroke:#1A202C,stroke-width:2px,color:#FFFFFF,font-weight:bold
    classDef aluno fill:#2B6CB0,stroke:#2C5282,stroke-width:1px,color:#FFFFFF
    classDef sistema fill:#4A5568,stroke:#2D3748,stroke-width:1px,color:#FFFFFF
    classDef prof fill:#2F855A,stroke:#22543D,stroke-width:1px,color:#FFFFFF

    %% Atores Principais
    A([Estudante]):::ator
    F([Professor]):::ator

    %% Etapas do Aluno
    subgraph Modulo_Aluno [Módulo do Estudante]
        B[Login no Sistema]:::aluno
        C[Acesso ao Mural]:::aluno
        D[Formulário de Envio]:::aluno
    end

    %% Processamento
    subgraph Modulo_Sistema [Serviço de Processamento]
        E[Fila de Mensagens / Notificação]:::sistema
    end

    %% Etapas do Professor
    subgraph Modulo_Professor [Módulo do Professor]
        G[Painel de Dúvidas Pendentes]:::prof
        H[Envio da Resposta]:::prof
    end

    %% Fluxo de Conexões
    A --> B
    B --> C
    C --> D
    D --> E
    E --> G
    F --> G
    G --> H
    H --> E
    E --> A
