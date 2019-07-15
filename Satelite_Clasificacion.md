# DISPONIBILIDAD DE DATOS SATELITALES Y CLASIFICACIÓN

>Hoy en dia disponer de datos satelitales es totalmente facil.

>Estos datos corresponden a información sobre areas geograficas, imagenes satelitales en series temporales, 
>imagenes de muy alta resolución espacial e imagenes hiperepectrales.


<a href="https://github.com/franciscoreyne/QGIS-ML/blob/master/CLASlite%20Workflow.jpg"><img src="https://github.com/franciscoreyne/QGIS-ML/blob/master/CLASlite%20Workflow.jpg" /></a>

## Algunas de estas fuentes de datos son gratis. Para tener acceso usamos Copernicus o Lansat Open Archive.

>Una de las aplicaciones de esta data es la clasificación de píxels en términos
>de uso de suelo, cobertura terrestre, cambios de cobertura.
>Esta gran cantidad de datos en tiempo y espacio permite desarrollar aplicaciones a escalas globales. 

## Los algoritmos convencionale definidos para sensores remotos en pequeñas o moderadas dimensiones no escalan bien.


Estos temas son vistos en la charla "Special Issue in Classification and Feature Extraction for Remote Sensing Image Analysis",
llevada a cabo por los investigadores: 

    Dr. Mathieu Fauvel 
    Dr. Jordi Inglada 
    Dr. Marco Chini 
    Dr. Fabio Pacifici Guest Editors.
    
### Temas vistos:

 >  Spatial, 
   > Temporal and spectral feature extraction, 
  >  Data-driven feature extraction, 
  >  Classification of multimodal remote sensing data for any thematic application (urban, agricultural or ecological ones) and for any scales, from locals to global ones.

# CÓMO PARTIR EN EL ANALISIS DE DATOS SATELITALES.

Usaremos datos provenientes de satelites llamados Sentinels que son la la agencia europea espacial. 

>Valen la pena los Satelites Sentinel de la ESA (European Space Agency) en comparaciòn a Landsat?
>
> Sentinel-2a y 2b tienen una visibilidad de 10 metros en la visible y near-infrared. Tiene 12 bandas espectrales y es gratis para las masas.
> Sentinel-1 tiene Apertura Radar en Banda-C Sintetica (C-band Synthetic Aperture Radar) para el mundo completo.

>Los satelites Sentinel entregan datos activos y pasivos de alta calidad para la Tierra completa.

> El hub de Sentinel (Sentinels Scientific Data Hub) es el sitio oficial para las descargas.

# MANOS A LA OBRA: Acceder gratis a la Data Sentinel vía Descargas.

        


----------------------------------------------
# Productos disponibles HOY y gratis de satelites Sentinel
----------------------------------------------
----------------------------------------------


# Descargando la Data.
## Lee primero cada una de las tres opciones que mostraré a continuación, antes de elegir la que más se acomode a lo que quieres hacer.


# Opcion 1.
## Copernicus. Archivo Zip.
**¿Cómo acceder a la data de Sentinel?. Lo único que necesitamos es registrarnos en la plataforma de Copernicus.**

*En copernicus nos dirigimos a la zona o área geografica que nos interese y presionamos sobre el boton "Buscar".*
        
        https://scihub.copernicus.eu/dhus/#/home
        
**Importante fijarse en el tamaño de los archivos que descarguemos. Hay de 7Gb, 800Mb, 600Mb.**

### Debemos presionar sobre el link "Download URL".

**Ejemplo de selección:**

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
**Seleccionaremos en este ejemplo la zona de Dubai por su escaza nubosidad y por su reconocimiento a nivel global.**
### Descargaremos las bandas Red, Blue y Green (RGB) correspondientes a B2, B3 y B4.

*Abrimos QGIS cargamos las imagenes TIF que se geolocalizan automaticamente.*


## **Las bandas que podemos encontrar en esta plataforma son las siguientes:**

    B1 - Coastal aerosol
    B2 - Blue
    B3 - Green
    B4 - Red
    B5 - Near Infrared
    B6 - Shortwave Infrared 1
    B7 - Shortwave Infrared 2
    B8 - Panchromatic (15m)
    B9 - Cirrus
    B10 - Thermal Infrared 1
    B11 - Thermal Infrared 2
    BQA - Quality Assessment
    MTL - Metadata


<a href="https://github.com/franciscoreyne/QGIS-Clasificacion-Imagenes-Satelitales-Dzetsaka/blob/master/espectros.png"><img src="https://github.com/franciscoreyne/QGIS-Clasificacion-Imagenes-Satelitales-Dzetsaka/blob/master/espectros.png" /></a>


----------------------------------------------
# Opcion 3.
## Sentinel Hub. Archivo ZIP.
**En SentinelHub podremos ver los distintos satelites y las bandas que combinan para cada color o vista.**

          https://apps.sentinel-hub.com/eo-browser/?lat=25.1670&lng=55.2530&zoom=11
 ### Opciones dentro de SentinelHub.
 
**Tenemos un Menú.**
**Elegiremos una zona de Dubai, en un día con baja Nubosidad.**

    Search: Seleccionamos Sentinel 2, LC1. Del 2018 al 2019, 1 enero de cada año.
    Results: nos indica los Links de descarga. Elegimos un link de AWS o uno de Copernicus.
    Visualization: Previsualizamos nuestra elección.
    Pins

*Si elegimos el link de AWS nos saldrá un link no interpretable por nuestro navegador web*

        s3://sentinel-s2-l1c/tiles/39/R/ZH/2018/12/30/0
        
*Si elegimos el link de Copernicus, se nos descargará el mismo ZIP que en la Opción 1.* 
**Por lo que no tiene gran utilidad esta tercera opción por el momento.**


-----------------------------------------------


-----------------------------------------------
# OPCION GANADORA: Opción 2.
# Remote Pixel. Archivos TIF.

Una vez tengamos los archivos de imagen TIF en bandas Red, Green y Blue las combinaremos en una sola para hacer nuestro
aprendizaje automatico.

# Combinación de BANDAS
## Instalamos MultiSpec.
**MultiSpec nos permite combinar imagenes de distintas bandas.** 
*Nosotros uniremos las de las bandas* **RED, GREEN Y BLUE (RGB)** *para tener una imagen en colores.*

Link de MultiSpec para su descarga:

        https://engineering.purdue.edu/~biehl/MultiSpec/download_win.html

## Combinación de varias imagenes TIF en una sola.
En MultiSpec abrimos las tres imagenes al mismo tiempo. Se nos deberá abrir una sola imagen a colores. 
**Guardamos el resultado como prueba_RGB en formato TIF.

# Abrimos el TIF prueba_RGB en QGIS.

# Generamos nuestro shapefile con nuestros propios ejemplos de clasificación. Yo hice figuras sobre el mar, zonas de tierra, construcciones y otras zonas de nada (representa el área negra o sin información de la imagen).

<a href="https://github.com/franciscoreyne/QGIS-ML/blob/master/dubai.png"><img src="https://github.com/franciscoreyne/QGIS-ML/blob/master/dubai.png" /></a>

# Hacemos la clasificación con Dzetsaka.

<a href="https://github.com/franciscoreyne/QGIS-ML/blob/master/dubai2.png"><img src="https://github.com/franciscoreyne/QGIS-ML/blob/master/dubai2.png" /></a>


------------------------------------------------
------------------------------------------------
# El fin.
# The End.

------------------------------------------------
------------------------------------------------

# Próximos desafios:

*Ver la reducción de hielos glaciares. Zona central Chile.*
*Ver la alteracion de Humedales en zona central*
__Ver la alteración de Humedales Ramsar__
**Buscar impactos del Cambio Climático o Climate Change en Chile.**

------------------------------------------------
------------------------------------------------

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
 ------------------------------------
 ------------------------------------
# Info extra
### Aquí una hoja de información
        https://sentinel.esa.int/documents/247904/1848117/Sentinel-2_Data_Products_and_Access
### Pagina central de acceso a los datos Sentinel.
        https://sentinel.esa.int/web/sentinel/sentinel-data-access
        
## Tutorial para descargar imagenes satelitales
**Video Tutorial https://www.youtube.com/watch?v=3_Q96HzKt40** 
*Observación: el video está desactualizado. AWS es de pago ahora.

*Tambien existe la opcion de usar la data en la Nube. Ver **sentinel-data-access**.*
### Más información:
        https://scihub.copernicus.eu/
----------------------------------------------------------------

Links relacionados:

## Complementos QGIS para Clasificación Supervisada con Imágenes Sentinel-2
https://carbajallosa.blogspot.com/2017/07/complementos-qgis-para-clasificacion.html

**Tutorial - [Como descargar Sentinel 2 por grillas]
 
        https://www.youtube.com/watch?v=3_Q96HzKt40
        

## Estimation and mapping of forest stand density, volume, and cover type using the k-nearest neighbors method.

        https://www.sciencedirect.com/science/article/abs/pii/S0034425701002097
        

## Otros.
https://www.karasiak.net/dzetsaka-how-to-make-your-first-classification-in-qgis/
https://joseguerreroa.wordpress.com/2011/09/06/combinacion-de-bandas-landsat-usando-gdal/
https://engineering.purdue.edu/~biehl/MultiSpec/download_win.html
https://engineering.purdue.edu/~biehl/MultiSpec/tutorials/20180806_Nexus_Remote_Sensing_Exercise_Spanish.pdf
http://geoapis.sourcepole.com/qgispyapi/qgsvectorlayer
https://docs.qgis.org/3.4/en/docs/pyqgis_developer_cookbook/intro.html#python-plugins


## Data.
https://gisgeography.com/free-satellite-imagery-data-list/

https://www.usgs.gov/land-resources/nli/landsat/data-tools
https://www.usgs.gov/land-resources/eros/lcmap/lcmap-sample-products?qt-science_support_page_related_con=0#qt-science_support_page_related_con

### AWS - SENTINEL 2
https://aws.amazon.com/es/blogs/publicsector/complete-sentinel-2-archives-freely-available-to-users/
https://registry.opendata.aws/
https://registry.opendata.aws/sentinel-2/



https://search.remotepixel.ca/#7.85/25.954/55.709

### SAGA
https://www.geosci-model-dev.net/8/1991/2015/
***Normalised burn ratio Tutorial SAGA saga system for automated geoscientific analyses.

        https://www.youtube.com/watch?v=HtWyf7QnzqA


## Python y R
https://kodu.ut.ee/~kmoch/geopython2018/lessons/L2/projections.html
https://github.com/volaya
http://geopandas.org/install.html

## GitHub
https://github.com/ricval/Documentacion/blob/master/Guias/GitHub/mastering-markdown.md
