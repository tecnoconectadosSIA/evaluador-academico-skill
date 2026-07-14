# Evaluador Académico Inteligente (Antigravity Skill)

Habilidad global para Google Antigravity y plataformas de agentes de desarrollo de software compatibles, diseñada para la calificación y retroalimentación académica automatizada de entregas de estudiantes.

## 🚀 Características
- **Evaluación basada en rúbricas:** Analiza de forma autónoma el código y archivos de las entregas y los califica contra los criterios establecidos.
- **Análisis forense de IA:** Evalúa si el código fue generado con IA (revisando patrones de indentación, coherencia y comentarios).
- **Retroalimentación Neurocognitiva Invisible:** Redacta comentarios humanos, empáticos y motivadores, señalando los errores con precisión pero sin desanimar al alumno (sin revelar el uso de técnicas de neurociencia).
- **Invocación por comando:** Permite el uso del comando `/evaluador-academico` para autogenerar una plantilla limpia de solicitud.

## 📥 Instalación

### En Google Antigravity
Clona este repositorio directamente en tu carpeta de configuraciones globales de Antigravity o en la raíz de tu proyecto:

#### Opción A: Instalación Global (Para todas las conversaciones)
Copia la carpeta del skill en:
- **Windows:** `%USERPROFILE%\.gemini\config\skills\evaluador-academico`
- **Linux/macOS:** `~/.gemini/config/skills/evaluador-academico`

#### Opción B: Instalación por Proyecto
Clona la carpeta en la raíz de tu espacio de trabajo:
`[Proyecto]/.agents/skills/evaluador-academico`

## 💬 Uso del Comando
Escribe `/evaluador-academico` en el chat para obtener la plantilla de datos:

```markdown
🎓 **[Plantilla de Evaluación Académica]**
Por favor, completa los siguientes datos para iniciar la calificación:

* 📚 **Materia:** 
* 📝 **Actividad / Requerimiento:** 
* 📊 **Criterios de Evaluación / Rúbrica:** 
* 📁 **Directorio de la Entrega (Ruta absoluta):** 
```
