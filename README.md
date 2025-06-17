# Ansible Minecraft Server Role

This Ansible role automates the deployment and configuration of a Minecraft server on Rocky Linux 9 / AlmaLinux 9. The role handles all aspects of the server setup, including security, backups, and system configuration.

## Requirements

- Rocky Linux 9 or AlmaLinux 9
- Ansible 2.9 or higher
- Root or sudo access
- SSH access with key-based authentication

## Role Variables

All configurable variables are defined in `roles/minecraft_server/defaults/main.yml`. Here are the main categories of variables:

### Minecraft Server Configuration
- `minecraft_version`: Minecraft server version
- `minecraft_server_dir`: Installation directory
- `minecraft_memory_min`: Minimum memory allocation
- `minecraft_memory_max`: Maximum memory allocation
- `minecraft_port`: Server port (default: 25565)

### Server Settings
- `minecraft_server_properties`: Dictionary of server.properties settings
  - difficulty
  - gamemode
  - max-players
  - view-distance
  - motd
  - and more...

### System Configuration
- `system_timezone`: System timezone
- `system_locale`: System locale

### Security Settings
- `security_ssh_port`: SSH port
- `security_ssh_permit_root_login`: Root login permission
- `security_ssh_password_authentication`: Password authentication setting

### Backup Configuration
- `backup_enabled`: Enable/disable automatic backups
- `backup_schedule`: Cron schedule for backups
- `backup_retention_days`: Number of days to keep backups

## Usage

1. Clone this repository
2. Create an inventory file with your server details
3. Create a playbook or use the provided `site.yml`
4. Customize variables as needed
5. Run the playbook:

```bash
ansible-playbook -i inventory.ini site.yml
```

## Features

- Automatic server installation and configuration
- System hardening and security measures
- Automated backups with retention policy
- Firewall configuration
- Systemd service management
- Java installation and configuration
- User and permission management

## Security Features

- Firewall configuration (only necessary ports open)
- Non-root user for Minecraft server
- SSH security hardening
- Automatic updates
- Regular backups

## Backup System

The role includes an automated backup system that:
- Creates daily backups
- Compresses backups
- Implements retention policy
- Stores backups in a dedicated directory


## Author Information

Created by Santi Vermeulen

