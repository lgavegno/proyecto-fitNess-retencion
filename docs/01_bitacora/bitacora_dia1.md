
## ✅ Completado hoy
- Creada estructura de carpetas
- Instaladas librerías Python
- Cargados los 5 archivos en Jupyter
- Exploración inicial de actividad_usuarios.csv

## 📊 Hallazgos preliminares
- El archivo tiene 11,600 registros
- 523 usuarios únicos en actividad_usuarios
- Tipos de eventos encontrados: inicio_sesion, entrenamiento_completado, video_visto

## 🐛 Problemas encontrados
- Error al cargar datos_demograficos.json → encoding UTF-8
- **Solución:** Usar `encoding='utf-8-sig'`

## 💡 Decisiones tomadas
- Decidí eliminar duplicados completos (son solo 15 filas)
- Mantuve outliers en Duracion_Minutos (sesiones de 120+ min son válidas)

## ⏭️ Próximo paso mañana
- Limpiar valores nulos
- Empezar a unir archivos por ID_Usuario

