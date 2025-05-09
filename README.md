## 🚀 WordPress Deployment with Ansible (RedHat-based Systems)

This project automates the deployment of a full WordPress stack using Ansible on Red Hat-based Linux systems (such as CentOS or RHEL). It installs and configures MariaDB, Apache, PHP, and WordPress with minimal manual intervention, following Infrastructure-as-Code best practices.

## 📦 Project Structure

```
mywordpress_ansible/
├── group_vars/
│   └── all.yaml
├── inventory
├── mywebsite.yaml
├── roles/
│   ├── apache/
│   │   └── tasks/
│   │       └── main.yaml
│   ├── mariadb/
│   │   └── tasks/
│   │       └── main.yaml
│   └── php/
│       └── tasks/
│           └── main.yaml
└── README.md
```

## ⚙️ Features

- 🔒 Secures MariaDB root access and automates database/user creation for WordPress

- ⚙️ Installs and configures Apache, PHP, and WordPress automatically

- 🧱 Uses modular Ansible roles for clean structure and easy maintenance

- 🔁 Supports changing Apache’s listening port (default changed to 88)

- 🔐 Configures SELinux and firewalld to allow the new custom port

- 📦 Handles Ansible collection dependencies

- 🧑‍💻 Designed for Red Hat-based distributions only

## 🚀 How to Use

### 1. Clone the Repository

```bash
git clone https://github.com/mariam0o0/wordpress_ansible.git
cd wordpress_ansible
```

### 2. Configure Inventory and Variables

- Edit `inventory.ini` to define your target server under `[webservers]`.
- Update `group_vars/all.yaml` with your own database credentials:

### 3. Run the Playbook

```bash
ansible-playbook -i inventory.ini mywebsite.yaml
```

> This will

- Install all dependencies (Apache, PHP, MariaDB)

- Secure MariaDB and create WordPress DB/user

- Download and configure WordPress

- Change Apache port to 88

- Update SELinux rules and open port 88 on the firewall

- Start all services

Make sure to access your WordPress site via:
```
http://<your-server-ip>:88
```
## 📦 Prerequisites
Ensure the following are installed on your control node (your local machine):

- Ansible 2.10+
- Python 3 + pip
- PyMySQL (required by community.mysql collection):


## 📚 Required Ansible Collection
This project uses:

- community.mysql
- posix (for firewalld and semanage tasks)

Install it with:
```bash
ansible-galaxy collection install community.mysql
ansible-galaxy collection install ansible.posix
```

## **👤 Author:**

Sherif Shaban
