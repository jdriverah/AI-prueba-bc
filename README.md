**Prueba tecnica Científico de Datos Gerencia Tecnica en Inteligencia Artificial
Centro de Excelencia Analítica, Inteligencia Artificial y Gobierno de la Información
Vicepresidencia de Analítica, Datos e Inteligencia Artificial**

Julian David Rivera Hoyos

**Pasos:**
- Realizar embedding sobre el entrenamiento para validar la eficienciad del modelo encontrando los documentos relevantes y comprobar la medida de MMR
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

**Conclusiones**
- Gurdandose los documentos indexados y embebidos con una ejecucion costo inicial de 0.06 dolares de 5000 documentos,4100 querys y usando la api de Open AI siendo el modelo mas eficiente se hace un analisis de costo basado pricing y de viabilidad del uso de la api teniedo el promedio de tokens por query de 12 y el costo por cada mil tokens para el modelo ada V2 es de 0.00010 haciendo las opereciones respectivas por cada dolar podemos realizar 833.333 querys =1/(0.00010/1000*12), y dada una base de 32000 colaboradores en una organizacion y asumiendo 10 consultas en promedio por dia por colaborador,y 20 dias laborales se tendria un costo para busqueda de documentos previamiente indexados de 7,68 dolares al mes, siendo entonces esta una opción viable y economica para la organización, teniendo como riesgo el envio de información a openAI donde se debe revisar los terminos y condiciones para realizar el embedding de los documentos teniendo como garantia la confidencialidad de la información

![image.png](attachment:image.png)