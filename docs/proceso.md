# Proceso comercial de ARTTPA

## Objetivo y alcance

El proceso describe cómo ARTTPA Gluten Free Products S.R.L. recibe una solicitud comercial, elabora un presupuesto y lo convierte en un pedido confirmado.

Comienza con la recepción de la solicitud del cliente y termina con uno de tres resultados: pedido confirmado, cierre sin pedido o cierre sin venta. No incluye el despacho ni la entrega física de los productos.

## Participantes y responsabilidades

El diagrama BPMN distingue dos pools:

- **Cliente:** participante externo que solicita un presupuesto, recibe la propuesta y comunica su respuesta.
- **ARTTPA:** organización que gestiona la solicitud y confirma el pedido.

Dentro del pool de ARTTPA se utilizan cuatro lanes:

- **Comercial:** registra la solicitud, elabora y envía el presupuesto, recibe la respuesta y notifica la confirmación.
- **Sistema de gestión:** valida la información disponible, evalúa las condiciones registradas y genera un pedido único.
- **Administración y facturación:** registra los cierres sin pedido o sin venta y prepara los datos de facturación.
- **Producción y logística:** registra las cantidades y la fecha prevista del pedido.

## Inicio del proceso

El proceso comienza cuando el cliente envía una solicitud de presupuesto. Se utiliza un **evento de inicio de mensaje**, representado por un círculo de borde fino con un sobre vacío.

Comercial registra la solicitud. A continuación, se comprueban los datos del cliente, los productos solicitados, las cantidades y la disponibilidad.

La disponibilidad solo puede validarse automáticamente si el sistema cuenta con información suficiente y actualizada. Cuando requiere confirmación de una persona, debe intervenir el área responsable.

## Primera decisión: datos y disponibilidad

La compuerta exclusiva **“¿Datos válidos y disponibles?”** permite continuar por un solo camino:

- **Sí:** Comercial elabora y envía el presupuesto al cliente.
- **No:** Administración informa la incidencia, cierra la solicitud y alcanza el evento de fin **“Sin pedido”**.

Si después del cierre se acuerda otra propuesta, se inicia una nueva solicitud.

## Segunda decisión: aceptación y vigencia

Después de enviar el presupuesto, Comercial recibe la respuesta del cliente.

La compuerta exclusiva **“¿Aceptado y vigente?”** verifica que el cliente haya aceptado la propuesta y que esta continúe dentro de su período de validez:

- **Sí:** el sistema genera un pedido único vinculado al presupuesto.
- **No:** Administración registra el motivo del cierre y el proceso termina en **“Sin venta”**.

Un presupuesto no debe generar más de un pedido. Si se intenta convertir nuevamente uno que ya tiene un pedido asociado, el sistema debe mostrar el existente.

La falta de respuesta del cliente se gestiona mediante el seguimiento comercial y la próxima acción registrada. El diagrama no incluye un evento temporizador para esta situación.

## Actividades paralelas

Una vez generado el pedido, una compuerta paralela activa dos actividades:

1. **Administración y facturación:** prepara los datos necesarios para facturar.
2. **Producción y logística:** registra las cantidades y la fecha prevista.

Estas actividades pueden realizarse al mismo tiempo y utilizan la información del mismo pedido, evitando volver a cargar los datos comerciales.

Una segunda compuerta paralela sincroniza las ramas: el proceso solo continúa cuando ambas actividades finalizaron.

## Confirmación y finales

Después de completar las dos actividades, Comercial notifica la confirmación al cliente y el proceso termina en **“Pedido confirmado”**.

El diagrama tiene tres resultados posibles:

| Evento de fin | Significado |
|---|---|
| Sin pedido | La solicitud no pudo continuar por problemas en los datos o en la disponibilidad. |
| Sin venta | El presupuesto fue rechazado o la aceptación quedó fuera de vigencia. |
| Pedido confirmado | El pedido fue generado y ambas áreas completaron las actividades previas a su confirmación. |

Los tres son **eventos de fin simples, de tipo Ninguno (None)**. Se representan mediante un círculo de borde grueso sin símbolo interior.

No se utilizan eventos de fin de terminación, porque no se necesita interrumpir de inmediato todas las ramas activas del proceso.

## Conexiones utilizadas

- **Flujos de secuencia:** líneas continuas con flecha que indican el orden de las actividades dentro de ARTTPA. Pueden cruzar lanes del mismo pool.
- **Flujos de mensaje:** líneas discontinuas con círculo inicial y flecha abierta que representan comunicaciones entre Cliente y ARTTPA.
- **Compuertas exclusivas (X):** seleccionan una sola alternativa según una condición.
- **Compuertas paralelas (+):** activan actividades simultáneas y esperan su finalización antes de continuar.

Los mensajes intercambiados son la solicitud del cliente, el presupuesto, la respuesta y la confirmación del pedido.

## Relación con el sistema de información

El proceso utiliza las entidades Cliente, Producto, Presupuesto y Pedido definidas en el proyecto. La entidad Seguimiento permite registrar los contactos y las próximas acciones comerciales.

El pedido conserva la referencia al presupuesto de origen. Los detalles de productos, cantidades y precios deben mantenerse relacionados para compartir información coherente entre las áreas.

El modelo representa el funcionamiento propuesto del proceso; no constituye evidencia de que el software esté implementado o haya superado las pruebas.
