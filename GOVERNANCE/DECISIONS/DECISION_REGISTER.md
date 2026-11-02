# Decision Register — INnGeNiUs MIND ARCHIVE

Registro central de decisiones. Cada decisión debe tener ID estable, estado, fecha, responsable, contexto, decisión, consecuencias y referencias.

## Decisiones

| ID | Fecha | Decisión | Estado | Alcance |
|---|---|---|---|---|
| ADR-0001 | 2026-11-01 | Biblioteca modular multi-proyecto | APPROVED | Principio arquitectónico |
| ADR-0002 | 2026-11-01 | Agent Skills como formato abierto de capacidades especializadas | APPROVED | Estándar de capacidades |
| ADR-0003 | 2026-11-01 | Semantic Versioning para componentes versionados | APPROVED | Versionado |
| ADR-0004 | 2026-11-01 | CORE BLUEPRINT v0.1.0 | APPROVED IN CONVERSATION | Documento histórico; archivo literal pendiente |
| ADR-0005 | 2026-11-01 | Arquitectura consolidada v0.2.0 y estructura ampliada | PROPOSED | Pendiente de aprobación arquitectónica |

| ADR-0006 | 2026-11-02 | Modelo híbrido: 7 capas lógicas + 12 dominios organizativos | APPROVED IN CONVERSATION | Formalizado en candidata v0.3.0; documento pendiente de revisión |
| ADR-0007 | 2026-11-02 | SKILLS, PROMPTS y ROUTINES como módulos integrados en SKILLS ENGINE | APPROVED IN CONVERSATION | Módulos diferenciados dentro de una capa lógica común |
| ADR-0008 | 2026-11-02 | GOVERNANCE y PROJECTS como dominios transversales | APPROVED IN CONVERSATION | Formalizado en candidata v0.3.0 |

## Reglas

- No convertir una recomendación en decisión aprobada.
- Toda modificación a una decisión aprobada crea una nueva revisión o ADR; no reescribe la historia.
- Registrar quién aprueba y la evidencia que respalda la decisión.
- Vincular decisiones con archivos, commits, pruebas y componentes afectados.
- Los estados IMPLEMENTED y VALIDATED requieren evidencia técnica, no solo aprobación.

## Nota de trazabilidad — 2026-11-02

Las decisiones ADR-0006 a ADR-0008 fueron seleccionadas explícitamente por el propietario. Su formalización documental se encuentra en CORE/ARCHITECTURE/MASTER_ARCHITECTURE_CANDIDATE_v0.3.0.md. La candidata completa permanece pendiente de revisión y aprobación como baseline. El borrador v0.2.0 se conserva como antecedente; no se sobrescribe.
