# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine
<img width="901" height="619" alt="Captura de pantalla 2026-04-17 a la(s) 1 27 38 p  m" src="https://github.com/user-attachments/assets/6f4453db-86df-43b0-a5e4-32dd863266be" />

Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world
<img width="901" height="619" alt="Captura de pantalla 2026-04-17 a la(s) 1 33 11 p  m" src="https://github.com/user-attachments/assets/7e10a046-2882-4f74-a7f1-b2382f746b42" />

### Listar los contenedores ejecutándose o no

```
docker ps -a
```

### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```
Iniciar el contenedor srv-web 
<img width="901" height="619" alt="Captura de pantalla 2026-04-17 a la(s) 1 34 27 p  m" src="https://github.com/user-attachments/assets/f5918d4a-abef-4a65-873a-0f68a8975552" />

### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```

### Para detener un contenedor

```
docker stop <nombre contenedor>
```

### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>
```
![Ecosistema de Docker](dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine
<img width="917" height="636" alt="Captura de pantalla 2026-04-17 a la(s) 1 36 18 p  m" src="https://github.com/user-attachments/assets/390aac04-299e-4443-9048-f4faf66eb2a5" />

**¿Qué sucede luego de la ejecución del comando?**
El terminal entra en modo Attached porque el proceso que corre en primer plano. No se puede usar la ventana de la terminal para otros comandos hasta detener el proceso con ctrl + c.

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine
<img width="917" height="636" alt="Captura de pantalla 2026-04-17 a la(s) 1 37 51 p  m" src="https://github.com/user-attachments/assets/be4eafc3-504d-4276-b5f4-815d43bd1033" />

### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```
Eliminar el contenedor que se creó a partir de la imagen hello-world 
<img width="917" height="636" alt="Captura de pantalla 2026-04-17 a la(s) 1 40 09 p  m" src="https://github.com/user-attachments/assets/d9761505-4919-42bd-a1ff-9ad8bf5ba88c" />

Verificar que el contenedor que se eliminó
<img width="917" height="636" alt="Captura de pantalla 2026-04-17 a la(s) 1 40 30 p  m" src="https://github.com/user-attachments/assets/ba6b2a11-31b2-4b4b-a973-19bc9c629777" />

### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```
Eliminar el contenedor **srv-web3** 
<img width="917" height="636" alt="Captura de pantalla 2026-04-17 a la(s) 1 40 53 p  m" src="https://github.com/user-attachments/assets/d72d1609-6f2b-40ee-93dc-247de447c4f2" />

Verificar que el contenedor que se eliminó
<img width="917" height="636" alt="Captura de pantalla 2026-04-17 a la(s) 1 41 02 p  m" src="https://github.com/user-attachments/assets/d5e4fbef-e0e7-46b7-befa-f09ff705d8e9" />

### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 
<img width="917" height="636" alt="Captura de pantalla 2026-04-17 a la(s) 1 41 41 p  m" src="https://github.com/user-attachments/assets/d2d43bee-5cc1-4562-ab86-1ea089736ee0" />
