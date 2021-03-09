SELECT DISTINCT nationality FROM authors;

UPDATE authors SET nationality = 'GBR' WHERE nationality = 'ENG';

SELECT COUNT(*) FROM books;

SELECT COUNT(book_id) FROM books;

SELECT COUNT(book_id) , SUM(1) FROM books;

SELECT SUM(price) FROM books WHERE sellable = 1;

SELECT SUM(price*copies) FROM books WHERE sellable = 1;

SELECT sellable, SUM(price*copies) FROM books GROUP BY sellable;

SELECT COUNT(book_id) , SUM(IF(YEAR < 1950,1,0)) AS '< 1950' FROM books;

SELECT COUNT(book_id)   FROM books WHERE YEAR < 1950;

SELECT COUNT(book_id) , SUM(IF(YEAR < 1950,1,0)) AS '< 1950' , SUM(IF(YEAR <= 1950,0,1)) AS '>= 1950'  FROM books;

SELECT COUNT(book_id) , SUM(IF(YEAR < 1950,1,0)) AS '< 1950' , SUM(IF(YEAR >= 1950 AND YEAR < 1990,1,0)) AS '< 1990',
SUM(IF(YEAR >= 1990 AND YEAR < 2000,1,0)) AS '< 2000'
FROM books;

SELECT COUNT(book_id) , SUM(IF(YEAR < 1950,1,0)) AS '< 1950' , SUM(IF(YEAR >= 1950 AND YEAR < 1990,1,0)) AS '< 1990',
SUM(IF(YEAR >= 1990 AND YEAR < 2000,1,0)) AS '< 2000' , SUM(IF(YEAR >= 2000 ,1,0)) AS '> 2000'
FROM books;

SELECT nationality,COUNT(book_id) , SUM(IF(YEAR < 1950,1,0)) AS '< 1950' , SUM(IF(YEAR >= 1950 AND YEAR < 1990,1,0)) AS '< 1990',
SUM(IF(YEAR >= 1990 AND YEAR < 2000,1,0)) AS '< 2000' , SUM(IF(YEAR >= 2000 ,1,0)) AS '> 2000'
FROM books AS b INNER JOIN authors AS a ON
b.author_id = a.author_id
WHERE nationality IS NOT NULL
GROUP BY nationality ;