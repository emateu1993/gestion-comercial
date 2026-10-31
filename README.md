# ARTTPA — Sistema de gestión comercial y clientes

Trabajo Práctico Integrador de Organización Empresarial.

## Datos académicos

- **Alumno:** Emmanuel Mateu.
- **Comisión:** 3.
- **Carrera:** Tecnicatura Universitaria en Programación.
- **Institución:** Universidad Tecnológica Nacional.
- **Docente titular:** Prof. Gabriela Martínez.
- **Docente tutor:** Corts Romeo Franco Nicolás.

## Descripción del proyecto

El proyecto propone un software de gestión comercial y clientes para ARTTPA Gluten Free Products S.R.L., empresa dedicada a elaborar y comercializar productos de panificación sin gluten.

El sistema busca centralizar la información de clientes, presupuestos, pedidos y seguimientos comerciales, y compartirla con administración, producción y logística. Su objetivo es evitar la carga duplicada de datos y mejorar la coordinación entre las áreas.

Este repositorio contiene la documentación y el seguimiento del proyecto. No representa, por sí mismo, un sistema implementado.

## Funcionalidades propuestas

- Registrar y consultar clientes.
- Elaborar y gestionar presupuestos.
- Convertir un presupuesto aceptado y vigente en un pedido único.
- Compartir los datos del pedido con las áreas involucradas.
- Registrar contactos comerciales y próximas acciones.
- Consultar el historial de presupuestos, pedidos y seguimientos de cada cliente.

## Proceso modelado en BPMN

El diagrama representa el proceso desde la recepción de una solicitud comercial hasta la confirmación del pedido o el cierre sin venta.

Incluye dos participantes: Cliente y ARTTPA. Dentro de ARTTPA se distinguen cuatro áreas o roles:

- Comercial.
- Sistema de gestión.
- Administración y facturación.
- Producción y logística.

Se contemplan decisiones sobre la validez de los datos, la disponibilidad y la aceptación del presupuesto. También se representan actividades paralelas de administración y producción y logística.

El modelo fue realizado en Bizagi Modeler.

**Acceso al diagrama:** [Pegar enlace al archivo del diagrama]

## Historias de usuario

### HU-01 — Consultar ficha del cliente

Como integrante del área comercial, quiero consultar la ficha completa de un cliente, para conocer sus contactos, presupuestos, pedidos y seguimientos sin buscar en registros separados.

### HU-02 — Convertir presupuesto en pedido

Como vendedor, quiero convertir un presupuesto aceptado y vigente en un pedido, para compartir los datos con administración, producción y logística sin volver a cargarlos.

### HU-03 — Registrar seguimiento comercial

Como responsable de atención al cliente, quiero registrar cada contacto y su próxima acción, para mantener la continuidad de la atención y no perder compromisos comerciales.

Los criterios de aceptación se detallan en las issues correspondientes.

## Gestión del trabajo

Las historias y actividades se organizan en un tablero con tres estados:

- **Por Hacer:** actividades que todavía no comenzaron.
- **En Progreso:** actividades que se están realizando.
- **Listo:** actividades terminadas y verificadas según sus criterios de aceptación.

**Tablero del proyecto:** [Pegar enlace real de GitHub Projects]

Los cambios se preparan en ramas secundarias, se guardan mediante commits descriptivos y se proponen para su integración mediante Pull Requests.

**Pull Request con revisión de pares:** Pendiente de completar.

## Indicadores de control

Se establecen los siguientes estándares para verificar el sistema durante su desarrollo:

- Consultar la ficha de un cliente en menos de 3 segundos, con 1.000 clientes y 5.000 pedidos registrados.
- Soportar 10 usuarios simultáneos con respuestas inferiores a 5 segundos.
- Cargar y verificar al menos 50 clientes hasta la semana 7.
- Finalizar la semana 9 sin errores críticos abiertos.
- Implementar el sistema y capacitar a los usuarios en la semana 10.
- Evitar que un mismo presupuesto genere pedidos duplicados.

Estos valores son metas de aceptación; no se presentan como resultados de pruebas ya ejecutadas.

## Documentación

- **Trabajo Práctico N.º 4:** [Pegar enlace al PDF]
- **Modelo BPMN de Bizagi:** [Pegar enlace al archivo editable]
- **Diagrama exportado:** [Pegar enlace al PDF o imagen]
- **Historias y actividades:** disponibles en la sección Issues.
- **Seguimiento:** disponible en el tablero del proyecto.

