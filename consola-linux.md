# Comandos de consola Linux


### Información del sistema

`arch`: mostrar la arquitectura de la máquina (1).<br>
`uname -m`: mostrar la arquitectura de la máquina (2).<br>
`uname -r`: mostrar la versión del kernel usado.<br>
`dmidecode -q`: mostrar los componentes (hardware) del sistema.<br>
`hdparm -i /dev/hda`: mostrar las características de un disco duro.<br>
`hdparm -tT /dev/sda`: realizar prueba de lectura en un disco duro.<br>
`cat /proc/cpuinfo`: mostrar información de la CPU.<br>
`cat /proc/interrupts`: mostrar las interrupciones.<br>
`cat /proc/meminfo`: verificar el uso de memoria.<br>
`cat /proc/swaps`: mostrar ficheros swap.<br>
`cat /proc/version`: mostrar la versión del kernel.<br>
`cat /proc/net/dev`: mostrar adaptadores de red y estadísticas.<br>
`cat /proc/mounts`: mostrar el sistema de ficheros montado.<br>
`lspci -tv`: mostrar los dispositivos PCI.<br>
`lsusb -tv`: mostrar los dispositivos USB.<br>
`date`: mostrar la fecha del sistema.<br>
`cal 2011`: mostrar el almanaque de 2011.<br>
`cal 07 2011`: mostrar el almanaque para el mes julio de 2011.<br>
`date 041217002011.00`: colocar (declarar, ajustar) fecha y hora.<br>
`clock -w`: guardar los cambios de fecha en la BIOS.<br>


### Apagar (Reiniciar Sistema o Cerrar Sesión)

`shutdown -h now`: apagar el sistema (1).<br>
`init 0`: apagar el sistema (2).<br>
`telinit 0`: apagar el sistema (3).<br>
`halt`: apagar el sistema (4).<br>
`shutdown -h hours:minutes &`: apagado planificado del sistema.<br>
`shutdown -c`: cancelar un apagado planificado del sistema.<br>
`shutdown -r now`: reiniciar (1).<br>
`reboot`: reiniciar (2).<br>
`logout`: cerrar sesión.<br>


### Archivos y Directorios

`cd /home`: entrar en el directorio “home”.<br>
`cd ..`: retroceder un nivel.<br>
`cd ../..`: retroceder 2 niveles.<br>
`cd`: ir al directorio raíz.<br>
`cd ~user1`: ir al directorio user1.<br>
`cd –`: ir (regresar) al directorio anterior.<br>
`pwd`: mostrar el camino del directorio de trabajo.<br>
`ls`: ver los ficheros de un directorio.<br>
`ls -F`: ver los ficheros de un directorio.<br>
 `ls -l`: mostrar los detalles de ficheros y carpetas de un directorio.<br>
 `ls -a`: mostrar los ficheros ocultos.<br>
 `ls *[0-9]*`: mostrar los ficheros y carpetas que contienen números.<br>
 `tree`: mostrar los ficheros y carpetas en forma de árbol comenzando por la raíz.(1)<br>
 `lstree`: mostrar los ficheros y carpetas en forma de árbol comenzando por la raíz.(2)<br>
 `mkdir dir1`: crear una carpeta o directorio con nombre ‘dir1’.<br>
 `mkdir dir1 dir2`: crear dos carpetas o directorios simultáneamente (Crear dos directorios a la vez).<br>
 `mkdir -p /tmp/dir1/dir2`: crear un árbol de directorios.<br>
 `rm -f file1`: borrar el fichero llamado ‘file1’.<br>
 `rmdir dir1`: borrar la carpeta llamada ‘dir1’.<br>
 `rm -rf dir1`: eliminar una carpeta llamada ‘dir1’ con su contenido de forma recursiva. (Si lo borro recursivo estoy diciendo que es con su contenido).<br>
 `rm -rf dir1 dir2`: borrar dos carpetas (directorios) con su contenido de forma recursiva.<br>
 `mv dir1 new_dir`: renombrar o mover un fichero o carpeta (directorio).<br>
 `cp file1`: copiar un fichero.<br>
 `cp file1 file2`: copiar dos ficheros al unísono.<br>
 `cp dir /* .`: copiar todos los ficheros de un directorio dentro del directorio de trabajo actual.<br>
 `cp -a /tmp/dir1 .`: copiar un directorio dentro del directorio actual de trabajo.<br>
 `cp -a dir1`: copiar un directorio.<br>
 `cp -a dir1 dir2`: copiar dos directorio al unísono.<br>
 `ln -s file1 lnk1`: crear un enlace simbólico al fichero o directorio.<br>
 `ln file1 lnk1`: crear un enlace físico al fichero o directorio.<br>
 `touch -t 0712250000 file1`: modificar el tiempo real (tiempo de creación) de un fichero o directorio.<br>
 `file file1`: salida (volcado en pantalla) del tipo mime de un fichero texto.<br>
 `iconv -l`: listas de cifrados conocidos.<br>
 `iconv -f fromEncoding -t toEncoding inputFile > outputFile`: crea una nueva forma del fichero de entrada asumiendo que está codificado en fromEncoding y convirtiéndolo a ToEncoding.<br>
 `find . -maxdepth 1 -name *.jpg -print -exec convert ”{}” -resize 80×60 “thumbs/{}” \;`: agrupar ficheros redimensionados en el directorio actual y enviarlos a directorios en vistas de miniaturas (requiere convertir desde ImagemagicK).<br>


### Encontrar archivos

`find / -name file1`: buscar fichero y directorio a partir de la raíz del sistema.<br>
`find / -user user1`: buscar ficheros y directorios pertenecientes al usuario ‘user1’.<br>
`find /home/user1 -name \`*.bin: buscar ficheros con extensión ‘. bin’ dentro del directorio ‘/ home/user1’.<br>
`find /usr/bin -type f -atime +100`: buscar ficheros binarios no usados en los últimos 100 días.<br>
`find /usr/bin -type f -mtime -10`: buscar ficheros creados o cambiados dentro de los últimos 10 días.<br>
`find / -name \*.rpm -exec chmod 755 ‘{}’ \;`: buscar ficheros con extensión ‘.rpm’ y modificar permisos.<br>
`find / -xdev -name \*.rpm`: Buscar ficheros con extensión ‘.rpm’ ignorando los dispositivos removibles como cdrom, pen-drive, etc.…<br>
`locate \*.ps`: encuentra ficheros con extensión ‘.ps’ ejecutados primeramente con el command ‘updatedb’.<br>
`whereis halt`: mostrar la ubicación de un fichero binario, de ayuda o fuente. En este caso pregunta dónde está el comando ‘halt’.<br>
`which halt`: mostrar la senda completa (el camino completo) a un binario / ejecutable. Montando un sistema de ficheros<br>
`mount /dev/hda2 /mnt/hda2`: montar un disco llamado hda2. Verifique primero la existencia del directorio ‘/ mnt/hda2’; si no está, debe crearlo.<br>
`umount /dev/hda2`: desmontar un disco llamado hda2. Salir primero desde el punto ‘/ mnt/hda2.<br>
`fuser -km /mnt/hda2`: forzar el desmontaje cuando el dispositivo está ocupado.<br>
`umount -n /mnt/hda2`: correr el desmontaje sin leer el fichero /etc/mtab. Útil cuando el fichero es de solo lectura o el disco duro está lleno.<br>
`mount /dev/fd0 /mnt/floppy`: montar un disco flexible (floppy).<br>
`mount /dev/cdrom /mnt/cdrom`: montar un cdrom / dvdrom.<br>
`mount /dev/hdc /mnt/cdrecorder`: montar un cd regrabable o un dvdrom.<br>
`mount /dev/hdb /mnt/cdrecorder`: montar un cd regrabable / dvdrom (un dvd).<br>
`mount -o loop file.iso /mnt/cdrom`: montar un fichero o una imagen iso.<br>
`mount -t vfat /dev/hda5 /mnt/hda5`: montar un sistema de ficheros FAT32.<br>
`mount /dev/sda1 /mnt/usbdisk`: montar un usb pen-drive o una memoria (sin especificar el tipo de sistema de ficheros).<br>


### Espacio de Disco

`df -h`: mostrar una lista de las particiones montadas.<br>
`ls -lSr |more`: mostrar el tamaño de los ficheros y directorios ordenados por tamaño.<br>
`du -sh dir1`: Estimar el espacio usado por el directorio ‘dir1’.<br>
`du -sk * | sort -rn`: mostrar el tamaño de los ficheros y directorios ordenados por tamaño.<br>
`rpm -q -a –qf ‘%10{SIZE}t%{NAME}n’ | sort -k1,1n`: mostrar el espacio usado por los paquetes rpm instalados organizados por tamaño (Fedora, Redhat y otros).<br>
`dpkg-query -W -f=’${Installed-Size;10}t${Package}n’ | sort -k1,1n`: mostrar el espacio usado por los paquetes instalados, organizados por tamaño (Ubuntu, Debian y otros).<br>


### Usuarios y Grupos

`groupadd nombre_del_grupo`: crear un nuevo grupo.<br>
`groupdel nombre_del_grupo`: borrar un grupo.<br>
`groupmod -n nuevo_nombre_del_grupo viejo_nombre_del_grupo`: renombrar un grupo.<br>
`useradd -c “Name Surname ” -g admin -d /home/user1 -s /bin/bash user1`: Crear un nuevo usuario perteneciente al grupo “admin”.<br>
`useradd user1`: crear un nuevo usuario.<br>
`userdel -r user1`: borrar un usuario (‘-r’ elimina el directorio Home).<br>
`usermod -c “User FTP” -g system -d /ftp/user1 -s /bin/nologin user1`: cambiar los atributos del usuario.<br>
`passwd`: cambiar contraseña.<br>
`passwd user1`: cambiar la contraseña de un usuario (solamente por root).<br>
`chage -E 2011-12-31 user1`: colocar un plazo para la contraseña del usuario. En este caso dice que la clave expira el 31 de diciembre de 2011.<br>
`pwck`: chequear la sintaxis correcta el formato de fichero de ‘/etc/passwd’ y la existencia de usuarios.<br>
`grpck`: chequear la sintaxis correcta y el formato del fichero ‘/etc/group’ y la existencia de grupos.<br>
`newgrp group_name`: registra a un nuevo grupo para cambiar el grupo predeterminado de los ficheros creados recientemente.<br>


### Permisos en Ficheros (Usa ”+” para colocar permisos y ”-” para eliminar)

`ls -lh`: Mostrar permisos.<br>
`ls /tmp | pr -T5 -W$COLUMNS`: dividir la terminal en 5 columnas.<br>
`chmod ugo+rwx directory1`: colocar permisos de lectura ®, escritura (w) y ejecución(x) al propietario (u), al grupo (g) y a otros (o) sobre el directorio ‘directory1’.<br>
`chmod go-rwx directory1`: quitar permiso de lectura ®, escritura (w) y (x) ejecución al grupo (g) y otros (o) sobre el directorio ‘directory1’.<br>
`chown user1 file1`: cambiar el dueño de un fichero.<br>
`chown -R user1 directory1`: cambiar el propietario de un directorio y de todos los ficheros y directorios contenidos dentro.<br>
`chgrp group1 file1`: cambiar grupo de ficheros.<br>
`chown user1`:group1 file1: cambiar usuario y el grupo propietario de un fichero.<br>
`find / -perm -u+s`: visualizar todos los ficheros del sistema con SUID configurado.<br>
`chmod u+s /bin/file1`: colocar el bit SUID en un fichero binario. El usuario que corriendo ese fichero adquiere los mismos privilegios como dueño.<br>
`chmod u-s /bin/file1`: deshabilitar el bit SUID en un fichero binario.<br>
`chmod g+s /home/public`: colocar un bit SGID en un directorio –similar al SUID pero por directorio.<br>
`chmod g-s /home/public`: desabilitar un bit SGID en un directorio.<br>
`chmod o+t /home/public`: colocar un bit STIKY en un directorio. Permite el borrado de ficheros solamente a los dueños legítimos.<br>
`chmod o-t /home/public`: desabilitar un bit STIKY en un directorio.<br>


### Atributos especiales en ficheros (Usa ”+” para colocar permisos y ”-” para eliminar)

`chattr +a file1`: permite escribir abriendo un fichero solamente modo append.<br>
`chattr +c file1`: permite que un fichero sea comprimido / descomprimido automaticamente.<br>
`chattr +d file1`: asegura que el programa ignore borrar los ficheros durante la copia de seguridad.<br>
`chattr +i file1`: convierte el fichero en invariable, por lo que no puede ser eliminado, alterado, renombrado, ni enlazado.<br>
`chattr +s file1`: permite que un fichero sea borrado de forma segura.<br>
`chattr +S file1`: asegura que un fichero sea modificado, los cambios son escritos en modo synchronous como con sync.<br>
`chattr +u file1`: te permite recuperar el contenido de un fichero aún si este está cancelado.<br>
`lsattr`: mostrar atributos especiales.<br>


### Archivos y Ficheros comprimidos

`bunzip2 file1.bz2`: descomprime in fichero llamado ‘file1.bz2’.<br>
`bzip2 file1`: comprime un fichero llamado ‘file1’.<br>
`gunzip file1.gz`: descomprime un fichero llamado ‘file1.gz’.<br>
`gzip file1`: comprime un fichero llamado ‘file1’.<br>
`gzip -9 file1`: comprime con compresión máxima.<br>
`rar a file1.rar test_file`: crear un fichero rar llamado ‘file1.rar’.<br>
`rar a file1.rar file1 file2 dir1`: comprimir ‘file1’, ‘file2’ y ‘dir1’ simultáneamente.<br>
`rar x file1.rar`: descomprimir archivo rar.<br>
`unrar x file1.rar`: descomprimir archivo rar.<br>
`tar -cvf archive.tar file1`: crear un tarball descomprimido.<br>
`tar -cvf archive.tar file1 file2 dir1`: crear un archivo conteniendo ‘file1’, ‘file2′ y’dir1’.<br>
`tar -tf archive.tar`: mostrar los contenidos de un archivo.<br>
`tar -xvf archive.tar`: extraer un tarball.<br>
`tar -xvf archive.tar -C /tmp`: extraer un tarball en / tmp.<br>
`tar -cvfj archive.tar.bz2 dir1`: crear un tarball comprimido dentro de bzip2.<br>
`tar -xvfj archive.tar.bz2`: descomprimir un archivo tar comprimido en bzip2<br>
`tar -cvfz archive.tar.gz dir1`: crear un tarball comprimido en gzip.<br>
`tar -xvfz archive.tar.gz`: descomprimir un archive tar comprimido en gzip.<br>
`zip file1.zip file1`: crear un archivo comprimido en zip.<br>
`zip -r file1.zip file1 file2 dir1`: comprimir, en zip, varios archivos y directorios de forma simultánea.<br>
`unzip file1.zip`: descomprimir un archivo zip.<br>


### Paquetes RPM (Red Hat, Fedora y similares)

`rpm -ivh package.rpm`: instalar un paquete rpm.<br>
`rpm -ivh –nodeeps package.rpm`: instalar un paquete rpm ignorando las peticiones de dependencias.<br>
`rpm -U package.rpm`: actualizar un paquete rpm sin cambiar la configuración de los ficheros.<br>
`rpm -F package.rpm`: actualizar un paquete rpm solamente si este está instalado.<br>
`rpm -e package_name.rpm`: eliminar un paquete rpm.<br>
`rpm -qa`: mostrar todos los paquetes rpm instalados en el sistema.<br>
`rpm -qa | grep httpd`: mostrar todos los paquetes rpm con el nombre “httpd”.<br>
`rpm -qi package_name`: obtener información en un paquete específico instalado.<br>
`rpm -qg “System Environment/Daemons”`: mostar los paquetes rpm de un grupo software.<br>
`rpm -ql package_name`: mostrar lista de ficheros dados por un paquete rpm instalado.<br>
`rpm -qc package_name`: mostrar lista de configuración de ficheros dados por un paquete rpm instalado.<br>
`rpm -q package_name –whatrequires`: mostrar lista de dependencias solicitada para un paquete rpm.<br>
`rpm -q package_name –whatprovides`: mostar la capacidad dada por un paquete rpm.<br>
`rpm -q package_name –scripts`: mostrar los scripts comenzados durante la instalación /eliminación.<br>
`rpm -q package_name –changelog`: mostar el historial de revisions de un paquete rpm.<br>
`rpm -qf /etc/httpd/conf/httpd.conf`: verificar cuál paquete rpm pertenece a un fichero dado.<br>
`rpm -qp package.rpm -l`: mostrar lista de ficheros dados por un paquete rpm que aún no ha sido instalado.<br>
`rpm –import /media/cdrom/RPM-GPG-KEY`: importar la firma digital de la llave pública.<br>
`rpm –checksig package.rpm`: verificar la integridad de un paquete rpm.<br>
`rpm -qa gpg-pubkey`: verificar la integridad de todos los paquetes rpm instalados.<br>
`rpm -V package_name`: chequear el tamaño del fichero, licencias, tipos, dueño, grupo, chequeo de resumen de MD5 y última modificación.<br>
`rpm -Va`: chequear todos los paquetes rpm instalados en el sistema. Usar con cuidado.<br>
`rpm -Vp package.rpm`: verificar un paquete rpm no instalado todavía.<br>
`rpm2cpio package.rpm | cpio –extract –make-directories *bin*`: extraer fichero ejecutable desde un paquete rpm.<br>
`rpm -ivh /usr/src/redhat/RPMS/{arch}/package.rpm`: instalar un paquete construido desde una fuente rpm.<br>
`rpmbuild –rebuild package_name.src.rpm`: construir un paquete rpm desde una fuente rpm.<br>


### Actualizador de paquetes YUM (Red Hat, Fedora y similares)

`yum install package_name`: descargar e instalar un paquete rpm.<br>
`yum localinstall package_name.rpm`: este instalará un RPM y tratará de resolver todas las dependencies para ti, usando tus repositorios.<br>
`yum update package_name.rpm`: actualizar todos los paquetes rpm instalados en el sistema.<br>
`yum update package_name`: modernizar / actualizar un paquete rpm.<br>
`yum remove package_name`: eliminar un paquete rpm.<br>
`yum list`: listar todos los paquetes instalados en el sistema.<br>
`yum search package_name`: Encontrar un paquete en repositorio rpm.<br>
`yum clean packages`: limpiar un caché rpm borrando los paquetes descargados.<br>
`yum clean headers`: eliminar todos los ficheros de encabezamiento que el sistema usa para resolver la dependencia.<br>
`yum clean all`: eliminar desde los paquetes caché y ficheros de encabezado.<br>


### Paquetes Deb (Debian, Ubuntu y derivados)

`dpkg -i package.deb`: instalar / actualizar un paquete deb.<br>
`dpkg -r package_name`: eliminar un paquete deb del sistema.<br>
`dpkg -l`: mostrar todos los paquetes deb instalados en el sistema.<br>
`dpkg -l | grep httpd`: mostrar todos los paquetes deb con el nombre “httpd”<br>
`dpkg -s package_name`: obtener información en un paquete específico instalado en el sistema.<br>
`dpkg -L package_name`: mostar lista de ficheros dados por un paquete instalado en el sistema.<br>
`dpkg –contents package.deb`: mostrar lista de ficheros dados por un paquete no instalado todavía.<br>
`dpkg -S /bin/ping`: verificar cuál paquete pertenece a un fichero dado.<br>


### Actualizador de paquetes APT (Debian, Ubuntu y derivados)

`apt-get install package_name`: instalar / actualizar un paquete deb.<br>
`apt-cdrom install package_name`: instalar / actualizar un paquete deb desde un cdrom.<br>
`apt-get update`: actualizar la lista de paquetes.<br>
`apt-get upgrade`: actualizar todos los paquetes instalados.<br>
`apt-get remove package_name`: eliminar un paquete deb del sistema.<br>
`apt-get check`: verificar la correcta resolución de las dependencias.<br>
`apt-get clean`: limpiar cache desde los paquetes descargados.<br>
`apt-cache search searched-package`: retorna lista de paquetes que corresponde a la serie «paquetes buscados».<br>


### Ver el contenido de un fichero

`cat file1`: ver los contenidos de un fichero comenzando desde la primera hilera.<br>
`tac file1`: ver los contenidos de un fichero comenzando desde la última línea.<br>
`more file1`: ver el contenido a lo largo de un fichero.<br>
`less file1`: parecido al commando ‘more’ pero permite salvar el movimiento en el fichero así como el movimiento hacia atrás.<br>
`head -2 file1`: ver las dos primeras líneas de un fichero.<br>
`tail -2 file1`: ver las dos últimas líneas de un fichero.<br>
`tail -f /var/log/messages`: ver en tiempo real qué ha sido añadido al fichero.<br>


### Manipulación de texto

`cat file1 file2 .. | command <> file1_in.txt_or_file1_out.txt`: sintaxis general para la manipulación de texto utilizando PIPE, STDIN y STDOUT.<br>
`cat file1 | command( sed, grep, awk, grep, etc…) > result.txt`: sintaxis general para manipular un texto de un fichero y escribir el resultado en un fichero nuevo.<br>
`cat file1 | command( sed, grep, awk, grep, etc…) » result.txt`: sintaxis general para manipular un texto de un fichero y añadir resultado en un fichero existente.<br>
`grep Aug /var/log/messages`: buscar palabras “Aug” en el fichero ‘/var/log/messages’.<br>
`grep ^Aug /var/log/messages`: buscar palabras que comienzan con “Aug” en fichero ‘/var/log/messages’<br>
`grep [0-9] /var/log/messages`: seleccionar todas las líneas del fichero ‘/var/log/messages’ que contienen números.<br>
`grep Aug -R /var/log/*`: buscar la cadena “Aug” en el directorio ‘/var/log’ y debajo.<br>
`sed ‘s/stringa1/stringa2/g’ example.txt`: reubicar “string1” con “string2” en ejemplo.txt<br>
`sed ‘/^$/d’ example.txt`: eliminar todas las líneas en blanco desde el ejemplo.txt<br>
`sed ‘/ *#/d; /^$/d’ example.txt`: eliminar comentarios y líneas en blanco de ejemplo.txt<br>
`echo ‘esempio’ | tr ‘[`:lower:]’ ‘[:upper:]’: convertir minúsculas en mayúsculas.<br>
`sed -e ‘1d’ result.txt`: elimina la primera línea del fichero ejemplo.txt<br>
`sed -n ‘/stringa1/p’`: visualizar solamente las líneas que contienen la palabra “string1”.<br>


### Establecer caracter y conversión de ficheros

`dos2unix filedos.txt fileunix.txt`: convertir un formato de fichero texto desde MSDOS a UNIX.<br>
`unix2dos fileunix.txt filedos.txt`: convertir un formato de fichero de texto desde UNIX a MSDOS.<br>
`recode ..HTML < page.txt > page.html`: convertir un fichero de texto en html.<br>
`recode -l | more`: mostrar todas las conversiones de formato disponibles.<br>


### Análisis del sistema de ficheros

`badblocks -v /dev/hda1`: Chequear los bloques defectuosos en el disco hda1.<br>
`fsck /dev/hda1`: reparar / chequear la integridad del fichero del sistema Linux en el disco hda1.<br>
`fsck.ext2 /dev/hda1`: reparar / chequear la integridad del fichero del sistema ext 2 en el disco hda1.<br>
`e2fsck /dev/hda1`: reparar / chequear la integridad del fichero del sistema ext 2 en el disco hda1.<br>
`e2fsck -j /dev/hda1`: reparar / chequear la integridad del fichero del sistema ext 3 en el disco hda1.<br>
`fsck.ext3 /dev/hda1`: reparar / chequear la integridad del fichero del sistema ext 3 en el disco hda1.<br>
`fsck.vfat /dev/hda1`: reparar / chequear la integridad del fichero sistema fat en el disco hda1.<br>
`fsck.msdos /dev/hda1`: reparar / chequear la integridad de un fichero del sistema dos en el disco hda1.<br>
`dosfsck /dev/hda1`: reparar / chequear la integridad de un fichero del sistema dos en el disco hda1.<br>


### Formatear un sistema de ficheros

`mkfs /dev/hda1`: crear un fichero de sistema tipo Linux en la partición hda1.<br>
`mke2fs /dev/hda1`: crear un fichero de sistema tipo Linux ext 2 en hda1.<br>
`mke2fs -j /dev/hda1`: crear un fichero de sistema tipo Linux ext3 (periódico) en la partición hda1.<br>
`mkfs -t vfat 32 -F /dev/hda1`: crear un fichero de sistema FAT32 en hda1.<br>
`fdformat -n /dev/fd0`: formatear un disco flooply.<br>
`mkswap /dev/hda3`: crear un fichero de sistema swap.<br>


### Trabajo con la SWAP

`mkswap /dev/hda3`: crear fichero de sistema swap.<br>
`swapon /dev/hda3`: activando una nueva partición swap.<br>
`swapon /dev/hda2 /dev/hdb3`: activar dos particiones swap.<br>


### Salvas (Backup)

`dump -0aj -f /tmp/home0.bak /home`: hacer una salva completa del directorio ‘/home’.<br>
`dump -1aj -f /tmp/home0.bak /home`: hacer una salva incremental del directorio ‘/home’.<br>
`restore -if /tmp/home0.bak`: restaurando una salva interactivamente.<br>
`rsync -rogpav –delete /home /tmp`: sincronización entre directorios.<br>
`rsync -rogpav -e ssh –delete /home ip_address`:/tmp: rsync a través del túnel SSH.<br>
`rsync -az -e ssh –delete ip_addr`:/home/public /home/local: sincronizar un directorio local con un directorio remoto a través de ssh y de compresión.<br>
`rsync -az -e ssh –delete /home/local ip_addr`:/home/public: sincronizar un directorio remoto con un directorio local a través de ssh y de compresión.<br>
`dd bs=1M if=/dev/hda | gzip | ssh user@ip_addr ‘dd of=hda.gz’`: hacer una salva de un disco duro en un host remoto a través de ssh.<br>
`dd if=/dev/sda of=/tmp/file1`: salvar el contenido de un disco duro a un fichero. (En este caso el disco duro es “sda” y el fichero “file1”).<br>
`tar -Puf backup.tar /home/user`: hacer una salva incremental del directorio ‘/home/user’.<br>
`( cd /tmp/local/ && tar c . ) | ssh -C user@ip_addr ‘cd /home/share/ && tar x -p’`: copiar el contenido de un directorio en un directorio remoto a través de ssh.<br>
`( tar c /home ) | ssh -C user@ip_addr ‘cd /home/backup-home && tar x -p’`: copiar un directorio local en un directorio remoto a través de ssh.<br>
`tar cf – . | (cd /tmp/backup ; tar xf – )`: copia local conservando las licencias y enlaces desde un directorio a otro.<br>
`find /home/user1 -name ‘*.txt’ | xargs cp -av –target-directory=/home/backup/ –parents`: encontrar y copiar todos los ficheros con extensión ‘.txt’ de un directorio a otro.<br>
`find /var/log -name ‘*.log’ | tar cv –files-from=- | bzip2 > log.tar.bz2`: encontrar todos los ficheros con extensión ‘.log’ y hacer un archivo bzip.<br>
`dd if=/dev/hda of=/dev/fd0 bs=512 count=1`: hacer una copia del MRB (Master Boot Record) a un disco floppy.<br>
`dd if=/dev/fd0 of=/dev/hda bs=512 count=1`: restaurar la copia del MBR (Master Boot Record) salvada en un floppy.<br>


### CD-ROM

`cdrecord -v gracetime=2 dev=/dev/cdrom -eject blank=fast -force`: limpiar o borrar un cd regrabable.<br>
`mkisofs /dev/cdrom > cd.iso`: crear una imagen iso de cdrom en disco.<br>
`mkisofs /dev/cdrom | gzip > cd_iso.gz`: crear una imagen comprimida iso de cdrom en disco.<br>
`mkisofs -J -allow-leading-dots -R -V “Label CD” -iso-level 4 -o ./cd.iso data_cd`: crear una imagen iso de un directorio.<br>
`cdrecord -v dev=/dev/cdrom cd.iso`: quemar una imagen iso.<br>
`gzip -dc cd_iso.gz | cdrecord dev=/dev/cdrom –`: quemar una imagen iso comprimida.<br>
`mount -o loop cd.iso /mnt/iso`: montar una imagen iso.<br>
`cd-paranoia -B`: llevar canciones de un cd a ficheros wav.<br>
`cd-paranoia – ”-3”`: llevar las 3 primeras canciones de un cd a ficheros wav.<br>
`cdrecord –scanbus`: escanear bus para identificar el canal scsi.<br>
`dd if=/dev/hdc | md5sum`: hacer funcionar un md5sum en un dispositivo, como un CD.<br>


### Trabajo con la RED ( LAN y Wi-Fi)

`ifconfig eth0`: mostrar la configuración de una tarjeta de red Ethernet.<br>
`ifup eth0`: activar una interface ‘eth0’.<br>
`ifdown eth0`: deshabilitar una interface ‘eth0’.<br>
`ifconfig eth0 192.168.1.1 netmask 255.255.255.0`: configurar una dirección IP.<br>
`ifconfig eth0 promisc`: configurar ‘eth0’en modo común para obtener los paquetes (sniffing).<br>
`dhclient eth0`: activar la interface ‘eth0’ en modo dhcp.<br>
`route -n`: mostrar mesa de recorrido.<br>
`route add -net 0/0 gw IP_Gateway`: configurar entrada predeterminada.<br>
`route add -net 192.168.0.0 netmask 255.255.0.0 gw 192.168.1.1`: configurar ruta estática para buscar la red ‘192.168.0.0/16’.<br>
`route del 0/0 gw IP_gateway`: eliminar la ruta estática.<br>
`echo “1” > /proc/sys/net/ipv4/ip_forward`: activar el recorrido ip.<br>
`hostname`: mostrar el nombre del host del sistema.<br>
`host www.example.com`: buscar el nombre del host para resolver el nombre a una dirección ip(1).<br>
`nslookup www.example.com`: buscar el nombre del host para resolver el nombre a una direccióm ip y viceversa(2).<br>
`ip link show`: mostar el estado de enlace de todas las interfaces.<br>
`mii-tool eth0`: mostar el estado de enlace de ‘eth0’.<br>
`ethtool eth0`: mostrar las estadísticas de tarjeta de red ‘eth0’.<br>
`netstat -tup`: mostrar todas las conexiones de red activas y sus PID.<br>
`netstat -tupl`: mostrar todos los servicios de escucha de red en el sistema y sus PID.<br>
`tcpdump tcp port 80`: mostrar todo el tráfico HTTP.<br>
`iwlist scan`: mostrar las redes inalámbricas.<br>
`iwconfig eth1`: mostrar la configuración de una tarjeta de red inalámbrica.<br>
`whois www.example.com`: buscar en base de datos Whois.<br>


### Redes de Microsoft Windows (SAMBA)

`nbtscan ip_addr`: resolución de nombre de red bios.<br>
`nmblookup -A ip_addr`: resolución de nombre de red bios.<br>
`smbclient -L ip_addr/hostname`: mostrar acciones remotas de un host en windows.<br>


### Tablas IP (CORTAFUEGOS)

`iptables -t filter -L`: mostrar todas las cadenas de la tabla de filtro.<br>
`iptables -t nat -L`: mostrar todas las cadenas de la tabla nat.<br>
`iptables -t filter -F`: limpiar todas las reglas de la tabla de filtro.<br>
`iptables -t nat -F`: limpiar todas las reglas de la tabla nat.<br>
`iptables -t filter -X`: borrar cualquier cadena creada por el usuario.<br>
`iptables -t filter -A INPUT -p tcp –dport telnet -j ACCEPT`: permitir las conexiones telnet para entar.<br>
`iptables -t filter -A OUTPUT -p tcp –dport http -j DROP`: bloquear las conexiones HTTP para salir.<br>
`iptables -t filter -A FORWARD -p tcp –dport pop3 -j ACCEPT`: permitir las conexiones POP a una cadena delantera.<br>
`iptables -t filter -A INPUT -j LOG –log-prefix “DROP INPUT”`: registrando una cadena de entrada.<br>
`iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE`: configurar un PAT (Puerto de traducción de dirección) en eth0, ocultando los paquetes de salida forzada.<br>
`iptables -t nat -A PREROUTING -d 192.168.0.1 -p tcp -m tcp –dport 22 -j DNAT –to-destination 10.0.0.2`:22: redireccionar los paquetes diriguidos de un host a otro.<br>


### Monitoreando y depurando

`top`: mostrar las tareas de linux usando la mayoría cpu.<br>
`ps -eafw`: muestra las tareas Linux.<br>
`ps -e -o pid,args –forest`: muestra las tareas Linux en un modo jerárquico.<br>
`pstree`: mostrar un árbol sistema de procesos.<br>
`kill -9 ID_Processo`: forzar el cierre de un proceso y terminarlo.<br>
`kill -1 ID_Processo`: forzar un proceso para recargar la configuración.<br>
`lsof -p $$`: mostrar una lista de ficheros abiertos por procesos.<br>
`lsof /home/user1`: muestra una lista de ficheros abiertos en un camino dado del sistema.<br>
`strace -c ls >/dev/null`: mostrar las llamadas del sistema hechas y recibidas por un proceso.<br>
`strace -f -e open ls >/dev/null`: mostrar las llamadas a la biblioteca.<br>
`watch -n1 ‘cat /proc/interrupts’`: mostrar interrupciones en tiempo real.<br>
`last reboot`: mostrar historial de reinicio.<br>
`lsmod`: mostrar el kernel cargado.<br>
`free -m`: muestra el estado de la RAM en megabytes.<br>
`smartctl -A /dev/hda`: monitorear la fiabilidad de un disco duro a través de SMART.<br>
`smartctl -i /dev/hda`: chequear si SMART está activado en un disco duro.<br>
`tail /var/log/dmesg`: mostrar eventos inherentes al proceso de carga del kernel.<br>
`tail /var/log/messages`: mostrar los eventos del sistema.<br>

### Otros comandos útiles

`apropos …keyword`: mostrar una lista de comandos que pertenecen a las palabras claves de un programa; son útiles cuando tú sabes qué hace tu programa, pero de sconoces el nombre del comando.<br>
`man ping`: mostrar las páginas del manual on-line; por ejemplo, en un comando ping, usar la opción ‘-k’ para encontrar cualquier comando relacionado.<br>
`whatis …keyword`: muestra la descripción de lo que hace el programa.<br>
`mkbootdisk –device /dev/fd0 `uname -r``: crear un floppy boteable.<br>
`gpg -c file1`: codificar un fichero con guardia de seguridad GNU.<br>
`gpg file1.gpg`: decodificar un fichero con Guardia de seguridad GNU.<br>
`wget -r www.example.com`: descargar un sitio web completo.<br>
`wget -c www.example.com/file.iso`: descargar un fichero con la posibilidad de parar la descargar y reanudar más tarde.<br>
`echo ‘wget -c www.example.com/files.iso‘ | at 09`:00: Comenzar una descarga a cualquier hora. En este caso empezaría a las 9 horas.<br>
`ldd /usr/bin/ssh`: mostrar las bibliotecas compartidas requeridas por el programa ssh.<br>
`alias hh=’history’`: colocar un alias para un commando –hh= Historial.<br>
`chsh`: cambiar el comando Shell.<br>
`chsh –list-shells`: es un comando adecuado para saber si tienes que hacer remoto en otra terminal.<br>
`who -a`: mostrar quien está registrado, e imprimir hora del último sistema de importación, procesos muertos, procesos de registro de sistema, procesos activos producidos por init, funcionamiento actual y últimos cambios del reloj del sistema.<br>

### Comprimir y descomprimir archivos
**Archivos .tar.gz:**

Comprimir: `tar -czvf empaquetado.tar.gz /carpeta/a/empaquetar/`

Descomprimir: `tar -xzvf archivo.tar.gz`

**Archivos .tar:**

Empaquetar: `tar -cvf paquete.tar /dir/a/comprimir/`

Desempaquetar: `tar -xvf paquete.tar`

**Archivos .gz:**

Comprimir: `gzip -9 index.php`

Descomprimir: `gzip -d index.php.gz`

**Archivos .zip:**
Comprimir: `zip archivo.zip carpeta`

Descomprimir: `unzip archivo.zip`

### Extras:

Recuperar la consola de BASH por defecto cuando se ejecuta otra shell:
```bash
$ nsudo chsh --shell=/bin/bash $USER
```


Ref: https://gist.github.com/ElenaMLopez/88c37c58a0c9ff7242a77c9a8eaea553