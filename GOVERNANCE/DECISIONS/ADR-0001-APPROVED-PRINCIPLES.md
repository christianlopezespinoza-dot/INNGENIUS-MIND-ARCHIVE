# ADR-0001 — Approved Architectural Principles

- **Estado:** APPROVED
- **Fecha:** 2026-11-01
- **Contexto:** definición de los principios rectores de INnGeNiUs MIND ARCHIVE.

## Decisión A — Biblioteca modular

El repositorio será una biblioteca central modular capaz de alojar componentes reutilizables para distintos proyectos y agentes.

Consecuencia: los proyectos consumidores mantienen sus datos, lógica de negocio, configuración y despliegues separados.

## Decisión B — Agent Skills

Se adopta Agent Skills como estándar abierto para capacidades especializadas. Un Skill define una capacidad reutilizable; no reemplaza el perfil, identidad, contrato o gobernanza de un agente.

Consecuencia: Skills deben poder registrarse, versionarse, descubrirse, validarse y ser utilizados por más de un agente cuando sus contratos sean compatibles.

## Decisión C — Semantic Versioning

Se adopta MAJOR.MINOR.PATCH para activos cuya evolución requiera trazabilidad y compatibilidad.

Consecuencia: cambios incompatibles incrementan MAJOR; capacidades compatibles incrementan MINOR; correcciones compatibles incrementan PATCH. Los documentos de trabajo pueden permanecer como DRAFT hasta su aprobación.
