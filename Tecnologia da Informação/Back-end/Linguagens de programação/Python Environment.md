# Python Environment

## Install
```bash
sudo apt-get install python3 python3-dev
```
Check current version:
```bash
python3 --version or python3 -V or python --version
```

## Upgrade pip
```bash
python3 -m pip install --upgrade pip
python -m pip install --upgrade pip
```

## Virtual Environment
Install Venv library:
```bash
sudo apt install python3.8-venv
```
Create environment folder:
```bash
python3 -m venv <folder name to create>
```
Activate:
```bash
source <environment folder>/bin/activate
```
Deactivate:
```bash
deactivate
```
List all installed packages:
```bash
python -m pip list
```
Set virtual environment for a specific python version:
```bash
python3.8 -m virtualenv myenv
```

## Setup necessary libraries (requirements.txt)
Generate the requirements.txt content from the current environment:
```bash
pip freeze > requirements.txt
```
It creates the requirements.txt with all necessary libraries and versions.

Install:
```bash
python -m pip install -r requirements.txt
```
Uninstall:
```bash
pip uninstall -r requirements.txt -y
```

## IDE
### Visual Studio Code
Install:
```bash
sudo apt install code
sudo snap install code --classic
```
Run:
```bash
code
```
Install Python extension.

### PyCharm

## API clients
Uses:
- Enables to explore, debug, and test APIs.
- Enables to define complex API requests for HTTP, REST, SOAP, GraphQL, and WebSockets.

### Insomnia
Website: [https://insomnia.rest/download](https://insomnia.rest/download)

Install: download and install \*.deb file or install from Ubuntu Software.

### Postman
Website: [https://www.postman.com/downloads/](https://www.postman.com/downloads/)

Install: download from website, extract and run or install from Ubuntu Software.

## Libraries
Uninstall library:
```bash
pip uninstall <packagename>
```

- NumPy: `pip install numpy`
- Pandas: `pip install pandas`
- Matplotlib: `pip install matplotlib`
- Seaborn: `pip install seaborn`
- Requests: `pip install requests`
    - Website: [https://requests.readthedocs.io/en/latest/](https://requests.readthedocs.io/en/latest/)
- Beautiful Soup: `pip install beautifulsoup4`
    - Website: [https://www.crummy.com/software/BeautifulSoup/](https://www.crummy.com/software/BeautifulSoup/)
- Selenium: `pip install selenium`

### Jupyter Notebook
Install on a virtual environment:
```bash
pip install jupyter
```
Run:
```bash
jupyter notebook
```
Quit from terminal: `Ctrl + c`

### Scrapy
Install dependencies:
```bash
sudo apt-get install python3 python3-dev python3-pip libxml2-dev libxslt1-dev zlib1g-dev libffi-dev libssl-dev
```
Install:
```bash
pip install scrapy
```
Test installation:
```bash
scrapy bench
```
If you see no errors, everything is fine.

## Generate application executable file using PyInstaller
Project website: [pyinstaller.org](https://pyinstaller.org)

Install:
```bash
pip install -U pyinstaller
```
Create executable in your project folder:
```bash
pyinstaller your_program.py --onefile
```

## Automate tasks with Cron
### Syntax
```bash
crontab [-u user] file
crontab [-u user] [-l | -r | -e] [-i] [-s]
```

### Options
- `file`: Load the crontab data from the specified file.
- `-u user`: Specifies the user whose crontab is to be viewed or modified (optional).
- `-l`: List/Display the current crontab.
- `-r`: Remove the current crontab.
- `-e`: Edit the current crontab.
- `-i`: Same as `-r`, but gives the user a yes/no confirmation prompt.
- `-s`: Appends the current SELinux security context string as an MLS_LEVEL.

### Process
1. Enter configuration:
```bash
crontab -e
```
2. Paste the attributes.
3. Press Esc, then type (for writing and quit): `wq + Enter`.
4. List active cronjobs:
```bash
crontab -l
```

### Install
```bash
sudo apt install cron
```

Run it on the background:
```bash
sudo systemctl enable cron
```

### Attributes order and example
```bash
<minute: 0-59> <hour: 0-23> <day_of_month: 1-31> <month: 1-12> <day_of_week: 0-7 (0 or 7 is Sunday)> <command_to_run>
```

Example:
```bash
30 17 * * 2 curl http://www.google.com
```
Runs the command `curl http://www.google.com` every Tuesday at 5:30 PM.

Helper website to generate attributes: [crontab.guru](https://crontab.guru)