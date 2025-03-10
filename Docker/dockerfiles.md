# Dockerfiles
Docker puede construir imagenes directamente de leer instrucciones de un Dockerfile. Un Dockerfile es un documento de texto que contiene todos los comandos que el usuario puede usar en la linea de comandos para construir la imagen.

## Instrucciones

| Instrucción  | Descripción |
| :-------------: |:-------------:|
| ADD           | Añadir archivos/directorios locales o remotos     |
| ARG           | Usar variables en tiempo de compilación     |
| CMD           | Especificar comandos default     |
| COPY          | Copiar archivos y directorios   |
| ENV           | Configurar variables de entorno   |
| EXPOSE        | Describir cuales puertos esta escuchando tu applicación   |
| FROM          | Ejecutar comandos de construcción  |
| WORKDIR       | Cambiar el directorio de trabajo  |
| SHELL       | Configurar el shell por default de la imagen  |

## Formato
El formato de un Dockerfile es:
```
INSTRUCCION argumentos
```
Las instrucciones no distinguen entre mayúsculas o minúsculas.

#### Importante
Docker ejecuta las instrucciones en el orden del Dockerfile. Un Dockerfile **debe comenzar con una instrucción ```FROM```**.  
La instrucción ```FROM``` especifica la base de la imagen de la cual se esta construyendo. Esta instrucción solo puede ser precedida por uno o mas instrucciones ```ARG```

## Comentarios
BuildKit trata a las lineas que comienzan con ```#``` como un comentario, a menos de que la linea es una directiva parser valida.

```docker
# Comentario
RUN echo 'hello-world'
```

