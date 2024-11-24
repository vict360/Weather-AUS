# Caso Weather AUS (Clima de Australia)

* Dataset 📁 [Weather-AUS](https://github.com/vict360/Weather-AUS/blob/main/weatherAUS.csv)
* Presentación 📊 [PPT](https://docs.google.com/presentation/d/1d6EKOzEXVRrcN4kDkumWg00nLuCZTbUr/edit?usp=sharing&ouid=113786428185283411378&rtpof=true&sd=true)
* Adicional 📝 [informe](https://docs.google.com/document/d/1DodBuFfIKagNQbSoBfz8fUq49XMx83v4/edit?usp=sharing&ouid=113786428185283411378&rtpof=true&sd=true)

## Objetivo 🎯💡
El objetivo de este conjunto de datos es predecir la variable **"RainTomorrow"**, la cual indica si lloverá o no al día siguiente en diversas ubicaciones de Australia. Esta variable es categórica, tomando el valor:

- **1**: Si hubo lluvia al día siguiente.
- **0**: Si no hubo lluvia al día siguiente.

Además, se incluye la variable **"RISK_MM"**, que representa la cantidad de lluvia registrada en milímetros, proporcionando un contexto adicional para el análisis. Este conjunto de datos permite explorar relaciones meteorológicas y desarrollar modelos predictivos utilizando técnicas de minería de datos y aprendizaje automático.



## Contexto 📝
Australia tiene un clima predominantemente desértico en el centro, pero la franja costera entre Sídney y Adelaida es más fértil con lluvias moderadas todo el año. A pesar de estar en la misma latitud que otros países con climas extremos, Australia experimenta menos extremos debido a los efectos moderadores de los mares y océanos circundantes y la ausencia de grandes montañas. Las temperaturas medias oscilan entre los 27°C en la zona norte y los 13°C en las zonas más al sur. Australia tiene inviernos suaves y veranos cálidos con abundante sol y poca humedad. Las precipitaciones son escasas en el interior y aumentan en las zonas costeras, y las zonas mejor regadas son los litorales norte, este, sudeste y sudoeste. En el norte del país hay dos estaciones, seca en invierno y húmeda en verano con la irrupción de lluvias monzónicas. Australia es uno de los principales productores y exportadores de minerales y productos energéticos a nivel mundial, con el sector minero representando alrededor del 10% del PIB. El valor de las exportaciones totales de productos mineros y energéticos se espera que alcance los 299.000 millones AUD en el periodo 2019-20. Las exportaciones de mineral de hierro alcanzaron los 100.000 millones de AUD en 2018-19, y Australia es uno de los cinco principales países exportadores del mundo de bauxita, alúmina, mineral del hierro, zinc, carbón y de gas natural licuado (GNL).

Esta investigación se basa en un conjunto de datos de observaciones meteorológicas diarias obtenidas de la Oficina de Meteorología de la Commonwealth de Australia. El set de datos ha sido procesado para proporcionar dos variables: RainTomorrow (que indica si habrá lluvia al día siguiente) y RISK_MM (que indica la cantidad de lluvia registrada en milímetros). Estas variables son la variable objetivo y la variable de riesgo, respectivamente.

## Preguntas Guía ❓
* ¿Cuál es el promedio de la temperatura Máxima y Mínima de una Ubicación Geográfica?
* ¿Cual es la distribución anual de las temperaturas a lo largo de los años?
* ¿Cual es la distribución anual de la cantidad de lluvia (mm) a lo largo de los años?
* ¿Cuál es la distribución anual de la humedad a las 9am comparada con la humedad de las 3pm?
* ¿Cuál es el Promedio de la probabilidad de la cantidad de lluvia para el dia siguiente?
* ¿Cómo es el comportamiento del RainTomorrow (llueve mañana) según el día anterior (RainToday)?
* ¿Cuál es la dirección predominante cuando hubo lluvia por las tardes?


## Conclusiones 📋
Bajo el contexto del Dataset de Australia, podemos indicar que existen muchas características que no aportan en la detección de algún patrón relacionado a la variable objetiva, la cual es “RainTomorrow”. A continuación, se destacan puntos importantes de las secciones del proyecto, comenzando por el análisis exploratorio:

* El Dataset contiene una gran cantidad de datos nulos, los cuales fueron tratados por el comportamiento de otras características que influyen entre sí, colocando según los datos encontrados, el valor de la moda o la mediana.
* En característica “Rainfall”, si esta posee mayor a 1 mm de agua, se considera lluvia en la característica “RainToday”.
* Debido al clima que posee Australia, en las diversas localidades que se encuentran en el conjunto de datos, la mayoría de estas poseen poca lluvia a lo largo de los años, donde la gran cantidad de localidades que contiene un alto índice de lluvia son las que están ubicadas al sur del país.
* El valor de la característica “RainToday” no influye notablemente en la variable objetiva “RainTomorrow”, demostrando el clima tropical que puede haber a lo largo del Dataset.

Ahora, finalizado el análisis exploratorio, se trabajó bajo el aprendizaje supervisado, el cual se implementaron cuatro modelos, donde se indican los siguientes puntos:
* La característica “RISK_MM” influye directamente en la clasificación según los modelos, por lo que tuvo que ser eliminada para todos los modelos a realizar.
* El modelo con los resultados más bajos corresponde al Logístico, debido a que posee un recall bajo a diferencia de los otros modelos.
* El modelo que debe ser implementado en el aprendizaje supervisado, es el Random Forest, por su alta precisión y recall.

Por último, se implementó dos algoritmos no supervisados, para observar el comportamiento de las características, donde se realizaron cinco modelos respectivamente, donde se resalta los siguientes hallazgos:
* El algoritmo K-Means esta orientado a algunos de los climas abundantes en Australia (árido, semiárido y tropical), mientras que el Clúster Jerárquico esta mas centrado a la variable objetiva del estudio, si llueve o no según el comportamiento de este efecto climatológico en algunas variables.
* No es posible trabajar los algoritmos no supervisados con el Data Frame normalizado, puesto que solamente se aceptan datos enteros para su correcta clasificación.
* Por la poca cantidad de RAM y Procesamiento proporcionado, se redujo notablemente la cantidad de observaciones del Data Frame, siendo quinientas por cada localidad en los modelos de Clustering Jerárquico.
* Ambos algoritmos no supervisados se destacan en sí, puesto que ambos otorgan una mirada distinta, sin embargo, al haber sufrido reducción de datos el Clúster Jerárquico, el comportamiento de los datos en los gráficos no dan un real patrón para realizar predicciones, puesto que se destacan muchas localidades por sus escasas lluvias y en los gráficos se aprecia un gran presencia de lluvia o post-lluvia, por otro lado, las divisiones entre los clúster en K-Means son, en algunas características, muy lineales otorgando una interpretación muy forzada por el comportamiento de los datos según el contexto climatológico de Australia. Por lo tanto, si se desea correlacionar el aprendizaje no supervisado a la variable objetivo, es recomendado utilizar Clúster Jerárquico, pero si se desea predecir los climas en Australia por las diversas características, es recomendable utilizar K-Means.

En conclusión, es posible entregar un modelo óptimo para el aprendizaje supervisado y no supervisado, donde es necesario que estos sean implementados con las características correspondientes para realizar predicciones lo más correctas posibles, por lo tanto, se deben eliminar una cantidad considerable de características.

#### Mejoras:
Una mejora esencial bajo el contexto trabajado, el conocer si lloverá o no, es importante enfatizar en características que brinden una información valiosa a dicho fenómeno, donde existen localidades con bajas probabilidades de lluvia durante todo el año en Australia, mientras que hay otras regiones con un clima tropical, los que contienen la mayor tasa de lluvia en el año, por lo que, para poder hallar un correcto patrón para estas localidades, habrá un comportamiento distintos entre las características, donde sería correcto dividir los datos por las localidades que sufran un clima árido, semiárido, tropical, entre otros. Con la finalidad, de detectar con mayor exactitud si lloverá en la localidad según el clima que abunda en dicha zona.


## Tecnologías y Librerías 💻

- **Python** 🐍: Lenguaje de programación de alto nivel, ampliamente utilizado en análisis de datos.
- **Numpy** 🔢: Librería para cálculos numéricos y operaciones con matrices.
- **Pandas** 🐼: Librería para la manipulación y análisis de datos en estructuras de datos como DataFrames.
- **Seaborn** 📊: Librería para visualización de datos basada en Matplotlib, ideal para gráficos estadísticos.
- **Matplotlib - pyplot** 📈: Herramienta de visualización de gráficos, ampliamente utilizada para crear gráficos estáticos.
- **Google Colab** ☁️: Entorno de desarrollo interactivo basado en la web, ideal para ejecutar Python en la nube.

## Procedimientos 🛠️  
1. 📊 **Análisis Exploratorio de Datos (EDA):**  
   - Exploración inicial para identificar patrones, relaciones y valores atípicos.  

2. 🧹 **Preprocesamiento de Datos:**  
   - Limpieza de datos, manejo de valores faltantes y creación de nuevas características.  

3. 🤖 **Construcción de Modelos:**  
   - **Aprendizaje Supervisado:** Modelos de clasificación y predicción basados en datos etiquetados.  
   - **Aprendizaje No Supervisado:** Detección de patrones y agrupaciones en datos no etiquetados.

## Diccionario de Variables 🏷️

| **Variable**       | **Descripción**                                                                                       |
|---------------------|-------------------------------------------------------------------------------------------------------|
| Date               | Fecha de la observación                                                                              |
| Location           | Ubicación de la estación meteorológica                                                              |
| MinTemp            | Temperatura mínima en grados Celsius                                                                |
| MaxTemp            | Temperatura máxima en grados Celsius                                                                |
| Rainfall           | Cantidad de lluvia registrada ese día en mm.                                                        |
| Evaporation        | Evaporación (mm) en 24 horas                                                                         |
| Sunshine           | Número de horas de sol brillante en el día                                                          |
| WindGustDir        | Dirección de la ráfaga de viento más fuerte en 24 horas                                             |
| WindGustSpeed      | Velocidad (km/hr) de la ráfaga de viento más fuerte en 24 horas                                      |
| WindDir9am         | Dirección del viento a las 9am                                                                      |
| WindDir3pm         | Dirección del viento a las 3pm                                                                      |
| WindSpeed9am       | Velocidad (km/hr) del viento a las 9am                                                              |
| WindSpeed3pm       | Velocidad (km/hr) del viento a las 3pm                                                              |
| Humidity9am        | Porcentaje de humedad a las 9am                                                                     |
| Humidity3pm        | Porcentaje de humedad a las 3pm                                                                     |
| Pressure9am        | Presión atmosférica (hpa) a nivel del mar a las 9am                                                 |
| Pressure3pm        | Presión atmosférica (hpa) a nivel del mar a las 3pm                                                 |
| Cloud9am           | Fracción del cielo cubierto por nubes a las 9am (medido en "octavos", de 0 a 8)                      |
| Cloud3pm           | Fracción del cielo cubierto por nubes a las 3pm (medido en "octavos", de 0 a 8)                      |
| Temp9am            | Temperatura en grados Celsius a las 9am                                                             |
| Temp3pm            | Temperatura en grados Celsius a las 3pm                                                             |
| RainToday          | Variable indicadora que toma el valor 1 si la precipitación en mm. en las últimas 24 hrs. excede 1 mm, y 0 si no. |
| RISK_MM            | La cantidad de lluvia, como una medida del "riesgo"                                                 |
| RainTomorrow       | Variable indicadora que toma el valor 1 si al día siguiente llovió, y 0 si no.                      |




## Creditos 🙌
* David Valenzuela
* Mauricio Donato
* Víctor Vargas
