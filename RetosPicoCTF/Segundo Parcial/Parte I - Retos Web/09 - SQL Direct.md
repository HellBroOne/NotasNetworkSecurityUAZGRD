## Descripcion
Connect to this PostgreSQL server and find the flag! `psql -h saturn.picoctf.net -p 51315 -U postgres pico`Password is `postgres`

### Pistas
1. What does a SQL database contain?

1. ¿Qué contiene una base de datos SQL?
### Solución
```
hellbroone-picoctf@webshell:~$ psql -h saturn.picoctf.net -p 51315 -U postgres pico
Password for user postgres: 
psql (14.11 (Ubuntu 14.11-0ubuntu0.22.04.1), server 15.2 (Debian 15.2-1.pgdg110+1))
WARNING: psql major version 14, server major version 15.
         Some psql features might not work.
Type "help" for help.

pico=# SHOW TABLES;
pico-# \l
                                 List of databases
   Name    |  Owner   | Encoding |  Collate   |   Ctype    |   Access privileges   
-----------+----------+----------+------------+------------+-----------------------
 pico      | postgres | UTF8     | en_US.utf8 | en_US.utf8 | 
 postgres  | postgres | UTF8     | en_US.utf8 | en_US.utf8 | 
 template0 | postgres | UTF8     | en_US.utf8 | en_US.utf8 | =c/postgres          +
           |          |          |            |            | postgres=CTc/postgres
 template1 | postgres | UTF8     | en_US.utf8 | en_US.utf8 | =c/postgres          +
           |          |          |            |            | postgres=CTc/postgres
(4 rows)

pico-# \c pico
psql (14.11 (Ubuntu 14.11-0ubuntu0.22.04.1), server 15.2 (Debian 15.2-1.pgdg110+1))
WARNING: psql major version 14, server major version 15.
         Some psql features might not work.
You are now connected to database "pico" as user "postgres".
pico-# \dt
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)

pico-# SELECT * FROM flags;
ERROR:  syntax error at or near "SELECT"
LINE 2: SELECT * FROM flags;
        ^
pico=# select * from flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)
```
### Notas Adicionales
Postgres tiene diferentes sintaxis de comandos a diferencia de otros sistemas manejadores de bases de datos.

### Referencias
https://play.picoctf.org/practice/challenge/303