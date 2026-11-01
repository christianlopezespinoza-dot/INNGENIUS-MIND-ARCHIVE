# ADR-0005 — Consolidated Architecture v0.2.0

- **Estado:** PROPOSED — pendiente de aprobación del usuario.
- **Fecha:** 2026-11-01.
- **Propuesta:** adoptar `CORE/ARCHITECTURE/MASTER_ARCHITECTURE_DRAFT_v0.2.0.md` como modelo consolidado.

## Contexto

Las propuestas históricas distribuyen las responsabilidades de formas distintas. La revisión identificó que prompts, rutinas y gobernanza necesitan visibilidad propia, mientras que el archivo intelectual y la biblioteca de capacidades deben coexistir sin confundirse.

## Decisión propuesta

Aprobar los doce dominios descritos en el borrador v0.2.0: CORE, KNOWLEDGE, AGENTS, SKILLS, PROMPTS, ROUTINES, EXECUTION, INTEROPERABILITY, VALIDATION, GOVERNANCE, VERSIONING y PROJECTS.

## Consecuencias

- Catálogo de activos explícito y reutilizable.
- Separación de responsabilidades y proyectos.
- Mayor trazabilidad de instrucciones, capacidades y decisiones.
- Más estructura documental que mantener; requiere responsables y políticas de ciclo de vida.

## Alternativas consideradas

1. Mantener siete capas originales: simple, pero prompts, rutinas y gobernanza quedan implícitos.
2. Adoptar las cinco capas históricas: no hay suficiente evidencia recuperada de sus contratos exactos.
3. Adoptar doce dominios: propuesta más explícita para el alcance ampliado de la biblioteca.

## Criterios de aceptación

La decisión se considera aprobada solo cuando el usuario confirme expresamente la arquitectura v0.2.0 o indique ajustes.
