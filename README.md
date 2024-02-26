**Prueba tecnica Científico de Datos Gerencia Tecnica en Inteligencia Artificial
Centro de Excelencia Analítica, Inteligencia Artificial y Gobierno de la Información
Vicepresidencia de Analítica, Datos e Inteligencia Artificial**

Julian David Rivera Hoyos

**Pasos:**
- Realizar embedding sobre el entrenamiento para validar la eficienciad del modelo encontrando los documentos relevantes y comprombar la medida de MMR
- Se realiza un embedding sobre el modelo de Open AI text-embedding-ada-002 para el test query y test document
- Se crea el algoritmo para evaluar cosine similarity entre el query test embedding y el document test embedding y recuperar los 10 mejores resultados en cuanto a esta metrica.
  
**Notas:**
- Se realizo la prueba tambien con un modelo de tokenizacion y embebido de bert donde La media de los MMR es : 0.33875.
- Se considero construir un modelo proprio atravez de el algoritmo basado en el paper "Attention is all you need" (transformer) realizando una tokenizacion y embedding propio pero dado el rendimiendo bajo de bert en comparacion con ada-v2, para obtener un resultado similar a la referencia ada-v2 con un modelo propio se requiere una mayor conjunto de entremiento de procesamiento, y tiempo de estudio para la construccion de este, por tanto se obta por la solucion inicial.

**Referencias:**
- https://platform.openai.com/docs/guides/embeddings
- https://learn.microsoft.com/en-us/azure/ai-services/openai/tutorials/embeddings?tabs=python%2Ccommand-line&pivots=programming-language-python
- https://www.tensorflow.org/text/tutorials/transformer
- https://www.tensorflow.org/text/guide/subwords_tokenizer
  
**Requisitos:**
- pip install openai
- pip install tiktoken
- pip install pandas
- Configurar variable de entorno SECRET_KEY_OPENAI de openai secretkey
  
**Estructura:**
  - Insumos: Datos de entrenamiento y test
  - Ejecuciones: Ejecuciones del modelo
  - model_test: Modelo bert, con las librerias necesarias
