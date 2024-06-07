## Create and Manage your Project Virtual Environment

This project uses external packages, which are not included in the Python Standard Library - we must install them. 
To keep our project separate from all other Python projects,
we will create and manage a local project virtual environment.
Additional details and commands are listed below. 

## Recommended Process

1. Open your project folder in VS Code.
2. Open a terminal window in VS Code (PowerShell for Windows, zsh or bash for Mac/Linux).
3. In the terminal, run the command `git pull` first, to make sure you have the current project contents on your machine.
4. In the terminal, run the command `py -m venv .venv` to create a new .venv environment in the project repo.
5. In the terminal, activate your environment using the command for your operating system.
6. In the terminal, use `py -m pip install` command(s) to install necessary packages into your active project virtual environment.
7. Edit your README.md to record your commands, process, and notes.
8. Set your VS Code Python Interpreter so your installed packages will be available for import.
9. In the terminal, run `git add .` then `git commit -m "msg"`, then` git push -u origin main` to add / commit / push to GitHub.
10. Verify your GitHub repository.

### 1. Open Project Folder in VS Code

Open the project folder on your machine (the one you cloned from GitHub into your Documents folder) if not already open. 

### 2. Open VS Code Terminal

Open a terminal window in VS Code (PowerShell for Windows, zsh or bash for Mac/Linux). 

### 3. Git Pull

In the terminal, run git pull to fetch any changes that might have been made to the GitHub version.
There may not be any changes, but it's good practice to pull every time you start work on a git project. 

```shell
git pull
```

### 4. Create Project Virtual Environment (One-Time Only)

Use your terminal to create your project virtual environment by running venv as a Python module (py -m venv) and providing a name to use for the local folder as .venv.
If you name it differently, be sure that your folder name is included in the .gitignore file. 

Windows command

```shell
py -m venv .venv
```

Mac/Linux command

```
python3 -m venv .venv
```

You should get a new folder in your project repository named .venv. 
If VS Code asks to use use this environment, click Yes. 

### 5. Activate the Project Virtual Environment (Every time you open a terminal) 

Use your terminal to activate your project virtual environment. (Do this every time you open a new terminal to work on your project.)

Windows commands to activate your .venv. Try the first. Use the second if the first doesn't work. 

```shell
.venv\Scripts\Activate
.\.venv\Scripts\Activate.ps1
```

Mac/Linux command to activate your .venv

```shell
source .venv/bin/activate
```

Verify you see the virtual environment name (.venv) in your terminal prompt.

### 6. Install Packages into Active Environment (One-Time, As Needed) 

Verify your project virtual environment located in .venv is active.
If not, activate it. 
You should see .venv in your terminal prompt. 
Use your favorite method to install the necessary packages.

At this point, the only project dependencies we know we need are:

- requests - one of the most popular and widely used packages for web (HTTP) requests in Python
 
Windows command to install project dependencies:

```shell
py -m pip install pandas pyarrow
```

Mac/Linux command to install project dependencies:

```shell
python3 -m pip install pandas pyarrow
```

OR: Use requirements.txt to install packages instead

If you like, you can use a [requirements.txt](requirements.txt) file to install dependencies instead.
These files are helpful in projects when we have several external packages to install and it can be good practice.

To do so, you'll need a file named requirements.txt in the root folder of your repository listing each external package used, one per line. 

If using Windows PowerShell, install into your active project virtual environment with this command:

```shell
py -m pip install -r requirements.txt
```

If using Mac or Linux, install into your active project virtual environment with this command:

```shell
python3 -m pip install -r requirements.txt
```

If successful, you will now be able to use the following line in your Python scripts.
If you get an error on this line, work through the steps above to
create, activate, and install into your local project virtual environment,
and make sure VS Code is using your .venv local project environment. 

```
import requests
```

### 7. Edit README.md

In VS Code, edit your README.md file to record your commands, process, and notes.

Use one hash followed by a space for the title.

Use two hashes followed by a space to create second level headings. 

Use triple back tics on a line by themselves above and below to "fence" your code and commands. 
 
### 8. Set VS Code Interpreter

In VS Code, from the menu, select View.
From the dropdown menu, select Command Palette.... 

Alternatively, you can use the shortcut Ctrl+Shift+P (Windows/Linux) or Cmd+Shift+P (Mac) to open the Command Palette.

In the Command Palette, start typing Python: Select Interpreter.

When you see Python: Select Interpreter in the list of options, click on it.
A list of available Python interpreters will appear.

Locate and select your project's virtual environment, typically named .venv (or similar).

Confirm your selection. VS Code will now use the selected interpreter for your project.

### 9. Git Add / Commit / Push to GitHub

Use your terminal to add your files to source control, commit your changes to git, and push them up to GitHub. 

Git add any new files.

```shell
git add .
```

Git commit changes.

```shell
git commit -m "after .venv setup"
```

Git push to GitHub. 

```shell
git push -u origin main
```

### 10. Verify

Verify your README.md and .gitignore (and optionally, requirements.txt if used) appear correctly in your GitHub repo.
Since you added .venv/ to your .gitignore, your .venv folder should NOT appear in GitHub.
This is good - it saves space and allows us to track just the progress of our project files. 
