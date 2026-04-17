# Imagen
### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**
<img width="1021" height="653" alt="Captura de pantalla 2026-04-17 a la(s) 1 07 25 p  m" src="https://github.com/user-attachments/assets/9c4fb726-d208-4c05-be94-2dd33e5df1e5" />

**¿Qué es nginx?**
Es un servidor web de alto rendimiento, proxy inverso y balanceador de carga. Destaca por su arquitectura orientada a eventos y asincrónica, lo que le permite manejar miles de conexiones simultáneas con un consumo de memoria mínimo comparado con servidores tradicionales como Apache.

Descargar la imagen  **nginx** en la versión **alpine**
<img width="1021" height="653" alt="Captura de pantalla 2026-04-17 a la(s) 1 09 16 p  m" src="https://github.com/user-attachments/assets/ac57441b-b1ae-42b8-af3a-480d40f24680" />

### Listar imágenes

```
docker images
```

<img width="1021" height="653" alt="Captura de pantalla 2026-04-17 a la(s) 1 10 59 p  m" src="https://github.com/user-attachments/assets/b0cbc6a9-141e-464e-b666-1f62015626c4" />

**Identificadores**

En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 
<img width="1021" height="653" alt="Captura de pantalla 2026-04-17 a la(s) 1 12 10 p  m" src="https://github.com/user-attachments/assets/fe28f951-6948-4638-8397-7f90bdd36342" />

**¿Con qué algoritmo se está generando el ID de la imagen**
Se utiliza el algoritmo SHA256 (Secure Hash Algorithm 256-bit).

### Filtrar imágenes

```
docker images | grep <termino a buscar>

```

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world 
<img width="1021" height="653" alt="Captura de pantalla 2026-04-17 a la(s) 1 13 57 p  m" src="https://github.com/user-attachments/assets/d0aaf786-b8c1-4bcc-bae7-b2dd7a62fa6c" />

-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```
