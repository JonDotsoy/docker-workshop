Workshop Docker [![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/jonDotsoy/docker-workshop?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=body_badge)
===============


Este workshop trabajar con los siguientes contenidos.

  - Docker Conceptos Básicos
  - Cliente Docker
    - Clonar un contenedor
    - Replicar contenedores
    - Actualizar Contenedores
  - Creando un Dockerfile
    - Crear un contenedor
    - Aplicando Configuraciones ENVIRONMENT


Preparaciones:

  - Instalar Docker.
    - [Windows](https://docs.docker.com/installation/windows/)
    - [Mac OS X](https://docs.docker.com/installation/mac/)
    - [Ubuntu](https://docs.docker.com/installation/ubuntulinux/)
    - [Otros](https://docs.docker.com/installation/)
  - Clonar repositorios `git clone https://github.com/jonDotsoy/docker-workshop.git`.



Conceptos Básicos de Docker 
---------------------------

[![Presentación Docker](docs/imgs/Presentation%20Docker.jpg)](https://goo.gl/LBfC3N)
:link: (https://goo.gl/LBfC3N)



Cliente Docker
--------------

### Crea un contenedor

Descargar una imagen.

```sh
$ docekr pull ubuntu
```

Ejecutamos un bash dentro de un nuevo contenedor.

```sh
$ docker run -it ubuntu /bin/bash
```

Listar Proceso ejecutados.

```sh
$ docker ps
```

#### Definir un sombre al contenedor ejecutado

Debemos tener presente el actual nombre del contenedor.

```sh
$ docker rename OLD_NAME NEW_NAME
```



### Clonando un contenedor

 - **Nota:** Documentación pendiente.



### Replicar contenedor

 - **Nota:** Documentación pendiente.



## Ejemplo: Contenedor PHP

Creamos un directorio y creamos dentro un archivo `index.php`.

```php
<!-- filename: index.php -->
<?php
echo "Saludos desde PHP Usando Docker.";
?>
```


Abrimos nuestra consola docker y ejecutamos el siguiente comando.

```sh
$ docker run -it --name myapp -P -v $(pwd):/var/www/html php:5.6-apache
```


### Ejecutar contenedor de modo demonio bajo puerto 80

Levantaremos el servicio php usando el puerto 80 del servidor como un sitio web.

```sh
$ docker run -d --name myapp -p 80:80 -v $(pwd):/var/www/html php:5.6-apache
```

 - **Nota:** En este caso atributo `-p` es con Minúscula.

Verificamos su ejecución con el comando `docker ps` y veremos nuestro proceso con el nombre `myapp`. 
