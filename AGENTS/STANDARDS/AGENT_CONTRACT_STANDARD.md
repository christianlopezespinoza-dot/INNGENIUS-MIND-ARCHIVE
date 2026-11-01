# Agent Profile and Contract Standard

**Estado:** DRAFT.

## 1. Propósito

Separar identidad y responsabilidad de un agente de las capacidades que consume.

## 2. Perfil mínimo

Cada perfil de agente debe definir:
- `agent_id` estable;
- nombre y propósito;
- misión y responsabilidades;
- tareas incluidas y excluidas;
- autoridad y límites;
- entradas y salidas;
- Skills autorizados y rangos compatibles;
- herramientas y permisos;
- dependencias;
- política de escalamiento y aprobación humana;
- criterios de evaluación;
- versión y estado.

## 3. Contrato de ejecución

Debe especificar:
- precondiciones;
- esquema de entrada;
- comportamiento esperado;
- esquema de salida;
- errores y condiciones de abstención;
- fuentes de verdad;
- manejo de información no confiable;
- acciones que requieren confirmación;
- evidencias y logs permitidos.

## 4. Reglas

- Un agente no hereda permisos por el mero hecho de consumir un Skill.
- Los permisos se conceden explícitamente y con mínimo privilegio.
- El perfil no debe duplicar el contenido completo de cada Skill.
- Un agente debe revelar incertidumbre y abstenerse ante evidencia insuficiente.
- No atribuir nombres, funciones ni jerarquías a los seis agentes históricos hasta recuperar los perfiles originales.
