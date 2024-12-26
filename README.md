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
