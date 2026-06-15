# 📋 Clase 1 — Introducción a Big Data + Setup (05 de junio de 2026)

> Primera clase del curso (grabada en Teams). Introducción a Big Data, metodología, y el **setup práctico de GitHub + Databricks** que todos deben replicar. Arquitectura Medallion y primera práctica con PySpark.

---

## 🧭 Lo esencial de esta clase
- Qué es Big Data (las **5 V**) y cuándo aplica.
- **Metodología** del curso y cómo se evalúa (todo gira en torno al proyecto final).
- **Setup de GitHub** (cuenta → fork → PAT → branch).
- **Setup de Databricks Free Edition** (cuenta → Git folder → linked accounts).
- Intro a **arquitectura Medallion** y a **Genie**.

---

## 1. ¿Qué es Big Data? Las 5 V
**Volumen, Velocidad, Variedad, Valor y Veracidad.** Aparece cuando la capacidad tradicional de procesamiento ya no alcanza: datos en tiempo real (sensores IoT), no estructurados (imágenes, audio, JSON, PDFs, grafos) y a gran escala. Al final del curso se verá también *small data*.

## 2. Metodología del curso
- **6 sesiones** → **5 clases efectivas** + **3 asesorías de 45 min por equipo** (reemplazan la 6.ª).
- Modalidad **híbrida** (presencial + Teams); las clases se graban.
- Material en **Teams**: 3 presentaciones en inglés (hechas con NotebookLM) + pasos y fechas del proyecto.
- Dinámica: **noticias del sector** → teoría corta → **mucha práctica guiada**.
- **Sin parciales**: la nota es el **proyecto final** (con porcentajes por componente).
- Herramienta principal: **Databricks Free Edition** (sin tarjeta, agnóstica a la nube).

## 3. Ecosistema de herramientas presentado
- **Procesamiento**: Spark ("el papá de todos") vía PySpark; ingesta con Kafka.
- **Visualización**: Power BI, Tableau, Qlik Sense, Dash, Gradio.
- **ML**: scikit-learn, TensorFlow, PyTorch, MLflow.
- **Exploración**: pandas, NumPy, Matplotlib, Seaborn.
- **Bases de datos**: Cassandra, MongoDB, Neo4j.
- **Storage / fuentes**: AWS S3, Azure ADLS Gen2, GCS; Kaggle y Hugging Face.

---

## 🐙 Setup de GitHub (paso a paso)
1. **Crear cuenta** en github.com con **correo personal de Gmail** (sin ñ, tildes, mayúsculas ni espacios).
2. **Fork** del repo del profesor → **https://github.com/yeiscop/Big_Data** (Fork → *Create new fork*). El fork te hace **dueño de tu propia copia**.
3. **Personal Access Token (PAT)**: perfil → *Settings → Developer settings → Personal access tokens → Tokens (classic) → Generate new token (classic)* → nombre `clase`, expiración 30 días, marcar scopes necesarios → **copiar el token** (no lo subas al repo).
4. **Crear rama**: en el Git folder, clic en `main` → *Create branch* → ej. `feature_clase`. **Nunca trabajes sobre `main`.**

> GitHub es para **código**, no para datos.

## 🧱 Setup de Databricks (paso a paso)
1. **Cuenta en Databricks Free Edition** con correo personal (no pide tarjeta).
2. **Clonar tu fork**: `New → More → Git folder` → pegar la URL HTTPS (botón verde **Code** en GitHub) → *Create Git folder*.
3. **Linkear GitHub**: inicial (arriba dcha.) → *Settings → Linked accounts → Add Git credential → Personal access token* → correo + token → **Save**.

---

## 🥉🥈🥇 Arquitectura Medallion (introducción)
**Bronce** (datos crudos sin tocar) → **Plata** (limpios/depurados) → **Oro** (curados, listos para consumo). Se gestiona con **Unity Catalog**.

## 💻 Práctica 1 — Sensores de presión de agua (PySpark) `practice 1.ipynb`
1. Crear DataFrame simulado (sensor, presión).
2. Filtrar presiones > 0.
3. Agrupar por sensor y promediar.
4. Marcar riesgo si presión < 35–40 PSI (regla determinística → "se manda la cuadrilla").
- Diferencia visual: `.show()` (Spark DataFrame) vs `display()` (pandas).

## 🧠 Genie (introducción)
Asistente de IA de Databricks: con un *prompt* genera el código (instala librerías, EDA, modelado). Mensaje del profe: *"ya no serán programadores, sino orquestadores de código"*.

---

## 🎯 Proyecto final (presentado)
Equipos de 2 (máx. 3). 7 componentes: caso de negocio, beneficio–costo, arquitectura, pipeline Medallion, modelo, visualización y repo documentado. **Unity Catalog/linaje ≈ 50%**. Entrega **29 de junio**.

## ✅ Checklist tras la Clase 1
- [ ] Cuenta de GitHub + **fork** de `yeiscop/Big_Data`.
- [ ] Cuenta de Databricks + **Git folder** del fork.
- [ ] **PAT** generado y **linkeado** en Databricks.
- [ ] Rama `feature_clase` creada.
- [ ] Definir **equipo** y empezar a pensar el **caso de negocio**.
- [ ] Agendar la primera **asesoría**.

## ⚠️ Advertencias
- No subas tokens/credenciales al repo.
- Nada de eñes, tildes, mayúsculas ni espacios.
- No trabajes sobre `main`.
- No actives BigQuery/GCP con tarjeta personal.

---

*Resumen generado a partir de la transcripción de la clase del 05 de junio de 2026.*
