# AI Automation Portfolio — Carlos Restrepo
### Portafolio de Automatización de IA — Carlos Restrepo

> Production-grade AI automation workflows built with n8n, OpenAI, PostgreSQL, Twilio WhatsApp API, Google Vision OCR, Google Sheets, Python, and scikit-learn.
>
> Flujos de automatización de IA de nivel productivo construidos con n8n, OpenAI, PostgreSQL, API de WhatsApp de Twilio, OCR de Google Vision, Google Sheets, Python y scikit-learn.

---

## Projects / Proyectos

| # | Project | Stack | File |
|---|---------|-------|------|
| 1 | WhatsApp AI Assistant with Persistent Memory | n8n · OpenAI · PostgreSQL · Twilio | `whatsapp-ai-assistant-sanitized.json` |
| 2 | Automated Invoice Processing (OCR + AI) | n8n · Google Vision · OpenAI · Sheets · Telegram | `factura-telegram-gmail-v5-sanitized.json` |
| 3 | Medellín Business Leads Scraper | Python · Google Maps API · Selenium · pandas | `leads_scraper_medellin_public.ipynb` |
| 4 | Credit Risk — Early Delinquency Model | Python · scikit-learn · pandas · matplotlib | `riesgo_de_credito_morosidad_temprana.ipynb` |

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

**ES:** Pipeline totalmente automatizado que extrae datos financieros estructurados de imágenes de facturas recibidas por Gmail. Combina OCR de Google Vision con extracción LLM para convertir imágenes de facturas no estructuradas en registros almacenados en Google Sheets, con notificaciones por Telegram.

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

**EN:** Automated data pipeline that extracts and enriches business leads from Google Maps across 22 zones in Medellín. Covers the Health (Dentistry) and Aesthetics (Aesthetic Clinics) sectors, enriching each record with email and WhatsApp contact data via static scraping and Selenium for JS-rendered sites.

**ES:** Pipeline de datos automatizado que extrae y enriquece leads empresariales de Google Maps en 22 zonas de Medellín. Cubre los sectores de Salud (Odontología) y Estética (Clínicas Estéticas), enriqueciendo cada registro con email y WhatsApp mediante scraping estático y Selenium para sitios renderizados en JS.

### Architecture / Arquitectura
```
Google Maps API → Place Details → Static Email Scraping → Selenium Enrichment → Excel Database
```

### Capabilities / Capacidades
- 22 search zones across Medellín metro area / 22 zonas de búsqueda en el área metropolitana
- Deduplication by `place_id` / Deduplicación por `place_id`
- Email extraction via `requests` + Selenium fallback / Extracción de email con `requests` + fallback Selenium
- WhatsApp detection from `wa.me` links and Colombian mobile numbers / Detección de WhatsApp desde enlaces `wa.me` y números móviles colombianos
- Output: structured Excel database / Salida: base de datos Excel estructurada

### Stack
`Python` · `Google Maps Places API` · `Selenium` · `pandas` · `requests` · `regex` · `openpyxl`

---

## Project 4 — Credit Risk: Early Delinquency Model
## Proyecto 4 — Riesgo de Crédito: Modelo de Morosidad Temprana

**EN:** Exploratory and predictive analysis of early delinquency (60-day default within 6 months) on a real credit portfolio of 235,000+ records. Builds an IVC (Credit Velocity Index) as the primary risk signal, performs economic threshold optimization, and trains a logistic regression baseline model.

**ES:** Análisis exploratorio y predictivo de morosidad temprana (default a 60 días en los primeros 6 meses) sobre una cartera crediticia real de más de 235,000 registros. Construye un IVC (Índice de Velocidad Crediticia) como señal de riesgo principal, optimiza el umbral económicamente y entrena un modelo baseline de regresión logística.

### Key Findings / Hallazgos Clave
- Base early delinquency rate: **~11.3%** / Tasa base de morosidad temprana: **~11.3%**
- IVC (search queries / credit age) is the strongest univariate predictor / El IVC es el predictor univariado más fuerte
- Red zone (IVC > 0.09): significantly higher default rate / Zona roja (IVC > 0.09): tasa de mora significativamente mayor
- Economic threshold optimization performed using expected net utility / Optimización del umbral con utilidad neta esperada

### Pipeline
```
Data Loading → Feature Engineering (IVC) → EDA → Traffic Light Segmentation → Economic Optimization → Logistic Regression Baseline
```

### Stack
`Python` · `pandas` · `numpy` · `matplotlib` · `scikit-learn` · `LogisticRegression` · `ROC-AUC`

---

## Tech Stack / Stack Técnico

| Tool | Role |
|------|------|
| n8n | Workflow orchestration / Orquestación de flujos |
| OpenAI / LLM | Natural language processing / Procesamiento de lenguaje natural |
| PostgreSQL | Persistent memory database / Base de datos de memoria persistente |
| Twilio WhatsApp API | Messaging integration / Integración de mensajería |
| Google Vision OCR | Document data extraction / Extracción de datos de documentos |
| Google Sheets API | Structured data storage / Almacenamiento de datos estructurados |
| Telegram API | Automated notifications / Notificaciones automatizadas |
| Python | Data pipelines & ML / Pipelines de datos y ML |
| scikit-learn | Machine learning / Aprendizaje automático |
| Selenium | Web scraping / Scraping web |
| Docker / VPS | Production deployment / Despliegue en producción |

---

## Author / Autor

**Carlos Restrepo**  
AI Automation Engineer / Ingeniero de Automatización de IA

Specialized in / Especializado en:
- LLM automation systems / Sistemas de automatización con LLM
- Conversational AI agents / Agentes de IA conversacional
- Intelligent document processing / Procesamiento inteligente de documentos
- Workflow orchestration with n8n / Orquestación de flujos con n8n
- Credit risk modeling / Modelado de riesgo crediticio

🔗 [github.com/ebseducacioncolombia-tech](https://github.com/ebseducacioncolombia-tech)

