# SQL Things

(PLSQL) Mostrar elementos (packages, functions, procedures, etc) invalidos (descompilador, con error, etc)

```sql
declare
cursor pack is
      select object_type,object_name
      from user_objects
      where status = 'INVALID';
BEGIN
    DBMS_OUTPUT.PUT_LINE('---------------------------------------------------');
    DBMS_OUTPUT.PUT_LINE('Elementos Descompilados: ');
    DBMS_OUTPUT.PUT_LINE('---------------------------------------------------');
    for c in pack loop
        DBMS_OUTPUT.PUT_LINE(rpad (c.object_type,12,' ')||' : '||c.object_name);
    end loop;
    DBMS_OUTPUT.PUT_LINE('---------------------------------------------------');
END;
/
```

(PLSQL) (Intentar) Compilar todos los elementos:

```sql
DECLARE
	str long;
	msg long:='';
BEGIN
	FOR str IN (SELECT 'ALTER '  ||  decode (ao.object_type,
	                              'PACKAGE BODY', 'PACKAGE '  ||  ao.object_name   ||  ' COMPILE BODY',
	                               ao.object_type  || ' ' ||  ao.object_name  ||  ' COMPILE') as sent
	            FROM USER_objects ao
	           WHERE ao.status != 'VALID'
	             and ao.object_name != 'PKG_CARGA_ARCHIVO_TEST'
	             and ao.object_type in ('FUNCTION',
	                                    'PROCEDURE',
	                                    'PACKAGE',
	                                    'PACKAGE BODY',
	                                    'TRIGGER',
	                                    'VIEW',
	                                    'JAVA SOURCE',
	                                    'JAVA CLASS')PARA_ENCOLAR_GIS_CDL_SERIALIZADO
	             )
	  loop
	     begin
	        EXECUTE IMMEDIATE str.sent;
	        DBMS_OUTPUT.put_line ('Se ejecuto la sentencia: '  ||  str.sent);
	     EXCEPTION
	          WHEN OTHERS
	          THEN
	             DBMS_OUTPUT.put_line ('Error al ejecutar la sentencia : '  ||  str.sent  ||  ' - '  ||  SQLERRM  ||  CHR(10));
	     end;
	end loop;
END;
/
```


(PLSQL) Crear tabla a partir de select (SIN INDICES NI TRIGGERS NI CONSTRAINTS NI NADA)

```
CREATE TABLE MY_TEMP_TABLE AS
SELECT *
FROM ORIGINAL_TABLE;
```