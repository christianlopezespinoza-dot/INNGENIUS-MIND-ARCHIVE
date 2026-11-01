# Component Metadata and Lifecycle Standard

**Estado:** DRAFT.

## 1. Propósito

Definir una ficha mínima común para registrar Skills, Prompts, Agents, Routines, Knowledge assets, Tools y Adapters sin forzar que todos tengan los mismos campos operativos.

## 2. Metadatos comunes

| Campo | Requisito | Descripción |
|---|---|---|
| id | Obligatorio | Identificador estable y único |
| name | Obligatorio | Nombre legible |
| type | Obligatorio | Tipo de componente |
| version | Condicional | SemVer cuando haya ciclo de compatibilidad |
| status | Obligatorio | Estado de ciclo de vida |
| purpose | Obligatorio | Responsabilidad y resultado esperado |
| owner | Obligatorio | Responsable funcional |
| created_at | Recomendado | Fecha de creación |
| updated_at | Recomendado | Última actualización |
| dependencies | Cuando aplique | IDs y rangos de versión requeridos |
| inputs | Cuando aplique | Entradas esperadas y validaciones |
| outputs | Cuando aplique | Resultados y formato |
| source_refs | Cuando aplique | Procedencia |
| validation_refs | Cuando aplique | Pruebas y evidencias |
| change_history | Obligatorio para releases | Referencia al historial |

## 3. Estados

- DRAFT: trabajo interno sin propuesta formal.
- PROPOSED: sometido a revisión.
- APPROVED: autorizado para implementación.
- IMPLEMENTED: existe en el repositorio o sistema designado.
- VALIDATED: superó las pruebas declaradas.
- DEPRECATED: se recomienda no usar en nuevos trabajos.
- RETIRED: fuera de servicio, conservado por trazabilidad.

## 4. Reglas

- APPROVED no significa IMPLEMENTED.
- IMPLEMENTED no significa VALIDATED.
- No incluir secretos en metadatos.
- Declarar dependencias con versión o rango compatible.
- Conservar identificadores estables aunque cambie el nombre visible.
- Los esquemas formales se almacenan en CORE/SCHEMAS.
