# Mapeo de puertos
El mapeo de puertos es un mecanismo que permite redirigir el tráfico de red desde un puerto en el host (tu máquina local o servidor) hacia un puerto específico en un contenedor Docker.
Por ejemplo, supongamos que tienes un contenedor que ejecuta un servidor web en el puerto 80 dentro del contenedor, pero quieres acceder a ese servidor desde tu navegador en la máquina host. Puedes usar el mapeo de puertos para redirigir el tráfico del puerto 80 del contenedor al puerto 3000 en el host. De esta manera, cuando accedas a http://localhost:3000 en tu navegador, el tráfico se dirigirá al servidor web dentro del contenedor en el puerto 80.

![mapeo](mapeoPuertos.PNG)

### Para crear un mapeo de puertos (puerto host y puerto contenedor)
El mapeo de puertos se especifica al ejecutar un contenedor Docker utilizando la opción -p o --publish seguida de los puertos que deseas mapear
```
docker run -d --name <nombre contenedor> -p <puerto host>:<puerto contenedor> <nombre imagen>:<tag>

```
Crear un contenedor a partir de la imagen nginx version alpine con el mapeo de puertos del ejemplo gráfico, host 3000 y contenedor 80
<img width="917" height="636" alt="Captura de pantalla 2026-04-17 a la(s) 2 12 42 p  m" src="https://github.com/user-attachments/assets/7c68d9b3-cf67-4764-9463-784711eac608" />

# COLOCAR UNA CAPTURA DE PANTALLA  DEL ACCESO http://localhost:3000
<img width="1624" height="1061" alt="Captura de pantalla 2026-04-17 a la(s) 2 13 03 p  m" src="https://github.com/user-attachments/assets/30d19d41-e60a-400a-bae5-d8b91ac1d359" />

### Para mapear más de un puerto

```
docker run -d --name <nombre contenedor> -p <puerto host 01>:<puerto contenedor 01> -p <puerto host 02>:<puerto contenedor 02> <nombre imagen>:<tag>
```

Crear un contenedor a partir de la imagen rabbitmq version management-alpine, para este mapeo de puertos usar en el host los mismos puertos del contenedor.
<img width="837" height="585" alt="imagen" src="https://github.com/user-attachments/assets/9d86baed-9023-4a24-97c9-4dd4a3f69f4d" />

### Usando una forma más semántica cuando se especifican puertos

```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> <nombre imagen>:<tag> 
```
### Publicando todos los puertos
```
docker run -P -d --name <nombre contenedor> <nombre imagen>:<tag> 
```

-P: le indica a Docker que asigne automáticamente puertos aleatorios en tu host para todos los puertos expuestos por el contenedor.

**Recordar**
No puedes mapear puertos a un contenedor existente directamente después de su creación con Docker. El mapeo de puertos debe especificarse en el momento de crear y ejecutar el contenedor.

### Crear contenedor de Jenkins puertos contenedor: 8080 (interface web) y 50000 (comunicación entre nodos) imagen: jenkins/jenkins:alpine3.18-jdk11
<img width="917" height="636" alt="Captura de pantalla 2026-04-17 a la(s) 2 18 21 p  m" src="https://github.com/user-attachments/assets/19e4debd-daf4-4881-999b-2f4e7f4a75de" />

# COLOCAR UNA CAPTURA DE PANTALLA  DEL ACCESO http://localhost:8080
<img width="1624" height="1061" alt="Captura de pantalla 2026-04-17 a la(s) 2 18 37 p  m" src="https://github.com/user-attachments/assets/3de9dde1-845b-44ed-92bf-df8257631951" />


### ¿Cómo obtener la contraseña solicitada?
Para obtener la contraseña solicitada es necesario ingresar al contenedor.

![Imagen](jenkins.PNG)

