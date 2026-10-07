# Olá, eu sou o Leandro 👋

### Engenheiro de Software Sênior · Node.js · Sistemas Distribuídos · AWS

> *"Funciona na minha máquina" não é estratégia de deploy. Saga com compensação automática é.* 😎

Há **15+ anos** transformando café ☕ em sistemas que aguentam o tranco. Hoje meu habitat natural é **Node.js** e **sistemas distribuídos**: microsserviços, mensageria, eventos assíncronos e aquela arte milenar de fazer vários serviços concordarem entre si sem ninguém ler a tabela de ninguém.

Já fiz Kafka carregar eventos de **todas as comarcas de Minas Gerais** ⚖️ e ajudei a monitorar **mais de 500 mil hectares de soja** 🌱. Se tem fila, retry, idempotência e um alarme às 3h da manhã envolvidos, provavelmente eu tô feliz.

---

## 🧪 Projeto em destaque: Distributed Systems Playground

### 👉 [**Brinque com ele rodando ao vivo**](https://d3vp3zj9sxbgz7.cloudfront.net/) 👈

**[lab_dist_system](https://github.com/Leandrodasilvahuber/lab_dist_system)** é o meu laboratório de sistemas distribuídos na AWS: um e-commerce **100% serverless** em que cada compra é uma **saga orquestrada pelo Step Functions**, assíncrona e com **compensação automática** quando algo dá errado (e eu faço questão de que algo dê errado 😈).

```
CreateOrder ─▶ ReserveStock ─▶ ProcessPayment ─▶ CommitReservation ─▶ ConfirmOrder ─▶ ✅ COMPLETED
     │              │               │                    │                  │
     ▼ falha        ▼ falha         ▼ falha              ▼ falha            ▼ falha
  ❌ FAILED      ReleaseStock    RefundPayment ◀──────────┴──────────────────┘
                 CancelOrder     ReleaseStock · CancelOrder ──────────▶ 🔁 COMPENSATED
```

**O que tem lá dentro:**

- ⚙️ **Node.js 22 em AWS Lambda** (arm64 + esbuild), API Gateway HttpApi e infra como código com **AWS SAM**
- 🧵 **Saga pattern** com compensação em ordem reversa, retry com backoff para falhas transitórias e reconciliação de sagas "travadas"
- 🔑 **Idempotência de ponta a ponta**: `Idempotency-Key` obrigatória, operações seguras para retry e escritas condicionais/transacionais no **DynamoDB** (nada de vender o mesmo estoque duas vezes)
- 📣 **EventBridge** para eventos de domínio, com Archive para auditoria e **DLQ** com redrive pelo dashboard
- 🔭 **Observabilidade de verdade**: logs JSON estruturados, métricas EMF, rastreio por `correlationId`, X-Ray, alarmes e **SLOs** (p95 < 2 s, ≥ 99,5% das sagas concluídas ou compensadas)
- 💥 **Engenharia de caos**: injete latência, throttling, crash ou indisponibilidade em qualquer serviço e veja retry, circuit breaker e compensação trabalhando
- 💸 **Kill switch de custo**: AWS Budgets + alarme anti-flood que derrubam a API para 429 antes que a fatura me derrube
- 🛡️ **Segurança**: Cognito + JWT authorizer, ESLint security, Semgrep, Gitleaks, Checkov e OWASP ZAP
- 🐳 **Roda local** com LocalStack e um dashboard sem build (ES modules puros) com tema claro e escuro

> 💡 **Dica:** compre o produto `server` (R$ 25.000) e veja o pagamento ser recusado e a saga desfazer tudo sozinha. Depois ative o caos e tente quebrar o resto. Pode, eu deixo. 😄

---

## 🛠️ Stack principal

| Área | Ferramentas |
|---|---|
| 🟢 **Node.js & JS** | Node.js, TypeScript, Express.js, React, Vue.js |
| 🕸️ **Sistemas distribuídos** | Microsserviços, Saga, Event-Driven, Kafka, RabbitMQ, EventBridge, SQS, Step Functions |
| ☁️ **Cloud & DevOps** | AWS (Lambda, DynamoDB, API Gateway, CloudWatch, CloudFront, S3, Cognito), DigitalOcean, Docker, CI/CD, GitHub Actions |
| 🗄️ **Dados** | PostgreSQL, MySQL, MongoDB, DynamoDB, Redis, ElasticSearch |
| 🐘 **Também falo** | PHP / Laravel, Java |
| 🤖 **AI-Assisted Dev** | GitHub Copilot, MCPs, Prompt Engineering, AI Pair Programming |

---

## 💼 Por onde andei recentemente

- **Desenvolvedor Full Stack Sênior — Hammer Consult** *(2023 – atual)*
  Integrações via **Kafka** para processamento assíncrono em alta escala (todas as comarcas de MG), cache com **Redis**, deploy em **AWS/DigitalOcean** e liderança na adoção de AI-assisted development e MCPs no time.

- **Desenvolvedor Full Stack — Digifarmz** *(2021 – 2023)*
  Referência técnica em **microsserviços** e APIs REST com **Node.js**, tópicos Kafka entre serviços distribuídos e pipelines de CI/CD que **reduziram rollbacks em 90%** 🚀.

- **10+ anos antes disso** construindo backends e sistemas full stack em Node.js, PHP e Java. Sim, eu já vi coisas. 👀

---

## 📫 Bora conversar?

[![LinkedIn](https://img.shields.io/badge/LinkedIn-leandrohuber-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/leandrohuber)
[![Email](https://img.shields.io/badge/Email-emaildohuber%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:emaildohuber@gmail.com)
[![Demo](https://img.shields.io/badge/Demo-Distributed_Playground-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)](https://d3vp3zj9sxbgz7.cloudfront.net/)

<sub>📍 Florianópolis (SC) · Disponível para PJ ou CLT · Eventualmente consistente, mas sempre disponível. 😉</sub>
# Olá, eu sou o Leandro 👋

Desenvolvedor Full Stack Sênior com 16+ anos de experiência arquitetando e entregando sistemas web escaláveis. Atuo principalmente nos ecossistemas JavaScript/Node.js e PHP/Laravel, com experiência prática em microsserviços, processamento assíncrono de alta escala e infraestrutura cloud.

## 🛠️ Stack principal

**JavaScript / Node.js:** Express.js, TypeScript, React, Vue.js

**PHP / Laravel:** APIs REST, Microsserviços, CakePHP

**Cloud & DevOps:** AWS, DigitalOcean, Docker, CI/CD, GitHub Actions

**Dados & Mensageria:** PostgreSQL, MySQL, MongoDB, Redis, Kafka, RabbitMQ, ElasticSearch

**AI-Assisted Development:** GitHub Copilot, MCPs, AI Pair Programming, Prompt Engineering

## 💼 Experiência recente

**Desenvolvedor Full Stack Sênior — Hammer Consult (2023 – atual)**
Arquitetura de aplicações escaláveis em Vue.js, Laravel e Node.js; estratégias de cache com Redis; processamento assíncrono com Kafka; deploy e operação em AWS/DigitalOcean.

**Desenvolvedor Full Stack Pleno/Sênior — Digifarmz (2021 – 2023)**
Microsserviços e APIs RESTful em Vue.js, Laravel, React e Node.js; pipelines de CI/CD; arquitetura orientada a eventos com Kafka.

10+ anos anteriores construindo sistemas backend e full stack em diversas empresas — base sólida em JavaScript, Node.js, PHP e Java.

## 📌 Projetos em destaque

**[api-documentacao-colaboradores](https://github.com/Leandrodasilvahuber/api-documentacao-colaboradores)** — API em Node.js + TypeScript (Express, Prisma, PostgreSQL) para controle de documentos de colaboradores, com testes e2e, controle de concorrência via transações e documentação OpenAPI completa.

**[job-sourcing](https://github.com/Leandrodasilvahuber/job-sourcing)** — API em Node.js/Express para descobrir empresas de desenvolvimento de software (Brasil e Portugal) via OCR, crawler do GitHub e crawler do Google, com pesquisa automatizada por IA (Gemini) e frontend em React.

**[redacao](https://github.com/Leandrodasilvahuber/redacao)** (Orquestrador IA) — Pipeline automatizado que busca notícias via RSS, gera e revisa textos com IA (Groq/Gemini/Mistral), ilustra e publica no blog e/ou LinkedIn. Backend em Spring Boot (Java) e frontend em React.

**[blog](https://github.com/Leandrodasilvahuber/blog)** — Blog pessoal ([acesse aqui](https://leandrohuber.duckdns.org/)) com redação orquestrada por IA e revisão humana; painel administrativo em Laravel, API de publicação autenticada por token e testes automatizados (unit, feature e e2e com Dusk).

## 📫 Contato

💼 [LinkedIn](https://www.linkedin.com/in/leandrohuber/)

✉️ emaildohuber@gmail.com
