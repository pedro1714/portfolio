# Fábrica de Contenido con IA (n8n)

> An n8n content factory: image generation through gen.pollinations.ai (flux.1-schnell, authenticated) with a character-sheet flow for consistent characters, plus a voice factory (Python container + edge-TTS) exposed by webhook.
> Status: ✅ Built; it produces the images and voices used by my animated video pipeline.

**Estado:** ✅ Construido

## Qué es

Una fábrica de contenido en n8n con dos líneas de producción: **imágenes** generadas por IA con personajes consistentes entre escenas, y **voces** sintetizadas bajo demanda. Ambas se consumen por webhook, así que cualquier otro flujo (o yo mismo desde el teléfono) puede pedir "una imagen de este personaje haciendo esto" o "narra este texto" y recibir el archivo.

## El problema que resuelve

Generar contenido con IA herramienta por herramienta es lento e inconsistente: los personajes cambian de cara entre imágenes y cada voz toca generarla a mano. La fábrica centraliza ambas cosas con una interfaz única y personajes definidos una sola vez.

## Arquitectura y stack

- **n8n**: flujos `Fabrica - Imagenes` (`/webhook/imagen`) y `Fabrica - Voz` (`/webhook/voz`)
- **gen.pollinations.ai** con autenticación Bearer y modelo **flux.1-schnell** (la ruta gratuita sin autenticar producía caras deformes; se descartó para producción)
- **Flujo de hoja de personaje**: una descripción fija y detallada del personaje se inyecta en cada prompt de escena para mantener consistencia visual
- **Fábrica de voz**: contenedor Python con **edge-tts** (puerto interno 5050); voces es-DO-EmilioNeural (dominicana), es-MX-DaliaNeural y otras de catálogo
- Las llaves viven **solo** en las credenciales de n8n, nunca en archivos ni en este repositorio

## Paso a paso: cómo se construyó

1. Probé la ruta gratuita de generación de imágenes y la descarté con evidencia: calidad insuficiente para producción (caras deformes).
2. Re-enruté el flujo de imágenes a gen.pollinations.ai con encabezado de autenticación y flux.1-schnell, con la llave guardada como credencial de n8n.
3. Creé el sistema de hoja de personaje: ficha fija por personaje (rasgos, ropa, estilo) que el flujo antepone a cada escena solicitada.
4. Para la voz, el primer intento con un nodo de Node.js falló de forma persistente; lo reemplacé por un contenedor Python dedicado con edge-tts y un endpoint HTTP simple.
5. Expuse ambas fábricas por webhooks de n8n con parámetros claros (personaje + escena; texto + voz).
6. Verifiqué la consistencia generando series de escenas del mismo personaje y episodios narrados completos con distintas voces.

## Estado real

✅ Construida y en uso: alimenta el pipeline de video animado (ver proyecto [Pipeline de Video Animado con IA](../pipeline-video-animado-ia/)). Corre en mi PC; si está apagada, la fábrica no responde.

## Qué demuestra de mis habilidades

- Evaluación de proveedores de IA con criterio de calidad medido, no por moda
- Diseño de sistemas de consistencia de personajes para generación de imágenes
- Servicios de voz/imagen desacoplados y reutilizables vía webhooks
- Manejo seguro de credenciales (solo dentro de n8n)
