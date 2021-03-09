# Que es una base de datos

  es una convención que nos permite almacenar datos sobre unas tablas y establecer una relación entre ellas,
  que es posible convertir en información.


# Tipos de tablas en myql

MyISAM(mayor uso en lectura)

  1. Bloqueo de tabla

  2. Aumento del rendimiento si nuestra aplicación realiza un elevado número de consultas “Select”.

  3. Las tablas pueden llegar a dar problemas en la recuperación de datos.

  4. Permite hacer búsquedas full-text

  5. Menor consumo memoria RAM

  6. Mayor velocidad en general a la hora de recuperar datos.

  7. Ausencia de características de atomicidad ya que no tiene que hacer comprobaciones de la integridad referencial,
    ni bloquear las tablas para realizar las operaciones, esto nos lleva como los anteriores puntos a una mayor velocidad.

InnoDB(mas lenta en lectura, pero mas robusta en almacenamiento)

  1. Bloqueo de registros

  2. Soporte de transacciones

  3. Rendimiento

  4. Concurrencia

  5. Confiabilidad

  6. Permite hacer búsquedas full-text (mysql >= 5.6)