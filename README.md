# vagrant-web-provisioning 🚀

A fully automated web server provisioning setup using Vagrant and VirtualBox.
No manual configuration — just `vagrant up` and your site is live.

## 📌 Project Overview

This project automates the complete setup of an Apache web server on Ubuntu 22.04,
including package installation, service configuration, website deployment, and cleanup.
Built to demonstrate Infrastructure as Code (IaC) principles using Vagrant shell provisioning.

## 🛠 Stack

| Tool                 | Purpose                    |
|----------------------|----------------------------|
| Vagrant              | VM lifecycle management    |
| VirtualBox           | Hypervisor / VM provider   |
| Ubuntu 22.04 (Jammy) | Guest OS                   |
| Apache2              | Web server                 |
| Shell                | Provisioning / automation  |

## ⚙️ Prerequisites

Make sure you have these installed on your host machine:

- [Vagrant](https://www.vagrantup.com/downloads) `>= 2.x`
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads) `>= 6.x`

## 🚀 Getting Started

```bash
git clone <your-repo-url>
cd vagrant-web-provisioning
vagrant up
```

That's it. Vagrant will:
1. Download the Ubuntu 22.04 box (first time only)
2. Create and configure the VM (1024MB RAM, private network)
3. Install Apache, wget, unzip, vim
4. Deploy the website to `/var/www/html`
5. Start and enable Apache on boot
6. Clean up all temp files

## 🌐 Access the Site

Once provisioning completes, open your browser:

```
http://192.168.33.28
```

## 📁 Project Structure

```
.
├── Vagrantfile   # All VM config and provisioning logic
└── README.md
```

## 🔧 VM Configuration

| Setting  | Value                   |
|----------|-------------------------|
| Box      | ubuntu/jammy64          |
| RAM      | 1024 MB                 |
| Network  | Private — 192.168.33.28 |
| Provider | VirtualBox              |

## 📦 What Gets Provisioned

- Apache2 installed, started, and enabled on boot
- Website template downloaded from [Tooplate](https://www.tooplate.com) and deployed to `/var/www/html`
- Temp files cleaned up automatically after deployment

## 🗑 Tear Down

```bash
vagrant halt      # stop the VM
vagrant destroy   # delete the VM completely
```

## 💡 What I Learned

- Vagrant provisioning with inline shell scripts
- Apache web server setup and service management on Linux
- Private networking in VirtualBox
- Infrastructure as Code fundamentals

## 📄 License

MIT
