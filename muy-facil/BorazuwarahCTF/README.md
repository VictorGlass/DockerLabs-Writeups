# DockerLabs: BorazuwarahCTF - Writeups (Muy Fácil)

¡Máquina vulnerada con exito, en la cual realice reconocimiento de puertos y servicios, ademas de una tecnica de investigación de metadatos

<img src="assets/hero.png" alt="">


## Resumen de la Auditoría

## Objetivo:

Enumeración de rutas en web, y hacking de protocolos de red, principalmente SSH y FTP

---


## Inicio

### Descripción de la VM - Obsession


Laboratorio para practicar estaganografía y fuerza bruta contra protocolos de red


### Creador:

- Borazuwarah

---


## 📚 Comenzando

* Descargar la VM de DockerLabs - Hedgehog
* Descomprimir la VM desde la terminal de Kali

```
unzip borazuwarahctf.zip
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
sudo ./auto_deploy.sh borazuwarahctf.tar
```

<img src="assets/maquina.png" alt="">

<br></br>


## 1. Revisión de Conexión por paquetes ICMP

<img src="assets/1 revision de conectividad.png" alt="">

Existe conexión exitosa

<br></br>


## 2. Reconocimiento de Puertos y Servicios

<img src="assets/2 escaneo de puertos.png" alt="">

Puerto:

```
Puerto 22: Servicio SSH

Puerto 80: Servidor Web HTTP
```

<br></br>


## 3. Enumeración Web

<img src="assets/3 enumeracion web.png" alt="">

Al ingresar en el navegador con **http://172.17.0.2** encuentro una pagina web simple, solo una imagen

<br></br>


### Inspección con Exiftool 

<img src="assets/4 inspeccion de la imagen metadatos.png" alt="">

Se aprecia un nombre de usuario pero no la contraseña

Además, en la pagina web no existe panel web evidente.

<br></br>


## 4. Explotación usando Hydra

<img src="assets/5 ataque fuerza bruta con hydra.png" alt="">

Se obtiene el usuario el cual concuerda con el obtenido usando **exiftool**, además que aparece la contraseña

<br></br>


## 5. Intentando Conexión por SSH

<img src="assets/6 conexion via ssh.png" alt="">

Al utilizar la contraseña obtenida anteriormente, ya es posible entrar

<br></br>


## 6. Escalada Root

<img src="assets/7 escalada de privilegios.png" alt="">

Indica una linea **(ALL) NO PASSWD: /bin/bash**.

Significa que el usuario puede invocar una shell root directamente


<br></br>


## 7. Convertirse en usuario Admin

<img src="assets/8 pasar a super usuario.png" alt="">

<img src="assets/usuario admin.png" alt="">

Listo, de esta forma ya comprometi la VM



