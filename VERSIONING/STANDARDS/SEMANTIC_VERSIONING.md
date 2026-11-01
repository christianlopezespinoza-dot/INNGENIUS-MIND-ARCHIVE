# Semantic Versioning Standard

**Estado:** DRAFT — principio SemVer aprobado; política operativa detallada pendiente de ratificación.

## Formato

`MAJOR.MINOR.PATCH`

- MAJOR: cambio incompatible en contrato, interfaz o comportamiento garantizado.
- MINOR: funcionalidad compatible y retrocompatible.
- PATCH: corrección compatible.

## Aplicación

Usar SemVer para Skills, contratos, esquemas, APIs, herramientas y workflows cuando existan consumidores o expectativas de compatibilidad.

No todo archivo Markdown necesita una versión independiente. Los documentos editoriales pueden versionarse por Git; los estándares y contratos que gobiernan consumidores deben tener versión explícita.

## Reglas de compatibilidad

- Declarar versiones de dependencias.
- Documentar cambios incompatibles y ruta de migración.
- Mantener changelog por release.
- Marcar componentes obsoletos antes de retirarlos cuando sea posible.
- No reutilizar números de versión para contenidos diferentes.
- No sobrescribir versiones históricas aprobadas.
