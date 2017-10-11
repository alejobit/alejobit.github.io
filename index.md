## MySQL: Gestión de usuarios

Para crear o eliminar usuarios

```sql
CREATE USER 'user'@'host' IDENTIFIED BY 'password';

DROP USER 'user'@'host';
```

Para asignar o revocar permisos

```sql
GRANT [permission] ON [database].[table] TO '[user]'@'host';

REVOKE [permission] ON [database].[table] FROM '[user]'@'host';

FLUSH PRIVILEGES;
```

Los tipos de permisos son: `ALL PRIVILEGES`, `CREATE`, `DROP`, `DELETE`, `INSERT`, `SELECT`, `UPDATE`, `GRANT OPTION`,

***

## Bash: Buscar y remplazar una cadena de texto simple en un archivo

```bash
sed 's/old_string/new_string/g' file.txt
```

***

## Instalar la aplicación nativa de Postman

Descargar y descomprimir

```bash
wget https://dl.pstmn.io/download/latest/linux64 -O Postman.tar.gz
sudo tar -xzf Postman.tar.gz -C /opt
```

Crear entrada en el escritorio

```bash
cat > ~/.local/share/applications/postman.desktop <<EOL
[Desktop Entry]
Encoding=UTF-8
Name=Postman
Exec=/opt/Postman/Postman
Icon=/opt/Postman/resources/app/assets/icon.png
Terminal=false
Type=Application
Categories=Development;
EOL
```

***

## MySQL: Respaldar y restaurar bases de datos

Para realizar el respaldo

```bash
# Texto plano
mysqldump -u {user} -p {database} > {database}$(date -I).sql

# Con compresión
mysqldump -u {user} -p {database} | gzip > {database}$(date -I).sql.gz
```

Para la restauración

```bash
# Texto plano
mysql -u {user} -p {database} < {database}.sql

# Con compresión
gzip -dc < {database}.sql.gz | mysql -u {user} -p {database}
```

Reemplazar `{user}` y `{database}` con el usuario y la base de datos correspondiente.
