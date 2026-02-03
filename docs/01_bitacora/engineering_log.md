# Engineering Log - FitNess App Retención

Este documento registra los hitos, decisiones técnicas y hallazgos del proyecto de análisis de retención.

---

## 📅 [2026-02-03] - Fase 3: Análisis de Contenido (Finalizada)
### ✅ Completado
- Creación de métrica personalizada: **Índice de Efectividad** ($Progreso / Riesgo$) [cite: 2026-01-26].
- Ranking de planes: **Cardio** (9.25) y **HIIT** (9.20) identificados como los mejores retenedores [cite: 2026-01-26].
- Exportación de `resumen_efectividad_planes.csv` para uso en visualización [cite: 2026-01-26].

### 📊 Hallazgos
- El 61% de la muestra (**7,070 usuarios**) no tiene un plan asignado y presenta el mayor riesgo de abandono (Risk Score: 7.49) [cite: 2026-01-26].
- Los planes de **Fuerza** son los menos efectivos entre los activos, con la menor tasa de completitud (44.5%) [cite: 2026-01-26].

### 💡 Decisiones
- Se decide mantener a los usuarios "Sin Plan" en el dataset para proponer estrategias de conversión de onboarding [cite: 2026-01-26].

### ⏭️ Próximo paso (Fase 4)
- Analizar el embudo de los primeros 7 días (Onboarding) en la rama `feature/objetivo4-onboarding` [cite: 2026-01-08, 2026-01-26].

---

## 📅 [2026-01-27] - Fase 1 & 2: ETL y Segmentación IA
### ✅ Completado
- Unificación de los 5 datasets (CSV, JSON, Excel) en `df_maestro_unificado.csv` [cite: 2026-01-27].
- Implementación de **Risk Scoring (1-10)** normalizado [cite: 2026-01-26].
- Ejecución de **Clustering K-Means** validado por Método del Codo ($k=3$) [cite: 2026-01-26].

### 📊 Hallazgos
- El 99.6% de usuarios provenientes de Facebook Ads se encuentran en el segmento de Riesgo Crítico [cite: 2026-01-27].

---

## 📅 [2026-01-19] - Fase 0: Inicialización
### ✅ Completado
- Creada estructura de carpetas y entorno virtual.
- Exploración inicial de 11,600 registros de actividad.

### 🐛 Problemas y Soluciones
- Error de encoding en `datos_demograficos.json`. **Solución:** Uso de `encoding='utf-8-sig'`.

### 💡 Decisiones
- Eliminación de duplicados exactos (15 filas).
- Conservación de outliers en duración para capturar sesiones extendidas válidas.