# Automação de Processos de TI com n8n

Este repositório documenta um projeto de automação implementado para otimizar rotinas operacionais críticas da equipa de TI, resultando numa **redução de 30% no tempo gasto em tarefas manuais** e aumentando a fiabilidade dos processos.

---

## O Problema

Num ambiente de TI dinâmico, uma quantidade significativa de tempo era gasta em tarefas repetitivas e manuais, tais como:
-   Agendamento de reuniões e gestão de calendário.
-   Execução de backups de sistemas e verificação de sucesso.
-   Integração manual de dados entre diferentes plataformas.

Estas tarefas não só consumiam tempo valioso, como também eram propensas a erro humano.

## A Solução

Para resolver estes desafios, foi implementada uma solução de automação utilizando o **n8n**, orquestrado através de **Docker**. Foram criados vários workflows para automatizar os processos mais críticos.

### Arquitetura Utilizada
-   **n8n:** Ferramenta de automação de workflows (low-code).
-   **Docker & Docker Compose:** Para garantir um ambiente de execução isolado, portátil e facilmente replicável.
-   **PostgreSQL:** Como base de dados para o n8n.
-   **Redis:** Para gestão de memória de conversas em chatbots.
-   **Google Gemini & LangChain:** Para processamento de linguagem natural e criação de agentes de IA.
-   **APIs REST:** Para a comunicação e integração entre os diferentes sistemas (WhatsApp, Google Calendar, Slack).

---

## Workflows Incluídos (.json)

Na pasta `/workflows`, você encontrará os exports em formato JSON dos workflows descritos neste documento.

### 1. Bot de Agendamento Inteligente para WhatsApp
-   **Ficheiro:** `01-bot-agendamento-whatsapp.json`
-   **Descrição:** Este workflow implementa uma secretária virtual chamada "Thay" que interage com utilizadores via WhatsApp.
-   **Funcionalidades:**
    -   Recebe mensagens através de um webhook ligado a uma API de WhatsApp (WAHA).
    -   Utiliza um **Agente de IA (Google Gemini)** para interpretar as mensagens em linguagem natural.
    -   Possui uma **lógica condicional** que dá permissões de administrador a um número específico, permitindo a gestão completa da agenda.
    -   Conecta-se à **API do Google Calendar** para consultar, criar e apagar eventos.
    -   Usa **Redis** para manter a memória da conversa, permitindo que o bot entenda o contexto de perguntas anteriores.

### 2. Backup Diário Automatizado de Servidor
-   **Ficheiro:** `02-backup-diario-servidor.json`
-   **Descrição:** Um workflow clássico de infraestrutura para garantir a segurança dos dados.
-   **Funcionalidades:**
    -   **Gatilho Agendado:** O workflow é executado automaticamente todos os dias às 02:00 da manhã.
    -   **Execução de Comando:** Executa um script shell no servidor (ex: `pg_dump`) para criar um backup da base de dados.
    -   **Verificação de Sucesso:** Verifica o código de saída do script. Se for `0`, o backup foi bem-sucedido.
    -   **Notificação no Slack/Teams:** Envia uma mensagem para um canal específico, informando se o backup foi concluído com **sucesso** (✅) ou se houve uma **falha** (🚨), incluindo a mensagem de erro.

---

## Como Executar Localmente

Este ambiente pode ser replicado localmente usando Docker.

1.  Clone este repositório.
2.  Crie um ficheiro `.env` a partir do modelo `.env.example` e preencha as variáveis de ambiente.
3.  Execute o seguinte comando na raiz do projeto:
    ```bash
    docker-compose up -d
    ```
4.  Aceda ao n8n através do endereço `http://localhost:5678`.
