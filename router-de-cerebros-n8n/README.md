# Router de Cerebros v2 (n8n)

> An n8n research router built for my master's thesis: it queries scholarly APIs (Crossref as the working engine, Semantic Scholar in the fallback chain), organizes sources for Zotero/Notion, and keeps per-session memory.
> Status: ✅ Built and used for real thesis research.

**Estado:** ✅ Construido

## Qué es

Un enrutador de investigación académica construido en n8n. Recibe una pregunta o tema de investigación, consulta fuentes académicas mediante APIs REST, ordena y deduplica los resultados y los deja listos para trabajarlos en Zotero y Notion. Lo construí como la "central de cerebros" de mi tesis de maestría en ciberseguridad.

## El problema que resuelve

Investigar para una tesis significa saltar entre buscadores académicos, perder fuentes ya encontradas y repetir consultas. Necesitaba un solo punto de entrada que consultara varias fuentes, sobreviviera a la caída de una API y recordara el contexto de cada sesión de trabajo.

## Arquitectura y stack

- **n8n** (autohospedado) como motor de flujos
- **Crossref API** como motor de búsqueda bibliográfica en funcionamiento
- **Semantic Scholar API** integrada en la cadena de fuentes (su llave propia quedó pendiente de activar; el enrutador funciona con Crossref y está diseñado para sumar la fuente sin rehacer el flujo)
- **Fallback automático** entre fuentes/llaves de respaldo cuando una consulta falla
- **Memoria por sesión** para mantener el contexto de cada línea de investigación
- **Ollama local** para apoyo de clasificación/resumen sin costo por token
- Salida organizada hacia **Zotero / Notion**

## Paso a paso: cómo se construyó

1. Definí el caso de uso: una pregunta de tesis entra; salen fuentes verificables, ordenadas y listas para citar.
2. Monté el flujo base en n8n: webhook de entrada → normalización de la consulta → nodo HTTP contra la API de Crossref.
3. Estructuré la respuesta: extracción de título, autores, año, DOI y enlace, con deduplicación por DOI.
4. Añadí la cadena de fallback: si una fuente responde error o vacío, el flujo intenta la siguiente antes de rendirse.
5. Implementé memoria por sesión para que las consultas de seguimiento ("más sobre el segundo tema") tuvieran contexto.
6. Conecté la salida con mi sistema de notas (Zotero/Notion) para pasar de "resultado de búsqueda" a "fuente de trabajo" sin copiar y pegar.
7. Lo probé con los dos temas reales de mi tesis (vulnerabilidades en LLMs y optimización de SIEM con IA) y ajusté el ordenamiento de resultados.

## Estado real

✅ Construido y usado para la investigación de mi tesis. La rama de Semantic Scholar está preparada en el diseño; su llave de API propia quedó pendiente, por lo que el motor que trabaja hoy es Crossref.

## Qué demuestra de mis habilidades

- Diseño de flujos de automatización con manejo de errores y fallback (n8n en producción personal)
- Integración de APIs REST académicas y normalización de datos bibliográficos
- Arquitectura de "cerebros" externos para apoyar investigación con IA sin depender de un solo proveedor
