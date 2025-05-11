## ✅ 1. Conexión a PostgreSQL desde Bash

```bash
# Conectar a PostgreSQL como usuario por defecto
psql -U postgres

# Conectar a PostgreSQL especificando una base de datos
$ psql -U postgres -d nombre_base_datos
```
## Entrar a postgress:
```
#Entrar a postgress
psql

#Entrar si ya tienes permisos:
psql -U postgres
```



```sql
# Listar base de datos
$ \l

# Seleccionar una base de datos
$ \c nombre_base_datos

#Listas de tablas de base de datos seleccionada
$ \dt

```
## ✅ 2. Ejecución de Comandos SQL Directamente

