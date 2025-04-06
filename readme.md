# Vagrant Tutorial

This repository is a collection of various Vagrant files along with a comprehensive tutorial to help you get started with Vagrant. Whether you’re a beginner or an experienced developer, this guide will walk you through the basics and beyond.

---

## Table of Contents

1. [Introduction](#introduction)
2. [What is Vagrant?](#what-is-vagrant)
3. [How to Get Started](#how-to-get-started)
4. [Installation](#installation)
5. [Vagrant Command Cheatsheet](#vagrant-command-cheatsheet)
    - [Basic Commands](#basic-commands)
    - [Provisioning & Configuration](#provisioning--configuration)
    - [Cloud Provisioners](#cloud-provisioners)
6. [Example Vagrantfiles](#example-vagrantfiles)
7. [Additional Resources and Links](#additional-resources-and-links)

---

## Introduction

Vagrant is a powerful tool built by Hashicorp for automating the configuration, provisioning, and management of virtual machines. It simplifies the process of setting up and sharing development environments, ensuring consistency across different systems and teams. This guide covers everything from installation to advanced cloud provisioning techniques.

---

## What is Vagrant?

Vagrant is an open-source tool that enables you to build and manage virtualized development environments. With Vagrant, you can:

- **Define OS requirements:** Specify the operating system and version.
- **Install tools and apps:** Automatically set up the necessary software.
- **Configure servers:** Set up servers and networking.
- **Run commands:** Execute scripts and commands during provisioning.
- **Port Forwarding:** Configure ports for external access.

Vagrant uses a simple file called the **Vagrantfile** to describe the configuration of the virtual environment, making it easy to replicate the same setup on multiple machines.

---

## How to Get Started

### Step 1: Install Vagrant

1. **Download Vagrant:**  
   Visit the [official Vagrant website](https://www.vagrantup.com/downloads) to download and install Vagrant for your operating system.

2. **Install a Provider:**  
   While VirtualBox is the most common provider, Vagrant also supports others like VMware, Hyper-V, and Docker. Choose the one that suits your needs.

### Step 2: Verify the Installation

Open your terminal (or Command Prompt) and type:

`vagrant`

If you see an output similar to the following, your installation has been successful:

```sh
Usage: vagrant [options] <command> [<args>]

    -h, --help                       Print this help.

Common commands:
     autocomplete    Manages autocomplete installation on host
     box             Manages boxes: installation, removal, etc.
     cloud           Manages everything related to Vagrant Cloud
     destroy         Stops and deletes all traces of the Vagrant machine
     global-status   Outputs status of Vagrant environments for this user
     halt            Stops the Vagrant machine
     help            Shows the help for a subcommand
     init            Initializes a new Vagrant environment by creating a Vagrantfile
     login           Login to Vagrant Cloud
     package         Packages a running Vagrant environment into a box
     plugin          Manages plugins: install, uninstall, update, etc.
     port            Displays information about guest port mappings
     powershell      Connects to machine via PowerShell remoting
     provision       Provisions the Vagrant machine
     push            Deploys code in this environment to a configured destination
     rdp             Connects to machine via RDP
     reload          Restarts Vagrant machine, loads new Vagrantfile configuration
     resume          Resumes a suspended Vagrant machine
     serve           Starts Vagrant server
     snapshot        Manages snapshots: saving, restoring, etc.
     ssh             Connects to machine via SSH
     ssh-config      Outputs OpenSSH valid configuration to connect to the machine
     status          Outputs status of the Vagrant machine
     suspend         Suspends the machine
     up              Starts and provisions the Vagrant environment
     upload          Uploads to machine via communicator
     validate        Validates the Vagrantfile
     version         Prints current and latest Vagrant version
     winrm           Executes commands on a machine via WinRM
     winrm-config    Outputs WinRM configuration to connect to the machine

For help on any individual command run:
vagrant COMMAND -h
``` 

As you can see, the CLI already comes with a list of all commands that you can run.
---


### Cloud Provisioners

Vagrant is not just for local VMs; it can also provision cloud environments using plugins and providers such as:

- **AWS (Amazon Web Services):**  
  Use plugins like [vagrant-aws](https://github.com/mitchellh/vagrant-aws) to launch and manage EC2 instances.
  
- **Azure:**  
  Provision Azure VMs using plugins like [vagrant-azure](https://github.com/Azure/vagrant-azure).

- **DigitalOcean:**  
  Provision DigitalOcean droplets with the [vagrant-digitalocean](https://github.com/smdahlen/vagrant-digitalocean) plugin.

- **Google Cloud Platform (GCP):**  
  Use community plugins to integrate GCP provisioning.

Each cloud provider typically requires you to configure credentials, specify regions, and define instance types within your Vagrantfile. Detailed setup instructions are available in the respective plugin documentation.

---


## Vagrant Command Cheatsheet

Below is a categorized list of the most commonly used Vagrant commands.

### Basic Commands

- **`vagrant init`**  
  Initializes a new Vagrant environment by creating a default Vagrantfile.

- **`vagrant up`**  
  Starts and provisions the Vagrant environment.

- **`vagrant halt`**  
  Stops the Vagrant machine.

- **`vagrant destroy`**  
  Stops and deletes all traces of the Vagrant machine.

- **`vagrant status`**  
  Displays the current status of the Vagrant machine.

- **`vagrant reload`**  
  Restarts the machine and applies any changes in the Vagrantfile.

- **`vagrant suspend`**  
  Suspends the current machine state.

- **`vagrant resume`**  
  Resumes a suspended machine.

- **`vagrant snapshot`**  
  Manages snapshots for saving and restoring machine states:
  - `vagrant snapshot save <name>`
  - `vagrant snapshot restore <name>`
  - `vagrant snapshot list`

### Provisioning & Configuration

- **`vagrant provision`**  
  Manually runs the provisioners defined in the Vagrantfile.

- **`vagrant validate`**  
  Validates the Vagrantfile for syntax errors.

- **`vagrant ssh`**  
  Connects to the virtual machine via SSH.

- **`vagrant ssh-config`**  
  Outputs the OpenSSH configuration needed to connect to the virtual machine.

- **`vagrant box`**  
  Manages Vagrant boxes (images):
  - `vagrant box add <box-name>`
  - `vagrant box list`
  - `vagrant box remove <box-name>`

- **`vagrant plugin`**  
  Manages Vagrant plugins:
  - `vagrant plugin install <plugin-name>`
  - `vagrant plugin uninstall <plugin-name>`
  - `vagrant plugin list`




## Example Vagrantfiles

Here are a few example Vagrantfile snippets to help you get started:

1. [Basic - ubuntu 22](/examples/basic-ubuntu)  
2. [AWS provisioning](/examples/aws-plugin-vagrantfile)  
3. [Azure provisioning](/examples/azure-vagrant-file)  
4. [Multi-VM setup](/examples/multiple-vm-same-os)  
5. [Full stack (frontend, backend, db)](/examples/multiple-component-vm)  
6. [Load balancing setup](/examples/lb-ha-proxy-vagrantfile)  
7. [High availability servers](/examples/keepalive-nginx-high-availability)


Ensure that you save the particular file you need as the singular vagrantfile in your folder.

---

## Additional Resources and Links

1. [Official Documentation](https://developer.hashicorp.com/vagrant/docs)
2. [Install Vagrant](https://developer.hashicorp.com/vagrant/install)
3. [Youtube References](https://www.youtube.com/playlist?list=PLhW3qG5bs-L9S272lwi9encQOL9nMOnRa)




Thank you for reading. If you have any doubts or issues or have found some inconsistencies or incorrect information in this repository, I encourage you to add it to the "issues" of this repository.
