# Ghost Server Setup with Ansible

This repository contains an Ansible playbook for automatic setup of a Ghost server on an Ubuntu system.

## Prerequisites

To use this playbook, you need to have the following installed and configured:

- A server or a Virtual Private Server (VPS) with Ubuntu.
- Ansible on your local machine or control machine.

## Getting Started

1. Clone this repository to your local machine or control machine:

git clone https://github.com/f0rk-b0mb/ansible-ghost-server
cd ghost-ansible

2. Customize the variables in the `vars/main.yml` file according to your needs.

---
# System
ssh_port: 2222
ufw_rules:
  - { rule: allow, name: 'Nginx Full' }
  - { rule: allow, name: '{{ ssh_port }}/tcp' }

# MySQL
mysql_root_password: your_mysql_root_password
ghost_db: ghost
ghost_db_user: ghost_user
ghost_db_password: ghost_password
ghost_user: ghost
ghost_path: /var/www/ghost

# Ghost
domain: your_domain
email: your_email

# Bashrc
user: your_user


Replace the placeholders (e.g., `your_mysql_root_password`, `your_domain`, `your_email`, and `your_user`) with the actual values you want to use.

**Note:** Please handle the `vars/main.yml` file with caution as it contains sensitive information such as passwords. We recommend using Ansible Vault or a similar system for the security of your data.

3. Run the playbook on your server:

ansible-playbook -i your_server_ip, main.yml

Replace `your_server_ip` with the IP address of your server.

## Contribution

Contributions are always welcome! Please read the CONTRIBUTING.md before making a contribution.

## License

This project is licensed under the MIT License. For more information, see the `LICENSE` file.


###################### GERMAN VERSION - DEUTSCHE VERSION ######################

# Ghost Server Setup mit Ansible

Dieses Repository enthält ein Ansible Playbook, das zur automatischen Einrichtung eines Ghost Servers auf einem Ubuntu-System verwendet werden kann.

## Voraussetzungen

Um dieses Playbook zu verwenden, müssen Sie folgendes installiert und konfiguriert haben:

- Ein Server oder ein virtueller privater Server (VPS) mit Ubuntu.
- Ansible auf Ihrem lokalen Rechner oder einer Steuerungsmaschine.

## Erste Schritte

1. Klone dieses Repository auf Ihren lokalen Rechner oder Ihre Steuerungsmaschine:


git clone https://github.com/f0rk-b0mb/ansible-ghost-server
cd ghost-ansible


2. Passen Sie die Variablen in der `vars/main.yml` Datei nach Ihren Bedürfnissen an. 


---
# System
ssh_port: 2222
ufw_rules:
  - { rule: allow, name: 'Nginx Full' }
  - { rule: allow, name: '{{ ssh_port }}/tcp' }

# MySQL
mysql_root_password: your_mysql_root_password
ghost_db: ghost
ghost_db_user: ghost_user
ghost_db_password: ghost_password
ghost_user: ghost
ghost_path: /var/www/ghost

# Ghost
domain: your_domain
email: your_email

# Bashrc
user: your_user


Ersetzen Sie die Platzhalter (z.B. `your_mysql_root_password`, `your_domain`, `your_email` und `your_user`) durch die tatsächlichen Werte, die Sie verwenden möchten.

**Hinweis:** Bitte behandeln Sie die `vars/main.yml` Datei mit Vorsicht, da sie sensible Informationen wie Passwörter enthält. Wir empfehlen Ihnen, für die Sicherheit Ihrer Daten Ansible Vault oder ein ähnliches System zu verwenden.

3. Führen Sie das Playbook auf Ihrem Server aus:

ansible-playbook -i your_server_ip, main.yml

Ersetzen Sie `your_server_ip` durch die IP-Adresse Ihres Servers.

## Beitrag

Beiträge sind immer willkommen! Bitte lesen Sie die CONTRIBUTING.md, bevor Sie einen Beitrag leisten.

## Lizenz

Dieses Projekt steht unter der MIT-Lizenz. Weitere Informationen finden Sie in der `LICENSE` Datei.
