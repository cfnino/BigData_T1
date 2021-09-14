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


<details>
<summary>:pushpin: Parte 1 - Hadoop</summary>
  <br>
  1. Se instalo una maquina virtual en VirtualBox con Ubuntu como sistema:
   <br><br>
   <img src="./Screenshots/Parte1/Ubuntu.png">

  <br>
  2. Se siguieron los pasos de esta guía:   
    <a href="http://cis.csuohio.edu/~sschung/cis612/Instruction_INSTALLING_HADOOP_Ubuntu.pdf">Guía Hadoop</a>
    <br><br>
    Evidencia de su ejecución y funcionamiento:
    <br><br>
    <img src="./Screenshots/Parte1/Evidencia1.png">
   
    
</details>

<details>
<summary>:pushpin: Parte 2 - MapReduce</summary>
    <br>
   1. Se siguieron los pasos de la <a href="https://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-common/SingleCluster.html#Execution">guía oficial</a> de Apache Hadoop, en especifico la sección de execution:
   <br>
   1.1. Web interface:
    <br><br>
    <img src="./Screenshots/Parte2/localhost.png">
   <br>
   1.2. Se crearon los directorios: 
  hdfs/*
    ├─ user/ 
        ├─ hdoop/ 
            ├─ input/ 
            ├─ output/
    <br> 
    Evidencia:
    <br><br>
    <img src="./Screenshots/Parte2/ruta.png">
    <br>
    1.3. Copiar los archivos etc/hadoop/*.xml a la carpeta input:
    <br> 
    Para esto se utiliza el siguiente comando de la guía oficial: bin/hdfs dfs -put etc/hadoop/*.xml input
    <br> 
    Evidencia de su ejecución en localhost:
    <br><br>
    <img src="./Screenshots/Parte2/put.png">
    
  
</details>

<details>
<summary>:pushpin: Parte 3 - Spark</summary>
this is hidden
</details>

<details>
<summary>:pushpin: Parte 4 - Jupyter Notebook</summary>
this is hidden
</details>
