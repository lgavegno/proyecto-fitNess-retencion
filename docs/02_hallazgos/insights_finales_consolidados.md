# Insights Finales Consolidados - FitNess App

## 1. El Problema Estructural (Data Integrity)
Tras auditar 11,600 registros, se determinó que la base de datos sufría de una grave falta de integridad referencial. La purga técnica a **1,226 registros veraces** fue necesaria para evitar falsos positivos en las métricas de retención.

## 2. La Paradoja de la Intensidad
Los usuarios que abandonan (Churn) muestran un progreso inicial superior (~18%) al de los usuarios retenidos (~13%).
*   **Insight**: El exceso de actividad inicial es un predictor de fatiga (burnout) y no de compromiso a largo plazo.

## 3. Segmentación y Origen de Tráfico
El Clustering K-Means ($k=3$) reveló que el **99.6%** de los usuarios captados vía Facebook Ads entran directamente en el segmento de "Riesgo Crítico".
*   **Insight**: La estrategia de adquisición actual atrae usuarios con baja intención de uso o expectativas desalineadas con el producto.

## 4. El Mapa de Valor del Contenido
Utilizando el **Índice de Efectividad** ($Progreso / Riesgo$), se identificó el core de valor de la app:
*   **Ganadores**: HIIT ($11.57$) y Fuerza ($11.31$).
*   **Crítico**: Yoga y Meditación presentan los niveles más bajos de adherencia.

## 5. El Fenómeno de la "Retención Fantasma"
La métrica **Sticky Factor** confirmó que no existe activación real en el Día 0. Los usuarios retenidos "despiertan" recién al Día 7.
*   **Insight**: Existe una ventana de inactividad peligrosa de una semana donde la app es invisible para el usuario.

---

## Conclusión Estratégica
La solución a la retención no es "más contenido", sino una mejor gestión de la intensidad inicial y un onboarding agresivo centrado en HIIT/Fuerza que se active antes del Día 3.
