# left joins

  SELECT  b.title, a.name
  from authors as a, books as b
  WHERE a.author_id = b.author_id
  LIMIT 10;

  --Join implícito
  SELECT b.title, a.name
  from books as b
  inner JOIN authors as a
      on a.author_id = b.author_id
  LIMIT 10;

  --Left JOIN
  select a.author_id, a.name, a.nationality, b.title
  from authors as a
  join books as b
      on b.author_id = a.author_id
  WHERE a.author_id BETWEEN 1 AND 5;

  --Nuevo decorador
  select a.author_id, a.name, a.nationality, b.title
  from authors as a
  join books as b
      on b.author_id = a.author_id
  WHERE a.author_id BETWEEN 1 AND 5
  ORDER BY a.name desc;

  --Left JOIN
  select a.author_id, a.name, a.nationality, b.title
  from authors as a
  left join books as b
      on b.author_id = a.author_id
  WHERE a.author_id BETWEEN 1 AND 5
  ORDER BY a.author_id;

  --Funciones agrupados
  select a.author_id, a.name, a.nationality, count(b.book_id)
  from authors as a
  left join books as b
      on b.author_id = a.author_id
  WHERE a.author_id BETWEEN 1 AND 5
  GROUP BY a.author_id
  ORDER BY a.author_id;