# fcom-us-open-source-ai-editing-classroom

Repositorio de documentación y planificación para el proyecto **Aula de Edición Digital Asistida por IA Open Source** de la Facultad de Comunicación de la Universidad de Sevilla.

El objetivo del proyecto es definir y desplegar un entorno académico y docente para edición digital asistida por IA, con infraestructura propia, software libre, control institucional de los datos y criterios de operación sostenibles.

## Contenido del repositorio

- [AI_Assisted_Digital_Editing_Classroom.md](AI_Assisted_Digital_Editing_Classroom.md): documento principal con el roadmap, la arquitectura de referencia, la gobernanza, los riesgos y el plan de adopción.
- [README.md](README.md): resumen de navegación del proyecto.

## Resumen del proyecto

El roadmap propone una implantación gradual en fases:

1. Descubrimiento y definición del alcance.
2. Diseño técnico y de seguridad.
3. Puesta en marcha de la plataforma base.
4. Piloto docente con asignaturas seleccionadas.
5. Producción inicial del servicio.
6. Escalado y mejora continua.

La propuesta se apoya en una arquitectura open source que combina:

- Cómputo Linux con recursos CPU/GPU.
- Kubernetes para orquestación.
- Motores de inferencia como vLLM, Ollama o TGI.
- MLflow y MinIO para gestión de artefactos.
- PostgreSQL, Redis y buscadores vectoriales para datos y recuperación semántica.
- Keycloak, Kong o Traefik para control de acceso y exposición de servicios.
- Prometheus, Grafana, Loki y Alertmanager para observabilidad.

## Principios

- Soberanía tecnológica sobre infraestructura, modelos y datos.
- Uso de componentes open source siempre que sea viable.
- Privacidad por defecto y cumplimiento normativo.
- Crecimiento progresivo según uso real y resultados del piloto.
- Operación profesional con procedimientos, monitorización y soporte definidos.

## Destinatarios

- Dirección académica y equipos docentes de la Facultad de Comunicación.
- Servicio de Informática responsable de la operación técnica.
- Personal de administración, legal y protección de datos.
- Estudiantes y profesorado que participen en los pilotos.

## Documento principal

Si quieres ver el detalle completo del planteamiento, consulta el documento principal:

- [AI_Assisted_Digital_Editing_Classroom.md](AI_Assisted_Digital_Editing_Classroom.md)

## Estado

Este repositorio contiene una propuesta de roadmap y documentación asociada. No incluye todavía implementación de software ni despliegues automáticos.
