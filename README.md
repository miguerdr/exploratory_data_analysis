## Introdución 
En el siguiente proyecto trabajaremos con una serie de datos, con la que averiguaremos los factores que influyen en el precio de un vehículo

## ¿Qué vende un coche?

Eres un analista en Crankshaft List. Cientos de anuncios gratuitos de vehículos se publican en tu sitio web cada día. Necesitas estudiar los datos recopilados durante los últimos años y determinar qué factores influyen en el precio de un vehículo.

**Descripción de los datos**

Descripción de los datos

El conjunto de datos contiene los siguientes datos:
- price
- model_year
- model
- condition
- cylinders
- fuel— gasolina, diesel, etc.
- odometer— el millaje del vehículo cuando el anuncio fue publicado
- transmission
- paint_color
- is_4wd— si el vehículo tiene tracción a las 4 ruedas (tipo Booleano)
- date_posted— la fecha en la que el anuncio fue publicado
- days_listed— desde la publicación hasta que se elimina

## conclusiones
- En la muestra podemos observar valores ausentes en las columnas model_year, cylinders, odometer, paint_color, is_4wd
- Podemos ver que los valores para model_year, date_posted, no estan en el formato correcto.

- Podemos observar que solo se registran valores 1, ya que solo hay dos tipos de valores (1, 0) podemos suponer que los valores faltantes son 0, y los sustituiremos por ese valor

- Creamos un nuevo DataFrame sin valores ausentes, le pasamos la funcion value_counts para saber la frecuencia relativa en cada columna, hacemos lo mismo con el DataFrame con valores ausentes

- Tomamos los valores de mediana ya que no puede haber numeros de coma flotante para el año y sustituimos los valores ausentes 
- Ya que el numero de cilindro y el color no depende del modelo del auto, sustituiremos los valores ausentes

- Podemos ver que el porcentaje de valores ausentes es del 15.316836%, determinaremos si los valores ausentes presentan un patrón, es decir, si su aparición en el conjunto de datos es aleatoria o no.
- Ya que no hay valores atípicos significativos, aplicaremos la media del año del modelo, para rellenar valores ausentes

- Los valores ausentes pueden deverse al desconocimiento del color, estos los llenaremos con el valor Other, ya que no hay un patron entre el color del carro y algun otro factor, los datos ausentes son de tipo aleatorio, los datos ausentes se cambian por Other, ya que no hay un patron para el color y el auto

- En la columna is_4wd, en los valores de tipo booleano solo existen 2 respuestas (0, 1), en el DataFrame solo encontramos el valor 1, eso quiere decir que el valor ausente es 0
- En la columna model_year, se aplico la mediana de cada modelo de auto, ya que la media nos arroja un valor de punto flotante
- En la columna de cylinders, se ocupa la mediana de los cylindros que tiene cada modelo de auto
- En la columna Odometer, buscamos valores atipicos significativos, al no encontrar se ocupo la media de odometer para el modelo de cada año
- En esta coluumna encontramos un error en la columna 1929 y se realizo el cambio manualmente

- agragamos la columna date_end_posted, que nos indica la fecha en que el anuncio fue eliminado 
- Sustituimos los valores de la columna condition, por valores numericos mas facil de indentificar 
    + new = 5
    + like new = 4
    + excellent = 3
    + good = 2
    + fair = 1
    + salvage = 0
- En el diagrama podemos ver que hay precios arriba de 350000 y precios en cero, estos son valores atipicos, recortaremos los valores que no esten entre el 5000 hasta 34597.5
- Ya que los autos se pueden vender en condiciones de nuevo, eliminaremos los valores atipicos mayores de 24 años
- Podemos observar que los valores atipicos en nuestros datos son los millajes arriba del 269779.2978173464
- Ya que el numero de cilindros es un valor estandar del auto y no presenta valores atipicos no los eliminaremos
- Ya que el estado del auto es un valor estandar y no presenta valores atipicos no los eliminaremos
- Podemos observar una mejor distribucion de los precios en el DataFrame sin valores atipicos, y con esta informaciòn podemos observar que hay dos picos 4000, 6000 y 8000
- podemos observar picos en 4, 10 y 12 años que no se logran observar en el histograma con los datos atipicos
- Podemos observar un pico entre los valores de 10000 y 15000 millas

- El tiempo promedio de los dias anunciados es de 40 días, el anuncio mas rapido en eliminarce no duro ni un dia, y el mas prolongado fue de 271 días
- Podemos observar en el grafico que los tipos de autos con mas anuncios son 'suv' y 'sedan', de igual forma podemos observar el tipo 'Suv' tiene una correlacion mas priesio-anuncio
- Como podemos observar en el diagrama, los vehiculos con mayor numero de anuncios son SUV, Sedan, solo analizaremos estos tipos de vehiculos
- Ya que los valores de anuncios son parecidos trabajemos con la relación entre cada uno de ellos con edad, millaje por año, condición, tipo de transmisión y color.

- Podemos observar que la correlación entre precio y edad del vehiculo es -0.57, esto es muy lejano a uno, esto quiere decir que no hay relación, ya que si la edad del vehiculo aumenta, el precio del vehiculo disminuye
- Podemos observar que la correlación entre precio y millaje del vehiculo es -0.53 esto muy lejano a uno, esto quiere decir que no hay relación, esto quiere decir que entre mayor millaje, el precio disminuye
- Podemos observar que la correlación entre precio y condición del vehiculo es 0.27 mas cercano a uno, esto quiere decir que hay relación, y la condición del vehiculo si afecta el precio del mismo
- Podemos observar que la correlación entre precio y millaje por año del vehiculo es 0.25 mas cercano a uno, esto quiere decir que hay relación, el millaje del vehiculo si afecta el precio del mismo, entre menor millaje por año, menor es el precio

- En la el diagrama de cajas, podemos observar que el precio de los autos aumenta si el auto es de transmición manual
- En el diagrama de caja, podemos observar que el valor aumenta cuando el auto es color negro, naranja, y amarillo
