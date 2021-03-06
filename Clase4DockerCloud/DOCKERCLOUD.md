# DOCKER CLOUD 馃悑
### Contenido
1. Repaso
2. Docker Cloud
3. Instalaci贸n de Jenkis


----
## 1. Repaso 馃摑
Durante esta sesi贸n se repasaron algunas cosas vistas en las anteriores sesiones como por ejemplo:
* Contenedores
* Imagenes

De igual manera se hicieron algunas explicaciones importantes acerca de: 
> Contribuci贸n de Docker
> Diferencia entre Docker y GitHub

----
## 2. Docker Cloud 馃悑
Para empezar con el tema de Docker Cloud se debe ejecutar el  archivo Docker Compose, este proceso es bastante sencilla y lo puedes encontrar [aqu铆](https://jsgiraldoh.io/Blog/Archivo-docker-compose)

Cuando hayas hecho el proceso deber铆a salirte una interfaz as铆:

[Interfaz Docker Cloud](https://drive.google.com/file/d/1TeLZs9ygGLh08rHNwfYRdD0nF1bTG2NO/view?usp=sharing)

Para crear varios contenedores utilizamos el siguiente comando:

> docker-compose up --scale web=5

#### Informaci贸n importante:
>  version: '3' -> **La versi贸n que se est谩 utilizando, suele ser la 煤ltima**
> 
>    services: -> Ex铆sten dos servicios
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
> volumes: -> **Docker de comunicaci贸n entre los dos servicios**
>       - /var/run/docker.sock:/var/run/docker.sock
>ports: -> **Puerto donde estar谩 ubicado el servicio**
>       - 80:80
      

----


## 3. Instalaci贸n de Jenkis 馃懆馃徎鈥嶐煉?

Primero damos los permisos necesarios con el comando:

> sudo chown "usuario":"usuario" jenkins_home

Para correr Jenkis usamos el siguiente comando:
> docker-compose -f docker-compose-jenkins.yml up -d

Para ver la contrase帽a que Jenkis te pedir谩 cuando inicias por primera vez utiliza el comando:
> docker logs -f jenkins

Luego de ingresar te va a pedir descargar actualizaciones y listo! 

Tendr谩s una interfaz como la que se muestra en la siguiente imagen:

[Interfaz Jenkis](https://drive.google.com/file/d/1twqnMprslsJZT4N2G_VfLA3R9llX5GFF/view?usp=sharing)

La pr贸xima vez que levantes el servicio te aparecer谩 un interfaz de inicio as铆

[Interfaz Inicio](https://drive.google.com/file/d/1RX_XSTHkaDAhRXTM9AEIwjLlWQGzk5XY/view?usp=sharing)
```
Informaci贸n importante: Todos los archivos que crees en Jenkis se guardar谩n en la carpeta jenkins_home!

