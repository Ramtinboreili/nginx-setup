# nginx-setup

This project is a simple Ansible playbook to install and configure Nginx on Linux servers.  
It allows you to automatically and consistently deploy an Nginx web server across multiple hosts.

## 📦 Prerequisites

- Ansible installed on your control node
- SSH access to target servers with `sudo` privileges
- A configured `inventory` file listing your target hosts

## ⚙️ Usage

1. Clone the repository:

   ```bash
   git clone https://github.com/Ramtinboreili/nginx-setup.git
   cd nginx-setup
   ```

2. Edit the `inventory` file to define your target servers.

3. Review and modify `ansible.cfg` if needed.

4. Run the playbook:

   ```bash
   ansible-playbook -i inventory setup-nginx.yml
   ```

## 🗂 Project Structure

```
nginx-setup/
├── ansible.cfg           # Ansible configuration file
├── inventory             # Target servers inventory
├── setup-nginx.yml       # Main playbook to install Nginx
├── roles/
│   └── nginx/            # Nginx role
│       ├── tasks/
│       │   └── main.yml  # Main tasks for setup and configuration
│       └── templates/
│           └── nginx.conf.j2  # Nginx config template (Jinja2)
└── .vault.pass           # Ansible Vault password file (if used)
```

## 🔐 Security Notes

- If you store sensitive data (e.g. passwords, secrets), use Ansible Vault to encrypt them.
- Never commit `.vault.pass` to public repositories — make sure it's listed in `.gitignore`.

## 📄 License

This project is licensed under the MIT License. See the `LICENSE` file for more details.
