
Se vera a continuación una guía del como poder crear nuestro propio contenedor, y con el que levantaremos el servicio de balanceo de carga. El cual permite distribuir las conexiones entre servidores activos.

Construir un contenedor
-----------------------

Para esto debemos de crear nuestro propio documento [Dockerfile](http://docs.docker.com/reference/builder/), para caso de este ejercicio se puede ver el Dockerfile que esta dentro del directorio `nginx/`.

Una ves se tenga prepara do se ejecutar el siguiente comando.

***NOTA:*** Para ejecutar este comando se debe de estar en el directorio en donde se encuentre el documento `Dockerfile`.

```bash
$ docker build -t ownnginx .
```



Preparando app1
---------------

Se debe de estar dentro del directorio `app1/` para este comando.

```bash
$ docker build -t ownapp1 .
```



Preparando app2
---------------

Se debe de estar dentro del directorio `app2/` para este comando.

```bash
$ docker build -t ownapp2 .
```



Arquitectura de sistema
-----------------------

Ya teniendo listo estos dos contenedores podemos ejecutar la siguiente arquitectura.

![Arquitectura Balanceo de Carga](diagrama.jpg)



docker run -d --name con --link app1:srv1 --link app2:srv2 -P ownnginx
