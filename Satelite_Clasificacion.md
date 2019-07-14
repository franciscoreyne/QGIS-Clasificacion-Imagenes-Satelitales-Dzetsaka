# DISPONIBILIDAD DE DATOS SATELITALES Y CLASIFICACIÓN

Hoy en dia disponer de datos satelitales es totalmente facil.
Estamos hablando de datos sobre areas geograficas, imagenes satelitales en series temporales, 
imagenes de muy alta resolución espacial e imagenes hiperepectrales.

**Algunas de ellas son gratis a traves de programas de libre acceso
como Copernicus y Lansat Open Archive.**

Una de las aplicaciones de esta data es la clasificación de píxels en términos
de uso de suelo, cobertura terrestre, cambios de cobertura.
Esta gran cantidad de datos en tiempo y espacio permite desarrollar aplicaciones a escalas globales. 

## Los algoritmos convencionale definidos para sensores remotos en pequeñas o moderadas dimensiones no escalan bien.


Estos temas son vistos en la charla "Special Issue in Classification and Feature Extraction for Remote Sensing Image Analysis",
llevada a cabo por los investigadores 

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

## Obtención de la Data
Para obtener las imagenes existen varias opciones, existen los datos disponibles por Amazon Web Services (AWS) 
http://sentinel-pds.s3-website.eu-central-1.amazonaws.com/

Estas imágenes pueden ser descargadas con el buscador Sentinel Image browser. 
http://sentinel-pds.s3-website.eu-central-1.amazonaws.com/image-browser/

# Tutorial para descargar imagenes sateluitales

**Video Tutorial https://www.youtube.com/watch?v=3_Q96HzKt40**

# Shapefiles satelite
**Necesitamos tener los shapefiles para QGIS de las grillas de coordenadas del satelite.**
        http://bit.ly/GrillaSentinel2
 
 **De allí sacamos el o los codigos de nuestra(s) area(s) de interés.
 ***Ejemplo: 20KMF, 20KMG.***
 
 Ese código se busca en la página de amazon, donde están los archivos a descargar de esta data.
        http://sentinel-s2-l1c.s3-website.eu-central-1.amazonaws.com/
**Pero NO funciona el LInk. BUSCAR.... SENTINEL PUBLIC IMAGE SERVER       
ahora es de pago con AWS: "The data is in Requester Pays S3 bucket."
https://roda.sentinel-hub.com/sentinel-s2-l1c/readme.html


https://search.remotepixel.ca/#8.57/25.3266/55.3757

### Página para ver los distintos satelites y las bandas que combinan para cada color o vista.
        https://apps.sentinel-hub.com/eo-browser/?lat=25.234&lng=55.330&zoom=9&time=2018-12-30&preset=1_TRUE_COLOR&datasource=Sentinel-2%20L1C
        
        https://scihub.copernicus.eu/dhus/#/home
        
# Productos disponibles para satelites sentinel
## Aquí una hoja de información
        https://sentinel.esa.int/documents/247904/1848117/Sentinel-2_Data_Products_and_Access
### Lo que nos lleva a la pagina central del acceso a los datos.
        https://sentinel.esa.int/web/sentinel/sentinel-data-access
        
# Acceder gratis a la Data Sentinel vía Descargas.

**Existe posibilidad de acceder a la data de Sentinel. Lo único que necesitaremos es registrarnos en la plataforma del programa de Copernicus.

        https://scihub.copernicus.eu/dhus/#/home
        
        #Para más información:
        https://scihub.copernicus.eu/
        
*Tambien existe la opcion de usar la data en la Nube. Ver **sentinel-data-access**.*



