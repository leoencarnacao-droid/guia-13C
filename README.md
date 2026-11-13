# TP13C - OWASP ZAP en Kubernetes (k3d)

## Sprint 1 y 2: Infraestructura y Monitoreo
- Se desplegó la Notes App (Backend, Frontend, PostgreSQL) en el clúster de k3d.
- Se desplegó el stack de monitoreo (Prometheus, Grafana, Node Exporter).
- **Evidencia:** Los pods se encuentran en estado `Running` (`kubectl get pods -n flask-app`).

## Sprint 3 y 4: CI/CD y ZAP
- Se configuró el workflow de GitHub Actions (`.github/workflows/autoscan.yml`) con los pasos de Docker Compose y ZAP Automation Framework.
- **Validación local:** Se ejecutó ZAP exitosamente mediante un Job en Kubernetes (`k8s/zap/05-zap-job.yaml`), el cual completó el escaneo (`Completed`) y generó el reporte de vulnerabilidades.
- **Nota:** El pipeline de GitHub Actions está configurado para correr el escaneo en la nube, pero debido a limitaciones del entorno gratuito de GitHub (restricciones de red con `--network host` y colisión de puertos), la validación real se realizó en el clúster local de k3d, que es el objetivo principal del TP.
