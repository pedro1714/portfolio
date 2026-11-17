# Pipeline de Video Animado con IA

> A fully local animated-video pipeline — Python + Pillow scene rendering, edge-TTS voices and FFmpeg assembly — that produced "Claude y el Robot", a short animated series with a consistent character kit. Two episodes rendered: 49.6 s and 47.2 s, 1080×1920.
> Status: ✅ Built; 2 episodes produced. Honestly labeled a format pilot, not a premium finish.

**Estado:** ✅ Construido (2 episodios producidos)

## Qué es

Un pipeline de producción de video animado que corre **en local**: un script de Python compone las escenas (personajes y textos con Pillow), las voces se sintetizan con edge-TTS desde mi fábrica de voz, y FFmpeg ensambla todo en video vertical 1080×1920 listo para redes. Con él produje la serie corta **"Claude y el Robot"** y una mininovela de gatos.

## El problema que resuelve

Quería producir video animado con personajes consistentes **sin depender de suscripciones caras ni de editar a mano en un editor**: dar la idea y el guion, y que el sistema renderizara el episodio. La ruta "premium" por API resultó tener costos por uso separados de las suscripciones, así que construí la ruta local reproducible.

## Arquitectura y stack

- **Python + Pillow**: composición de escenas a partir de un kit fijo de personajes
- **Kit de personajes consistente**: CLAUDE (bloque naranja) y ROBOT (gris metálico), con voces fijas — CLAUDE con es-DO-EmilioNeural y ROBOT con es-MX-JorgeNeural (edge-TTS)
- **FFmpeg 8.x**: ensamblaje de escenas, audio y subtítulos en 1080×1920
- Guiones estructurados por escenas con diálogos y tiempos

## Paso a paso: cómo se construyó

1. Definí el formato: video vertical corto, dos personajes fijos, humor sobre IA y trabajo real.
2. Creé el kit de personajes (diseños y voces fijas) para que cada episodio se viera y sonara igual.
3. Escribí `build_episode.py`: toma el guion por escenas, genera las imágenes de cada escena con Pillow y calcula los tiempos.
4. Integré la síntesis de voz por personaje (edge-TTS) y la mezcla con las escenas.
5. Ensamblé con FFmpeg y añadí subtítulos (tiempos proporcionales a la duración de cada línea).
6. Produje el **Episodio 1: "El mismo perro"** (49.6 s) y la mininovela **"¿Quién es la gata, Michi?"** (47.2 s), revisé el resultado y documenté los defectos reales: animación por saltos, subtítulos por tiempos proporcionales y tercio superior con aire de más.

## Estado real

✅ Pipeline construido y reutilizable; 2 piezas producidas y publicables como **piloto de formato**. No lo presento como acabado premium: es la base sobre la que diseño la fábrica premium totalmente automatizada (ver proyecto planeado).

## Qué demuestra de mis habilidades

- Pipelines multimedia programáticos (Python, Pillow, FFmpeg) de principio a fin
- Diseño de sistemas de consistencia de personajes entre piezas
- Evaluación honesta de calidad: sé exactamente qué le falta y por qué
