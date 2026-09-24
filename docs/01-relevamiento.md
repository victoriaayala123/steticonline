# Relevamiento del proyecto Steticonline

## 1. Descripción del proyecto
Steticonline será un sistema web orientado a la gestión de turnos para una estética de barrio.

El sistema estará compuesto por una landing page pública, desde la cual los clientes podrán conocer los servicios disponibles y solicitar un turno, y un panel privado de administración destinado a la gestión de las reservas.

El proyecto surge a partir de la observación de una situación habitual en pequeños negocios de estética que gestionan sus turnos principalmente mediante WhatsApp.

> Nota: El negocio utilizado como referencia para el análisis será tratado como un caso ficticio y no se incorporarán nombres ni datos personales reales.

## 2. Situación actual
La estética cuenta con diferentes profesionales que brindan distintos servicios.

Entre los servicios identificados para el caso de estudio se encuentran:

- Depilación.
- Manicuría y servicios relacionados con uñas.
- Alisados y tratamientos capilares.
- Pestañas.Cada servicio puede ser realizado por una profesional diferente.

Actualmente, la gestión de los turnos se realiza principalmente mediante WhatsApp.

Los clientes solicitan información sobre disponibilidad y horarios a través de mensajes. La responsable de la estética debe revisar las solicitudes y responderlas manualmente, indicando o confirmando los horarios disponibles.
- 


## 3. Problema detectado
Durante el relevamiento se observó que la gestión manual de los turnos mediante WhatsApp puede generar una carga importante de trabajo para la responsable de la estética.

Cuando se acumulan solicitudes, la confirmación de los turnos puede demorarse.

La situación observada muestra la necesidad de contar con una herramienta que permita centralizar las solicitudes y facilitar la organización de la agenda de las diferentes profesionales.

El problema principal identificado es:

> La gestión de turnos depende de un proceso manual de recepción, revisión y confirmación de mensajes, lo que dificulta la organización de las reservas cuando aumenta la cantidad de solicitudes.

## 4. Necesidades detectadas
A partir del problema identificado, se plantea la necesidad de desarrollar un sistema web que permita:

- Mostrar los servicios disponibles.
- Identificar qué profesional realiza cada servicio.
- Mostrar los horarios disponibles.
- Permitir que los clientes soliciten turnos online.
- Registrar las reservas en una base de datos.
- Centralizar las reservas en un panel administrativo.
- Permitir visualizar los turnos por fecha.
- Permitir identificar el servicio y la profesional correspondiente.
- Permitir gestionar el estado de cada reserva.

El sistema deberá complementar, y no necesariamente reemplazar, los canales de comunicación existentes como WhatsApp.

## 5. Objetivo del sistema
Desarrollar una aplicación web que permita digitalizar y centralizar la gestión de turnos de una estética, facilitando la reserva por parte de los clientes y la administración de las agendas por parte del personal responsable.


## 6. Actores involucrados
Cliente

Persona que desea solicitar un servicio de la estética.

Podrá consultar los servicios, seleccionar una fecha y horario disponible e ingresar sus datos para solicitar un turno.

### Administrador

Persona responsable de gestionar la agenda de la estética.

Podrá visualizar y administrar los turnos, servicios, profesionales y horarios disponibles.

Profesional

Persona que brinda uno o más servicios dentro de la estética.

La profesional estará asociada a los servicios que realiza y a los turnos correspondientes.

## 7. Alcance inicial
Servicios identificados

Para la primera versión del caso de estudio se contemplan los siguientes servicios:

| Servicio  | Profesional |
|---------- |-------------|
| Depilación| Profesional de depilación |
| Uñas      | Profesional de uñas |
| Alisados  | Responsable de alisados |
| Pestañas  | Profesional de pestañas |

La información anterior podrá modificarse durante las siguientes etapas del análisis.

## 8. Información a relevar

Alcance inicial

El sistema inicialmente contemplará:

- Landing page informativa.
- Catálogo de servicios.
- Información de profesionales.
- Consulta de disponibilidad.
- Reserva de turnos.
- Registro de clientes.
- Panel administrativo.
- Gestión de turnos.
- Gestión de servicios.
- Gestión de profesionales.
- Gestión de horarios.
- Estados de los turnos.
Las funcionalidades definitivas se determinarán durante la etapa de análisis y especificación de requerimientos.

 Observaciones del relevamiento

La problemática fue identificada a partir de la observación de una estética de barrio que utiliza canales digitales, principalmente WhatsApp, para gestionar las solicitudes de turnos.

La observación de la necesidad de responder y confirmar manualmente las solicitudes permitió identificar una oportunidad para mejorar la organización interna mediante un sistema de gestión de turnos.

El proyecto se utilizará como caso de estudio para diseñar y desarrollar una solución web utilizando PHP, Laravel, MySQL y una API REST.
