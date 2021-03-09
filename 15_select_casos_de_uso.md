# generar consultas con base a una pregunta o caso de uso

## ¿Qué nacionalidades hay?

  SELECT nationality FROM authors WHERE nationality IS NOT NULL GROUP BY nationality;

## ¿Cuántos escritores hay de cada nacionalidad?

  SELECT author_id, nationality, COUNT(author_id) AS total FROM authors WHERE nationality
  IS NOT NULL GROUP BY nationality;

## ¿Cuántos libros hay de cada nacionalidad?

  SELECT a.nationality, COUNT(book_id) AS total_libros
  FROM books AS b INNER JOIN authors AS a ON
  a.author_id = b.author_id
  GROUP BY nationality;

## ¿Cuál es el promedio/desviación standard del precio de libros

  SELECT AVG(price) AS promedio FROM books;

## idem, pero por nacionalidad

## ¿Cuál es el precio máximo/mínimo de un libro

  SELECT MAX(price) AS valor_max, MIN(price) AS valor_min
  FROM books;

## ¿Cómo quedaría el reporte de prestamos

  SELECT t.transaction_id, b.title,
  c.name, (CASE
  WHEN finished = 1 THEN 'Devuelto'
  WHEN finished = 0 THEN 'Pendiente'
  END) AS estado FROM transactions AS t INNER JOIN books AS b ON
  t.book_id = b.book_id INNER JOIN clients AS c ON
  t.client_id = c.client_id
  WHERE type = 'lend';```
