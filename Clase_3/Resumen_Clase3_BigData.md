# 📋 Clase 3 — Workshop: del modelo al *serving endpoint* + datos no estructurados (sábado 20 de junio de 2026)

> Tercera sesión, en formato **workshop práctico** (mezcla de teoría corta, trabajo guiado en clase y asesorías uno a uno). Se retoma el setup de las Clases 1–2 y se lleva un modelo **hasta producción**: registrarlo con **MLflow** y **servirlo como un endpoint** en Databricks. Se profundiza en **Unity Catalog** (catálogo → esquema → volúmenes), el manejo de **datos no estructurados** en Delta Lake y las herramientas de visualización/apps.

---

## 🧭 Lo esencial de esta clase
- **Repaso** de las 5 V y de la arquitectura **Medallion** (bronce → plata → oro).
- Llevar un modelo a producción: **MLflow registra el modelo** y se **sirve como *serving endpoint*** (API consumible desde cualquier lugar).
- **Unity Catalog** a fondo: catálogo (gobierna datos, modelos, funciones y **agentes**) → esquema → volúmenes/tablas.
- **Datos no estructurados** (imágenes, audio, video) tratados como tablas dentro de un **Delta Lake**; formatos open source **Parquet / Iceberg / Delta**.
- Herramientas de **visualización** (Power BI, Tableau, Qlik Sense) y de **apps** (Dash, Gradio, Flask, Streamlit), más IDE **VS Code** y *no-code* (**KNIME**, **n8n**).
- **Noticias del sector** y mucho énfasis en **agendar las asesorías**.

---

## 1. Noticias del sector
- **Agentes autónomos**: el profe mostró **OpenClaude** (asistente de IA de código abierto que ejecuta tareas como agente, no solo chatea) y comentó que en EE. UU. hay quien lo monta en mini-equipos (Mac con varias GPU). Mención del modelo de Anthropic con seguridad reforzada por su potencial en ciberseguridad.
- **Automatización de ETL con agentes**: en un *lakehouse* (que reemplaza al *warehouse*) ya se pone un **agente** a coordinar la información, lanzar *queries* y construir los ETL. Lo clave hoy es **orquestar**, no programar línea a línea. Artículos de referencia de AWS y Databricks.

## 2. Repaso de fundamentos
- Las **5 V**: Volumen, Velocidad, Variedad, Valor, Veracidad → cubren data estructurada, semiestructurada y no estructurada.
- **Cloud vs on-premise**: no todo debe ir a la nube; hay que evaluar **costo computacional**, **regulación** (datos que no pueden salir) y costo-beneficio. El stack de Databricks (Unity Catalog, MLflow, PySpark) es **open source** y también corre local. El escalamiento se hace por **clúster/procesadores**, no comprando más computadores.
- **Hadoop / MapReduce**: "lleva el código a los datos" y particiona archivos para procesarlos de forma distribuida; Spark unifica eso corriendo en RAM.

## 3. Unity Catalog: gobierno de datos (y de modelos y agentes)
Jerarquía: **catálogo** (donde se gobierna todo) → **esquema** (define tablas, volúmenes, modelos, funciones, **agentes**) → **tablas / volúmenes / modelos**. En el ejemplo de la práctica se sube información **cruda de Kaggle** a un **volumen** dentro de un esquema. Aviso recurrente del taller: si el nombre del esquema es muy largo o lleva caracteres raros, **falla**; los nombres deben ir **pegados, sin espacios ni mayúsculas**.

## 4. De MLflow al *serving endpoint* (lo central del workshop)
Flujo que cada estudiante replicó (caso guía: modelo que pronostica el **crecimiento de árboles** según el tipo de cultivo, con datos de Kaggle):
1. Cargar datos crudos a un **volumen** (Unity Catalog).
2. Entrenar el modelo y **registrarlo con MLflow** (queda con traza/versión).
3. Ir a **Models** → abrir el modelo → **Serve model** → darle un nombre → queda un **Serving endpoint**.
4. Ya **en producción**: el modelo se **consume desde cualquier lugar** (API). Databricks también ofrece modelos servidos listos (Llama, GPT, etc.), pero aquí se sirvió **el propio**.

## 5. Datos no estructurados en Delta Lake
Lo interesante de los formatos **Delta**: un volumen, una imagen, un audio o un video se manipulan **como si fueran una tabla** (la imagen "es" píxeles + tipo), lo que facilita su tratamiento. Relevante en marketing (p. ej. zonas más visitadas en una tienda), audio y video. Para grandes volúmenes se usa **Parquet** (comprime y agiliza; junto con **Iceberg** son los más usados), cargado con **PySpark**.

## 6. Herramientas de visualización, apps y entornos
- **Visualización**: Power BI, Tableau, Qlik Sense (equivalentes entre sí).
- **Apps / dashboards**: Dash, **Gradio**, Flask, Streamlit, Shiny (R). Antes se programaba mucho; hoy casi no hace falta.
- **IDE**: **VS Code** para manejar todo el árbol de directorios y tirar cualquier tipo de código, conectándose a la nube; puede invocar la IA propia de la empresa (Copilot).
- ***No-code***: **KNIME** (lienzo de nodos para ETL, gratis, se integra con bases de datos) y **n8n** para flujos. Asistentes para código: Genie, Copilot, Claude Code, Cursor, Gemini.
- **Microsoft Fabric vs Databricks**: Fabric replica la idea (también tiene Medallion) e integra el ecosistema Microsoft; si sabes Databricks, te mueves igual en Fabric.

## 💻 Práctica — Modelo servido como endpoint (repaso de la práctica de presión de agua)
Se recordó la **Práctica 1** (sensores de presión de agua: riesgo si < 35–40 PSI) y, sobre el modelo de árboles, se completó el ciclo **entrenar → registrar con MLflow → servir como endpoint**. La mayoría del grupo dejó su **endpoint servido** durante la clase.

## 🧪 Práctica 3 (introducción) — Imágenes reales vs generadas por IA
Se presentó la **Práctica 3**: un modelo que **distingue imágenes reales de imágenes creadas por IA**, usando catálogo + esquema y guardando las imágenes como **Delta tables**. Quedó planteada para profundizarse en la Clase 4.

## 🗣️ Casos de los equipos (asesorías en vivo)
El profe aterrizó proyectos reales con varios estudiantes:
- **Deforestación en el Chocó** (datos 2019–2020): modelo **geo-temporal** que pinta el avance en un mapa por colores a partir de latitud/longitud.
- **Ventas**: **regresión lineal múltiple** para ver qué variables explican mejor la venta (estandarización de variables, multicolinealidad, *stepwise*) y construir **indicadores de alerta temprana** por cliente/categoría/municipio.
- **Automatización** de un proceso de auditoría (web scraping periódico de un sitio público) llevado a un *job* programado en Databricks.
- **Riesgo de crédito** y modelos supervisados como hilo conductor del curso (con datos de Kaggle).

---

## ✅ Checklist tras la Clase 3
- [ ] Tener el modelo **registrado con MLflow** y **servido como endpoint**.
- [ ] Dominar la creación **catálogo → esquema → volumen** en Unity Catalog (y resolver el típico error de **ruta/OS** y de **nombre del esquema**).
- [ ] Cargar datos crudos (CSV/JSON/imágenes) y entender **Parquet/Delta**.
- [ ] Avanzar el **caso de negocio** del proyecto y su **pipeline Medallion**.
- [ ] **Agendar las asesorías** (3 × 45 min) por WhatsApp/correo. ⚠️ Son clave.

## ⚠️ Advertencias
- **Nombres sin eñes, tildes, mayúsculas ni espacios** (sobre todo el del **esquema**: si es largo o tiene caracteres raros, falla).
- Cuando falle la **ruta** de carga, defínela con la librería **OS**.
- Nunca subas tokens/credenciales al repo.
- Nunca trabajes sobre `main`; usa ramas `feature_*`.
- GitHub = código, no datos.

---

*Resumen generado a partir de la transcripción de la clase del sábado 20 de junio de 2026.*
