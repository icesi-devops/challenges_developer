# Icesi-DevOps SERVER STATE

Queremos crear un servicio que nos permita obtener información sobre un servidor
y saber si las configuraciones han cambiado.

### Parte 1

Para eso, se nos pide crear un API rest con un endpoint que reciba un dominio
como truora.com y retorne un JSON con la siguiente información:

```
{
“servers”: [
{
“address”: “server1”,
“ssl_grade”: “B”,
“country”: “US”,
“owner”: “Amazon.com, Inc.”
},
{
“address”: “server2”,
“ssl_grade”: “A+”,
“country”: “US”
“owner”: “Amazon.com, Inc.”
},
{
“address”: “server3”,
“ssl_grade”: “A”,
“country”: “US”
“owner”: “Amazon.com, Inc.”
}
],
“servers_changed”: true,
“ssl_grade”: “B”,
“previous_ssl_grade”: “A+”,
“logo”: “https://server.com/icon.png”,
“title”: “Title of the page”,
“is_down”: false
}
```
- servers: contiene un array de los servidores asociados al dominio, cada objeto
del array contiene
	- address: la IP o el host del servidor
	- ssl_grade: el grado SSL calificado por SSLabs
	- country: El país del servidor como aparece cuando se usa el comando whois <ip>
	- owner: la organización dueña de la IP, como aparece cuando se usa el comando whois <ip>
	- servers_changed: es true si los servidores cambiaron, respecto a una hora o más antes
	- ssl_grade: el grado más bajo de todos los servidores
	- previous_ssl_grade: el grado que tenía una hora o más antes
	- logo: el logo del dominio sacado del <head> del HTML
	- title: el título de la página sacado del <head> del HTML
	- is_down: true si el servidor está caído y no se puede contactar

### Parte 2

Crear otro endpoint que liste los servidores que han sido consultados previamente, aún si se reinicia el navegador.
Por ejemplo, si se consulta truora.com y google.com el endpoint debería retornar ambos resultados:

```
{
“items”: [
{google.com info},
{truora.com info}
]
}
```

### Parte 3

Crear una interfaz web con Vue o móvil con Android o iOS para consultar dominios
y ver las búsquedas recientes.

### Fuentes de Información

Información de SSL y servidores
	https://api.ssllabs.com/api/v3/analyze?host=<dominio>
	Ejemplo:
	https://api.ssllabs.com/api/v3/analyze?host=truora.com

Información de país y dueño
	whois <ip>
	Ejemplo:
	whois 54.239.132.139

Información del logo
	Página web del sitio
	Ejemplo:
	Mirar el <head>

### Tecnologías

Las siguientes tecnologías deben ser usadas para resolver la prueba.
Entendemos que es posible que no tengas mucha experiencia usando estas
tecnologías. Para nosotros, es muy importante medir la capacidad de aprender que
tiene un/a ingeniero/a. Esto además, ayuda a entender de mejor forma el talento.
Lenguaje: Go
Base de Datos: CockroachDB
API Router: fasthttprouter
Interfaz: Vue.js & bootstrap-vue.js o Android o iOS
No usar ORMs
