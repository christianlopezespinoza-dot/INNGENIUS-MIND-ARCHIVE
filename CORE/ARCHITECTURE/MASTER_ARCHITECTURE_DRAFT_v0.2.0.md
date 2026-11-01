# INnGeNiUs MIND ARCHIVE — Master Architecture v0.2.0

**Estado:** DRAFT — pendiente de aprobación arquitectónica  
**Tipo:** arquitectura lógica y organizacional  
**Alcance:** biblioteca central multi-proyecto y multi-agente  
**No es:** una aplicación runtime ya implementada.

## 1. Propósito

INnGeNiUs MIND ARCHIVE es una infraestructura modular para crear, registrar, descubrir, reutilizar, ejecutar y validar activos de conocimiento y trabajo con IA.

Administra:
- perfiles y contratos de agentes;
- Skills y capacidades especializadas;
- prompts y plantillas de instrucciones;
- rutinas, procedimientos y workflows;
- conocimiento, fuentes y contextos de proyecto;
- scripts, herramientas, adaptadores y conectores;
- decisiones, aprobaciones, pruebas y evidencias;
- versiones, dependencias y ciclos de vida.

El repositorio es una biblioteca central, no un contenedor de todos los datos ni de todo el código de cada proyecto consumidor.

## 2. Principios aprobados que se preservan

1. **Biblioteca modular:** diferentes proyectos y agentes pueden reutilizar componentes sin fusionar sus dominios.
2. **Agent Skills:** formato abierto para capacidades especializadas; no reemplaza la identidad, el perfil ni el contrato del agente.
3. **Semantic Versioning:** versionado semántico para componentes cuyo cambio pueda afectar compatibilidad o comportamiento.

Estos principios están aprobados. La organización detallada de módulos de este documento sigue siendo una propuesta hasta su aprobación.

## 3. Modelo conceptual

El sistema distingue seis clases de activos:

| Activo | Responde a | Contenido típico |
|---|---|---|
| Agent | ¿Quién ejecuta y con qué límites? | Perfil, rol, permisos, contrato |
| Skill | ¿Qué capacidad reutilizable sabe ejecutar? | Instrucciones, recursos, scripts auxiliares |
| Prompt | ¿Qué instrucción o misión se entrega? | Objetivo, contexto, restricciones, salida |
| Routine / Workflow | ¿En qué secuencia se realiza el trabajo? | Pasos, decisiones, entradas y salidas |
| Knowledge / Context | ¿Qué información fundamenta el trabajo? | Fuentes, hechos, contexto, vigencia |
| Tool / Adapter | ¿Qué operación externa o local se puede invocar? | Interfaces, configuración no secreta, contratos |

Los activos se complementan con registros transversales de decisiones, dependencias, validaciones, procedencia y versiones.

## 4. Arquitectura lógica propuesta

### 4.1 CORE — gobierno y contratos del sistema
Define principios, arquitectura, estándares, políticas, taxonomías, metadatos y esquemas comunes.

### 4.2 KNOWLEDGE — conocimiento y contexto
Conserva fuentes, investigaciones, conceptos, glosarios, afirmaciones y contexto específico de cada proyecto. Debe registrar procedencia, vigencia y estado de revisión.

### 4.3 AGENTS — identidad y responsabilidad
Define perfiles, contratos, capacidades permitidas, límites, entradas, salidas, dependencias y criterios de evaluación. Un agente puede consumir varios Skills.

### 4.4 SKILLS — capacidades especializadas
Biblioteca de Skills con formato Agent Skills y recursos auxiliares. Cada Skill tiene alcance delimitado, instrucciones, entradas/salidas, dependencias y pruebas.

### 4.5 PROMPTS — instrucciones y misiones
Biblioteca versionada de prompts reutilizables. Un prompt puede ser utilizado por un agente, Skill o rutina, pero no sustituye sus contratos.

### 4.6 ROUTINES — procesos reproducibles
Define procedimientos y workflows con pasos, bifurcaciones, responsables, controles, manejo de errores y criterios de finalización.

### 4.7 EXECUTION — implementación operativa
Contiene scripts, herramientas locales, automatizaciones y utilidades. La ejecución debe estar separada de la documentación conceptual y usar configuración segura.

### 4.8 INTEROPERABILITY — integración
Define adaptadores, conectores y protocolos para comunicar modelos, aplicaciones, servicios, repositorios y sistemas externos. Los proveedores deben ser reemplazables cuando sea viable.

### 4.9 VALIDATION — calidad y evidencia
Mantiene planes de prueba, casos, resultados, reportes y evidencias. Diferencia validación documental, estructural, funcional, integración y seguridad.

### 4.10 GOVERNANCE — decisiones y control
Mantiene ADRs, aprobaciones, revisiones, políticas, responsables y registro de cambios. Las decisiones aprobadas no se modifican silenciosamente.

### 4.11 VERSIONING — evolución y compatibilidad
Mantiene changelog, releases, historial de versiones, matrices de compatibilidad y avisos de deprecación.

### 4.12 PROJECTS — catálogo de proyectos consumidores
Contiene únicamente manifiestos, referencias, mapas de integración y contexto de alto nivel. El código, datos privados, secretos y reglas de negocio de cada producto permanecen en sus repositorios o sistemas propios.

## 5. Estructura de directorios propuesta

```text
INNGENIUS-MIND-ARCHIVE/
├── README.md
├── START_HERE.md
├── LICENSE
├── .gitignore
├── CORE/
│   ├── ARCHITECTURE/
│   ├── BLUEPRINT/
│   ├── POLICIES/
│   ├── STANDARDS/
│   ├── SCHEMAS/
│   └── REGISTRY/
├── KNOWLEDGE/
│   ├── SOURCES/
│   ├── RESEARCH/
│   ├── CONCEPTS/
│   ├── GLOSSARY/
│   ├── CLAIMS/
│   └── CONTEXT/
├── AGENTS/
│   ├── PROFILES/
│   ├── CONTRACTS/
│   ├── REGISTRY/
│   └── STANDARDS/
├── SKILLS/
│   ├── LIBRARY/
│   ├── TEMPLATES/
│   ├── REGISTRY/
│   └── STANDARDS/
├── PROMPTS/
│   ├── LIBRARY/
│   ├── TEMPLATES/
│   └── REGISTRY/
├── ROUTINES/
│   ├── PROCEDURES/
│   ├── WORKFLOWS/
│   ├── TEMPLATES/
│   └── REGISTRY/
├── EXECUTION/
│   ├── SCRIPTS/
│   ├── TOOLS/
│   └── AUTOMATIONS/
├── INTEROPERABILITY/
│   ├── ADAPTERS/
│   ├── CONNECTORS/
│   └── PROTOCOLS/
├── VALIDATION/
│   ├── PLANS/
│   ├── TEST_CASES/
│   ├── REPORTS/
│   └── EVIDENCE/
├── GOVERNANCE/
│   ├── DECISIONS/
│   ├── POLICIES/
│   └── REVIEWS/
├── VERSIONING/
│   ├── CHANGELOG/
│   ├── RELEASES/
│   └── COMPATIBILITY/
└── PROJECTS/
    ├── REGISTRY/
    └── TEMPLATES/
```

Los directorios vacíos se crean cuando exista un primer componente real; no se recomienda generar carpetas sin propósito ni archivos placeholder masivos.

## 6. Relaciones y dependencias

- Un Agent declara los Skills que puede utilizar.
- Un Skill puede referenciar Prompts, scripts, herramientas y fuentes.
- Un Prompt puede ser llamado desde una Routine o directamente por un Agent.
- Una Routine coordina agentes, Skills y herramientas mediante pasos explícitos.
- Knowledge aporta fuentes y contextos a Agents, Skills y Routines.
- Tools y Adapters implementan operaciones concretas sin convertirse en la fuente de autoridad de las políticas.
- Validation comprueba componentes y workflows.
- Governance registra quién propuso, aprobó y autorizó los cambios.
- Versioning registra la evolución y compatibilidad de todos los activos versionados.

No debe existir una dependencia circular no documentada. Los contratos se definen antes que las implementaciones.

## 7. Modelo común de metadatos

Todo activo administrado debe tener, como mínimo, cuando corresponda:

- `id`: identificador estable;
- `name`: nombre legible;
- `type`: tipo de activo;
- `version`: versión del activo;
- `status`: estado de ciclo de vida;
- `purpose`: propósito;
- `owner`: responsable;
- `created_at` y `updated_at`;
- `dependencies`: dependencias declaradas;
- `inputs` y `outputs`;
- `source_refs`: referencias de procedencia;
- `validation_refs`: pruebas/evidencias;
- `change_history`: historial o referencia al changelog.

Los esquemas formales JSON/YAML se definirán en CORE/SCHEMAS tras aprobar el modelo. No inventar campos obligatorios para tipos de activos que no los necesiten.

## 8. Estados de ciclo de vida

`DRAFT → PROPOSED → APPROVED → IMPLEMENTED → VALIDATED → DEPRECATED → RETIRED`

No todos los activos necesitan recorrer todos los estados. APPROVED indica autorización; IMPLEMENTED indica presencia real; VALIDATED exige pruebas identificables. No son sinónimos.

## 9. Gobernanza

- **Nivel operativo:** correcciones editoriales, metadatos y documentación sin cambiar contratos ni arquitectura.
- **Nivel arquitectónico:** estructura, esquemas, estándares, contratos, dependencias y compatibilidad; requiere revisión y aprobación.
- **Nivel crítico:** seguridad, permisos, datos sensibles, cambios destructivos, secretos o ruptura de compatibilidad; requiere autorización específica y validación reforzada.

El usuario conserva la autoridad final sobre las decisiones arquitectónicas y los cambios críticos.

## 10. Seguridad y separación de dominios

- No almacenar secretos, tokens, contraseñas ni credenciales en el repositorio.
- Separar instrucciones confiables de entradas externas no confiables.
- Aplicar mínimo privilegio a agentes, conectores y automatizaciones.
- Validar entradas y salidas en los límites de confianza.
- Documentar licencias y restricciones de reutilización.
- Mantener datos privados y lógica de negocio en los proyectos consumidores.
- No tratar salidas de modelos como hechos sin verificación.

## 11. Proyectos consumidores

INnGeNiUs Electoral IA es un consumidor prioritario. Debe mantener sus propios datos, configuración, reglas electorales, modelos de negocio y despliegues. Puede reutilizar Skills, contratos, rutinas y estándares publicados por MIND ARCHIVE.

No incorporar datos electorales ni lógica de campaña al núcleo general.

## 12. Componentes históricos y referencias

Las propuestas anteriores con Research Engine, Mind Engine, Agent Orchestrator y Test Factory se consideran antecedentes útiles, no módulos aprobados automáticamente. Sus responsabilidades se redistribuyen en KNOWLEDGE, AGENTS, ROUTINES y VALIDATION cuando corresponda.

La arquitectura de archivo intelectual/personas debe tratarse como un dominio de conocimiento especializado, no como el sistema completo de gestión de agentes y Skills.

## 13. Fuera de alcance en esta versión

- Runtime de orquestación multiagente.
- Base de datos operacional o vectorial.
- Panel web o aplicación móvil.
- Automatización autónoma con permisos de escritura.
- Implementación de los seis perfiles históricos sin recuperar y verificar sus contratos.
- Migración automática de proyectos consumidores.

## 14. Criterios de aceptación del CORE

1. Principios y responsabilidades modulares aprobados.
2. Contratos y metadatos definidos.
3. Registro de decisiones operativo.
4. Estándares para Agent, Skill, Prompt, Routine y Context.
5. Estrategia de versionado y compatibilidad.
6. Pruebas documentales y estructurales reproducibles.
7. Política de seguridad y separación multi-proyecto.
8. Un componente piloto documentado y validado de extremo a extremo.

**Estado final:** propuesta arquitectónica consolidada v0.2.0; pendiente de aprobación. No declarar el CORE completo ni listo para producción.
