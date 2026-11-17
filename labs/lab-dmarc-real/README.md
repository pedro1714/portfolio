# Lab DMARC Real — SPF/DKIM/DMARC hasta p=reject con reportes rua

**Estado:** 💡 Guía lista — pendiente de ejecutar

## Objetivo

Desplegar la autenticación completa de correo en un **dominio de práctica** propio, recorriendo el camino real y seguro: SPF y DKIM correctos, DMARC en `p=none` con reportes **rua**, análisis de los reportes, y endurecimiento progresivo hasta **`p=reject`**.

## Habilidad de vacante que prueba

Es exactamente la habilidad de mi Gig 1 de Fiverr y de los trabajos de email security en Upwork: "SPF/DKIM/DMARC implementation & monitoring". Este lab produce la evidencia práctica de ese servicio.

## Prerrequisitos

- Un dominio de práctica barato registrado a mi nombre, con control total de su DNS
- Una cuenta de correo real enviando desde ese dominio (buzón del propio dominio o un servicio de envío)
- Acceso a herramientas públicas de verificación (registros DNS y analizadores de reportes DMARC)

## Paso a paso

1. Inventariar los remitentes legítimos del dominio: quién envía correo "desde" él (buzón, web, servicios).
2. Publicar el registro **SPF** con solo esos remitentes y verificarlo con una consulta DNS y un correo de prueba.
3. Activar **DKIM** en el emisor y publicar la llave pública; enviar correo de prueba y confirmar `DKIM=pass`.
4. Publicar **DMARC en `p=none`** con dirección `rua` a un buzón propio para recibir reportes agregados.
5. Esperar y **analizar los reportes rua** (XML): identificar fuentes legítimas olvidadas y fuentes de suplantación.
6. Corregir lo que los reportes revelen (alinear SPF/DKIM de cada fuente legítima).
7. Subir la política por etapas: `p=quarantine` (con % creciente) y, con reportes limpios, **`p=reject`**.
8. Prueba final: intentar enviar correo suplantado desde un servicio externo y documentar que es rechazado.

## Entregable / evidencia final

- Capturas de los registros DNS en cada etapa (SPF, DKIM, DMARC none→quarantine→reject)
- Un reporte rua real analizado, con mis conclusiones escritas
- Captura de la prueba de suplantación rechazada con `p=reject`
- Checklist reutilizable del procedimiento (base documental de mi servicio de consultoría de correo)

## Tiempo estimado

3–4 horas de trabajo activo + días de espera entre etapas por los ciclos de reporte (24–72 h por etapa)
