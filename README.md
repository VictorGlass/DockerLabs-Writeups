<div align="center">

  # 🧪 DockerLabs Writeups & Penetration Testing Portfolio

  <p align="center">
    <b>Colección centralizada de writeups, metodologías de explotación y escalada de privilegios en laboratorios de DockerLabs.</b>
  </p>

  [![GitHub Stars](https://img.shields.io/github/stars/VictorGlass/DockerLabs-Writeups?style=for-the-badge&color=00f2fe)](https://github.com/VictorGlass/DockerLabs-Writeups/stargazers)
  [![Profile](https://img.shields.io/badge/Author-VictorGlass-4facfe?style=for-the-badge&logo=github)](https://github.com/VictorGlass)
  [![Platform](https://img.shields.io/badge/Platform-DockerLabs-111827?style=for-the-badge&logo=docker)](https://dockerlabs.es/)
  [![License](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)

</div>

---

## 📌 Sobre este Repositorio

Este repositorio contiene la documentación detallada y paso a paso (**Writeups**) de la resolución de máquinas virtuales y entornos vulnerables de la plataforma **DockerLabs**. 

El objetivo principal es documentar el proceso de aprendizaje en pruebas de penetración (*pentesting*), análisis de vectores de ataque, explotación de servicios y técnicas de escalada de privilegios en entornos controlados basados en contenedores Docker.

---

## 📊 Progreso & Estadísticas

```text
  [██████████..........] Muy Fácil (4/8)  - 100%
  [....................] Fácil     (0/68)  - 0%
  [....................] Media     (0/0)  - 0%
  [....................] Difícil   (0/0)  - 0%
  [....................] Insana    (0/0)  - 0%
```

---

## 📂 Índice de Máquinas Resueltas

### 🟢 Nivel: Muy Fácil
| Máquina | SO / Entorno | Vectores & Técnicas Principales | Writeup |
| :--- | :---: | :--- | :---: |
| **Tproot** | 🐧 Linux | vsftpd 2.3.4 (`CVE-2011-2523`), Explotación Manual | [📄 Leer Writeup](./muy-facil/DockerLabs-Tproot/) |
| **Trust** | 🐧 Linux | Nmap, Gobuster, Fuerza bruta SSH, GTFOBins (`Vim`) | [📄 Leer Writeup](./muy-facil/DockerLabs-Trust/) |
| **FirstHacking** | 🐧 Linux | Reconocimiento de servicios, Integridad en archivos | [📄 Leer Writeup](./muy-facil/DockerLabs-FirstHacking/) |
| **BreakMySSH** | 🐧 Linux | Auditoría de SSH, Ataques de autenticación, Hardening | [📄 Leer Writeup](./facil/DockerLabs-BreakMySSH/) |

### 🟡 Nivel: Fácil
*Próximamente...*

### 🟠 Nivel: Media
*Próximamente...*

### 🔴 Nivel: Difícil
*Próximamente...*

### 🟣 Nivel: Insana
*Próximamente...*

---

## 🧰 Toolkit & Arsenal de Herramientas

* **Reconocimiento & Fuzzing:** `Nmap`, `Gobuster`, `Wfuzz`, `FFUF`
* **Explotación:** `Netcat`, `Metasploit Framework`, Scripts personalizados
* **Escalada de Privilegios:** `GTFOBins`, Auditoría de Permisos SUID/Capabilities, `LinPEAS`

---

## 🛠️ Estructura del Repositorio

```text
DockerLabs-Writeups/
├── muy-facil/          <-- Máquinas de nivel introductorio / fácil
├── facil/              <-- Máquinas de nivel básico
├── media/              <-- Máquinas de nivel intermedio
├── dificil/            <-- Máquinas de nivel avanzado
├── insana/             <-- Desafíos de nivel experto
└── README.md           <-- Índice principal del proyecto
```

---

<div align="center">

⭐ **Si este contenido te resulta útil, ¡no dudes en darle una estrella al repositorio!** ⭐

*Creado por [VictorGlass](https://github.com/VictorGlass) con fines puramente educativos.*

</div>
