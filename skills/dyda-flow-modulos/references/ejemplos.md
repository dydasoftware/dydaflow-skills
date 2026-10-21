# Cuatro conversaciones de ejemplo · DyDa Flow

Estos recorridos ilustran decisiones, no son plantillas para otros negocios. Los módulos existentes se confirmaron en cada conversación. Los nombres y datos son ficticios.

## 1. Servicio: despacho de traducciones

**IA:** ¿Qué servicio prestan y qué ocurre desde que reciben un encargo hasta entregarlo?

**Persona:** Traducimos documentos. Recibimos un archivo, calculamos páginas y tarifa, asignamos traductor y entregamos. Quiero controlar fechas e importes.

**IA:** ¿Quién usará Flow y qué módulos tienen ya?

**Persona:** Coordinación y traductores. Tenemos Contactos para clientes. Starter, sin módulos propios todavía, con 20 créditos disponibles.

**IA:** Propongo ampliar Contactos con Idioma preferido y crear Encargos para seguir cada traducción. El traductor será un usuario responsable. ¿Los aceptas?

**Persona:** Sí. No necesito un catálogo de idiomas; solo trabajamos español e inglés.

**IA:** Para Contactos: Idioma preferido, una opción, opcional, Español o Inglés. Para Encargos: Folio consecutivo de seis dígitos; propongo Cliente ligado a Contactos, Traductor responsable, Fecha de entrega, Idioma de entrega, Tipo de documento, Páginas y Tarifa por página como obligatorios; Archivo y Notas opcionales; Importe calculado y Estado obligatorio. Idiomas Español/Inglés; tipos General/Legal. Propongo estados Recibido, En traducción y Entregado, iniciando en Recibido y avanzando en ese orden. ¿Confirmas la obligatoriedad propuesta y esos estados, o qué cambiarías?

**Persona:** Quita Tipo de documento. Acepto lo demás; el importe es páginas por tarifa. No bloquees la edición. Quiero que cada traductor vea sus encargos y pueda editarlos, sin borrar. Coordinación ve, crea y edita todos, sin borrar.

**IA:** Resumen: ampliar Contactos con un campo y crear Encargos con once campos, su liga a clientes, responsable, cálculo y tres estados. Dos roles propios: Coordinación de traducciones y Traductor; con los permisos acordados sobre Encargos y lectura de Contactos. Se configurarán después la asignación de usuarios en Usuarios y la vista Kanban en Editar módulo → Diseño del listado → Listado de registros. La primera generación cuesta 2 créditos y cada ajuste 1. ¿Confirmas este alcance?

**Persona:** Confirmo.

**Prompt final:**

```text
Diseña esta estructura en DyDa Flow para coordinar encargos de traducción y controlar responsables, entregas e importes.

EXISTENTES A CONSERVAR
Contactos ya contiene nuestros clientes. Conserva sus campos, nombres y flujos; agrega únicamente el campo indicado.

MÓDULOS
1. Contactos: Idioma preferido (una opción; opcional).
2. Encargos: Folio (consecutivo; generado), Cliente (liga a Contactos; obligatorio), Traductor (usuario responsable; obligatorio), Fecha de entrega (fecha; obligatoria), Idioma de entrega (una opción; obligatorio), Páginas (número entero positivo; obligatorio), Tarifa por página (dinero; obligatoria), Archivo (archivo; opcional), Notas (texto; opcional), Importe (dinero), Estado (una opción; obligatorio).

DETALLES POR MÓDULO
Amplía Contactos; Idioma preferido tiene las opciones Español e Inglés.
Crea Encargos para cada trabajo de traducción. Folio tiene seis dígitos, sin prefijo. Idioma de entrega tiene las opciones Español e Inglés. Páginas debe ser mayor que cero. Tarifa por página usa la moneda de la organización y dos decimales, sin negativos. No agregues Tipo de documento ni un catálogo de idiomas.

LIGAS Y PARTIDAS
Encargos.Cliente elige un registro de Contactos. Encargos.Traductor elige una cuenta de Flow y define al responsable. No hay partidas.

ESTADOS
En Encargos usa Estado con Recibido, En traducción y Entregado. Inicia en Recibido. Permite Recibido a En traducción y En traducción a Entregado. Ningún estado bloquea la edición; los cambios de estado quedan disponibles según los permisos del módulo.

CAMPOS CALCULADOS
- Campos calculados en Encargos: Importe.
Calcula Importe multiplicando Páginas por Tarifa por página del mismo encargo.

PERMISOS BÁSICOS
Crea roles propios Coordinación de traducciones y Traductor. En Encargos, Coordinación de traducciones puede ver todos, crear y editar, sin borrar. Traductor ve solo sus propios encargos según el campo Traductor; puede leer y editar, sin crear ni borrar. Ambos roles pueden leer todos los Contactos, sin crearlos, editarlos ni borrarlos. No modifiques roles del sistema.

ALCANCE
Reutiliza Contactos y crea solo lo acordado. Explica cualquier elemento omitido o simplificado antes de aplicar el plano.
```

**Después de copiar:** configurar Kanban en Diseño del listado y asignar los roles en Usuarios. Revisar que Importe conserve su cálculo y que el acceso propio use Traductor.

## 2. Comercio: tienda con reparto local

**IA:** ¿Qué venden y qué necesitan controlar de su operación diaria?

**Persona:** Artículos para el hogar. Ya capturamos ventas, pero necesitamos registrar cada entrega, la dirección y quién reparte.

**IA:** ¿Qué módulos usan y quién capturará las entregas?

**Persona:** Contactos, Productos, Pedidos y Partidas ya están. El coordinador y repartidores usarán Flow. Agenda, con dos módulos propios libres y cinco créditos.

**IA:** Reutilicemos esos módulos. Propongo agregar Empaque a Productos y crear Entregas, ligado a un Pedido. Así no duplicamos las ventas. ¿Lo aceptas?

**Persona:** Sí. Puede haber varias entregas para un pedido. El empaque puede ser Estándar o Frágil. También quiero avisar al cliente un día antes.

**IA:** El aviso se configura después en Automatización → Flujos → Por tiempo, sujeto al plan; Agenda tiene cero automatizaciones activas de referencia, así que hay que revisar la disponibilidad en Plan y consumo. Para Entregas propongo Folio consecutivo, Pedido, Fecha programada, Dirección, Repartidor responsable y Estado obligatorios; Comprobante y Observaciones opcionales. Estados Pendiente, En ruta, Entregada o Cancelada; inicio Pendiente. ¿Qué cambias?

**Persona:** Nada. Acepto esos campos. De Pendiente pasa a En ruta o Cancelada; de En ruta a Entregada o Cancelada. Sin bloqueos. Dejemos el aviso pendiente.

**IA:** Resumen: un campo nuevo en Productos y un módulo nuevo Entregas con ocho campos y cuatro estados. Cada entrega elige un pedido; varias pueden apuntar al mismo. Conservamos Pedidos, Partidas y sus cálculos y estados actuales. No se acordaron permisos nuevos. El aviso queda fuera del prompt, condicionado al plan. Primera generación 2 créditos; ajustes 1. ¿Confirmas?

**Persona:** Confirmo.

**Prompt final:**

```text
Diseña esta estructura en DyDa Flow para organizar el reparto de una tienda de artículos para el hogar.

EXISTENTES A CONSERVAR
Ya existen Contactos, Productos, Pedidos y Partidas. Conserva sus campos, flujos y cálculos. Reutiliza Pedidos para las ventas y agrega solo lo indicado a Productos.

MÓDULOS
1. Productos: Empaque (una opción; opcional).
2. Entregas: Folio (consecutivo; generado), Pedido (liga a Pedidos; obligatorio), Fecha programada (fecha; obligatoria), Dirección (texto; obligatoria), Repartidor (usuario responsable; obligatorio), Estado (una opción; obligatorio), Comprobante (archivo; opcional), Observaciones (texto; opcional).

DETALLES POR MÓDULO
Amplía Productos con Empaque: Estándar o Frágil.
Crea Entregas para cada salida de reparto. Folio tiene seis dígitos sin prefijo. Dirección se captura en cada entrega y no cambia los datos del cliente. No dupliques los pedidos ni sus partidas.

LIGAS Y PARTIDAS
Cada Entrega elige un Pedido existente mediante Pedido; distintas entregas pueden referirse al mismo pedido. Repartidor elige una cuenta de Flow y define al responsable de la entrega. No agregues partidas nuevas ni cálculos.

ESTADOS
En Entregas usa Estado con Pendiente, En ruta, Entregada y Cancelada. Inicia en Pendiente. Permite Pendiente a En ruta, Pendiente a Cancelada, En ruta a Entregada y En ruta a Cancelada. Ningún estado bloquea la edición; los cambios de estado quedan disponibles según los permisos del módulo.

ALCANCE
Amplía Productos y crea solo Entregas. No cambies los estados de Pedidos. Explica cualquier elemento omitido o simplificado antes de aplicar el plano.
```

**Después de copiar:** configurar Kanban en Editar módulo → Diseño del listado → Listado de registros. Para el aviso, revisar primero el cupo de automatizaciones en Ajustes → Plan y consumo; si está habilitado, usar Automatización → Flujos → Por tiempo con Fecha programada y una hora en la zona de la organización. No se promete un canal nuevo.

## 3. Operación interna: revisiones de calidad

**IA:** ¿Qué proceso interno quieren organizar y quién participa?

**Persona:** Supervisores revisan áreas de la empresa y registran resultados. Quiero fecha, responsable, hallazgo y evidencia, sin tratarlo como venta ni como ticket.

**IA:** ¿Qué estructura ya tienen y necesitan dar seguimiento al hallazgo?

**Persona:** Tenemos las cuentas de supervisores, pero ningún módulo equivalente. Solo una revisión y su cierre. Estamos en Crecimiento con 100 créditos.

**IA:** Propongo Revisiones internas y un catálogo Áreas, usado desde cada revisión. Para Áreas: Nombre obligatorio y Descripción opcional. Para Revisiones: Folio, Área, Supervisor responsable, Fecha de revisión, Resultado y Estado obligatorios; Hallazgo y Evidencia opcionales. Resultado: Conforme o Con hallazgo. Estados Borrador, Revisada y Cerrada; al cerrar, exigir Hallazgo. ¿Qué cambias?

**Persona:** Hallazgo solo si hay problema. Para cerrar prefiero una Conclusión obligatoria en ese momento. Agrega esa conclusión como texto opcional al capturar. No bloquees la edición ni agregues permisos.

**IA:** Resumen: crear Revisiones internas con nueve campos y tres estados, y Áreas con dos campos; Supervisor usa las cuentas existentes. La regla de cierre exige Conclusión, sin condición entre módulos. El catálogo Áreas se llena después y no consume cupo de módulos operativos propios; ambos cuentan en el máximo de módulos nuevos por plano. Primera generación 2 créditos; ajustes 1. ¿Confirmas?

**Persona:** Confirmo.

**Prompt final:**

```text
Diseña esta estructura en DyDa Flow para registrar revisiones internas de calidad por área y su cierre.

EXISTENTES A CONSERVAR
Las personas supervisoras ya tienen cuenta en Flow. No crees un módulo de usuarios ni cambies los módulos instalados. No hay un módulo existente equivalente a estas revisiones.

MÓDULOS
1. Revisiones internas: Folio (consecutivo; generado), Área (liga a Áreas; obligatoria), Supervisor (usuario responsable; obligatorio), Fecha de revisión (fecha; obligatoria), Resultado (una opción; obligatorio), Estado (una opción; obligatorio), Hallazgo (texto; opcional), Evidencia (archivo; opcional), Conclusión (texto; opcional al capturar).
2. Áreas: Nombre (texto; obligatorio), Descripción (texto; opcional).

DETALLES POR MÓDULO
Crea Revisiones internas como módulo operativo y Áreas como catálogo reutilizable. Folio tiene seis dígitos sin prefijo. Resultado permite Conforme o Con hallazgo. Conclusión es opcional durante la captura y se exige al cerrar. Hallazgo permanece opcional.

LIGAS Y PARTIDAS
Revisiones internas.Área elige un registro del catálogo Áreas. Supervisor elige una cuenta de Flow y define al responsable. No hay partidas ni cálculos.

ESTADOS
En Revisiones internas usa Estado con Borrador, Revisada y Cerrada. Inicia en Borrador. Permite Borrador a Revisada y Revisada a Cerrada. Antes de pasar a Cerrada, bloquea el cambio si falta Conclusión y muestra “Captura la conclusión”. Ningún estado bloquea la edición; los cambios de estado quedan disponibles según los permisos del módulo. No agregues reglas basadas en otros módulos ni permisos nuevos.

ALCANCE
Crea únicamente Revisiones internas y Áreas, sin catálogos de estados ni duplicar usuarios. Explica cualquier elemento omitido o simplificado antes de aplicar el plano.
```

**Después de copiar:** cargar las áreas en el catálogo Áreas y configurar la vista deseada en Editar módulo → Diseño del listado → Listado de registros. Revisar que el cierre exija Conclusión, sin volver obligatorio Hallazgo.

## 4. Empaque agrícola: recepciones, estibas y embarques facturables

**Persona:** Tenemos un empaque agrícola. Necesito recibir producto de distintos productores y mezclar varias recepciones en una estiba. Facturo las cajas que salen en cada manifiesto. Quiero que usted me ayude a definirlo; los catálogos los capturaremos después.

**IA:** ¿Qué módulos tiene y qué cupo aparece en Plan y consumo? ¿Factura desde pedidos o directamente desde lo embarcado?

**Persona:** Tenemos Contactos para clientes y Productos; Starter con diez módulos propios libres y veinte créditos. No usamos pedidos. Facturamos directamente cada embarque. Necesito productor, variedad y kilos recibidos; ubicación de estiba; fecha, cliente, transportista, chofer y placas al salir. Cada partida lleva estiba, producto, cajas, precio unitario e importe de cajas por precio. Sugiera los folios; no requiero estados.

**IA:** Propongo Recepciones, Estibas, Mezcla de estibas, Embarques y Partidas de embarque, más Productores y Variedades como catálogos. Mezcla de estibas permite ligar varias recepciones a cada estiba y guardar sus kilos aportados. Crearemos Embarques con ese nombre para Facturación; después puede renombrarlo a Manifiestos. ¿Confirma las ligas y cantidades obligatorias —incluidos fecha y cliente del embarque—, los precios obligatorios y los demás textos opcionales, con folios de seis dígitos?

**Persona:** Confirmo. Fecha de recepción y de estiba también obligatorias. Notas opcionales. En los catálogos, Nombre obligatorio y Teléfono de productor opcional. No agregue más requisitos.

**IA:** Son siete módulos nuevos por plano: cinco operativos y dos catálogos; se reutilizan Contactos y Productos. Importe no se captura. Los catálogos se llenan después en sus módulos; la integración fiscal y una serie activa se preparan en Ajustes → Facturación antes de facturar. No hay otros pendientes. La generación cuesta 2 créditos; cada ajuste 1. ¿Confirma el conjunto?

**Persona:** Confirmo.

**Prompt final:**

```text
Diseña esta estructura en DyDa Flow para un empaque agrícola con mezcla de recepciones y facturación desde lo embarcado, sin pedidos.

EXISTENTES A CONSERVAR
Contactos para clientes y Productos ya existen; conserva sus campos, nombres y flujos.

MÓDULOS
1. Recepciones: Folio (consecutivo), Fecha (fecha; obligatoria), Productor (liga a Productores; obligatorio), Variedad (liga a Variedades; obligatoria), Kilos (número; obligatorio), Notas (texto; opcional).
2. Estibas: Folio (consecutivo), Fecha (fecha; obligatoria), Ubicación, Notas (texto; opcional).
3. Mezcla de estibas: Estiba (liga a Estibas; obligatoria), Recepción (liga a Recepciones; obligatoria), Kilos aportados (número; obligatorio).
4. Embarques: Folio (consecutivo), Fecha (fecha; obligatoria), Cliente (liga a Contactos; obligatorio), Transportista, Chofer, Placas (texto; opcional).
5. Partidas de embarque: Embarque (liga a Embarques; obligatorio), Estiba (liga a Estibas; obligatoria), Producto (liga a Productos; obligatorio), Cajas (número; obligatorio), Precio unitario (dinero; obligatorio), Importe (dinero).
6. Productores: Nombre (texto; obligatorio), Teléfono (texto; opcional).
7. Variedades: Nombre (texto; obligatorio).

DETALLES POR MÓDULO
Crea los cinco primeros como módulos operativos; Productores y Variedades son catálogos. Folios generados de seis dígitos sin prefijo. Kilos, Kilos aportados y Cajas mayores que cero; Cajas entero. Precio unitario en moneda de la organización, dos decimales y sin negativos. Crea el documento con el nombre Embarques.

LIGAS Y PARTIDAS
Cada liga elige un registro del destino indicado. Varias filas de Mezcla de estibas pueden enlazar una estiba con distintas recepciones y sus kilos aportados. Partidas de embarque se liga a Embarques mediante Embarque; cada partida identifica Estiba y Producto. Cliente se toma de Contactos. No agregues pedidos ni sus partidas.

CAMPOS CALCULADOS
- Campos calculados en Partidas de embarque: Importe.
Multiplica Cajas por Precio unitario del mismo renglón.

ALCANCE
Crea solo lo acordado, sin estados nuevos ni duplicar módulos existentes. Explica omisiones o simplificaciones antes de aplicar el plano.
```

**Después de copiar:** Péguelo en el Diseñador IA y revise el plano antes de aplicarlo. Capture después Productores y Variedades en sus catálogos. Prepare la integración fiscal de clientes y productos y una serie activa en Ajustes → Facturación antes de generar el borrador. Puede renombrar Embarques a Manifiestos después de crearlo; revise que los conceptos correspondan a las cajas embarcadas.
