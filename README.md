# QGIS-ML


Dzetsaka (https://github.com/lennepkade/dzetsaka) sirve para hacer clasificaciones del territorio en imagenes georeferenciadas de las cuales se tengan muestras de territorio clasificados.

INTRODUCCION

Haremos una clasificacion del territorio usando el ejemplo que provee dzetsaka (https://github.com/lennepkade/dzetsaka/archive/docs.zip). 
Dentro de la carpeta sample se encuentran el archivo (demo_dzetsaka.qgs) que cargaremos como proyecto en QGIS.
Para hacer una clasificacion con dzetsaka se necesitan dos cosas, un raster y un shapefile. 
El shapefile debe contener las variables ordinales. Debemos considerar que Dzetsaka no entiende las variables tipo texto.
Por lo que debemos transformar nuestras variables ordinales en números (Tabla de atributos del shapefile).

Necesitaremos instalar (en WINDOWS):
- QGIS
- OsGeo shell para instalar sckit-learn.
- Scikit-learn (paquete de python, dentro de QGIS).
- El complemento DZETSAKA en QGIS para hacer la clasificacion (disponible en https://github.com/lennepkade/dzetsaka)

---------------------------------------------------

PARTE1. DESCRIPCION DE LAS INSTALACIONES.



QGIS:

Descargamos e instalamos QGIS.  Instalador autónomo de QGIS Version 3.8 (64 bit). 
(disponible en https://qgis.org/es/site/forusers/download.html)



OsGeo Shell y Scikit-learn:

Para hacer corer dzetsaja necesitamos OsGeo Shell que se usa para instalar scikit-learn en QGIS.
Instalamos osgeo4w (disponible en http://trac.osgeo.org/osgeo4w/)
Abrimos OsGeo shell en modo administrador y ejecutamos los siguientes comandos:

#py3_env.bat

#pip install scikit-learn



DZETSAKA:

En QGIS vamos a Complementos y descargamos el complemento "dzetsaka : Classification tool".

-------------------------------------------------

PARTE 2. CLASIFICACION DE IMAGENES.


En QGIS abrimos nuestro proyecto del ejemplo de dzetsaka (https://github.com/lennepkade/dzetsaka/archive/docs.zip) 
proyecto Qgis llamado "demo_dzetsaka.qgs" dentro de la carpeta sample.


Abrimos el complemento Dzetsaka. Cargamos en la imagen el mapa "map" (formato GeoTIFF).
Luego cargamos nuestro shapefile llamado "train" (formato ESRI Shapefile) con los polígonos de ejemplo ya clasificados. 
Despues debemos seleccionar la columna que contiene la clase en números.

·Para ver cual está en números vamos a hacer click derecho sobre el shapefile "train" y veremos que tiene dos variables.
·Está la variable "Type" que indica el tipo de territorio en texto mientras que la variable "Class" lo indica en números. 
·Por lo tanto seleccionamos la columna Class por ser de tipo numérico.

Ya tenemos seleccionado lo que nos pide DZETSAKA: map, train y Class.

Antes de hacer click sobre "Perform the clasification", presionamos sobre la pestaña desplegable 'Optional'.

Seleccionamos las opciones "Save matrix" (guardamos como CMM1.csv) y "Confidence map" (guardamos como CMM1.tif). 
Estas dos opciones nos permitiran evaluar los resultados de nuestros modelos.

En Split ponemos 75%. Esta proporción correspondrá al tamaño de datos a usar para entrenar (train) al modelo.

El 25% lo utilizará para comprobar (test) que tan bueno es nuestro modelo.

Presionamos sobre la figura de configuracion, al lado derecho del boton "Perform the clasification".
Se nos abrirá una ventana emergente donde seleccionaremos en 'Clasifier' el tipo de modelo a utilizar para realizar nuestra clasificación
El 'Clasifier' corresponde al modelo de aprendizaje que utizará Dzetsaka para identificar los objetos que le enseñaremos.

Tenemos los siguientes modelos de clasificacion:

-GMM: Gaussian Mixture Model
-RF: Random Forest
-SVM: Support Vector Machines.
-KNN: K-Nearest Neighbors.

Seleccionamos GMM y cerramos esa ventana. Ejecutamos la clasificación presionando sobre "Perform the clasification".
Nos deberan aparecer dos objetos en el visor de capas de QGIS. 
Una llamada map_class (formato GeoTIFF) y otra llamada CMM1 (formato GeoTIFF).



Vamos a la tabla de atributos del shapefile 'train' y anotamos los números asignados a cada categoria,
que aparecen en la columna Class.
"Agriculture": 2
"Buildings": 5
"Forest": 1 
"Grey": 3 
"Water": 4.


Hacemos click derecho sobre la imagen "map_class" que fue3 creada luego de ejecutar nuestra clasificacion.
Seleccionamos 'Simbología' y en "Tipo de renderizador" elegimos 'Valores en paleta/únicos'. 

Luego hacemos click en el simbolo "+" cinco veces para agregar un color a cada categoria de nuestro shapefile (Y que hemos clasificado).

Recordemos que estas cinco categorias vienen inicialmente en nuestro set de datos del train, que estaban en el shapefile "train".
Ahí encontramos las cinco categorias: "Agriculture", "Buildings", "Forest", "Grey" y "Water".
Asiganmos un color a cada categoria. 

Yo las dejé así:

Forest 1 verde. Agriculture 2 cafe. Grey 3 gris. "Water": 4 celeste. "Buildings": 5 negro. 


Siguiente mision: 

https://www.karasiak.net/dzetsaka-how-to-make-your-first-classification-in-qgis/


---------------------------------------
(OPCIONAL) 


Podemos modificar el shapefile para agregar nuevas categorias si lo quisieramos. Yo agregué dos categorias más. 
Una para las lineas rojas que dividen ciertas zonas del mapa y otras zonas que parecen ser bosques más oscuros.
Cree distintos polígonos y les asigné a cada uno un nombre comun. Llene segun esto los datos de "Type" (de tipo texto)
y "Class" (de tipo numérica) según su categoria.
Para esto hacemos click sobre el Lapiz (Conmutar edicion) y luego sobre Añadir polígono. Agregaramos y asignamos las variables 
de type y class correspondientes.
