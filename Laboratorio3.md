# Laboratorio #3: Aplicar RLS sobre un modelo y optimizar consultas lentas con análisis de rendimiento

## Planteamiento del ejercicio.

> Como parte de las actividades de analista de Power BI, le piden crear roles dentro de un modelo para impedir que la información sea visible para todos en la organización y que de esta manera, podamos tener un control mas granular para la información. Ademas de ello le piden revisar el desempeño general de un informe, con el objetivo de poder identificar posibles cuellos de botella o consultas que puedan ser optimizadas.

## Objetivo

> Implementar RLS y modificar expresiones DAX que no esten optimisadas.

## Tiempo estimado

> Dependiendo la experiencia previa que tenga Power BI, puede que algunas de las actividades le resulten conocidas, permitiendo que elabore esta actividad en una menor cantidad de tiempo, en caso contrario, puede llegar a tomarle hasta 70 minutos para poder realizar este ejercicio de forma exitosa.

## Actividades a realizar

![Actividades a realizar.](./images/Diagrama%20Ejercicio%203.png)

## Explorar los datos.

Comience abriendo el archivo denominado RLS y DAX que se encuentra dentro de la maquina virtual en la carpeta documentos. Una vez acceda al archivo, explore el contenido de este archivo, navegue y vea la información que esta disponible.

![Actividades a realizar.](./images/E3-1.png)

Apartir de sus observaciones, le piden aplicar en primer lugar una serie de roles para que, dependiendo la persona a la que le esten otorgando dicho rol, solamente pueda ver la información de un determinado grupo, fuera de eso, no deberia poder información de los otros grupos.

## Crear Roles

Con esto en mente, le piden crear 3 roles para representar cada uno de estos grupos.

* America
* Europa
* Pacifico

Pruebe cada uno de estos roles y observe que información queda disponible con cada uno de ellos.

> Puede guiarse de la siguiente imagen como referencia.

![Actividades a realizar.](./images/E3-2.png)

Si bien esta primer aproximación resulta util para poder filtrar el contenido dependiendo el grupo al que le vende uno de los vendedores, se da cuenta que los vendedores suelen vender a mas de un territorio por lo que seguir implementando este enfoque "estatico" quizas no sea lo mas conveniente. 

Por lo que le piden crear un nuevo rol, este nuevo rol debe filtrar de forma dinamica con base al correo electronico del usuario, de forma tal que solamente vea la información relacionada con este usuario, este rol de momento solamente filtrara la información de las tablas Salesperson y Salesperson Performance.

Vuelva a ver el contenido del reporte, observe que ahora el contenido se muestra unicamente cuando el correo del usuario coincide con el del usuario que ha iniciado sesión. Este tipo de filtrado dinamico lo podremos usar para poder filtrar otras tablas y el contenido de forma dinamica.

Dependiendo las expresiones DAX que sean utilizadas se podrá filtrar la información de maneras mas complejas a las que anteriormente nos solicitaron, por ejemplo en lugar de obtener el UPN, hacer busquedas con los valores que tenemos en nuestras tablas (por ejemplo el ID de los empleados) se podrán construir este tipo de expresiones.

## Explorar el rendimiento

Dejando de momento lo anterior, ahora le piden examinar el desempeño del reporte, por lo que es necesario comenzar a grabar los tiempos de respuesta dentro de las paginas del reporte y poder detectar posibles cuellos de botella.

Para obtener una medicion correcta, primero genere una nueva pagina en blanco y situela como la primer imagen del reporte.

![Actividades a realizar.](./images/E3-3.png)

Ahora vaya a los ajustes de Power BI

![Actividades a realizar.](./images/E3-4.png)

Borre todos los datos en cache que actualmente tiene Power BI.

![Actividades a realizar.](./images/E3-5.png)

Ahora guarde los cambios que ha realizado y proceda a cerrar Power BI Desktop. Esto con el objetivo de efectivamente cuando vuelva a abrir el reporte, los tiempos de carga sean lo mas limpios posibles y no se use contenido en cache.

Cuando termine de abrir de nuevo Power BI Desktop habilite el analizador de rendimiento y navegue entre las paginas y observe los resultados arrojados.

> En la imagen se observan los datos de referencia cuando se hizo este primer analisis en la pagina Overview, los datos pueden variar a los que usted obtenga.

![Actividades a realizar.](./images/E3-6.png)

Despues de interactuar y observar los resultados, no deberia tener ningun resultado donde los tiempos de respuesta de DAX sean demasiado elevados (Recordemos que tiempos de respuesta de DAX mayores a 200 son elementos que potencialmente deberiamos modificar.)

Si bien en nuestra exploracion con el conjunto de datos parece no haber resultados que sean criticos para cambiar o corregir, eso no implica que las formulas usadas para calcular las medidas o las columnas sean lo mas correctas.

Por lo anterior vaya a la vista del modelo y explore las distintas medidas que estan disponibles.

* Avg Price
* Max Price
* Median Price
* Min Price
* Order Lines
* Orders
* Profit
* Profit Margin
* Sales % All Region
* Sales % Country
* Sales % Group
* Sales YoY Growth
* Sales YTD
* Target
* Variance
* Variance Margin

Despues de observar los datos, deberia realizar algunos cambios en almenos 4 medidas. Los cambios serán principalmente sobre el uso de variables para optimizar ligeramente las consultas.

Pruebe de nuevo el desempeño para poder examinar que tanto impacto tuvo los cambios realizados con el desempeño del informe.

## Publicación en Power BI

Ya teniendo estos resultados listos y estando conformes con los resultados, ahora procederemos a publicar este reporte en el servicio de Power BI, por lo que será necesario iniciar sesión dentro de Power BI Desktop con la cuenta designada por su instructor para poder acceder.

Es hora de iniciar sesión dentro de Power BI Service. Por lo que puede usar la siguiente liga para ingresar.

https://app.powerbi.com/

Dentro del servicio de Power BI genere un area de trabajo, esta area de trabajo se denominara EjercioRLSXXXX donde cada X representan tus iniciales. Dentro de esta area de trabajo es donde subiras tu contenido.

Una vez haya creado la area de trabajado proceda a subir el contendio al servicio de Power BI. 

De nuevo en el servicio de Power BI,ahora configure la seguridad del modelo para poder fijar uno de los roles que acaba de crear a un usuario.

> En la siguiente imagen se muestra un ejemplo de un usuario asignado a uno de los roles. Apartir de asignarle este rol, ahora ese usuario podra ver la información limitada siempre y cuando sea invitado como lector.

![Actividades a realizar.](./images/E3-7.png)

Ahora que esta el rol asignado a un usuario, proceda a invitar a dicho usuario como miembro lector del area de trabajo.

![Actividades a realizar.](./images/E3-8.png)

Ahora deberia ser capaz de ver la información de forma "controlada" de acuerdo al rol que haya asignado.