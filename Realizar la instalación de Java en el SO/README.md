## Instalación de JDK en el Ubuntu
_Nerae Glez._

- __Indice__
1. [¿Como instalar Java en Ubunt en desde repositorio?](#como-instalar-java-en-ubunt-en-desde-repositorio)
2. [¿Como instalar una version especifica de Java?](#como-instalar-una-version-especifica-de-java)
3. [Configuracion de las variables del entorno](#configuracion-de-las-variables-del-entorno)


## ¿Como instalar Java en Ubunt en desde repositorio?
- Lo primero debemos de actualizar el sistema con:

``` 
  sudo apt-get update
```
- Salida.  

```
nereaglez@nereaglez-VirtualBox:~$ sudo apt-get update
[sudo] contraseña para nereaglez:         	 
Obj:1 http://archive.ubuntu.com/ubuntu jammy InRelease
Ign:2 http://packages.linuxmint.com victoria InRelease                     	 
Des:3 http://archive.ubuntu.com/ubuntu jammy-updates InRelease [119 kB]    	 
Des:4 http://security.ubuntu.com/ubuntu jammy-security InRelease [110 kB]    	 
Des:5 http://packages.linuxmint.com victoria Release [24,2 kB]               	 
Des:6 http://archive.ubuntu.com/ubuntu jammy-backports InRelease [109 kB]    	 
Des:7 http://archive.ubuntu.com/ubuntu jammy-updates/main i386 Packages [515 kB]  
Des:8 http://packages.linuxmint.com victoria Release.gpg [833 B]             	 
Des:9 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 Packages [1.103 kB]
Des:10 http://archive.ubuntu.com/ubuntu jammy-updates/main Translation-en [239 kB]
Des:11 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 DEP-11 Metadata [101 kB]
```
- Instalamos Java con este comando:

```
  sudo apt-get install default-jdk
```
- Salida. 
```
nereaglez@nereaglez-VirtualBox:~$  sudo apt-get install default-jdk
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias... Hecho
Leyendo la información de estado... Hecho
Se instalarán los siguientes paquetes adicionales:
  default-jdk-headless libice-dev libpthread-stubs0-dev libsm-dev libx11-6
  libx11-dev libx11-xcb1 libxau-dev libxcb1-dev libxdmcp-dev libxt-dev
  openjdk-11-jdk openjdk-11-jdk-headless openjdk-11-jre openjdk-11-jre-headless
  x11proto-dev xorg-sgml-doctools xtrans-dev
Paquetes sugeridos:
  libice-doc libsm-doc libx11-doc libxcb-doc libxt-doc openjdk-11-demo
  openjdk-11-source visualvm fonts-dejavu-extra fonts-ipafont-gothic
  fonts-ipafont-mincho fonts-wqy-microhei | fonts-wqy-zenhei
```
- Comprobamos que tenemos instalado Java en nuestro sistema solo debemos de ejecutar:

```
  java --version
```

- Salida.

```
nereaglez@nereaglez-VirtualBox:~$ java--version
java--version: orden no encontrada
```
## ¿Como instalar una version especifica de Java?

- Para instalar Ubuntu Java Open JDK
```
OpenJDK:

    11

sudo apt install openjdk-11-jdk

    13

sudo apt install openjdk-13-jdk

    8

sudo apt install openjdk-8-jdk

```
- Salida.
```
nereaglez@nereaglez-VirtualBox:~$ sudo apt install openjdk-8-jdk
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias... Hecho
Leyendo la información de estado... Hecho
Se instalarán los siguientes paquetes adicionales:
  fonts-dejavu-extra libatk-wrapper-java libatk-wrapper-java-jni
  openjdk-8-jdk-headless openjdk-8-jre openjdk-8-jre-headless
Paquetes sugeridos:
  openjdk-8-demo openjdk-8-source visualvm fonts-nanum fonts-ipafont-gothic
  fonts-ipafont-mincho fonts-wqy-microhei fonts-wqy-zenhei
```

- La versión que se debe de trabajar es la versión 8.Para ello verificaremos la versión de java 
que se esta ejecutando con la sentencia:
```
  java --version
```
- Salida. 
```
nereaglez@nereaglez-VirtualBox:~$ java --version
openjdk 11.0.20.1 2023-08-24
OpenJDK Runtime Environment (build 11.0.20.1+1-post-Ubuntu-0ubuntu122.04)
OpenJDK 64-Bit Server VM (build 11.0.20.1+1-post-Ubuntu-0ubuntu122.04, mixed mode, sharing)
``` 

## Configuracion de las variables del entorno.

- Ejecuta el siguiente comando para verificar que se han descargado las diferentes versiones de OpenJDK.
```
 ls /usr/lib/jvm
 
```
- Salida.
```
nereaglez@nereaglez-VirtualBox:~$  ls /usr/lib/jvm
default-java           	java-11-openjdk-amd64 	java-8-openjdk-amd64
java-1.11.0-openjdk-amd64  java-1.8.0-openjdk-amd64  openjdk-11
nereaglez@nereaglez-VirtualBox:~$ sudo update-alternatives --config java
Existen 2 opciones para la alternativa java (que provee /usr/bin/java).

Selección   Ruta                                        	Prioridad  Estado
------------------------------------------------------------
* 0        	/usr/lib/jvm/java-11-openjdk-amd64/bin/java  	1111  	modo automático
  1        	/usr/lib/jvm/java-11-openjdk-amd64/bin/java  	1111  	modo manual
  2        	/usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java   1081  	modo manual

Pulse <Intro> para mantener el valor por omisión [*] o pulse un número de selección: 2
update-alternatives: utilizando /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java para proveer /usr/bin/java 
(java) en modo manual
```
- Edita y modifica el fichero profile, con los comandos:
```
sudo update-alternatives --config java
```
- Salida. 
```
nereaglez@nereaglez-VirtualBox:~$ sudo update-alternatives --config java
Existen 2 opciones para la alternativa java (que provee /usr/bin/java).

  Selección   Ruta                                        	Prioridad  Estado
------------------------------------------------------------
  0        	/usr/lib/jvm/java-11-openjdk-amd64/bin/java  	1111  	modo automático
  1        	/usr/lib/jvm/java-11-openjdk-amd64/bin/java  	1111  	modo manual
* 2        	/usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java   1081  	modo manual
```
- Añadir el siguiente código:
```
# Java version
JAVA_HOME=/usr/lib/jvm/(SELECCIONA UN PATH DE LA VERSION QUE DESEAS QUE SE EJECUTE)
PATH=$PATH:$HOME/bin:$JAVA_HOME/bin
export JAVA_HOME
export JRE_HOME
export PATH
```

- Salida.
```
java-1.11.0-openjdk-amd64  java-1.8.0-openjdk-amd64  openjdk-11
nereaglez@nereaglez-VirtualBox:~$ JAVA_HOMO=/java/1.8.0-openjdk/amd64
nereaglez@nereaglez-VirtualBox:~$ JAVA_HOME=java-1.8.0-openjdk-amd64
nereaglez@nereaglez-VirtualBox:~$ PATH=$PATH:$HOME/bin:$JAVA_HOME/bin
nereaglez@nereaglez-VirtualBox:~$ export JAVA_HOME
nereaglez@nereaglez-VirtualBox:~$ export JRE_HOME
nereaglez@nereaglez-VirtualBox:~$ export PATH
nereaglez@nereaglez-VirtualBox:~$ JAVA_HOME=java/1.8.0-openjdk/amd64
nereaglez@nereaglez-VirtualBox:~$ export PATH

```
- Haga que el script sea ejecutable con chmod:
```
sudo chmod +x /etc/profile.d/java.sh
```
- Salida.
```
nereaglez@nereaglez-VirtualBox:~$ sudo chmod +x /etc/profile.d/java.sh
```

-Finalmente, cargue las variables de entorno usando el comando de source

```
source /etc/profile.d/java.sh

```

- Salida. 
```
nereaglez@nereaglez-VirtualBox:~$ source /etc/profile.d/java.sh
```


