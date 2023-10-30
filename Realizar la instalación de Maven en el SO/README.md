## Instalación de MAVEN en el Ubuntu
_Nerae Glez._

- __Indice__
1. [Instalar Apache Maven](#instlar-apache-maven-)
2. [Instalar una version concreta de Apache Maven](#instalar-una-version-concreta-de-apache-maven)


## Instlar Apache Maven 
- Instalar Maven en Ubuntu usando apt es un proceso simple y directo.

Actualice el índice del paquete e instale Maven ingresando los siguientes comandos:

``` 
   sudo apt update
   sudo apt install maven

```
- Salida.

```
nereaglez@nereaglez-VirtualBox:~$ sudo apt update
[sudo] contraseña para nereaglez:         	 
Obj:1 http://archive.ubuntu.com/ubuntu jammy InRelease                    	 
Des:2 http://archive.ubuntu.com/ubuntu jammy-updates InRelease [119 kB]   	 
Ign:3 http://packages.linuxmint.com victoria InRelease                    	 
Des:4 http://archive.ubuntu.com/ubuntu jammy-backports InRelease [109 kB] 	 
Obj:5 http://packages.linuxmint.com victoria Release                      	 
Des:6 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 Packages [1.107 kB]
Des:7 http://archive.ubuntu.com/ubuntu jammy-updates/main i386 Packages [516 kB]
Des:9 http://archive.ubuntu.com/ubuntu jammy-updates/main Translation-en [240 kB]
Des:10 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 DEP-11 Metadata [101 kB]
Des:11 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 c-n-f Metadata [16,1 kB]
Des:12 http://archive.ubuntu.com/ubuntu jammy-updates/restricted amd64 Packages [1.037 kB]
Des:13 http://archive.ubuntu.com/ubuntu jammy-updates/restricted Translation-en [168 kB]
Des:14 http://archive.ubuntu.com/ubuntu jammy-updates/universe i386 Packages [660 kB]
Des:15 http://archive.ubuntu.com/ubuntu jammy-updates/universe amd64 Packages [995 kB]
Des:16 http://archive.ubuntu.com/ubuntu jammy-updates/universe amd64 DEP-11 Metadata [305 kB]
Des:17 http://archive.ubuntu.com/ubuntu jammy-updates/universe amd64 c-n-f Metadata [22,0 kB]

nereaglez@nereaglez-VirtualBox:~$ sudo apt install maven
Leyendo lista de paquetes... Hecho
Creando árbol de dependencias... Hecho
Leyendo la información de estado... Hecho
maven ya está en su versión más reciente (3.6.3-5).
0 actualizados, 0 nuevos se instalarán, 0 para eliminar y 227 no actualizados.
nereaglez@nereaglez-VirtualBox:~$ mvn -version
Apache Maven 3.6.3
Maven home: /usr/share/maven
Java version: 1.8.0_382, vendor: Private Build, runtime: /usr/lib/jvm/java-8-openjdk-amd64/jre
Default locale: es_ES, platform encoding: UTF-8
OS name: "linux", version: "5.15.0-76-generic", arch: "amd64", family: "unix"
nereaglez@nereaglez-VirtualBox:~$ wget https://www.apache.org/dist/maven/maven-3/3.8.8/binaries/apache
-maven-3.8.8-bin.tar.gz -P /tmp

```
- Para verificar la instalación, ejecute mvn -version:

```
  mvn -version
```
- Salida.
```
nereaglez@nereaglez-VirtualBox:~$ mvn -version
Apache Maven 3.6.3
Maven home: /usr/share/maven
Java version: 1.8.0_382, vendor: Private Build, runtime: /usr/lib/jvm/java-8-openjdk-amd64/jre
Default locale: es_ES, platform encoding: UTF-8
OS name: "linux", version: "5.15.0-76-generic", arch: "amd64", family: "unix"

```

## Instalar una version concreta de Apache Maven
- Descargue Apache Maven en el directorio /tmp:

```
 wget https://www.apache.org/dist/maven/maven-3/3.8.8/binaries/apache-maven-3.8.8-bin.tar.gz -P /tmp
```

- Salida.

```
nereaglez@nereaglez-VirtualBox:~$ wget https://www.apache.org/dist/maven/maven-3/3.8.8/binaries/apache
-maven-3.8.8-bin.tar.gz -P /tmp
--2023-10-30 09:17:02--  https://www.apache.org/dist/maven/maven-3/3.8.8/binaries/apache-maven-3.8.8-bin.tar.gz
Resolviendo www.apache.org (www.apache.org)... 151.101.2.132, 2a04:4e42::644
Conectando con www.apache.org (www.apache.org)[151.101.2.132]:443... conectado.
Petición HTTP enviada, esperando respuesta... 302 Found
Ubicación: https://downloads.apache.org/maven/maven-3/3.8.8/binaries/apache-maven-3.8.8-bin.tar.gz [siguiente]
--2023-10-30 09:17:03--  https://downloads.apache.org/maven/maven-3/3.8.8/binaries/apache-maven-3.8.8-bin.tar.gz
Resolviendo downloads.apache.org (downloads.apache.org)... 135.181.214.104, 88.99.95.219, 2a01:4f8:10a:201a::2, ...
Conectando con downloads.apache.org (downloads.apache.org)[135.181.214.104]:443... conectado.
Petición HTTP enviada, esperando respuesta... 200 OK
Longitud: 8296049 (7,9M) [application/x-gzip]
Guardando como: ‘/tmp/apache-maven-3.8.8-bin.tar.gz’

apache-maven-3.8.8- 100%[===================>]   7,91M  1,20MB/s	en 6,8s 
```

- Una vez que se complete la descarga, extraiga el archivo en el directorio /opt
```
sudo tar xf /tmp/apache-maven-*.tar.gz -C /opt

```
- Salida.
```
nereaglez@nereaglez-VirtualBox:~$ sudo tar xf /tmp/apache-maven-*.tar.gz -C /opt

```

- Para tener más control sobre las versiones y actualizaciones de Maven, que a crear un maven enlace simbólico
que apunte al directorio de instalación de Maven:
```
 sudo ln -s /opt/apache-maven-3.8.8 /opt/maven
```
- Salida.
```
nereaglez@nereaglez-VirtualBox:~$ sudo ln -s /opt/apache-maven-3.8.8 /opt/maven

```
- Establecer variables de entorno
```
sudo nano /etc/profile.d/maven.sh
 
```
- Salida.
```
nereaglez@nereaglez-VirtualBox:~$ sudo nano /etc/profile.d/maven.sh
```
- Haga que el script sea ejecutable con chmod:
```
 sudo chmod +x /etc/profile.d/maven.sh
```

- Salida.
```
nereaglez@nereaglez-VirtualBox:~$ sudo nano /etc/profile.d/maven.sh
```
- Finalmente, cargue las variables de entorno usando el comando de source
```
 source /etc/profile.d/maven.sh
```
- Salida.
```
nereaglez@nereaglez-VirtualBox:~$  sudo chmod +x /etc/profile.d/maven.sh

```

- Verificar la instalación. 

```
mvn -version

```
- Debería ver algo similar a lo siguiente:
```
Apache Maven 3.8.6 (cecedd343002696d0abb50b32b541b8a6ba2883f)
 Maven home: /opt/maven
 Java version: 11.0.7, vendor: Ubuntu, runtime: /usr/lib/jvm/java-11-openjdk-amd64
 Default locale: en_US, platform encoding: UTF-8
 OS name: "linux", version: "5.4.0-29-generic", arch: "amd64", family: "unix"
 ```
- Salida.
```
nereaglez@nereaglez-VirtualBox:~$ mvn -version
Apache Maven 3.8.8 (4c87b05d9aedce574290d1acc98575ed5eb6cd39)
Maven home: /opt/maven
Java version: 1.8.0_382, vendor: Private Build, runtime: /usr/lib/jvm/java-8-openjdk-amd64/jre
Default locale: es_ES, platform encoding: UTF-8
OS name: "linux", version: "5.15.0-76-generic", arch: "amd64", family: "unix"

```

