# Engineering Log - FitNess App Retención

Este documento registra los hitos, decisiones técnicas y hallazgos del proyecto de análisis de retención.

---
## 📅 [2026-02-04] - Conclusión del Objetivo 4: Onboarding y Retención
### 🚨 Hallazgo de "Retención Fantasma"
- **Evidencia**: El 100% de los usuarios exitosos (N=8) registraron su primera actividad recién en el Día 7 [cite: 2026-02-04].
- **Diagnóstico**: La app no retiene, sino que "recupera" usuarios al borde del abandono mediante estímulos externos tardíos [cite: 2026-02-04].
- **Recomendación**: Rediseñar el flujo de los días 1 a 6 para capturar valor antes del vencimiento del acceso [cite: 2026-01-26].

### 🚨 Hallazgo Crítico: Ruptura de Activación
- **Resultado**: 0% de los usuarios que iniciaron actividad el Día 0 alcanzaron el Día 7 [cite: 2026-02-04].
- **Interpretación**: Completar un entrenamiento el primer día no es un predictor de retención; el contenido inicial no está generando el "Aha! Moment" necesario [cite: 2026-01-26].

---

## 📅 [2026-02-03] - Refactorización y Fase 3: Análisis de Contenido
### 🛠️ Refactorización de Integridad (ETL Maestro)
- **Acción**: Saneamiento de registros huérfanos y anomalías temporales en `04_objetivo2_segmentacion_riesgo.ipynb` [cite: 2026-02-04].
- **Resultado**: Reducción de muestra a 1,226 registros con trazabilidad 100% íntegra. Se descartó el segmento "Sin Plan" al identificarse como error de log [cite: 2026-02-04].

### ✅ Hallazgos Saneados (Objetivo 3)
- **Ranking de Efectividad**: **HIIT** (11.57) y **Fuerza** (11.31) lideran la retención real [cite: 2026-02-04].
- **Plan Crítico**: **Meditación** (8.95) presenta el mayor riesgo de abandono tras la limpieza de datos [cite: 2026-02-04].
- **Exportación**: `resumen_efectividad_planes.csv` actualizado con métricas reales [cite: 2026-02-04].

## 📅 [2026-01-27] - Fase 1 & 2: ETL y Segmentación IA
### ✅ Completado
- Unificación de los 5 datasets (CSV, JSON, Excel) en `df_maestro_unificado.csv` [cite: 2026-01-27].
- Implementación de **Risk Scoring (1-10)** normalizado [cite: 2026-01-26].
- Ejecución de **Clustering K-Means** validado por Método del Codo ($k=3$) [cite: 2026-01-26].

### 📊 Hallazgos
- El 99.6% de usuarios provenientes de Facebook Ads se encuentran en el segmento de Riesgo Crítico
- Generación de df_maestro_unificado_scored.csv como base para análisis predictivos

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