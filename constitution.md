# Constitución — Mesa de Ayuda

## Misión y audiencia

**Misión:** Ofrecer un servicio confiable de mesa de ayuda donde los tickets se crean, asignan, responden, escalan y cierran, con SLA por prioridad y visibilidad operativa del trabajo en curso.

**Audiencia:**
- **Producto / solicitantes:** necesitan registrar y seguir tickets.
- **Agentes de soporte (niveles 1, 2 y 3):** asignan, responden, escalan y cierran.
- **Operaciones:** monitorean abiertos por nivel y cumplimiento de SLA.
- **Ingeniería:** mantienen un servicio simple, popular y fácil de operar.

## Stack

- **Lenguaje / API:** Python + FastAPI
- **Persistencia:** PostgreSQL
- **Tests:** pytest
- **Entorno local:** Docker Compose

Sin frontend propio, colas ni caché en el alcance inicial salvo que una historia lo justifique.

## Calidad

- Cada historia entregable incluye tests automatizados con pytest.
- Una historia → un spec → un merge; no se mezcla alcance entre fases.
- El código debe ser claro y fácil de mantener; se prioriza simplicidad sobre abstracciones prematuras.
- Los criterios de aceptación del spec son la fuente de verdad de lo entregado en esa fase.

## Seguridad y datos

- Los tickets contienen datos de negocio (contenido, solicitante, prioridad, estado, nivel); tratarlos como información interna.
- No exponer secretos (credenciales de DB, variables de entorno) en el repositorio.
- Autenticación y autorización finas se definen por historia cuando apliquen; hasta entonces, no asumir un modelo de auth completo.
- Preferir mínimos datos necesarios por ticket; no persistir PII extra sin necesidad de una historia.

## Forma de trabajo

1. El backlog vive en `specs/backlog.md` (fases `MDA-n` en orden).
2. Antes de implementar una fase: escribir `specs/NNN-.../spec.md` alineado a esta constitución.
3. El spec describe contexto, historias, requisitos en EARS (`R1`, `R2`, …), fuera de alcance y preguntas abiertas. Sin decisiones de stack en el spec.
4. Implementar solo lo del spec activo; marcar la casilla en el backlog al cerrar la fase.
5. Referencia de stakeholders e historias: `README.md`.
