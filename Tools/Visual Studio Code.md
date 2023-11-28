# Visual Studio Code

## Install

1. Download package to current directory:

   ```bash
   wget -O code-latest.deb 'https://code.visualstudio.com/sha/download?build=stable&os=linux-deb-x64'
   ```

2. Install the downloaded package:

   ```bash
   sudo apt install ./code-latest.deb
   ```

## Open IDE

- **First method:** Open project

  ```bash
  code my_awesome_project/.
  ```

- **Second method:** Must be in a project folder, then run

  ```bash
  code .
  ```

## Setup

### Extensions

- **Prettier:**

  - Settings to change:
    - Format On Save (enable)
    - Default Formatter (Prettier)

- **Live Server**

### Duplicate line

1. Go To Preferences -> Keyboard Shortcuts.
2. Search for "Duplicate Selection".
3. Change it to: `Ctrl + d`

## Editing

- **Comment line:** `Ctrl + /`
- **Delete line:** `Ctrl + x`
- **Move line(s) up or down:** `Alt + up/down arrows`
- **Generate HTML boilerplate:** `!`
