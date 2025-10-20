<!-- BANNER -->
<p align="center">
  <img src="https://raw.githubusercontent.com/<teu-usuario>/<teu-repo>/main/assets/banner-n8n-dark.png" alt="n8n Automation Banner" width="100%">
</p>

<h1 align="center">🤖 Automação de Processos de TI com n8n</h1>

<p align="center">
  <b>Automatize. Integre. Escale — Libere sua equipa de TI das tarefas manuais.</b>
</p>

<p align="center">
  <a href="https://n8n.io"><img src="https://img.shields.io/badge/n8n-Automation-orange?logo=n8n&logoColor=white" alt="n8n"></a>
  <a href="https://www.docker.com/"><img src="https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker&logoColor=white" alt="Docker Compose"></a>
  <a href="https://www.postgresql.org/"><img src="https://img.shields.io/badge/PostgreSQL-Database-4169E1?logo=postgresql&logoColor=white" alt="PostgreSQL"></a>
  <a href="https://redis.io/"><img src="https://img.shields.io/badge/Redis-Memory-DC382D?logo=redis&logoColor=white" alt="Redis"></a>
  <a href="https://ai.google.dev/"><img src="https://img.shields.io/badge/Google%20Gemini-LLM-4285F4?logo=google&logoColor=white" alt="Gemini"></a>
  <a href="#"><img src="https://img.shields.io/badge/Status-Ativo-brightgreen?style=flat-square" alt="Status"></a>
</p>

---

## 💡 O Problema

Em ambientes de TI dinâmicos, **tarefas repetitivas** consumiam tempo precioso da equipa:
- 🗓️ Agendamento de reuniões e gestão de calendários  
- 💾 Execução e verificação de backups  
- 🔄 Integrações manuais entre sistemas e APIs  

Essas rotinas eram **ineficientes e propensas a erro humano**, limitando a capacidade da equipa de focar em tarefas estratégicas.

---

## 🚀 A Solução

Implementação de uma stack de automação **low-code com n8n** e **Docker**, criando **workflows inteligentes e escaláveis** que reduziram em **30% o tempo operacional** e aumentaram a confiabilidade dos processos.

### 🧱 Arquitetura Utilizada

| Componente | Função |
|-------------|--------|
| 🧩 **n8n** | Plataforma de automação e orquestração de workflows |
| 🐳 **Docker & Compose** | Isolamento e portabilidade dos ambientes |
| 🐘 **PostgreSQL** | Base de dados do n8n |
| ⚡ **Redis** | Armazenamento de contexto de chatbots e cache |
| 🤖 **Google Gemini + LangChain** | Processamento de linguagem natural e IA generativa |
| 🔗 **APIs REST (WhatsApp, Google Calendar, Slack)** | Integração entre sistemas |

---

## 🧮 Workflows Incluídos (`/workflows`)

### 1️⃣ Bot de Agendamento Inteligente (WhatsApp)

📁 **`01-bot-agendamento-whatsapp.json`**

**Descrição:**  
Um assistente virtual (“Thay”) que gerencia agendas via WhatsApp com IA e integrações diretas com o Google Calendar.

**Funcionalidades:**
- Recebe mensagens via **Webhook (WAHA API)**  
- Usa **Google Gemini** para interpretar mensagens  
- Permite **gestão administrativa** por número autorizado  
- Integra com o **Google Calendar** para criar, listar e apagar eventos  
- Usa **Redis** para manter o **contexto da conversa**

---

### 2️⃣ Backup Diário Automatizado

📁 **`02-backup-diario-servidor.json`**

**Descrição:**  
Workflow que executa **backups automáticos** e envia alertas inteligentes.

**Funcionalidades:**
- ⏰ **Gatilho agendado** (02:00 da manhã)  
- 💻 **Execução remota de script** (`pg_dump`)  
- ✅ **Validação automática** de sucesso via código de saída  
- 💬 **Notificação no Slack/Teams** com emoji de status e logs do job  

---

💬 Contribuições

Contribuições são muito bem-vindas — automação é um trabalho coletivo!
Abra um Pull Request com novos fluxos, melhorias ou correções.

👉 [Ver Issues](../../issues)

---

## 👨‍💻 Autor

**Gustavo Barbosa**  
💼 Profissional de TI • Automação • Infraestrutura • PowerShell  
🌐 [Portfólio](https://gl-tech-alpha.vercel.app)  
💻 [GitHub](https://github.com/XablauGtx) | 💬 [LinkedIn](www.linkedin.com/in/gustavo-barbosa-0909241b7)

---

<p align="center"> <i>“Automatizar é transformar complexidade em eficiência.”</i><br> — n8n Automation Lab </p>
