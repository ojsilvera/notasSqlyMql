# COMANDO INSERT PARA ACTUALIZAR UN REGISTRO

  Teniendo en cuenta que el registro existe, los cmapos con restricciones de primery key o unique
  no pueden ser sobre-escritos, lo gual generara un error.

  ON DUPLICATE KEY UPDATE => permite actualizar un campo con restricción unique o que no pueda ser duplicado

  INSERT INTO nombredelatabla(FIELDS) VALUES(VALUE1, VALUE2) ON DUPLICATE KEY UPDATE
  AQUI_NOMBRE_DE_LA_COLUMNA = VALUES(AQUI_NOMBRE_DE_LA_COLUMNA);

