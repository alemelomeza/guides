CURL es una herramienta impresionante que permite crear solicitudes `HTTP` desde la línea de comandos. Admite muchos protocolos como `HTTP`, `HTPPS`, `FTP`, `FTPS`, `SFTP`, `IMAP`, `SMTP` y `POP3`.

# Realizar una solicitud HTTP GET

Cuando realice una solicitud, CURL devolverá el cuerpo de la respuesta:

```bash
$ curl http://hostname.tld
```

# Obtener los encabezados de una respuesta GET

Por defecto, los encabezados de una respuesta están ocultos en la salida de CURL. Para mostrarlos se usa la opción `i`:

```bash
$ curl -i http://hostname.tld
```

# Obtener solo los encabezados de una respuesta

Usando la opción `I`, se puede obtener solo los encabezados sin el cuerpo de la respuesta:

```bash
$ curl -I http://hostname.tld
```

# Realizar una solicitud HTTP POST

La opción `X` permite cambiar el método `HTTP`. Por defecto se usa `GET` siendo lo mismo escribir:

```bash
$ curl -X GET http://hostname.tld
```

Usando `-X POST` se realizará una petición `POST`.

Se puede realizar una solicitud `POST` pasando los datos codificados en la `URL`:

```bash
$ curl -d "key=value&otherkey=othervalue" -X POST http://hostname.tld
```

En este ejemplo se envía el `Content-Type` como `application/x-www-form-urlencoded`.

# Realizar una solicitud HTTP POST enviando un JSON

En vez de enviar los datos codificados en la `URL`, es posible enviarlo en formato `JSON`.

En este ejemplo se debe establecer explícitamente el encabezado `Content-Type` utilizando la opción `H`:

```bash
$ curl -d '{"key":"value","otherkey":"othervalue"}' -H "Content-Type: application/json" -X POST http://hostname.tld
```

También es posible enviar un archivo `.json`:

```bash
$ curl -d "@my-file.json" -X POST http://hostname.tld
```

# Realizar una solicitud HTTP PUT

El concepto es el mismo que en una solicitud `PUT`, solo se debe cambiar el método `HTTP` usando `-X PUT`.

# Seguir una redirección

Una respuesta de redireccionamiento como `301`, que especifica el encabezado de respuesta de ubicación `Location`, puede seguirse utilizando la opción `L`:

```bash
$ curl -L http://hostname.tld
```

# Guardar la respuesa en un archivo

Usando la opción `o` se puede guardar la respuesta en un archivo:

```bash
$ curl -o my-file.html http://hostname.tld
```

También se puede guardar en un archivo con el nombre del servidor, utilizando la opción `O`:

```bash
$ curl -O http://hostname.tld
```

# Usando autenticación

Si una solicitud require autenticación HTTP básica, se puede usar la opción `u` indicando la credenciales:

```bash
$ curl -u user:password http://hostname.tld
```

# Configurar un agente de usuario diferente

El agente de usuario le dice al servidor qué cliente está realizando la solicitud. Por defecto, CURL envía el agente de usuario `curl/<version>`.

Se puede especificar un agente de usuario diferente utilizando la opción `--user-agent`:

```bash
$ curl --user-agent "my-user-agent" http://hostname.tld
```

# Inspeccionado todos los detalles de la solicitud y la respuesta

Utilizando la opción `--verbose` se puede hacer que CURL muestre todos los detalles de la solicitud y la respues:

```bash
$ curl --verbose http://hostname.tld
```