# Lab Tenable Casero — Escaneo de mi laboratorio + Informe de Remediación

**Estado:** 💡 Guía lista — pendiente de ejecutar

## Objetivo

Usar **Tenable** (Nessus Essentials, la edición gratuita) para escanear las máquinas de mi propio laboratorio, interpretar los resultados como lo haría en un trabajo real y producir lo que un cliente o un jefe realmente recibe: un **informe de remediación priorizado** por riesgo, no una lista cruda de hallazgos.

## Habilidad de vacante que prueba

"Gestión de vulnerabilidades con Tenable: escaneo, análisis y remediación priorizada" — la herramienta con la que ya trabajé en el sector financiero, aquí evidenciada sobre mi propio lab.

## Prerrequisitos

- Nessus Essentials (gratuito, hasta 16 IPs) instalado en mi PC o en una VM
- Mi laboratorio: VM víctima, VM Kali y los hosts de práctica disponibles
- Plantilla simple de informe (la creo como parte del lab)

## Paso a paso

1. Instalar y activar Nessus Essentials; actualizar plugins.
2. Descubrimiento: escaneo de descubrimiento sobre la red del laboratorio para inventariar hosts y servicios reales.
3. Preparar una víctima "antes": dejar deliberadamente servicios y configuraciones vulnerables conocidos (versiones viejas, puertos innecesarios) para tener hallazgos reales que remediar.
4. Ejecutar un escaneo de vulnerabilidades completo (con credenciales donde sea posible) sobre el laboratorio.
5. Analizar los resultados: agrupar por host y por criticidad, separar ruido de riesgo real (explotabilidad + exposición + criticidad del activo).
6. Redactar el **informe de remediación priorizado**: por cada hallazgo importante — qué es, por qué importa, cómo se arregla y en qué orden.
7. Remediar los 3 hallazgos principales y **re-escanear** para verificar que desaparecieron (evidencia antes/después).

## Entregable / evidencia final

- El informe de remediación priorizado (documento) con hallazgos reales de mi lab
- Capturas del antes/después de los 3 hallazgos remediados (escaneo inicial vs re-escaneo limpio)
- La plantilla de informe reutilizable para futuros trabajos de consultoría

## Tiempo estimado

3–5 horas (en 2 sesiones)
