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

## Comandos postgres en terminal psql 

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

