## Conexión a PostgreSQL desde Bash

```bash
# Conectar a PostgreSQL como usuario por defecto
bash: $ psql -U postgres

# Conectar a PostgreSQL especificando una base de datos
bash: $ psql -U postgres -d nombre_base_datos
```

## Entrar a postgress ya instalado desde BASH:

```**bash**
#Entrar a postgress
bash: $ psql

#Entrar si ya tienes permisos:
bash: $ psql -U postgres
```
Esto permitira que el terminal este en: **psql**

## 📝 Comandos postgres en terminal psql 

```sql
# Listar base de datos
psql: $ \l

# Seleccionar una base de datos
psql: $ \c nombre_base_datos

#Listas de tablas de base de datos seleccionada
psql: $ \dt

#Listar secuencias (seriales)
psql: $ \ds

#Listar vistas
psql: $ \dv

#Listar roles de usuario:
psql: $ \du

#Listar usuarios y privilegios:
psql: $ \dg

#Ver permisos de tablas:
psql: $ \dp

```

## 🔒 Gestión de usuarios y permisos

```
#Crear un usuario
psql: $ CREATE USER nombre_usuario WITH PASSWORD 'tu_contraseña';

#Asignar privilegios de superusuario
psql: $ ALTER USER nombre_usuario WITH SUPERUSER;

#Revocar privilegios de superusuario
psql: $ ALTER USER nombre_usuario WITH NOSUPERUSER;

Eliminar un usuario
psql: $ DROP USER nombre_usuario;

```
## ⚙️ Gestión de bases de datos

```
#Crear una nueva base de datos:
psql: $ CREATE DATABASE nombre_base_datos;

#Eliminar una base de datos:
psql: $ DROP DATABASE nombre_base_datos;

#Renombrar una base de datos:
psql: $ ALTER DATABASE nombre_base_datos RENAME TO nuevo_nombre;

#Realizar un respaldo de una base de datos:
psql: $ pg_dump nombre_base_datos > respaldo.sql

#Restaurar un respaldo:
psql: $ psql nombre_base_datos < respaldo.sql


```

## 🔧 Eliminar conexiones activas en PostgreSQL
Usado previo a una aliminacion de una base de datos o de un usuario.
### Ver las conexciones activas:
```
SELECT pid, usename, datname, client_addr, state 
FROM pg_stat_activity 
WHERE datname = 'nombre_base_datos';

```
###Terminar una conexión especifica:
```
SELECT pg_terminate_backend(pid) 
FROM pg_stat_activity 
WHERE pid = 12345; -- Reemplaza 12345 por el PID específico

```
### Eliminar todas las conexiones de una base de datos (excepto la tuya)

```
SELECT pg_terminate_backend(pid) 
FROM pg_stat_activity 
WHERE datname = 'nombre_base_datos'
  AND pid <> pg_backend_pid();
```

### Forzar el cierre de todas las conexiones en PostgreSQL
```
SELECT pg_terminate_backend(pid) 
FROM pg_stat_activity 
WHERE datname = 'nombre_base_datos';

```

### Desactivar nuevas conexiones temporalmente (modo mantenimiento)
```
ALTER DATABASE nombre_base_datos CONNECTION LIMIT 0;
```
Permitir conexiones nuevamente:
```
ALTER DATABASE nombre_base_datos CONNECTION LIMIT -1;
```

