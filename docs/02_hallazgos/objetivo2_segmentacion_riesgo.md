# Objetivo 2: Segmentación Avanzada de Riesgo

## 📊 Metodología de Scoring
Se implementó un modelo de scoring conductual (Risk Score 1-10) ponderando dos dimensiones clave:
- **Inactividad (50%)**: Días transcurridos desde la última sesión.
- **Progreso (50%)**: Porcentaje de completitud del plan de entrenamiento actual.

## 🤖 Segmentación por Machine Learning (K-Means)
Se validó la segmentación manual mediante un algoritmo de clustering K-Means ($k=3$), obteniendo una alta correlación entre la lógica de negocio y los patrones matemáticos identificados.

### Perfiles de Segmentos Identificados:

| Segmento | Volumen | Perfil del Usuario | Acción Recomendada |
| :---     | :---    | :---               | :---                 |
| **Riesgo Crítico** | 3,258 | Abandono confirmado. Inactividad máxima y nulo progreso. | Análisis de baja y encuesta de salida. |
| **Riesgo Medio** | 4,192 | El "Segmento de Intervención". Usuarios que entran pero no logran avanzar. | Notificaciones push de motivación y ajuste de dificultad. |
| **Bajo Riesgo** | 1,686 | Usuarios leales y activos. Alto progreso y uso frecuente. | Programas de referidos y beneficios VIP. |

## 💡 Hallazgo Estratégico
El **Cluster 1 (Riesgo Medio)** es el grupo más numeroso. Esto indica que el problema principal de la app no es atraer usuarios, sino ayudarlos a superar la barrera de completar su primera rutina.