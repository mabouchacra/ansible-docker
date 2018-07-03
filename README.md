[English](#english)  
[Français](#french)
# <a name="english"></a>Overview

**OS Requirement :** This procedure works for Ubuntu based OS (Ubuntu, Linux Mint)

**Purpose :** The purpose of this script is to install Docker CE via Ansible.

**What does it do really ? :** This repository consist of an ansible playbook that install Docker CE. It does the following steps :  
1. Installation of Docker (in fact it just follows [the official installation guide](https://docs.docker.com/install/linux/docker-ce/ubuntu/ "Installation guide"))
   * Install apt package to use a repository over HTTPS
   * Add Docker’s official GPG key
   * Add Docker's stable repository
   * Install Docker CE

## Prerequisites
* Python 2.7 ou 3 *(it should be installed automatically with Ansible)*
* Ansible (2.4+)

### Ansible installation
```
$ sudo apt-get update
$ sudo apt-get install software-properties-common
$ sudo apt-add-repository ppa:ansible/ansible
$ sudo apt-get update
$ sudo apt-get install ansible
```

## Usage

To install Docker via Ansible, you need to execute the following command :  
`$ ./install.sh`  

You need to type in the root password in order to install all the apt package and execute the commands that need super-user (**sudo**) privileges

## Optional post-installation steps

* Add user to docker group :  

After the installation is complete, Docker should be installed on your computer. However, in order to manipulate the docker daemon, you need to use super-user privilege (e.g : **sudo**). In order to use docker as a non-privileged user, you need to execute the following command :  
`$ sudo usermod -aG docker $USER`  
After that, the current user (**$USER**) will be added to the docker group and will be able to use docker commands directly.  
:warning: You need to logout/login for that change to be applied.

# <a name="french"></a>Objet

**OS Concernés :** Cette procédure fonctionne avec des OS basés sur Ubuntu (Ubuntu, Linux Mint)

**Objectif :** L'objectif de cette procédure est d'installer Docker CE via Ansible.

**Et en réalité, ça fait quoi ? :** La procédure est en réalité un playbook ansible *(d'où les pré-requis)* qui installe Docker CE. Ainsi le script suit les étapes suivantes :    
1. Installation de docker (on ne fait que suivre [la procédure officielle](https://docs.docker.com/install/linux/docker-ce/ubuntu/ "Procédure d'installation"))
   * Installation des packets apt requis
   * Ajout de la clé GPG officielle de Docker
   * Ajout du repo apt Docker
   * Installation de Docker

## Pré-requis
* Python 2.7 ou 3 *(installé automatiquement avec Ansible normalement)*
* Ansible (2.4+)

### Installation d'Ansible
```
$ sudo apt-get update
$ sudo apt-get install software-properties-common
$ sudo apt-add-repository ppa:ansible/ansible
$ sudo apt-get update
$ sudo apt-get install ansible
```

## Usage

Pour lancer la procédure d'installation, il suffit d'exécuter la commande suivante :  
`$ ./install.sh`  

Il faut renseigner le mot de passe root afin de faire l'installation de tous les packets apt nécessaire et d'éxecuter les commandes qui demandent les privilèges super-user (**sudo**).

## Etapes optionnelles supplémentaires

* Ajout de l'utilisateur dans le groupe Docker :  

Une fois l'installation terminée, Docker devrait être installé sur votre machine. Cependant, pour pouvoir manipuler le démon docker, vous devez avoir les droits super-utilisateur (e.g : **sudo**). Afin d'utiliser docker sans les droit super-utilisateur, vous devez éxecuter la commande suivante :  
`$ sudo usermod -aG docker $USER`  
Après ça, l'utilisateur courant (**$USER**) sera rajouté au groupe docker et pourra utiliser les commandes docker directement.  
:warning: Vous devez vous relogguer sur la session utilisateur pour que la modification soit prise en compte