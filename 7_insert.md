# COMANDO INSERT

  INSERT INTO nombredelatabla(FIELDS) VALUES(VALUE1, VALUE2);

  Ejemplo:

    INSERT INTO authors(author_id, name, nacionalidad)
    values('', '', '')
    values('', '', '')
    values('', '', '');

    (id auto-incremento, por esto no se envia)
    INSERT INTO authors(name, nacionalidad)
    values('', '')
    values('', '')
    values('', '');

    INSERT INTO authors(name, nacionalidad)
    values('', ''),
          ('', ''),
          ('', '');
