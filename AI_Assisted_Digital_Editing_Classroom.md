<div align="center">
    <br /><br />
    <h1>Universidad de Sevilla</h1>
    <h2>Servicio de Informática.</h2>
    <h3> Facultad de Comunicación</h3>
    <img src="./images/logo_us.png" alt="Logo Universidad de Sevilla" width="250" />
    <br />
    <hr />
    <br />
    <h1>Roadmap</h1>
    <h2>Proyecto Aula de Edición Digital Asistida por IA Open Source</h2>
    <br />
    <hr />
    <br />
    <br /><br />
</div>

## Control de Versiones

| Versión |   Fecha    | Autor                       | Descripción del Cambio                                                                                                           |
| :-----: | :--------: | :-------------------------- | :------------------------------------------------------------------------------------------------------------------------------- |
| **1.0** | 13/03/2026 | Juan Antonio Fernández Ruiz | Creación del informe para documentar el Roadmap del proyecto para montar un Aula de Edición Digital Asistida por IA Open Source. |

<br /><br /><br /><br />

<div align="right" >
    <p><strong>Autor:</strong><br />
    Juan Antonio Fernández Ruiz<br />
</div>

<div style={{ pageBreakAfter: 'always' }}></div>

## Tabla de Contenidos

1. [Objetivo y alcance](#1-objetivo-y-alcance)
2. [Principios de diseño](#2-principios-de-diseño)
3. [Gobernanza y roles](#3-gobernanza-y-roles)
4. [Roadmap por fases](#4-roadmap-por-fases)
5. [Arquitectura de referencia](#5-arquitectura-de-referencia)
6. [Catálogo inicial de modelos](#6-catálogo-inicial-de-modelos)
7. [Seguridad, cumplimiento y riesgo](#7-seguridad-cumplimiento-y-riesgo)
8. [Operación y mantenimiento](#8-operación-y-mantenimiento)
9. [KPIs de éxito](#9-kpis-de-éxito)
10. [Plan de adopción y formación](#10-plan-de-adopción-y-formación)
11. [Riesgos clave y mitigación](#11-riesgos-clave-y-mitigación)
12. [Hitos de decisión](#12-hitos-de-decisión)

<div style={{ pageBreakAfter: 'always' }}></div>

## 1. Objetivo y alcance

Implementar un entorno docente y de producción académica para edición digital asistida por IA (texto, audio, imagen y vídeo) con control institucional de datos, seguridad, costes y continuidad de servicio.

**Modelo operativo:** infraestructura autoalojada, stack 100% Open Source, operación y mantenimiento a cargo del Servicio de Informática.

## 2. Principios de diseño

1. **Soberanía tecnológica:** modelos y datos en infraestructura propia.
2. **Open Source end-to-end:** sistema operativo, orquestación, inferencia, observabilidad y herramientas de aula.
3. **Privacidad por defecto:** cumplimiento RGPD/LOPDGDD, minimización de datos y trazabilidad.
4. **Escalabilidad gradual:** empezar con piloto controlado y ampliar por demanda real.
5. **Operación profesional:** SRE/DevOps del Servicio de Informática con SLAs definidos.

## 3. Gobernanza y roles

| Rol                               | Responsable principal          | Función                                                      |
| --------------------------------- | ------------------------------ | ------------------------------------------------------------ |
| Dirección académica del proyecto  | Facultad de Comunicación       | Priorizar casos de uso docentes e investigación              |
| Puesta en producción y operación  | Servicio de Informática FCom   | Arquitectura, despliegue, seguridad, monitorización, soporte |
| Oficina legal/protección de datos | Universidad                    | Evaluación jurídica, DPIA, bases de tratamiento              |
| Coordinación docente              | Facultad                       | Diseño pedagógico, adopción y formación                      |
| Comité de IA                      | Facultad + Informática + Legal | Aprobación de modelos, políticas de uso y revisión ética     |

## 4. Roadmap por fases (12 meses)

| Fase                           | Duración  | Objetivo                            | Entregables                                                                       | Criterio de salida              |
| ------------------------------ | --------- | ----------------------------------- | --------------------------------------------------------------------------------- | ------------------------------- |
| F0. Descubrimiento             | 4 semanas | Definir alcance y riesgos           | Catálogo de casos de uso, mapa de datos, requisitos técnicos y legales            | Aprobación del comité           |
| F1. Diseño técnico y seguridad | 6 semanas | Diseñar arquitectura objetivo       | Diseño de red, IAM, cifrado, backup, observabilidad, SLOs, runbooks               | Diseño validado por Informática |
| F2. Plataforma base            | 8 semanas | Levantar infraestructura core       | Kubernetes/virtualización, almacenamiento, registro de modelos, gateway IA, CI/CD | Entorno preproducción operativo |
| F3. Piloto docente             | 8 semanas | Validar en cursos seleccionados     | 2-3 asignaturas piloto, métricas de uso, feedback docente/estudiantes             | KPI mínimos cumplidos           |
| F4. Producción inicial         | 8 semanas | Abrir servicio institucional        | Portal de autoservicio, soporte N1/N2, catálogo inicial de modelos                | SLA en verde 30 días            |
| F5. Escalado y mejora continua | Continuo  | Optimizar coste, calidad y adopción | FinOps, retraining/evaluación periódica, ampliación de casos de uso               | Revisión trimestral aprobada    |

## 5. Arquitectura de referencia (Open Source)

1. **Capa de cómputo:** servidores CPU/GPU Linux (Ubuntu Server o Rocky Linux).
2. **Orquestación:** Kubernetes (k3s o kubeadm) + Helm.
3. **Inferencia de modelos:** vLLM / Ollama / TGI (según tipo de modelo y latencia).
4. **MLOps y artefactos:** MLflow + MinIO (S3 compatible) + registry interno.
5. **Base de datos y caché:** PostgreSQL + Redis.
6. **RAG y búsqueda semántica:** OpenSearch / Qdrant / Weaviate.
7. **Gateway y seguridad API:** Kong o Traefik + Keycloak (SSO, OAuth2/OIDC, RBAC).
8. **Observabilidad:** Prometheus + Grafana + Loki + Alertmanager.
9. **Automatización y CI/CD:** GitLab CE o Gitea + Woodpecker/Drone + Ansible/Terraform.
10. **Aula y consumo:** LMS (Moodle) + interfaces web internas + plugins de edición.

## 6. Catálogo inicial de modelos (autoalojados, licencia revisada)

1. **LLM generalista:** Llama, Mistral, Qwen (según benchmark y licencia vigente).
2. **Transcripción/voz:** Whisper.
3. **OCR y documento:** Tesseract + pipelines con OCRmyPDF.
4. **Generación/edición de imagen:** Stable Diffusion (entorno controlado).
5. **NLP específico académico:** modelos fine-tuned en corpus internos anonimizados.

## 7. Seguridad, cumplimiento y riesgo

1. **Marco normativo:** RGPD, LOPDGDD, ENS (si aplica por servicio público), políticas internas US.
2. **Controles técnicos:** cifrado en tránsito/reposo, segmentación de red, secretos en vault, hardening de nodos.
3. **Controles de uso:** logging de prompts/salidas con anonimización, límites por usuario, políticas antiabuso.
4. **Gobierno del dato:** clasificación, retención, borrado, auditoría y registro de tratamientos.
5. **Continuidad:** backup 3-2-1, pruebas de restauración, plan DR con RTO/RPO definidos.

## 8. Operación y mantenimiento (Servicio de Informática)

1. **Modelo de soporte:** N1 (CAU), N2 (sistemas), N3 (plataforma IA/MLOps).
2. **SLO iniciales:** disponibilidad 99.5%, latencia p95 por servicio, tasa de error <2%.
3. **Mantenimiento planificado:** parches mensuales, upgrades trimestrales de stack.
4. **Capacidad y coste:** panel FinOps por GPU-hora, almacenamiento, consumo por asignatura.
5. **Gestión de cambios:** despliegues con ventanas aprobadas y rollback documentado.

## 9. KPIs de éxito

1. Tiempo medio de respuesta por herramienta IA.
2. Disponibilidad mensual del servicio.
3. Número de asignaturas y docentes activos.
4. Reducción de tiempo en tareas de edición (baseline vs post-implantación).
5. Incidencias críticas por trimestre.
6. Coste por usuario activo y por crédito docente.
7. Satisfacción de estudiantes y profesorado.

## 10. Plan de adopción y formación

1. Formación técnica para Informática: operación Kubernetes, observabilidad, seguridad IA.
2. Formación docente: diseño de actividades con IA y evaluación responsable.
3. Guías para estudiantes: uso permitido, citación, ética y límites.
4. Programa de embajadores: profesorado piloto para transferencia de buenas prácticas.

## 11. Riesgos clave y mitigación

| Riesgo                           | Impacto | Mitigación                                                     |
| -------------------------------- | ------- | -------------------------------------------------------------- |
| Sobrecoste GPU                   | Alto    | Cuotas, autoscaling, modelos cuantizados, ventanas de uso      |
| Incumplimiento legal             | Alto    | DPIA, revisión legal previa, políticas de datos estrictas      |
| Baja adopción docente            | Medio   | Pilotos con casos reales, formación aplicada y soporte cercano |
| Deriva de calidad de modelos     | Medio   | Evaluación periódica, versionado y rollback de modelos         |
| Dependencia de perfiles técnicos | Medio   | Documentación operativa, runbooks y formación cruzada          |

## 12. Hitos de decisión

1. **Go/No-Go F2:** arquitectura y seguridad cerradas.
2. **Go/No-Go F3:** piloto con métricas mínimas.
3. **Go/No-Go F4:** operación estable y compliance validado.
4. **Go/Scale F5:** ampliación a más facultades o servicios transversales.
