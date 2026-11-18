# Checklist de seguridad de correo: SPF, DKIM y DMARC

**Por Pedro Gomez** — Analista de Seguridad de la Información · [Portafolio](https://github.com/pedro1714/portfolio) · [LinkedIn](https://www.linkedin.com/in/pedro-gomezbernabel)

Si tu empresa envía correos con su propio dominio y no tiene estos tres registros bien puestos, cualquiera puede enviar correos *como si fuera tu empresa* (suplantación/phishing) y tus correos legítimos caen en spam. Esta es la lista que uso para corregirlo, paso a paso.

## 0. Antes de tocar nada
- [ ] Inventario: lista TODOS los servicios que envían correo con tu dominio (Google Workspace/Microsoft 365, la web, el CRM, la plataforma de facturación, marketing, la tienda…).
- [ ] Acceso al DNS del dominio (sin acceso al DNS no se puede hacer nada).
- [ ] Anota los registros TXT actuales: nunca borres un registro que no entiendas.

## 1. SPF — quién puede enviar con tu dominio
- [ ] Un solo registro SPF por dominio (dos registros SPF = SPF roto).
- [ ] Incluye SOLO los servicios del inventario (`include:` por servicio).
- [ ] Termina en `-all` (rechazo duro) cuando todo esté verificado; mientras tanto `~all`.
- [ ] Revisa el límite de 10 consultas DNS (si te pasas, SPF falla en silencio).
- [ ] Verifica subdominios que envían (ej. `mail.tudominio.com`) por separado.

## 2. DKIM — firma criptográfica de cada correo
- [ ] Activa DKIM en CADA servicio del inventario (cada uno tiene su selector).
- [ ] Llaves de 2048 bits (1024 ya no es aceptable).
- [ ] Publica el registro TXT del selector y confirma que el servicio quedó "autenticando".
- [ ] Envía un correo de prueba a una cuenta externa y confirma `dkim=pass` en las cabeceras.

## 3. DMARC — la política y los reportes
- [ ] Publica DMARC en modo monitoreo: `v=DMARC1; p=none; rua=mailto:dmarc@tudominio.com`.
- [ ] Lee los reportes (rua) durante 2–4 semanas: ahí aparecen los servicios olvidados y los intentos de suplantación.
- [ ] Corrige alineación: el dominio visible (From) debe alinearse con SPF y/o DKIM.
- [ ] Sube la política por etapas: `p=quarantine` (empieza con `pct=10`) → `p=reject` al 100%.
- [ ] Publica también DMARC para subdominios que NO envían correo (p=reject) — son la puerta favorita de los suplantadores.

## 4. Errores que veo todo el tiempo
- Dos registros SPF "porque dos proveedores lo pidieron".
- DKIM activo en el correo principal pero no en la tienda/CRM.
- DMARC en `p=none` para siempre: eso es solo mirar, no protege.
- Nadie lee los reportes rua (ahí está la evidencia de quién te está suplantando).

## 5. Verificación final
- [ ] Desde una cuenta externa: `spf=pass`, `dkim=pass`, `dmarc=pass` en las cabeceras.
- [ ] Prueba de suplantación controlada desde un servicio externo: debe ser rechazada con `p=reject`.
- [ ] Documenta los registros finales y quién es dueño de cada servicio autorizado.

---
¿Quieres que lo deje funcionando en tu empresa sin tocar tú el DNS? Es mi servicio de **seguridad de correo SPF/DKIM/DMARC** (Fiverr/Upwork) o escríbeme por LinkedIn. Comenta **DMARC** en cualquiera de mis posts y te ayudo a revisar tu dominio.
