# 🛵 Delivery Assistant

Ecossistema de microsserviços para análise preditiva de rentabilidade para entregadores em tempo real.

## 🏗️ Arquitetura e Tech Stack
O sistema utiliza uma abordagem de microsserviços poliglotas para separar regras de negócio de alta concorrência da inferência de dados.

- [cite_start]**Core (Go):** Orquestrador principal, lida com turnos e regras de negócio. [cite: 143, 144]
- [cite_start]**Analytics (Python):** Motor de IA para predição de demanda e geração de scores. [cite: 145, 146]
- [cite_start]**Comunicação:** gRPC (Interno) e REST (Externo). [cite: 148, 149]
- [cite_start]**Mensageria:** RabbitMQ para notificações e alertas assíncronos. [cite: 150, 157]
- [cite_start]**Dados:** PostgreSQL (Persistência) e Redis (Cache/Hotspots). [cite: 155, 156]

## 🧠 Inteligência (Features)
O sistema calcula o **Score de Oportunidade** cruzando:
- [cite_start]**Sazonalidade:** Horários de pico, feriados e dias de pagamento. [cite: 158]
- [cite_start]**Clima:** Temperatura (ex: demanda de sorveterias) e riscos de chuva. [cite: 159]
- [cite_start]**Eventos:** Calendário esportivo e grandes eventos regionais. [cite: 160]

## 📂 Estrutura do Projeto
```text
├── backend/
│   ├── core/         # Go: Clean Architecture & Goroutines
│   └── analytics/    # Python: ML (XGBoost) & LLM (Llama 3)
├── infrastructure/
│   ├── contracts/    # Definições .proto (gRPC)
│   ├── docker/       # Docker Compose e Dockerfiles
│   └── k8s/          # Manifestos Kubernetes
└── docker-compose.yaml
