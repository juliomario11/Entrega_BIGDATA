# 📋 Resumen — Clase de Big Data (Esp. Analítica de Datos, 1er semestre G2)

> Resumen de la grabación de la reunión en Teams del 06 de junio de 2026. Incluye fechas clave, configuración de GitHub y Databricks, contenido teórico sobre Big Data y arquitectura medallion, y práctica con sensores de presión de agua.

---

## 🗓️ Fechas y logística (¡lo más urgente!)

| Qué | Cuándo | Detalle |
|---|---|---|
| **Próxima clase** | **Mañana 07 de junio a las 8:00** | Workshop práctico: caso de riesgo de crédito leyendo datos desde Kaggle. Cada uno generará código con prompts (Genie). También se hará el *pull* para actualizar el repo. |
| Viaje del profesor | 15–18 de junio | Va al **Databricks Summit en San Francisco**. No hay clase viernes ni esa semana. Regresa el 19 en la noche. |
| Clase 3 | **Sábado 20 de junio** | Confirmó que sí hay clase ese día (hablará con la universidad por el cierre de semestre; avisa por Teams). |
| Clases 4 y 5 | **Lunes 22 y jueves 25 de junio** | Empiezan más tarde de lo normal: **~5:30–5:40 pm**. Se puede asistir virtual. |
| Sexta sesión | Se reemplaza | En vez de una 6ª clase, cada equipo tiene **3 asesorías de 45 minutos** (virtuales). Se piden por **WhatsApp o correo** al profesor y pueden empezar **desde ya**. |
| **Entrega del trabajo final** | **A más tardar el 29 de junio** | Fecha inamovible: el profesor pasa notas ese día porque cierra el semestre. |

---

## 📦 Trabajo final (sí hay entrega — vale la materia)

Se hace en **equipos de 2 personas (máximo 3)**. Los pasos y fechas están publicados en **Teams** junto con las 3 presentaciones del curso (en inglés). Componentes que debe tener:

1. **Caso de negocio** — puede ser real (de tu empresa) o con datos ficticios/simulados.
2. **Análisis beneficio–costo** — *cualitativo*, no cuantitativo: qué beneficio trae la solución vs. lo que cuesta (ej.: una IA de 300 USD/mes que reemplaza el trabajo de 3 funcionarios, ¿vale la pena?).
3. **Arquitectura propuesta** — diagrama de qué herramientas/frameworks vas a usar para captura, procesamiento, almacenamiento, modelado y visualización. *El profesor dijo que esta parte pesa ~10% del trabajo.*
4. **Pipeline de ingesta de datos** — automatización de cómo los datos viajan desde la fuente hasta el consumo (arquitectura *medallion*: bronce → plata → oro).
5. **Modelo / análisis** — el dato debe terminar siendo consumido por un modelo o regla de negocio.
6. **Visualizaciones** — Power BI, Tableau u otra herramienta vista en clase.
7. **Repositorio en GitHub** — todo documentado en Markdown (README con: caso de negocio, análisis económico, arquitectura, fuente de datos, cómo se ejecuta, qué hace el modelo). El profesor mostró ejemplos de estudiantes anteriores (predicción de partidos de Champions, scoring de cartera, dashboard de acueductos) y su propio repo de un robot que detecta fallas en alcantarillados con YOLO. La meta: *superar esos trabajos*.

> 💡 También insistió en que en Databricks, el **catálogo / linaje de datos (Unity Catalog)** es clave — lo describió como "el 50% de lo que tienen que hacer para ganar la materia". Tenlo presente al armar el pipeline.

---

## 🐙 Qué debes hacer en GitHub (paso a paso de la clase)

La clase fue muy práctica en esto. Si no estuviste, esto es lo que todos hicieron y tú debes replicar:

1. **Crear cuenta en GitHub** (github.com) — recomendado con **correo personal de Gmail** (entra directo, sin fricción). Sin eñes, tildes ni mayúsculas en nombres de usuario/repos.
2. **Hacer *fork* del repositorio del profesor** — el link es **https://github.com/yeiscop/Big_Data** (repo llamado `Big_Data`, con guion bajo). Fork ≠ clone: el fork te deja **dueño de tu propia copia** para siempre. Botón **Fork → Create new fork**.
3. **Crear cuenta en Databricks Free Edition** — en el link que compartió en Teams, con **correo personal** (no el institucional, salvo que tu empresa tenga convenio). No pide tarjeta de crédito.
4. **Clonar tu fork dentro de Databricks**: `New → More → Git folder` → pegar la URL de tu repo (botón verde **Code** en GitHub → copiar la URL HTTPS) → **Create Git folder**.
5. **Generar un Personal Access Token en GitHub**: tu foto de perfil → **Settings → Developer settings → Personal access tokens → Tokens (classic) → Generate new token (classic)** → ponle un nombre (ej. `clase`), expiración por defecto (30 días), y **marca todos los scopes** → generar y **copiar el token**.
6. **Linkear GitHub con Databricks**: en Databricks, tu inicial (arriba a la derecha) → **Settings → Linked accounts → Add Git credential → Personal access token** → pega tu correo de GitHub y el token → **Save**.
7. **Crear una rama (branch)**: en tu Git folder, clic en `main` → **Create branch** → nombre en minúsculas con guion bajo, ej. `feature_clase`. **Nunca trabajes directo sobre `main`** — trabajas en la rama y luego los cambios se aprueban/versionan (eso es Git: un gestor de versiones de código; GitHub es "el jefe" que autoriza los cambios de "la empresa", que es Databricks).
8. ⚠️ Regla de oro al programar: **nada de eñes, tildes, mayúsculas ni espacios** en nombres de archivos, ramas o variables.

> Nota: GitHub es para **código**, no para almacenar datos (el profe subió datos ahí solo por fines de clase).

---

## 🧠 Metodología del curso

- **6 sesiones**, pero quedan **5 clases efectivas** + **3 asesorías de 45 min por equipo** que reemplazan la sexta (para nivelar, porque hay perfiles muy diversos: administradores, politólogos, ingenieros, contadores, licenciados...).
- Modalidad **híbrida**: presencial + virtuales conectados por Teams. Las clases se graban.
- Material en **Teams**: 3 presentaciones (en inglés, porque la literatura de ciencia de datos está en inglés) + pasos y fechas del proyecto.
- Dinámica de cada clase: arranca con **noticias del sector** (Hugging Face, papers, Google I/O, Databricks Summit...), luego teoría corta y **mucha práctica guiada** en vivo.
- Evaluación: **no hay parciales** — todo gira alrededor del **proyecto final** (con porcentajes por componente para "sacar el 5").
- Herramienta principal: **Databricks Free Edition** (agnóstica a la nube, sin configurar servidores, sin tarjeta). Se complementa con vistazos a **AWS (S3, SageMaker), Azure (ADLS Gen2, Azure ML, AI Foundry) y GCP (BigQuery, GCS, Vertex AI)**.
- ⚠️ **No actives BigQuery/GCP con tu tarjeta**: puede generar cobros (el profesor contó que una vez dejó GPUs prendidas y le costó ~3 millones de pesos). Él hace esas demos con su propia cuenta.
- Recomendó registrarse (con correo personal) en **Databricks Academy** — tiene cursos y certificaciones gratis.

---

## 📚 Contenido que te perdiste (resumen conceptual)

### 1. Qué es Big Data — las 5 V
**Volumen, Velocidad, Variedad, Valor y Veracidad.** Big Data aparece cuando la capacidad tradicional de procesamiento ya no alcanza: datos en tiempo real (sensores IoT), no estructurados (imágenes, audio, JSON, PDFs, grafos), y a gran escala. Al final del curso verán también *small data* (qué hacer cuando hay pocos datos).

### 2. Ecosistema de herramientas presentado
- **Visualización**: Power BI, Tableau, Qlik Sense, Dash, Gradio.
- **ML/Modelado**: scikit-learn, TensorFlow, PyTorch, MLflow.
- **Exploración**: pandas, NumPy, Matplotlib, Seaborn.
- **Bases de datos**: Cassandra, MongoDB, Neo4j.
- **Procesamiento masivo**: **Spark** ("el papá de todos") vía **PySpark**; ingesta con **Kafka**.
- **Storage**: AWS S3, Azure ADLS Gen2, Google Cloud Storage; **Kaggle** y **Hugging Face** como fuentes de datos y modelos.

### 3. Arquitectura *Medallion* (la verán a fondo)
Bronce = datos crudos sin tocar → Plata = datos limpios/depurados → Oro = datos curados listos para consumo. (Un compañero confirmó: equivale a capa cruda / depurada / procesada.)

### 4. Plataformas de nube mencionadas
- **AWS Amazon**: muy madura, tiene S3 como storage (puede almacenar cualquier cosa), SageMaker para ML.
- **Azure**: ADLS Gen2 como storage, Azure ML, AI Foundry.
- **GCP (Google Cloud Platform)**: especializada en AI y BigQuery (muy buena para SQL a gran volumen), Google Cloud Storage (GCS), Google Compute Engine (GCE). Manejan TPUs.

### 5. Repositorios como hoja de vida
El profesor enfatizó que si quieren ser analistas de datos y cotizarse en el mercado, **el repositorio es su hoja de vida**. Muestra lo que han hecho. Las empresas organizadas en ciencia de datos deben tener repositorios para no perder el código cuando las personas se van.

### 6. Práctica 1 (en el repo, archivo *practice 1*, formato `.ipynb`)
Simularon sensores de presión de agua con **PySpark**: crear el DataFrame, filtrar presiones > 0, agrupar por sensor y promediar, y marcar riesgo si la presión < 35–40 PSI (regla determinística, sin modelo aún → a esos se les "manda la cuadrilla"). Diferencia visual: tablas de **Spark DataFrame** (`.show()`) vs. **pandas DataFrame** (`display()`).

### 7. Ejercicio con Genie — el asistente de IA de Databricks
Al final hicieron un mini-ejercicio: crear un Notebook nuevo, abrir **Genie** y pedirle con un prompt: *"simular datos de medidores de energía con pandas en Python, transformar valores menores a cero y hacer un modelo de regresión para pronosticar futuras medidas"*. Genie genera todo el código (instala librerías, hace EDA, series de tiempo con tendencia/estacionalidad, train/test split). Mensaje del profe: *"ya no van a ser programadores, sino orquestadores de código"* (GitHub Copilot, Claude Code, Cursor, Gemini...). Todo se guarda solo (auto-save).

### 8. Noticias del sector
- **Hugging Face**: plataforma con modelos libres de IA.
- **Google I/O**: conferencia de Google del mes pasado con novedades en ciencia de datos.
- **Papers**: investigaciones recientes sobre ciencia de datos.
- **Databricks Summit**: evento en San Francisco del 15 al 18 de junio (donde irá el profesor).

### 9. Tipos de modelos (mención introductoria, lo verán en Modelado)
- **Supervisados**: hay etiqueta histórica (ej. scoring de crédito, motos robadas, pérdida esperada/IFRS 9).
- **No supervisados**: sin etiquetas → clusterización.
- **Semisupervisados**: mezcla de ambos.

### 10. Concepto de orquestadores de código
El profesor explicó que con herramientas como Genie, Copilot, Claude Code, Cursor, Gemini, uno se vuelve un "orquestador de código" en lugar de programar directamente. Le dices qué quieres y la IA genera el código en el lenguaje que necesites (SQL, R, Ruby, C, C++, Python, etc.).

---

## 🔧 Herramientas y tecnologías mencionadas

| Categoría | Herramienta | Uso principal |
|---|---|---|
| **Procesamiento** | Spark / PySpark | Procesamiento masivo de datos ("el papá de todos") |
| **Procesamiento** | pandas | Exploración y manipulación de datos en Python |
| **Visualización** | Power BI | Dashboards y visualizaciones |
| **Visualización** | Tableau | Dashboards y visualizaciones |
| **Visualización** | Qlik Sense | Dashboards y visualizaciones |
| **ML** | scikit-learn | Machine learning en Python |
| **ML** | TensorFlow | Deep learning |
| **ML** | PyTorch | Deep learning |
| **ML** | MLflow | Gestión del ciclo de vida de modelos |
| **Exploración** | NumPy | Computación numérica |
| **Exploración** | Matplotlib | Gráficos en Python |
| **Exploración** | Seaborn | Gráficos estadísticos en Python |
| **Bases de datos** | Cassandra | Base de datos NoSQL distribuida |
| **Bases de datos** | MongoDB | Base de datos NoSQL orientada a documentos |
| **Bases de datos** | Neo4j | Base de datos de grafos |
| **Storage - AWS** | S3 | Almacenamiento de objetos (cualquier tipo de dato) |
| **Storage - AWS** | SageMaker | Machine learning en AWS |
| **Storage - Azure** | ADLS Gen2 | Azure Data Lake Storage Gen2 |
| **Storage - Azure** | Azure ML | Machine learning en Azure |
| **Storage - Azure** | AI Foundry | Plataforma de IA de Azure |
| **Storage - GCP** | BigQuery | Data warehouse para SQL a gran escala |
| **Storage - GCP** | GCS | Google Cloud Storage |
| **Storage - GCP** | GCE | Google Compute Engine |
| **Storage - GCP** | Vertex AI | Machine learning en GCP |
| **Fuentes de datos** | Kaggle | Competencias de ciencia de datos y datasets |
| **Fuentes de datos** | Hugging Face | Modelos y datasets de IA |
| **Ingesta** | Kafka | Streaming de datos en tiempo real |
| **Control de versiones** | GitHub | Gestión de versiones de código |
| **Plataforma principal** | Databricks Free Edition | Plataforma unificada para ciencia de datos |
| **IA asistente** | Genie (Databricks) | Asistente de IA para generar código |
| **IA asistente** | GitHub Copilot | Asistente de IA para programar |
| **IA asistente** | Claude Code | Asistente de IA para programar |
| **IA asistente** | Cursor | Editor de código con IA |
| **IA asistente** | Gemini | IA generativa de Google |
| **IA generativa** | ChatGPT | IA generativa de OpenAI |

---

## 💻 Ejercicios prácticos realizados

### Práctica 1: Sensores de presión de agua con PySpark
- **Archivo**: `practice 1` (formato `.ipynb`)
- **Objetivo**: Simular sensores de presión de agua y detectar riesgos.
- **Pasos**:
  1. Crear DataFrame con datos simulados de sensores (columnas: sensor, presión).
  2. Filtrar presiones mayores a 0.
  3. Agrupar por sensor y calcular promedio.
  4. Marcar como "riesgoso" si la presión promedio está por debajo de 35–40 PSI.
  5. Aplicar regla determinística: a los riesgos se les "manda la cuadrilla" para inspección.
- **Diferencia clave**: `.show()` para Spark DataFrame vs `display()` para pandas DataFrame.

### Ejercicio con Genie: Medidores de energía
- **Objetivo**: Simular datos de medidores de energía y hacer un modelo de regresión.
- **Prompt usado**: *"simular datos de medidores de energía con pandas en Python, transformar valores menores a cero y hacer un modelo de regresión para pronosticar futuras medidas"*
- **Lo que Genie generó automáticamente**:
  - Instalación de librerías (pandas, numpy, matplotlib, seaborn).
  - Creación de datos simulados con patrón de consumo realista (consumo base ~50 kW, tendencia que sube 0.01 por hora, componente estacional).
  - Transformación de valores negativos (menores a cero).
  - Análisis exploratorio de datos (EDA): estadísticas descriptivas, gráficos.
  - Preparación de datos para modelado: train/test split.
  - Modelo de regresión para pronóstico.
  - Visualización de consumo vs temperatura.
- **Concepto**: Uno se vuelve un "orquestador de código" en lugar de programar directamente.

---

## 📋 Asignaciones y tareas pendientes

1. **Crear repositorio en GitHub** (para quienes no tienen): tarea pendiente para poder trabajar en el proyecto.
2. **Hacer fork del repositorio del profesor** y clonarlo en Databricks.
3. **Crear rama (branch)** en el repo para trabajar (no trabajar directamente en `main`).
4. **Generar Personal Access Token** en GitHub y vincularlo con Databricks.
5. **Pedir asesoría** (3 sesiones de 45 min por equipo) por WhatsApp o correo al profesor — pueden empezar desde ya.
6. **Definir caso de negocio** para el proyecto final.
7. **Prepararse para la próxima clase** (07 de junio): workshop práctico con caso de riesgo de crédito desde Kaggle.

---

## 📰 Noticias del sector

1. **Hugging Face**: plataforma con modelos libres de IA para ciencia de datos.
2. **Google I/O**: conferencia de Google del mes pasado con novedades en ciencia de datos y IA.
3. **Papers**: investigaciones recientes sobre ciencia de datos disponibles en plataformas académicas.
4. **Databricks Summit**: evento en San Francisco del 15 al 18 de junio de 2026 (el profesor asistirá).

---

## 📝 Detalles específicos de lo que se enseñó

### Sobre los estudiantes
- El grupo es muy diverso: administradores de empresas, ingenieros financieros, ingenieros de sistemas, ingenieros de producción, licenciados en educación, politólogos, contadores públicos, ambientalistas, etc.
- El profesor mencionó que psicólogos, politólogos y médicos a veces trabajan los datos mejor que ingenieros de sistemas porque se vuelven expertos en sus ramas específicas.

### Sobre las presentaciones del curso
- Hay 3 presentaciones en inglés (la literatura de ciencia de datos está principalmente en inglés).
- Las presentaciones fueron generadas con NotebookML y son resúmenes visuales del contenido.
- Conceptos como "aprendizaje por refuerzo" se encuentran en inglés como "reinforcement learning", "capas ocultas" como "hidden layers", etc.

### Sobre la arquitectura medallion en Databricks
- Databricks tiene Unity Catalog que permite 3 medallions: bronce, silver y gold.
- **Bronce**: donde llega la data sin transformar, sin tocar, llega bruta o cruda.
- **Silver**: datos limpios, depurados, más bonitos.
- **Gold**: datos curados listos para consumo.
- El profesor usó el ejemplo de sensores de agua: primero llevan a bronce (datos crudos), luego se aplican condiciones para volverlos más bonitos en plata, y finalmente a gold para consumo.

### Sobre Spark vs pandas
- Spark es "el papá de todos" para procesar grandes volúmenes de datos.
- Spark solamente entiende Linux; en Windows hay dificultades para configurarlo on premise.
- PySpark es la librería de Python para Spark.
- En la práctica se usó: Spark DataFrame (`.show()`) vs pandas DataFrame (`display()`).
- Hay estudiantes que prefieren PySpark, otros prefieren pandas.

### Sobre el análisis exploratorio de datos (EDA)
- Siempre hay que hacer EDA antes de crear un modelo.
- Incluye estadísticas descriptivas, visualización de datos, identificación de valores negativos o anomalías.
- En el ejemplo con Genie, se hizo: consumo vs temperatura, correlogramas, análisis de estacionalidad.

### Sobre series de tiempo
- Las series de tiempo tienen varios componentes: estacionalidad (qué tan a menudo se repite), tema autoregresivo (lo que hoy depende de cuánto atrás), tema de tendencia (baja, alta), estacionario y media móvil.
- Los que manejan series de tiempo se encontrarán mucho con SARIMAS (Estacionalidad Auto Regresivo Integrado de Media Móvil con variables Exógenas).

### Sobre la importancia del caso de negocio
- El profesor enfatizó: "Importante es el caso de negocio, el pronto".
- Más que la programación, lo importante es tener un caso de negocio claro que justifique el uso de ciencia de datos.

---

## ⚠️ Advertencias y recomendaciones

- **No actives BigQuery/GCP con tu tarjeta**: puede generar cobros inesperados.
- **Regla de oro**: nada de eñes, tildes, mayúsculas ni espacios en nombres de archivos, ramas o variables.
- **Nunca trabajes directo sobre `main`**: siempre crea una branch y trabaja allí.
- **GitHub es para código, no para almacenar datos** (el profe subió datos ahí solo por fines de clase).
- **El repositorio es tu hoja de vida**: si quieres ser analista de datos y cotizarte en el mercado, mantén un repositorio público con tus proyectos.
- **Las empresas organizadas en ciencia de datos deben tener repositorios**: para no perder el código cuando las personas se van.

---

## 🎯 Próximos pasos

1. **Mañana 07 de junio**: workshop práctico con caso de riesgo de crédito desde Kaggle.
2. **Hacer pull** del repo para actualizar cambios.
3. **Pedir asesoría** si aún no lo has hecho (3 sesiones de 45 min por equipo).
4. **Definir caso de negocio** para el proyecto final.

---

## 📄 Documentos de referencia complementarios

En la carpeta `Documentos/` encontrarás material adicional que complementa lo visto en esta clase:

| Documento | Tema Principal | Relevancia para esta clase |
|---|---|---|
| **Big_Data_UNAULA_First_Module.pdf** | Fundamentos de Big Data - Módulo 1 UNAULA | Refuerza los conceptos de las 5 V y el ecosistema de herramientas |
| **AI_Native_Data_Blueprint.pdf** | Arquitectura de datos nativa para IA | Complementa la arquitectura Medallion y diseño de pipelines |
| **Modern_Data_Refinery.pdf** | Refinería de datos moderna | Profundiza en los procesos de transformación de datos (bronce → plata → oro) |
| **Big_Data_to_AgentOps.pdf** | Evolución de Big Data a operaciones con agentes | Relacionado con el uso de Genie y orquestación de código con IA |
| **PROYECTO_FINAL.pdf** | Especificaciones detalladas del proyecto final | Detalles completos sobre los 7 componentes del trabajo final mencionados en clase |

> 💡 Para esta clase, los documentos **AI_Native_Data_Blueprint.pdf** y **Modern_Data_Refinery.pdf** son especialmente relevantes para profundizar en la arquitectura Medallion y el diseño del pipeline de datos del proyecto final. El documento **Big_Data_to_AgentOps.pdf** complementa la discusión sobre Genie y el futuro de la orquestación de código con IA.
5. **Revisar las presentaciones** en Teams para prepararte para las próximas clases.

---

*Resumen generado el 13 de junio de 2026 basado en la transcripción de la clase del 06 de junio de 2026.*
