![VideoClub ](https://github.com/crisgo-data/sql-data-base-building/blob/main/imagenes/video-club.jpg)



PROYECTO DE CREACIÓN DE UNA BASE DE DATOS PARA UN VIDEOCLUB

Para llevar a cabo la creación de una buena base de datos es necesario que esos datos esten revisados, limpios y listos para importarlos a SQL.



OBJETIVO


El objetivo de este proyecto es la creacíon de una base da datos para un videoclub que tiene un inventario incompleto, que tiene un disco duro del cual nos sirve solo su relación de Peliculas con Actores y del cual no nos interesan ni los datos anteriores de alquiler ni los datos de tiendas y clientes anteriores.


Nos quedamos con todas las tablas pero modificadas con los datos que realmente nos van a interesar. Por ejemplo la tabla Rental solo tendrá rental_id y inventory_id. Es una tabla a completar a partír de que se empiecen a alquilar las películas. Al igual que la tabla Inventory se deberán ir incluyendo el resto de películas.


LIMPIEZA DE DATOS


1. Existen columnas que aparecen en todas las tablas y no nos aportan ninguna información. 'Last_update'.

2. En general todas las columnas están bastante limpias, queremos que todas tengan su propio _id. Después la relacionaremos entre ellas.

3. Hay un tabla interesante que es oldhdd. En esta tenemos datos que ya pertenecen a la tabla film y otros que no nos sirven. Al final esta tabla será nuestra tabla intermedia entre la tabla 'film' y la tabla 'actor', con el _id de cada una de las tablas.

4. Obviamente al tratarse de un videoclub y que nuestro producto sean la películas, la tabla que más informació y que se relaciona con todas las demás es 'film'

Estas son las tablas, sus columnas y las conexiones que tendrán cada una de ellas:


![Diagrama relaciones ](https://github.com/crisgo-data/sql-data-base-building/blob/main/imagenes/diagrama.jpg)


Con estas relaciones ya podemos empezar a lanzar las consultas 'Querys' a la base de datos existente:



MIS QUERYS

1- Quiero saber los dos primeros actores que han hecho más peliculas en Inglés.


actor_id,  first_name    last_name   film_count
37      VAL        BOLGER       78
13      UMA        WOOD        78



2- En esta consulta quiero saber el numero de películas de la categoría 'action' se lanzaron en 2006.


count = 77



3- Quiero saber la cantidad de peliculas por genero que tengo:  pongo limit 16 ya que son 16 categorías las que tengo.

name film_count
Sports79
Action77
Animation75
Drama74
New73
Documentary72
Horror64
Foreign64
Children62
Sci-Fi58
Family57
Classics55
Music54
Travel52
Comedy46
Games38




4- Quiero saber el actor que más sale en las películas de categoría 'Comedy'.

actor_id   first_name  last_name    count
 34    AUDREY     OLIVIER    8
 37      VAL      BOLGER     8
 
 


5- Quiero saber las 5 películas de las cuales tengo más copias en mi inventario:

title copies
CONEHEADS SMOOCHY35
ACADEMY DINOSAUR32
CLASH FREDDY28
CALENDAR GUNFIGHT28
CUPBOARD SINNERS24




6- Quiero saber el número de películas por idioma. Aunque previamnete analizando los datos 
ya me di cuenta que todas eran en Inglés pero a la hora de incluir más películas en el inventario estaría bien tener la consulta para más adelante:



name      count
english   1000




7- Quiero saber el Actor que sale en la película de categía 'Horror' que más rental_rate tiene:

actor_id first_name last_name title
1       Penelope    Guinness  Rules Human 
    
    
    

8- Quiero obtener el mayor rental_rate y que me diga el nombre de las 5 primeras películas que tienen ese rental rate por orden alfabético:

 title                  rental_rate
ACE GOLDFINGER         4.99
ALADDIN CALENDAR       4.99
AMERICAN CIRCUS        4.99
APACHE DIVINE          4.99
ATTACKS HATE          '4.99'



Tenemos una base de datos consistente a la cual podemos hacerle multiples de consultas.
