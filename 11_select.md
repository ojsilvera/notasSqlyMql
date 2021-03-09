# El select

Traer solo una columna especifica (en este caso la columna “name”):

  SELECT name FROM clients;

Traer varias columnas especificas (en este caso la columna “name” y “gender”):

  SELECT name, email, gender FROM clients;

Limitar el numero de resultados (en este caso maximo 10 resultados):

  SELECT name, email, gender FROM clients LIMIT 10;

Condicionar los resultados a una caracteristica (en este caso todos los resultados que tengan gender con el valor “M”):

  SELECT name, email, gender FROM clients WHERE gender='M';

Utilizar funciones para obtener datos especificos (en este caso todas las Mujeres que en su nombre tengan la cadena “Lop”):

  SELECT name, email, YEAR(NOW()) - YEAR(birthdate) AS edad, gender
  FROM clients
  WHERE gender='F'
      AND name LIKE '%Lop%';