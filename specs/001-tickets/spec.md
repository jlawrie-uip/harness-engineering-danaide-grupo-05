# MDA-1 — Crear y consultar tickets

**Historia:** [MDA-1 · Crear y consultar tickets](../backlog.md)  
**Constitución:** [constitution.md](../../constitution.md)

## Contexto

Primera entrega de Mesa de Ayuda: permitir registrar tickets y consultarlos. Sin asignación, respuestas, cierre, SLA, escalamiento ni reportes (fases posteriores).

## Historias

- Como solicitante o agente, quiero **crear un ticket** con datos mínimos para iniciar el flujo de soporte.
- Como solicitante o agente, quiero **consultar un ticket por id** y **listar tickets** para ver el estado del trabajo registrado.

## Criterios de aceptación (EARS)

- **R1:** When a client submits a valid create-ticket request with title and description, the system shall persist a new ticket and return it including a unique identifier and creation timestamp.
- **R2:** When a create-ticket request omits title or description, or sends them empty, the system shall reject the request and shall not create a ticket.
- **R3:** When a client requests a ticket by an existing identifier, the system shall return that ticket’s stored data.
- **R4:** When a client requests a ticket by an identifier that does not exist, the system shall indicate that the ticket was not found.
- **R5:** When a client requests the ticket list, the system shall return all currently stored tickets (possibly empty).
- **R6:** Where a ticket is created successfully, the system shall set an initial status of `abierto`.

## Fuera de alcance

- Asignar tickets a agentes (MDA-2)
- Responder / comentar en un ticket (MDA-2)
- Cerrar tickets (MDA-3)
- SLA y vencimientos por prioridad (MDA-4, MDA-6)
- Escalamiento de nivel 1/2/3 (MDA-5, MDA-6)
- Reportes operativos (MDA-7)
- Autenticación / autorización de usuarios
- Filtros avanzados, búsqueda full-text, paginación obligatoria
- Decisiones o detalles de stack (ver constitución)

## Preguntas abiertas

- ¿El campo prioridad existe ya en MDA-1 (sin SLA) o se introduce en MDA-4?
- ¿Hace falta un identificador de solicitante (email/usuario) en la creación, o alcanza título + descripción?
- ¿El listado de MDA-1 debe soportar algún filtro mínimo (p. ej. por estado) o solo “todos”?
- ¿Hay categorías o tipos de ticket en esta fase?
