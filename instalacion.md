# instalacion ubuntu 20.04

sudo apt-get update

sudo apt-get upgrade

sudo apt-get install mysql-server

sudo mysql

# Error de acceso por credenciales

* ERROR 2002 (HY000): Can't connect tolocal MySQL server through socket '/var/run/mysqld/mysqld.sock'

## solución 1: Reiniciar el servicio

  sudo apt-get update

  sudo apt-get upgrade

  sudo service mysql restart&

## Solución 2: Actualizar crdenciales al user

  sudo mysql -u root

  ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'aquí el password';

  sudo service mysql restart