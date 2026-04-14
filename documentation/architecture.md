# Arquitectura de Referencia

## Capa de cómputo

Servidores Linux con recursos CPU y GPU para alojar la inferencia y los servicios del aula.

## Orquestación

Kubernetes con Helm para desplegar y gestionar los componentes de la plataforma.

## Inferencia de modelos

Motores como vLLM, Ollama o TGI según el caso de uso, la latencia y el tipo de modelo.

## Datos y artefactos

- PostgreSQL para datos estructurados.
- Redis para caché.
- MLflow y MinIO para artefactos y seguimiento.
- OpenSearch, Qdrant o Weaviate para búsqueda y recuperación semántica.

## Acceso y exposición

- Keycloak para SSO y control de identidades.
- Kong o Traefik como gateway de entrada.

## Observabilidad

- Prometheus.
- Grafana.
- Loki.
- Alertmanager.

## Integración académica

La plataforma se consume desde el LMS y desde interfaces web internas orientadas a la docencia y la producción académica.
