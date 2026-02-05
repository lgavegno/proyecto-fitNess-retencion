# Bitácora de Ingeniería - FitNess App

Este documento centraliza el historial de desarrollo, decisiones de arquitectura y hallazgos del análisis de retención, unificando el proceso desde la exploración inicial hasta el reporte ejecutivo.

---

## Registro de Decisiones Técnicas (ADR)

### ADR 01: Saneamiento de Integridad Referencial
- **Fecha:** 2026-02-03
- **Contexto:** Se detectaron métricas de retención inconsistentes (>100%) y logs sin fecha de registro.
- **Decisión:** Purga masiva de 10,374 registros (89% de la muestra inicial) que presentaban anomalías temporales o eran registros "huérfanos".
- **Impacto:** Los KPIs resultantes son estadísticamente veraces y permiten un análisis de supervivencia real.

### ADR 02: Normalización vía Sticky Factor
- **Fecha:** 2026-02-04
- **Contexto:** La retención clásica sobre el universo total diluía la visibilidad del comportamiento activo.
- **Decisión:** Implementar "Sticky Factor" utilizando como denominador únicamente a los 55 usuarios con actividad en la Semana 1.
- **Impacto:** Identificación del fenómeno de "Retención Fantasma" en el Día 7.

---

## Registro Cronológico de Desarrollo

### [2026-02-04] - Fase 4: Onboarding y Cierre Técnico
- **Hallazgo Crítico:** 0% de efectividad en la activación del Día 0 para usuarios que logran retenerse.
- **Evidencia:** El 100% de los usuarios exitosos registran su primera actividad recién en el Día 7.
- **Acción:** Reestructuración de la arquitectura de documentación y generación del Reporte Ejecutivo Final.

### [2026-02-03] - Fase 3: Análisis de Contenido Saneado
- **Resultado:** Los planes de HIIT (11.57) y Fuerza (11.31) se identifican como los motores de retención del producto.
- **Acción:** Se descartó el análisis del segmento "Sin Plan" al confirmarse como un error de log en la captura de datos original.

### [2026-01-27] - Fase 1 & 2: ETL Maestro y Segmentación IA
- **Acción:** Unificación de 5 datasets (CSV, JSON, Excel) en un dataframe maestro scored.
- **IA:** Ejecución de Clustering K-Means ($k=3$) para segmentación de riesgo basada en inactividad y progreso.
- **Hallazgo:** El 99.6% de los usuarios provenientes de Facebook Ads se encuentran en el segmento de Riesgo Crítico.

### [2026-01-19] - Fase 0: Exploración e Integridad Inicial
- **Diagnóstico:** Carga de 11,600 registros de actividad y detección de 5,115 usuarios "fantasma" sin datos demográficos.
- **Churn Temprano:** Identificación inicial de un 46.4% de abandono antes de los 7 días de uso.
- **Soluciones Técnicas:** Implementación de `encoding='utf-8-sig'` para el JSON demográfico y conversión de tipos `datetime` para análisis temporal.
- **Decisiones de Limpieza:** Se eliminaron 15 duplicados exactos y se conservaron outliers en duración (>120 min) por ser plausibles en alto rendimiento.