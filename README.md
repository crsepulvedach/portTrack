#PortTrack Monitoring Setup
##Estructura del Repositorio
-`monitoring/prometheus/prometheus.yml`: Configuración de Prometheus para la recolección de métricas.
-`monitoring/grafana/`: Carpeta que contiene la configuración de Grafana.
  -`provisioning/datasources.yml`: Configuración de la fuente de datos para Grafana.
  -`provisioning/dashboards.yml`: Configuración para la carga automática de dashboards.
  -`dashboards/example-dashboard.json`: Un ejemplo de dashboard para visualizar métricas.

##Prometheus
1.Configura tu servidor Prometheus apuntando a `monitoring/prometheus/prometheus.yml`.
2.Asegúrate de tener exporters corriendo en las instancias que deseas monitorizar.

##Grafana
1.Crea un nuevo datasource en Grafana utilizando `monitoring/grafana/provisioning/datasources.yml`.
2.Configura Grafana para cargar automáticamente los dashboards desde la carpeta especificada.