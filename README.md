# vagrant-web-provisioning 🚀

Automatically sets up an Apache web server and deploys a website with a single command — no manual configuration needed.

---

## Step 1 — Download and Install Vagrant

Go to [https://www.vagrantup.com/downloads](https://www.vagrantup.com/downloads) and install it for your OS.

Verify it works:
```bash
vagrant --version
```

---

## Step 2 — Download and Install VirtualBox

Go to [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads) and install it for your OS.

---

## Step 3 — Clone this Repo

```bash
git clone https://github.com/<your-username>/vagrant-web-provisioning.git
cd vagrant-web-provisioning
```

> Make sure [Git](https://git-scm.com/downloads) is installed if you don't have it.

---

## Step 4 — (Optional) Edit the Vagrantfile

Open the `Vagrantfile` in any text editor before running.

**Change the private IP** (if `192.168.33.28` conflicts with your network):
```ruby
config.vm.network "private_network", ip: "192.168.33.28"  # edit this
```

**Change the website template** (find free templates at [tooplate.com](https://www.tooplate.com)):
```ruby
wget https://www.tooplate.com/zip-templates/2153_fireworks_composer.zip  # replace URL
unzip -o 2153_fireworks_composer.zip                                      # update filename
cp -r 2153_fireworks_composer/* /var/www/html                             # update folder name
```

Save the file after making changes.

---

## Step 5 — Open a Terminal in the Project Folder and Run

```bash
vagrant up
```

Vagrant will:
- Download Ubuntu 22.04 (first time only, may take a few minutes)
- Create and boot the VM
- Install Apache automatically
- Deploy the website
- Clean up temp files

---

## Step 6 — View the Site

Open your browser and go to:

```
http://192.168.33.28
```

(Use whatever IP you set in the Vagrantfile if you changed it)

---

## Useful Commands

| Command         | What it does              |
|-----------------|---------------------------|
| `vagrant up`    | Start and provision the VM |
| `vagrant halt`  | Shut down the VM          |
| `vagrant reload`| Restart the VM            |
| `vagrant destroy` | Delete the VM completely |
| `vagrant ssh`   | SSH into the VM           |

---

## License

MIT
