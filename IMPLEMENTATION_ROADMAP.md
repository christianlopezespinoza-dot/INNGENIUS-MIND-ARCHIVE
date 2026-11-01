# INnGeNiUs MIND ARCHIVE — Implementation Roadmap

**Estado:** propuesta de ejecución basada en la auditoría 001.

## Fase 0 — Fundamento documental
- Inventariar historia y estado real.
- Aprobar arquitectura consolidada.
- Ratificar estructura y gobernanza.
- Preservar decisiones y documentos históricos.

**Salida:** arquitectura aprobada y registro de decisiones completo.

## Fase 1 — Contratos y metadatos
- Definir modelos comunes.
- Crear JSON Schemas para Agent, Skill, Prompt, Routine, Context y Decision.
- Definir catálogos y reglas de identificadores.
- Validar esquemas y ejemplos.

**Salida:** contratos estructurales versionados y pruebas automáticas.

## Fase 2 — Bibliotecas mínimas
- Migrar un Skill piloto.
- Migrar un Prompt piloto.
- Crear una Routine piloto.
- Registrar un agente piloto sin inventar los seis perfiles históricos.
- Crear un contexto de proyecto de ejemplo con datos no sensibles.

**Salida:** componentes reutilizables, documentados y validados.

## Fase 3 — Registro y recuperación
- Definir catálogo de componentes.
- Establecer búsqueda por ID, tipo, tags, estado y dependencia.
- Definir cómo se recupera contexto y procedencia.
- Evitar duplicación y componentes huérfanos.

**Salida:** catálogo verificable y método de recuperación.

## Fase 4 — Validación y gobernanza
- Añadir validación automática de metadatos y esquemas.
- Añadir pruebas de Skills, prompts y workflows.
- Formalizar ADRs, revisiones y aprobaciones.
- Establecer changelog y compatibilidad.

**Salida:** proceso de cambio y release reproducible.

## Fase 5 — Integración de proyectos
- Registrar proyectos consumidores.
- Definir contratos de consumo y versiones compatibles.
- Probar reutilización en INnGeNiUs Electoral IA.
- Mantener sus datos y reglas de negocio separados.

**Salida:** primer proyecto consumidor integrado sin acoplamiento indebido.

## Fase 6 — Runtime y automatización (solo si se justifica)
- Evaluar orquestación de agentes.
- Evaluar almacenamiento estructurado o base de datos.
- Evaluar adaptadores MCP y conectores.
- Evaluar automatizaciones con mínimo privilegio.

**Salida:** decisión basada en requisitos, costes, riesgos y evidencia.

## Puertas de control

No avanzar de fase si:
- los contratos previos no están aprobados;
- las pruebas requeridas no pasan;
- no existe responsable;
- la seguridad y procedencia no están resueltas;
- el cambio mezcla el núcleo con datos de un proyecto consumidor.

No iniciar el proyecto Al-Juarismi hasta validar el núcleo y documentar evidencia suficiente.
