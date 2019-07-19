# ¿Cómo calcular las hectareas de cada categoria de nuestra clasificacion?
Ya tenemos nuestras imagenes satelitales con sus áreas clasificadas, pero ahora queremos hacer comparaciones temporales.
**Para hacer estas comparaciones calcularemos las áreas de cada categoría clasificada autmaticamente con Dzetsaka.**
### *Así veremos cómo varía cada categoria en el tiempo.*


## Buscamos que tengamos instalado el complemento "Processing". Si no, debemos activarlo.
# Luego, vamos a :

    Procesos ‣ Caja de Herramientas ‣ GRASS ‣ Ráster ‣ r.report (hacemos doble click).
> 
>  
> Seleccionamos nuestra imagen tiff generada con nuestra clasificación. 
>
> Debemos indicar para los parámetros de la ventana del r.report, los siguientes valores:
>     
>     Raster layer(s) to report on //seleccionamos nuestra imagen Tiff con nuestra clasificación.
>     Unidades //sleccionamos h para hectareas
     
     
     Lo demas lo dejamos por defecto y creamos un archivo para nuestros resultados.
     
     
     
### Una vez finalizado nos dejará un archivo txt con nuestros resultados.
## abrir el .txt en excel como archivo delimitado por comas, con delimitador |.
**Ahí nos indicará nuestra área para cada categoría. Con estos datos podremos hacer nuestros analisis estadísticos.**


# El FIN.
