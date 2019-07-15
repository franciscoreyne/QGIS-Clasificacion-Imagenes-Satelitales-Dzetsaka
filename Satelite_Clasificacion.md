# DISPONIBILIDAD DE DATOS SATELITALES Y CLASIFICACIÓN

>Hoy en dia disponer de datos satelitales es totalmente facil.

>Estos datos corresponden a información sobre areas geograficas, imagenes satelitales en series temporales, 
>imagenes de muy alta resolución espacial e imagenes hiperepectrales.

## >**Algunas de ellas son gratis a traves de programas de libre acceso
>como Copernicus y Lansat Open Archive.**

>Una de las aplicaciones de esta data es la clasificación de píxels en términos
>de uso de suelo, cobertura terrestre, cambios de cobertura.
>Esta gran cantidad de datos en tiempo y espacio permite desarrollar aplicaciones a escalas globales. 

## >Los algoritmos convencionale definidos para sensores remotos en pequeñas o moderadas dimensiones no escalan bien.


Estos temas son vistos en la charla "Special Issue in Classification and Feature Extraction for Remote Sensing Image Analysis",
llevada a cabo por los investigadores: 

    Dr. Mathieu Fauvel 
    Dr. Jordi Inglada 
    Dr. Marco Chini 
    Dr. Fabio Pacifici Guest Editors.
    
### Temas vistos:

    Spatial, 
    Temporal and spectral feature extraction, 
    Data-driven feature extraction, 
    Classification of multimodal remote sensing data for any thematic application (urban, agricultural or ecological ones) and for any scales, from locals to global ones.

# CÓMO PARTIR EN EL ANALISIS DE DATOS SATELITALES.

# Tutorial para descargar imagenes satelitales
**Video Tutorial https://www.youtube.com/watch?v=3_Q96HzKt40** *Obs: Desactualizado. AWS es de pago ahora.

----------------------------------------------
# HOY: Productos disponibles para satelites sentinel
## Aquí una hoja de información
        https://sentinel.esa.int/documents/247904/1848117/Sentinel-2_Data_Products_and_Access
### Lo que nos lleva a la pagina central del acceso a los datos.
        https://sentinel.esa.int/web/sentinel/sentinel-data-access



# MANOS A LA OBRA: Acceder gratis a la Data Sentinel vía Descargas.
**Existe posibilidad de acceder a la data de Sentinel. Lo único que necesitaremos es registrarnos en la plataforma del programa de Copernicus.

        https://scihub.copernicus.eu/dhus/#/home
        
### Para más información:
        https://scihub.copernicus.eu/
        
*Tambien existe la opcion de usar la data en la Nube. Ver **sentinel-data-access**.*


----------------------------------------------------------------


# Descargando la data.

# Opcion 1.
## Copernicus. Archivo Zip.

**En copernicus nos dirigimos a la área que nos interese y ponemos buscar.
*Importante fijarse en el tamaño de los archivos que descarguemos. Hay de 7Gb, 800Mb, 600Mb.
###Debemos presionar sobre el link "Download URL".

**Ejemplo de selección:

    S2B_MSIL1C_20190714T153609_N0208_R111_T20VPJ_20190714T190344
    Download URL: https://scihub.copernicus.eu/dhus/odata/v1/Products('6e2962fb-2501-478c-9f11-7b3be62973d5')/$value
    Mission: Sentinel-2  Instrument: MSI  Sensing Date: 2019-07-14T15:36:09.024Z  Size: 229.88 MB

### Se descargará un archivo ZIP.

---------------------------------------------------

# Opcion 2.
## Remote Pixel. Archivos TIF.

https://search.remotepixel.ca/#8.57/25.3266/55.3757
Desde allí seleccionamos nuestra área y la banda que queremos descargar. Nos descargará la información en 
formato TIF.
**Seleccionaremos en este ejemplo la zona de Dubai por su escaza nubosidad y por su reconocimiento a nivel global.
### Descargaremos las bandas Red, Blue y Green (RGB) correspondientes a B2, B3 y B4.

*Abrimos QGIS cargamos las imagenes TIF que se geolocalizan automaticamente.



----------------------------------------------
# Opcion 3.
## Sentinel Hub
**En SentinelHub podremos ver los distintos satelites y las bandas que combinan para cada color o vista.

          https://apps.sentinel-hub.com/eo-browser/?lat=25.1670&lng=55.2530&zoom=11
 ### Opciones dentro de SentinelHub.
 
**Tenemos un Menú.
** Elegiremos una zona de Dubai, en un día con baja Nubosidad.

    Search: Seleccionamos Sentinel 2, LC1. Del 2018 al 2019, 1 enero de cada año.
    Results: nos indica los Links de descarga. Elegimos un link de AWS o uno de Copernicus.
    Visualization: Previsualizamos nuestra elección.
    Pins

*Si elegimos el link de AWS no saldrá un link no interpretable por nuestro navegador web

        s3://sentinel-s2-l1c/tiles/39/R/ZH/2018/12/30/0
        
El link de copernicus nos descarga el mismo ZIP que en la opción 1. Por lo que no tiene gran utilidad esta tercera opción por el momento.


-----------------------------------------------

# SHAPEFILES GRILLAS SATELITES
**Si Necesitamos tener los shapefiles para QGIS de las grillas de coordenadas del satelite.**
        http://bit.ly/GrillaSentinel2
  **De allí sacamos el o los codigos de nuestra(s) area(s) de interés.
 ***Ejemplo: 20KMF, 20KMG.***






 ------------------------------------
 # ESTO YA NO FUNCIONA
 
 ## Obtención de la Data
Para obtener las imagenes existen varias opciones, existen los datos disponibles por Amazon Web Services (AWS) 
http://sentinel-pds.s3-website.eu-central-1.amazonaws.com/

Estas imágenes pueden ser descargadas con el buscador Sentinel Image browser. 
http://sentinel-pds.s3-website.eu-central-1.amazonaws.com/image-browser/
 
***Ejemplo: 20KMF, 20KMG.***

    Ese código se busca en la página de amazon, donde están los archivos a descargar de esta data.
        http://sentinel-s2-l1c.s3-website.eu-central-1.amazonaws.com/
    **Pero NO funciona el LInk. BUSCAR.... SENTINEL PUBLIC IMAGE SERVER       
    ahora es de pago con AWS: "The data is in Requester Pays S3 bucket."
    https://roda.sentinel-hub.com/sentinel-s2-l1c/readme.html

 ------------------------------------
