# Mantecion
>ssh csandoval@pillan.inf.uct.cl
>whoami > soypillan.txt && uname -a >> soypillan.txt
>echo "El texto" >> ultima linea primera linea
>
>(whoami) imprime el nombre del usuario actual
>(>) escribimos en la primera linea
>(>>) escribimos en la utlima linea
>(uname) nos da el resumen informativo del sistema mientras que (-a) nos dara toda la informacion del sistema

Descargar archivo de pillan
> scp csandoval@pillan.inf.uct.cl:~/archivo.txt .

para borrar rm y listok
> rm -r 

>mkdir [nombre del directorio]  # creamos un directorio o carpeta
>touch [archivo vacio] # creamos un archivo vacio

Para ver el modilo o drivers se usa
>cat /proc/modules

para escribirlo en un archo txt es 
>cat /proc/modules > nombrearchivo.txt

para ver los dispositivos PCi
>lspci

variable de entorno 
>env 
>o
>printenv

Para renombrar un archivo
>mv #nombrecarpeta #nombrenuevo

para ver la hora
>date

copiamos archivo a otro lugar
>cp -p #nombredearchivo #/direcciondeenvio #nombrenuevo 

Darme Permisos a usuario
>chmod u+rwx #nombredearchivo

Quitar permisos a grupo y otros 
>chmod go-rwx #nombredearchivo