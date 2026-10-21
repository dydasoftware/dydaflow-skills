# Capacidades del Diseñador IA de DyDa Flow

Referencia del skill 1.0.0, contrastada con DyDa Flow 0.223.4. Describe lo que se puede solicitar; la propuesta generada debe revisarse antes de aplicarla.

## Qué construye

| Necesidad | Qué se puede pedir |
|---|---|
| Módulos nuevos | Módulos de operación y catálogos reutilizables, con nombre, descripción, icono y campos. Un catálogo suele ser una lista de registros con datos propios que otro módulo utiliza. |
| Ampliar lo existente | Agregar campos nuevos y partidas propias. Conserva nombres, campos, reglas y flujos existentes; no sirve para sustituirlos ni borrarlos. |
| Campos | Definir qué se captura, si es obligatorio y las reglas compatibles con su tipo. |
| Ligas | Elegir registros de otro módulo existente o propuesto. Puede enlazar módulos entre sí; una liga de selección elige un registro. Para varios, concretar asociaciones entre módulos distintos o un módulo intermedio con sus ligas. No duplicar una liga de usuario con otra asociación. |
| Personas que usan Flow | Campos de usuario del sistema, incluso varios cuando se acuerde, y un campo que identifique al responsable del registro. Un perfil adicional puede ligarse a un usuario único; no crea cuentas de acceso. |
| Encabezado y partidas | Un documento con renglones que son registros propios, su liga al encabezado y totales. Una tabla sencilla es para listas que no requieren registros independientes. |
| Estados | En módulos nuevos, un campo de una opción con todas las etapas, estado inicial, cambios permitidos, bloqueos de edición y campos exceptuados del bloqueo. No reemplaza el flujo de un módulo existente. |
| Reglas para avanzar | Exigir campos del registro al pasar de estado; advertir o bloquear según conteo o suma de sus partidas. También admite comparar cantidades de partidas con un valor numérico relacionado, con sus ligas reales. Esto no equivale a reglas arbitrarias entre módulos. |
| Cálculos numéricos | Sumar, restar, multiplicar o dividir campos numéricos del mismo módulo; expresiones numéricas con comparaciones, condiciones, operaciones lógicas, mínimo, máximo, redondeo y valor absoluto. También suma, conteo, promedio, mínimo y máximo de registros ligados hacia el módulo principal, con filtros simples compatibles. |
| Permisos básicos por módulo | Roles propios con lectura, creación, edición y borrado, y visibilidad de todos los registros o solo propios. Para «propios» se necesita el campo de usuario responsable. No modifica roles del sistema ni crea o asigna cuentas de usuario. |

El Diseñador puede ajustar o quitar elementos de una propuesta aún sin aplicar. Esto no autoriza borrar, renombrar o reescribir módulos, campos o estados que ya existen en la organización.

## Campos en palabras simples

| Cómo explicarlo | Qué permite y qué concretar |
|---|---|
| Texto | Nombres, descripciones y notas; también hora por separado. Puede usar formatos guiados como correo o teléfono, longitud mínima/máxima, quitar espacios y convertir mayúsculas o minúsculas. No se ofrecen patrones personalizados de programación. |
| Número | Cantidades, enteros o decimales, mínimos, máximos, positivos y múltiplos cuando proceda. |
| Dinero | Importes con moneda y decimales; confirmar si se admiten negativos. |
| Sí/no | Casilla, con aceptación obligatoria cuando se necesite. |
| Fecha | Día de un evento, con límites fijos o relativos a hoy, valor inicial de hoy y comparación anterior/posterior con otra fecha del mismo módulo. No hay un tipo separado para fecha y hora juntas. |
| Una opción | Lista fija con sus opciones completas y, si se acuerda, opción inicial y colores. Es el campo que usa el flujo de estados y la agrupación Kanban. |
| Varias opciones | Lista fija donde se pueden elegir varias; puede limitar cuántas. |
| Liga a otro módulo | Elegir un registro existente del destino. Puede limitar elegibles mediante coincidencia de un campo simple con un valor fijo; no prometer filtros que dependan dinámicamente de otro registro. |
| Usuario del sistema | Elegir una persona con cuenta en Flow; puede identificar al responsable. La elección de personal o roles elegibles no concede permisos por sí misma. |
| Archivo | Referencia a un archivo; permite limitar tipos admitidos y tamaño, hasta 15 MB por archivo. No carga documentos por describirlos en el prompt. |
| Consecutivo | Numeración generada, de 1 a 15 dígitos. Puede tener prefijo fijo o tomado de un texto de un registro ligado, no ambos a la vez. |
| Tabla sencilla | Renglones dentro de un campo, con columnas de texto, número, sí/no, fecha o liga. No tablas anidadas ni cálculos por columna prometidos. |
| Datos de estructura libre | Datos agrupados de forma flexible. Capacidad avanzada; para la entrevista habitual prefiere campos claros o partidas, sin pedir formatos técnicos al usuario. |

Los cálculos se guardan en campos de número o dinero. No admiten dependencias circulares, operaciones con la fecha actual ni diferencias entre fechas. Un límite de captura relativo a hoy o el valor inicial de hoy en un campo de fecha sí están admitidos; no son cálculos de antigüedad o vencimiento.

## Reutilizar lo que trae Flow

Comprueba en la cuenta cuáles están instalados y si les cambiaron el nombre:

| Área | Módulos base que debes buscar |
|---|---|
| CRM | Contactos, Empresas, Negocios y Tickets. |
| Agenda | Citas, Servicios, Recursos y Servicios de la cita. Agenda es el área; el módulo principal es Citas. |
| Ventas | Productos, Cotizaciones, Pedidos y Partidas. |
| Cobro | Facturas y Pagos. |
| Operación | Proveedores, Compras e Inventario. |

Reutiliza los datos que ya existen. Si basta con campos adicionales, amplía el módulo y enumera solo lo nuevo. Crear un módulo con un nombre parecido no debe duplicar otro existente. La presencia de Facturas o Inventario en la cuenta no significa que el Diseñador configure facturación electrónica ni movimientos de inventario.

Si Citas base está instalado, no propongas otra agenda, reservas o turnos equivalentes. Conserva su flujo: Agendada, Confirmada, En curso, Terminada, Cancelada y No asistió. Su estado inicial es Agendada; no deduzcas cambios permitidos entre todas las opciones. El Diseñador no instala plantillas prearmadas: si falta una, la persona elige el módulo prearmado antes, o acuerda crear uno propio. No prometas instalar la plantilla dentro del prompt.

## Qué se configura después, fuera del prompt

| Necesidad | Pantalla y alcance real |
|---|---|
| Tabla, Kanban o Calendario | **Editar módulo → Diseño del listado → Listado de registros**. Para Kanban prepara un campo de una opción; para calendario, las fechas y demás campos necesarios. Definir estados no activa la vista. |
| Acomodo visual de la ficha | **Editar módulo → Diseño del detalle**. El Diseñador puede enlazar partidas, pero no se le encarga el diseño visual completo. |
| Cambiar campos existentes o completar un cálculo simplificado | **Editar módulo → Campos**. Solo operaciones y reglas que Flow admite; no es una vía para crear funciones de cálculo inexistentes. Los campos base pueden tener protecciones. |
| Ajustar un flujo existente o limitar quién cambia un estado | **Editar módulo → Flujo de estados**. Las restricciones por rol en las transiciones se configuran allí; no inventar roles para las transiciones del prompt. Se respetan las protecciones del módulo base. |
| Permisos de aplicación, permisos por campo y acceso más detallado | **Roles y permisos**; para acceso a aplicaciones, **Administrar aplicaciones**. Invitar personas y asignar sus roles corresponde a **Usuarios**. Los permisos básicos por módulo sí pueden incluirse en el diseño acordado. |
| Reportes | **Reportes**, desde el módulo para sus reportes impresos. Su diseño y publicación no los realiza este Diseñador de módulos. |
| Avisos y acciones al crear, actualizar o borrar | **Automatización → Flujos**. Usan las acciones y canales existentes y requieren disponibilidad según plan. |
| Avisos por una fecha de registro | **Automatización → Flujos → Por tiempo**: minutos, horas o días antes o después de una fecha del registro, de creación o de actualización. Para una fecha sin hora se elige la hora en la zona de la organización. La condición se evalúa cuando dispara. No incluye recurrencias sin registro ni canales nuevos. |
| Datos iniciales de catálogos y registros | En el **catálogo o módulo correspondiente**, después de aplicar. Crear la estructura no carga clientes, productos ni registros de ejemplo. Las opciones fijas de un campo sí son parte de su configuración. |
| Resumen operativo y accesos rápidos | **Inicio** ofrece el resumen existente y permite personalizar accesos rápidos; no es un editor de dashboards propios. |
| Tableros propios con indicadores y gráficas | **Tableros → Editar**, con permisos y cupo del plan. Es un editor separado: el Diseñador de módulos no crea ni configura esos tableros. |

## Lo que no se debe prometer

- Vistas de registros guardadas con nombre: no están disponibles en este alcance. No confundirlas con las vistas Tabla, Kanban y Calendario ni con el editor separado de Tableros.
- Horarios recurrentes sin un registro, como «todos los lunes a las nueve»: no están disponibles en este alcance; no enviarlos a Flujos como si fueran compatibles.
- Cálculos con hoy, fecha actual o diferencias entre fechas: no están disponibles como fórmulas. No prometer resolverlos desde Campos.
- Reglas condicionales arbitrarias entre módulos: no están admitidas. Distinguirlas de los acumulados, filtros simples y reglas de partidas expresamente descritos arriba.
- Código, páginas web, consultas de base de datos, enlaces ejecutables o integraciones creadas desde el prompt de módulos. El Diseñador crea estructura; no programa funciones nuevas.
- Borrar o sustituir la estructura ya instalada, ni modificar roles del sistema.

Explica la limitación cuando aparezca; acuerda una captura manual solo si la persona la acepta. Mantén estos pendientes fuera del bloque que se pegará en el Diseñador.

## Límites y créditos

| Plan | Módulos operativos propios | Créditos del Diseñador por periodo |
|---|---:|---:|
| Agenda | 2 | 5 |
| Starter | 10 | 20 |
| Crecimiento | Sin tope de plan | 100 |
| Escala | Sin tope de plan | 300 |
| Empresarial | Sin tope de plan | Sin tope de plan |

Estos son valores de referencia. **Ajustes → Plan y consumo** muestra los límites efectivos y lo ya utilizado; puede haber excepciones o créditos adicionales. «Sin tope de plan» no elimina los límites de cada plano ni garantiza disponibilidad de la IA.

Los módulos base del sistema y los catálogos no consumen el cupo de módulos operativos propios. Los módulos operativos propios fuera de la papelera sí, incluidas partidas propias de ese tipo; ampliar uno existente no suma otro módulo. No conviertas operaciones en catálogos para eludir el cupo.

En cada plano se admiten como máximo **15 módulos nuevos**, incluidos catálogos y partidas; **40 campos nuevos por módulo**, también al ampliar; y **10 estados por flujo**. Estos límites son independientes del plan.

La primera generación cuesta **2 créditos** y cada ajuste de la propuesta cuesta **1**. La entrevista en una IA externa no gasta créditos del Diseñador. Esa IA puede cobrar su propio servicio. Durante la prueba sin tarjeta, los créditos incluidos son la mitad del plan, redondeada hacia arriba; el cupo estructural de módulos se conserva. Confirma siempre el saldo disponible antes de generar.

Si el plano avisa que dejó un cálculo como campo simple, quitó una regla u omitió un campo, dilo expresamente. Revisa que estén todos los módulos, campos, relaciones, estados y cálculos acordados antes de aplicar. Una propuesta válida puede incluir simplificaciones: no garantiza cobertura total.
