# 📊 Telecom X — Análisis de Evasión de Clientes (Churn)

Análisis exploratorio de datos (EDA) completo para identificar patrones y factores que influyen en la cancelación de clientes de una empresa de telecomunicaciones.

> Challenge ONE Data Science LATAM — Parte 1 | Dataset provisto por Alura Latam.
> 
> 👉 Este proyecto es la base del modelo predictivo: [telecom-x-churn-prediction](https://github.com/antonellarios/telecom-x-churn-prediction)

---

## 🎯 Objetivo

Telecom X enfrenta una alta tasa de cancelación de clientes. Este análisis busca **identificar qué variables explican el churn** para que el equipo de negocio pueda diseñar estrategias de retención antes de avanzar al modelado predictivo.

---

## 🔄 Pipeline ETL

Una de las particularidades de este proyecto es que los datos **se obtienen desde una API pública en formato JSON con estructura anidada** — no desde un CSV plano. El proceso ETL incluye:

```
API JSON (anidado)
      │
      ▼
Extracción con pd.read_json()
      │
      ▼
Normalización de columnas anidadas (customer · phone · internet · account)
      │
      ▼
Limpieza: nulos · duplicados · tipos de datos · inconsistencias lógicas
      │
      ▼
Transformaciones: DailyCharges · TenureGroup · Churn_Binary · estandarización de servicios
      │
      ▼
Dataset limpio listo para EDA y modelado
```

---

## 🧹 Tratamiento de datos

| Problema encontrado | Solución aplicada |
|---|---|
| Columnas anidadas en JSON | `pd.json_normalize()` por cada bloque |
| `TotalCharges` como string | Conversión con `pd.to_numeric(errors='coerce')` |
| Espacios vacíos como valores | Reemplazo por `NaN` con regex |
| Inconsistencia lógica: `tenure=0` con cargos | Imputación a 0 por criterio de negocio |
| Servicios con valor `'No internet service'` | Estandarización a `'No'` |

---

## 📊 Análisis exploratorio

### Variables analizadas
- **Demográficas:** género, pareja, dependientes
- **Contractuales:** tipo de contrato, método de pago, facturación sin papel
- **Servicios:** internet, seguridad online, soporte técnico, streaming
- **Financieras:** cargos mensuales, cargos totales, cargos diarios
- **Temporales:** antigüedad del cliente (tenure), grupo de antigüedad

### Principales hallazgos

| Factor | Impacto en churn |
|---|---|
| Contrato mes a mes | Alta tasa de cancelación vs contratos anuales/bianuales |
| Antigüedad baja (0–12 meses) | Clientes nuevos son los más vulnerables |
| Cargos mensuales altos | Correlación positiva con churn |
| Sin soporte técnico | Mayor tendencia a cancelar |
| Pago por cheque electrónico | Perfil con mayor churn |

---

## 💡 Recomendaciones de negocio

- **Retención en contratos mensuales** — implementar incentivos para migrar a contratos anuales
- **Programa de onboarding** para clientes con menos de 12 meses de antigüedad
- **Revisión de precios** en planes con cargos mensuales elevados
- **Ampliar acceso a soporte técnico** — reduce significativamente la probabilidad de cancelación

---

## 🛠️ Stack tecnológico

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data-150458?logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualización-9cf)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)

- **Librerías:** pandas, numpy, matplotlib, seaborn
- **Entorno:** Google Colab
- **Fuente de datos:** API pública en formato JSON con estructura anidada
- **Técnicas:** ETL desde API, json_normalize, limpieza, EDA, análisis de correlación

---

## 📁 Estructura del proyecto

```
telecomx-churn-analysis/
│
├── TelecomX_Churn_Analysis.ipynb   # Notebook principal (ETL + EDA)
└── README.md
```

---

## 🔗 Proyecto relacionado

Este análisis es la **Parte 1** de un pipeline completo. La Parte 2 construye el modelo predictivo:

👉 [telecom-x-churn-prediction](https://github.com/antonellarios/telecom-x-churn-prediction) — Machine Learning + Predicción

---

## 👩‍💻 Autora

**Antonella Ríos**
Junior Data Analyst | Python · SQL · Power BI · Machine Learning
[LinkedIn](https://www.linkedin.com/in/antonellarios) · [GitHub](https://github.com/antonellarios)
