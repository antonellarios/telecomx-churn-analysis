# Telecom X: Análisis de Evasión de Clientes (Churn)

¡Bienvenido a mi proyecto del **Challenge ONE Data Science**! En este repositorio, presento un análisis profundo sobre la pérdida de clientes en una empresa de telecomunicaciones, aplicando técnicas de **ETL**, **EDA** y pensamiento analítico orientado a negocios.

---

## Contexto del Problema
**Telecom X** enfrenta una alta tasa de cancelaciones de servicios. El objetivo de este proyecto es identificar los factores clave que llevan a los clientes a abandonar la empresa para apoyar la toma de decisiones estratégicas y la retención de usuarios.

---

## Tecnologías y Librerías
* **Lenguaje:** Python 3.x
* **Entorno:** Google Colab
* **Librerías principales:** * `Pandas`: Manipulación y limpieza de datos.
    * `Seaborn` & `Matplotlib`: Visualización estratégica.
    * `Numpy`: Operaciones matemáticas.
    * `JSON`: Extracción de datos.

---

## Flujo de Trabajo (ETL)

### 1. Extracción (Extract)
Los datos fueron provistos en formato **JSON**, simulando la respuesta de una **API REST**. Se utilizó la técnica de normalización para aplanar estructuras anidadas.

### 2. Transformación (Transform)
* **Limpieza de datos:** Se corrigieron inconsistencias en la columna `TotalCharges` (conversión a numérico y manejo de nulos).
* **Estandarización:** Se simplificaron categorías de servicios para un análisis estadístico más coherente.
* **Ingeniería de Características:** Se creó la métrica **DailyCharges** y se segmentó a los clientes por su antigüedad (**TenureGroup**).

### 3. Carga (Load)
El dataset procesado fue exportado a un archivo `telecomx_clean.csv`, optimizado para su uso en modelos de Machine Learning.

---

## Análisis Exploratorio e Insights
A través del análisis visual, se identificaron los siguientes puntos críticos:



* **El factor Contrato:** Los clientes con contrato "Mes a mes" tienen la mayor tasa de abandono (**42%**).
* **Soporte Técnico:** Los usuarios que NO cuentan con servicios de soporte técnico presentan una tasa de evasión significativamente más alta.
* **Sensibilidad al Precio:** Existe una correlación positiva entre los cargos mensuales elevados y la probabilidad de churn.

---

## Conclusiones
Para reducir la evasión en Telecom X, se recomienda:
1.  Incentivar la migración de contratos mensuales a contratos anuales mediante beneficios exclusivos.
2.  Promover servicios de valor agregado (**TechSupport** y **OnlineSecurity**) para aumentar la fidelidad.
3.  Monitorear a los clientes durante su **primer año**, que es el periodo de mayor riesgo detectado.

---

## Estructura del Repositorio
* `TelecomX_LATAM.ipynb`: Notebook con el código completo y documentado.
* `telecomx_clean.csv`: El dataset limpio resultante del proceso ETL.
* `TelecomX_diccionario.md`: Descripción de cada variable del dataset.

---

### Autora
**Antonella Ríos** *Estudiante de Ciencia de Datos* 
