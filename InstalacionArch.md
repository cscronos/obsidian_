# ArchLinux
```md
curl -s https://raw.githubusercontent.com/CristobalSg/scriptcs/master/ForDiscos.sh -o ArchScript.sh ; chmod +x ArchScript.sh ; ./ArchScript.sh
```

**Idioma teclado**
*Este es para español, pero por defecto viene en ingles.**
```md 
loadkeys es
 ```


**Conexión Inalámbrica**
*si estas conectado por cable no es necesario hacer lo siguiente.*
```md 
iwctl 
device list 
station NOMBRE_DISPOSITIVO scan # El nombre sale del comando anterior 
station NOMBRE_DISPOSITIVO get-networks 
station NOMBRE_DISPOSITIVO connect NOMBRE_ROUTER 
exit

# comprobar si tienes internet 
ping archlinux.org 
timedatectl set-ntp true
 ```

**Particion**
En local
```md 
# Enlistamos los discos. 
fdisk -l 
# Para entrar a armar los discos
cfdisk
cfdisk /dev/NOMBRE_DISCO_O_PARTICION
# Orden de Discos / todas estas son particiones primatias
sda1 - 512M - Type:EFI System
sda2 - 50G - Linux filesystem - raiz para el SO
sda3 - 350G -Linux filesystem - para archivos
sda4 - 8G - Linux swap
# Para ver todos los discos
lsblk
# Formateamos partes
1. mkfs.vfat -F32 /dev/sda1 # boot; 521M 
3. mkfs.ext4 /dev/sda2      # raiz; 50G
4. mkfs.ext4 /dev/sda3      # home; 370G
5. mkswap /dev/sda4         # swap; 8G
swapon
# montamos los sda
mount /dev/sda2 /mnt
mkdir /mnt/boot
mkdir /mnt/boot/efi
mount /dev/sda1 /mnt/boot/efi
mkdir /mnt/home
mount /dev/sda3 /mnt/home
```

**Intalamos el Kernel y el Firmware**
```md
pacstrap /mnt base linux linux-firmware nano grub networkmanager dhcpcd efibootmgr

pacstrap /mnt netctl wpa_supplicant dialog

genfstab /mnt >> /mnt/etc/fstab
```

**Config del sistema**
```md
arch-chroot /mnt
echo "cscolchones" > /etc/hostname
# zona horaria
ln -sf /usr/share/zoneinfo/America/Santiago /etc/localtime
# editamos el archivo
nvim /etc/locale.gen # Buscar en_US.UTF-8 UTF-8 y es_ES.UTF-8 UTF-8
locale-gen
hwclock -w

echo "LANG=es_CL.UTF-8" > /etc/locale.conf 
echo "KEYMAP=es" > /etc/vconsole.conf 

systemctl enable NetworkManager 

# grub
grub-install --efi-directory=/boot/efi --bootloader -id='Arch Linux' --target=x86_64-efi

grub-mkconfig -o /boot/grub/grub.cfg
```

**Damos Contraseñas**
```md 
passwd 
> ****
> ****
useradd -m USUARIO 
passwd USUARIO 
> exit  
umount -R /mnt 
shutdown now
```

**Para el wifi**
```md 

```
