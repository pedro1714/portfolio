# Ganalaloto — Estadísticas de la Lotería Dominicana

> A statistics page for the Dominican lottery built from historical draw data: number frequencies, most common pairs and overdue numbers, generated automatically from the dataset.
> Status: ✅ Built and published.

**Estado:** ✅ Construido

## Qué es

Una página web de estadísticas de la lotería dominicana: a partir de datos históricos de sorteos calcula frecuencias por número, pares más frecuentes y números "atrasados" (los que llevan más sorteos sin salir), y presenta todo en una página clara y consultable desde el teléfono.

## El problema que resuelve

Los jugadores consultan estadísticas dispersas, desactualizadas o mezcladas con predicciones engañosas. Ganalaloto presenta solo estadística descriptiva real, calculada desde los datos: qué ha salido, con qué frecuencia y hace cuánto no sale — sin prometer predicciones.

## Arquitectura y stack

- Procesamiento de datos históricos de sorteos (limpieza y normalización)
- Cálculo de frecuencias, pares y atrasos
- Página web estática generada desde los resultados

## Paso a paso: cómo se construyó

1. Recopilé y normalicé el histórico de resultados en un formato único y consultable.
2. Escribí el cálculo de frecuencias individuales y validé los conteos contra muestras manuales.
3. Añadí el análisis de pares (combinaciones de dos números que más se repiten juntas).
4. Añadí el cálculo de atrasos: sorteos transcurridos desde la última aparición de cada número.
5. Generé la página con los resultados ordenados para consulta rápida desde el móvil.
6. Dejé el proceso reproducible: con datos nuevos, se recalcula y se regenera la página.

## Estado real

✅ Construida y publicada. Es estadística descriptiva: no predice resultados ni lo pretende.

## Qué demuestra de mis habilidades

- Limpieza y análisis de datos históricos con fines prácticos
- Generación de páginas estáticas desde datos
- Producto completo: de la idea a la página publicada
