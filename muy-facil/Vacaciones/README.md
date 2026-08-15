# DockerLabs: Vacaciones - Writeups (Muy Fácil)

¡Máquina vulnerada con exito, en la cual realice práctica de fuerza bruta contra SSH y escalada de privilegios


<img src="assets/hero.png" alt="">


## Resumen de la Auditoría

## Objetivo:

Laboratorio para practicar fuerza bruta contra SSH y escalada de privilegios en Linux

---


## Inicio

### Descripción de la VM - Vacaciones


Laboratorio para practicar fuerza bruta contra SSH y escalada de privilegios en Linux


### Creador:

- Romabri

---


## 📚 Comenzando

* Descargar la VM de DockerLabs - Hedgehog
* Descomprimir la VM desde la terminal de Kali

```
unzip hedgehog.zip
```


* Archivo descomprimido

```
auto_deploy.sh
```

* Pasar a Super_Usuario

```
sudo su
```

* Correr la VM

```
sudo ./auto_deploy.sh hedgehog.tar
```

<img src="assets/maquina.png" alt="">

<br></br>


## 1. Verificar Conectividad (Ping)

<img src="assets/revisar conexion icmp.png" alt="">

Conexión funcionando correctamente


<br></br>


## 2. Reconocimiento de Puertos y Servicios Abiertos

<img src="assets/reconocimiento de puertos.png" alt="">

Puertos abiertos

- 22/tcp open SSH 

- 80/tcp open HTTP


## 3. Enummeración Web

Tomando en cuenta que tengo el puerto 80/tcp abierto, intento ver en texto plano que encuentro

<img src="assets/enumeracion web.png" alt="">


### Revisión de Estructura de Directorios

<img src="assets/revision estructura directorios.png" alt="">

```
index.html -> al intentar ingresar con el link no hay nada que explotar 

javascript -> http://172.17.0.2/javascript/

Tampoco hay mucho en dicho link
```


## 4. Fase Intrusión - Acceso inicial 

En el paso de enumeración, tuve un resultado de 2 nombres, los cuales usare para esta fase de intrusión

<img src="assets/fase intrusion acceso inicial a mano.png" alt="">

¡No da ingreso! ... Pero

Como dice el texto plano...
De Juan para "Camilo"

## 5. Explotación

Entonces procedo a realizar lla explotación utilizando **Hydra**


<img src="assets/explotacion.png" alt="">

```
Login: camilo

Password: password1
```

Ya teniendo las credenciales ingresare por SSH


¡Perfecto!


## 6. Obtener Acceso

<img src="assets/obtener acceso.png" alt="">

Pude ingresar


## 7. Realizando Pivote

Podria leer el correo del que hablaba el texto anterior, dentro de la maquina para asi poder escalar al usuario **Juan**


Ejecuto como camilo

```
cd /var/mail/camilo
```

<img src="assets/realizando pivot.png" alt="">

Me dice que es un directorio...


## 8. Listar los Ficheros que estan dentro

```
ls -la
```

<img src="assets/listar ficheros.png" alt="">

Encontre un archivo .txt, a leerlo...


### Leyendo el contenido

```
cat correo.txt
```

<img src="assets/leyendo contenido.png" alt="">


Me entrego un mensaje y una contraseña que utilizare ahora...


## 9. Pasos Finales

Ahora ya debo realizar la elevacion de privilegios a **root**

All hacer un cambio de usuario a **Juan** y utilizando la contraseña encontrada en el archivo correo.txt, realizo un cambio de usuario y poara verificarlo se escribe un **whoami**

<img src="assets/cambio de usuario.png" alt="">


### Verificar Permisos de SuperUsuario de Juan

```
sudo -l
```

<img src="assets/verificar permisos.png" alt="">


Esto me dice que el usuario **Juan** puede ejecutar binario como root sin necesidad de contraseña


### Paso Final

Pasar a **root** ejecutare el payload de Ruby listado en **GTFOBins**

```
sudo ruby -e 'exec "/bin/sh"'
```

<img src="assets/paso final.png" alt="">

Y ya ejecutando **whoami** nos da como resultado **root**



