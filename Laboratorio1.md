# Laboratorio #1: Diseño de modelo complejo a partir de múltiples fuentes con relaciones inactivas

## Planteamiento del ejercicio.

> Como parte de las actividades de analista de Power BI, le piden crear un modelo apartir de distintas fuentes de datos, conectandolas entre si mediante las relaciones en el modelo y, creando algunas medidas que permitan analizar la información usando relaciones desactivadas.

## Objetivo

> Crear distintas medidas de DAX para repesar las funciones financieras.

## Tiempo estimado

> Dependiendo la experiencia previa que tenga Power BI, puede que algunas de las formulas les resultes conocidas, permitiendo que elabore esta actividad en una menor cantidad de tiempo, en caso contrario, puede llegar a tomarle hasta 70 minutos para poder realizar este ejercicio de forma exitosa.

## Actividades a realizar

![Actividades a realizar.](./images/Diagrama%20Ejercicio%201.png)

## Obtener los datos

Antes de poder crear el modelo, es necesario tener acceso a los datos y, por lo tanto, poder manipularlos para que puedan ser utilizados para el analisis y el modelado.

Para ello, recordemos que la información puede venir de distintos lugares, archivos locales, archivos remotos (en ubicaciones de la empresa o bien en internet), servicios especializados (Servicios de Microsfot, AWS, Google, entre un largo etcetera).

En ese sentido, de la siguiente lista se muestran los archivos que se estaran utilizando, asi como su ubicación para poder acceder a ellos.

* Empleados.xlsx - Este archivo se encuentra dentro de la carpeta documentos de la maquina virtual.

* Fechas.xlsx - Este archivo se encuentra dentro de la carpeta documentos de la maquina virtual.

* Maquinaria - Este archivo se encuentra dentro de Google Drive puedes acceder directamente usando la siguiente liga.
https://docs.google.com/spreadsheets/d/1-qGpKZzbVLMBqmVqSqjrk0n8WeymT-gg/edit?usp=sharing&ouid=107815825877798659253&rtpof=true&sd=true

* Minas - Este archivo se encuentra en una cuenta de almacenamiento de Azure puedes acceder a el utilizando la siguiente liga.
https://accesos.blob.core.windows.net/recursos/Minas.xlsx?st=2025-07-14T23:50:52Z&se=2025-12-31T08:05:52Z&si=Accesos recursos&spr=https&sv=2024-11-04&sr=b&sig=VS5bQ3R4XEDILXpMcyOc2xkGO8hP8Xu9Cof2OkoFshA%3D

* Minerales.pdf - Este archivo se encuentra dentro de la carpeta documentos de la maquina virtual.

* Producción.xlsx - Este archivo se encuentra dentro de una cuenta de almacenamiento de Azure puedes acceder a el utilizando la siguiente liga.
https://accesos.blob.core.windows.net/recursos/Producci%C3%B3n.xlsx?st=2025-07-15T00:55:37Z&se=2025-12-31T09:10:37Z&si=Accesos recursos&spr=https&sv=2024-11-04&sr=b&sig=PBhZWSjYVXEtp3FkcLZvKDRfZvG80h6YORu8VzPqoqQ%3D

* Turnos.pdf - Este documento se encuentra dentro de la carpeta documentos de la maquina virtual.

Recuerda que hay que hacer transformaciones para poder utilizar los datos.

## Crear relaciones

Hasta este punto deberiamos tener 7 consultas en el modelo, deberia verse hasta el momento algo parecido a lo siguiente:

![Actividades a realizar.](./images/E1-1.png)

Ahora genere las relaciones entre las siguientes tablas:

* Empleados[IDEmpleado] - Producción[IDEmpleado]

* Maquinaria[IDMaquinaria] - Producción [IDMaquinaria]

* Minas [IDMina] - Minas [IDMina]

* Minerales [IDCategoriaMineral] - Producción [IDCategoriaMineral]

* Turnos [IDTurno] - Producción [IDTurno]

![Actividades a realizar.](./images/E1-2.png)

---

Ahora genere las siguientes relaciones

* Fechas [Fecha] - Producción[Fecha extracción]

* Fechas [Fecha] - Producción[Fecha envio]

![Actividades a realizar.](./images/E1-3.png)

## Crear visuales

Ahora que ya hemos generado algunas relaciones, es hora de poner a prueba los resultados usando unas tablas como referencia. Para ello genere una visualización de tabla e inserte los siguientes valores:

* Fecha extracción
* IDMina
* Toneladas extraidas

Asignele un titulo, esta primer tabla la conoceremos como Tabla Eelación - Fecha extracción.

Copie la tabla y peguela, modificando los campos para ahora incluir los siguientes:

* Fecha envio
* IDMina
* Toneladas extraidas

Asignele el titulo correspondiente.

![Actividades a realizar.](./images/E1-4.png)

## Crear medidas

Ahora que tenemos la tabla que contiene los datos considerando la fecha de extracción y la de envio respectivamente, lo que buscamos ahora es crear dos medidas, estas medidas nos permitiran ver la información de la suma de lo que se ha extraido una usando la relacion predeterminada y otra usando la relación apagada.

Usaremos cada metrica con la tabla que es su contra parte, es decir la medida que usa la fecha de envio la usaremos en la tabla de extracción y viceversa.

> Dependiendo como este intentando crear la medida, o le devolvera los mismos resultados que ya tiene (la medida sigue obteniendo filtros que hacen que los calculos sean exactamente los mismos) o bien una serie de resultados dependiendo que filtro haya decidido mantener.

Tome por ejemplo la siguiente imagen de referencia donde se han quitado los filtros de las fechas, resumiendo el contenido de acuerdo con el IDMina.

![Actividades a realizar.](./images/E1-5.png)

Ahora le piden agregar las siguientes relaciones:

* Minas [Fecha apertura] - Fechas[Fecha]

* Minas [Fecha ultimo accidente] - Fechas [Fecha]

![Actividades a realizar.](./images/E1-6.png)

Estas dos relaciones nos podrian ayudar para hacer analisis de productividad desde la fecha de creación o bien datos de seguridad desde el ultimo accidente o antes del ultimo accidente.

Por ello le piden elaborar otra medida:

* Esta medida será usada con el objetivo de medir la cantidad de Toneladas extraidas desde la fecha de creación de la mina.

![Actividades a realizar.](./images/E1-7.png)

![Actividades a realizar.](./images/E1-8.png)
