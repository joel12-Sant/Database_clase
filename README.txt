Nota:olvide colocarlo en los pasos pero antes de ejecutar el comando " docker compose up -d " no se olviden de usar el comando sudo su para tener privilegios de administrador 

1.-Extrae el documento .zip en la ruta que desees 
2.-Ingresa a la carpeta que acabas de extraer y abre una terminal desde ahi
3.-Ejecuta el comando " docker compose up -d " sin las comillas para que puedas levantar el contenedor
4.-Ejecuta el comnado " docker ps " para poder ver los contenedores que estan corriendo y copia el id del contenedor que tenga la imagen de mysql
5.-Ejecuta el siguiente comando " docker cp backup.sql id_contenedor:/backup.sql " reemplaza la parte que dice id_contenedor por el id que copiaste en el paso anterior
6.-Ejecuta el comando " docker exec -it id_contenedor mysql -u root -p " reemplaza la parte que dice id_contenedor por el id que copiaste en el paso anterior, te pedira que ingreses una contraseña: "root"
7.-coloca la siguiente instruccion " create database olympics; "
8.-coloca la siguiente instruccion " use olympics; "
9.-coloca la siguinete instruccion " source backup.sql "

listo ya tendras todas las tablas de la base de datos en tu contendor, estas instrucciones solo es nesesario hacerlas una vez.
Si quieres cambiar el puerto pudes hacerlo desde el archivo docker-compose.yml, por defecto el puerto es el 8082
