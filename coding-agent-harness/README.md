# Coding Agent Harness (Python puro)

> A tool-using coding-agent loop written from scratch in plain Python — no agent frameworks: the model proposes tool calls, the harness asks for confirmation before executing, and destructive commands are blocked by design.
> Status: ✅ Built as a learning and portfolio piece.

**Estado:** ✅ Construido

## Qué es

Un arnés (harness) de agente programador escrito desde cero en **Python puro**, sin frameworks de agentes: un bucle que le da a un modelo de lenguaje herramientas (leer/escribir archivos, ejecutar comandos), interpreta sus llamadas, **pide confirmación antes de ejecutar** y **bloquea comandos destructivos** por política, no por confianza en el modelo.

## El problema que resuelve

Quería entender por dentro cómo funciona un agente que programa — no usar una caja negra. Y quería hacerlo con guardarraíles reales: un agente que puede ejecutar comandos en mi máquina necesita frenos que no dependan de que el modelo "se porte bien".

## Arquitectura y stack

- **Python puro** (sin LangChain ni frameworks de agentes)
- Bucle agente: mensajes → llamada de herramienta propuesta → validación → confirmación → ejecución → resultado
- Herramientas: lectura/escritura de archivos y ejecución de comandos en terminal
- **Política de seguridad en el arnés**: lista de comandos destructivos bloqueados y confirmación humana previa a cualquier ejecución

## Paso a paso: cómo se construyó

1. Escribí el bucle mínimo: enviar contexto al modelo, recibir una acción propuesta, ejecutarla y devolver el resultado.
2. Definí las herramientas con esquemas claros (nombre, parámetros, salida) para que el modelo las usara sin ambigüedad.
3. Añadí la capa de confirmación: ninguna ejecución ocurre sin un "sí" explícito del operador.
4. Implementé el bloqueo de comandos destructivos por patrones (borrados recursivos, formateos, etc.) directamente en el arnés.
5. Probé el agente con tareas reales pequeñas (crear y corregir scripts), observando dónde fallaba el bucle y ajustando el manejo de errores y de contexto.
6. Documenté las decisiones: qué hace el arnés, qué hace el modelo y dónde están los límites.

## Estado real

✅ Construido y funcional para tareas supervisadas. Es una pieza de aprendizaje y portafolio, no un producto: su valor es demostrar que entiendo y puedo construir la maquinaria de un agente, con seguridad desde el diseño.

## Qué demuestra de mis habilidades

- Comprensión profunda de agentes LLM: bucles, herramientas, contexto y errores
- Python aplicado a sistemas, no solo a scripts sueltos
- Seguridad en agentes: confirmación humana y bloqueo por política (guardarraíles)
