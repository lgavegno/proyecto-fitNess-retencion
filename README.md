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
- **Specific**: Crear modelo de segmentación **Clustering K-Means ($k=3$)**, validado matemáticamente mediante el **Método del Codo**.
- **Measurable**: Lograr que el modelo identifique correctamente al 80% de usuarios que abandonarán (recall ≥ 80%)
- **Achievable**: Variables de comportamiento disponibles (frecuencia sesiones, % completado, días activos)
- **Relevant**: Permite activar estrategias proactivas de retención
- **Time-bound**: Semanas 2-3 del proyecto

#### Objetivo 3: Identificación de Contenido Efectivo (Semanas 2-3)
- **Specific**: Determinar qué tipos de planes de entrenamiento y contenido nutricional tienen mayor correlación con retención (r > 0.6)
- **Measurable**: Calcular el **Índice de Efectividad ($Progreso / Riesgo$)**, resaltando que HIIT y Fuerza lideran la retención.
- **Achievable**: Dataset de progreso_planes.csv e interacciones_nutricion.xlsx disponibles
- **Relevant**: Permite optimizar estrategia de contenido y recomendaciones personalizadas
- **Time-bound**: Semanas 2-3 del proyecto

#### Objetivo 4: Optimización de Onboarding (Semanas 1-2)
- **Specific**: Identificar los 3-5 "eventos clave" durante el onboarding, analizando el fenómeno de la **"Retención Fantasma"**.
- **Measurable**: Cuantificar el impacto mediante el **Sticky Factor** para normalizar la curva de activación.
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
├── docs/                      # Documentación centralizada
│   ├── 00_fase0_planificacion/
│   ├── 01_bitacora/           # bitacora_ingenieria.md
│   ├── 02_hallazgos/
│   └── 03_entregables_finales/ # reporte_ejecutivo.md
├── notebooks/                 # Jupyter Notebooks (01 al 06)
│   └── figures/               # Gráficos exportados (Assets)
├── data/
│   ├── raw/                   # Datos originales
│   ├── processed/             # df_maestro_unificado_scored.csv
│   └── samples/               # sample_final.csv
└── outputs/                   # Resultados finales
```

## Auditoría de Integridad & Calidad de Datos (Data Governance)

Una de las fases más críticas de este proyecto fue el **Data Sanitization Pipeline**. Se procesó un dataset inicial ruidoso mediante un rigor de auditoría Senior:

- **Universe Refinement**: De 11,600 registros de actividad brutos, se identificó que el 89% presentaba inconsistencias de integridad referencial o stamps temporales corruptos.
- **Integrity Purge**: Se aplicó una purga estricta para consolidar una muestra de **1,226 usuarios con trazabilidad 100% veraz**, garantizando que los insights no fueran artefactos de datos sucios.
- **Imputación Técnica**: Tratamiento de **27,700 celdas nulas** mediante algoritmos de imputación basados en el perfil de usuario, evitando sesgos en el cálculo del Churn.

## Metodología de Análisis Avanzado

### Algoritmos y Modelado Estadístico

- **Clustering K-Means (k=3)**: Implementado para segmentar perfiles de riesgo, validando la estabilidad de los clusters mediante el **Método del Codo**.
- **Cálculo de Sticky Factor**: Cuantificación de la adherencia al onboarding para identificar el **"Aha! Moment"**.
- **Análisis de Correlación de Pearson**: Identificación de la relación directa entre el consumo de contenido de **HIIT/Fuerza** e la retención a largo plazo (r > 0.6).

## Hallazgos de Ingeniería de Producto

- **La Paradoja del Progreso**: Los usuarios churned mostraban una velocidad de progreso un **38% superior** a los retenidos en la primera semana, indicando un patrón de fatiga o expectativas poco realistas en el onboarding.
- **Breakpoint Día 0**: Se detectó una inactividad crítica post-instalación. La curva de activación real se desplaza al Día 7, lo que denominamos **"Retención Fantasma"**.


## Tecnologías Utilizadas

- **Python 3.11** con Pandas, NumPy, Matplotlib, Seaborn
- **Jupyter Notebook** para análisis exploratorio
- **Power BI** para dashboards interactivos
- **Excel** para análisis preliminares
- **Git/GitHub** para control de versiones

## Cómo Ejecutar el Proyecto

1. **Clonar el repositorio**: `git clone https://github.com/tu-usuario/Proyecto-FitnessApp.git`
2. **Instalar dependencias**: `pip install -r requirements.txt`
3. **Ejecución**: Abrir los cuadernos en la carpeta `/notebooks` y ejecutarlos en orden numérico (01 al 06) para reproducir el análisis completo.

## Conclusiones de Negocio
- **Aha! Moment**: El contenido de **HIIT y Fuerza** es el principal motor de retención real.
- **Fuga Crítica**: Se identificó una desconexión total en el Día 0; la app depende de estímulos de último momento (Día 7) para retener usuarios.
- **Estrategia**: Se recomienda adelantar las notificaciones de reactivación al Día 3 para quebrar el patrón de abandono detectado.