# Operación y Mantenimiento

## Modelo de soporte

- N1: CAU.
- N2: sistemas.
- N3: plataforma IA y MLOps.

## Objetivos de servicio

- Disponibilidad inicial objetivo: 99.5%.
- Latencia p95 por servicio controlada.
- Tasa de error por debajo del umbral definido por servicio.

## Operación habitual

- Parcheado mensual.
- Actualizaciones trimestrales del stack.
- Ventanas de mantenimiento aprobadas.
- Rollback documentado para cada despliegue relevante.

## Capacidad y costes

Se debe llevar seguimiento de GPU-hora, almacenamiento y consumo por uso académico para tomar decisiones de escalado.

## Continuidad

- Copias de seguridad 3-2-1.
- Pruebas de restauración.
- Plan de recuperación ante desastres con RTO y RPO definidos.
