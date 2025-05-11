## ✅ 1. Conexión a PostgreSQL desde Bash

```bash
# Conectar a PostgreSQL como usuario por defecto
psql -U postgres

# Conectar a PostgreSQL especificando una base de datos
psql -U postgres -d nombre_base_datos

# Conectar a PostgreSQL en un servidor remoto
psql -h 192.168.1.100 -p 5432 -U postgres -d nombre_base_datos
