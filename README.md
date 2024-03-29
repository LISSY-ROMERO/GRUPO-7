
**Autores:** 

+ María Belén Apolo Renjifo
+ Eduardo Giuseppe Basantes Rivera
+ Lissy Katherine Romero Jadán
+ Joselyn Katerine Tulcanaz Montesdoca
  



**Fecha:**  Marzo del 2024


## 1. Tema 

Eliminación de lecturas humanas de los datos de secuenciación del SARS-CoV-2 


## 2. Problema 

Aunque la secuenciación genómica del SARS-CoV-2 es fundamental para comprender su evolución, identificar nuevas variantes y desarrollar estrategias de control, la presencia de lecturas humanas en los datos genómicos puede distorsionar los resultados y dificultar el análisis preciso. La contaminación de las muestras con ADN humano es una preocupación significativa en la secuenciación del SARS-CoV-2, ya que puede afectar la interpretación de los datos y llevar a conclusiones incorrectas sobre la variabilidad genética y la epidemiología del virus (Goldshmidt, 2020). 

Esta contaminación puede ocurrir durante la recolección de muestras, el procesamiento en el laboratorio o la manipulación de los datos. La presencia de ADN humano en las muestras puede deberse a una amplia gama de factores, como la contaminación cruzada durante la toma de muestras, la manipulación inadecuada en el laboratorio o la contaminación ambiental. Además, la falta de protocolos estandarizados para la eliminación de lecturas humanas en los datos de secuenciación del SARS-CoV-2 puede exacerbar este problema (Goldshmidt, 2020). 
 

## 3. Antecedentes 

Desde el inicio de la pandemia de COVID-19, la secuenciación genómica del SARS-CoV-2 se ha convertido en una herramienta crucial para comprender la evolución del virus, identificar variantes emergentes y rastrear la propagación de la enfermedad. Esta técnica permite analizar el ADN del virus y detectar mutaciones que podrían influir en su transmisibilidad, gravedad y respuesta a tratamientos y vacunas (Álvarez-Díaz et al., 2020). 

Durante el proceso de recolección, procesamiento y secuenciación de muestras de SARS-CoV-2, existe el riesgo de contaminación con ADN humano. Esta contaminación puede ocurrir debido a diversos factores, como la manipulación inadecuada de muestras, la contaminación cruzada en el laboratorio o la presencia de células humanas en las muestras biológicas (Goldshmidt, 2020). 

La presencia de lecturas humanas en los datos genómicos del SARS-CoV-2 puede distorsionar los resultados de la secuenciación, dificultando la interpretación precisa de la variabilidad genética del virus y su epidemiología. Esto puede llevar a conclusiones erróneas sobre la evolución del virus, la efectividad de las intervenciones de salud pública y el desarrollo de estrategias de control de la pandemia (Álvarez-Díaz et al., 2020). 

Aunque existen métodos para identificar y eliminar lecturas humanas de los datos de secuenciación, la mayoría resultan complicados por la variedad de protocolos y técnicas de extracción de muestras de ADN del tipo viral, sin embargo, una de las maneras más eficientes para este proceso de eliminación de secuencias especificas es la de alineamiento contra el genoma humano de referencia y el filtrado por características específicas del ADN humano (Naqvi et al., 2020). 

 
## 4. Objetivos 

### 4.1 Objetivo General
Establecer un flujo de trabajo eficiente y reproducible para la eliminación de lecturas humanas de los datos de secuenciación del SARS-CoV-2.

### 4.2 Objetivos Especificos
+ Crear scripts en Bash utilizando la terminal de Linux para evaluar la calidad de secuencias de SARS-CoV-2.
+ Configurar flujos de trabajo en la plataforma Galaxy para la eliminación de lecturas humanas, integrando herramientas de alineamiento y filtrado de datos.

## 5. Flujo de trabajo

### 5.1 Revisión de la calidad de las secuencias
Para la evalucación de la calidad calidad individual de cada secuencia objetivo, se utilizó la máquina virtual con interfaz Lubuntu. Para ello primero se realizó 
la respectiva descarga de los archivos, descomprensión de los mismos en la carpeta del usuario y se inició la terminal(Quality control, s.f.).
En la terminal se utilizó el comando "fastqc" para evaluar las cuatro secuencias. 

**Figura 1.** 
Ejecución de las cuatro secuencias en FastQ en la terminal y uso del comando "fastqc".

![WhatsApp Image 2024-03-23 at 1 55 28 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/8a799aad-7c05-47f6-b3ef-c7a38d54948e)

Se utilizó el comando "ls" para observar los archivos .HTML creados para cada secuencia (Quality control, s.f.).

**Figura 2.**
Ejecución del comando "ls" para enlistar los archivos HTML creados. 

![WhatsApp Image 2024-03-23 at 1 55 51 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/22151375-5376-488d-b558-ff37b57eefc4)

Dentro de Virtual Box se ingresó a las carpetas con las secuencias a analizar y se observó la creación específica de estos documentos .HTML dentro del computador (Quality control, s.f.).

**Figura 3.** 
Visualización de archivos .HTML en carpetas de Virtual Box.

![WhatsApp Image 2024-03-23 at 1 56 27 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/40c133f6-8be3-4935-a358-b8226ff0757e)

En los resultados del control de calidad se identificó que hay un número total de secuencias de 476632, con una longitud de 140 - 151 y %GC 44. De acuerdo a las técnicas Illumina 1.9 encoding se considera que tiene una puntuación de calidad buena para todas las bases y para todas las secuencias sin superar los límites de error. Sin embargo, el contenido de adaptadores, secuencias sobrerrepresentadas y la cantidad de GC no cumplen los estándares, observe la Figura 4.

**Figura 4.**
Control de calidad de "SRR10903401_r1.fq.gz"

![WhatsApp Image 2024-03-23 at 1 56 40 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/bdf74be0-6134-45db-a529-bf2a9e9383b2)

En los resultados del control de calidad se identificó que hay un número total de secuencias de 476632, con una longitud de 140 - 151 y %GC 43. De acuerdo a las técnicas Illumina 1.9 encoding se considera que tiene una puntuación de calidad aceptable para todas las bases y para todas las secuencias, ya que en su mayoría no superan el límite de error. Sin embargo, el contenido de adaptadores, secuencias sobrerrepresentadas y la cantidad de GC no cumplen los estándares, observe la Figura 5.

**Figura 5.** 
Control de calidad de "SRR10903401_r2.fq.gz"

![WhatsApp Image 2024-03-23 at 2 22 05 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/c4d26ea4-3249-4def-8225-2fc4b80f90f1)

En los resultados del control de calidad se identificó que hay un número total de secuencias de 676694, con una longitud de 140 - 151 y %GC 43. De acuerdo a las técnicas Illumina 1.9 encoding se considera que tiene una puntuación de calidad buena para todas las bases y para todas las secuencias, sin superar el límite de error. Sin embargo, el contenido de adaptadores, secuencias sobrerrepresentadas y la cantidad de GC no cumplen los estándares, observe la Figura 6.

**Figura 6.**
Control de calidad de "SRR10903402_r1.fq.gz".

![WhatsApp Image 2024-03-23 at 2 24 29 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/b4f3d9a8-8601-4616-bdc4-faf250c3c597)

En los resultados del control de calidad se identificó que hay un número total de secuencias de 676694, con una longitud de 140 - 151 y %GC 43. De acuerdo a las técnicas Illumina 1.9 encoding se considera que tiene una puntuación de calidad aceptable para todas las bases y para todas las secuencias, ya que en su mayoría no superan el límite de error. Sin embargo, el contenido de adaptadores, secuencias sobrerrepresentadas y la cantidad de GC no cumplen los estándares, observe la Figura 7.

**Figura 7.**
Figura 7 Control de calidad de "SRR10903402_r2.fq.gz".

![WhatsApp Image 2024-03-23 at 2 26 23 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/a6fe6f50-05b9-4fd1-b6ab-2f8238f4ed81)


### 5.2 Obtención de los datos 

Importación de las secuencias crudas del SARS-COV-2 obtenidas de la plataforma Zenodo, mismas secuencias que en formato FASTQ se subieron a la plataforma Galaxy (Maier, 2021). 

**Figura 8.**
Obtención de datos.

![WhatsApp Image 2024-03-23 at 12 19 54 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/7bf073dd-de2f-4cee-b413-d8f648b08bbc)


### 5.3 Emparejamiento de secuencias

Dentro de la plataforma Galaxy se seleccionó las 4 secuencias importadas a emparejar, se colocó un indicador "unpair forward"="_r1.fq.gz" y "unpaired reverse"="_r2.fq.gz" para el emparejamiento de las dos muestras "SRR10903401" y "SRR10903402" (Maier, 2021).

**Figura 9.** 
Emparejamiento de secuencias Fastq de lecturas forward y reverse.

![WhatsApp Image 2024-03-23 at 12 39 40 PM (1)](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/f509ef4b-3cd6-4386-b506-652ebc05de7c)

### 5.4 Lectura, corte y mapeo 

En la página de Galaxy previamente se crearon dos ficheros "pair" y "unpair". Posteriormente en la sección de herramientas seleccionamos "Trimmomatic" con las opciones por default, se cambió "Paired-end (as collection)" y como FASTQ dataset se seleccionó la carpeta de nuestras secuencias pareadas (Maier, 2021).

**Figura 10.**
Trimmomatic para recorte de secuencias.

![WhatsApp Image 2024-03-23 at 2 35 24 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/0cb436e5-ea89-4f0a-b7d5-fcf7bae8d5a0)

Se utilizó la herramienta map with BWA-MEM para la alineación de secuencias de las lecturas generadas respecto a un genoma de referencia (Maier, 2021).

**Figura 11.**
Uso de la herramienta map with BWA-MEM.

![WhatsApp Image 2024-03-23 at 3 31 15 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/17104b9a-37c9-4943-8454-f1fe6a900e2c)


### 5.5 Obtención de los identificadores de pares de lectura no humanos

La herramienta Samtools fastX, es importante por el filtrado de lecturas, el recorte de adaptadores y el respectivo control de calidad y así manipular y analizar archivos en formato fastq (Maier, 2021).

**Figura 12.**
Uso de la herramienta Samtool fastX.

![WhatsApp Image 2024-03-23 at 3 28 39 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/38eb2564-6727-4141-adba-823662654206)

Se utilizó la herramienta "Select lines that match an expresión" escogiendo el output previamente creado "Samtools fastx", con la opción de "Matching" y el patrón "^>.+" que nos permite escoger aquellas líneas que comienzan con un carácter ">" para retener los identificadores (Maier, 2021).

**Figura 13.**
Uso de la herramienta Select line.

![WhatsApp Image 2024-03-23 at 3 39 48 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/daee3f4b-fb5a-4e0c-af7a-dcb44ace1817)

Para la herramienta " Replace Text in entire line" usamos los parámetros de encontrar el patrón "^>(.+)" y remplazarlo con "\1" para hacer que el programa identifique las líneas que inician con ">" y reemplacenal caracter "(.+)" por " \1 (Maier, 2021).

**Figura 14.**
Uso de la herramienta Replace text in entire line.

![WhatsApp Image 2024-03-23 at 3 48 53 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/e92c92fa-ff39-4cf8-8c2e-c48d8b74ef50)

### 5.6  Identificación de lecturas no humanos para extraer las lecturas de interés de las entradas originales

Para descomprimir las secuencias no pareadas se utilizó la herramienta "Unzip" (Maier, 2021). 

**Figura 15.**
Uso de la herramienta Unzip.

![WhatsApp Image 2024-03-23 at 3 57 45 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/a2e0d42a-eddd-41fb-8590-b8ddc057a465)

Obtuvimos dos subconjuntos de datos a partir de la secuencias principal con la herramienta "Seqkt_subseq" ; la Figura 16 nos muestra la creación del subconjunto "forward" y la Figura 17 el subconjunto "reverse" (Maier, 2021). 

**Figura 16.**
Creación subconjunto "forward".

![WhatsApp Image 2024-03-23 at 3 57 45 PM (1)](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/6aae1b70-3396-49e0-b7be-726ef27c6f28)

**Figura 17.**
Creación subconjunto "reverse".

![WhatsApp Image 2024-03-23 at 4 15 20 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/7cf887d5-252c-4741-b380-9c762f1dd586)

Para finalizar transformamos los subconjuntos a archivos comprimidos para su uso posterior con la herramienta "Zipcollection" (Maier, 2021).

**Figura 18.**
Creación de un archivo comprimido.

![WhatsApp Image 2024-03-23 at 4 27 20 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/b476b0e0-e43e-49e2-a5be-743d215703a8)

### 5.7 Flujo de trabajo de Galaxy 

**Figura 19.**
Flujo de trabajo extraido de Galaxy EU.

![WhatsApp Image 2024-03-24 at 9 20 25 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/fd0f394c-8027-4745-b4dd-5dd6ec537998)

## 6. Resultados

Se lograron obtener dos secuencias de ADN viral de SARS-CoV-2 completamente libres de cualquier contaminación por lecturas humanas, asegurando así su integridad y listas para ser empleadas en futuros estudios.

**Figura 20.**
Secuencias comprimidas.

![image](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163610087/94948842-b48f-4621-aad7-8a9c02117a86)

**Figura 21.**
Subconjunto final 1.

![image](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163610087/8bd2e043-cbbf-4c36-a7a1-da7016890454)

**Figura 22.**
Subconjunto final 2.

![image](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163610087/72c8d09b-b464-4041-baa8-4c1109b32615)



## 7. Conclusiones

+ La correcta eliminación de las lecturas humanas de los datos de secuenciación del SARS-CoV-2 es esencial para asegurar la fiabilidad y precisión de los resultados. Este proceso facilita una interpretación más exacta de la diversidad genética del virus y su epidemiología, evitando así conclusiones incorrectas que podrían comprometer las estrategias de control de la pandemia y el progreso en el desarrollo de tratamientos y vacunas.
+ El establecimiento de un flujo de trabajo eficiente y reproducible para la eliminación de lecturas humanas de los datos de secuenciación del SARS-CoV-2 es un paso crucial hacia una investigación más rigurosa y confiable. La implementación de scripts y flujos de trabajo específicos, como el uso de herramientas de alineamiento y filtrado de datos, proporciona una base sólida para futuros estudios genómicos del virus, permitiendo una mejor comprensión de su biología y comportamiento epidemiológico.
  
## Referencias 

Goldschmidt, Pablo. (2020). Dificultades en la detección de genomas del nuevo coronavirus 2 (SARS CoV-2).. Revista Argentina de Salud Pública, 12(Supl. 1), 17. Epub 30 de diciembre de 2020. Recuperado en 23 de marzo de 2024, de http://www.scielo.org.ar/scielo.php?script=sci_arttext&pid=S1853-810X2020000300017&lng=es&tlng=es. 

Álvarez-Díaz, D. A., Laiton‐Donato, K., Franco-Muñoz, C., & Mercado, M. (2020). Secuenciación del SARS-CoV-2: la iniciativa tecnológica para fortalecer los sistemas de alerta temprana ante emergencias de salud pública en Latinoamérica y el Caribe. Biomedica, 40(Supl. 2), 188-197. https://doi.org/10.7705/biomedica.5841 

Naqvi, A. A. T., Fatima, K., Mohammad, T., Fatima, U., Singh, I., Singh, A., Atif, S. M., Hariprasad, G., Hasan, G. M., & Hassan, I. (2020). Insights into SARS-CoV-2 genome, structure, evolution, pathogenesis and therapies: Structural genomics approach. Biochimica Et Biophysica Acta (BBA) - Molecular Basis Of Disease, 1866(10), 165878. https://doi.org/10.1016/j.bbadis.2020.165878 

Quality control: Assessing FASTQC results | Introduction to RNA-Seq using high-performance computing - ARCHIVED. (s.f.). Retrieved March 22, 2024, from https://hbctraining.github.io/Intro-to-rnaseq-hpc-salmon/lessons/qc_fastqc_assessment.html

Wolfgang Maier, Eliminación de lecturas humanas de datos de secuenciación del SARS-CoV-2 (Materiales de capacitación de Galaxy) . https://training.galaxyproject.org/training-material/topics/sequence-analysis/tutorials/human-reads-removal/tutorial.html En línea; consultado el sábado 23 de marzo de 2024.



