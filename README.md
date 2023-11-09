# Proyecto
## Predicción del mercado de divisas
Los grandes bancos, sociedades anónimas, fondos de pensiones, entidades financieras y no financieras e inversionistas buscan instrumentos financieros que les reporten la mayor rentabilidad al menor riesgo posible, uno de estos instrumentos es el mercado de divisas. Este es un mercado no regulado, por lo tanto, no existe un órgano que intermedie entre las partes por lo que no hay ningún tipo de compensación o liquidación como en los mercados bursátiles lo que genera un mayor riesgo a la hora de invertir. Un método muy utilizado para minimizar el riesgo al momento de invertir en estos mercados es la utilización de modelos de Inteligencia artificial para predecir estos movimientos, mejorar sus estrategias comerciales y disminuir el riesgo.

### Requisitos
* Para poder ejecutar el código es necesario crear una cuenta en la API de fixer, la cual nos proporciona los datos de diferentes monedas del mundo "FOREX"
* Crear una cuenta en MongoDB Atlas para hacer uso de la base de datos

### Metodología
Ya cumpliendo con los requisitos se ejecuta el NoteBook Proyecto.ipynb, en este archivo se genera una lista de fechas diarias de los últimos dos años para realizar el consumo de la API, posteriormente se hace el consumo de la api, por la suscripción gratuita hay un limite en el número de peticiones, por esta razón se realiza un ciclo para consumir la api con cada una de las fechas y almacenar los datos obtenidos es una lista.

Posteriormente se ordena la lista y se genera un DataFrame, con las fechas como index y el nombre de las columnas es la divisa.
Ya con los datos organizados se realiza la conección a la base de datos, el DataFrame se convierte en json ya que es el formato que admite MongoDB y se guarda el json en la base de datos. De esta manera no es necesario seguir consumiendo la API. Al guardar el archivo en la base de datos se genera un ID el cual es almacenado en un documento para posteriormente buscar el json por medio del ID


En los archivos prueba.ipynb y 1D.ipynb se realiza la conección a la base de datos, se lee el documento post_id.pickle el cual contiene el id de los datos en la BD y se hace la extraxión del documento, se lee y el json obtenido se convierte en un DataFrame

Con los datos obtenidos se diseña el modelo de una red neuronal convolucional de 1D y una red neuronal Long Short Term Memory (LSTM), se compilan los modelos y se entrenan

```java
import
```
Obtener datos de diversas divisas y entrenar una red neuronal que prediga el movimientol dolar
