# Lab Seguridad de Webhooks en n8n — HMAC, Secretos y Rate Limiting

**Estado:** 💡 Guía lista — pendiente de ejecutar

## Objetivo

Endurecer los webhooks de mis propios flujos de n8n (revisor ATS, fábricas de imagen/voz) aplicando las tres defensas que un cliente pagaría por tener: **validación de firma HMAC** en las peticiones, **secretos fuera del flujo** (nada de llaves escritas en los nodos) y **rate limiting** básico contra abuso.

## Habilidad de vacante que prueba

"Automatización segura: autenticación de webhooks, gestión de secretos, hardening de integraciones" — diferenciador directo para trabajos de automatización con n8n en Upwork/Fiverr.

## Prerrequisitos

- Mi n8n autohospedado con los flujos actuales (ATS, fábrica de imágenes, fábrica de voz)
- Un cliente HTTP para pruebas (curl o Postman)
- Conocimiento de dónde viven hoy las credenciales de mis flujos (auditoría previa)

## Paso a paso

1. Inventariar mis webhooks actuales: qué recibe cada uno, quién puede llamarlo hoy y qué secretos toca.
2. Elegir un flujo piloto (el revisor ATS) y añadir **validación HMAC**: el llamante firma el cuerpo con un secreto compartido; el flujo recalcula la firma y rechaza cualquier petición que no coincida.
3. Probar los tres casos: firma válida (pasa), firma inválida (rechazada), sin firma (rechazada) — y documentar cada respuesta.
4. Mover cualquier secreto que esté escrito dentro de nodos al almacén de **credenciales de n8n** o a variables de entorno, y verificar que el flujo sigue funcionando sin secretos visibles en el lienzo.
5. Añadir **rate limiting** básico (límite de peticiones por ventana de tiempo por origen) y probarlo con una ráfaga de peticiones.
6. Repetir el patrón (HMAC + secretos + límite) en los demás flujos del inventario.
7. Escribir la guía de "webhook seguro" resultante como plantilla reutilizable para clientes.

## Entregable / evidencia final

- Capturas de las tres pruebas HMAC (válida / inválida / ausente) y de la ráfaga bloqueada por rate limiting
- Inventario antes/después: qué secretos salieron de los flujos y dónde quedaron
- Plantilla escrita "Webhook seguro en n8n" lista para reusar en trabajos de clientes

## Tiempo estimado

2–3 horas (1 sesión)
