# Comandos mas utilizados en SQL 

## SELECT

>[!NOTE]
>Utilizamos el comando `SELECT` para seleccionar elementos de tablas

`SELECT * FROM users;` -> Seleccionar todos los elementos de la tabla users

`SELECT name FROM users;` -> Seleccionar la columna name de la tabla users

`SELECT user_id, name FROM users;` -> Seleccionar la columna user_id y la columna name de la tabla users

## DISTINCT

>[!NOTE]
>Utilizamos el comando `DISTINCT` para selecionar elmentos distintos

`SELECT DISTINCT * FROM users;`-> Seleccionar todos los elementos distintos de la tabla users

`SELECT DISTINCT name FROM users;` -> Seleccionar los elementos distintos de la columna name 

`Select DISTINCT users_id FROM users;` -> Seleccionar los elementos distintos de la columna users_id 

## WHERE

>[!NOTE]
>Utilizamos el comando `WHERE` para selecionar elementos que cumplan una condicion

`SELECT * FROM users where age = 15;`-> Seleccionar todos los elementos de la tabla en que 'age' sea igual a 15

`SELECT name FROM users where age = 15;` -> Seleccionar los elementos de la tabla name que tengan la columna age igual a 15 

`SELECT DISTINCT age FROM users where age = 15;` -> Seleccionar los elemenos distintos de la columna age que tengan su valor igual a 15

## ORDER BY

>[!NOTE]
>Utilizamos el comando `ORDER BY` para ordenar elementos

`SELECT * FROM users order by age DESC;` -> Seleccionar todos los elementos de la tabla y ordenarlos por la columna age de forma descendente

`SELECT * FROM users order by age ASC;` -> Seleccionar todos los elementos de la tabla y ordenarlos por la columna age de forma ascendente

`SELECT * FROM users WHERE email='sara@gmail.com' order by age DESC;` -> Seleccionar todos los elementos de la tabla donde tengan como valor 'sara@gmail.com' en la columna email  y ordenarlos por la columna age de forma descendente

## LIKE

>[!NOTE]
>Utilizamos el comando `LIKE` para seleccionar elementos que contengan valores dentro de los valores de las columnas

`SELECT name FROM users WHERE email LIKE '%gmail.com';` -> Seleccionar los elementos de la columna name donde la columna email contenga 'gmail.com' al final de su valor

`SELECT name FROM users WHERE email LIKE 'sara%';` -> Seleccionar los elementos de la columna name donde la columna email contenga 'sara'al principio en su valor

`SELECT name FROM users WHERE email LIKE '%@%';` -> Seleccionar los elementos de la columna name donde la columna email contenga '@' en el medio de su valor


## AND/OR/NOT 

>[!NOTE]
>Utilizamos el comando `AND` para seleccionar elementos que cumplan 2 condiciones
>Utilizamos el comando `OR` para seleccionar elementos que cumplan una de 2 condiciones
>Utilizamos el comando `NOT` para selecionar elementos que no cumplan una condicion

`SELECT name FROM users WHERE NOT email='sara@gmail.com';` -> Seleccionar los elementos de la columna name que no tengan el valor 'sara@gmail.com' en la columna email 

`SELECT * FROM users WHERE NOT email='sara@gmail.com' AND age=15;` -> Seleccionar los elementos de la columna name que no tengan el valor 'sara@gmail.com' en la columna email y tengan el valor 15 en la columna age

`SELECT * FROM users WHERE NOT email='sara@gmail.com' OR age=15;` -> Seleccionar los elementos de la columna name que no tengan el valor 'sara@gmail.com' en la columna email o tengan el valor 15 en la columna age

## LIMIT

>[!NOTE]
>Utilizamos el comando `LIMIT` para mostrar solo la cantidad de elementos deseada

`SELECT * FROM users LIMIT 4;` -> Seleccionar tods los elementos de la tabla y mostrar solo 4 elementos

`SELECT * FROM users WHERE NOT email='sara@gmail.com' OR age=15 LIMIT 2;` -> Selecionar todos los qlementos de la tabla donde no tengan el valor 'sara@gmail.com' en la columna email o tengan el valor de 15 en la columna age y mostrar solo 2 elementos

## NULL

>[!NOTE]
>Utilizamos el comando `NULL` para selecionar elementos que contengan el valor NULL

`SELECT * FROM users Where int_date is NUll;` -> Seleccionar todos los elementos de la tabla donde en la columna int_date el valor sea NULL

`SELECT * FROM users Where int_date is NOT NUll;` -> Seleccionar todos los elementos de la tabla donde en la columna int_date el valor no sea NULL

## MAX / MIN

>[!NOTE]
>Utilizamos el comando `MAX` para seleccionar el valor maximo de una columna
>Utilizamos el comando `MIN` para seleccionar el valor minimo de una columna

`SELECT MAX(age) FROM users;` -> Seleccionar el elemento maximo de la columna 'age' de la tabla users

`SELECT MIN(age) FROM users;` -> Seleccionar el elemento minimo de la columna 'age' de la tabla users


## COUNT

>[!NOTE]
>Utilizamos el comando `COUNT` para contar elementos de una columna

`SELECT COUNT(age) FROM users;` -> Contar los elementos de la columna 'age' de la tabla users

`SELECT COUNT(*) FROM users;` -> Contar todos los elementos de la tabla users


## SUM

>[!NOTE]
>Utilizamos el comando `SUM` para sumar elementos de una columna

`SELECT SUM(age) FROM users;` -> Sumar los elementos de la columna 'age' de la tabla users


## AVG

>[!NOTE]
>Utilizamos el comando `AVG` para mostrar la media de los valores de una columna

`SELECT AVG(age) FROM users;` -> Mostrar la media de la columna 'age' de la tabla users


## IN

>[!NOTE]
>Utilizamos el comando `IN` para seleccionar elementos que contengan valores especificos en las columnas 
>(Debe estar antecedido por un WHERE)*/

`SELECT * FROM users WHERE name IN('Brice','Sara');` -> Seleccionar todos los elementos de la tabla donde en la columna 'name' tengan el valor 'Brice' y 'Sara'


## BETWEEN

>[!NOTE]
>Utilizamos el comando `BETWEEN` para seleccionar elementos que tengan el valor de una columna en un rango determinado*/

`SELECT * FROM users WHERE age BETWEEN 20 and 30;` -> Seeccionar todos los elementos de la tabla donde el valor de la columna 'age' este entre 20 y 30


## ALIAS

>[!NOTE]
>Utilizamos el comando `ALIAS` para cambiarle el nombre a las columnas

`SELECT name, int_date AS 'Fecha' FROM users;` -> Seleccionar los elementos de las columnas 'name' y 'int_date' y cambiarle el nombre de la columna 'int_date' a 'Fecha'

`SELECT name, int_date AS 'Fecha' FROM users WHERE name = 'Brice';` -> Seleccionar los elementos de las columnas 'name' y 'int_date' donde en la columna 'name' tengan el valor 'Brice' y cambiarle el nombre de la columna 'int_date' a 'Fecha'

`SELECT concat(name, apellidos) AS 'Nombre y apellido' FROM users;` -> Unir los elementos de las columnas 'name' y 'apellidos' en una nueva columna y ponerle el nombre de 'Nombre y Apellido'


## GROUP BY

>[!NOTE]
>Utilizamos el comando `GROUP BY` para agrupar elementos de una columna

`SELECT max(age) FROM users GROUP BY age;` -> Seleccionar los elementos maximos de la columna 'age' y agruparlos por la columna 'age'

`SELECT count(age), age FROM users GROUP BY age;` -> Contar los elementos de la columna 'age' y agruparlos por la columna 'age'

`SELECT count(age), age FROM users WHERE age > 15 GROUP BY age;` -> Contar los elementos de la columna 'age' donde la el valor de la columna 'age' sea mayor que 15 y agruparlos por la columna 'age'


## HAVING

>[!NOTE]
>Utilizamos el comando `HAVING` para mostrar elementos si cumplen una condicion

`SELECT count(age) FROM users having count(age) > 3;` -> Contar los elementos de la columna 'age' y mostrarlos solo si el valor de contar la columna 'age' es mayor que 3


## CASE

>[!NOTE]
>Utilizamos el comando `CASE` para mostrar valores deseados en una columna
>si los valores de las columnas seleccionadas cumplen las condiciones establecidas
```
SELECT *,
case
	when age > 17 THEN TRUE
	else FALSE
end AS 'Saber_si es mayor de edad'
   From users;
 ``` 

>Seleccionar todos los elementos de la tabla,
>si el valor de la columna 'age' es mayor que 17 mostrar '1',
>si no es asi mostrar '0',
>mostrar estos elementos en una columna llamada 'Saber si es mayor de edad'


 ## IFNULL

 >[!NOTE]
 >Utilizamos el valor `IFNULL` para mostrar un valor deseado en los elementos que contienen el valor NULL

`select name, ifnull(apellidos,0) AS apellidos, ifnull(age,0) AS age from users;` -> Seleccionar la columna 'name', 'apellidos'(Si tiene el valor de NULL mostrar '0', y ponerle el nombre 'apellidos' a la columna) y 'age'(Si tiene el valor de NULL mostrar '0', y ponerle el nombre de 'age' a la columna),
 
 >[!WARNING]
 >Se hace el cambio de el nombre de las columnas porque este comando crea por defecto el nombre: 'ifnull(apellidos,0)' y 'ifnull(age,0)'
