# Equipo Personal de Agentes en VPS (OpenClaw + Hermes)

> A planned personal agent team: OpenClaw and Hermes agents hosted on an always-free VPS, working in shifts under central direction with n8n as the control board — ideas come in by chat, tasks run in turns.
> Status: 💡 Planned — idea designed, not yet built. Nothing in this file is presented as done.

**Estado:** 💡 Planeado (idea diseñada, aún no existe)

## Qué es (la idea)

Un equipo personal de agentes de IA corriendo 24/7 en un VPS gratuito (Oracle Always Free, con Hetzner como plan B): agentes con roles distintos (OpenClaw y Hermes) que trabajan **por turnos bajo una dirección central**, reciben ideas por chat y usan **n8n como tablero** de tareas y estado.

## El problema que resolvería

Mis agentes y automatizaciones actuales viven en mi PC: cuando la PC se apaga, el equipo se apaga. Un VPS siempre encendido les daría continuidad real, y una estructura por turnos con tablero evitaría que varios agentes pisen el mismo trabajo.

## Arquitectura planeada

- **VPS** (Oracle Always Free ARM; plan B: Hetzner CX32)
- **OpenClaw + Hermes** como agentes del equipo
- **n8n** como tablero central de tareas y coordinación
- Acceso y administración por SSH con llaves

## Paso a paso planeado

1. Crear la instancia del VPS e instalar el acceso SSH por llaves.
2. Montar n8n en el VPS como tablero central.
3. Instalar y configurar los agentes con roles definidos.
4. Definir el sistema de turnos y de entrega de tareas por chat.
5. Migrar primero una tarea pequeña y medible; luego escalar.

## Estado real

💡 Planeado: la decisión de plataforma está tomada y el diseño existe; la instancia aún no está creada. El paso que falta es de infraestructura (crear la red/instancia en la consola del proveedor).

## Qué demostrará de mis habilidades

- Orquestación multi-agente con coordinación y tableros
- Administración de servidores Linux en la nube (VPS, SSH, servicios)
