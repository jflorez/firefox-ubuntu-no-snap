# Ubuntu Automation with Vagrant and Ansible

This project automates the setup of an Ubuntu virtual machine using Vagrant and Ansible. It provisions the VM with essential software like VS Code, Firefox, and Google Chrome.

## Prerequisites

- Vagrant
- VirtualBox

## Getting Started

1. **Clone the repository:**
   ```sh
   git clone <repository-url>
   cd <repository-directory>
   ```

2. **Start the Vagrant VM:**
   ```sh
   vagrant up
   ```

3. **SSH into the VM:**
   ```sh
   vagrant ssh
   ```

## Provisioning Details

The provisioning is handled by Ansible (local) through the `ubuntu-automation-playbook.yaml` playbook. Below are the key tasks performed:

### VS Code

- Removes any existing VS Code installation.
- Downloads and imports the Microsoft GPG key.
- Adds the VS Code repository.
- Installs VS Code.

### Firefox

- Removes any existing Firefox Snap installation.
- Adds the Mozilla Team PPA.
- Configures preferences to prioritize the PPA over Snap.
- Installs Firefox from the Mozilla Team PPA.
- Configures Firefox for unattended upgrades.

### Google Chrome

- Installs Google Chrome from the official Google repository.

## Vagrant Configuration

The `Vagrantfile` configures the VM with the following settings:

- **Base Box:** `ubuntu/bionic64`
- **Memory:** 8192 MB
- **CPUs:** 2
- **Provisioner:** Ansible (local)

## Running the Playbook Manually

If you prefer to run the playbook inside an Ubuntu 22.04 or 24.04 VM without using Vagrant, follow these steps:

1. **Install Ansible and Git:**
   ```sh
   sudo apt update
   sudo apt install -y ansible git
   ```

2. **Clone the repository:**
   ```sh
   git clone <repository-url>
   cd <repository-directory>
   ```

3. **Run the playbook:**
   ```sh
   ansible-playbook ubuntu-automation-playbook.yaml
   ```

## Contributing

Feel free to submit issues or pull requests if you have any improvements or bug fixes.

## License

This project is licensed under the MIT License.

## Acknowledgments

- [Vagrant](https://www.vagrantup.com/)
- [VirtualBox](https://www.virtualbox.org/)
- [Ansible](https://www.ansible.com/)


