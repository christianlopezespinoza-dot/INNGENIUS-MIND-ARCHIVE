# Reusable Prompt Standard

**Estado:** DRAFT.

## Campos recomendados

- prompt_id;
- name;
- purpose;
- activation/use case;
- target model or model-independent status;
- role (si es necesario);
- input variables;
- context sources;
- task instructions;
- constraints and exclusions;
- expected output format;
- quality criteria;
- failure/abstention behavior;
- dependencies;
- version and status;
- test examples.

## Reglas

1. Un prompt define una tarea o patrón de instrucción, no un permiso.
2. No incrustar secretos ni datos personales innecesarios.
3. Separar variables del texto fijo.
4. Identificar instrucciones de sistema, datos y material no confiable.
5. Incluir criterios observables de aceptación.
6. Evitar duplicar el contenido de Skills y contratos de agentes.
7. Probar con casos positivos, negativos y ambiguos.
