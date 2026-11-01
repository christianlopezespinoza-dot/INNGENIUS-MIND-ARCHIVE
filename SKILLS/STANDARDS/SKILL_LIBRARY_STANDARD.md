# Skill Library Standard

**Estado:** DRAFT.

## 1. Unidad de distribución

Cada Skill vive en un directorio independiente y contiene un archivo raíz `SKILL.md`. Puede incluir referencias, scripts y recursos auxiliares si son necesarios para ejecutar o comprender la capacidad.

## 2. Metadatos

El encabezado YAML debe incluir, como mínimo, un nombre estable y una descripción clara de la capacidad y sus condiciones de activación. Los metadatos adicionales deben seguir la especificación Agent Skills vigente y no introducir campos incompatibles sin documentarlos.

## 3. Contenido del Skill

- propósito;
- cuándo se activa;
- entradas requeridas;
- procedimiento;
- restricciones y límites;
- resultados esperados;
- criterios de calidad;
- manejo de errores y abstención;
- referencias a recursos;
- ejemplos mínimos cuando aporten valor.

## 4. Diseño

- Una capacidad principal por Skill.
- Instrucciones claras y accionables.
- Evitar prompts monolíticos que mezclen identidad, tarea y contexto.
- Mover material extenso a archivos de referencia y cargarlo solo cuando sea necesario.
- No incluir credenciales.
- Declarar dependencias externas y permisos.
- Versionar y probar el Skill antes de recomendarlo como estable.

## 5. Estados

DRAFT, PROPOSED, APPROVED, IMPLEMENTED, VALIDATED, DEPRECATED, RETIRED.
