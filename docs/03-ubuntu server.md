# Ubuntu Sever LTS

Proxmox Virtual Environment (Proxmox VE) es una plataforma de virtualización de servidores de código abierto
que permite administrar máquinas virtuales y contenedores desde una única interfaz web

## Objetivos
- Habilitar la virtualización anidada en Hyper-V
- Configurar hostname y dominio
- Instalar el repositorio y el kernel de Proxmox VE
- Acceder a la interfaz web de Proxmox

## Paso 1: Creacion maquina virtual
Repetimos el proceso para la creacion de la maquina virtual que hicimos con pfsanse usando el ISO de ubuntu server LTS, ese ISO lo descargamos en:
````
http://ubuntu.com/download/server
````

Debe tener estas especificaciones:
1-CARACTERISTICAS UBUNTU 
![UBUNTU ](img/1-CARACTERISTICAS_UBUNTU.png)

## Paso 2: Configuracion Ubuntu
Al correr la maquina recien creada nos apareceran los tipicos inicia al arrancar linux.
-idioma
-teclado
un punto importante es que nos mostrara el tipo de instalacion:
![UBUNTU ](img/2-TIPO_INSTALACION.png)
