# Automação de Processos de TI com n8n

Este repositório documenta um projeto de automação implementado para otimizar rotinas operacionais críticas da equipa de TI, resultando numa **redução de 30% no tempo gasto em tarefas manuais** e aumentando a fiabilidade dos processos.

---

## O Problema

Num ambiente de TI dinâmico, uma quantidade significativa de tempo era gasta em tarefas repetitivas e manuais, tais como:
-   Execução de backups de sistemas.
-   Integração manual de dados entre diferentes plataformas.
-   Geração de relatórios de monitorização.

Estas tarefas não só consumiam tempo valioso, como também eram propensas a erro humano, podendo levar a falhas em backups ou inconsistência de dados.

## A Solução

Para resolver estes desafios, foi implementada uma solução de automação utilizando o **n8n**, orquestrado através de **Docker**. Foram criados vários workflows para automatizar os processos mais críticos.

### Arquitetura Utilizada
-   **n8n:** Ferramenta de automação de workflows (low-code).
-   **Docker & Docker Compose:** Para garantir um ambiente de execução isolado, portátil e facilmente replicável.
-   **PostgreSQL:** Como base de dados para o n8n, garantindo a persistência dos workflows e dados de execução.
-   **APIs REST:** Para a comunicação e integração entre os diferentes sistemas.

---

## Exemplo de Workflow Implementado

### Workflow 1: Backup Automatizado de Sistemas
Este workflow automatiza o processo de backup de uma aplicação crítica.

1.  **Gatilho (Trigger):** Executa todos os dias às 02:00 da manhã (Schedule Trigger).
2.  **Ação 1 (HTTP Request):** Envia uma requisição para a API do sistema A para iniciar o processo de geração de backup.
3.  **Ação 2 (Wait):** Aguarda 5 minutos para garantir que o ficheiro de backup foi completamente gerado.
4.  **Ação 3 (FTP):** Conecta-se ao servidor do sistema A via FTP e descarrega o ficheiro de backup para um local seguro.
5.  **Ação 4 (IF Node):** Verifica se o download foi bem-sucedido.
    -   **Em caso de sucesso:** Envia uma notificação para um canal do Microsoft Teams ou Slack com a mensagem "Backup do Sistema A concluído com sucesso".
    -   **Em caso de falha:** Envia uma notificação de erro para o canal de alertas, permitindo uma ação imediata da equipa.

### Screenshot do Workflow
*(Aqui, você deve adicionar um print screen do seu workflow no n8n. Esconda qualquer informação sensível como URLs ou tokens.)*

![Exemplo de Workflow no n8n](caminho/para/sua/imagem.png)

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
