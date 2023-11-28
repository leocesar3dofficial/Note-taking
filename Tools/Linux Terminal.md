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
- **Change Directory:** `cd [name of the directory]`

### Go to Drive

```bash
cd /media/$USER/<drive name>
cd /path/to/my\ folder\ with\ spaces/
```

- **Up One Level:** `cd` or `cd ..`
- **Return to User Directory:** `cd ~`
- **Rename File or Directory (Move):** `mv [current name] [new name]`
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
- **Print Some Text:** `echo [text to print]`

## Hardware

### WebCam

```bash
sudo rmmod -f uvcvideo # to kill laptop camera
sudo modprobe -r uvcvideo # to restart the video module
sudo modprobe uvcvideo # to restart the laptop camera
sudo modprobe -a uvcvideo # can be used while skipping steps 2&3 to restart the camera directly
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

- **Text Editor:** `sudo apt install notepadqq`
- **File Merge and Comparison:** `FreeFileSync_11.27_Install.run`
- **Video Codecs:**
  - `sudo apt install ubuntu-restricted-extras -y`
  - `sudo apt install vlc`

## Uninstall Software

- `sudo apt remove <package-name>`

## Troubleshooting

- **On Boot, the OS GUI Does Not Load, and You Have Access to the CLI:**
  1. Restart the GUI: `sudo startx`
  2. Reinstall the GUI (GNOME Desktop Environment): `sudo apt-get install --reinstall ubuntu-desktop`
