# Data & AI Portfolio — Carlos Restrepo
### Portafolio de Datos e IA — Carlos Restrepo

> Production-grade AI automation workflows, data analytics pipelines, and machine learning models built with Python, n8n, OpenAI, PostgreSQL, scikit-learn, Twilio, Google Vision OCR, and Google Sheets.
>
> Flujos de automatización de IA, pipelines de analítica de datos y modelos de machine learning de nivel productivo, construidos con Python, n8n, OpenAI, PostgreSQL, scikit-learn, Twilio, OCR de Google Vision y Google Sheets.

---

## Projects / Proyectos

| # | Project | Domain | Stack |
|---|---------|--------|-------|
| 1 | Medellín Business Leads Scraper | Data Engineering | Python · Google Maps API · Selenium · pandas |
| 2 | Credit Risk — Early Delinquency Model | Data Analytics & ML | Python · scikit-learn · pandas · matplotlib |
| 3 | Medellín Vehicle Recovery Analysis & Forecasting | Data Analytics & ML | Python · scikit-learn · DuckDB · Plotly · pandas |
| 4 | WhatsApp AI Assistant with Persistent Memory | AI Automation | n8n · OpenAI · PostgreSQL · Twilio |
| 5 | Automated Invoice Processing (OCR + AI) | AI Automation | n8n · Google Vision · OpenAI · Sheets · Telegram |

---

## Project 1 — Medellín Business Leads Scraper
## Proyecto 1 — Scraper de Leads Empresariales en Medellín

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

## Project 2 — Credit Risk: Early Delinquency Model
## Proyecto 2 — Riesgo de Crédito: Modelo de Morosidad Temprana

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

## Project 3 — Medellín Vehicle Recovery Analysis & Forecasting
## Proyecto 3 — Análisis y Pronóstico de Recuperación de Automotores en Medellín

**EN:** End-to-end data analytics project on Medellín's open vehicle recovery dataset (2003–2020), built as part of my work at the Secretaría de Movilidad. Covers the full analytics cycle: ETL, exploratory analysis, K-Means clustering of communes by risk profile, three forecasting models (linear, polynomial, EWM) projected to 2025, interactive Plotly dashboards, embedded SQL via DuckDB with window functions, and export-ready datasets for Power BI and Tableau.

**ES:** Proyecto de analítica de datos de extremo a extremo sobre el dataset abierto de recuperación de automotores de Medellín (2003–2020), construido a partir de mi trabajo en la Secretaría de Movilidad. Cubre el ciclo analítico completo: ETL, análisis exploratorio, clustering K-Means de comunas por perfil de riesgo, tres modelos de predicción (lineal, polinomial, EWM) proyectados a 2025, dashboards interactivos con Plotly, SQL embebido con DuckDB usando window functions, y datasets listos para Power BI y Tableau.

### Key Findings / Hallazgos Clave
- Total historical recoveries: **33,517 vehicles (2003–2020)** / Total de recuperaciones históricas: **33,517 vehículos (2003–2020)**
- Peak year 2003: **3,806 vehicles** — sustained downward trend ever since / Pico en 2003: **3,806 vehículos** — tendencia bajista sostenida desde entonces
- Decline of **-79.5%** from peak to 2020 / Caída del **-79.5%** del pico a 2020
- High-risk cluster: **Aranjuez, La Candelaria, Laureles-Estadio** / Cluster de alto riesgo: **Aranjuez, La Candelaria, Laureles-Estadio**
- EWM model selected as base scenario for 2021–2025 planning / Modelo EWM seleccionado como escenario base para planeación 2021–2025

### Pipeline
```
CSV Load → ETL & Data Quality → EDA → K-Means Clustering → Forecasting Models → Dashboards → SQL (DuckDB) → Power BI / Tableau Export
```

### Capabilities / Capacidades
- Full ETL with data quality report and feature engineering / ETL completo con reporte de calidad del dato e ingeniería de características
- 9 static visualizations (heatmaps, scatter clusters, forecast bands) / 9 visualizaciones estáticas (heatmaps, scatter de clusters, bandas de predicción)
- 2 interactive HTML dashboards (Plotly) / 2 dashboards interactivos en HTML (Plotly)
- K-Means clustering with elbow method and silhouette score / Clustering K-Means con método del codo y silhouette score
- Three forecasting models compared: Linear, Polynomial g2, EWM / Tres modelos de predicción comparados: Lineal, Polinomial g2, EWM
- SQL with window functions (`RANK`, `LAG`, `PARTITION BY`) via DuckDB / SQL con funciones de ventana (`RANK`, `LAG`, `PARTITION BY`) mediante DuckDB
- 4 export-ready CSV files for Power BI and Tableau / 4 archivos CSV listos para Power BI y Tableau
- Auto-generated conclusions with dynamic f-string variables / Conclusiones auto-generadas con variables dinámicas f-string

### Stack
`Python` · `pandas` · `numpy` · `matplotlib` · `seaborn` · `plotly` · `scikit-learn` · `KMeans` · `LinearRegression` · `DuckDB` · `Power BI` · `Tableau`

### Data Source / Fuente de datos
[Datos Abiertos — Alcaldía de Medellín / MEData](https://medata.gov.co) · Dataset: Recuperación de Automotores por Año y Comuna

---

## Project 4 — WhatsApp AI Assistant with Persistent Memory
## Proyecto 4 — Asistente de IA para WhatsApp con Memoria Persistente

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

## Project 5 — Automated Invoice Processing (OCR + AI)
## Proyecto 5 — Sistema Automatizado de Procesamiento de Facturas (OCR + IA)

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
| DuckDB | Embedded SQL engine / Motor SQL embebido |
| Selenium | Web scraping / Scraping web |
| Plotly | Interactive dashboards / Dashboards interactivos |
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
