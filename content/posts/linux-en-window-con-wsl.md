---
title: "Linux en Window con WSL"
date: 2022-10-19T11:00:26-04:00
draft: false
---

# Introducción

**Linux** o mejor dicho **GNU Linux** para referirnos a EL sistema operativo. Si bien no es muy popular para el usuario común, es el más utilizado en el mundo de los servidores y también el preferido entre muchos desarrolladores de software. Y como dicen, “para gustos, colores”; existen diferentes distribuciones de Linux para todo tipo de usuarios, entre las más populares tenemos a Ubuntu, Manjaro, Debian entre muchas otras.

Bien, como usuarios de Windows que somos y queremos empezar a usar Linux pero también conservar nuestro querido Windows tenemos 2 opciones:

1. Instalar una máquina virtual (usando VMware o Virtual Box) el cual si nuestro ordenador tiene pocos recursos, la experiencia al usarlo dejará mucho que desear.
2. Formatear tu disco duro y/o hacer una partición con DUAL BOOT. Esta opción es bastante tentadora; al iniciar nuestra computadora tendremos la opción de elegir si iniciar con Windows o Linux. Esta opción puede ser algo desafiante si recién estas iniciando.

Sin embargo desde hace tiempo el equipo de Microsoft ha desarrollado un proyecto el cual también es una opción para usar Linux manteniendo Windows a la mano:

1. **Windows Subsystem for Linux** nos da la posibilidad de usar Linux y absolutamente todo su poder como si fuera un programa más dentro de Windows.

Antes de continuar en el caso de que estes comenzando desde cero a manejar  Linux te recomiendo algunas cosas:

- Tener conocimientos básicos del manejo de la terminal. Si estas incursionando en el área de informática desplazarse en la terminal te ayudará bastante
- Procura guiarte de fuentes conocidas y mejor aún si tenemos documentación oficial. En la presente procuraré dejarte los enlaces para que puedas consultarlos
- Tener tu Windows ya sea el 10 u el 11 actualizado.

### ¿Qué es WSL?

Windows Subsystem for Linux (WSL) es un entorno de terminal completo. Nos ayuda a desarrollar aplicaciones multiplataforma,  o para flujos de trabajo de desarrollo web y administrar la infraestructura de TI o en la ciencia de datos sin salir de Windows. WSL actualmente se encuentra en la versión 2 y es en esa versión la cual usaremos.

### ¿Por qué WSL?

Las primeras veces que quise aprender Bash y manejar Linux en general opté por la opción de hacer el famoso Dual BOOT, el cual personalmente (muy personalmente) se me hizo muy complicado y me dejo diferentes problemas; desde el MBR (Master Boot Record) hasta la instalación de los drivers para la tarjeta de red. WSL resulta bastante conveniente para usar Linux.

También hay programas como Git, Ansible, Docker entre muchos otros que se llevan mejor con Linux, y para usarlos en Windows en algunos casos puede llegar a complicarse.

### ¿Quiénes necesitan WSL?

Principalmente:

- Entusiastas aprendices de bash y linux en general
- Desarrolladores de Software
- Administradores de infraestructura TI
- Personas de la rama de Ciencia de Datos

# Instalación

## Instalación rápida

Vamos a la instalación, esto no tiene que ser complicado y tampoco necesitas un videotutorial de 30 minutos para hacerlo, ya existe la guía completa que puedes encontrarla en la documentación en [este enlace](https://learn.microsoft.com/es-es/windows/wsl/install). Pero por motivos de simplicidad puedes hacer lo siguiente:

- Abre una terminal, puedes usar el CMD o PowerShell
- `wsl --install`

Ya de ahí se instalará la distribución por defecto (Ubuntu) y te pedirá un usuario y contraseña. Así de simple.

## Instalación específica de una distribución de Linux

Antes de continuar debemos tener en cuenta 2 aspectos muy importantes.

- Habilitar en “Caracteristicas de Windows”
    - Virtualización
    - Subsistema para Linux
- Habilitar la virtualización desde la BIOS

### Listar las distribuciones disponibles

Para ver las distribuciones disponibles podemos ejecutar el comando `wsl --list --online` y nos mostrará algo así:

```bash
The following is a list of valid distributions that can be installed.
The default distribution is denoted by '*'.
Install using 'wsl --install -d <Distro>'.

  NAME            FRIENDLY NAME
* Ubuntu          Ubuntu
  Debian          Debian GNU/Linux
  kali-linux      Kali Linux Rolling
  openSUSE-42     openSUSE Leap 42
  SLES-12         SUSE Linux Enterprise Server v12
  Ubuntu-16.04    Ubuntu 16.04 LTS
  Ubuntu-18.04    Ubuntu 18.04 LTS
  Ubuntu-20.04    Ubuntu 20.04 LTS
```

### Instalación de Ubuntu

Como vimos anteriormente tenemos una variedad de opciones, sin embargo en la presente vamos a instalar Ubuntu en su versión más reciente, para esto podemos dirigirnos a su documentación de Microsoft en [este enlace](https://ubuntu.com/wsl) donde nos muestra una guía para Windows 10 y 11, pero son prácticamente la misma. Además instalaremos a versión [Ubuntu 22.04 LTS](https://apps.microsoft.com/store/detail/ubuntu-22041-lts/9PN20MSR04DW), 

Par aesta instalación al ir al enlace de Ubuntu 22.04 LTS nos llevará a la página de Microsoft Store la cual podremos instalar de forma gráfica

### Configurar la versión de WSL

También podemos elegir la versión de **WSL** ya sea la versión `1` o `2` (la 2 es la recomendada).

```bash
wsl --set-default-version <Version#>
```

### Configurar la distribución por defecto

Algo que podemos hacer para cambiar de distribución de Linux que se instalará por defecto es usar el comando:

```bash
wsl --set-version <distro name> 2
```

Podemos substituir `<distro name>` por el nombre de la distribución de Linux que queramos. Por ejemplo, `wsl --set-version Ubuntu-20.04 2` establecerá la distribución de Ubuntu 20.04 para usar WSL 2.

Un problema muy común es que la virtualización está deshabilitada en el menú BIOS de su dispositivo, así que actívalo!

# ¿Y ahora qué sigue?

Una vez tenemos corriendo nuestra terminal de Ubuntu tenemos en terminal instalado algunos programas de línea de comandos como:

- BASH
- SSH
- GIT
- APT
- NPM
- PIP

y muchas más. 

## ¿Qué más podemos hacer?

Pero no solo eso, también hay algunas cosas que podemos hacer y te las menciono a continuación.

### WSL.exe

Esta poderosa herramienta no solo es bonita, sino también nos ofrece diferentes opciones como:

- Podemos elegir una partición del disco duro para instalar nuestras distros
- Cambiar el directorio principal
- Importar una nueva distribución

Entre muchas otras opciones que puedes consultar en [este enlace de comandos básicos de WSL](https://learn.microsoft.com/es-es/windows/wsl/basic-commands).

### Instalación de programas comunes

- [VSCode](https://learn.microsoft.com/es-es/windows/dev-environment/javascript/nodejs-on-wsl?source=recommendations#install-visual-studio-code)
- [Node.js, NPM, NVM](https://learn.microsoft.com/es-es/windows/dev-environment/javascript/nodejs-on-wsl)

### Instalación de Terminal Windows

De forma opcional y casi con fines estéticos podemos instalar la terminal de Windows permite abrir varias pestañas o varios paneles para mostrar y cambiar rápidamente entre varias distribuciones de Linux u otras líneas de comandos, esto lo puedes descargar desde la Microsoft Store, para más detalles te dejo **[este enlace](https://learn.microsoft.com/es-es/windows/terminal/install)**.

## Fuentes y Enlaces

[Instalación de WSL](https://learn.microsoft.com/es-es/windows/wsl/install)

[WSL | Ubuntu](https://ubuntu.com/wsl)

[Get Ubuntu 22.04.1 LTS from the Microsoft Store](https://apps.microsoft.com/store/detail/ubuntu-22041-lts/9PN20MSR04DW)

[Pasos de instalación manual para versiones anteriores de WSL](https://learn.microsoft.com/es-es/windows/wsl/install-manual)
