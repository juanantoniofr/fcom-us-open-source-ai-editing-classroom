# Guía de Contribución

## Bienvenida

Gracias por tu interés en contribuir al **Aula de Edición Digital Asistida por IA** de la Facultad de Comunicación de la Universidad de Sevilla.

Este repositorio es un proyecto institucional colaborativo que documenta, planifica y opera una infraestructura de edición digital con IA de código abierto, bajo los principios de soberanía tecnológica, privacidad (RGPD) y escalabilidad gradual.

Este documento explica cómo contribuir al proyecto, incluyendo política de ramas, procesos de revisión por pares, y cómo solicitar acceso como nuevo colaborador.

---

## Quién puede contribuir

Este repositorio está abierto a **contribuidores internos**: personal de la Universidad de Sevilla (Servicio de Informática, profesorado, investigadores, personal administrativo) autorizados por el Servicio de Informática.

### Solicitud de acceso como nuevo colaborador

Si deseas convertirte en colaborador del proyecto:

**1. Envía un email a:** `informaticafcom@us.es`

**2. Asunto sugerido:**

```
[CONTRIBUIDOR] Solicitud de acceso - [Tu Nombre] - [Tu Departamento/Servicio]
```

**3. Información requerida:**

- Nombre completo y apellidos
- Departamento o Servicio (ej: Servicio de Informática, Dpto. de Periodismo)
- Rol que desempeñarás (ej: documentación técnica, arquitectura, operación)
- Justificación: por qué necesitas acceso (ej: "Implementación de módulo X", "Revisión de gobernanza")
- Confirma que has leído y aceptas el [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)

**4. Proceso:**

- El Servicio de Informática validará tu solicitud contra la estructura de governance del proyecto
- Se verificará tu afiliación a la Universidad de Sevilla
- Tiempo esperado de respuesta: **1-2 semanas de trabajo**
- Una vez aprobado, recibirás credenciales de acceso al repositorio

**5. Consideraciones adicionales:**

- Para cambios sobre **modelos de IA, políticas de datos, o gobernanza**, la aprobación puede requerir revisión del **Comité de IA** (véase sección de Gobernanza en [AI_Assisted_Digital_Editing_Classroom.md](AI_Assisted_Digital_Editing_Classroom.md#gobernanza-y-roles))
- Tu acceso se revocará automáticamente después de 1 año sin actividad en el repositorio, salvo renovación formal

---

## Política de ramas (Git Flow)

Usamos **Git Flow** para organizar el desarrollo. Esta política garantiza estabilidad de `main` (producción) mientras permite trabajo paralelo en features.

### Ramas principales

| Rama      | Propósito                                          | Origen | Merge a                                  |
| --------- | -------------------------------------------------- | ------ | ---------------------------------------- |
| `main`    | Releases estables y producción                     | N/A    | Etiquetada con versión (v1.0, v1.1, etc) |
| `develop` | Integración de features, rama de trabajo principal | N/A    | `main` al crear release                  |

### Ramas de características

**Creación de rama:**

```bash
git flow feature start descripcion-corta
# o manualmente:
git checkout -b feature/descripcion-corta develop
```

**Naming convention:**

- Usa **lowercase** con guiones: `feature/arquitectura-keycloak`, `feature/operacion-sre`
- Incluye el área del cambio: `feature/roadmap-fase2`, `feature/docs-rgpd`
- Máximo 50 caracteres en el nombre

**Duración y scope:**

- Una rama de feature = **una tarea o historia de usuario**
- Rama de corta vida: **máximo 2 semanas** de trabajo
- Si tarda más, divídela en sub-tareas con sub-ramas

**Ejemplo de workflow:**

```bash
git checkout develop
git pull origin develop
git checkout -b feature/actualizar-arquitectura
# ... haz cambios, commits ...
git push origin feature/actualizar-arquitectura
# Abre Pull Request (ver sección siguiente)
```

### Ramas de hotfix

Para correcciones críticas de `main`:

```bash
git checkout -b hotfix/descripcion-corta main
# ... corrige el problema ...
git checkout main && git merge hotfix/descripcion-corta
git checkout develop && git merge hotfix/descripcion-corta
git push origin main develop
```

**Requisito:** Hotfix 1 aprobación + documento que justifique por qué no se incluyó antes.

### Releases

**Creación de release (ejecuta Servicio de Informática):**

```bash
git checkout -b release/v1.1.0 develop
# Actualizar versiones en documentación
git checkout main && git merge release/v1.1.0
git tag -a v1.1.0 -m "Release v1.1.0"
git push origin main --tags
git checkout develop && git merge main
```

**Versionado:** Seguimos [Semantic Versioning](https://semver.org/es/):

- MAJOR: cambios de gobernanza o arquitectura significativa (v1.0 → v2.0)
- MINOR: nuevas fases del roadmap o features (v1.0 → v1.1)
- PATCH: correcciones, actualizaciones de documentación (v1.0 → v1.0.1)

---

## Proceso de Pull Request (PR)

Todos los cambios llegan a través de Pull Requests. No se hace merge directo a `develop` ni `main`.

### Crear un PR

**1. Abre el PR desde tu rama feature a `develop`** (o a `main` si es hotfix):

**2. Usa esta plantilla de descripción:**

```markdown
## Descripción

[Explica brevemente qué cambias y por qué]

## Tipo de cambio

- [ ] Documentación nueva o actualización
- [ ] Arquitectura o diseño técnico
- [ ] Políticas de gobernanza o seguridad
- [ ] Roadmap o planificación
- [ ] Caso de uso educativo

## Cambios principales

- Punto 1
- Punto 2
- Punto 3

## Impacto

**Áreas afectadas:** [Ej: Operación, Gobernanza, Docencia]

**Cambios en compliance:** ¿Afecta RGPD, seguridad, o políticas? [Describe]

**¿Requiere Comité de IA?** [ ] Sí [ ] No

## Checklist

- [ ] He leído y acepto el [CODE_OF_CONDUCT](CODE_OF_CONDUCT.md)
- [ ] He actualizado referencias cruzadas si aplica
- [ ] He revisado la ortografía y formato
- [ ] Mi cambio no introduce breaking changes sin justificación
- [ ] He añadido contexto sobre decisiones no obvias

## Enlaces relacionados

[Links a issues, documentación relacionada]
```

### Requisitos pre-merge

Antes de hacer merge, el PR debe cumplir:

- ✅ **1 aprobación obligatoria** del Servicio de Informática o revisor designado
- ✅ **Formato y linting:** archivo markdown válido, sin errores ortográficos obvios
- ✅ **Descripción clara:** el PR explica QUÉ cambia y POR QUÉ
- ✅ **Referencias:** si actualiza documento X, verifica que no haya referencias rotas en otros archivos
- ✅ **Consenso en comentarios:** responde a todos los comentarios del revisor
- ⚠️ **Escalación si aplica:** si es sobre modelos, gobernanza, o políticas, puede requerir revisión adicional del Comité de IA

### Tamaño y scope del PR

- **Pequeño (aceptado rápidamente):** ≤ 500 líneas, un cambio temático
- **Mediano (requiere revisión cuidadosa):** 500-2000 líneas, múltiples cambios relacionados
- **Grande (puede ser rechazado):** > 2000 líneas; divide en varios PRs

### Tiempos esperados de review

- **PR pequeño:** 2-3 días de trabajo
- **PR mediano:** 5-7 días de trabajo
- **PR grande:** 1-2 semanas (o solicitud de división)

---

## Revisión por pares

### Quién revisa

- **Revisor principal:** Servicio de Informática (`informaticafcom@us.es`)
- **Revisores secundarios (si aplica):**
  - Cambios sobre modelos IA: Comité de IA
  - Cambios sobre gobernanza: Dirección de Facultad
  - Cambios sobre RGPD/seguridad: DPO (Data Protection Officer)

### Criterios de revisión

El revisor verificará:

1. **Claridad y estructura**
   - ¿El cambio está bien explicado?
   - ¿La documentación es accesible para la audiencia?
   - ¿Hay consistencia de formato con el resto del repo?

2. **Conformidad institucional**
   - ¿Respeta la estructura de [Gobernanza](AI_Assisted_Digital_Editing_Classroom.md#gobernanza-y-roles)?
   - ¿Cumple requisitos RGPD si toca datos personales?
   - ¿Es coherente con la visión del proyecto?

3. **Completitud técnica**
   - ¿Referencias cruzadas están actualizadas?
   - ¿No introduce inconsistencias o deuda técnica?
   - ¿Hay recursos o timestamps que requieren revisión?

4. **Impacto en stakeholders**
   - ¿Afecta a múltiples departamentos?
   - ¿Requiere comunicación adicional?

### Feedback esperado

El revisor proporcionará feedback constructivo:

- ✅ **Aprobado:** El PR está listo para merge
- 🔄 **Cambios solicitados:** Se requieren ajustes antes de aprobar (con especificación clara)
- 💬 **Comentario:** Sugerencia no vinculante; el autor decide

---

## Áreas de contribución

### Aceptadas ✅

- **Documentación técnica:** mejoras en claridad, precisión sobre arquitectura, operación, despliegue
- **Roadmap y planificación:** actualizar fases, hitos, estimaciones; casos de uso nuevos
- **Gobernanza y políticas:** procesos RGPD, políticas de uso, roles, responsabilidades
- **Guías educativas:** contexto academico, casos de uso docentes, evaluación
- **Correcciones:** errores, links rotos, inconsistencias, actualizaciones de versiones de componentes
- **Propuestas estratégicas:** nuevas fases, mejoras, reflexiones documentadas

### No aceptadas ❌

- **Cambios de infraestructura sin revisión:** cualquier modificación de stack, versiones críticas, o componentes requiere aprobación del Comité de IA
- **Datos personales o sensibles:** nunca incluyas datos reales, credenciales, o información sensible de estudiantes
- **Contribuciones no autorizadas:** si no estás en la lista de colaboradores aprobados, solicita acceso primero
- **Spam, promoción, o contenido no relacionado**

---

## Contacto y preguntas

**Email principal:** `informaticafcom@us.es`

**¿Qué escribir?**

| Pregunta                                         | Contacto                                                                                                                    |
| ------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------- |
| Solicitar acceso como colaborador                | informaticafcom@us.es                                                                                                       |
| Problema técnico con el repo                     | informaticafcom@us.es                                                                                                       |
| Pregunta sobre gobernanza del proyecto           | Véase [Gobernanza en AI_Assisted_Digital_Editing_Classroom.md](AI_Assisted_Digital_Editing_Classroom.md#gobernanza-y-roles) |
| Pregunta sobre modelos, IA, o políticas de datos | informaticafcom@us.es (escalará a Comité de IA si es necesario)                                                             |
| Código de Conducta: reporte de violación         | informaticafcom@us.es + CC a Dirección de Facultad                                                                          |

---

## Cumplimiento, seguridad y confidencialidad

### Código de Conducta

Todos los colaboradores aceptan cumplir el [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md). Las violaciones pueden resultar en suspensión o remoción de acceso.

### RGPD y privacidad

- **No ** incluyas datos personales reales (nombres de estudiantes, emails, IPs, etc.) en documentación o ejemplos
- Si necesitas documentar un proceso que toca datos, usa términos genéricos o pseudónimos
- Cualquier cambio sobre procesamiento de datos requiere validación del DPO

### Confidencialidad

- Contenido marcado como "Interno" o "Confidencial" no se divulga fuera de la Universidad de Sevilla
- Si contribuyes código o documentación bajo acuerdo de confidencialidad, notifica al revisor
- NDA institucional se aplica a todos los colaboradores

### Reporte de vulnerabilidades de seguridad

Si identificas una vulnerabilidad en la infraestructura descrita:

1. **No la publiques** en PR público
2. **Contacta confidencialmente:** `informaticafcom@us.es` con asunto `[SEGURIDAD] Reporte de vulnerabilidad`
3. **Proporciona detalles:** descripción, riesgo estimado, pasos de reproducción
4. **Tiempo de respuesta:** el Servicio de Informática responderá dentro de 5 días de trabajo

---

## Versionado y cambios de este documento

**Versión actual:** 1.0  
**Última actualización:** 14 de abril de 2026  
**Próxima revisión:** Trimestral (o cuando cambie gobernanza)

**Cambios significativos:**

- Si modificas política de ramas, requisitos de PR, o acceso, notifica a todos los colaboradores activos
- Cambios menores (mejoras de redacción, correcciones) no requieren notificación

---

## Agradecimiento

Tu contribución ayuda a construir una infraestructura de IA responsable, soberana y académicamente valiosa. Gracias por ser parte de este proyecto.

¿Preguntas? Contacta a `informaticafcom@us.es`.
