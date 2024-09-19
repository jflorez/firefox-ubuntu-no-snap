# Ubuntu Automation with Vagrant and Ansible

This project is designed to simplify the setup of an Ubuntu virtual machine by using Vagrant and Ansible. Vagrant is a tool for building and managing virtual machine environments, while Ansible is an automation tool that handles software provisioning and configuration management.

The main goal of this project is to automatically install and configure essential software and tools needed for web automation tasks on the virtual machine. This includes setting up development environments with popular applications like Visual Studio Code (VS Code), Firefox, and Google Chrome. Additionally, the Ansible playbook ensures that all necessary dependencies and configurations are in place for smooth automation workflows.

The Vagrant configuration in this project uses only VirtualBox as a provider, ensuring compatibility and ease of use. For those who prefer not to use Vagrant or VirtualBox, the Ansible playbook can also be run manually on an existing Ubuntu 22.04 or 24.04 VM to achieve the same setup.

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

### JDK 21

- Installs JDK 21 and other pre-requisite packages.

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


