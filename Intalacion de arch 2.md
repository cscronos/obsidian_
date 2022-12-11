Siiii segundo intento
# Guia de instalación de Arch Linux en asus g14

# este comando es solo si tienes una tarjeta de nvidia
rmmod nouveau

# si estas conectado por cable no es necesario hacer lo siguiente
# Conexión Inalámbrica
loadkeys es
iwctl
device list
station NOMBRE_DISPOSITIVO scan  # El nombre sale del comando anterior
station NOMBRE_DISPOSITIVO get-networks
station NOMBRE_DISPOSITIVO connect NOMBRE_ROUTER
exit

# comprobar si tienes internet
ping archlinux.org
timedatectl set-ntp true

# Crear y formatear particiones (comandos usados en mi caso)

cfdisk
# Se crean 4 particiones
# Una para el /boot, 512M
# Una para el /, 50G
# Una para el /home, lo que quede de espacio
# La última para el swap, 1G

mkfs.fat -F32 /dev/nvme0n1p1
mkfs.ext4 /dev/nvme0n1p2
mkfs.ext4 /dev/nvme0n1p3
mkswap /dev/nvme0n1p4
swapon /dev/nvme0n1p4
mount /dev/nvme0n1p2 /mnt
mkdir /mnt/home
mount /dev/nvme0n1p3 /mnt/home
mkdir /mnt/boot
mount /dev/nvme0n1p1 /mnt/boot

# Para prevenir un error
pacman -Sy archlinux-keyring

# Instalar el kernel y el firmware

pacstrap /mnt base linux linux-firmware 
genfstab -U /mnt >> /mnt/etc/fstab 

# Configurar sistema

arch-chroot /mnt
ln -sf /usr/share/zoneinfo/Europe/Madrid /etc/localtime
hwclock --systohc
pacman -S neovim 
nvim /etc/locale.gen  # Buscar en_US.UTF-8 UTF-8 y es_ES.UTF-8 UTF-8
locale-gen
echo "LANG=es_CL.UTF-8" > /etc/locale.conf
echo "KEYMAP=es" > /etc/vconsole.conf
echo "asus" > /etc/hostname
nvim /etc/hosts
passwd
pacman -S grub efibootmgr
grub-install --target=x86_64-efi --efi-directory=/boot
grub-mkconfig -o /boot/grub/grub.cfg
pacman -S networkmanager
systemctl enable NetworkManager
useradd -m usuario
passwd usuario
usermod -aG wheel,audio,video,storage usuario
pacman -S sudo
nvim /etc/sudoers
exit
umount -R /mnt
shutdown now

# Sacar USB y arrancar PC

# Instalar Entorno de Escritorio gnome

nmcli device wifi list
nmcli device wifi connect NOMBRE password CONTRASEÑA
ping archlinux.org
sudo pacman -S xorg gnome
sudo systemctl enable gdm.service