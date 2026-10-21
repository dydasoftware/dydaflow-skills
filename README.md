Dile a tu IA: **«instala la skill de dydaflow»**.

```bash
npx skills add dydasoftware/dydaflow-skills
```

# DyDa Flow · Skills oficiales

**DyDa Flow · Dydaflow · Flow ERP.** Un asistente para **diseñar módulos** y preparar un prompt para el **Diseñador IA**: te pregunta cómo opera tu negocio, propone módulos y campos, y te deja aceptar, quitar o agregar antes de confirmar.

**Repositorio oficial:** [github.com/dydasoftware/dydaflow-skills](https://github.com/dydasoftware/dydaflow-skills), publicado por DyDa Software.

## Instalar y empezar

En una IA que pueda buscar en internet y ejecutar comandos, di «instala la skill de dydaflow». Si no la encuentra, dale el repositorio `dydasoftware/dydaflow-skills` o el comando de arriba. La búsqueda depende de la IA y de la indexación; no todas las cuentas pueden instalar desde una conversación.

Para instalar solo esta skill:

```bash
npx skills add dydasoftware/dydaflow-skills --skill dyda-flow-modulos
```

El CLI permite elegir agente y alcance: en **Claude Code, Codex o Cursor** guarda la skill en la computadora, en el proyecto por defecto; con `-g`, para uso entre proyectos. Consulta la [guía del CLI skills](https://github.com/vercel-labs/skills/blob/main/docs/commands.md).

En **claude.ai**, una descarga o instalación mediante comandos dentro del entorno de una conversación sirve para esa conversación; no la añade automáticamente a tus Skills guardadas. Para conservarla en tu cuenta, usa la carga del ZIP en Personalizar → Skills, como explica la [guía de Claude Desktop y claude.ai](skills/dyda-flow-modulos/README.md). La [ayuda de Anthropic](https://support.claude.com/en/articles/12512180-use-skills-in-claude) documenta esa carga persistente.

Después de instalar, escribe: **«Quiero diseñar los módulos de mi negocio para DyDa Flow»**. No necesitas saber programación. La skill no entra a tu cuenta ni aplica cambios: tú revisas el prompt y el plano en Flow.

## Claude Code como plugin

El repositorio también incluye el manifiesto y el catálogo para Claude Code. Después de publicarlo, esta es una alternativa a instalar con `skills`; elige una de las dos:

```text
/plugin marketplace add dydasoftware/dydaflow-skills
/plugin install dydaflow@dydaflow-skills
```

Dentro de Claude Code puedes invocarla como `/dydaflow:dyda-flow-modulos`. La estructura sigue la [documentación de plugins de Anthropic](https://code.claude.com/docs/en/plugins-reference). No requiere conexiones a Flow, claves ni herramientas adicionales para hacer la entrevista.

## ChatGPT, Gemini y Proyectos de Claude

Copia el texto de [instrucciones para otras IA](skills/dyda-flow-modulos/instrucciones-otras-ia.md) en una conversación o en las instrucciones de tu asistente, Gem o proyecto. Es una alternativa completa que incluye capacidades y límites. La [guía de uso](skills/dyda-flow-modulos/README.md) explica cada opción.

## Qué obtienes

- Una entrevista breve adaptada a tu giro y operación.
- Módulos que aprovechan lo existente, con campos, opciones, ligas y estados revisados contigo.
- Un resumen para confirmar y un prompt listo para el Diseñador IA.
- Indicaciones de qué configurar después y en qué pantalla, sin prometer funciones ajenas al Diseñador.

La primera generación en el Diseñador cuesta **2 créditos**; cada ajuste, **1**. Preparar el prompt en otra IA no consume esos créditos, aunque esa IA puede tener su propio costo. Revisa **Ajustes → Plan y consumo** antes de generar.

Consulta [capacidades](skills/dyda-flow-modulos/references/capacidades.md) y [tres ejemplos](skills/dyda-flow-modulos/references/ejemplos.md).

**Skill 1.0.0 · Validado con DyDa Flow 0.223.4 · Licencia [MIT](LICENSE) · DyDa Software.**
