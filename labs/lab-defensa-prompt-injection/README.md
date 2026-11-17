# Lab Defensa contra Prompt Injection — OWASP Top 10 for LLM + Guardarraíles

**Estado:** 💡 Guía lista — pendiente de ejecutar

## Objetivo

Construir una aplicación pequeña con un LLM local, atacarla sistemáticamente con las técnicas del **OWASP Top 10 for LLM** (empezando por prompt injection directo e indirecto y jailbreaks) y luego defenderla con **guardarraíles** medibles: repetir los mismos ataques y comparar resultados antes/después.

## Habilidad de vacante que prueba

Seguridad de aplicaciones de IA: "LLM security, prompt injection, OWASP Top 10 for LLM". Conecta directamente con el **Tema 1 de mi tesis** de maestría (explotación de vulnerabilidades en modelos generativos).

## Prerrequisitos

- Ollama local con un modelo pequeño ya instalado (llama3.2)
- Python para la app mínima (un endpoint que recibe texto y responde con el modelo)
- Mi Coding Agent Harness como referencia de guardarraíles por política (confirmación y bloqueos)

## Paso a paso

1. Construir la app mínima: un asistente con instrucciones de sistema definidas (ej.: "asistente de soporte que solo habla de los productos de la tienda X") usando Ollama local.
2. Preparar la batería de ataques (mínimo 15 casos) mapeada al OWASP Top 10 for LLM: inyección directa ("ignora tus instrucciones…"), inyección indirecta (instrucciones escondidas en un texto/documento que la app procesa), jailbreak por rol, extracción del prompt del sistema y fuga de datos fuera de alcance.
3. Ejecutar la batería contra la app **sin defensas** y registrar qué ataques tienen éxito (línea base).
4. Aplicar guardarraíles por capas: delimitación y refuerzo de instrucciones, validación de entrada, filtro de salida (que la respuesta no contenga el prompt del sistema ni datos fuera de alcance) y principio de mínimo privilegio en lo que la app puede hacer.
5. Re-ejecutar **la misma batería** y registrar el nuevo resultado por ataque.
6. Documentar los ataques que siguen funcionando y por qué (límites honestos de las defensas).

## Entregable / evidencia final

- Tabla antes/después: ataque × técnica OWASP × resultado sin defensas × resultado con guardarraíles
- El código de la app y de los guardarraíles, con los casos de ataque como batería reutilizable
- Mini-informe de hallazgos (material directo para el marco práctico de mi tesis, Tema 1)

## Tiempo estimado

4–5 horas (en 2 sesiones)
