# Laboratorio #2: Construcción de un set de medidas avanzadas para análisis financiero y productivo

## Planteamiento del ejercicio.

> Como parte de las actividades de analista de Power BI, le piden crear distintas medidas con DAX para poder utilizarlas en contexto financieros, si bien aun no le piden aplicarlos sobre un reporte que actualmente este corriendo, le comentan que necesita comprender y tener preparados los distintos metodos de estas funciones.

## Objetivo

> Crear distintas medidas de DAX para repesar las funciones financieras.

## Tiempo estimado

> Dependiendo la experiencia previa que tenga Power BI / Excel, puede que algunas de estas formulas les resultes conocidas, permitiendo que elabore esta actividad en una menor cantidad de tiempo, en caso contrario, puede llegar a tomarle hasta 70 minutos para poder realizar este ejercicio de forma exitosa.

## Actividades a realizar

![Actividades a realizar.](./images/Diagrama%20Ejercicio%202.png)

### Abrir el archivo y crear 2 visualizaciones de referencia.

En este punto abra el archivo PrimerasFunciones que se encuentra en la carperta documentos dentro de la maquina virtual.  

En el creará una visualización de tabla que contenga los detalles del préstamo. Asignele un titulo como Detalles del préstamo

    > IDPrestamo  
    Nombre del préstamo
    Vida (Años)
    Fecha de pago
    Tasa Anual
    Pago
    Tasa
    Numero periodos
    Valor presente
    Tipo

Ahora copie y pegue la tabla para tener una copia de los Detalles del prestamo, sobre esta segunda tabla iremos mostrando los calculos de las medidas por lo que asignele un titulo como Detalles con DAX.

> Puede tomar de referencia la siguiente imagen.

![Creación de las tablas.](./images/E2-1.png)


Ahora sobre la tabla de Detalles con DAX, asegurese de dejar solamente los valores de las siguientes columnas:

    > IDPrestamo  
    Nombre del préstamo
    Vida (Años)
    Fecha de pago
    Tasa Anual

![Creación de las tablas.](./images/E2-2.png)


Para evitar cualquier duda con los datos que se estan utilizando, se deja esta breve explicación de cada uno de los campos.    

Tasa - La tasa de interés por período. En este caso mensual, de forma tal que, se toma la tasa anual y se divide entre el numero de periodos (12) para obtenerla.

Pago - El pago realizado en cada período. Este pago incluye capital e intereses, pero no otras tarifas o impuestos.

Numero periodos - El número total de períodos de pago.

Valor presente - Cantidad total que vale una serie de pagos futuros en
actualidad.

Valor futuro – Saldo de efectivo que espera alcanzar.

Tipo: Indica cuándo vencen los pagos.
0 - Los pagos vencen al final del período
1 - Los pagos vencen al comienzo del período

### Creación de los calculos.

Considerando lo anterior, le piden elaborar un calculo que le permita obtener el monto del pago que se tiene que realizar, dicho calculo se denominará Pago calculado, una vez realizado este valor agreguelo a la segunda tabla.

> Considera que teniendo los siguientes datos se puede calcular cual es el monto a pagar:  
* Tasa de interés
* Numero de períodos 
* Valor presente.

> Recuerda darle formato de divisa a este calculo, considera que para este ejemplo, la exactitud de los decimales debe ser de 2 digitos y, por ultimo, no se resuma este dato.

![Creación de las tablas.](./images/E2-3.png)


---

Ahora le piden elaborar un calculo que le permita obtener la tasa de interes del credito, se denominará Tasa calculada, una vez obtenido este valor agreguelo a la segunda tabla.

> Considera que teniendo los siguientes datos se puede calcular cual es la tasa:  

* Numero de períodos
* Pago 
* Valor presente.
* Valor Futuro
* Tipo
* Tasa anual

> Recuerda darle formato de porcentaje a este calculo, considera que para este ejemplo, la exactitud de los decimales debe ser de 2 digitos y, por ultimo, no se resuma este dato.

![Creación de las tablas.](./images/E2-4.png)

---

Ahora le piden elaborar un calculo que le permita obtener la cantidad de periodos, se denominará Periodos calculados, una vez obtenido este valor agreguelo a la segunda tabla.

> Considera que teniendo los siguientes datos se puede calcular la longitud de periodos:  

* Tasa anual
* Pago 
* Valor presente.
* Valor Futuro
* Tipo

> Recuerda darle formato de numero entero a este calculo y, por ultimo, no se resuma este dato.

![Creación de las tablas.](./images/E2-5.png)

---

Ahora le piden elaborar un calculo que le permita obtener el valor presente, se denominará Valor presente calculado, una vez obtenido este valor agreguelo a la segunda tabla.

> Considera que teniendo los siguientes datos se puede calcular la longitud de periodos:  

* Tasa anual
* Numero periodos
* Pago 
* Valor Futuro
* Tipo

> Recuerda darle formato de divisa a este calculo con una presición de dos decimales y, por ultimo, no se resuma este dato.

![Creación de las tablas.](./images/E2-5-1.png)

---

Ahora le piden elaborar un calculo que le permita obtener el valor futuro, se denominará Valor futuro calculado, una vez obtenido este valor agreguelo a la segunda tabla.

> Considera que teniendo los siguientes datos se puede calcular la longitud de periodos:  

* Tasa anual
* Numero periodos
* Pago 
* Valor presente
* Tipo

> Recuerda darle formato de divisa a este calculo con una presición de dos decimales y, por ultimo, no se resuma este dato.

---

### Abrir el segundo archivo y crear las tablas.

En este punto abra el archivo SegundasFunciones que se encuentra en la carperta documentos dentro de la maquina virtual.  

En el creará una visualización de tabla que contenga los detalles de los activos, a esta primer tabla le pondremos el titulo de Depreciación en línea recta.

> Fecha de compra  
ID Activo  
Nombre del activo  
Costo  
Valor de recuperación  
Periodo de vida  

Una vez tenga esta tabla, copiela y peguela 3 veces, para tener un total de 4 tablas, posicionelas en el lienzo de tal forma que los datos queden ordenados.

Asigneles a las copias los siguientes titulos:
* Depreciación de dígitos de suma de años
* Depreciación de saldo decreciente fija
* Depreciación de saldo decreciente doble

![Creación de las tablas.](./images/E2-6.png)

---

Sin entrar mucho en detalle de las implicaciones y formas de depresiación que se pueden llevar acabo, y el marco legal aplicable para cada país, podemos observar que indistintamente de estos aspectos los parametros son muy similares para estas operaciones.

Los argumentos/parámetros compartidos son:

Costo: el costo inicial del activo. 

Valor de salvamento: el valor al final de la depreciación.

Periodo de vida: el número de períodos durante los cuales se deprecia el activo.

---

Ahora le piden elaborar un calculo que le permita obtener la depreciación de un activo, donde el monto por depreciar será el mismo durante todos los periodos, este valor se denominará Depreciación Linea Recta, una vez obtenido este valor agreguelo a la segunda tabla.

> Considera que teniendo los siguientes datos se puede calcular la depresiación:  

* Costo
* Valor de recuperacion
* Periodo de vida

> Recuerda darle formato de divisa a este calculo con una presición de dos decimales y, por ultimo, no se resuma este dato.

![Creación de las tablas.](./images/E2-7.png)

---

Ahora le piden elaborar un calculo que le permita obtener la depreciación de un activo, donde el monto por depreciar incialmente sea mas elevado y, posteriormente, será mas bajo, este valor se denominará DepreciaciónSA17 y representará el valor a depreciar en el primer año, una vez obtenido este valor agreguelo a la segunda tabla.

> Considera que teniendo los siguientes datos se puede calcular la depresiación:  

* Costo
* Valor de recuperacion
* Periodo de vida
* Tiempo de depreciación

> Recuerda darle formato de divisa a este calculo con una presición de dos decimales y, por ultimo, no se resuma este dato.

Haga lo mismo ahora para el año 2018, 2019, 2020, 2021.

![Creación de las tablas.](./images/E2-8.png)

---

Ahora le piden elaborar un calculo que le permita obtener la depreciación de un activo, donde el monto por depreciar incialmente sea mas elevado y, posteriormente, será mas bajo, este valor se denominará DepreciaciónSF17 y representará el valor a depreciar en el primer año, una vez obtenido este valor agreguelo a la segunda tabla.

> Considera que teniendo los siguientes datos se puede calcular la depresiación:  

* Costo
* Valor de recuperacion
* Periodo
* Numero de meses para el primer año

> Recuerda darle formato de divisa a este calculo con una presición de dos decimales y, por ultimo, no se resuma este dato.

Haga lo mismo ahora para el año 2018, 2019, 2020, 2021.

![Creación de las tablas.](./images/E2-9.png)

---

Ahora le piden elaborar un calculo que le permita obtener la depreciación de un activo, usando el metodo de saldo decreciente doble este valor se denominará DepreciaciónDD17 y representará el valor a depreciar en el primer año, una vez obtenido este valor agreguelo a la segunda tabla.

> Considera que teniendo los siguientes datos se puede calcular la depreciación:  

* Costo
* Valor de recuperacion
* Periodo de vida
* Periodo

> Recuerda darle formato de divisa a este calculo con una presición de dos decimales y, por ultimo, no se resuma este dato.

Haga lo mismo ahora para el año 2018, 2019, 2020, 2021.

![Creación de las tablas.](./images/E2-10.png)
