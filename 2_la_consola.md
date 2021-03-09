# Comandos basicos de la consola Myql sistemas basados en unix

  -accedo a la consola de mysql:
    sudo mysql -u root -h localhost -p

  -Lista las bases de datos en el sistema:
    show databases;

  -Selecciona una base de datos:
    use nombreDB;

  -Muestra la base de datos en uso:
    select database();

  -Muestra la base de datos en uso:
    show tables;

  -Muestra errores al ejecutar un comando:
    show warnings;

  -Salir de mysql:
     \q o ctrl + d
