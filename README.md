# SistemasInformaticos

## AGREGAR UN HTML PERSONALIZADO EN NGINX A TRAVÉS DE DOCKER

Una vez con docker en nuestra máquina, nos instalamos la imagen de nginx a través del comando 
``sudo pull nginx``

<img width="359" alt="nginxblabla" src="https://user-images.githubusercontent.com/91744554/168890234-c037c722-24d5-41d7-ad14-c3fa22270aa5.png">

Y posteriormente el comando ``docker run --rm -d -p 8080:80 --name web nginx`` que será para iniciar nuestra imagen. La ejecución del contenedor como demonio (-d), puerto 8080 en la red local y de nombre --name, que podremos personalizar.

Una vez que ya tenemos en nginx en docker, modificaremos el HTML para que muestre nuestro nombre cuando se accede.
La ruta base es ``/usr/share/nginx/html``, aunque crearemos una carpeta para alojar nuestro HTML. El directorio final será
``/home/diegoms/Documents/nginx/sistemas``

Usaremos el siguiente código:
``` 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Actividad Sistemas</title>
</head>
<body>
    <h1>DIEGO MORRO SILVA</h1>
</body>
</html>
```

Este código lo guardaremos como ``index.html`` y lanzaremos el siguiente comando:
``docker run --rm -d -p 8080:80 --name web -v /home/diegoms/Documents/nginx/sistemas:/usr/share/nginx/html nginx``

El resultado es el siguiente:

<img width="358" alt="DIEGOMORRO" src="https://user-images.githubusercontent.com/91744554/168892420-6fe8a703-33f9-4ca7-963a-b4fb572a5656.png">




