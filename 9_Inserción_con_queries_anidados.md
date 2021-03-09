# Insert con quierties anidados

Tenemos un archivo CVS con la siguiente información

El laberinto de la Soledad | Octavio Paz | 1955
Vuelta al laberinto de la Soledad | Octavio Paz | 1960
Mediante un script de PHP podemos obtener estos datos e ir iterando para las insercciones,
pero el problema surge en que nuestra tabla de books tenemos solo el title y el year, el nombre
del autor lo tenemos en otra tabla llamada authors.

Supongamos que insertamos un libro, pero como el autor es de tipo integer
por referencia lógica a la tabla authors, en un primer momento tenemos que hacer un select a la tabla authors,
fijarse que id tiene el autor en cuestión y regresar a insertar el registro

INSERT INTO books (title, author_id) VALUES ('El laberinto de la Soledad', 6);
Sin embargo al usar INSERT con SELECT anidados, podemos saltarnos el paso de hacer el select previo a la tabla de autores
y colocarlo internamente en la consulta de insercción

Para el campo author_id, su valor lo obtengo de una subconsulta, de ahí que este entre parentesis, para que se haga primero

INSERT INTO books (title, author_id, year) VALUES ('Vuelta al laberinto de la Soledad',
  (SELECT author_id FROM authors WHERE name = 'Octavio Paz'),
1960);

## Código:

  INSERT INTO books (title, author_id) VALUES ('El laberinto de la Soledad', 6);

  INSERT INTO books (title, author_id, year) VALUES ('Vuelta al laberinto de la Soledad',
    (SELECT author_id FROM authors WHERE name = 'Octavio Paz'),
  1960);
