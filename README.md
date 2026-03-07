# Data & AI Portfolio — Carlos Restrepo
### Portafolio de Datos e IA — Carlos Restrepo

> Production-grade AI automation workflows, data analytics pipelines, and machine learning models built with Python, n8n, OpenAI, PostgreSQL, scikit-learn, Twilio, Google Vision OCR, and Google Sheets.
>
> Flujos de automatización de IA, pipelines de analítica de datos y modelos de machine learning de nivel productivo, construidos con Python, n8n, OpenAI, PostgreSQL, scikit-learn, Twilio, OCR de Google Vision y Google Sheets.

---

## Projects / Proyectos

| # | Project | Domain | Stack |
|---|---------|--------|-------|
| 1 | WhatsApp AI Assistant with Persistent Memory | AI Automation | n8n · OpenAI · PostgreSQL · Twilio |
| 2 | Automated Invoice Processing (OCR + AI) | AI Automation | n8n · Google Vision · OpenAI · Sheets · Telegram |
| 3 | Medellín Business Leads Scraper | Data Engineering | Python · Google Maps API · Selenium · pandas |
| 4 | Credit Risk — Early Delinquency Model | Data Analytics & ML | Python · scikit-learn · pandas · matplotlib |

---

## Project 1 — WhatsApp AI Assistant with Persistent Memory
## Proyecto 1 — Asistente de IA para WhatsApp con Memoria Persistente

**EN:** A fully automated WhatsApp assistant powered by AI that maintains persistent conversation memory, understands user intent, and responds contextually. Deployed via Twilio webhooks and orchestrated through n8n.

**ES:** Asistente de WhatsApp completamente automatizado que mantiene memoria persistente de conversación, comprende la intención del usuario y responde de forma contextual. Desplegado con webhooks de Twilio y orquestado mediante n8n.

### Architecture / Arquitectura
```
WhatsApp → Twilio Webhook → n8n → AI Agent (OpenAI) → PostgreSQL Memory → WhatsApp Response
```

### Capabilities / Capacidades
- Persistent conversation memory via PostgreSQL / Memoria persistente de conversación con PostgreSQL
- Context-aware AI responses via LLM / Respuestas de IA con contexto usando LLM
- Automated WhatsApp message handling / Manejo automatizado de mensajes de WhatsApp
- Production webhook architecture / Arquitectura de webhooks en producción
- Scalable workflow orchestration via n8n / Orquestación escalable de flujos con n8n

---

## Project 2 — Automated Invoice Processing (OCR + AI)
## Proyecto 2 — Sistema Automatizado de Procesamiento de Facturas (OCR + IA)

**EN:** Fully automated pipeline that extracts structured financial data from invoice images received via Gmail. Combines Google Vision OCR with LLM extraction to convert unstructured invoice images into structured records stored in Google Sheets, with Telegram notifications.

**ES:** Pipeline totalmente automatizado que extrae datos financieros estructurados de imágenes de facturas recibidas por Gmail. Combina OCR de Google Vision con extracción LLM para convertir imágenes no estructuradas en registros almacenados en Google Sheets, con notificaciones por Telegram.

### Architecture / Arquitectura
```
Gmail → Google Vision OCR → LLM Extraction → Data Normalization → Google Sheets → Telegram Notification
```

### Capabilities / Capacidades
- OCR extraction from invoice images / Extracción OCR de imágenes de facturas
- Structured JSON generation via LLM / Generación de JSON estructurado mediante LLM
- Automated financial data normalization / Normalización automatizada de datos financieros
- Google Sheets integration / Integración con Google Sheets
- Telegram notifications / Notificaciones por Telegram
- Fully automated email-triggered pipeline / Pipeline completamente automático activado por correo

---

## Project 3 — Medellín Business Leads Scraper
## Proyecto 3 — Scraper de Leads Empresariales en Medellín

**EN:** Data engineering pipeline that extracts and enriches business leads from Google Maps across 22 zones in Medellín. Covers Dentistry and Aesthetic Clinics sectors, enriching each record with email and WhatsApp contact data using static scraping and Selenium for JS-rendered sites.

**ES:** Pipeline de ingeniería de datos que extrae y enriquece leads empresariales de Google Maps en 22 zonas de Medellín. Cubre los sectores de Odontología y Clínicas Estéticas, enriqueciendo cada registro con email y WhatsApp mediante scraping estático y Selenium para sitios renderizados en JS.

### Architecture / Arquitectura
```
Google Maps API → Place Details → Static Email Scraping → Selenium Enrichment → Excel Database
```

### Capabilities / Capacidades
- 22 search zones across Medellín metro area / 22 zonas en el área metropolitana de Medellín
- Deduplication by `place_id` / Deduplicación por `place_id`
- Email extraction via `requests` + Selenium fallback / Extracción de email con `requests` + fallback Selenium
- WhatsApp detection from `wa.me` links and Colombian mobile numbers / Detección de WhatsApp desde `wa.me` y números colombianos
- Output: structured Excel database / Salida: base de datos Excel estructurada

### Stack
`Python` · `Google Maps Places API` · `Selenium` · `pandas` · `requests` · `regex` · `openpyxl`

---

## Project 4 — Credit Risk: Early Delinquency Model
## Proyecto 4 — Riesgo de Crédito: Modelo de Morosidad Temprana

**EN:** Exploratory data analysis and predictive modeling of early delinquency (60-day default within 6 months) on a real credit portfolio of 235,000+ records. Builds an IVC (Credit Velocity Index) as the primary risk signal, applies traffic-light segmentation, performs economic threshold optimization, and trains a logistic regression baseline.

**ES:** Análisis exploratorio y modelado predictivo de morosidad temprana (default a 60 días en los primeros 6 meses) sobre una cartera crediticia real de más de 235,000 registros. Construye el IVC (Índice de Velocidad Crediticia) como señal de riesgo principal, aplica segmentación tipo semáforo, optimiza el umbral económicamente y entrena un baseline de regresión logística.

### Key Findings / Hallazgos Clave
- Base early delinquency rate: **~11.3%** / Tasa base de morosidad temprana: **~11.3%**
- IVC (credit queries / credit age) is the strongest univariate predictor / El IVC es el predictor univariado más fuerte
- Red zone (IVC > 0.09): significantly higher default rate / Zona roja (IVC > 0.09): mayor tasa de mora
- Economic threshold optimization via expected net utility / Optimización del umbral con utilidad neta esperada

### Pipeline
```
Data Loading → Feature Engineering (IVC) → EDA → Traffic Light Segmentation → Economic Optimization → Logistic Regression
```

### Stack
`Python` · `pandas` · `numpy` · `matplotlib` · `scikit-learn` · `LogisticRegression` · `ROC-AUC`

---

## Tech Stack / Stack Técnico

| Tool | Role |
|------|------|
| Python | Data pipelines, analytics & ML / Pipelines de datos, analítica y ML |
| n8n | Workflow orchestration / Orquestación de flujos |
| OpenAI / LLM | Natural language processing / Procesamiento de lenguaje natural |
| PostgreSQL | Persistent memory database / Base de datos de memoria persistente |
| Twilio WhatsApp API | Messaging integration / Integración de mensajería |
| Google Vision OCR | Document data extraction / Extracción de datos de documentos |
| Google Sheets API | Structured data storage / Almacenamiento de datos estructurados |
| Telegram API | Automated notifications / Notificaciones automatizadas |
| scikit-learn | Machine learning / Aprendizaje automático |
| Selenium | Web scraping / Scraping web |
| Docker / VPS | Production deployment / Despliegue en producción |

---

## Author / Autor

**Carlos Restrepo**  
Data & AI Automation Engineer / Ingeniero de Datos y Automatización de IA

Specialized in / Especializado en:
- AI automation systems / Sistemas de automatización con IA
- Conversational AI agents / Agentes de IA conversacional
- Intelligent document processing / Procesamiento inteligente de documentos
- Data analytics & credit risk modeling / Analítica de datos y modelado de riesgo crediticio
- Workflow orchestration with n8n / Orquestación de flujos con n8n

🔗 [github.com/ebseducacioncolombia-tech](https://github.com/ebseducacioncolombia-tech)

