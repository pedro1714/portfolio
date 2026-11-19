# Asistente RAG con Control de Acceso y Auditoría

> A retrieval-augmented assistant over a document set where permissions matter: each document has an access level, the retriever enforces it per user, answers cite their sources, and every query is audit-logged — built on local models so the data never leaves the machine.
> Status: 💡 Designed — full build plan documented, not yet executed. Nothing in this file is presented as done.

**Estado:** 💡 Diseñado (plan completo documentado, pendiente de ejecutar)

## El problema que resuelve

Los asistentes RAG ingenuos filtran información: recuperan cualquier documento para cualquier usuario. En una empresa eso es inaceptable. Este proyecto demuestra un RAG con control de acceso real por documento y trazabilidad completa.

## Arquitectura y stack

- Ollama (LLM local) + embeddings locales
- Índice vectorial con metadatos de nivel de acceso por documento
- Filtro de recuperación por rol del usuario (pre-retrieval)
- Registro de auditoría: usuario, consulta, documentos usados
- Set de documentos de prueba con 3 niveles (público, interno, confidencial)

## Paso a paso de construcción

1. Preparar el corpus de prueba con niveles de acceso marcados por documento.
2. Indexar con embeddings guardando el nivel como metadato obligatorio.
3. Implementar la recuperación con filtro por rol: el rol bajo jamás recibe fragmentos confidenciales, ni siquiera citados.
4. Añadir citas obligatorias: cada respuesta referencia los documentos usados.
5. Atacar el sistema: preguntas diseñadas para filtrar documentos confidenciales con rol bajo (incluye inyección vía documento).
6. Revisar el log de auditoría y documentar cada intento y su resultado.

## Entregable / evidencia final

Matriz rol × nivel con resultados de las pruebas de fuga + ejemplos de respuestas con citas + extracto del log de auditoría.

## Qué demuestra de mis habilidades

RAG, Ollama, control de acceso, auditoría, seguridad de IA aplicada
