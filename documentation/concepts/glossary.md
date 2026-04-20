# Glosario de términos

---

## LLM (Large Language Model)

**Tipo:** modelo  
**Área:** IA / NLP

### Definición

Modelo basado en transformers entrenado para predecir el siguiente token en una secuencia de texto.

### Detalle técnico

Utiliza arquitecturas decoder-only o encoder-decoder con mecanismos de atención. Entrenado sobre grandes volúmenes de texto mediante aprendizaje autoregresivo.

### Uso en el proyecto

Se utilizará como motor principal de generación de texto (ej: Gemma) dentro de servicios de asistencia, edición y consulta.

### Ejemplo

Generación de respuestas en un chatbot académico.

### Términos relacionados

- RAG
- Fine-tuning

---

## RAG (Retrieval-Augmented Generation)

**Tipo:** técnica  
**Área:** IA / arquitectura

### Definición

Arquitectura que combina recuperación de información externa con generación de texto mediante un LLM.

### Detalle técnico

El sistema recupera documentos relevantes desde una base de datos (normalmente vectorial) y los inyecta como contexto en el prompt del modelo.

### Uso en el proyecto

Permite construir asistentes que responden basándose en documentación institucional (PDFs, normativa, contenidos docentes).

### Ejemplo

Consulta sobre normativa universitaria usando documentos internos indexados.

### Términos relacionados

- Embeddings
- Vector database

---

## Embeddings

**Tipo:** técnica  
**Área:** IA / NLP

### Definición

Representación vectorial de texto que captura su significado semántico.

### Detalle técnico

Los textos se transforman en vectores de alta dimensión que permiten medir similitud semántica mediante distancia (coseno, dot product).

### Uso en el proyecto

Se utilizarán para indexar documentos y realizar búsqueda semántica en sistemas RAG.

### Ejemplo

Buscar documentos similares a una pregunta de usuario.

### Términos relacionados

- RAG
- Vector database

---

## Fine-tuning

**Tipo:** técnica  
**Área:** IA / entrenamiento

### Definición

Proceso de adaptar un modelo preentrenado a un dominio o tarea específica mediante entrenamiento adicional.

### Detalle técnico

Puede implicar actualización completa de parámetros o técnicas eficientes como LoRA/QLoRA.

### Uso en el proyecto

Se usará de forma limitada para adaptar modelos a necesidades concretas, priorizando RAG como alternativa más eficiente.

### Ejemplo

Ajustar un modelo para responder con terminología académica específica.

### Términos relacionados

- LoRA
- QLoRA

---

## Vector database

**Tipo:** infraestructura  
**Área:** backend / datos

### Definición

Base de datos optimizada para almacenar y consultar vectores (embeddings).

### Detalle técnico

Permite búsquedas por similitud semántica usando índices especializados (HNSW, IVF, etc.).

### Uso en el proyecto

Almacenar embeddings de documentos para su recuperación en pipelines RAG.

### Ejemplo

Qdrant, Weaviate, OpenSearch con soporte vectorial.

### Términos relacionados

- Embeddings
- RAG
