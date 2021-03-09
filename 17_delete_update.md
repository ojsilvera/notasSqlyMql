# Delete y Update

Tips:

Los datos no deberían borrarse, siempre y cuando se respete el acuerdo con el usuario final.
SIEMPRE usar WHERE con comandos UPDATE.
Al hacer UPDATE o DELETE usar LIMIT para limitar el impacto del comando si algo saliese mal.
Comandos:

DELETE: elimina información.
Puedes hacer rollback posterior a realizar el DELETE a tabla siempre y cuando no hayas
hecho COMMIT sino tampoco puedes regresar los cambios

UPDATE: actualiza información en una tabla.

TRUNCATE: elimina el contenido de una tabla por completo.
No puedes dar un rollback posterior a realizar el TRUNCATE a tabla, no se puede regresar la información

## SINTAXIS

UPDATE tabla
SET
  [COLUMNA = VALOR, COLUMNA = VALOR, ...]
WHERE
  [CONDICIÓN]
LIMIT 1;

DELETE
FROM
  [TABLA]
WHERE
  CONDICIÓN[active = '0' LIMIT 1;];

TRUNCATE tabla;

## ejemplos:

----Uso del DELETE
    DELETE FROM  authors where author_id = 161 limit 1;

----Uso del UPDATE
    select client_id, name from clients where active <> 1;
    select client_id, name, active from clients ORDER BY rand() LIMIT 10;
    select client_id, name, active from clients WHERE  client_id in (80, 65, 76, 1, 61,19,97);
    UPDATE clients
    SET active = 0
    WHERE client_id = 80
    LIMIT 1;

    SELECT  client_id, name, email, active
    FROM clients
    WHERE client_id IN (7, 80, 65, 76, 1, 61, 19, 97);

    UPDATE clients
    SET email = 'javier@gmail.com'
    WHERE client_id = 7 OR client_id = 9
    LIMIT 1;

    SELECT client_id, name, active
    FROM clients
    WHERE
      client_id IN (1,6,8,27,90)
      OR name LIKE '%lopez%';

    UPDATE clients
    SET active = 0
    WHERE
        client_id IN (1,6,8,27,90)
        OR name LIKE '%lopez%';

---- Borrar toda una tabla
    SELECT * FROM transactions;
    TRUNCATE transactions;