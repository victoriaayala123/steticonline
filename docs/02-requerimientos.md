# 02. Especificación de requerimientos

## 1. Introducción

El presente documento define los requerimientos funcionales y las reglas de negocio del sistema **SteticOnline**.

El objetivo es establecer qué funcionalidades deberá ofrecer el sistema y bajo qué condiciones deberán ejecutarse, tomando como referencia las necesidades identificadas durante la etapa de relevamiento.

La especificación servirá como base para las siguientes etapas del desarrollo: casos de uso, diseño, arquitectura, modelado de datos, implementación y pruebas.

## 2. Objetivo del sistema

Desarrollar una aplicación web para un centro de estética que permita a los clientes consultar servicios, profesionales y disponibilidad horaria, y gestionar sus reservas de manera sencilla.

El sistema también contará con un panel administrativo desde el cual se podrán gestionar turnos, servicios, profesionales, horarios, señas y comprobantes de pago.

Se busca reducir la gestión manual de turnos mediante WhatsApp, mejorar la organización de la agenda y automatizar el proceso de reservas y confirmaciones.

## 3. Actores del sistema

- **Cliente:** persona que consulta los servicios y solicita turnos. Podrá reservar como invitada o registrarse.
- **Administrador:** responsable de gestionar los servicios, profesionales, horarios, reservas, señas y configuración general del sistema.
- **Profesional:** persona que presta los servicios del centro de estética. Sus servicios y disponibilidad estarán administrados desde el panel administrativo.

 4. Requerimientos funcionales

### RF-01. Consultar servicios

El sistema deberá permitir que los clientes visualicen el catálogo de servicios ofrecidos por el centro de estética.

Cada servicio podrá mostrar información descriptiva, imágenes y precio, cuando corresponda.

### RF-02. Consultar profesionales

El sistema deberá permitir visualizar los profesionales habilitados, sus especialidades y los servicios que realizan.

El cliente podrá filtrar los profesionales según el servicio que desea contratar.

### RF-03. Consultar disponibilidad

El sistema deberá permitir consultar los días y horarios disponibles para reservar un turno, teniendo en cuenta el servicio y el profesional seleccionado.

Al seleccionar una fecha, se deberán mostrar únicamente los horarios habilitados y disponibles.

### RF-04. Solicitar y registrar un turno

El sistema deberá permitir que el cliente seleccione un servicio, un profesional, una fecha y un horario para solicitar una reserva.

Antes de registrar el turno, el sistema deberá validar que el horario continúe disponible.

Una vez registrada la solicitud, el sistema deberá asignarle el estado correspondiente según la política de señas configurada.

### RF-05. Reservar como invitado

El sistema deberá permitir realizar reservas sin necesidad de crear una cuenta.

Para ello, el cliente deberá completar los datos mínimos de contacto solicitados por el sistema.

### RF-06. Registro e inicio de sesión

El sistema deberá permitir que los clientes creen una cuenta e inicien sesión mediante correo electrónico y contraseña.

También se contempla la posibilidad de iniciar sesión mediante una cuenta de Google, utilizando un mecanismo de autenticación seguro.

El sistema no deberá almacenar las contraseñas de las cuentas de Google.

### RF-07. Consultar historial y próximos turnos

El sistema deberá permitir que los clientes registrados consulten sus próximos turnos y el historial de reservas realizadas.

La información deberá estar asociada a la cuenta del cliente autenticado.

### RF-08. Cancelar turnos propios

El sistema deberá permitir que un cliente registrado solicite la cancelación de sus propios turnos desde su cuenta.

Antes de confirmar la acción, el sistema deberá solicitar una confirmación para evitar cancelaciones accidentales.

La cancelación deberá actualizar el estado del turno y reflejarse en el panel administrativo.

La política de anticipación y las condiciones económicas de cancelación deberán definirse con el negocio antes de su implementación definitiva.

### RF-09. Gestionar turnos desde el panel administrativo

El administrador deberá poder consultar la agenda de turnos y visualizar las reservas organizadas por fecha, profesional y servicio.

También deberá poder modificar o cancelar reservas cuando sea necesario.

Toda modificación deberá actualizar la información correspondiente y quedar registrada.

### RF-10. Gestionar servicios, profesionales y horarios

El sistema deberá permitir que el administrador realice las siguientes operaciones:

- Registrar nuevos servicios.
- Modificar la información de los servicios existentes.
- Habilitar o deshabilitar servicios.
- Registrar y modificar profesionales.
- Asociar profesionales con los servicios que realizan.
- Configurar y modificar los horarios de atención.
- Gestionar la disponibilidad de los profesionales.

### RF-11. Gestionar señas y comprobantes de pago

El sistema deberá permitir que el administrador configure si el centro de estética requiere una seña para confirmar las reservas.

Cuando se requiera una seña, el administrador podrá configurar el importe o porcentaje correspondiente y los datos necesarios para realizar el pago.

El cliente deberá poder visualizar las instrucciones de pago y adjuntar el comprobante de transferencia desde el sistema.

El administrador deberá poder consultar los comprobantes recibidos y verificar manualmente si el dinero fue acreditado.

Una vez verificado el pago, el administrador podrá marcar la seña como acreditada y el sistema deberá actualizar el estado de la reserva.

La carga de un comprobante no significará que el pago se encuentre automáticamente verificado.

### RF-12. Gestionar turnos de último momento

El sistema deberá permitir que el administrador vuelva a habilitar un horario que haya quedado disponible luego de una cancelación.

El administrador podrá publicar ese horario como una oportunidad de último momento para que otros clientes puedan reservarlo.

En la primera versión, esta funcionalidad permitirá destacar la disponibilidad, sin aplicar descuentos automáticos.

### RF-13. Enviar notificaciones

El sistema deberá informar al cliente los cambios importantes relacionados con su reserva, como la recepción de una solicitud, la confirmación del turno, la cancelación o la actualización de su estado.

Se contempla la utilización de correo electrónico y otros canales de comunicación. La integración con WhatsApp Business podrá incorporarse según la disponibilidad de los servicios necesarios.

## 5. Reglas de negocio

Las siguientes reglas establecen las condiciones que deberá respetar el sistema durante la gestión de reservas.

### RN-01. Disponibilidad de horarios

Un horario solamente podrá reservarse si se encuentra habilitado y disponible para el servicio y profesional seleccionados.

### RN-02. Prevención de reservas duplicadas

El sistema deberá impedir que dos clientes puedan obtener una reserva confirmada o provisional sobre el mismo horario y profesional.

La validación deberá realizarse también desde el servidor y la base de datos, no solamente desde la interfaz visual.

### RN-03. Confirmación automática sin seña

Cuando el centro de estética no requiera una seña, el sistema podrá confirmar automáticamente la reserva una vez validados los datos y la disponibilidad.

### RN-04. Reserva provisional con seña

Cuando el centro de estética requiera una seña, la reserva deberá quedar en estado provisional mientras el cliente realiza el pago y envía el comprobante.

Durante ese período, el horario permanecerá reservado temporalmente para evitar que otro cliente lo ocupe.

### RN-05. Plazo para realizar el pago

El cliente dispondrá de un plazo máximo de **30 minutos** desde la creación de la reserva provisional para realizar la transferencia y adjuntar el comprobante.

Este plazo deberá informarse claramente antes de finalizar la reserva y también después de registrarla.

### RN-06. Liberación automática por vencimiento

Si el cliente no adjunta el comprobante dentro de los 30 minutos establecidos, el sistema deberá cambiar el estado de la reserva a vencida o liberada y habilitar nuevamente el horario para otros clientes.

El estado de una reserva vencida no deberá confundirse con una cancelación de un turno previamente confirmado.

### RN-07. Comprobante recibido dentro del plazo

Si el cliente adjunta el comprobante dentro del plazo establecido, la reserva deberá permanecer retenida y pasar a un estado de pendiente de verificación.

El horario no deberá liberarse automáticamente mientras el administrador verifica el pago.

### RN-08. Verificación manual de la seña

El administrador deberá comprobar que el dinero se encuentre efectivamente acreditado antes de confirmar el turno.

La imagen o archivo del comprobante enviado por el cliente no será suficiente para considerar acreditado el pago.

### RN-09. Configuración de señas

El administrador podrá habilitar o deshabilitar la exigencia de señas y configurar los datos de pago correspondientes.

Los datos de transferencia, como alias, CBU, entidad bancaria y titular, deberán poder modificarse desde el panel administrativo sin necesidad de modificar el código fuente.

### RN-10. Confirmación después de verificar el pago

Cuando el administrador confirme que la seña fue acreditada, el sistema deberá actualizar la reserva al estado confirmado y comunicarlo al cliente.

### RN-11. Gestión de comprobantes rechazados

Si el comprobante no corresponde a un pago acreditado, el administrador deberá poder rechazarlo y gestionar la liberación de la reserva según las condiciones definidas por el negocio.

El cliente deberá recibir información sobre el resultado de la verificación.

### RN-12. Cancelación de turnos

Cuando un turno confirmado sea cancelado, deberá conservarse el registro de la reserva y actualizarse su estado a cancelado.

La cancelación no deberá liberar automáticamente el horario. El administrador decidirá si mantiene el horario bloqueado o vuelve a habilitarlo.

### RN-13. Publicación de horarios de último momento

Cuando el administrador decida habilitar un horario liberado, podrá publicarlo como disponibilidad de último momento.

Los clientes solamente visualizarán los horarios disponibles, sin acceder a información privada de otras reservas o de las personas que las cancelaron.

### RN-14. Registro de modificaciones

Las acciones importantes realizadas sobre las reservas deberán quedar registradas para facilitar su seguimiento y control administrativo.

## 6. Estados de las reservas

Para organizar correctamente el proceso de turnos, se contemplan inicialmente los siguientes estados:
Estado

**Estados de las reservas:**

- **Provisional:** esperando el pago de la seña.
- **Pendiente de verificación:** comprobante recibido, falta verificar el pago.
- **Confirmado:** turno confirmado.
- **Cancelado:** turno cancelado por el cliente o administrador.
- **Vencido / Liberado:** no se recibió el comprobante dentro de los 30 minutos y el horario quedó disponible.
- **Finalizado:** el servicio fue realizado.

La disponibilidad de un horario se gestionará de manera independiente al estado de la reserva. Esto permitirá mantener un horario bloqueado después de una cancelación o volver a habilitarlo cuando el administrador lo decida.

## 7. Alcance de la primera versión

La primera versión del sistema contempla:

- Sitio web público con información del centro de estética.
- Catálogo de servicios.
- Listado de profesionales y especialidades.
- Consulta de disponibilidad.
- Solicitud y registro de reservas.
- Reservas como invitado.
- Registro e inicio de sesión de clientes.
- Consulta de próximos turnos e historial.
- Solicitud de cancelación de turnos propios.
- Panel administrativo.
- Gestión de servicios, profesionales y horarios.
- Gestión de señas y comprobantes.
- Confirmación de reservas según las reglas establecidas.
- Liberación automática de reservas provisionales vencidas.
- Publicación de horarios de último momento.
- Notificaciones relacionadas con las reservas.

## 8. Funcionalidades previstas para futuras versiones

Para mantener un alcance inicial controlado, se consideran posibles ampliaciones:

- Integración con Mercado Pago u otras plataformas de pago.
- Verificación automática de pagos.
- Integración avanzada con WhatsApp Business.
- Promociones y descuentos automáticos.
- Configuración de políticas de señas diferentes según cada servicio.
- Reportes estadísticos y análisis de ingresos.
- Funcionalidades adicionales de fidelización de clientes.

## 9. Consideraciones finales

Los requerimientos definidos en este documento representan la primera especificación funcional de SteticOnline.

Servirán como referencia para desarrollar los casos de uso, diseñar la arquitectura y construir el modelo de datos.

Las políticas comerciales que todavía requieran confirmación por parte del negocio, como los plazos de cancelación y la devolución de señas, deberán definirse antes de implementar esas funcionalidades.
