# Casos de usando

## ¿Cuál es el promedio/desviación standard del precio de libros + idem, pero por nacionalidad

    SELECT nationality, COUNT(book_id) AS libros
    AVG(price) AS prom
    STADDEV(price) AS std
    FROM books as b
    JOIN authors as a
    ON a.author_id = b.author_id
    GROUP BY nationality
    ORDER BY libros DESC;

## ¿Cuál es el precio máximo/mínimo de un libro?

    SELECT nationality, MAX(price), MIN(price)
    FROM books AS b
    JOIN authors AS a
    ON a.author_id = b.author_id
    GROUP BY nationality

## ¿Cómo quedaría el reporte final de préstamos?

    SELECT c.name, t.type, b.title
    CONCAT (a.name, " (", a.nationality, ")") AS autor
    TO_DAYS(NOW()) - TO_DAYS(t.created_at) AS ago
    FROM transactions AS t
    LEFT JOIN clients AS c
    ON c.client_id = t.client_id
    LEFT JOIN books AS b
    ON b.book_id = t.book_id
    LEFT JOIN authors AS a
    ON b.author_id = a.author_id