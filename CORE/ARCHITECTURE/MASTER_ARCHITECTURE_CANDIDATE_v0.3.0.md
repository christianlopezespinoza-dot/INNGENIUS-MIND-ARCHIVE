# INnGeNiUs MIND ARCHIVE — Master Architecture Candidate v0.3.0

**Estado:** CANDIDATE — preparado para revisión del propietario; no aprobado como baseline definitivo  
**Base:** Master Architecture Draft v0.2.0 + decisiones explícitas del propietario  
**Modelo:** siete capas lógicas + doce dominios organizativos  
**Rama:** architecture/core-foundation-v0.1.0  
**Alcance:** arquitectura documental y organizativa de la biblioteca central multi-proyecto

---

## 1. Propósito y resultado de esta revisión

Esta versión formaliza tres decisiones arquitectónicas:

1. **HYBRID:** conservar siete capas como modelo lógico y organizar doce dominios como unidades de responsabilidad.
2. **INTEGRATED:** mantener SKILLS, PROMPTS y ROUTINES como módulos diferenciados dentro de la capa lógica SKILLS ENGINE.
3. **CROSS:** definir GOVERNANCE y PROJECTS como dominios transversales que se relacionan con todas las capas, sin convertirse en capas adicionales.

La decisión fue comunicada explícitamente por el propietario el 2026-11-01. Esta versión documenta esa selección y la convierte en una propuesta coherente para revisión. La aprobación de las tres decisiones no equivale a aprobar automáticamente este documento completo como baseline final.

## 2. Naturaleza y límites del sistema

INnGeNiUs MIND ARCHIVE es una biblioteca central de conocimiento, capacidades, contratos, instrucciones, rutinas, herramientas y estándares reutilizables.

No es, por el solo hecho de organizar estos activos:

- un runtime de agentes;
- un orquestador multiagente operativo;
- una base de datos vectorial;
- una aplicación web o móvil;
- un repositorio que absorbe el código, los datos o los secretos de todos los productos.

La arquitectura define responsabilidades, relaciones, reglas de gobierno y evolución. Las capacidades ejecutables se implementarán y validarán por etapas.

## 3. Decisiones arquitectónicas formalizadas

### ADR-0006 — Modelo híbrido de arquitectura

**Decisión:** adoptar siete capas lógicas y doce dominios organizativos.

**Motivo:** separar el modelo conceptual de la organización operativa. Las capas ofrecen una vista estable del sistema; los dominios permiten asignar responsabilidades específicas sin convertir cada módulo en una nueva capa.

**Consecuencias:**
- Las capas no son equivalentes a carpetas ni a equipos.
- Los dominios no se interpretan como doce motores de software.
- Un dominio puede tener artefactos en más de una ubicación técnica cuando exista una razón documentada; debe evitarse la duplicación de autoridad.
- La relación capa-dominio debe mantenerse en el registro arquitectónico.

### ADR-0007 — Módulos de capacidades integrados

**Decisión:** SKILLS, PROMPTS y ROUTINES son módulos separados dentro de la capa lógica SKILLS ENGINE.

**Motivo:** son activos distintos con contratos y ciclos de vida propios, pero se combinan para proporcionar capacidades reutilizables.

**Consecuencias:**
- SKILLS define capacidades especializadas reutilizables.
- PROMPTS define instrucciones y misiones.
- ROUTINES define secuencias de trabajo reproducibles.
- No se crean tres motores independientes por el simple hecho de separar los módulos.
- Cada módulo conserva metadatos, pruebas, dependencias y versionado propios.

### ADR-0008 — GOVERNANCE y PROJECTS transversales

**Decisión:** GOVERNANCE y PROJECTS son dominios transversales.

**Motivo:** las reglas de gobierno y la relación con proyectos consumidores afectan a todo el sistema; no constituyen etapas de procesamiento ni capas de ejecución.

**Consecuencias:**
- GOVERNANCE registra decisiones, políticas, aprobaciones y revisiones que pueden afectar a cualquier capa.
- PROJECTS registra consumidores, manifiestos, dependencias, versiones y mapas de integración.
- Ningún proyecto consumidor obtiene autoridad implícita para modificar el núcleo.
- Los datos privados, secretos y reglas de negocio permanecen en los entornos propios de cada proyecto.

## 4. Nivel lógico: siete capas

| Orden | Capa lógica | Responsabilidad principal |
|---|---|---|
| 1 | CORE | Identidad, principios, arquitectura, contratos y estándares comunes |
| 2 | KNOWLEDGE | Fuentes, investigación, conceptos, procedencia y contextos |
| 3 | AGENTS | Identidad, perfiles, responsabilidades, límites y contratos de agentes |
| 4 | SKILLS ENGINE | Composición y administración de Skills, Prompts y Routines |
| 5 | EXECUTION | Scripts, herramientas locales, automatizaciones y utilidades |
| 6 | INTEROPERABILITY | Adaptadores, conectores, protocolos e integración externa |
| 7 | VALIDATION & VERSIONING | Calidad, evidencia, historial, compatibilidad y evolución |

Las siete capas son una vista de arquitectura lógica. No implican una secuencia rígida de ejecución ni obligan a que todas las solicitudes atraviesen cada capa.

## 5. Nivel organizativo: doce dominios

| Dominio | Capa lógica primaria | Responsabilidad |
|---|---|---|
| CORE | CORE | Arquitectura, principios, estándares, políticas estructurales y esquemas |
| KNOWLEDGE | KNOWLEDGE | Fuentes, investigación, conceptos, glosarios, afirmaciones y contexto |
| AGENTS | AGENTS | Perfiles, contratos, registro y estándares de agentes |
| SKILLS | SKILLS ENGINE | Capacidades especializadas reutilizables |
| PROMPTS | SKILLS ENGINE | Instrucciones, plantillas y misiones versionadas |
| ROUTINES | SKILLS ENGINE | Procedimientos, secuencias y workflows reproducibles |
| EXECUTION | EXECUTION | Scripts, herramientas y automatizaciones |
| INTEROPERABILITY | INTEROPERABILITY | Adaptadores, conectores y protocolos |
| VALIDATION | VALIDATION & VERSIONING | Planes, casos de prueba, resultados y evidencias |
| VERSIONING | VALIDATION & VERSIONING | Versiones, changelog, releases y compatibilidad |
| GOVERNANCE | Transversal | Decisiones, políticas, aprobaciones y revisiones |
| PROJECTS | Transversal | Registro de consumidores, manifiestos y dependencias |

La columna “capa lógica primaria” identifica la ubicación conceptual predominante, no una restricción que impida referencias controladas a otras capas.

## 6. Relación entre capas y dominios

La correspondencia primaria es:

- CORE → CORE.
- KNOWLEDGE → KNOWLEDGE.
- AGENTS → AGENTS.
- SKILLS ENGINE → SKILLS + PROMPTS + ROUTINES.
- EXECUTION → EXECUTION.
- INTEROPERABILITY → INTEROPERABILITY.
- VALIDATION & VERSIONING → VALIDATION + VERSIONING.
- GOVERNANCE y PROJECTS → transversales a las siete capas.

Representación conceptual:

~~~text
                 INnGeNiUs MIND ARCHIVE
              Arquitectura lógica de 7 capas

  ┌──────────────────────────────────────────────┐
  │ 1. CORE                                      │
  │ 2. KNOWLEDGE                                 │
  │ 3. AGENTS                                    │
  │ 4. SKILLS ENGINE                             │
  │      ├── SKILLS                              │
  │      ├── PROMPTS                             │
  │      └── ROUTINES                            │
  │ 5. EXECUTION                                 │
  │ 6. INTEROPERABILITY                          │
  │ 7. VALIDATION & VERSIONING                   │
  │      ├── VALIDATION                          │
  │      └── VERSIONING                           │
  └──────────────────────────────────────────────┘

       GOVERNANCE ─── transversal a las capas
       PROJECTS   ─── transversal a las capas

       Proyectos consumidores:
       repositorios y entornos independientes
~~~

## 7. Reglas de separación y autoridad

### 7.1 Capas frente a dominios

- Una capa responde a una pregunta arquitectónica amplia.
- Un dominio responde por una responsabilidad administrable.
- Un módulo es una unidad concreta de activos y contratos dentro de un dominio.
- Una carpeta es una decisión de organización del repositorio, no una capa ni un dominio por sí misma.

### 7.2 SKILLS, PROMPTS y ROUTINES

- Un Skill declara una capacidad y sus instrucciones, recursos, entradas, salidas y límites.
- Un Prompt define una instrucción para una tarea o contexto; no sustituye un Skill ni un contrato de agente.
- Una Routine define el proceso, sus pasos, decisiones, controles y condiciones de finalización.
- Los componentes pueden referenciarse mutuamente mediante identificadores y versiones; no deben copiarse íntegramente sin necesidad.

### 7.3 GOVERNANCE

- Las decisiones arquitectónicas se registran con identificador, estado, contexto, decisión, consecuencias y evidencia.
- Las aprobaciones no se infieren de recomendaciones.
- Los estados APPROVED, IMPLEMENTED y VALIDATED son distintos y requieren evidencias distintas.
- Los cambios a decisiones aprobadas se registran como nuevas revisiones o decisiones relacionadas; no se reescribe la historia.

### 7.4 PROJECTS

- Cada proyecto consumidor tiene identidad, responsable, manifiesto y referencias a componentes centrales.
- El registro central no debe duplicar el repositorio de código, los datos privados ni las reglas de negocio del consumidor.
- Las dependencias deben identificar versiones o rangos compatibles.
- Un consumidor no puede imponer cambios al núcleo sin el proceso de gobierno correspondiente.

## 8. Estructura documental de referencia

La estructura modular de doce dominios del borrador v0.2.0 se conserva como base organizativa. La vista de siete capas se documenta como mapa lógico, no como una nueva jerarquía de directorios.

~~~text
INNGENIUS-MIND-ARCHIVE/
├── CORE/
│   ├── ARCHITECTURE/
│   ├── BLUEPRINT/
│   ├── POLICIES/
│   ├── STANDARDS/
│   ├── SCHEMAS/
│   └── REGISTRY/
├── KNOWLEDGE/
├── AGENTS/
├── SKILLS/
├── PROMPTS/
├── ROUTINES/
├── EXECUTION/
├── INTEROPERABILITY/
├── VALIDATION/
├── GOVERNANCE/
│   ├── DECISIONS/
│   ├── POLICIES/
│   └── REVIEWS/
├── VERSIONING/
└── PROJECTS/
    ├── REGISTRY/
    └── TEMPLATES/
~~~

Los subdirectorios específicos y los contratos formales se crean cuando exista una necesidad real y un activo que administren. No se crearán directorios vacíos masivos.

## 9. Contratos y metadatos

Se conserva la propuesta de metadatos comunes del documento v0.2.0. Los esquemas formales para Agent, Skill, Prompt, Routine, Context, Tool, Project y Decision se definirán en una fase posterior.

Como mínimo, cada activo deberá declarar, cuando aplique:

- identificador estable y nombre;
- tipo, versión y estado;
- propósito y responsable;
- entradas, salidas y dependencias;
- referencias de procedencia;
- referencias a pruebas y validaciones;
- historial de cambios o referencia al changelog.

No se deben imponer campos que no tengan sentido para un tipo particular de activo.

## 10. Ciclo de vida y versionado

Se conserva la distinción entre estados:

DRAFT → PROPOSED → APPROVED → IMPLEMENTED → VALIDATED → DEPRECATED → RETIRED

No todos los activos deben recorrer todos los estados. La aprobación autoriza; la implementación demuestra que el activo existe; la validación demuestra que se probó con evidencia identificable.

Semantic Versioning se aplica a componentes cuyo cambio pueda afectar compatibilidad o comportamiento. La versión de este documento no implica que todos los activos del repositorio deban compartir el mismo número.

## 11. Seguridad y límites multi-proyecto

- No guardar secretos, tokens ni credenciales en el repositorio.
- Aplicar mínimo privilegio a agentes, conectores y automatizaciones.
- Tratar datos externos y salidas de modelos como entradas no confiables hasta verificarlas.
- Mantener procedencia y licencias de los activos reutilizados.
- Mantener separados los datos, secretos, código privado y reglas de negocio de cada consumidor.
- Definir interfaces y contratos antes de automatizar intercambios entre proyectos.

## 12. Aplicación a proyectos consumidores

INnGeNiUs Electoral IA es un consumidor prioritario, pero no define el dominio del núcleo.

Podrá consumir componentes publicados por MIND ARCHIVE mediante referencias y contratos versionados. Sus datos electorales, configuraciones, lógica de negocio, análisis y despliegues permanecerán en su propio entorno.

Los mismos principios permitirán registrar futuros productos de INnGeNiUs sin convertir la biblioteca central en un proyecto monolítico.

## 13. Fuera de alcance

Esta versión no autoriza ni declara implementados:

- runtime u orquestador multiagente;
- motor de recuperación semántica o base vectorial;
- aplicación web o móvil;
- automatización autónoma con permisos de escritura;
- sincronización automática entre repositorios;
- migración de datos o código de proyectos consumidores;
- perfiles de agentes históricos no recuperados y verificados.

## 14. Criterios de revisión y aceptación

Antes de promover esta candidata a baseline aprobada, revisar:

1. Que la correspondencia entre siete capas y doce dominios sea inequívoca.
2. Que SKILLS, PROMPTS y ROUTINES tengan límites y contratos distintos.
3. Que GOVERNANCE y PROJECTS sean transversales sin duplicar autoridad.
4. Que la estructura de carpetas refleje los dominios sin confundirla con las capas.
5. Que la separación entre biblioteca central y consumidores sea suficiente.
6. Que los estados de aprobación, implementación y validación no se mezclen.
7. Que la documentación histórica aprobada se preserve literalmente cuando se recupere.
8. Que los cambios propuestos no se interpreten como runtime ya construido.

## 15. Registro de estado

| Elemento | Estado |
|---|---|
| Selección HYBRID / INTEGRATED / CROSS | Decidida explícitamente por el propietario |
| Formalización en esta candidata v0.3.0 | Preparada para revisión |
| CORE BLUEPRINT v0.1.0 literal | Aprobado en conversación; archivo no localizado en esta rama |
| Arquitectura v0.3.0 como baseline definitivo | Pendiente de revisión y aprobación |
| Implementación runtime | Fuera de alcance; no declarada |
| Integración a main | No realizada ni autorizada |

**Siguiente puerta de control:** revisión del propietario y aprobación explícita de esta candidata o solicitud de correcciones. No hacer merge a main antes de esa aprobación.
