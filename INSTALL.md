# 🛠️ Guide d'Installation des Logiciels pour Votre Projet

## 🖥️ Windows Server 2022

### Objectif
Installation d'un serveur Windows pour environnement professionnel

### Prérequis
- **Matériel**
  - Ordinateur avec virtualisation activée
  - VirtualBox ou autre logiciel de virtualisation
  - ISO de Windows Server 2022



## 🐧 Ubuntu

### Objectif
Système d'exploitation Ubuntu

### Prérequis
- **Materiel**
  - Ordinateur avec virtualisation activée
  - VirtualBox ou autre logiciel de virtualisation
  - ISO de la derniere version de ubuntu


# Installation et Utilisation de John The Ripper sur Ubuntu

## 1. Installation de Snap

Si Snap n'est pas installé nativement, utilisez les commandes suivantes :

```bash
sudo apt update
sudo apt install snap
```

## 2. Installation de John The Ripper via Snap

```bash
sudo snap install john-the-ripper
```

## 3. Vérification de l'Installation

Tapez `john` dans le terminal pour vérifier :
- Version : 1.9.0
- Usage : Indique les options pour déchiffrer des fichiers

### Options Principales

- `--single` : Mode par défaut, combinaisons variables basées sur le nom d'utilisateur
- `--wordlist` : Attaque par dictionnaire, utilise une liste de mots de passe 
- `--incremental` : Force brute, teste toutes les combinaisons de caractères

## 4. Création d'Alias

```bash
sudo snap alias john-the-ripper.zip2john zip2john 

```

### Désinstallation (si nécessaire)

```bash
sudo snap remove john-the-ripper
```

## Avertissements Importants

- Utilisez uniquement sur des fichiers dont vous êtes propriétaire
- Le crackage de fichiers sans autorisation est illégal

# 🛠️Installation de Windows Server 2022 sur une Machine Virtuelle

## Préparation

### Téléchargement de l'ISO
- Téléchargez la dernière version de l'ISO Windows Server 2022 depuis le site officiel de Microsoft

### Configuration de VirtualBox
1. Ouvrez VirtualBox
2. Cliquez sur "Nouvelle"
3. Nommez votre machine virtuelle
4. Sélectionnez le type de machine
5. Cochez la case "Skip Unattended Installation"

### Configuration Matérielle
- Mémoire : Sélectionnez au minimum 4 Go
- Disque dur : Choisissez la taille de stockage souhaitée

## Processus d'Installation

### Démarrage de l'Installation
1. Cliquez sur "Démarrer" pour lancer la machine virtuelle
2. Suivez les instructions à l'écran

### Étapes de Configuration

#### Sélection de la Langue et du Clavier
- Choisissez la langue d'installation
- Configurez le format du clavier

#### Installation
- Cliquez sur "Installer maintenant"

#### Licence
- Lisez attentivement les termes de la licence
- Acceptez les conditions

#### Type d'Installation
- Sélectionnez "Installation personnalisée" pour une installation complète

#### Partitionnement du Disque
- Choisissez le disque pour l'installation
- Créez ou utilisez des partitions existantes
- Formatez la partition sélectionnée

## Configuration Initiale du Serveur

### Paramètres Généraux
- **Nom du serveur** : SRVWIN01
- **Mot de passe administrateur** : Azerty1*
- **Fuseau horaire** : Configurez selon votre région

### Configuration Réseau
- **Type de réseau** : Domaine ou Groupe de travail
- **Adresse IP** : 172.16.10.10/24
- **Passerelle par défaut** : Configurez selon votre réseau
- **Serveurs DNS** : Configurez selon votre environnement

### Installation des Fonctionnalités
Sélectionnez les rôles et fonctionnalités nécessaires, par exemple :
- Active Directory
- Serveur de fichiers
- Serveur web

## Finalisation
- Le serveur redémarrera automatiquement après la configuration

**Remarque** : Assurez-vous de bien noter vos configurations réseau et mot de passe pour un accès ultérieur.
