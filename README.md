<img align="right" width="100" height="100" src="./Screenshots/UB.jpg">

<p>
Big Data Analytics.
<br>
Universidad el bosque.
<br>
Nombre: Carlos Niño.
<br>
Profesor: Fabian Peña. 
</p>

---------------------------

<p align="center">
    :page_facing_up: TALLER 1
</p>

<!------------------------------------------------------------ PARTE 1 ------------------------------------------------------->
<details>
<summary>:pushpin: Parte 1 - Hadoop</summary>
  <br>
  1. Se instalo una máquina virtual en VirtualBox con Ubuntu como sistema:
   <br><br>
   <img src="./Screenshots/Parte1/Ubuntu.png">
  <br><br>
  2. Se siguieron los pasos de esta guía:   
    <a href="http://cis.csuohio.edu/~sschung/cis612/Instruction_INSTALLING_HADOOP_Ubuntu.pdf">Guía Hadoop</a>
    <br><br>
    Evidencia de su ejecución y funcionamiento:
    <br><br>
    <img src="./Screenshots/Parte1/Evidencia1.png">
   
    
</details>

<!------------------------------------------------------------ PARTE 2 ------------------------------------------------------->
<details>
<summary>:pushpin: Parte 2 - MapReduce</summary>
    <br>
   1. Se siguieron los pasos de la <a href="https://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-common/SingleCluster.html#Execution">guía oficial</a> de Apache Hadoop, en específico la sección de execution:
   <br><br>
   &nbsp;&nbsp;1.1. Web interface:
    <br><br>
    <img src="./Screenshots/Parte2/localhost.png">
   <br><br>
   &nbsp;&nbsp;1.2. Se crearon el siguiente directorio con el siguiente comando de la guía oficial:
    <br><br>
    <pre><code>bin/hdfs dfs -mkdir /user/hdoop/input </code></pre>
    <br> 
    &nbsp;&nbsp;Evidencia:
    <br><br>
    <img src="./Screenshots/Parte2/ruta.png">
    <br><br>
   &nbsp;&nbsp;1.3. Copiar los archivos etc/hadoop/*.xml a la carpeta input:
    <br><br>
    &nbsp;&nbsp;Para esto se utiliza el siguiente comando de la guía oficial:
    <br><br>
    <pre>bin/hdfs dfs -put etc/hadoop/*.xml input</pre>
    <br> 
    &nbsp;&nbsp;Evidencia de su ejecución en localhost:
    <br><br>
    <img src="./Screenshots/Parte2/put.png">
    <br><br>
   &nbsp;&nbsp;1.4. Ejecución del ejemplo:
     <br><br>
    <img src="./Screenshots/Parte2/Ejemplo/Consola1.png">
    <br>
    <img src="./Screenshots/Parte2/Ejemplo/Consola2.png">
    <br>
    <img src="./Screenshots/Parte2/Ejemplo/Consola3.png">
    <br><br>
   &nbsp;&nbsp;1.5. Salida:
    <br><br>
    <img src="./Screenshots/Parte2/Ejemplo/Consola4.png">
    <br><br>
    &nbsp;&nbsp;1.6. ¿Qué resultados generó el programa y cuáles son los pasos MapReduce que implementa?
    <br><br>
    La salida generada nos muestra todos los archivos que empiecen con dfs de la carpeta input, la cual habíamos subido los archivos de etc/hadoop/*.xml, y cuenta cuantos archivos se llaman así.
    <br><br>
    En el código <a href="https://github.com/naver/hadoop/blob/master/hadoop-mapreduce-project/hadoop-mapreduce-examples/src/main/java/org/apache/hadoop/examples/Grep.java">grep</a> podemos observar que para mapReduce primero se define un job, el cual será el encargado de generar el MapReduce, este job primero hace el map el cual es el encargado de dividir las nombres de los archivos sacados de la carpeta input, luego se ejecuta la función reduce para cada grupo de datos creados por el map.
    <br><br>
     La función de map genera una clave, de este modo al hacer reduce se pueden buscar valores asociados a la clave para poder fusionar estos datos y de este modo ir reduciendo los resultados (conjunto más pequeño de valores)
     <br><br>
     Al finalizar los organiza de manera decreciente, por esta razón en la salida se observa primero los nombres de los archivos que se repiten 2 veces y luego los que se repiten una sola vez.
    <br><br>
    <hr>
<!------------------------------------------------------------ PARTE 2.2. ------------------------------------------------------->
   2. Ejecutar WordCount del <a href="https://github.com/naver/hadoop/tree/master/hadoop-mapreduce-project/hadoop-mapreduce-examples/src/main/java/org/apache/hadoop/examples">jar de ejemplos</a>, cargando al HDFS un archivo de texto plano.
    <br><br>
    <details>
    <summary>:pushpin: Re-instalación Hadoop</summary>
       <br>
     &nbsp;&nbsp; Por problemas técnicos la primera máquina virtual la elimine y cree una nueva, donde maneje la última versión de Hadoop:
        <br><br>
    <img src="./Screenshots/Parte2/Wordcount/Hdoop/1.png">
        <br>
    </details>
    &nbsp;&nbsp;2.1. Archivo de texto plano:
    <br><br>
    &nbsp;&nbsp; Para esta parte copiamos el poema: <a href="https://www.zendalibros.com/los-30-mejores-poemas-en-espanol/">Me gusta cuando callas, de Pablo Neruda</a> y creamos un archivo llamado poema.txt
    <br><br>
    <img src="./Screenshots/Parte2/Wordcount/put.png">
    <br><br>
    &nbsp;&nbsp;2.2. Archivo cargado al HDFS:
    <br><br>
    &nbsp;&nbsp; Para subirlo al HDFS:
    <br><br>
    <pre>bin/hdfs dfs -put poema.txt input</pre>
    &nbsp;&nbsp; Archivo cargado:
    <br><br>
    <img src="./Screenshots/Parte2/Wordcount/hdfs2.png">
    <br><br>
    &nbsp;&nbsp;2.3. Ejecución WordCount:
    <br><br>
    <pre>bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-3.3.1.jar wordcount input output</pre>
    &nbsp;&nbsp;Consola:
    <br><br>
    <img src="./Screenshots/Parte2/Wordcount/consola1.png">
    <br>
    <img src="./Screenshots/Parte2/Wordcount/Consola2.png">
    <br><br>
    &nbsp;&nbsp;1.5. Salida:
    <br><br>
    <img src="./Screenshots/Parte2/Wordcount/resultado.png">
    <br><br>
    &nbsp;&nbsp; Resultado por localhost:
    <br><br>
    <img src="./Screenshots/Parte2/Wordcount/output.png">
    <br><br>
    &nbsp;&nbsp;2.4. ¿Qué resultados generó el programa y cuáles son los pasos MapReduce que implementa?
    <br><br>
   El archivo de salida se encuentra en la ruta: <a href="./Parte2/">Parte2/part-r-00000</a>
    <br><br>
   Como podemos observar la salida es un archivo con la cantidad de veces que aparece cada palabra, para este caso, en el archivo de wordcount.java podemos observar que se genera un job encargado de ejecutar la función map que es la encargada de dividir la información en subconjuntos más pequeños, donde el reduce se aplica a cada uno de estos conjuntos para poder reducirlos.
    <br><br>
    A diferencia del ejemplo, en este caso no se esta organizando por la cantidad de veces que aparezca una palabra.
    
</details>

<!------------------------------------------------------------ PARTE 3 ------------------------------------------------------->
<details>
<summary>:pushpin: Parte 3 - Spark</summary>
 <br>
    1. Se siguieron los pasos de la <a href="http://cis.csuohio.edu/~sschung/cis612/CIS612_SparkInstallation_Ubuntu.pdf">guía</a> para instalar Spark en Ubuntu.
   <br><br>
    2. Se ejecuta el master y el worker:
    <br><br>
    <pre>start-master.sh </pre>
    <img src="./Screenshots/Parte3/start-master.png">
    <br>
    <img src="./Screenshots/Parte3/8080.png">
    <br><br>
    <pre>start-worker.sh spark://carlos:7077 </pre>
    <img src="./Screenshots/Parte3/worker.png">
    <br>
    <img src="./Screenshots/Parte3/8080-worker.png">
    <br><br>
    3. Se ejecuta pyspark:
    <br><br>
    <img src="./Screenshots/Parte3/pyspark.png">
    <br><br>
    4. Creamos un archivo de texto plano llamado poema.txt, para esta parte copiamos el poema: <a href="https://www.zendalibros.com/los-30-mejores-poemas-en-espanol/">Tú me quieres blanca, de Alfonsina Storni</a>
    <br><br>
    5. Ejecución wordcount:
    <br><br>
    En la siguiente imagen se ejecuta el código para el wordCount y observamos que es mucho más simplificado que el wordCount de Hadoop que era en java, en este caso estamos ejecutando la consola de pyspark para poder trabajar con python.
    <br><br>
    Lo primero es leer el archivo al que queremos contar sus palabras, en este caso el archivo es poema.txt, luego se va a generar un mapa con los valores capturados del texto, estos valores son separador por los espacios entre cada palabra, para luego poder correr el map que asigna llaves para poder hacer reduce y generar el archivo que devolverá cuantas veces aparece esa palabra en el archivo.
    <br><br>
    <img src="./Screenshots/Parte3/wordcount.png">
    <br><br>
    6. El archivo de salida se encuentra en la ruta: <a href="./Parte3/">Parte3/part-r-00000</a>
    <br><br>
</details>

<!------------------------------------------------------------ PARTE 4 ------------------------------------------------------->
<details>
<summary>:pushpin: Parte 4 - Jupyter Notebook</summary>
    <br>
    1. Se clono la carpeta SparkTutorial:
    <br><br>
    <img src="./Screenshots/Parte4/clone.png">
    <br><br>
    2. Se descargó el archivo: <a href="https://www.kaggle.com/dinnymathew/usstockprices">stocks_price_final.csv</a>
    <br><br>
    3. Se descargó Anaconda3:
    <br><br>
    <img src="./Screenshots/Parte4/wget.png">
    <br><br>
    4. Jupyter lab:
    <br><br>
    <img src="./Screenshots/Parte4/jupyter.png">
    <br><br>
    5. La carpeta que contiene los archivos .ipynb es: <a href="./Parte4/SparkTutorial/">Parte4/SparkTutorial</a>
    <br><br>
    :pencil2: Analisis:
    <br><br>
    :page_with_curl: <a href="./Parte4/SparkTutorial/pyspark-basics.ipynb">spark-basics.ipynb</a>
    <br><br>
    Para poder ejecutar el SparkContext coloque la ruta de mi master, que sería spark://carlos:7077, ya que colocando spark://localhost:7078 me negaba la conexión, pero al colocar el master si ha podido crear el context ya que no se niega la conexión, de igual manera podemos observar que en el master que si se han ejecutado las aplicaciones, para este caso el appName era pyspark-basics.
    <br><br>
    <img src="./Screenshots/Parte4/localhost.png">
    <br><br>
   En el ejercicio se nos muestra algunas clases de tipos de conjuntos por decirle, como las tuplas o listas, también a leer el texto de un archivo y sacar una cantidad de registros de ese documento.
    <br><br>
    En el caso del archivo stocks_price_final.csv, el ejercicio nos muestra cómo saber cuántos registros totales tiene y poder imprimir las columnas y que tipo de datos son estas columnas en este archivo.
    <br><br>
    También nos muestra cómo podemos hacer map, el cual podemos observar que genera varios subconjuntos dentro del conjunto principal, y como obtener un flat structure, que sería un conjunto de datos sin los subconjuntos adentro.
    <br><br>
    Al final nos muestra cómo funciona el reduceByKey y organizan los resultados por la llave, siendo de manera descendente.
    <br><br>
    :page_with_curl: <a href="./Parte4/SparkTutorial/pyspark-data-analysis.ipynb">pyspark-data-analysis.ipynb</a>
    <br><br>
   Para este ejercicio se inicia construyendo una sesión con el appName pyspark-data-analysis.
    <br><br>
    Lo primero es leer el archivo stocks_price_final.csv definiendo su separador (sep = ","), se nos muestra como contar los registros, y como poder cambiar la estructura de las columnas del archivo, ya que, se cambian los tipos de datos de algunas columnas.
    <br><br>
    Luego de esto, se filtran los datos y se transforman con pandas para poder graficarlos, las siguientes gráficas hacen referencia al precio con respecto al tiempo de TSLA y GME.
    <br><br>
    La siguiente grafica haría referencia a la cantidad de empresas por sector.
    <br><br>
    Por último, almacenamos la información en un archivo .csv, esta información serían los precios más altos y bajos por fecha. Este archivo se encuentra: <a href="./Parte4/SparkTutorial/Resultado/">aquí</a>
    <br><br>
    <br><br>
    Nota: En la carpeta <a href="./Parte4/SparkTutorial/Html">Parte4/SparkTutorial/Html</a> se anexan los archivos ejecutados de jupyter lab exportados como html por si acaso.
</details>
