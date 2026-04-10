# README.md



### Sommaire
1. [Description du projet](#1-description-du-projet)
2. [Intro](#2-intro)
3. [Logiciels utilisées](#3-logiciels-utilisées)
- 3.1 [Machines Virtuelles](#31-machines-virtuelles)
- 3.2 [Outils utilisés](#32-outils-utilisés)
4. [Fonctionnalités du script](#4-fonctionnalites-du-script)
  - 4.1 [Gestions des machines](#41-gestions-des-machines)
  - 4.2 [Gestion des utilisateurs](#42-gestion-des-utilisateurs)
## 1. Description du projet

Cet outil d'administration centralisée permet de gérer des utilisateurs et des machines Linux à distance via un Script Bash.

Il est capable de :
- Gérer des utilisateurs à distance 
- Administrer des postes clients
- Interroger le status d'une machine
- Automatiser des opérations ciblées
---

## 2. Intro

Ce projet consiste à mettre en place une infrastructure virtuelle client/serveur Linux et déveloper un script d'administration centrakisée en Bash.
Les machines sont sur le meme réseau.

---

## 3. Logiciels utilisées

### 3.1 Machines Virtuelles

2 VM sont hébergées sur **VirtualBox** en réseau interne (`intnet`).

| Nom | Role | OS | IP | Compte | Mot de passe |
|-----|------|----|----|--------|--------------|
| SRVLX01 | Serveur Principal | Debian | 172.16.50.10 | root/wilder | Azerty1* |
| CLILIN01 | Client | Ubuntu | 172.16.50.30 | wilder | Azerty1* |

### 3.2 Outils utilisés

| Outil | Usage |
|-------|-------|
| VirtualBox | Virtualisation des machines |
| Github | Dépot |
| OpenSSH Server | Communication entre les machines |
| Nano | Editer fichiers avec Terminal |

---

## 4. Fonctionnalités du script

## 4.1 Gestions des machines

| Option | Action | Commande SSH |
|--------|--------|--------------|
| 1 | Arreter la machine | `sudo shutdown now` |
| 2 | Redémarrer la machine | `sudo reboot` |
| 3 | Voir la version de l'OS | `cat /etc/os-release` |
| 4 | Voir l'adresse IP | `hostname -I` |

> les options Arret et Redémarrage néccessitent que `wilder` ait les droits sudo sans mot de passe sur CLILIN01.


## 4.2 Gestion des utilisateurs 
| Option | Action | Commande SSH |
|--------|--------|--------------|
| 1 | Créer utilisateur | `sudo adduser $NOM` |
| 2 | Supprimer utilisateur | `sudo deluser $NOM` |
| 3 | Modifier mot de passe | `sudo passwd $NOM` |
| 4 | Voir deenière connexion | `last $NOM \| head -1` |
| 5 | Voir dernier changement de mdp | `sudo chage -1 $NOM` |

---
