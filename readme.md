# Imagen de docker con Ubuntu, Wine, Metatrader, ZeroMq, VNC y Fluxbox


Clonar este directorio y su contenido.

Levantar la imagen con 

`docker build . -t headless-metatrader4:latest_vnc`

Modificar del docker-compose.yml para indicar el directorio
 local de Darwinex_MT4 e inciar el contenedor con
 
 `docker-compose up`
 
 Se puede conectar con VNC usando la contrase¤a 3579  (se puede modificar en 
 el archivo run_mt.sh)