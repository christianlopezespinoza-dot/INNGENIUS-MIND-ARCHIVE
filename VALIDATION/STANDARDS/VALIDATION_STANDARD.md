# Validation and Evidence Standard

**Estado:** DRAFT.

## Niveles de validación

1. **Documental:** completitud, coherencia y referencias.
2. **Estructural:** formatos, metadatos y esquemas.
3. **Unitario:** comportamiento aislado.
4. **Integración:** contratos entre componentes.
5. **End-to-end:** flujo completo.
6. **Seguridad:** permisos, secretos, límites y entradas hostiles.
7. **Regresión:** ausencia de degradaciones conocidas.

## Registro de una prueba

- test_id;
- componente y versión;
- objetivo;
- entorno;
- precondiciones;
- pasos;
- resultado esperado;
- resultado observado;
- estado PASS/FAIL/BLOCKED;
- evidencia;
- fecha y ejecutor.

## Reglas

- Un archivo presente no prueba que su funcionalidad opere.
- Una validación estructural no prueba comportamiento runtime.
- Los resultados deben ser reproducibles.
- Los fallos y limitaciones se conservan en el informe.
- No declarar PASS sin resultado y evidencia.
