# DOCKER CLOUD 🐋
### Contenido
1. Repaso
2. Docker Cloud
3. Instalación de Jenkis


----
## 1. Repaso 📝
Durante esta sesión se repasaron algunas cosas vistas en las anteriores sesiones como por ejemplo:
* Contenedores
* Imagenes

De igual manera se hicieron algunas explicaciones importantes acerca de: 
> Contribución de Docker
> Diferencia entre Docker y GitHub

----
## 2. Docker Cloud 🐋
Para empezar con el tema de Docker Cloud se debe ejecutar el  archivo Docker Compose, este proceso es bastante sencilla y lo puedes encontrar [aquí](https://jsgiraldoh.io/Blog/Archivo-docker-compose)

Cuando hayas hecho el proceso debería salirte una interfaz así:

[Interfaz Docker Cloud](https://drive.google.com/file/d/1TeLZs9ygGLh08rHNwfYRdD0nF1bTG2NO/view?usp=sharing)

Para crear varios contenedores utilizamos el siguiente comando:

> docker-compose up --scale web=5

#### Información importante:
>  version: '3' -> **La versión que se está utilizando, suele ser la última**
> 
>    services: -> Exísten dos servicios
>  
> web -> **servicio #1** *(Servicio web)*
>     image: dockercloud/hello-world
>     
>lb: -> **Servicio #2** (*Load balance*)
>     image: dockercloud/haproxy
>     
>links:
>     - web
>       
> volumes: -> **Docker de comunicación entre los dos servicios**
>       - /var/run/docker.sock:/var/run/docker.sock
>ports: -> **Puerto donde estará ubicado el servicio**
>       - 80:80
      

----


## 3. Instalación de Jenkis 👨🏻‍💼

Primero damos los permisos necesarios con el comando:

> sudo chown "usuario":"usuario" jenkins_home

Para correr Jenkis usamos el siguiente comando:
> docker-compose -f docker-compose-jenkins.yml up -d

Para ver la contraseña que Jenkis te pedirá cuando inicias por primera vez utiliza el comando:
> docker logs -f jenkins

Luego de ingresar te va a pedir descargar actualizaciones y listo! 

Tendrás una interfaz como la que se muestra en la siguiente imagen:

[Interfaz Jenkis](https://drive.google.com/file/d/1twqnMprslsJZT4N2G_VfLA3R9llX5GFF/view?usp=sharing)

La próxima vez que levantes el servicio te aparecerá un interfaz de inicio así

[Interfaz Inicio](https://drive.google.com/file/d/1RX_XSTHkaDAhRXTM9AEIwjLlWQGzk5XY/view?usp=sharing)
```
Información importante: Todos los archivos que crees en Jenkis se guardarán en la carpeta jenkins_home!

