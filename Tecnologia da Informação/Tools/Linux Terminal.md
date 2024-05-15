# Linux Terminal

## Basics

- **Prompt Structure:** `$ (prompt) | command | option | argument`
- **Open Terminal:** `CTRL + ALT + T`
- **Close Terminal:** `exit`
- **Clear Terminal:** `clear`

### Copy and Paste

- **Copy:** `Ctrl+Shift+C`
- **Paste:** `Ctrl+Shift+V`

### Tab: Auto-complete

```bash
echo set completion-ignore-case on | sudo tee -a /etc/inputrc
```

- **Get Help:** `[command] -help`
- **Set Permissions to Current User:** `sudo chown -Rv $(id -u):$(id -g) ~`
- **Notepad:** `nano`

### Shortcuts

- **Run Console for a Single Command:** `Alt+F2`

## Manual

- **Manual:** `man [command]`
- **Search in Manual:** `/[what you are looking for]`
- **Navigate Manual Search Results:** `N` or `Shift+N`

## Navigation

- **Print Working Directory:** `pwd`
- **Create Directory / Folder:** `mkdir [name]`
- **Create Nested Directories:** `mkdir -p [parent]/[child]`
- **Create File:** `touch [name of the file with extension]`
- **List Directory Content:** `ls [directory]`
  - Operadores:
    - `-R`: Lista de forma recursiva.
    - `-l`: Mostra os detalhes em formato longo.
    - `-a`: Mostra todos os arquivos e ocultos.
    - `>`: Redireciona a saída para um arquivo.
  - Exemplo: `ls -Rla > <filename>`
- **Change Directory:** `cd [name of the directory]`

### Go to Drive

```bash
cd /media/$USER/<drive name>
cd /path/to/my\ folder\ with\ spaces/
```

- **Up One Level:** `cd` or `cd ..`
- **Return to User Directory:** `cd ~`
- **Rename File or Directory (Move):** `mv [current name] [new name]`
  - Bulk extension renane: `find . -name "*.extension" -exec bash -c 'mv "$0" "${0%.extension}.new-extension"' {} \;`
- **Copy File or Directory:** `cp [current directory] [new directory]`
- **Delete File (Remove):** `rm [name]`
- **Delete Directory (Remove):** `rm -r [name]`
- **Delete All Files in a Directory:** `rm ~/path/to/folder/*`
- **Open File in Google Chrome:** `google-chrome [file]`

## Reading Files

- **Print All File Content in One Go:** `cat <filename>`
- **Print Large File Content:** `less <filename>`
- **Exit:** `q`
- **Open File in Default CLI Editor:** `editor <filename>`
- **Open File in Gedit Text Editor:** `gedit <filename>`

## Operating System

- **Change Username Displayed in the Terminal:** `sudo hostnamectl set-hostname <username>`
- **Update Linux:**
  - `sudo apt update`
  - `sudo apt upgrade`
  - `sudo apt update && sudo apt upgrade`
  - Remove orphaned dependencies: `sudo apt autoremove`
- **Check OS Version:** `lsb_release -a`
- **List Services:**
  - `service --status-all`
  - `systemctl list-units`
- **Reboot OS:** `reboot`

## Google Chrome Developer Tools

### Open

- `Ctrl + Shift + J`
- `F12`

### Install

```bash
sudo apt update
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb
# OR
sudo apt install ./google-chrome-stable_current_amd64.deb
```

- **Launch it:** `google-chrome`

## Other

- **Word Count:** `wc [filename]` (outputs: lines words characters)
- **Project total line count:** `find . -name "*.js" -type f -exec cat {} + | wc -l`
- **Print Some Text:** `echo [text to print]`

## Hardware

### WebCam

```bash
# to kill laptop camera
sudo rmmod -f uvcvideo

# to restart the video module
sudo modprobe -r uvcvideo

# to restart the laptop camera
sudo modprobe uvcvideo

# can be used while skipping steps 2&3 to restart the camera directly
sudo modprobe -a uvcvideo
```

### Disable Bluetooth

```bash
sudo systemctl disable bluetooth.service
sudo systemctl mask bluetooth.service
```

- **Hardware Info:** `sudo apt install hardinfo`
- **CPU Stress Test:**
  - `sudo apt install s-tui stress`
  - `s-tui`

## Install Software

- `sudo dpkg -i <filename>.deb`
- `sudo apt install ./<filename>.deb` (install with all dependencies)
- `sudo apt install -f` (fix broken software dependencies)
- **Locate Installation Directory:** `which <app name>`

### Tools

- **Nemo file manager (Not recommended, Nautilus is better):**

  ```bash
  # Install
  sudo apt install nemo

  # Make it the default file manager
  xdg-mime default nemo.desktop inode/directory application/x-gnome-saved-search
  gsettings set org.gnome.desktop.background show-desktop-icons false
  gsettings set org.nemo.desktop show-desktop-icons true
  ```

- **Text Editor:** `sudo apt install notepadqq`
- **File Merge and Comparison:** `FreeFileSync_11.27_Install.run`
- **Video Codecs**

  ```bash
  sudo apt install ubuntu-restricted-extras -y
  sudo apt install vlc`
  ```

- **Video Converter:** `sudo apt install ./winff_1.5.5-8build1_all.deb`
- **Font Manager:** `sudo apt install font-manager`
- **OBS Studio:**

  ```bash
  sudo add-apt-repository ppa:obsproject/obs-studio
  sudo apt install obs-studio
  ```

- **qBittorent:** `sudo apt-get install qbittorrent`
- **flatpak:** `sudo apt install flatpak`

- **Add Flathub repository:**

  ```bash
    flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
  ```

- **Install or update Blender:**

  ```bash
      flatpak install flathub org.blender.Blender
      flatpak update org.blender.Blender
  ```

## Uninstall Software (and all its dependencies)

- `sudo apt remove <package-name> --auto-remove`
- `sudo apt-get remove --purge <package-name>`

Or for removing unused packages for the whole OS:

- `sudo apt-get autoremove`

## Troubleshooting

### On Boot, the OS GUI Does not load, and you have access to the CLI

1. Restart the GUI:

   ```bash
   sudo startx
   ```

2. Reinstall the GUI (GNOME Desktop Environment)

   ```bash
   sudo apt-get install --reinstall ubuntu-desktop
   ```

### Error while trying to install: /var/lib/dpkg/lock or lock-frontend

```bash
Could not get lock /var/lib/dpkg/lock – open (11: Resource temporarily unavailable)
E: Unable to lock the administration directory (/var/lib/dpkg/),
is another process using it?
```

1. Try one at a time

   ```bash
   # Remove APT lock
   sudo rm -rf /var/lib/apt/lists/lock

   # Remove dpkg lock
   sudo rm /var/lib/dpkg/lock

   # Remove apt archives lock
   sudo rm /var/cache/apt/archives/lock
   ```

2. If the problem persists

   ```bash
   # Update APT package lists
   sudo apt-get update

   # Configure dpkg
   sudo dpkg --configure -a

   # Fix broken dependencies
   sudo apt-get -f install
   ```

3. For the frontend error variant

   ```bash
   # Remove dpkg frontend lock
   sudo rm /var/lib/dpkg/lock-frontend

   # Configure dpkg
   sudo dpkg --configure -a

   # Update APT package lists
   sudo apt update
   ```

### Pending update of "snap-store" snap Close the app to avoid disruptions

1. Kill all processes associated with the Snap Store and update all installed snap packages on the system to their latest versions.

   ```bash
   sudo killall snap-store && sudo snap refresh
   ```

### Gimp can not access drive: Permission denied

1. Run the command:

   ```bash
   sudo snap connect gimp:removable-media :removable-media
   ```