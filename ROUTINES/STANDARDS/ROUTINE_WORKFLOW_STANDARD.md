# Routine and Workflow Standard

**Estado:** DRAFT.

## Definición

Una Routine es un procedimiento repetible. Un Workflow es una secuencia coordinada de tareas, decisiones y transferencias entre personas, agentes, Skills y herramientas.

## Especificación mínima

- workflow_id y versión;
- propósito y disparador;
- propietario;
- precondiciones;
- entradas y fuentes;
- pasos numerados;
- responsable de cada paso;
- ramas y reglas de decisión;
- herramientas/Skills invocados;
- controles y aprobaciones;
- salidas y formatos;
- errores, reintentos y compensaciones;
- registro de ejecución;
- criterios de éxito y validación.

## Reglas

- Los pasos con efectos externos deben identificar permisos y confirmaciones.
- No diseñar rutinas con ciclos infinitos o reintentos sin límite.
- Distinguir automatización propuesta de automatización desplegada.
- Mantener el procedimiento independiente del proveedor cuando sea viable.
- Cada workflow debe tener pruebas de recorrido normal, error y excepción.
