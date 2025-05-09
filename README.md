## 🚀 WordPress Deployment with Ansible (RedHat-based Systems)

This project automates the deployment of a complete WordPress environment using Ansible on RedHat-based Linux systems (such as CentOS or RHEL). It installs and configures MariaDB, Apache, PHP, and WordPress seamlessly without any manual intervention.

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

- 🔒 Secure MariaDB installation with root password setup

- 🧰 Automatic installation of Apache, PHP, and WordPress

- 🧱 Modular Ansible roles for better organization and reusability

- 🧑‍💻 Custom database and user creation for WordPress

- ✅ OS-specific logic (supports Red Hat-based systems only)

- 📦 Handles Ansible collection dependencies

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

> This will automatically install dependencies, create the database, set up WordPress, and configure Apache.

## 📦 Prerequisites
Ensure the following are installed on your control node (your local machine):

- Ansible 2.10+
- Python 3 + pip
- PyMySQL (required by community.mysql collection):


## 📚 Required Ansible Collection
This project uses:

- community.mysql

Install it with:
```bash
ansible-galaxy collection install community.mysql
```
To install it manually (if needed):

## **👤 Author:**

Sherif Shaban
Feel free to fork and contribute!# ansible-wordpress-auto-deploy
# ansible-wordpress-deploy
