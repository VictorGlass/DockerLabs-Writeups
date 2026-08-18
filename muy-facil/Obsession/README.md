# DockerLabs: Obsession - Writeups (Muy Fácil)

¡Máquina vulnerada don exito, en la cual realice une enumeracion en web, hacking de protocolos, SSH y FTP


<img src="assets/hero.png" alt="">


## Resumen de la Auditoría

## Objetivo:

Enumeración de rutas en web, y hacking de protocolos de red, principalmente SSH y FTP

---


## Inicio

### Descripción de la VM - Obsession


Enumeración de rutas web y hacking de protocolos de red, principalmente SSH y FTP


### Creador:

- Juan

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


## 1. Revisión de Conectividad por paquetes ICMP

<img src="assets/1 revision conectividad.png" alt="">


<br></br>


## 2. Reconocimiento de Puertos y Servicios

<img src="assets/2 reconocimiento de puertos.png" alt="">


<br></br>


## 3. Intento Conexión Mediante Login Anónimo

Claramente existe el puerto 21/tcp FTP por el cual podemos intentar un acceso sin credenciales

<img src="assets/3 intento de conexion mediante login.png" alt="">


<br></br>


## 4. Enumeración de Archivos dentro de FTP


<img src="assets/4 enumeracion de archivos dentro de ftp.png" alt="">


<br></br>


## 5. Descargo los Archivos

<img src="assets/5 descargar archivos.png" alt="">


<br></br>


## 6. Leer el Contenido

<img src="assets/6 leer contenido.png" alt="">

Nombres dde usuarios potenciales


<br></br>


## 7. Ataque de Fuerza Bruta con Hydra al Puerto SSH

<img src="assets/7 ataque fuerza bruta hydra.png" alt="">


<br></br>


## 8. Intento de Conexión por SSH

<img src="assets/8 intento de conexion por SSH.png" alt="">


<br></br>


## 9. Reconocimiento Inicial de Sistema

<img src="assets/9 reconocimiento inicial de sistema.png" alt="">


<br></br>


## 10. Veamos que privilegios de admin tiene

<img src="assets/10 que privilegios tiene.png" alt="">

<br></br>


## 11. Esccalando privilegios de Usarios

<img src="assets/11 ejecutar vim con privilegios de root.png" alt="">


<br></br>


## 12. Dentro del Editor VM escribir

<img src="assets/12 dentro de editor vim.png" alt="">

<img src="assets/12.1 dentro de editor vim.png" alt="">


<br></br>


## 13. Verificar el Nuevo Estatus

<img src="assets/13 verificar el nuevo status.png" alt="">


