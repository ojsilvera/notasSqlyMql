# Manejo de fechas

EL no colocar AUTO_INCREMENT a la columna que es PRIMARY KEY simplemente vuelve el proceso de asignar id
a una forma manual o se puede asignar desde otra capa de negocios.

-UNIQUE, la columna que tenga el constraint unique garantiza que el valor que se guarda en esa columna sea
 único

-TIMESTAMP
Está basado en el número epoch que es el 1 enero de 1970 hasta la fecha y es donde se determina el inicio de
las computadoras y es un número entero que se guarda en segundos y permite hacer operaciones sobre el.

-DATETIME
Este tipo de datos puede guardar cualquier valor de tipo fecha sin restricción. Incluso anterior a nuestra era.
es por eso que las fechas de nacimiento de usuarios debe utilizar este valor para garantizar que podemos registrarlos
con la fecha adecuada.

TIMESTAMP vs DATETIME: hay que resaltar que un, 1.TIMESTAMP “NO PUEDE HACER TODO LO DE DATETIME pero DATETIME SÍ
PUEDE HACERLO DE UN TIMESTAMP”, 2.DATETIME no está guardado en segundos y no es tan eficiente para hacer cálculos.

-Active
Es buena práctica no eliminar registros de una bases de datos es por ello que se crea una columna como active que
es un valor booleano dicho valor sirve para para decir si el registro está activo o no.

-created_ad y updated_ad
Es buena práctica tener una columna que permite saber el momento exacto en el que se crea un registro o se actualiza.
Este tipo de dato se comporta más como una meta-información y nos puede ayudar por ejemplo a cuántos usuarios fueron
creados en una fecha en específico, saber cuando una tupla se actualizó

created_ad Es una columna de buena práctica que permite saber cuando se creó un registro. Está utilizará un conjunto de
propiedades llamada entre ella se colocará DEFAULT CURRENT_TIMESTAMP . Cuando se realiza un insert sí el valor de esta
columna viene vacío colocará en la tupla el valor de la fecha en que se creó de manera automática.

ejemplo:

 CREATE TABLE clients (
  client_id INTEGER UNSIGNED PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(50) NOT NULL,
  email VARCHAR(100) NOT NULL UNIQUE,
  birthdate DATETIME,
  gender ENUM(‘M’, ‘F’, ‘ND’) NOT NULL,
  active TINYINT(1) NOT NULL DEFAULT 1,
  created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
 );
