# Lab Observabilidad — Prometheus + Grafana sobre mi clúster k3d

**Estado:** 💡 Guía lista — pendiente de ejecutar

## Objetivo

Darle ojos a mi clúster local de Kubernetes: instalar **Prometheus** para recolectar métricas y **Grafana** para visualizarlas, con un dashboard útil (CPU/memoria por pod, reinicios, estado de nodos) y una alerta configurada que se dispare de verdad durante el lab.

## Habilidad de vacante que prueba

"Monitoreo y observabilidad: Prometheus, Grafana, Kubernetes" — combinación que aparece en roles de infraestructura, SRE junior y soporte de plataformas.

## Prerrequisitos

- Mi clúster **k3d** operativo (ver [proyecto de aprendizaje de Kubernetes](../../aprendizaje-kubernetes-k3d/))
- Helm instalado y acceso a internet para los charts
- Una aplicación de prueba desplegada en el clúster para generar métricas

## Paso a paso

1. Instalar el stack con Helm (kube-prometheus-stack) en un namespace de monitoreo.
2. Verificar que Prometheus está recolectando: consultar targets y ejecutar 3 consultas PromQL básicas (uso de CPU por pod, memoria, reinicios).
3. Entrar a Grafana, conectar el datasource de Prometheus (ya aprovisionado por el chart) y abrir los dashboards incluidos.
4. Construir **mi propio dashboard**: paneles de CPU y memoria por pod, reinicios por deployment y estado general del clúster.
5. Provocar un evento observable: escalar una app, matar pods en bucle (CrashLoopBackOff deliberado) y observar el evento en las métricas.
6. Configurar una **alerta** (ej.: pod reiniciándose repetidamente o CPU sostenida alta), provocarla y documentar su disparo y su resolución.
7. Exportar el dashboard como JSON y guardarlo como evidencia versionable.

## Entregable / evidencia final

- Capturas del dashboard propio con datos reales del clúster
- El JSON exportado del dashboard y las 3+ consultas PromQL documentadas
- Captura de la alerta disparada y resuelta, con la regla escrita por mí

## Tiempo estimado

3–4 horas (1–2 sesiones)
