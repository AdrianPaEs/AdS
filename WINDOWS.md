# WINDOWS

---

## 1. Instalación Linux
### 1.1 Conceptos Básicos y Distribuciones

Linux se presenta como una variante del sistema UNIX distribuido bajo licencia GPL (General Public License).

Características principales: Es un sistema multiusuario, multiproceso, multiplataforma y destaca por su estabilidad (no requiere reinicios frecuentes).

Arquitectura: Se estructura en capas que van desde el Hardware, pasando por el Kernel, Shell y Bibliotecas, hasta las Aplicaciones.

Distribuciones: Existen diversas "familias" de distribuciones como Debian/Ubuntu, Red Hat/Fedora, Arch Linux, Slackware y Android.

### 1.2 Estructura de Directorios y Dispositivos

![alt text](images/image1.png)

El sistema de archivos nace de la raíz / en forma de árbol.

Dispositivos (/dev): Los dispositivos de hardware se representan como ficheros.

Disco duro SATA: /dev/sda.

CD-ROM: /dev/cdrom.

Ficheros especiales: /dev/null (descarta salidas) y /dev/zero.

### 1.3 Esquema de Particionamiento Recomendado

| Partición  | Descripcion |
| ------------- |:-------------:|
| /      | Debe contener solo lo necesario y ser simple para evitar corrupción     |
| /boot      | Partición pequeña con los kernels y ficheros de arranque     |
| /var      | Almacena logs, correos y colas de impresión. Se separa para evitar que, si se llena, desestabilice el sistema.     |
| /tmp      | Para archivos temporales; se evita copiarlo en copias de seguridad     |
| /usr      | Contiene comandos y librerías; puede configurarse como "solo lectura"     |
| /home      | Directorios de usuarios. Separarlo permite reinstalar o actualizar el sistema operativo sin perder los datos personales     |
| swap      | Memoria de intercambio. La regla sugerida es asignar el doble de la memoria RAM.     |

### 1.4 Montaje de Sistemas de Ficheros

El proceso de "montaje" asocia una partición física (ej. /dev/sdb1) a un directorio del sistema (ej. /home).

* Manual: Se realiza mediante el comando mount.

* Automático: Se configura en el fichero /etc/fstab, donde se definen el dispositivo, el punto de montaje, el tipo de sistema de archivos (ej. ext3, ext4, swap) y las opciones de arranque.

### 1.5 Arranque del Sistema (Boot)

El gestor de arranque utilizado es GRUB2, el cual es flexible y permite cargar distintos sistemas operativos.

Proceso: BIOS/UEFI -> MBR (Etapa 1) -> Gestor de arranque (Etapa 2/Menú) -> Carga del Kernel.

UEFI: Reemplaza a la BIOS en sistemas modernos ofreciendo mayor flexibilidad.

6. Comandos y Ejercicios Prácticos
El documento finaliza con ejemplos prácticos de administración de discos:

Comandos de diagnóstico:
```bash
df -h // Muestra el espacio usado y disponible en los sistemas de ficheros montados.
lsblk // Lista los dispositivos de bloque y sus puntos de montaje en estructura de árbol.
```

---
## 2. Desarrollo por Apartados

### 2.1 Apartado A: 


### 2.2 Apartado B: Comparativa

---

## 3. Notas Técnicas y Fórmulas


---

## 4. Resumen y Puntos Clave

---

