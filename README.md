#  Buscador Multimodal Amazon - Proyecto RI (EPN)

Este proyecto implementa un sistema de **Recuperación de Información (RI)** avanzado realizado por estudaintes de la Escuela Politécnica Nacional. Combina búsqueda visual (Image-to-Product), textual y memoria conversacional bajo una arquitectura **RAG (Retrieval-Augmented Generation)**.

##  Estructura del Proyecto
El sistema se divide en etapas modulares para garantizar un flujo de datos eficiente:

* **Parte A: Indexación Multimodal:** Carga del corpus completo (34k+ productos) y generación de embeddings mediante **CLIP (ViT-B-32)**.
* **Parte B: Retrieval Flexible:** Motor de búsqueda por similitud de coseno compatible con texto, imágenes o vectores.
* **Parte C: Re-ranking Híbrido:** Uso de un **Cross-Encoder (MiniLM)** para refinar la relevancia de resultados textuales y visuales.
* **Parte D: Generación RAG:** Integración con la API de **Gemini (2.0/1.5 Flash)** para generar respuestas justificadas basadas en evidencia (Grounding).
* **Parte E: Memoria de Sesión:** Gestión de contexto mediante fusión de vectores (70% ancla / 30% refinamiento).
* **Parte F: Interfaz Gradio:** Aplicación web funcional para interacción en tiempo real y visualización de catálogo.



##  Instrucciones de Ejecución en Kaggle

Para ejecutar este proyecto correctamente, sigue estos pasos:

1.  **Configuración del Entorno:**
    * Activar el **Accelerator** (GPU T4 x2 o P100) en el panel de configuración de Kaggle.
    * Vincular el dataset `consumer-reviews-of-amazon-products` al notebook.
2.  **Instalación de Dependencias:**
    * Ejecutar la celda inicial para instalar `sentence-transformers`, `gradio` y `google-generativeai`.
3.  **Configuración de API Key:**
    * Insertar tu clave de Google AI Studio en la variable `MY_API_KEY` dentro de la Parte D.
4.  **Ejecución:**
    * Seleccionar **"Run All"**. La indexación inicial del corpus completo puede tardar entre 5 y 10 minutos debido al volumen de datos.

##  Tecnologías Utilizadas
* **Modelos**: CLIP (OpenAI), Cross-Encoder (MS MARCO), Gemini 2.5 Flash (Google).
* **Librerías**: PyTorch, Sentence-Transformers, Pandas, Gradio.
* **Dataset**: Consumer Reviews of Amazon Products (34k+ registros).

##  Autores
**Darlin Joel Anacicha Sánchez**
**Michael Andres Perugachi Sánchez**
Estudiante de Ingeniería en Ciencias de la Computación - EPN.
