# How To Install VMware Workstation On Arch Linux

This guide shows how to install **VMware Workstation** on **Arch Linux**

## Step 1: Install an AUR helper if you don't have one (like `yay` or `paru`):

### Installing `yay`

```bash
# Install yay if you don't have it
sudo pacman -S --needed git base-devel
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si
```

### Installing `paru`

```bash
# If you prefer paru this is how to install it
git clone https://aur.archlinux.org/paru-bin
cd paru-bin/
makepkg -si
```

## Step 2: Install Dependencies

```bash
sudo pacman -S fuse2 gtkmm linux-headers pcsclite libcanberra
```

```bash
yay -S --noconfirm --needed ncurses5-compat-libs
```

```bash
yay -S vmware-keymaps
```

## Step 3: Install VMware Workstation Pro

```bash
yay -S --noconfirm --needed  vmware-workstation
```

## Step 4: Enable and start the services

```bash
sudo systemctl enable vmware-networks.service
sudo systemctl enable vmware-usbarbitrator.service
sudo systemctl start vmware-networks.service
sudo systemctl start vmware-usbarbitrator.service
```

Now you should have full VMware functionality including NAT, host-only networking, and all the advanced features!
