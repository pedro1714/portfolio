# Gateway de Seguridad para Aplicaciones LLM

> A security gateway that sits in front of a local LLM app: it inspects inputs for prompt injection and jailbreak attempts, redacts PII before it reaches the model, filters outputs for system-prompt leakage, and logs every blocked attempt — tested with an OWASP LLM Top 10 battery.
> Status: 💡 Designed — full build plan documented, not yet executed. Nothing in this file is presented as done.

**Estado:** 💡 Diseñado (plan completo documentado, pendiente de ejecutar)

## El problema que resuelve

Las apps con LLM reciben ataques que un firewall no ve: inyecciones en el texto, extracción del prompt, fuga de datos. Un gateway especializado es la capa de defensa que las empresas están empezando a exigir — y es el frente práctico de mi Tema 1 de tesis.

## Arquitectura y stack

- Python (proxy/gateway frente a Ollama)
- Detección de inyección: reglas + clasificador ligero
- Redacción de PII (patrones y validación) antes del modelo
- Filtro de salida: prompt del sistema y datos fuera de alcance
- Batería de ataques OWASP Top 10 for LLM (la de mi lab de defensa)

## Paso a paso de construcción

1. Construir la app base con Ollama (asistente con alcance definido) detrás del gateway.
2. Implementar la inspección de entrada: patrones de inyección directa e indirecta y codificaciones típicas.
3. Añadir la redacción de PII (correos, teléfonos, cédulas, tarjetas) con registro de qué se redactó.
4. Añadir el filtro de salida: el prompt del sistema y los datos internos nunca salen.
5. Ejecutar la batería OWASP completa y medir: ataques bloqueados, falsos bloqueos sobre uso legítimo.
6. Publicar el informe de límites: qué ataques siguen pasando y qué capa adicional haría falta.

## Entregable / evidencia final

Código del gateway + resultados de la batería OWASP (bloqueados/pasan) + informe honesto de límites.

## Qué demuestra de mis habilidades

LLM security, OWASP LLM Top 10, Python, guardarraíles, seguridad de IA
