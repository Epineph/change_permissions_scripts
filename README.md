# change_permissions_scripts

# chPerms

**chPerms** is a command-line utility for managing file and directory ownership and permissions on Linux systems. It simplifies and streamlines operations like `chown` and `chmod` by combining them with flexible options and user-friendly feedback.

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
   git clone https://github.com/<YourGitHubUsername>/chPerms5.git
   ```

## Usage

```bash
chPerms5 [PATH] [OPTIONS]...

# Examples:

# Show current ownership and permissions:
chPerms5 ~/example/file.txt

# Specify target with --target:
chPerms5 -t ~/example/file.txt

# Recursively change ownership to 'user', group to 'root', and permissions to 755:
sudo chPerms5 -t ~/example/dir -o user -g root -p 755 -R

# Change permissions using symbolic format:
sudo chPerms5 -t ~/example/file.txt -p u=rwx,g=rx,o=rx

# Only show current permissions:
chPerms5 ~/example/file.txt --active-perms
```

# Example

- Show current ownership and permissions:

```bash
chPerms5 [PATH] [OPTIONS]...
```
# Examples:

# Show current ownership and permissions:
```bash
chPerms5 ~/example/file.txt
```
# Specify target with --target:
```bash
chPerms5 -t ~/example/file.txt
```
# Recursively change ownership to 'user', group to 'root', and permissions to 755:
```bash
sudo chPerms5 -t ~/example/dir -o user -g root -p 755 -R
```
# Change permissions using symbolic format:
```bash
sudo chPerms5 -t ~/example/file.txt -p u=rwx,g=rx,o=rx
```
# Only show current permissions:
```bash
chPerms5 ~/example/file.txt --active-perms
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
| `--help`            | Display this help text.                                                   |






