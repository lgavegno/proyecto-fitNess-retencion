# Análisis de Retención - FitNess App

## Descripción del Proyecto

FitNess App es una aplicación móvil de fitness y bienestar que enfrenta un problema crítico de retención de usuarios. Con una tasa de abandono del 65% en el primer mes (vs 40% benchmark industria), el proyecto busca identificar patrones de comportamiento que permitan implementar estrategias de retención personalizadas y reducir el churn al 45%.

## Objetivos SMART del Proyecto

### Objetivo Principal
Reducir la tasa de abandono al primer mes del 65% al 45% mediante la identificación de patrones de comportamiento que permitan implementar estrategias de retención personalizadas, en un plazo de 12 semanas.

### Objetivos Específicos SMART

#### Objetivo 1: Diagnóstico de Abandono (Semanas 1-2)
- **Specific**: Identificar las 5 principales causas de abandono analizando diferencias de comportamiento entre usuarios retenidos vs churned
- **Measurable**: Documentar al menos 5 patrones estadísticamente significativos (p-value < 0.05)
- **Achievable**: Dataset disponible con 11,600 registros de actividad
- **Relevant**: Permite enfocar esfuerzos de retención en causas reales
- **Time-bound**: Semanas 1-2 del proyecto

#### Objetivo 2: Segmentación de Usuarios en Riesgo (Semanas 2-3)
- **Specific**: Crear modelo de segmentación que clasifique usuarios en 3 grupos: Alto riesgo, Medio riesgo, Bajo riesgo de abandono
- **Measurable**: Lograr que el modelo identifique correctamente al 80% de usuarios que abandonarán (recall ≥ 80%)
- **Achievable**: Variables de comportamiento disponibles (frecuencia sesiones, % completado, días activos)
- **Relevant**: Permite activar estrategias proactivas de retención
- **Time-bound**: Semanas 2-3 del proyecto

#### Objetivo 3: Identificación de Contenido Efectivo (Semanas 2-3)
- **Specific**: Determinar qué tipos de planes de entrenamiento y contenido nutricional tienen mayor correlación con retención (r > 0.6)
- **Measurable**: Rankear top 10 planes por tasa de retención de usuarios que los completaron
- **Achievable**: Dataset de progreso_planes.csv e interacciones_nutricion.xlsx disponibles
- **Relevant**: Permite optimizar estrategia de contenido y recomendaciones personalizadas
- **Time-bound**: Semanas 2-3 del proyecto

#### Objetivo 4: Optimización de Onboarding (Semanas 1-2)
- **Specific**: Identificar los 3-5 "eventos clave" durante el onboarding (primeros 7 días) que predicen retención a 30 días
- **Measurable**: Cuantificar el impacto de cada evento (ej: "Completar perfil aumenta retención en 35%")
- **Achievable**: Data de actividad_usuarios.csv con timestamps detallados
- **Relevant**: Permite rediseñar flujo de onboarding para maximizar activación
- **Time-bound**: Semanas 1-2 del proyecto

#### Objetivo 5: Recomendaciones Accionables (Semana 4)
- **Specific**: Generar 10 recomendaciones priorizadas (alta/media/baja prioridad) basadas en hallazgos del análisis
- **Measurable**: Cada recomendación con impacto cuantificado (ej: "Reducir churn en 8%", "Aumentar LTV en $15")
- **Achievable**: Insights de objetivos 1-4 + benchmarks de industria
- **Relevant**: Entregable final que guía plan de acción de 90 días
- **Time-bound**: Semana 4 del proyecto

## Descripción de los 5 Datasets

### 1. Dataset de Actividad (actividad_usuarios.csv)
- **Registros**: 11,600 eventos de actividad en la app
- **Formato**: CSV estructurado
- **Contenido**: Eventos de usuario como inicios de sesión, entrenamientos completados, videos vistos, etc.
- **Variables clave**: ID_Actividad, ID_Usuario, Fecha_Actividad, Tipo_Evento, Duracion_Minutos, ID_Contenido
- **Tipos de eventos**: inicio_sesion, entrenamiento_completado, video_visto, articulo_leido, plan_iniciado, perfil_completado, clase_en_vivo_asistida

### 2. Dataset de Demografía (datos_demograficos.json)
- **Registros**: 1,000 perfiles demográficos de usuarios
- **Formato**: JSON semi-estructurado
- **Contenido**: Información sociodemográfica y de adquisición de usuarios
- **Variables clave**: ID_Usuario, Edad, Genero, Nivel_Fitness, Fuente_Registro, Ciudad
- **Niveles de fitness**: Principiante, Intermedio, Avanzado
- **Fuentes de registro**: Facebook, Google, Referido, Organico

### 3. Dataset de Suscripciones (suscripciones_usuarios.xlsx)
- **Registros**: 1,050 registros de estado y pagos
- **Formato**: Excel estructurado
- **Contenido**: Información completa de suscripciones y pagos
- **Variables clave**: ID_Suscripcion, ID_Usuario, Fecha_Inicio, Estado_Suscripcion, Costo_Suscripcion_USD, Metodo_Pago
- **Estados**: Activa, Cancelada, Vencida, Renovada
- **Métodos de pago**: Tarjeta_Credito, PayPal, Transferencia

### 4. Dataset de Progreso (progreso_planes.csv)
- **Registros**: 2,025 registros de avance en entrenamientos
- **Formato**: CSV estructurado
- **Contenido**: Seguimiento del progreso de usuarios en planes de entrenamiento
- **Variables clave**: ID_Progreso, ID_Usuario, ID_Plan, Porcentaje_Completado, Fecha_Actualizacion, Tipo_Plan
- **Tipos de planes**: Cardio, Fuerza, Yoga, HIIT, Perdida_Peso

### 5. Dataset de Nutrición (interacciones_nutricion.xlsx)
- **Registros**: 1,200 métricas nutricionales registradas
- **Formato**: Excel estructurado
- **Contenido**: Interacciones de usuarios con el módulo de nutrición
- **Variables clave**: ID_Interaccion_Nutricion, ID_Usuario, Fecha_Registro, Metrica_Registrada, Valor_Metrica
- **Métricas**: Calorias, Proteinas, Agua, Carbohidratos, Grasas

## KPIs Principales

- **Tasa de Abandono Actual**: 65% → **Objetivo**: 45%
- **Tasa de Retención a 30 días**: 35% → **Objetivo**: 55%
- **Tasa de Renovación**: 35% → **Objetivo**: 60%
- **Impacto Financiero**: Reducción de pérdida anual de $450K USD en MRR

## Estructura del Proyecto

```
├── README.md
├── requirements.txt
├── 01_exploracion_y_carga_fitness.ipynb
├── 02_limpieza_ETL_unificacion.ipynb
└── data/
    ├── docs/
    │   └── 00_fase0_planificacion/
    │       └── 01_definicion_proyecto
    ├── raw/
    ├── processed/
    ├── outputs/
    └── src/
```

## 🚀 Estado de Avance del Proyecto

### Fase 1: Diagnóstico y Carga (Completada ✅)
* **Hito:** Identificación del "Churn Temprano". 
* **Hallazgo Crítico:** Se confirmó que el **46.4% de los usuarios abandona la app en los primeros 7 días**, validando la importancia del Objetivo 4 (Optimización de Onboarding).

### Fase 2: Unificación y Limpieza - ETL (Completada ✅)
* **Hito:** Creación del Dataset Maestro.
* **Integración:** Consolidación de 11,600 registros de actividad con datos demográficos y de suscripción.
* **Limpieza:** Tratamiento del 100% de valores nulos (27,700 celdas corregidas) mediante imputación técnica.
* **Calidad de Datos:** Dataset final con **0 nulos**, listo para el análisis predictivo.

## Tecnologías Utilizadas

- **Python 3.11** con Pandas, NumPy, Matplotlib, Seaborn
- **Jupyter Notebook** para análisis exploratorio
- **Power BI** para dashboards interactivos
- **Excel** para análisis preliminares
- **Git/GitHub** para control de versiones
