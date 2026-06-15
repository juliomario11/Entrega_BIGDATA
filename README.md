# 📚 Curso: Big Data - Especialización en Analítica de Datos
**1er Semestre G2** | 2026

> Repositorio con los resúmenes y materiales del curso de Big Data. El curso cubre ciencia de datos, machine learning, inteligencia artificial y herramientas prácticas como Databricks, Spark y GitHub.

---

## 🗓️ Calendario del Curso

| Clase | Fecha | Tema Principal | Estado |
|---|---|---|---|
| **Clase 1** | 05 de junio de 2026 | Introducción a Big Data, configuración de GitHub y Databricks | ✅ Completada |
| **Clase 2** | 06 de junio de 2026 | Arquitectura Medallion, prácticas con PySpark y Genie | ✅ Completada |
| Clase 3 | 20 de junio de 2026 | TBD (confirmado por profesor) | ⏳ Pendiente |
| Clase 4 | 22 de junio de 2026 | TBD | ⏳ Pendiente |
| Clase 5 | 25 de junio de 2026 | TBD | ⏳ Pendiente |

> **Nota**: El profesor viajará al Databricks Summit en San Francisco del 15-18 de junio. No habrá clase esa semana.

---

## 📦 Estructura del Repositorio

```
BIG_DATA/
├── Clase_1/
│   ├── Clase_1_Transcripcion.txt
│   ├── Clase_1_Transcripcion.vtt
│   └── Resumen_Clase1_BigData.md
├── Clase_2/
│   ├── Clase_2_Transcripcion.txt
│   ├── Clase_2_Transcripcion.vtt
│   └── Resumen_Clase2_BigData.md
├── Documentos/
│   ├── AI_Native_Data_Blueprint.pdf
│   ├── Big_Data_UNAULA_First_Module.pdf
│   ├── Big_Data_to_AgentOps.pdf
│   ├── Modern_Data_Refinery.pdf
│   └── PROYECTO_FINAL.pdf
└── README.md
```

---

## 📋 Resúmenes de Clases

### [Clase 1 - 05 de junio de 2026](./Clase_1/Resumen_Clase1_BigData.md)

**Contenido principal:**
- Introducción a Big Data y las 5 V (Volumen, Velocidad, Variedad, Valor, Veracidad)
- Configuración paso a paso de GitHub (cuenta, fork, clonación en Databricks, Personal Access Token)
- Configuración de Databricks Free Edition
- Creación de branches en Git
- Ecosistema de herramientas: Power BI, Tableau, scikit-learn, TensorFlow, PySpark, Kafka, etc.
- Metodología del curso: 5 clases + 3 asesorías por equipo
- Arquitectura Medallion (Bronce → Plata → Oro)
- Práctica con sensores de presión de agua en PySpark
- Introducción a Genie (asistente de IA de Databricks)

**Entregables:**
- Crear cuenta en GitHub
- Hacer fork del repositorio del profesor
- Clonar en Databricks
- Generar Personal Access Token
- Crear branch de trabajo

---

### [Clase 2 - 06 de junio de 2026](./Clase_2/Resumen_Clase2_BigData.md)

**Contenido principal:**
- Noticias del sector (LLMs, ChatGPT, Gemini, Anthropic)
- Presentaciones del curso en inglés (3 presentaciones disponibles en Teams)
- Diversidad de perfiles en el curso (administradores, politólogos, ingenieros, contadores, licenciados)
- Profundización en la arquitectura Medallion
- Plataformas de nube: AWS (S3, SageMaker), Azure (ADLS Gen2, Azure ML, AI Foundry), GCP (BigQuery, GCS, Vertex AI)
- Repositorios como hoja de vida profesional
- Práctica 1: sensores de presión de agua con PySpark
- Ejercicio con Genie: simulación de medidores de energía con modelo de regresión
- Tipos de modelos: supervisados, no supervisados, semisupervisados, por refuerzo
- Spark DataFrame vs pandas DataFrame

**Asignaciones pendientes:**
- Definir caso de negocio para el proyecto final
- Solicitar asesorías de 45 minutos (por WhatsApp o correo)
- Continuar trabajando en el repositorio de GitHub

---

## 🎯 Trabajo Final

**Fecha de entrega:** 29 de junio de 2026 (inamovible)

**Equipos:** 2 personas (máximo 3)

**Componentes:**
1. **Caso de negocio** - real o con datos ficticios/simulados
2. **Análisis beneficio–costo** - cualitativo
3. **Arquitectura propuesta** - diagrama de herramientas/frameworks
4. **Pipeline de ingesta de datos** - automatización (arquitectura medallion)
5. **Modelo / análisis** - consumo por modelo o regla de negocio
6. **Visualizaciones** - Power BI, Tableau u otra herramienta
7. **Repositorio en GitHub** - documentado en Markdown

**Clave:** El catálogo/linaje de datos (Unity Catalog) en Databricks es ~50% del trabajo.

---

## 🔧 Herramientas del Curso

| Categoría | Herramientas |
|---|---|
| **Procesamiento** | Spark, PySpark, Kafka |
| **Visualización** | Power BI, Tableau, Qlik Sense, Dash, Gradio |
| **ML/Modelado** | scikit-learn, TensorFlow, PyTorch, MLflow |
| **Exploración** | pandas, NumPy, Matplotlib, Seaborn |
| **Bases de datos** | Cassandra, MongoDB, Neo4j |
| **Storage** | AWS S3, Azure ADLS Gen2, Google Cloud Storage |
| **Fuentes de datos** | Kaggle, Hugging Face |
| **Plataformas** | Databricks, AWS, Azure, GCP |
| **IA Asistentes** | Genie (Databricks), GitHub Copilot, Claude Code, Cursor, Gemini |

---

## 📄 Documentos de Referencia

La carpeta `Documentos/` contiene material complementario al curso:

| Documento | Descripción |
|---|---|
| **Big_Data_UNAULA_First_Module.pdf** | Fundamentos teóricos de Big Data - Módulo 1 de UNAULA |
| **AI_Native_Data_Blueprint.pdf** | Arquitectura de datos nativa para inteligencia artificial |
| **Modern_Data_Refinery.pdf** | Procesos modernos de refinería y transformación de datos |
| **Big_Data_to_AgentOps.pdf** | Evolución de Big Data hacia operaciones con agentes de IA |
| **PROYECTO_FINAL.pdf** | Especificaciones detalladas del proyecto final del curso |

> 💡 Estos documentos complementan los resúmenes de cada clase y proporcionan información detallada para el desarrollo del proyecto final, especialmente en las áreas de arquitectura de datos y pipelines de procesamiento.

---

## ⚠️ Advertencias Importantes

1. **No actives BigQuery/GCP con tu tarjeta personal** - puede generar cobros significativos
2. **Regla de oro al programar:** nada de eñes, tildes, mayúsculas ni espacios en nombres de archivos, ramas o variables
3. **Nunca trabajes directo sobre `main`** - usa branches
4. **GitHub es para código**, no para almacenar datos
5. **Usa correo personal** para GitHub y Databricks (no institucional, salvo convenio)

---

## 📞 Contacto del Profesor

- **WhatsApp o correo** para solicitar asesorías
- Viaja al **Databricks Summit en San Francisco** del 15-18 de junio
- Regresa el 19 de junio en la noche

---

## 🎓 Recursos Adicionales

- **Databricks Academy** - cursos y certificaciones gratis
- **Teams** - 3 presentaciones del curso (en inglés)
- **Repositorio del profesor**: https://github.com/yeiscop/Big_Data - hacer fork para comenzar

---

## 📝 Próximos Pasos

1. ✅ Revisar resúmenes de clases 1 y 2
2. 🔄 Completar configuración de GitHub y Databricks
3. 🔄 Definir caso de negocio para el proyecto final
4. 🔄 Solicitar primera asesoría (3 disponibles por equipo)
5. ⏳ Prepararse para el workshop de riesgo de crédito (Clase 3)

---

*Última actualización: 13 de junio de 2026*
