# Eliminación de lecturas humanas de los datos de secuenciación del SARS-CoV-2
## OBJETIVOS 
##
##

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



## OBTENCIÓN DE DATOS 

Importación de las secuencias crudas del SARS-COV-2 obtenidas de la plataforma Zenodo, mismas secuencias que en formato FASTQ se subieron a la plataforma Galaxy. 

**Figura 1.**
Obtención de datos
![WhatsApp Image 2024-03-23 at 12 19 54 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/7bf073dd-de2f-4cee-b413-d8f648b08bbc)


### EMPAREJAMIENTO DE SECUENCIAS 

Dentro de la plataforma Galaxy se seleccionó las 4 secuencias importadas a emparejar, se colocó un indicador "unpair forward"="_r1.fq.gz" y "unpaired reverse"="_r2.fq.gz" para el emparejamiento de las dos muestras "SRR10903401" y "SRR10903402".

**Figura 2.** 
Emparejamiento de secuencias Fastq de lecturas forward y reverse
![WhatsApp Image 2024-03-23 at 12 19 54 PM](https://github.com/LISSY-ROMERO/GRUPO-7/assets/163187194/bd263fd4-f99b-4d6e-b0e9-854853bb5eb0)

### LECTURA, RECORTE Y  MAPEO 

**Figura 3.**
Control



