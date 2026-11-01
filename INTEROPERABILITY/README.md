# INTEROPERABILITY

Módulo para contratos y adaptadores que permiten conectar MIND ARCHIVE con modelos, herramientas, servicios, repositorios y aplicaciones externas.

## Alcance
- protocolos;
- conectores;
- adaptadores de proveedores;
- contratos de intercambio;
- mapeos de autenticación y permisos (sin secretos).

## Reglas
- preferir estándares abiertos y contratos explícitos;
- aislar dependencias de proveedor detrás de adaptadores;
- documentar permisos, límites, datos transferidos y tratamiento de errores;
- no habilitar escrituras externas sin autorización y controles;
- validar compatibilidad y seguridad antes de publicar un conector.

La presencia de un protocolo en documentación no significa que exista un conector funcional.
