# Proyecto streaming

## 1. Elección de la base de datos a utilizar. 

Nos fueron provistas tres bases de datos:

	* movies_dataset.csv 
	* movies_dataset.xlsx 
	* movies_dataset(1).xlsx 

Las mismas se encuentran en: *https://drive.google.com/drive/folders/1KSWEKuOyyQ_5INWQHApqwBSXgdQ1HkLg* 

En el archivo [ 1_seleccion_de_base_de_datos_movies.ipynb](https://github.com/rominaEsc/project_streaming/blob/main/1_seleccion_de_base_de_datos_movies.ipynb "archivo 1_seleccion_de_base_de_datos_movies.ipynb") se comparan los tres datasets y se justifica la elección de [movies_dataset.csv](https://github.com/rominaEsc/project_streaming/blob/main/data/movies_dataset.csv "movies_dataset.csv") como base de datos a utilizar en el proyecto.

## 2. Modelar la Base de Datos

Primero, necesitamos identificar las entidades y sus atributos.

**Entidades y Atributos:**

* **movies:** id_movie, title, tagline, overview, runtime, release_date, release_year, status, popularity, vote_average, vote_count, budget, revenue, return

* **collections**: id_collection, name_collection
* **movies_collections**: id_collection, id_movie

<!-- 
* **production_companies**: id_production_companies, name_production_companies
* **movies_production_companies**: id_movie, id_production_companies


* **production_countries:** id_production_countries,	name_production_countries
* **movies_production_countries:** id_movie, id_production_countries
-->

* **genres:** id_genre, name_genre
* **movies_genres:**  id_movie, id_genre

<!--
* **languages:**	id_language, name_language
* **movie_spoken_language:** id_movie, id_language
* **movie_original_language:** id_movie, id_language
-->

## 3. Crear Tablas en Python 
**Requerimientos**

Se solicitan los siguientes requerimientos:

1. Eliminar las columnas que no serán utilizadas, video,imdb_id,adult,original_title,poster_path y homepage. 

3. Los valores nulos de los campos revenue, budget deben ser rellenados por el número 0.

5. Los valores nulos del campo release date deben eliminarse.

7. Crear la columna con el retorno de inversión, llamada return con los campos revenue y budget, dividiendo estas dos últimas revenue / budget, cuando no hay datos disponibles para calcularlo, deberá tomar el valor 0.

9. De haber fechas, deberán tener el formato AAAA-mm-dd, además deberán crear la columna release_year donde extraerán el año de la fecha de estreno.

11. Algunos campos, como belongs_to_collection, production_companies y otros (ver diccionario de datos) están anidados, esto es o bien tienen un diccionario o una lista como valores en cada fila, ¡deberán desanidarlos y unirlos al dataset de nuevo para hacer alguna de las consultas de la API! O bien buscar la manera de acceder a esos datos sin desanidarlos.

En el archivo [2_ETL.ipynb](https://github.com/rominaEsc/project_streaming/blob/main/2_ETL.ipynb "2_ETL.ipynb") se realiza la extracción, transformación y carga de los datos utilizando Python.

------------


------------

EN CONSTRUCCION:

## 4. Cargar Datos en MySQL 
Crearemos las tablas y cargaremos los datos en MySQL.


## 5. Diagrama de Entidad-Relación 
Usaremos MySQL Workbench para visualizar el diagrama de entidad-relación (ERD) de nuestra base de datos.

## 6. Consultas SQL 
Ejecutaremos consultas SQL para explorar y analizar los datos.

## 7. Desarrollo API:
Crear 6 funciones para los endpoints que se consumirán en la API.

- **def peliculas_mes(mes):** '''Se ingresa el mes y la funcion retorna la cantidad de peliculas que se estrenaron ese mes (nombre del mes, en str, ejemplo 'enero') historicamente''' return {'mes':mes, 'cantidad':respuesta}

- **def peliculas_dia(dia):** '''Se ingresa el dia y la funcion retorna la cantidad de peliculas que se estrenaron ese dia (de la semana, en str, ejemplo 'lunes') historicamente''' return {'dia':dia, 'cantidad':respuesta}

- **def franquicia(franquicia):** '''Se ingresa la franquicia, retornando la cantidad de peliculas, ganancia total y promedio''' return {'franquicia':franquicia, 'cantidad':respuesta, 'ganancia_total':respuesta, 'ganancia_promedio':respuesta}

- **def peliculas_pais(pais):** '''Ingresas el pais, retornando la cantidad de peliculas producidas en el mismo''' return {'pais':pais, 'cantidad':respuesta}

- **def productoras(productora):** '''Ingresas la productora, retornando la ganancia total y la cantidad de peliculas que produjeron''' return {'productora':productora, 'ganancia_total':respuesta, 'cantidad':respuesta}

- **def retorno(pelicula):**'''Ingresas la pelicula, retornando la inversion, la ganancia, el retorno y el año en el que se lanzo''' return {'pelicula':pelicula, 'inversion':respuesta, 'ganacia':respuesta,'retorno':respuesta, 'anio':respuesta}


## 8. Deployment
Realizar el deployment para poder consumir la API


## 9. Dashboard en Power BI 
Conéctaremos la base de datos MySQL desde Power BI y crearemos visualizaciones interactivas para mostrar los insights encontrados.

