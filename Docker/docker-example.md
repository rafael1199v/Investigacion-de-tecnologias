# Ejemplo de uso de docker

Una vez instalemos Docker, crearemos nuestra primer imagen con un Dockerfile!!!. Pero primero necesitamos algunos conceptos previos.

## FIGlet
Es una libreria para crear carateres grandes a partir de caracteres normales en las pantallas.  
Una vez instalado FIGlet podemos imprimir mensajes con una fuente de *starwars* con este comando:

```shell
figlet -w 200 -f starwars "Hello World"
```
> Que pasariía si quisieramos usar figlet independientemente del SO y con una configuracion ya establecida?  

*Esta es la dependencia que utilizaremos para simular la problematica que solucionan los contenedores con Docker*

## Creación Dockerfile
El contenido del dockerfile será así para la instalación de la dependencia.

```Dockerfile
FROM ubuntu:latest 
RUN apt-get update && apt-get install -y figlet wget
RUN wget http://www.jave.de/figlet/fonts/details/starwars.flf -O /usr/share/figlet/starwars.flf
CMD figlet -w 200 -f starwars "Hello World"
```

## Construcción de la imagen
Construimos la imagen con el Dockerfile con:

```Dockerfile
docker build -t "ascii" .
```

> Le adicionamos un nombre de etiqueta a la construcción de la imagen "ascii".
> El punto significa que queremos construir la imagen del dockerfile del mismo directorio.

Al final de construirse la imagen vamos a poder verla con el comando:
```
docker images
```

## Creación del contenedor y resultado
Y ejecutamos un nuevo contenedor de la imagen creada con:

```
docker run ascii
```

El resultado final deberia verse así.

```
 __    __   _______  __       __        ______      ____    __    ____  ______   .______       __       _______  
|  |  |  | |   ____||  |     |  |      /  __  \     \   \  /  \  /   / /  __  \  |   _  \     |  |     |       \
|  |__|  | |  |__   |  |     |  |     |  |  |  |     \   \/    \/   / |  |  |  | |  |_)  |    |  |     |  .--.  |
|   __   | |   __|  |  |     |  |     |  |  |  |      \            /  |  |  |  | |      /     |  |     |  |  |  |
|  |  |  | |  |____ |  `----.|  `----.|  `--'  |       \    /\    /   |  `--'  | |  |\  \----.|  `----.|  '--'  |
|__|  |__| |_______||_______||_______| \______/         \__/  \__/     \______/  | _| `._____||_______||_______/
```

Felicidades!!! Has creado tu primer contenedor desde un DockerFile.