# Registro de Decisiones Técnicas (ADR)

## ADR 01: Saneamiento de Integridad Referencial (ETL Maestro)
**Fecha:** 2026-02-03  
**Contexto:** Se detectaron métricas de retención inconsistentes (>100%) y un volumen masivo de logs sin fecha de registro asociada.  
**Decisión:** Ejecución de purga masiva de 10,374 registros (89% de la muestra inicial) que presentaban anomalías temporales o eran registros "huérfanos".  
**Consecuencia:** Reducción del dataset a 1,226 registros íntegros. Esto permite que los KPIs de negocio (Churn, LTV, Retención) sean estadísticamente veraces y no basados en ruido técnico [cite: 2026-02-04].

## ADR 02: Normalización de Métrica de Retención (Sticky Factor)
**Fecha:** 2026-02-04  
**Contexto:** La retención clásica sobre el universo total de usuarios (682) diluía la visibilidad del comportamiento de los usuarios que efectivamente activaron la app.  
**Decisión:** Implementar el "Sticky Factor" como métrica principal, utilizando como denominador únicamente a los 55 usuarios con actividad detectada en la Semana 1.  
**Consecuencia:** Detección de la "Retención Fantasma", donde el 100% de los usuarios exitosos registran actividad recién en el Día 7 [cite: 2026-02-04].
 