# Lab de Triaje de Falsos Positivos en SIEM (Wazuh + n8n + Ollama)

> A home SIEM lab — Kali attacker VM + victim VM with a Wazuh agent — where an n8n workflow triages alerts with a local LLM: hard rules handle true positives, the AI only judges the grey zone, and false-positive reduction is measured.
> Status: ✅ Built; it is the practical base of my master's thesis.

**Estado:** ✅ Construido

## Qué es

Un laboratorio de seguridad completo: una VM atacante (Kali Linux) y una VM víctima con el agente de Wazuh generan alertas reales; un flujo de n8n las clasifica con un modelo de lenguaje local (Ollama) y mide qué porcentaje del ruido (falsos positivos) se puede filtrar sin perder ataques verdaderos.

## El problema que resuelve

Los SOC pierden horas revisando alertas que no son ataques. La pregunta práctica — y la de mi tesis — es: ¿cuánto de ese ruido puede triar un sistema con IA local, gratis y sin enviar datos fuera, manteniendo la seguridad de que ningún verdadero positivo se descarte por error del modelo?

## Arquitectura y stack

- **Wazuh** como SIEM (manager + agente en la VM víctima)
- **VMware Workstation**: VM Kali (atacante) + VM víctima instrumentada
- **n8n**: recibe las alertas, aplica la lógica de triaje y registra resultados
- **Ollama local** (llama3.2) como clasificador de la zona gris
- **Reglas duras** (listas y condiciones deterministas) para los verdaderos positivos conocidos: la IA **nunca** decide sobre ellos

## Paso a paso: cómo se construyó

1. Monté el laboratorio virtual: red interna en VMware, VM víctima con agente Wazuh reportando al manager, VM Kali como fuente de ataques controlados.
2. Generé tráfico de ataque y de uso normal para producir un conjunto de alertas reales y etiquetables (verdadero/falso positivo).
3. Diseñé la política de triaje en dos capas: reglas duras primero (todo lo que coincide con patrones de ataque confirmado se escala siempre), IA solo para la zona gris.
4. Construí el flujo en n8n: ingesta de la alerta → aplicación de reglas → si cae en zona gris, consulta a Ollama local con el contexto de la alerta → veredicto y registro.
5. Definí la métrica antes de medir: % de reducción de falsos positivos y conteo de verdaderos positivos afectados (la meta es cero).
6. Ejecuté rondas de ataque/defensa, revisé los veredictos del modelo contra mi propio etiquetado y ajusté el prompt y las reglas con los desacuerdos.
7. Documenté el procedimiento para reutilizarlo como base práctica de la tesis.

## Estado real

✅ Laboratorio y clasificador construidos y funcionando en mi PC. Es la base práctica de mi tesis de maestría (tema de optimización de SIEM con detección de anomalías por IA).

## Qué demuestra de mis habilidades

- Despliegue y operación de un SIEM real (Wazuh) en laboratorio
- Diseño de triaje SOC con criterios de seguridad: la IA asesora, las reglas mandan
- Medición honesta de resultados (métrica definida antes de ejecutar)
- Integración SIEM → automatización (n8n) → IA local (Ollama)
