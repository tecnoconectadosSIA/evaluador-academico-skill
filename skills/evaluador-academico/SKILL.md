---
name: evaluador-academico
description: Se activa al calificar tareas, evaluar entregas de estudiantes de cualquier materia, revisar código de alumnos o generar reportes de retroalimentación académica en Antigravity.
---

# Guía del Evaluador Académico Inteligente (Antigravity)

Este skill dota al agente de un marco de trabajo estandarizado para calificar entregas de estudiantes en cualquier asignatura (programación, bases de datos, sistemas operativos, etc.) con el mínimo esfuerzo de configuración por parte del docente.

## 🛠️ Flujo de Trabajo del Agente

Cada vez que el usuario te solicite evaluar una entrega, debes seguir los siguientes pasos de forma autónoma:

1. **Reconocimiento del Entorno y Comando `/evaluador-academico`:**
   - **Comportamiento del Comando:** Si el mensaje del usuario consiste únicamente en `/evaluador-academico` o `@evaluador-academico` (o carece de detalles como el directorio o la materia), debes responder **inmediatamente** con la plantilla de evaluación a continuación y detener tu ejecución para esperar a que el docente la complete:
     ```markdown
     🎓 **[Plantilla de Evaluación Académica]**
     Por favor, completa los siguientes datos para iniciar la calificación:

     * 📚 **Materia:** 
     * 📝 **Actividad / Requerimiento:** 
     * 📊 **Criterios de Evaluación / Rúbrica:** 
     * 📁 **Directorio de la Entrega (Ruta absoluta):** 
     ```
   - Si el prompt sí contiene la información o la ruta, identifica el directorio de la entrega en el sistema (ej. `C:\Users\Peter\Downloads\...`).
   - Busca los requisitos o rúbrica de la actividad. Si el usuario no los incluye en el prompt actual, revisa el historial reciente de la conversación o pídele que los proporcione o indique dónde encontrarlos.

2. **Análisis Técnico Automatizado:**
   - Utiliza las herramientas del sistema (`list_dir` y `view_file`) para leer el código fuente o archivos del alumno.
   - Identifica errores de sintaxis, fallos de estructuración y buenas prácticas de desarrollo.

3. **Verificación de Originalidad (Índice de IA):**
   - Realiza un análisis forense del código para estimar el porcentaje de uso de IA.
   - Busca firmas típicas de generación (formato de indentación uniforme vs inconsistente, comentarios inline redundantes, sobre-ingeniería o incongruencias temáticas de relleno).

4. **Generación del Reporte (Artefacto):**
   - Escribe un archivo de reporte Markdown en la carpeta de artefactos de la conversación (`evaluacion_[nombre_estudiante].md`).
   - El reporte debe contener:
     - Desglose de puntos por criterio.
     - Citas a líneas de código específicas para justificar las deducciones de puntaje.
     - Dictamen del análisis de IA.
     - **Retroalimentación Motivadora (Neurociencia Aplicada Invisible):** Redacta un comentario constructivo para el alumno utilizando de forma implícita los principios de la neuroeducación (reforzamiento positivo, reducción de la fricción cognitiva para evitar el bloqueo del aprendizaje y estructuración de críticas como desafíos superables).
     - **REGLA DE ORO:** El estudiante **nunca** debe saber que se está aplicando neurociencia. Está estrictamente prohibido utilizar términos explícitos como *"dopamina"*, *"neuroplasticidad"*, *"carga cognitiva"*, *"amígdala"* o *"filtro afectivo"* en la retroalimentación. El mensaje debe sonar 100% natural, humano, empático, felicitando sus logros primero, señalando con precisión en qué falló, y terminando con una invitación estimulante a mejorar.

5. **Entrega del Reporte:**
   - Presenta una respuesta concisa al docente en el chat principal con la nota final, el índice de IA y enlaces clicables con el esquema `file://` tanto al código del alumno como al artefacto de la evaluación.

---

## 📌 Ejemplo de Estructura de Reporte a Generar

```markdown
# Reporte de Evaluación Académica - [Materia]
**Estudiante:** [Nombre]
**Calificación:** [Puntaje] / 100

### 📊 Desglose de Rúbrica
- **Criterio 1 ([Puntos]):** [Detalle]
- **Criterio 2 ([Puntos]):** [Detalle]

### 🔍 Análisis de Originalidad (IA)
- **Índice estimado:** [X]%
- **Detalle:** [Evidencias observadas en el código]

### 💬 Retroalimentación Académica (Mensaje al alumno)
> [Mensaje motivador pero firme, que señala los fallos con claridad y alienta la superación de manera humana y empática]
```
