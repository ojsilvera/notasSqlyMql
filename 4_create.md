# comando CREATE

  -Crea una base de datos
    CREATE database nombreBD;

  -Crea una base de datos sino existe:
    (Sí existe genera un warning)
    CREATE database IF NOT EXISTS nombreBD;

  -Muestra errores al ejecutar un comando:
    show warning;

  -selecciona una BD:
    use database;

  -crea una tabla en la base de datos que estemos usando
    (Nombre de la tabla en plural, minúsculas y en ingles)
    Create TABLE IF NOT EXISTS nombreTabla(campo1_id integer primary key auto_increment,
      campo2 tipo,
      campoN tipo
      );

  -crea una tabla en la base de datos que estemos usando si la tabla no existe
      (Nombre de la tabla(SUSTANTIVO) en plural, minúsculas y en ingles)
      (Unsigned: no almacena el signo en el campo byte, por lo tanto todos los enteros son positivos)
      (Not Null, evita que se pase un campo vacio)
      (Default valor, si el campo esta vacio con la propiedad not null, rellena el campo con el valor indicado por defecto)
      (comment 'el comentario',solo es visto por quien ve la estructura de la tabla)
      (varchar(n), setea el numero de caracteres del campo en n)
      (text, campo de conjunto de caracteres largo)
      Create TABLE IF NOT EXISTS nombreTabla(
      campo1_id UNSIGNED INTEGER PRIMARY KEY AUTO_INCREMENT,
      campo2 tipo NOT NULL,
      campoN tipo
      );
