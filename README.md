# User-friendly script to change permissions 

## Description

The script allows for **9-charachter-symbolic** (e.g., `rwxr-xr-x`), **extended symbolic** (`u=rwx,g=r-x,o=r-x`), **octal permissions** (`755`), `--group | -g` argument, `-o | --owner` argument for single files, folders (and optionally with `--recursive`, but user will be prompted unless `--noconfirm` is supplied) and allows for `--dry-runs` if you want to check what the current operation will do without applying it. If run with no arguments other than path, the script will simply show the current permissions, owner, group and other relevant info for that directory or file.

**changePermissions** is a command-line utility for managing file and directory ownership and permissions on Linux systems. It simplifies and streamlines operations like `chown` and `chmod` by combining them with flexible options and user-friendly feedback, plus some additional functionality.

## Features

- Change ownership (`-o`) and group (`-g`) independently or together.
- Set permissions using:
  - **Numeric format:** e.g., `755`
  - **9-character symbolic format:** e.g., `rwxr-xr-x`
  - **Extended symbolic format:** e.g., `u=rwx,g=rx,o=rx`
- Recursive operations with confirmation (`-R`).
- Automatic `sudo` detection and prompts when elevated permissions are required.
- Flexible argument parsing with support for `--target` (`-t`) as an alternative to positional paths.
- Clear, detailed output for current and updated permissions.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Epineph/change_permissions_scripts.git
   ```

## Usage

```bash
changePermissions [PATH] [OPTIONS]...

First sudo chmod +x "$(pwd)"/changePermissions

# Examples - run the examplles below with ./changePermissions or place it so found on $PATH and simply call it be name:

# Show current ownership and permissions:
changePermissions ~/example/file.txt

# Specify target with --target:
changePermissions -t ~/example/file.txt

# Recursively change ownership to 'user', group to 'root', and permissions to 755:
sudo changePermissions -t ~/example/dir -o user -g root -p 755 -R

# Change permissions using symbolic format:
sudo changePermissions -t ~/example/file.txt -p u=rwx,g=rx,o=rx

# Only show current permissions:
changePermissions ~/example/file.txt --active-perms
```

# Example

- Show current ownership and permissions:

```bash
changePermissions [PATH] [OPTIONS]...
```
# Examples:

# Show current ownership and permissions:
```bash
changePermissions ~/example/file.txt
```
# Specify target with --target:
```bash
changePermissions -t ~/example/file.txt
```
# Recursively change ownership to 'user', group to 'root', and permissions to 755:
```bash
sudo changePermissions -t ~/example/dir -o user -g root -p 755 -R
```
# Change permissions using symbolic format:
```bash
sudo changePermissions -t ~/example/file.txt -p u=rwx,g=rx,o=rx
```
# Only show current permissions:
```bash
changePermissions ~/example/file.txt --active-perms
```
Options
Option	Description
PATH	The file or directory to act upon (positional argument).
-t, --target <DIR>	Specify the target path as an option (alternative to positional PATH).
-R, --recursive	Apply changes recursively, with confirmation unless --noconfirm is used.
-o, --owner <USER>	Change owner to <USER>. Use <USER>:<GROUP> to set both simultaneously.
-g, --group <GROUP>	Change group to <GROUP>.
-p, --perm <PERMS>	Set permissions in numeric, symbolic, or extended symbolic format.
-c, --current-owner	Show current ownership (user and group).
-a, --active-perms	Show current permissions (numeric and symbolic).
--noconfirm	Skip confirmation prompts.
--version	Display version information.
--help	Display this help text.




Example Markdown Table:

| Option              | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| `PATH`              | The file or directory to act upon (positional argument).                   |
| `-t, --target <DIR>`| Specify the target path as an option (alternative to positional `PATH`).    |
| `-R, --recursive`   | Apply changes recursively, with confirmation unless `--noconfirm` is used. |
| `-o, --owner <USER>`| Change owner to `<USER>`. Use `<USER>:<GROUP>` to set both simultaneously.  |
| `-g, --group <GROUP>`| Change group to `<GROUP>`.                                                |
| `-p, --perm <PERMS>`| Set permissions in numeric, symbolic, or extended symbolic format.          |
| `-c, --current-owner`| Show current ownership (user and group).                                  |
| `-a, --active-perms` | Show current permissions (numeric and symbolic).                          |
| `--noconfirm`       | Skip confirmation prompts.                                                 |
| `--version`         | Display version information.                                               |
| `--help`        
| `--dry-run`        | No changes made, but simulates changes showing what changes would be made  |






