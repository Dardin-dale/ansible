# Ansible Development Environment Setup

This repository contains Ansible playbooks and roles to set up a development environment on a new Ubuntu-based system or container.

## Overview

This Ansible setup includes the following main components:

1. Core system setup
2. Git configuration
3. Dotfiles management
4. Development tools installation

## Prerequisites

- Ubuntu-based system (tested on Ubuntu 20.04 and later)
- Ansible installed on the target system

## Usage

1. Clone this repository:
   ```
   git clone https://github.com/yourusername/ansible-dev-setup.git
   cd ansible-dev-setup
   ```

2. Update the `vars/sensitive` directory with your personal information:
   - Copy `git_config.yml.example` to `git_config.yml` and update with your Git information
   - Copy `ssh_keys.yml.example` to `ssh_keys.yml` and add your SSH keys
   - Set your dotfiles repository URL in `git_config.yml`

3. Run the Ansible playbook:
   ```
   ansible-playbook local.yml --ask-become-pass
   ```

## Components

### Core Setup

- Installs essential packages and tools
- Sets up Zsh as the default shell
- Configures SSH

### Git Setup

- Configures Git with your personal information
- Sets up global Git preferences

### Dotfiles

- Clones your dotfiles repository (specified in `git_config.yml`)
- Creates symlinks for your configuration files

### Development Tools

- Go
- Node.js (via NVM)
- Rust
- Docker
- Visual Studio Code
- Python (with virtual environment)

## Python Virtual Environment

This setup includes a Python virtual environment. Use the following alias to activate it:

```bash
activate_python
```

## Customization

You can customize the setup by modifying the roles and tasks in the `roles` and `tasks` directories. The dotfiles repository URL can be changed in `vars/sensitive/git_config.yml`.

## Testing

To test the setup in a Docker container:

1. Build the test Docker container:
   ```
   sh build-docker
   ```

2. Run the Docker container:
   ```
   docker run --rm -it nvim-computer bash
   ```

3. Inside the container, run the Ansible playbook:
   ```
   ansible-playbook local.yml --ask-become-pass
   ```

## Contributing

Feel free to submit issues or pull requests if you have suggestions for improvements or encounter any problems.

## License

[MIT License](LICENSE)
