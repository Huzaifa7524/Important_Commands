# Important Commands for Developers

This document provides a collection of essential commands for various development and system tasks.

## Python Development Utilities

### Managing Virtual Environments

**1. Create a Virtual Environment**
   - Command:
     ```bash
     python -m venv env
     ```
   - Explanation: Creates an isolated Python environment.
   - Note: `env` is the default name for the virtual environment directory. You can choose a different name.

**2. Activate the Virtual Environment**
   - On Windows:
     ```powershell
     .\env\Scripts\activate
     ```
   - On Linux/macOS:
     ```bash
     source env/bin/activate
     ```
   - Explanation: Activates the virtual environment in your current shell session.

**3. Deactivate the Virtual Environment**
   - Command (works on all platforms):
     ```bash
     deactivate
     ```
   - Explanation: Returns to the global Python environment.

**4. PowerShell Execution Policy (for Windows users)**
   - Issue: If you see an error like `env\Scripts\activate cannot be loaded because running scripts is disabled on this system` when trying to activate the virtual environment on Windows.
   - Explanation: This error occurs because the PowerShell execution policy on your system is preventing scripts from running.
   - Solution: To allow scripts for the current user, run the following command in PowerShell:
     ```powershell
     Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy Unrestricted
     ```
   - Note: This command changes your execution policy. Understand the security implications before running it.

### Managing Project Dependencies (`requirements.txt`)

**1. Install packages from `requirements.txt`**
   - Command:
     ```bash
     pip install -r requirements.txt
     ```
   - Explanation: Installs all the packages listed in the `requirements.txt` file into your active virtual environment.

**2. Create or update `requirements.txt`**
   - Command:
     ```bash
     pip freeze > requirements.txt
     ```
   - Explanation: Generates a list of all packages currently installed in your virtual environment and saves them to `requirements.txt`.
   - Best Practice: Keep your `requirements.txt` file updated. After installing new packages, regenerate the file.

## Git Version Control

A quick reference for common Git commands.

*   **`git clone <repository_url>`**
    *   Explanation: Downloads a copy of a remote repository to your local machine.
*   **`git status`**
    *   Explanation: Shows the current status of your repository, including changed and untracked files.
*   **`git add <file_name>`**
    *   Explanation: Stages a specific file for the next commit.
*   **`git add .`**
    *   Explanation: Stages all modified and new untracked files in the current directory and subdirectories.
*   **`git commit -m "Your commit message"`**
    *   Explanation: Records the staged changes to the repository with a descriptive message.
*   **`git push`**
    *   Explanation: Uploads your local committed changes to the remote repository.
*   **`git pull`**
    *   Explanation: Fetches changes from the remote repository and merges them into your current local branch.
*   **`git branch <branch_name>`**
    *   Explanation: Creates a new local branch.
*   **`git checkout <branch_name>`**
    *   Explanation: Switches your working directory to the specified branch.
*   **`git merge <branch_name>`**
    *   Explanation: Merges changes from the specified branch into your current branch.

## File System Navigation and Manipulation

Commands for interacting with the file system.

*   **List files and directories**
    *   Bash (Linux/macOS): `ls`
    *   Windows CMD/PowerShell: `dir`
    *   Explanation: Displays files and folders in the current directory.
*   **Change directory**
    *   Command (cross-platform): `cd <directory_path>`
    *   Explanation: Navigates to the specified directory. Use `cd ..` to go up one level.
*   **Create a new directory**
    *   Command (cross-platform, though `md` is also common on Windows): `mkdir <directory_name>`
    *   Explanation: Creates a new folder.
*   **Delete a file**
    *   Bash (Linux/macOS): `rm <file_name>`
    *   Windows CMD/PowerShell: `del <file_name>`
    *   Explanation: Removes the specified file. **Use with caution.**
*   **Copy a file**
    *   Bash (Linux/macOS): `cp <source_file> <destination_path_or_file>`
    *   Windows CMD/PowerShell: `copy <source_file> <destination_path_or_file>`
    *   Explanation: Copies a file.
*   **Move or rename a file**
    *   Bash (Linux/macOS): `mv <source> <destination>`
    *   Windows CMD/PowerShell: `move <source> <destination>`
    *   Explanation: Moves or renames a file or directory.

## Network Utilities

Tools for basic network diagnostics.

*   **`ping <hostname_or_ip>`**
    *   Explanation: Sends test packets to a network host to check connectivity and response time.
*   **Display network configuration**
    *   Windows: `ipconfig`
    *   Linux/macOS: `ifconfig` (older, may need install) or `ip addr` (newer, preferred on Linux)
    *   Explanation: Shows details about your network interfaces (IP address, MAC address, etc.).
    *   Note for Linux: `ip addr` is generally preferred over `ifconfig` on modern systems.

## Microsoft Office Activation (for specific versions)

**Disclaimer:** The following method for Microsoft Office activation may not be officially sanctioned by Microsoft and could have risks or limitations. Use it at your own discretion. Official activation methods are recommended.

**Instructions:**
1.  Open Command Prompt (cmd) as Administrator.
2.  Navigate to the Office installation directory. For Office 16, this is typically:
    ```cmd
    cd C:\Program Files\Microsoft Office\Office16
    ```
    If your installation path is different (e.g., `C:\Program Files (x86)\...`), adjust the path accordingly.
3.  Run the following commands one by one:
    ```cmd
    cscript ospp.vbs /sethst:kms.03k.org
    ```
    ```cmd
    cscript ospp.vbs /act
    ```
    - Explanation: These commands attempt to activate Office using a KMS (Key Management Service) server. The first sets the KMS server address, and the second attempts activation.
