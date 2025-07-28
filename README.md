# ✨ **PortTrack Monitoring Setup**
## **Estructura del Repositorio**
- `monitoring/prometheus/prometheus.yml`: Configuración de Prometheus para la recolección de métricas.
- `monitoring/grafana/`: Carpeta que contiene la configuración de Grafana.
  - `provisioning/datasources.yml`: Configuración de la fuente de datos para Grafana.
  - `provisioning/dashboards.yml`: Configuración para la carga automática de dashboards.
  - `dashboards/example-dashboard.json`: Un ejemplo de dashboard para visualizar métricas.

## **Prometheus**
1. Configura tu servidor Prometheus apuntando a `monitoring/prometheus/prometheus.yml`.
2. Asegúrate de tener exporters corriendo en las instancias que deseas monitorizar.

## **Grafana**
1. Crea un nuevo datasource en Grafana utilizando `monitoring/grafana/provisioning/datasources.yml`.
2. Configura Grafana para cargar automáticamente los dashboards desde la carpeta especificada.

```mermaid
graph TD;
    A[Usuario Final] -->|Acceso via Web| B[Load Balancer]
    B -->|Redirige tráfico| C[EC2 Instances]
    C -->|Se comunica con| D[Microservicios]
    D -->|Almacena datos en| E[Base de Datos (RDS)]
    C -->|Monitorea estado en| F[Prometheus]
    F -->|Visualiza métricas en| G[Grafana]
    H[GitHub Actions] -->|Despliega a| C
    C -->|Despliega usando| I[AWS CodeDeploy]
    
    subgraph Seguridad
        J[AWS Secrets Manage r]
        K[Control de acceso IAM]
    end
    D -->|Gestiona secretos| J
    J -->|Acceso controlado| K
```
   