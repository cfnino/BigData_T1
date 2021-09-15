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
  1. Se instalo una maquina virtual en VirtualBox con Ubuntu como sistema:
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
   1. Se siguieron los pasos de la <a href="https://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-common/SingleCluster.html#Execution">guía oficial</a> de Apache Hadoop, en especifico la sección de execution:
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
    &nbsp;&nbsp;1.6. ¿Qué resultados generó el programa y cuales son los pasos MapReduce que implementa?
    <br><br>
    &nbsp;&nbsp;
    <br><br>
    <hr>
<!------------------------------------------------------------ PARTE 2.2. ------------------------------------------------------->
   2. Ejecutar WordCount del <a href="https://github.com/naver/hadoop/tree/master/hadoop-mapreduce-project/hadoop-mapreduce-examples/src/main/java/org/apache/hadoop/examples">jar de ejemplos</a>, cargando al HDFS un archivo de texto plano.
    <br><br>
    <details>
    <summary>:pushpin: Re-instalación Hadoop</summary>
     &nbsp;&nbsp; Por problemas tecnicos la primera maquina virtual la elimine y cree una nueva, donde maneje la ultima versión de Hadoop:
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
    &nbsp;&nbsp;2.4. ¿Qué resultados generó el programa y cuales son los pasos MapReduce que implementa?
    <br><br>
    &nbsp;&nbsp;El archivo de salida se encuentra en la ruta: <a href="./Parte2/">Parte2/part-r-00000</a>
    
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
    <img src="./Screenshots/Parte3/wordcount.png">
    <br><br>
    6. El archivo de salida se encuentra en la ruta: <a href="./Parte3/">Parte3/part-r-00000</a>
    <br><br>
</details>

<!------------------------------------------------------------ PARTE 4 ------------------------------------------------------->
<details>
<summary>:pushpin: Parte 4 - Jupyter Notebook</summary>
this is hidden
</details>
