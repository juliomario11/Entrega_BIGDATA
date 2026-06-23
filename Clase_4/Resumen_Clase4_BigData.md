# 📋 Clase 4 — Pipelines (script vs declarative), CNN para imágenes y linaje para auditoría (lunes 22 de junio de 2026)

> Cuarta sesión (virtual, grabada). **Cierra la mayor parte del módulo** (el profe insiste en terminar entre esta clase y el jueves). Se completa la **Práctica 3** (clasificar imágenes reales vs IA con redes neuronales), se construye un **pipeline Medallion** de dos formas (**a punta de script** y **declarativo / Lakeflow**), se conecta Databricks desde **VS Code (CLI)** y se cierra con el **linaje de Unity Catalog** como herramienta de **auditoría**. Termina desplegando una **Databricks App**.

---

## 🧭 Lo esencial de esta clase
- **Práctica 3**: clasificar **imágenes reales vs generadas por IA** con **redes neuronales convolucionales** (PyTorch/TensorFlow), **Optuna** para optimizar hiperparámetros y **MLflow** para la traza → servir el **endpoint**.
- **Pipeline Medallion** de dos maneras: **por script** (bronce → silver → gold) y **declarativo** (*Declarative / Lakeflow Pipeline*). Conceptos de **append vs overwrite** y **jobs** programados.
- **Lakeflow / Flow Designer**: diseñar flujos de datos de forma visual; **funciones AI/SQL** con LLM para analizar texto dentro de datos estructurados (**análisis de sentimiento**).
- **VS Code + CLI de Databricks** (host + access token) para orquestar el repo y los pipelines, portable a otras nubes.
- **ELT vs ETL**, propiedades **ACID** y **Hadoop/MapReduce** como base del porqué hoy se "carga primero y se transforma después".
- **Unity Catalog y linaje** como defensa ante una **auditoría** (caso **riesgo de crédito / scoring**). El linaje ≈ **50% de la nota**.

---

## 1. Continuación: Práctica 3 — imágenes reales vs IA
Se retomó lo planteado en la Clase 3. El pipeline del notebook:
- **Librerías**: PyTorch/`torch` (tensores e imágenes), TensorFlow, scikit-learn, **Optuna** (busca la red óptima: cuántas capas ocultas y neuronas), **MLflow** (registra el modelo para servirlo después).
- **Redes neuronales convolucionales (CNN)**: resumen la imagen en sus componentes significativos (color, forma).
- Se descargan imágenes (reales vs imaginarias), se guardan en **bronce** (Medallion) y se entrena por **épocas** hasta minimizar la **función de pérdida**.
- Evaluación con la **matriz de confusión** (aciertos/errores real vs falso); el profe recordó que **en la realidad siempre se falla algo** (cuidado con exactitudes "perfectas").
- Cierre: registrar el modelo → buscarlo en **Models** → **servir el endpoint**.

## 2. ELT vs ETL, ACID y Hadoop
- Hoy se **carga la data cruda** (bronce/`load`) y **luego se transforma**, al revés del ETL clásico; abaratado por el avance del almacenamiento (estado sólido) y por el algoritmo **MapReduce/Hadoop** (lleva el código a los datos).
- **ACID**: Atomicidad, Consistencia, Aislamiento (*isolation*) y Durabilidad → por eso es muy difícil perder información en grandes volúmenes (autosalvado y réplicas en varios clústeres).
- *Guiño futuro*: **computación cuántica** (estados probabilísticos entre 0 y 1) y librerías como **Qiskit** de IBM.

## 3. Pipeline Medallion: por script vs declarativo
- **Por script** (lo que ya hacían en asesoría): ingesta de un *source* → *landing*/cruda → **bronce** (con `overwrite` por fines académicos; en producción se usa **append** para no reescribir la historia) → **silver** (depuración) → **gold** (lista para modelo/visualización) → un **job** sincroniza cada actividad (como en el Flow).
- **Declarativo** (*Declarative / Lakeflow Pipeline*): el mismo resultado pero "por tubitos", encadenando pasos con funciones declarativas. Es otra forma de automatizar la **ingesta → carga → transformación**.
- **Dataset guía**: **eficiencia energética y emisiones de CO₂ en edificios** (*Open Data Aragón*, España). Casos: predecir consumo energético (**regresión multivariable**), predecir emisiones de CO₂ y **detectar anomalías** (también útil para fraude/ciberataques). Se distinguen variables **categóricas** vs **numéricas** antes de modelar.

## 4. Lakeflow / Flow Designer y funciones AI dentro de SQL
- **Flow Designer**: los arquitectos diseñan flujos visualmente (cargar CSV → transformaciones → operaciones). En *Free Edition* algunas piezas automáticas no están, pero se ve el concepto (similar a KNIME).
- **Funciones AI/SQL**: dentro de una tabla estructurada suele haber texto **no estructurado** (reseñas, comentarios). Con una **función SQL que invoca un LLM** se hace **análisis de sentimiento** o se extrae la razón de (dis)gusto del cliente. ⚠️ Consumen **tokens** (pueden ser costosas).

## 5. Conectar Databricks desde VS Code (CLI)
Con la librería **CLI de Databricks** basta el **host** + **access token** para conectarse desde **VS Code** y orquestar el repositorio, el código y los **pipelines**. La misma idea sirve para **Azure** u otras nubes, y maneja diversidad de formatos (`.py`, `.ipynb`, SQL, R, etc.).

## 6. Linaje de Unity Catalog = auditoría (caso riesgo de crédito)
Por qué el **linaje** es tan importante (y vale ~**50%**): cuando llega un **auditor** y pregunta por qué a un cliente le salió cierto **scoring** o categoría de riesgo (p. ej. "estándar"), hay que **demostrar de qué variables proviene** ese resultado. Si no se puede, se considera **discriminación** y acarrea **sanciones costosas** (crítico en bancos / IFRS 9). Unity Catalog muestra el **linaje** columna a columna y de dónde viene cada dato.

## 🚀 Despliegue de una Databricks App
Cierre práctico: crear una **App** en Databricks (*Go to Databricks → create app → customize*), **agregar un recurso** (database, MLflow Experiment, **serving endpoint** o dashboard) y desplegarla. En *Free Edition* solo se pueden tener **1–2 apps** (la versión premium permite más).

## 🔜 Próxima clase (jueves)
- Crear un **Genie** y **desplegar la app** para todos (incluida la generación de la app que a algunos no les salió).
- Practicar **SQL y NoSQL** (datos estructurados y no estructurados).
- Ver cómo **configurar Databricks en local** (recordando que Databricks "es Spark" y casi todo el stack es open source).

---

## ✅ Checklist tras la Clase 4
- [ ] Completar la **Práctica 3** (CNN imágenes reales vs IA) y **servir su endpoint**.
- [ ] Construir el **pipeline Medallion** (por script o declarativo) con **append** donde corresponda y un **job** que lo orqueste.
- [ ] Conectar el repo desde **VS Code** con la **CLI** (host + token).
- [ ] Verificar el **linaje** en Unity Catalog (pensar en la auditoría del proyecto).
- [ ] Dejar lista una **Databricks App** (endpoint o dashboard).
- [ ] Seguir con **asesorías** y avanzar el proyecto final (**entrega 29 de junio**).

## ⚠️ Advertencias
- En producción usa **append** (no `overwrite`): conservar la historia.
- Las **funciones AI/SQL** consumen tokens → cuidado con el costo.
- *Free Edition*: límite de **apps** y de funcionalidades automáticas de pipeline.
- Nunca subas tokens/credenciales (el **access token** de la CLI es sensible).
- Nunca trabajes sobre `main`; nombres sin eñes, tildes, mayúsculas ni espacios.

---

*Resumen generado a partir de la transcripción de la clase del lunes 22 de junio de 2026.*
