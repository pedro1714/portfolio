# Segundo Cerebro Local (Obsidian + script + n8n)

> A 100% local, free second brain: an Obsidian vault, a script that answers questions using ONLY my own notes as its source, and an n8n capture flow to feed the vault.
> Status: ✅ Built (v1) and in use.

**Estado:** ✅ Construido (versión 1)

## Qué es

Mi sistema personal de conocimiento en tres piezas: una **bóveda de Obsidian** con mis notas, un **script que responde preguntas consultando únicamente esas notas** (si la respuesta no está en mis notas, lo dice — no inventa) y un **flujo de captura en n8n** para guardar material nuevo en la bóveda sin fricción.

## El problema que resuelve

Acumulo notas, enlaces y documentos que luego no encuentro, y los asistentes de IA genéricos responden "de memoria" mezclando lo que yo guardé con lo que ellos creen. Quería un sistema que respondiera **desde mi material**, gratis y sin enviar mis notas a la nube.

## Arquitectura y stack

- **Obsidian** como bóveda de notas (archivos Markdown locales)
- **Script local** de consulta con recuperación sobre la bóveda: responde solo con lo que las notas contienen y cita la nota de origen
- **n8n** para el flujo de captura de material nuevo hacia la bóveda
- Todo corre en mi PC: 100% local, costo $0

## Paso a paso: cómo se construyó

1. Organicé la bóveda de Obsidian con una estructura simple y sostenible (nada de sistemas que se abandonan a la semana).
2. Escribí el script de consulta: indexa las notas y, ante una pregunta, recupera los fragmentos relevantes.
3. Impuse la regla de oro en el prompt del sistema: responder **solo** desde las notas recuperadas; si no está, decir "no está en tus notas".
4. Añadí la cita de la nota fuente en cada respuesta, para poder verificar en un toque.
5. Construí el flujo de captura en n8n para que guardar algo nuevo en la bóveda tomara segundos desde el teléfono.
6. Lo probé con preguntas cuya respuesta conocía (y con preguntas trampa fuera de mis notas) para verificar que no alucinara.

## Estado real

✅ Versión 1 construida y en uso. Límites conocidos y aceptados: no sincroniza automáticamente teléfono↔PC y responde preguntas, pero aún no ejecuta acciones.

## Qué demuestra de mis habilidades

- Sistemas de recuperación de información (RAG) locales y gratuitos
- Diseño anti-alucinación: respuestas con fuente y negativa honesta
- Integración Obsidian + scripting + n8n en un flujo personal real
