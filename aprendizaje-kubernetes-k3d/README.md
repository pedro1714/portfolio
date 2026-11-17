# Aprendizaje de Kubernetes con k3d

> A guided Kubernetes learning path on a local k3d cluster running on my own PC — workloads, services and troubleshooting practiced in small labs, with Prometheus/Grafana observability planned inside the cluster.
> Status: 🔄 In progress.

**Estado:** 🔄 En curso

## Qué es

Mi ruta práctica de Kubernetes sobre un clúster local **k3d** (Kubernetes ligero en Docker) montado en mi PC. Trabajo por laboratorios cortos y guiados: desplegar, exponer, romper y arreglar, entendiendo el porqué de cada pieza antes de pasar a la siguiente.

## El problema que resuelve

Kubernetes aparece en vacantes de infraestructura y seguridad, pero aprenderlo solo con teoría no deja habilidad real. Un clúster local gratuito me permite practicar con consecuencias cero y repetir cada lab hasta dominarlo.

## Arquitectura y stack

- **k3d** sobre Docker en mi PC (Ryzen, 64 GB RAM)
- kubectl, manifiestos YAML
- En la ruta: **Prometheus + Grafana** dentro del clúster (ver [Lab de Observabilidad](../labs/lab-observabilidad-k3d/))

## Paso a paso: cómo se está construyendo

1. Instalé Docker y k3d y levanté el primer clúster local de un nodo.
2. Recorrí los objetos base con práctica: Pods, Deployments, Services y su comunicación.
3. Trabajé con manifiestos YAML versionados en lugar de solo comandos imperativos.
4. Practiqué fallos deliberados (borrar pods, escalar a cero, manifiestos con errores) y su diagnóstico con `kubectl`.
5. En curso: configuración (ConfigMaps/Secrets), persistencia y la capa de observabilidad.

## Estado real

🔄 En curso: clúster operativo y fundamentos practicados; observabilidad y temas avanzados pendientes en la ruta.

## Qué demuestra de mis habilidades

- Fundamentos de Kubernetes con práctica real en clúster propio
- Método de aprendizaje por laboratorios con fallos controlados
