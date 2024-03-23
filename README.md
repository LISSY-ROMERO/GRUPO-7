# Eliminación de lecturas humanas de los datos de secuenciación del SARS-CoV-2
## OBJETIVOS 
##
# MARCO TEÓRICO
##
# METODOLOGÍA 
## REVISIÓN DE LA CALIDAD DE LAS SECUENCIAS A UTILIZAR
Previamente a utilizar las secuencias objetivo, es necesario evaluar su calidad individualmente. Para ello primero se realizó 
la respectiva descarga.

**Figura 1.** 
Ejecución de las cuatro secuencias en FastQ en la terminal y uso del comando "fastqc".
![WhatsApp Image 2024-03-23 at 1 55 28 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/8a799aad-7c05-47f6-b3ef-c7a38d54948e)

Se utilizó el comando "ls" para observar los archivos .HTML creados para cada secuencia.

**Figura 2.**
Ejecución del comando "ls" para enlistar los archivos HTML creados. 
![WhatsApp Image 2024-03-23 at 1 55 51 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/22151375-5376-488d-b558-ff37b57eefc4)

Dentro de Virtual Box se ingresó a las carpetas con las secuencias a analizar y se observó la creación específica de estos documentos .HTML dentro del computador.

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
Control de calidad de "SRR10903402_r1.fq.gz"
![WhatsApp Image 2024-03-23 at 2 24 29 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/b4f3d9a8-8601-4616-bdc4-faf250c3c597)

En los resultados del control de calidad se identificó que hay un número total de secuencias de 676694, con una longitud de 140 - 151 y %GC 43. De acuerdo a las técnicas Illumina 1.9 encoding se considera que tiene una puntuación de calidad aceptable para todas las bases y para todas las secuencias, ya que en su mayoría no superan el límite de error. Sin embargo, el contenido de adaptadores, secuencias sobrerrepresentadas y la cantidad de GC no cumplen los estándares, observe la Figura 7.

**Figura 7.**
Figura 7 Control de calidad de "SRR10903402_r2.fq.gz"
![WhatsApp Image 2024-03-23 at 2 26 23 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/a6fe6f50-05b9-4fd1-b6ab-2f8238f4ed81)


## OBTENCIÓN DE DATOS 

Importación de las secuencias crudas del SARS-COV-2 obtenidas de la plataforma Zenodo, mismas secuencias que en formato FASTQ se subieron a la plataforma Galaxy. 

**Figura 8.**
Obtención de datos
![WhatsApp Image 2024-03-23 at 12 19 54 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/7bf073dd-de2f-4cee-b413-d8f648b08bbc)


### EMPAREJAMIENTO DE SECUENCIAS 

Dentro de la plataforma Galaxy se seleccionó las 4 secuencias importadas a emparejar, se colocó un indicador "unpair forward"="_r1.fq.gz" y "unpaired reverse"="_r2.fq.gz" para el emparejamiento de las dos muestras "SRR10903401" y "SRR10903402".

**Figura 9.** 
Emparejamiento de secuencias Fastq de lecturas forward y reverse
![WhatsApp Image 2024-03-23 at 12 19 54 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/bd263fd4-f99b-4d6e-b0e9-854853bb5eb0)

### LECTURA, RECORTE Y  MAPEO 

En la página de Galaxy previamente se crearon dos ficheros "pair" y "unpair". Posteriormente en la sección de herramientas seleccionamos "Trimmomatic" con las opciones por default, se cambió "Paired-end (as collection)" y como FASTQ dataset se seleccionó la carpeta de nuestras secuencias pareadas.

**Figura 10.**
Trimmomatic para recorte de secuencias.
![WhatsApp Image 2024-03-23 at 2 35 24 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/0cb436e5-ea89-4f0a-b7d5-fcf7bae8d5a0)




