Indicaciones:

1. Descargar docker de la pagina oficial https://www.docker.com/

2. Clonar el repositorio actual del docker

3.  Ir al archivo docker-compose.yml y luego editar la linea ```/home/eren/projects/``` a la ruta donde estaran los proyectos de su equipo 

4. Ejecutar el comando ```docker compose up -d```

5. Una vez generado el contenedor tiene que buscarlo con el comando ```docker ps```
    y copia el CONTAINER ID donde el IMAGE es igual a ubuntuphp:v1

6. ejecutar docker compose exec -it CONTAINER_ID bash

7. Una vez dentro de la terminal del contenedor, acceder a la carpeta del proyecto que necesita

8.  En una pestaña ejecute el siguiente comando ```php artisan serve --host 0.0.0.0 --port 9090``` 

9. y en otra ```npm run dev -- --host``` para compilar los archivos

10. Listo, ahora vaya a su navegador y entre a la url http://127.0.0.1:9090/