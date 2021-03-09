# Tipos de columnas(relaciones)

La tabla en las bases datos requieren de una PRIMARY KEY para identificar los registros.

Buena práctica:

  MySQL permite minúsculas y mayúsculas en el nombre de tablas y sentencias sql,
  pero es recomendable colocar en mayúsculas las sentencias(palabras reservadas) sql y todo lo relaciona
  con lo propio de MySQL y en minúscula el nombre de tablas y columnas.

Como la relación entre tablas es lógica y se realiza mediante los id, en la tabla en donde se referencia
la columna debe ser del mismo tipo de datos.

El error vs Warnings: la diferencia entre estos dos es que el error rompe cualquier flujo de trabajo que
tengamos en nuestra aplicación mientras que el warnnigs nos muestra una advertencia que no rompe el flujo
de trabajo workflow.

DROP TABLE name_table; borra la estructura de la tabla de bases de datos y su contenido

DESCRIBE name_table; muestra la estructura de nuestra tabla.
  Nos muestra las columnas: field, type, Null, Key, Default, Extra.

DESC name_table; es un acrónimo de describe que realiza la misma función de describir la estructura de la tabla.

SHOW FULL COLUMNS FROM name_table; Esta función describe la estructura de la bases de datos incluyendo más información cómo:
  field, Type, Collation, Null, Key, Default, Extra, Privileges, comment.

Cuando queremos usar una palabra reservada del lenguaje como nombre de alguna columna lo colocamos encerrado
entre comillas de acento ejemplo: year.


/*Eliminar una tabla*/
DROP TABLE `authors`;

/*describe el contenido (columnas) las tabla book*/
DESCRIBE `books`;

/*describe todo el contenido de la tabla, como: field, Type data, collaction, Null, key, Extra, Privileges, coment*/
SHOW FULL COLUMNS FROM `books`;
