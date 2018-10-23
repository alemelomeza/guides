# Base

Actualización los repositiorios:

```bash
$ sudo apt-get update
```
Busqueda un paquete:

```bash
$ sudo apt-cache search "PACAKGE"
```

Obtención de infomación de un paquete:

```bash
$sudo apt-cache "PACKAGE"
```

Instalción de paquetes:

```bash
$ sudo apt-get install -yq wget curl zip unzip
```

# Git

Intalación de Git:

```bash
$ sudo apt-get install -yq git-core
```

Configuración local:

```bash
$ git config user.name "USER_NAME"
$ git config user.email "USER_EMAIL"
```

Configuración global:

```bash
$ git config --global user.name "USER_NAME"
$ git config --global user.email "USER_EMAIL"
```

# PHP

```bash
$ sudo apt-get install -yq \
php7.1 \
php7.1-cli \
php7.1-curl \
php7.1-mysql \
php7.1-xml \
php7.1-mcrypt \
php7.1-mbstring \
php7.1-zip
```

# Apache

Instalación:

```bash
$ sudo apt-get install -yq apache2 libapache2-mod-php7.1
```

Habilitación de módulos:

```bash
$ sudo a2enmod rewrite
```

# MySQL

Instalación:

```bash
$ sudo apt-get install -yq mysql-server
```

Configuración de seguridad:

```bash
$ sudo mysql_secure_installation
```

Conexión a la consola de MySQL:

```bash
$ mysql -u root -p
```

Creación de una base de datos:

```mysql
mysql> CREATE DATABASE 'DATABASE_NAME' DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

Eliminación de una base de datos:

```mysql
mysql> DROP DATABASE 'DATABASE_NAME';
```

Creación de un usuario:

```mysql
mysql> CREATE USER 'USER_NAME'@'%' IDENTIFIED BY 'USER_PASSWORD';
```

Asignar una base de datos a un usuario:

```mysql
mysql> GRANT ALL PRIVILEGES ON 'DATABASE_NAME'.* TO 'USER_NAME'@'%';
```

Listar usuarios:

```mysql
mysql> SELECT User, Host FROM mysql.user;
```

Eliminar un usuario:

```mysql
mysql> DROP USER 'USER_NAME'@'%';
```

# Composer

Instalación:

```bash
$ sudo curl -sS https://getcomposer.org/installer | \
sudo php -- --installer-dir=/usr/local/bin --filename=composer
```

# Laravel

Instalación:

```bash
$ sudo cd /var/www/html && \
composer create-project --prefer-dist laravel/laravel PROJECT_NAME
```

Configuración:

```bash
$ sudo cd /var/www/html/PROJECT_NAME && \
mv .env-example .env && \
php artisan key:generate
```

Permisos de carpetas:

```bash
$ sudo cd /var/www/html/PROJECT-NAME && \
chgrp -R www-data storage/ bootstrap/cache && \
chmod -R ug+rwx storage/ bootstrap/cache
```

Configuración del host virtual:

```bash
$ sudo cd /etc/apache2/sites-available && \
nano PROJECT_NAME.conf
```
Contenido de _PROJECT_NAME.conf_:

```
<VirtualHost *:80>

    ServerName PROJECT_NAME.TLD

    DocumentRoot "/var/www/html/PROJECT_NAME/public"
    <Directory /var/www/html/PROJECT_NAME/public>
        # Don't show directory index
        Options -Indexes +FollowSymLinks +MultiViews

        # Allow .htaccess files
        AllowOverride All

        # Allow web access to this directory
        Require all granted
    </Directory>

    # Error and access logs
    ErrorLog ${APACHE_LOG_DIR}/PROJECT_NAME.log
    # Possible values include: debug, info, notice, warn, error, crit,
    # alert, emerg.
    LogLevel warn
    CustomLog ${APACHE_LOG_DIR}/PROJECT_NAME.log combined

</VirtualHost>
```

Deshabilitación de sitio por defecto y habilitación de host virtual:

```bash
$ sudo a2dissite 000-default.conf && \
a2ensite PROJECT_NAME.conf && \
service apache2 restart
```
