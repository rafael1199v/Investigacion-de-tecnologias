# ¿Qué es Docker?
Docker es una plataforma abierta para desarrollar, compartir y ejecutar aplicaciones.Docker hace posible que las aplicaciones se separen de la infraestructura utilizada para asegurar una entrega de software mas rapido.

Docker provee la habilidad de empaquetar y ejecutar una aplicacion en un entorno ligeramente aislado llamado **contenedor**.

# ¿Para qué puedo usar Docker?
### Entrega rapida y consistente de tus aplicaciones
Docker agiliza el ciclo de vida del desarrollo, permitiendo a los desarrolladores trabajar en entornos estandarizados usando contenedores locales suministrando tus aplicaciones y servicios.

### Despliegue adaptable y escalable
La plataforma de docker basado en contenedores permite cargas de trabajo portables. Los contenedores Docker pueden correr en la computadora local de un desarrollador, en computadoras fisicas o virtuales en un centro de datos, en proveedores de servicios en la nube, y en una mezcla de entornos.

### Ejecutar mas cargas de trabajo en el mismo hardware
Docker es ligero y rapido. Provee una alternativa lviable a las maquinas virtuales basadas en hipervisores. Por esta razón puedes aprovechar mas la capacidad de tu servidor para lograr tus metas.

# Docker Desktop
Docker Desktop es una aplicación facil de instalar en un entorno de Linux, Mac or Windows, que te permite construir y compartir aplicaciones en contenedores y microservicios.  
#### Docker Desktop incluye:
* Docker daemon
* Docker client
* Docker Compose
* Docker Content Trust
* Kubernetes
* Credential Helper

# Objetos Docker
Cuando usas docker, estas creando y usando **imagenes**, **contenedores**, **redes**, **volumenes**, **plugins** y otros objetos.

### Imagenes
Una imagen es una plantilla de solo lectura con instrucciones para crear un contenedor Docker. Muchas veces una imagen esta basada en otra imagen con algunas configuraciones adicionales.  
Tu puedes crear tus propias imagenes o puedes imagenes creadas publicadas por otros usuarios en un registro.
Para crear tu propia imagen tienes que crear un **Dockerfile** con una sintaxis simple para definir los pasos necesarios para crear la imagen y ejecutarla.

### Contenedores
Un contenedor es una instancia en ejecución de una imagen. Puedes crear, iniciar, detener, mover o eliminar un contenedor usando la Docker API or CLI. Puedes conectar un contenedor a dos o mas redes y crear una imagen basada en el estado actual del contenedor.

Un contenedor es definido por su imagen como también las configuraciones definidas cuando creas o ejecutas el contenedor. Cuando un contenedor es removido, cualquier cambio a su estado no es guardado.
