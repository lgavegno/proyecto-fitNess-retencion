# Objetivo 1: Diagnóstico de Causas de Abandono (Churn)

## 📊 Resumen Ejecutivo
El análisis de los primeros 11,600 registros revela un estado crítico de retención, con una tasa de riesgo promedio del **46.4% semanal** y una proyección de abandono superior al **98%** en la mayoría de los segmentos.

## 🔍 Hallazgos Clave

### 1. Ineficacia del Nivel de Fitness como Segmentador
- Los usuarios **Principiantes** presentan una tasa de riesgo del **98.9%**, mientras que los **Avanzados** están en **98.4%** 
- **Insight**: El nivel de dificultad técnica no es la causa raíz del abandono; el problema es transversal 

### 2. Elasticidad de Precio Inexistente
- No hay diferencia significativa entre usuarios de bajo costo ($10 - $100) y alto costo ($100 - $199), ambos superan el **97.9%** de riesgo 
- **Insight**: El costo de la suscripción no está reteniendo a los usuarios premium ni expulsando a los básicos

### 3. Fuga en Adquisición (Facebook Ads)
- Los usuarios provenientes de **Anuncio Facebook** tienen la tasa de riesgo más alta documentada: **99.6%** 
- **Insight**: Existe un desajuste crítico entre la promesa de marketing en redes sociales y la propuesta de valor real de la app 

### 4. Punto Ciego en la Trazabilidad
- El **80.5% (9,344 registros)** de la base de usuarios figura como "No Registrado" en su fuente de origen 
- **Insight**: La falta de datos de atribución impide identificar canales saludables de adquisición 

### 5. Paradoja del Progreso
- Los usuarios en riesgo muestran, en promedio, un mayor avance en los planes que los usuarios activos.
- **Insight**: El abandono no se debe a la falta de uso, sino posiblemente a la falta de gratificación o resultados percibidos tras el esfuerzo inicial 

---
**Próximo Paso**: Iniciar Fase 4 (Objetivo 2) para realizar el Scoring de Riesgo y Clustering.