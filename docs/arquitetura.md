# Modelagem do Canal de Comunicação

```mermaid
graph TD
    A[Estudante] -->|Faz Login| B(Mural de Dúvidas)
    B -->|Envia Pergunta| C[Formulário de Dúvida]
    C -->|Notificação| D[Professor]
    D -->|Acessa Painel| E[Responde Dúvida]
    E -->|Notificação| A
