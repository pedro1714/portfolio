# Revisor de CV contra ATS (n8n)

> Two n8n webhooks that take a job posting plus a resume (plain text or PDF) and return keyword coverage and a list of what is missing. Its golden rule: report the gaps, never suggest inventing skills.
> Status: ✅ Built and validated on 8 real resumes (57–92% coverage range).

**Estado:** ✅ Construido

## Qué es

Un servicio de revisión de CV contra sistemas ATS (Applicant Tracking Systems) construido con webhooks en n8n. Un endpoint recibe la vacante y el CV en texto; otro acepta el CV en PDF. Devuelve el porcentaje de cobertura de palabras clave de la vacante y la lista concreta de términos y requisitos que el CV no cubre.

## El problema que resuelve

La mayoría de los CV se descartan por un filtro automático antes de que los vea una persona, simplemente porque no usan el lenguaje de la vacante. Yo necesitaba una herramienta propia para adaptar mis CV a cada vacante real — sin caer en la tentación de "rellenar" con habilidades que no tengo.

## Arquitectura y stack

- **n8n** con dos webhooks: `/webhook/ats-revisor` (texto) y `/webhook/ats-revisor-pdf` (PDF)
- Extracción de texto de PDF dentro del flujo
- Comparación de términos de la vacante contra el contenido del CV
- Regla de oro del sistema: **reporta lo que falta; jamás sugiere inventar una habilidad**

## Paso a paso: cómo se construyó

1. Definí la entrada mínima viable: texto de la vacante + texto del CV, y la salida: cobertura % + lista de faltantes accionables.
2. Construí el webhook de texto y la lógica de comparación de palabras clave (términos simples y frases compuestas de la vacante).
3. Agregué el segundo webhook con extracción de texto desde PDF, porque los CV reales llegan en PDF.
4. Escribí la regla de honestidad dentro del propio diseño del reporte: cada faltante se presenta como "esto pide la vacante y tu CV no lo muestra" — la decisión de si es verdad o no es del dueño del CV.
5. Validé el sistema con 8 CV reales adaptados a vacantes reales (formato Harvard, una página): las coberturas resultantes estuvieron entre 57% y 92%, y cada reporte se usó para corregir el CV correspondiente.
6. Lo dejé accesible desde mi teléfono vía mi red privada, para revisar una vacante en el momento en que aparece.

## Estado real

✅ Construido y validado con 8 CV reales. Depende de mi n8n local: si mi PC está apagada, el webhook no responde (limitación conocida y aceptada; la revisión también se puede hacer manualmente con el mismo criterio).

## Qué demuestra de mis habilidades

- Construcción de servicios útiles con webhooks y procesamiento de documentos
- Criterio ATS real: cobertura de palabras clave medida, no adivinada
- Ética aplicada al diseño: una herramienta que ayuda sin fabricar credenciales
