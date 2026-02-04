Buscador Multimodal Amazon - Proyecto RI (EPN)
Este proyecto implementa un sistema de Recuperación de Información (RI) de vanguardia para el 2do Bimestre de la Escuela Politécnica Nacional. Combina búsqueda visual, textual y memoria conversacional bajo una arquitectura RAG (Retrieval-Augmented Generation).

Estructura del Proyecto
El sistema está organizado en 6 etapas críticas para garantizar un flujo de datos eficiente y preciso:

Parte A: Indexación Multimodal: Carga del corpus completo (34k+ productos) y generación de embeddings mediante el modelo CLIP (ViT-B-32).

Parte B: Retrieval Flexible: Motor de búsqueda por similitud de coseno que permite entradas de texto, imagen o vectores matemáticos.

Parte C: Re-ranking Híbrido: Uso de un Cross-Encoder (MiniLM) para refinar la relevancia de los resultados textuales.

Parte D: Generación RAG: Integración con la API de Gemini (2.0/1.5 Flash) para generar respuestas justificadas y basadas en evidencia (Grounding).

Parte E: Memoria de Sesión: Gestión de contexto mediante fusión de vectores (70% ancla / 30% refinamiento) para búsquedas conversacionales.

Parte F: Interfaz Gradio: Aplicación web funcional que permite la interacción del usuario y visualización del catálogo.

Instrucciones de Ejecución
Sigue estos pasos para poner en marcha el buscador en Kaggle:

Configuración del Entorno:

Asegúrate de que el Accelerator esté configurado en GPU P100 o T4 x2 para que la indexación de los 34k productos sea rápida.

Verifica que el dataset consumer-reviews-of-amazon-products esté vinculado en el panel derecho de Kaggle.

Instalación de Dependencias:

Ejecuta la primera celda de instalación: !pip install -q -U sentence-transformers faiss-cpu gradio google-generativeai.

Configuración de API Key:

En la Parte D, asegúrate de colocar tu MY_API_KEY de Google AI Studio para que el módulo RAG pueda generar respuestas.

Ejecución del Pipeline:

Dale a "Run All". El proceso de "Generando vectores" puede tardar entre 5 y 10 minutos debido al tamaño del corpus completo.

Uso de la Interfaz:

Una vez que aparezca la interfaz de Gradio, puedes subir una foto desde tu celular o escribir una consulta.

Tip: Usa el checkbox "Refinar (Memoria)" para hacer preguntas de seguimiento sobre una búsqueda anterior.

Tecnologías Utilizadas
Modelos: CLIP (OpenAI), Cross-Encoder (MS MARCO), Gemini 2.0 Flash (Google).

Librerías: Sentence-Transformers, PyTorch, Pandas, Gradio.

Dataset: Consumer Reviews of Amazon Products (Corpus Completo).
