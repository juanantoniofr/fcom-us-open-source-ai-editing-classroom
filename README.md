# Repositorio de la Facultad de Comunicación para el Aula de Edición Digital Asistida por IA

Repositorio de documentación y planificación del **Aula de Edición Digital Asistida por IA** de la Facultad de Comunicación de la Universidad de Sevilla.

El objetivo del proyecto es definir y desplegar un entorno académico y docente para edición digital asistida por IA, con infraestructura propia, software libre, control institucional de los datos y criterios de operación sostenibles.

## Estructura del repositorio

| Carpeta / archivo                                                                    | Objetivo                                                                                                           |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------ |
| [AI_Assisted_Digital_Editing_Classroom.md](AI_Assisted_Digital_Editing_Classroom.md) | Documento maestro de referencia con la visión general y enlaces al resto de materiales.                            |
| [CONTRIBUTING.md](CONTRIBUTING.md)                                                   | Guía para contribuir al repositorio, con política de ramas, revisión por pares y proceso de alta de colaboradores. |
| [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)                                             | Normas de conducta para la comunidad del proyecto.                                                                 |
| [governance/](governance)                                                            | Gobernanza del proyecto: roles, comité de IA, gobierno del dato y cumplimiento.                                    |
| [documentation/](documentation)                                                      | Documentación técnica y operativa: arquitectura, despliegue y mantenimiento.                                       |
| [roadmap/](roadmap)                                                                  | Planificación por fases y evolución del proyecto.                                                                  |
| [education/](education)                                                              | Material orientado a adopción docente, formación y uso educativo.                                                  |
| [references/](references)                                                            | Referencias de stack, estándares y criterios técnicos.                                                             |
| [images/](images)                                                                    | Recursos gráficos y elementos visuales del proyecto.                                                               |
| [.github/](.github)                                                                  | Plantillas y automatización específica de GitHub.                                                                  |

## Visión general

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

## Estado

Este repositorio contiene una propuesta de roadmap y documentación asociada. No incluye todavía implementación de software ni despliegues automáticos.
