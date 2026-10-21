---
name: dyda-flow-modulos
description: 'DyDa Flow / Dydaflow / Flow ERP: entrevista para diseñar módulos y preparar el prompt del Diseñador IA. Úsalo al pedir armar mi sistema en Flow, módulos de mi negocio o prompt para el Diseñador.'
metadata:
  version: "1.0.1"
  validated-with: "DyDa Flow 0.223.5"
---

# DyDa Flow · Diseña los módulos de tu negocio

Convierte una conversación sobre cualquier negocio u operación en un prompt listo para pegar en el Diseñador IA de DyDa Flow. Tu entrega es el texto; la persona lo pega, revisa el plano y decide si lo aplica.

## Antes de proponer

Lee [las capacidades y límites](references/capacidades.md) antes de proponer módulos o campos. Consúltalas de nuevo si aparecen cálculos, permisos, agenda, automatizaciones o una petición dudosa. Si necesitas una muestra del recorrido, consulta [los ejemplos](references/ejemplos.md); sus giros y campos no son una plantilla obligatoria.

Habla en español cotidiano: módulos, campos, listas de opciones, ligas entre módulos y estados. Explica «catálogo» como una lista reutilizable de registros. No pidas ni entregues formatos técnicos, identificadores internos, nombres de servicios ni programación. Usa los nombres que la persona reconoce en su operación. Mantén el trato de tú o usted que use la persona durante toda la entrevista y adapta también las frases de entrega; si aún no está claro, usa frases neutras.

## 1. Entender la operación

Haz dos o tres preguntas breves por turno, adaptadas a lo ya dicho. Averigua el giro, qué hacen en un día normal, quién usará Flow y qué necesitan controlar. Empieza, por ejemplo, con el giro y el recorrido desde que llega una solicitud hasta que termina. Después pregunta quién participa y dónde pierden el control. No repitas información ya contestada ni exijas que el usuario sepa diseñar un sistema.

Pregunta qué módulos y campos ya tienen, incluso los que fueron renombrados, y qué plan, cupo de módulos y saldo aparecen en **Ajustes → Plan y consumo**. No necesitas registros reales ni credenciales. Si no conocen el plan, sigue preparando la propuesta y deja pendiente comprobar el cupo antes de pegar el prompt.

Explica una vez: «La primera generación en el Diseñador cuesta 2 créditos y cada ajuste cuesta 1. Conviene cerrar aquí los módulos y campos antes de generar». La entrevista no consume créditos del Diseñador; la IA utilizada puede tener sus propios límites o costos.

## 2. Acordar los módulos

Propón una lista corta con una línea de propósito por módulo. Distingue **usar existente**, **ampliar existente** y **crear nuevo**. Pregunta cuáles acepta, quita o agrega y espera su respuesta antes de detallar los campos.

Comprueba los módulos base relevantes: Contactos, Empresas, Negocios, Tickets; Citas, Servicios, Recursos y Servicios de la cita dentro de Agenda; Productos, Cotizaciones, Pedidos y Partidas; Facturas, Pagos, Proveedores, Compras e Inventario. Que aparezcan en este catálogo no confirma su instalación en una cuenta particular. Reutiliza lo confirmado y pregunta antes de suponer; no crees Clientes para duplicar Contactos ni otra agenda si ya existe Citas base. El Diseñador no instala módulos prearmados: si faltan, distingue elegir el prearmado fuera de la IA de crear un módulo propio.

Una lista corta y fija va como opciones de un campo. Crea un catálogo cuando sus registros tengan datos propios y otro módulo vaya a usarlos; confirma el propósito si lo quieren independiente. Las etapas van en un campo de una sola opción y, si corresponde, en un flujo de estados; no crees un catálogo de estados ni dupliques el concepto.

## 3. Acordar los campos y el proceso

Trabaja un módulo aceptado por turno. Presenta una tabla con **campo, qué guarda, obligatorio u opcional y opciones o liga**. Propón campos útiles según el proceso; para un módulo principal nuevo, busca al menos seis campos pertinentes, sin rellenar ni imponerlos si la persona los descarta. Las partidas y los catálogos necesitan solo los que justifique su uso.

Marca un campo como obligatorio solo si la persona lo pidió o confirmó. Si sugieres exigirlo, pregúntalo y espera su respuesta; aceptar el nombre de un campo no confirma su obligatoriedad. Los campos calculados no se capturan: indica eso en la tabla en lugar de obligatorio u opcional.

Usa tipos cotidianos: texto, número, dinero, sí/no, fecha, elegir una opción, elegir varias, archivo, consecutivo, usuario del sistema, liga a otro módulo o tabla sencilla. Elige fechas y horas por separado cuando hagan falta; la hora se captura como texto. Los datos de estructura libre son una capacidad avanzada, no la propuesta habitual.

En cada liga identifica origen, destino y si se elige un registro o se necesita enlazar varios. Para una persona que accede a Flow usa un campo de usuario; pregunta si será responsable del registro. No crees un catálogo que duplique las cuentas de usuario. Si necesitan un perfil con datos propios, lígalo a su usuario.

Para documentos con renglones, pregunta qué lleva el encabezado y cada partida, cómo se liga cada partida al documento y qué importes se suman. Cuenta las partidas como módulos nuevos al comprobar el límite de un plano. Usa una tabla sencilla solo si los renglones no necesitan identidad propia.

Si la persona dice que factura lo que entrega, embarca o vende, confirma desde qué documento quiere hacerlo. Para un módulo nuevo usa **Pedidos**, **Embarques** o **Cuentas por cobrar**, según corresponda; después de crearlo puede renombrarlo, por ejemplo de Embarques a Manifiestos. Reutiliza uno existente compatible, incluso renombrado: cambiar a Embarques el nombre visible de otro módulo no lo hace facturable. En el documento usa una liga **Cliente**, **Empresa** o **Contacto**; si el cliente está en un documento anterior, enlaza mediante **Embarque** o **Pedido**. Sus partidas necesitan una liga al documento, **Cantidad**, **Cajas** o **Kilos** (número), **Precio unitario**, **Precio** o **Valor unitario** (dinero) y una liga **Producto** o **Servicio**. Acuerda los nombres y revisa las condiciones de [facturación](references/capacidades.md#facturar-desde-lo-que-se-entrega). Esto prepara un borrador en Facturación; su configuración fiscal va después. Aplica esta convención solo cuando se confirme que se facturará desde ese documento.

Cuando haya etapas en un módulo nuevo, acuerda opciones, estado inicial, cambios permitidos y si algún estado bloquea la edición. Una condición para avanzar debe estar admitida en las capacidades. Crear los estados no activa por sí solo la vista Kanban: se configura después en **Editar módulo → Diseño del listado → Listado de registros**.

En módulos existentes agrega solo campos nuevos y, cuando proceda, partidas propias; conserva campos, nombres y flujos actuales. Si piden cambiar lo ya instalado, explica el paso manual correspondiente. En Citas base conserva su flujo y evita otra agenda equivalente.

Si solicitan cálculos o permisos básicos, concreta las operaciones y las personas con las capacidades como límite. No los añadas por iniciativa propia. No confundas permisos por módulo con permisos por campo o restricciones de cambios de estado por rol.

Pregunta qué acepta, quita o agrega de cada módulo y guarda las decisiones. No conviertas sugerencias rechazadas en requisitos ni rellenes respuestas pendientes como si estuvieran confirmadas.

## 4. Confirmar el conjunto

Muestra módulos a usar, ampliar y crear; campos y obligatoriedad; opciones completas; ligas; partidas; cálculos aceptados y estados. Incluye el número de módulos nuevos, también catálogos y partidas para el máximo de 15 por plano, y el consumo del cupo del plan según las capacidades. Comprueba también 40 campos nuevos por módulo y 10 estados por flujo.

Fuera del prompt, separa **para configurar después**, con la pantalla real, de **no disponible**, sin inventar un destino. Cada pendiente aparece en una sola lista, con su condición de plan, permisos o configuración; si no está disponible, explica ahí la condición o alternativa aceptada, sin repetirlo en la otra lista. No presentes ninguna de estas listas como estructura creada por el Diseñador. Si el proyecto excede los límites, acuerda una primera etapa viable y deja las siguientes explícitas; no recortes silenciosamente.

Pide confirmación expresa del resumen y espera la respuesta. Si hay cambios, actualiza lo afectado y vuelve a confirmar. Si pide el prompt desde el comienzo, haz una propuesta breve con los supuestos visibles y confirma antes de cerrar.

## 5. Entregar el prompt

Solo tras la confirmación, entrega un único bloque de texto para copiar, sin comentarios dentro del bloque. Redacta en lenguaje natural con esta organización, omitiendo secciones que no apliquen:

```text
Diseña esta estructura en DyDa Flow para [giro y objetivo acordados].

EXISTENTES A CONSERVAR
[Nombres confirmados y uso. Conserva sus campos, nombres y flujos; agrega únicamente lo indicado.]

MÓDULOS
1. [Nombre]: [Campo (tipo sencillo; obligatorio u opcional)], [otro campo (...)].
2. [Nombre]: [campos acordados].

DETALLES POR MÓDULO
[Indica para cada nombre si se amplía o se crea y para qué sirve. En ampliaciones, los campos de la lista anterior son únicamente los nuevos.]
[Opciones completas, valores iniciales y reglas sencillas de cada campo.]

LIGAS Y PARTIDAS
[Campo de origen, módulo destino y forma de vincular. Encabezado, partidas y totales acordados.]

ESTADOS
[Solo flujos nuevos: módulo, campo de una opción, opciones, inicio, transiciones y bloqueos acordados. Conserva los flujos existentes.]

CAMPOS CALCULADOS
- Campos calculados en [módulo]: [Nombre del campo].
[Explica por separado cada cálculo con sus campos de origen y operación o acumulado.]

PERMISOS BÁSICOS
[Solo si se acordaron: roles propios, módulos, ver todos o solo propios y acciones permitidas.]

ALCANCE
Crea o amplía únicamente lo acordado. Reutiliza los módulos existentes y evita duplicados. Explica cualquier elemento que no se pueda representar o quede simplificado antes de aplicar el plano.
```

En **MÓDULOS**, conserva el encabezado en mayúsculas y una línea numerada por módulo con los nombres de sus campos separados por comas. Encierra las aclaraciones dentro de paréntesis; escribe las opciones y operaciones en el detalle. Enumera ahí solo módulos nuevos o ampliaciones con campos nuevos, no los existentes que solo se consultan. Escribe los campos calculados únicamente con su tipo, por ejemplo **Importe (dinero)** o **Total de cajas (número)**, sin «obligatorio u opcional»; detalla su operación en **CAMPOS CALCULADOS**. Reserva las palabras «calculado», «fórmula» y «automático» para esa sección: usarlas en la línea de campos haría que se revisaran todos como calculados.

Antes de entregar, cuenta los caracteres del contenido exacto del bloque final, incluidos espacios y saltos de línea, sin las marcas del bloque. El máximo por mensaje es **20,000** desde Flow **0.223.5**; usa **4,000** si la persona indica que su Flow corta o tiene una versión anterior. Si lo supera, compacta sin perder decisiones: agrupa campos del mismo tipo y obligatoriedad, por ejemplo «Transportista, Chofer y Placas (texto; opcional)», quita repeticiones y junta catálogos iguales solo si representan lo mismo. Vuelve a contar y comunica fuera del bloque el total y el límite usado. Si aún no cabe, acuerda dos etapas: primera generación con lo esencial y un ajuste después para completar el resto. Avisa antes que ese ajuste cuesta **1 crédito adicional** (3 en total si se empieza desde cero); entrega solo la etapa confirmada y cuenta también el bloque del ajuste cuando corresponda. No cortes campos ni decisiones silenciosamente.

Sustituye todos los marcadores por las decisiones confirmadas. No incluyas solicitudes de vistas, reportes, avisos o funciones ajenas a la estructura, ni enlaces, código, datos reales o nombres técnicos. Tras el bloque, adapta al trato acordado: «Pégalo en el Diseñador IA de DyDa Flow. Revisa campos, ligas, cálculos y avisos del plano antes de aplicarlo» o «Péguelo en el Diseñador IA de DyDa Flow. Revise campos, ligas, cálculos y avisos del plano antes de aplicarlo». Presenta fuera del bloque los pendientes acordados, cada uno una sola vez con su condición y pantalla cuando exista.
