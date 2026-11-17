# App de Gastos de la Casa

> A household expense web app on Cloudflare Pages + Supabase with per-person login: it auto-registers expenses from the bank notification emails that arrive in the inbox (with deduplication) and supports manual cash entries, on a configurable monthly cycle.
> Status: ✅ Built, published and in daily family use.

**Estado:** ✅ Construido

## Qué es

Una aplicación web privada para controlar los gastos de mi casa: cada persona entra con su propio login, los gastos bancarios se registran solos a partir de las notificaciones que el banco envía por correo, y el efectivo se captura a mano o por foto de la factura. Todo suma por categoría y por ciclo mensual.

## El problema que resuelve

En mi casa los gastos se anotaban a mano (o no se anotaban) y nadie sabía en qué se iba el dinero. Los bancos dominicanos no ofrecen API para esto, pero sí envían notificaciones por correo de cada consumo: esa fue la fuente de datos.

## Arquitectura y stack

- **Cloudflare Pages** para la publicación de la app
- **Supabase** (plan gratuito) como base de datos y autenticación, con acceso restringido a las cuentas de la casa
- **Registro automático**: los resúmenes de correo procesan las notificaciones bancarias nuevas y las insertan con **deduplicación** (ningún gasto se cuenta dos veces)
- Reglas de negocio reales: ciclo que empieza el día 4, categorías fijas (luz, internet, súper, gasolina, medicamentos, etc.) y reglas de atribución por tarjeta
- Captura manual para efectivo y movimientos sin correo

## Paso a paso: cómo se construyó

1. Definí el modelo con mi hermana: quién registra, qué categorías existen, cuándo empieza el ciclo y qué gastos son fijos.
2. Creé el proyecto en Supabase (tablas de gastos, usuarios) y la app con login por persona y bloqueo de registro a cuentas ajenas.
3. Publiqué la app en Cloudflare Pages con su propia dirección.
4. Configuré el filtro de correo para que las notificaciones bancarias llegaran a un solo buzón procesable.
5. Construí el registro automático: cada resumen de correo revisa notificaciones nuevas, las normaliza (monto, comercio, categoría) y las inserta evitando duplicados.
6. Añadí la captura manual (efectivo, fotos de facturas) y la vista mensual por categoría.
7. Lo pusimos en uso real y corregí con datos verdaderos: movimientos que faltaban, reversos bancarios que debían anular su cargo y reglas de atribución por tarjeta.

## Estado real

✅ Construida, publicada y en uso diario en mi casa. La captura automática cubre los movimientos con notificación por correo; el efectivo sigue siendo manual por diseño.

## Qué demuestra de mis habilidades

- Aplicación web completa: autenticación, base de datos, reglas de negocio y publicación
- Automatización sobre fuentes imperfectas (correos bancarios) con deduplicación
- Iteración con usuarios reales y datos reales, no con ejemplos de juguete
