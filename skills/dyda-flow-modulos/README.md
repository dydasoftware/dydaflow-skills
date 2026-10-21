# DyDa Flow · Diseña los módulos de tu negocio

**Skill oficial de DyDa Flow · Versión 1.0.1 · Referencia de validación: DyDa Flow 0.223.5.**

Tu asistente te entrevista sobre el negocio, propone módulos y campos, y te deja aceptar, quitar o agregar. Al confirmar el resumen, entrega un prompt para copiar en el **Diseñador IA de DyDa Flow**. Funciona para distintos giros y también para procesos internos.

La entrevista prepara la estructura: no entra a tu cuenta ni aplica cambios. En Flow, una persona administradora revisa el plano y decide si lo aplica. La primera generación cuesta **2 créditos** y cada ajuste **1**; por eso conviene llegar con el prompt acordado. El servicio de IA que uses puede tener sus propios costos.

## Instalar en Claude Desktop o claude.ai

1. Usa el ZIP `dyda-flow-modulos-1.0.1.zip` de la entrega manual o de la release, cuando esté publicada. Contiene una carpeta `dyda-flow-modulos` y, dentro, `SKILL.md` y sus referencias.
2. En **Configuración → Capacidades**, habilita **Ejecución de código y creación de archivos**. En una organización, esta función puede depender de su administrador.
3. Abre **Personalizar → Skills** —puede aparecer como **Customize → Skills**—, pulsa **+ → Crear skill → Subir un skill** y selecciona el ZIP.
4. Activa el skill y comienza una conversación: «Quiero diseñar los módulos de mi negocio para DyDa Flow».

La ruta de carga actual es **Personalizar → Skills**. Algunas guías anteriores dicen **Configuración → Capacidades → Skills**; Capacidades sigue siendo el lugar para habilitar la ejecución. Pasos contrastados el 20 de octubre de 2026 con la [guía oficial de Anthropic](https://support.claude.com/en/articles/12512180-use-skills-in-claude).

Si lo comprimes de nuevo, conserva una sola carpeta `dyda-flow-modulos` dentro del ZIP, con `SKILL.md` en su primer nivel; no dejes los archivos sueltos. Incluye esta guía, las referencias y las instrucciones para otras IA; excluye el material de mantenimiento interno y el propio ZIP. Es el formato de [empaquetado de Anthropic](https://support.claude.com/en/articles/12512198-how-to-create-custom-skills).

## Usar en ChatGPT

Abre [instrucciones-otras-ia.md](instrucciones-otras-ia.md), copia su texto completo y pégalo como primer mensaje de una conversación. Después escribe: «Ayúdame a armar mi sistema en DyDa Flow». Este uso sigue el formato de instrucciones en lenguaje natural de la [documentación oficial de OpenAI](https://learn.chatgpt.com/docs/prompting).

Para reutilizarlo, coloca el texto en las instrucciones de un proyecto o, si tu cuenta conserva el editor de GPTs personalizados, en las instrucciones de tu GPT. Si no aparece ese editor, usa la conversación o un proyecto; las experiencias y permisos dependen de la cuenta. OpenAI está [migrando los GPTs personalizados de Enterprise a plugins](https://learn.chatgpt.com/docs/build-plugins); no necesitas crear un plugin para usar este texto en una conversación.

## Usar en Gemini o en un Proyecto de Claude

En Gemini, abre **Descubrir Gems → Nuevo Gem**, ponle un nombre y pega el texto completo de [instrucciones-otras-ia.md](instrucciones-otras-ia.md) en sus instrucciones. Prueba una conversación y pulsa **Guardar**; la vista previa no lo guarda por sí sola. Consulta la [guía oficial de Google](https://support.google.com/gemini/answer/15235603?hl=es). También puedes pegar el texto al comenzar un chat.

En un Proyecto de Claude, usa ese mismo texto como instrucciones del proyecto y comienza la entrevista allí. La versión condensada incluye las capacidades, de modo que no depende de adjuntar las referencias.

## Llevar el resultado a Flow

1. Cuenta qué hacen, quién participa y qué necesitan controlar. Indica los módulos que ya usan para aprovecharlos.
2. Revisa la propuesta; puedes quitar campos o pedir otros antes de confirmar.
3. Confirma el resumen cuando esté completo. Comprueba cupo y créditos en **Ajustes → Plan y consumo**.
4. Copia el bloque final en el **Diseñador IA**, revisa el plano y sus avisos y decide si lo aplicas.
5. Configura después las vistas, avisos u otros pendientes en las pantallas que te indique el asistente.

El asistente cuenta el bloque final y usa el límite de **20,000 caracteres desde Flow 0.223.5**. Para versiones anteriores o si indicas que Flow corta el texto, usa **4,000**. Primero compacta sin perder acuerdos; si aún no cabe, acuerda una generación esencial y un ajuste posterior que cuesta **1 crédito adicional**.

Si quieres facturar desde lo que entregas, acuerda usar **Pedidos**, **Embarques** o **Cuentas por cobrar** y los campos reconocidos por Facturación. Puedes renombrar el módulo después de crearlo. La estructura permite preparar el borrador; la configuración fiscal y su revisión se hacen después.

Puedes consultar [qué se puede construir](references/capacidades.md) y [cuatro recorridos de ejemplo](references/ejemplos.md), incluido un empaque agrícola. No necesitas compartir contraseñas ni registros reales para diseñar la estructura.
