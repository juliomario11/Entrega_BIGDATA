# 📚 Big Data — Especialización en Analítica de Datos (1er semestre, G2 · 2026)

> **Material de clases y documentos** del curso de Big Data. Cubre arquitectura Medallion en Databricks, PySpark, machine learning, gobierno de datos con Unity Catalog y flujo de trabajo con GitHub. Docente: **Yeis Livis Taborda Henao** ([@yeiscop](https://github.com/yeiscop)) · UNAULA, Facultad de Economía.

> ⚠️ **Alcance de este repositorio.** Aquí encontrarás **únicamente el material de clases** (transcripciones + resúmenes) **y los documentos del curso**. El **proyecto final completo** (código, pipeline Medallion, modelo y *serving*) vive en el repo **[agentes_ingesta_telecomunicaciones](https://github.com/juliomario11/agentes_ingesta_telecomunicaciones)**. Este repositorio **no contiene código del proyecto**.

---

## 🗂️ Estructura del repositorio

```
Entrega_BIGDATA/
├── Clase_1/
│   ├── Clase_1_Transcripcion.txt
│   ├── Clase_1_Transcripcion.vtt
│   └── Resumen_Clase1_BigData.md
├── Clase_2/
│   ├── Clase_2_Transcripcion.txt
│   ├── Clase_2_Transcripcion.vtt
│   └── Resumen_Clase2_BigData.md
├── Clase_3/
│   ├── Clase_3_Transcripcion.txt
│   ├── Clase_3_Transcripcion.vtt
│   └── Resumen_Clase3_BigData.md
├── Clase_4/
│   ├── Clase_4_Transcripcion.txt
│   ├── Clase_4_Transcripcion.vtt
│   └── Resumen_Clase4_BigData.md
├── Documentos/
│   ├── AI_Native_Data_Blueprint.pdf
│   ├── Big_Data_UNAULA_First_Module.pdf
│   ├── Big_Data_to_AgentOps.pdf
│   ├── Modern_Data_Refinery.pdf
│   └── PROYECTO FINAL.pdf
└── README.md
```

> Cada carpeta `Clase_N/` contiene la **transcripción limpia** (`.txt`, con hablantes), la **transcripción original** (`.vtt`, con *timestamps*) y un **resumen** en Markdown.

---

## 🗓️ Calendario

| Clase | Fecha | Tema | Estado |
|---|---|---|---|
| **Clase 1** | 05 jun 2026 | Introducción a Big Data, las 5 V, setup de GitHub y Databricks | ✅ |
| **Clase 2** | 06 jun 2026 | Plataformas de nube, profundización Medallion, PySpark y Genie | ✅ |
| **Clase 3** | sáb 20 jun 2026 | Workshop: del modelo al *serving endpoint* (MLflow), Unity Catalog y datos no estructurados en Delta Lake | ✅ |
| **Clase 4** | lun 22 jun 2026 | Pipelines Medallion (script vs declarativo/Lakeflow), CNN para clasificar imágenes reales vs IA, y linaje para auditoría | ✅ |
| Clase 5 | jue 25 jun 2026 (~5:30 pm) | Genie + despliegue de la app, SQL/NoSQL y Databricks local | ⏳ |

> El profesor viajó al **Databricks Summit (San Francisco)** del 15 al 18 de junio; regresó el 19 en la noche.
> En vez de una 6.ª clase, cada equipo tiene **3 asesorías de 45 min** (se piden por WhatsApp/correo).

---

## 🎯 Proyecto final — entrega: **29 de junio de 2026 (inamovible)**

> El desarrollo (código, notebooks, pipeline, modelo y *serving*) se entrega en **[agentes_ingesta_telecomunicaciones](https://github.com/juliomario11/agentes_ingesta_telecomunicaciones)**. Lo de aquí es solo material de referencia del curso.

Equipos de **2 personas (máx. 3)**. Componentes:

1. **Caso de negocio** — real o con datos simulados.
2. **Análisis beneficio–costo** — cualitativo.
3. **Arquitectura propuesta** — diagrama de herramientas/frameworks.
4. **Pipeline de ingesta** — automatizado, arquitectura Medallion.
5. **Modelo / análisis** — consumo por modelo o regla de negocio.
6. **Visualizaciones** — Power BI, Tableau u otra.
7. **Repositorio documentado** en Markdown.

> 💡 En Databricks, el **catálogo / linaje de datos (Unity Catalog)** es ~**50%** de la nota.

---

## 🔧 Stack del curso

| Categoría | Herramientas |
|---|---|
| Procesamiento | Spark, PySpark, Kafka |
| Visualización | Power BI, Tableau, Qlik Sense, Dash, Gradio |
| ML / Modelado | scikit-learn, TensorFlow, PyTorch, MLflow, Optuna |
| Exploración | pandas, NumPy, Matplotlib, Seaborn |
| Bases de datos | Cassandra, MongoDB, Neo4j |
| Storage | AWS S3, Azure ADLS Gen2, Google Cloud Storage |
| Fuentes | Kaggle, Hugging Face |
| Plataformas | Databricks, AWS, Azure, GCP |
| Asistentes IA | Genie (Databricks), GitHub Copilot, Claude Code, Cursor, Gemini |

---

## ⚠️ Reglas de oro

1. **Nunca subas tokens ni credenciales** (PAT de GitHub, claves de Databricks). Si algún token quedó en el historial, **revócalo y genera uno nuevo**.
2. **Nunca trabajes directo sobre `main`** — usa ramas `feature_*`.
3. **GitHub es para código, no para datos.**
4. Nombres **sin eñes, tildes, mayúsculas ni espacios** (archivos, ramas, variables).
5. **No actives BigQuery/GCP con tu tarjeta personal** — puede generar cobros.
6. Usa **correo personal** para GitHub y Databricks.

---

## 📄 Documentos de referencia (`Documentos/`)

| Documento | Tema |
|---|---|
| `Big_Data_UNAULA_First_Module.pdf` | Fundamentos de Big Data (Módulo 1) |
| `AI_Native_Data_Blueprint.pdf` | Arquitectura de datos nativa para IA |
| `Modern_Data_Refinery.pdf` | Transformación de datos a escala |
| `Big_Data_to_AgentOps.pdf` | De Big Data a operaciones con agentes |
| `PROYECTO FINAL.pdf` | Especificaciones y criterios del proyecto |

---

*Repo basado en un fork de [github.com/yeiscop/Big_Data](https://github.com/yeiscop/Big_Data). Material de clases del curso de Big Data, UNAULA — 2026.*
