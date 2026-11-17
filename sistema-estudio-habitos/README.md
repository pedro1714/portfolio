# Sistema de Seguimiento de Estudio y Hábitos

> Small Python CLI scripts (estudio.py, agua.py, comidas.py) that log my daily study blocks, water intake and meals, and feed honest daily balance reports — no fake percentages, just logged minutes and facts.
> Status: ✅ Built and in daily use.

**Estado:** ✅ Construido

## Qué es

Un sistema personal de registro con tres scripts de Python — `estudio.py`, `agua.py` y `comidas.py` — que anotan mis bloques de estudio (inglés, ciberseguridad, tesis, certificación, sesión de ingresos), mi agua y mis comidas. Con esos datos se genera mi balance diario: qué hice de verdad, medido en minutos registrados.

## El problema que resuelve

Tenía una rutina de estudio de 5 bloques diarios y metas de salud (recomposición corporal), pero sin registro no había forma honesta de saber si cumplía. Las apps genéricas no se adaptaban a mi rutina ni a mi forma de reportar (desde el teléfono, en lenguaje natural).

## Arquitectura y stack

- **Python** (scripts CLI pequeños y directos)
- Registro por categorías fijas de estudio: inglés / coursera / tesis / api-pentester / dinero
- Persistencia local en archivos de datos
- Salidas pensadas para el balance nocturno: minutos por tema, vasos de agua, comidas

## Paso a paso: cómo se construyó

1. Definí las categorías reales de mi rutina (los 5 bloques de estudio y los hábitos de salud) antes de escribir código.
2. Escribí `estudio.py` para registrar minutos por categoría con una interfaz mínima.
3. Añadí `agua.py` y `comidas.py` con la misma filosofía: registrar en segundos, sin fricción.
4. Conecté los registros al balance diario: el reporte lee los datos y presenta lo hecho, sin porcentajes inventados ni "estimaciones".
5. Lo integré a mi rendición de cuentas diaria: el balance contrasta lo planeado con lo registrado.

## Estado real

✅ Construido y en uso diario. Es deliberadamente simple: tres scripts que hacen una cosa bien y alimentan un reporte honesto.

## Qué demuestra de mis habilidades

- Python práctico para sistemas personales de registro
- Diseño de herramientas de baja fricción que sí se usan todos los días
- Cultura de medición honesta: datos registrados, no impresiones
