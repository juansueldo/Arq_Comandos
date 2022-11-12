# Arq_Comandos

*****COMANDOS INFORMACION DEL SISTEMA*****
*******************************************

- ***arch***                 arquitectura del ordenador
- ***uname -r***             version del kernel
- ***unane -a***             sistema operativo, usuario, kernel
- ***cat /proc/cpuinfo***    informacion sobre la CPU
- ***cat /proc/meminfo***    verifica uso de la memoria RAM
- ***free -m***              muestra el estado y uso de la RAM
- ***cat /proc/net/dev***    adaptadores de red
- ***cat /proc/mounts***     sistema de archivos montado


******COMANDOS NAVEGACION DEL SISTEMA******
*******************************************

- ***cd /home/usuario***      lleva hasta la ruta indicada, ejemplo usuario
- ***cd..***                  retrocede un nivel de jerarquia de directorios
- ***cd../..***               retrocede dos niveles
- ***cd***                    lleva al directorio raiz
- ***cd ~usuario***           lleva al directorio principal del usuario indicado
- ***cd -***                  lleva al direcotrio anterior
- ***pwd***                   mostrara la ruta del directorio actual
- ***ls***                    muestra los archivos y carpetas
- ***ls -l***                 muestra el detalle de los archivos y carpetas
- ***ls -a***                 muestra los archivos ocultos


**********CREACION DE DIRECTORIOS**********
*******************************************
- ***mkdir -p Ejercicio_D/{uba,utnfra}/clase{1..5}***     crea el directorio

![This is an image](https://i.postimg.cc/L4C5P7VW/subir1.png)
- ***tree Ejercicio_D/***                                 ver el directorio   
- ***rm -r  Ejercicio_D/***                               borrar de forma recursiva

- ***mkdir -p Ejercicio_E/{utnba/clases{1..5},utnfra/{clases{1..9},examen}}***

![This is an image](https://i.postimg.cc/SRBprWRn/subir2.png)
- ***tree Ejercicio_E/***                                   
- ***rm -r  Ejercicio_E/***

-***mkdir -p {Desarrollo/{fuentes,final}/backup,Testing/{fuentes,imagenes,final}/backup}***


**********CREACION DE ARCHIVOS**********
*******************************************
- ***cat /proc/cpuinfo > home/1erexamen/CPU.txt***
- ***echo -n "Marca=" > cpu.txt && cat /proc/cpuinfo | grep vendor | uniq | cut -d ":" -f2 >> cpu.txt && echo -n "Modelo de CPU=" >> cpu.txt && cat /proc/cpuinfo | grep model | grep name | uniq | cut -d ":" -f2 >> cpu.txt && echo -n "Frecuencia=" >> cpu.txt && cat /proc/cpuinfo | grep MHz | uniq | cut -d ":" -f2 >> cpu.txt && echo -n "Procesadores=" >> cpu.txt  &&  cat /proc/cpuinfo | grep cores | uniq | cut -d ":" -f2 >> cpu.txt***


**********CREACION DE PARTICIONES**********
*******************************************

- ***sudo fdisk -l***  Lista todos los discos
- ***sudo fdisk /dev/disco***
- ***n***
- ***sudo mkfs.ext4 /dev/disco***
- ***sudo mount /dev/disco /home/mount***
- ***lsblk***


**********CREACION DE USUARIOS**********
*******************************************
- ***useradd -m -s /bin/bash -c "Usuario tecnico" tecnico***
- ***grep tecnico /etc/passwd***
- ***grep tecnico /etc/group***
- ***grep tecnico /etc/shadow***

************LVM************
*******************************************
- ***lsblk*** para ver los discos
- ***fdisk /dev/sdb*** disco a particionar
luego de hacer las particiones cambiamos de tipo de particion con la letra t, se elige el sector y el formato 8e
- ***pvcreate /dev/sdb1*** creacion de physical volume
- ***pvs*** para comprobar la creacion
- ***vgcreate vg_Nombre /dev/sdb1*** creacion del voulume group
- ***vgs*** comprobar la creacion
- ***lvcreate -L +512M vg_Nombre -n LV_Nombre*** creacion del logical volume
- ***pvs; vgs; lvs*** para comprobar
- ***mkfs -t ext4 /dev/mapper/vg_Nombre-LV_Nombre*** dar formato
- ***mount /dev/mapper/vg_NombreLVM-LV_Nombre /Directorio*** montamos en el directorio indicado
- ***df -h*** para comprobar si se monto de manera correcta
- ***vgextend vg_Nombre /dev/sdb2*** extender volume group






