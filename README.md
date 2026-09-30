# ⚡ n8n Local + PostgreSQL + SearXNG + Sandbox

Ambiente local completo do **n8n** com suporte a **Instance AI**, **Sandbox isolado** via Docker-in-Docker, motor de busca privado **SearXNG** e banco de dados **PostgreSQL**.

---

## 🚀 Como Executar

### 1. Configurar as Variáveis de Ambiente
Copie o arquivo `.env.example` para `.env` e ajuste as senhas/chaves caso necessário:

```bash
cp .env.example .env
```

### 2. Iniciar os Containers com Docker Compose
No diretório do projeto (`~/GitHub/n8n-local`), execute:

```bash
docker compose up -d
```

Isso subirá os seguintes serviços:
- ⚡ **n8n**: [http://localhost:5678](http://localhost:5678)
- 🐘 **PostgreSQL 16**: Porta interna `5432`
- 🔍 **SearXNG**: Motor de busca privado
- 🛡️ **n8n Sandbox API & Runner**: Execução segura de código/AI em ambiente isolado

---

## 🛠️ Serviços Inclusos

| Serviço | Função | Porta |
| :--- | :--- | :--- |
| **n8n** | Automação de Workflows & IA | `5678` |
| **PostgreSQL** | Banco de dados relacional | Interna (`5432`) |
| **SearXNG** | Busca Web para Agentes de IA | Interna (`8080`) |
| **Sandbox API / Runner** | Ambientes de execução mTLS | Interna (`8080`, `9090`, `9091`) |

---

## 📁 Estrutura do Projeto

```
~/GitHub/n8n-local/
├── docker-compose.yml       # Orquestração de containers (PostgreSQL, n8n, SearXNG, Sandbox)
├── searxng-settings.yml     # Configurações do SearXNG
├── .env.example             # Modelo de variáveis de ambiente
├── .gitignore               # Proteção de credenciais (.env)
└── README.md                # Documentação de uso
```
