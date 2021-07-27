# Primeras Creaciones 💻

En esta sesión se realizaron las primeras creaciónes en docker y se habló de varios temas 


# Parte Práctica 👩‍💻
## Mi primer DockerFile


Pasos para crear mi primer docker 

**1.** Crear carpeta con el comando 
> mkdir mi-primer-dockerfile

**2.** Entramos a la carpeta 

**3.** Entramos a editar el dockerfile con vim
> vim Dockerfile

Cuando estemos adentro copiamos lo siguiente:
> FROM nginx
> COPY static-html-directory /usr/share/nginx/html

para alojar contenido estático simple

**4.** Creamos nueva carpeta llamada static-html-directory
> mkdir static-html-directory

**5.** Entramos en ella y abrimos el documento index.html

> cd static-html-directory
> vim index.html

Escribimos algo que quisieramos mostrar en la pantalla de nuestro navegador, para esta práctica escribi: 



> docker image build -t some-content-nginx .
```Prueba para el curso de Docker del semillero de Fedesoft```

volvemos a nuestra anterior carpeta

## Crear Imagen

creamos una imagen con el siguiente comando:

> docker image build -t some-content-nginx .

listamos las imagenes que hay en el docker para verificar

> docker image ls

## Crear cuenta de docker hub

Para poder crear repositorios debemos tener una cuenta en docker hub se crea [aquí](https://hub.docker.com/)

## Conectarnos a nuestra cuenta

Para conectarnos ponemos el comando:
> docker login

Luego nos solicitará nuestros datos de usuario y contraseña

## Crear un tag de nuestra imagen anterior
Para crear un tag de una imagen usamos el siguiente comando:

> docker tag some-content-nginx jsgiraldoh/fedesoft-web

ahora guardamos en nuestro repositorio de docker hub

> docker push nombrerepositorio/fedesoft-web

Y listo!! ya tenemos nuestra imagen, tag, y repositorio

# Parte Teórica 📖

### Imágenes

Se explicó algunas características de las imágenes

* Una imagen es una plantilla de solo lectura con instrucciones para crear un contenedor Docker
* Puedes crear tus propias imagenes o puedes utilizar ya creadas por otros usuarios


### Contenedores
Contenedor es una instancia ejecutable de una imagen

### Imagenes y contentedores y acciones 
se explicaron algunas acciones que se pueden realizar como por ejemplo
* Pull
* Push
* Build
* Run
 


