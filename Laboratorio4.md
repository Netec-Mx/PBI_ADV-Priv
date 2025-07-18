# Laboratorio #4: Dashboard con predicción de ingresos futuros.

## Planteamiento del ejercicio.

> Como parte de las actividades de analista de Power BI, le piden crear un panel que le permita ver la información mas relevante, y apartir de esta información poder tomar desiciones. 

>Esta información no siempre esta disponible, y en ocasiones buscamos justamente predecir estos valores antes de tenerlos. Por lo apartir del informe que se elaboró anteriormente en el ejercicio previo, lo modificaremos para agregar dos paginas nuevas y estas paginas las asignaremos a un panel.

## Objetivo

> Crear un Dashboard con analisis predictivo.

## Tiempo estimado

> Dependiendo la experiencia previa que tenga Power BI, puede que algunas de las actividades le resulten conocidas, permitiendo que elabore esta actividad en una menor cantidad de tiempo, en caso contrario, puede llegar a tomarle hasta 70 minutos para poder realizar este ejercicio de forma exitosa.

## Actividades a realizar

![Actividades a realizar.](./images/Diagrama%20Ejercicio%204.png)

## Modificar el reporte.

Ingrege al servicio de Power BI, una vez dentro de este servicio, vaya al informe que se subio en el ejercicio pasado y seleccione el icono de edicion para proceder a modificarlo.

![Actividades a realizar.](./images/E4-1.png)

Genere una nueva pagina y denominela como dispersión, en ella inserte un grafico de dispersión que abarque toda la pagina.

![Actividades a realizar.](./images/E4-2.png)

Este visual debe contener los siguientes datos:

* Eje X: Sales | Sales
* Eje Y: Sales | Profit Margin
* Leyenda: Reseller | Business Type
* Tamaño: Sales | Quantity
* Eje de reproducción: Date | Quarter

Agregue a los filtros de la pagina la catgeoria Product | Category y seleccione, por ejemplo, Bikes.

Comience con la animación y observe como la información se va actualizando con el pasar del tiempo.

Finalizando la animación seleccione cualquiera de las burbujas para ver la información a detalle y el recorrido que realiza a lo largo del tiempo.

Cambie el valor del filtro a otro tipo de producto y observe los resultados.

![Actividades a realizar.](./images/E4-3.png)

Genere una nueva pagina y denominela como Predicción, en ella inserte un grafico de lineas que abarque toda la pagina.

![Actividades a realizar.](./images/E4-2.png)

Este visual debe contener los siguientes datos:

* Eje X: Date | Date
* Eje Y: Sales | Sales

Agregue a los filtros de la pagina la catgeoria Date | Year y seleccione los años fiscales 2019 y 2020.

Agregue un control deslizante para poder ver mas o menos información dependiendo lo que desee ver.

Agregue la opción de prevision y configurela de tal forma que mida lo siguiente:

* Calcule los siguientes meses hasta llegar a finales de 2020, considere los datos de todo un año y el rango de confianza sea de un 80%.

![Actividades a realizar.](./images/E4-4.png)

El resultado al final debe quedar algo similar a lo siguiente:

![Actividades a realizar.](./images/E4-5.png)

## Crear un panel y asignarle el contenido.

De lo anterior, ahora solamente falta agregarlo a un dashboard, para ello ancle las horas del reporte en un nuevo panel para mantener los elementos interactivos dentro del panel.

> Recuerde que dependiendo que contenido fija en un panel, este elemento perderá los elementos interactivos. Si requiere mantener los elementos como estan (incluyendo sus interacciones fije siempre la hoja en lugar de la visualizacion.)

Una vez haya fijado el contenido en el panel ingrese en el y verifique el contenido.