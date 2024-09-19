# Ubuntu Automation with Vagrant and Ansible

Welcome to the Ubuntu Web Automation project! This repository aims to simplify the setup of an Ubuntu virtual machine using Vagrant and Ansible. Vagrant is a tool for building and managing virtual machine environments, while Ansible is an automation tool that handles software provisioning and configuration management.

## Table of Contents

- [About the Project](#about-the-project)
- [Prerequisites](#prerequisites)
- [Getting Started with Vagrant](#getting-started-with-vagrant)
  - [Clone the Repository](#clone-the-repository)
  - [Start the Vagrant VM](#start-the-vagrant-vm)
  - [Login through the Ubuntu GUI](#login-through-the-ubuntu-gui)
- [Getting Started with Playbook on an existing Ubuntu VM](#getting-started-with-playbook-on-an-existing-ubuntu-vm)
  - [Install Ansible and Git](#install-ansible-and-git)
  - [Clone the repository](#clone-the-repository-1)
  - [Run the playbook](#run-the-playbook)
- [Provisioning Details](#provisioning-details)
  - [JDK 21](#jdk-21)
  - [VS Code](#vs-code)
  - [Firefox](#firefox)
  - [Google Chrome](#google-chrome)
- [Vagrant Configuration](#vagrant-configuration)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## About the Project

This project is designed to automatically install and configure essential software and tools needed for web automation tasks on an Ubuntu virtual machine. It sets up development environments with popular applications like Visual Studio Code (VS Code), Firefox, and Google Chrome. Additionally, the Ansible playbook ensures that all necessary dependencies and configurations are in place for smooth automation workflows.

The Vagrant configuration in this project uses VirtualBox as a provider, ensuring compatibility and ease of use. For those who prefer not to use Vagrant or VirtualBox, the Ansible playbook can also be run manually on an existing Ubuntu 22.04 or 24.04 VM to achieve the same setup.

## Prerequisites

- Vagrant
- VirtualBox

## Getting Started with Vagrant

To get a local copy up and running, follow these simple steps.

### Clone the Repository
   ```sh
   git clone <repository-url>
   cd <repository-directory>
   ```

### Start the Vagrant VM
   ```sh
   vagrant up
   ```

### Login through the Ubuntu GUI
   After the `vagrant up` command completes, the VM will start in GUI mode. You can log in through the Ubuntu graphical user interface.

## Getting Started with Playbook on an existing Ubuntu VM

If you prefer to run the playbook inside an Ubuntu 22.04 or 24.04 VM without using Vagrant, follow these steps:

### Install Ansible and Git
   ```sh
   sudo apt update
   sudo apt install -y ansible git
   ```

### Clone the repository
   ```sh
   git clone <repository-url>
   cd <repository-directory>
   ```

### Run the playbook
   ```sh
   ansible-playbook ubuntu-automation-playbook.yaml
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

- **Base Box:** `gusztavvargadr/ubuntu-desktop-2204-lts`
- **Memory:** 4096 MB
- **CPUs:** 2
- **Provisioner:** Ansible (local)



## License

Distributed under the MIT License. See `LICENSE` for more information.

## Acknowledgments

- [Vagrant](https://www.vagrantup.com/)
- [VirtualBox](https://www.virtualbox.org/)
- [Ansible](https://www.ansible.com/)

