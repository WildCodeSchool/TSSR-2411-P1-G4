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
# 🐧 Procédure d'Installation d'Ubuntu sur VirtualBox

## 📋 Prérequis
- VirtualBox installé
- Fichier ISO d'Ubuntu (version LTS recommandée)
- Ordinateur avec suffisamment de ressources :
  - Minimum 4 Go RAM
  - 25 Go d'espace disque
  - Processeur avec support de virtualisation

## 🔧 Étape 1 : Préparation de VirtualBox
1. Ouvrir VirtualBox
2. Cliquer sur "Nouvelle"

## 🖥️ Étape 2 : Configuration de la Machine Virtuelle

### Paramètres Généraux
- Nom : `Ubuntu-VM`
- Type : `Linux`
- Version : `Ubuntu (64-bit)`

### Ressources Allouées
- Mémoire RAM : 
  - Recommandé : 4 Go 
  - Minimum : 2 Go
- Processeurs : 2 cœurs

### Configuration du Disque Dur
- Créer un disque virtuel
- Type de fichier : VDI
- Allocation dynamique
- Taille : 30 Go

## 💿 Étape 3 : Installation du Système

### Configuration Initiale
1. Sélectionner la VM
2. Cliquer sur "Paramètres"
3. Onglet "Stockage"
4. Sélectionner le lecteur optique
5. Choisir le fichier ISO d'Ubuntu
6. Cochez la case skip unattended installation

### Démarrage et Installation

#### Écran de Démarrage
- Sélectionner "Install Ubuntu"
- Choisir la langue
- Sélectionner le clavier

#### Configuration Système
- Type d'installation : Normal


#### Partitionnement
- Choisir "Effacer le disque et installer Ubuntu"
- Confirmer le partitionnement

#### Création d'un Utilisateur
- Définir un nom d'utilisateur
- Choisir un mot de passe fort
- Activer le cryptage du dossier personnel (optionnel)


### Configuration Réseau
- Mode par défaut : NAT
- Pour un accès réseau complet : 
  - Changer en "Réseau Ponté"

## 🛠️ Optimisations

### Mise à Jour Initiale
```bash
sudo apt update
sudo apt upgrade -y
```




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



# Procédure de Configuration du Partage de Fichiers SMB sur Windows Server 2022

## 🔧 Prérequis
- Serveur Windows Server 2022 installé
- Droits administrateur sur le serveur
- Dossier à partager déjà créé

## 📋 Étapes de Configuration

### 1. Ouvrir le Gestionnaire de Serveur
1. Cliquer sur le bouton Démarrer
2. Sélectionner "Gestionnaire de serveur"

### 2. Ajouter le Rôle Serveur de Fichiers
1. Cliquer sur "Gérer" > "Ajouter des rôles et fonctionnalités"
2. Dans l'assistant, sélectionner "Rôle de serveur"
3. Cocher "Services de fichiers et de stockage"
4. Sélectionner "Serveur de fichiers" et "Serveur de fichiers SMB"
5. Suivre l'assistant jusqu'à l'installation complète

### 3. Créer un Partage SMB
1. Dans le Gestionnaire de serveur, aller dans "Services de fichiers et de stockage"
2. Cliquer sur "Partages"
3. Cliquer-droit > "Nouveau partage"

### 4. Configuration du Partage
1. Choisir "Partage avancé"
2. Sélectionner le dossier à partager
3. Nommer le partage (ex: "PartageDocuments")
4. Cocher "Partager ce dossier"

### 5. Configurer les Autorisations
1. Onglet "Autorisations"
2. Cliquer sur "Personnaliser"
3. Ajouter les utilisateurs/groupes avec leurs droits :
   - Lecture
   - Modification
   - Contrôle total

### 6. Sécurité NTFS
1. Aller dans les propriétés du dossier
2. Onglet "Sécurité"
3. Cliquer "Modifier" pour ajuster les permissions

### 7. Vérification du Partage
1. Ouvrir l'Explorateur Windows
2. Dans la barre d'adresse, taper `\\NomServeur\NomPartage`
3. Vérifier l'accès et les permissions

## 🔒 Bonnes Pratiques
- Utiliser des groupes pour la gestion des droits
- Limiter les autorisations au strict nécessaire
- Activer l'authentification forte
- Chiffrer les partages sensibles

## ⚠️ Dépannage
- Vérifier le pare-feu
- Confirmer les droits utilisateurs
- Redémarrer le service serveur SMB si nécessaire

## 🛠️ Commandes PowerShell Utiles
```powershell
# Créer un partage
New-SmbShare -Name "MonPartage" -Path "C:\Dossier" -FullAccess "Administrateurs"

# Lister les partages
Get-SmbShare

# Vérifier les permissions
Get-Acl "C:\Dossier"
```
# 🐧 Procédure d'Installation et Configuration de Samba sur Ubuntu pour Partage de Fichiers avec Windows Server 2022

## 🔧 Prérequis
- Système Ubuntu 
- Accès administrateur (sudo)
- Connexion réseau fonctionnelle
- Windows Server 2022 configuré

## 1. Mise à Jour du Système
```bash
sudo apt update
sudo apt upgrade -y
```

## 2. Installation de Samba
```bash
sudo apt install samba smbclient cifs-utils -y
```

## 3. Configuration du Partage de Fichiers

### Créer un Dossier à Partager
```bash
# Exemple : création d'un dossier partagé
sudo mkdir /srv/partage
sudo chown -R nobody:nogroup /srv/partage
sudo chmod -R 777 /srv/partage
```

### Configuration du Fichier Samba
```bash
sudo nano /etc/samba/smb.conf
```

Ajouter la configuration suivante à la fin du fichier :
```ini
[PartageDocuments]
   path = /srv/partage
   browsable = yes
   read only = no
   guest ok = no
   create mask = 0755
   directory mask = 0755
   valid users = @smbusers
```

### Créer un Utilisateur Samba
```bash
# Créer un utilisateur système
sudo adduser wilder

# Ajouter l'utilisateur à Samba
sudo smbpasswd -a wilder

# Créer un groupe pour les utilisateurs Samba
sudo groupadd smbusers
sudo usermod -aG smbusers wilder
```

## 4. Configuration du Pare-Feu
```bash
sudo ufw allow from 172.16.10.10/24 to any port 445
sudo ufw allow from 172.16.10.10/24 to any port 139
sudo ufw enable
```

## 5. Redémarrer les Services Samba
```bash
sudo systemctl restart smbd
sudo systemctl restart nmbd
sudo systemctl enable smbd
sudo systemctl enable nmbd
```

## 6. Vérification de la Configuration
```bash
# Vérifier le statut de Samba
sudo systemctl status smbd

# Lister les partages
sudo smbclient -L localhost -U wilder
```

## 🔒 Configuration Avancée de Sécurité

### Limiter l'Accès
- Modifier `/etc/samba/smb.conf`
- Ajouter des restrictions d'accès
```ini
hosts allow = 172.16.10.10/24
hosts deny = ALL
```

### Authentification
- Utiliser uniquement des comptes utilisateurs
- Désactiver l'accès invité

## 🌐 Connexion depuis Windows Server 2022
1. Ouvrir l'Explorateur de fichiers
2. Cliquer sur "Réseau"
3. Saisir `\\AdresseIPUbuntu\PartageDocuments`
4. Entrer les identifiants Samba

## ⚠️ Dépannage
- Vérifier les logs : `sudo tail -f /var/log/samba/log.smbd`
- Tester la connexion : `testparm`
- Vérifier les ports ouverts : `sudo ss -tuln | grep -E ':139|:445'`



📝 **Notes Importantes**
- Adapter les adresses IP et configurations à votre réseau
- Les captures d'écran spécifiques peuvent varier selon votre environnement
- Testez chaque étape minutieusement
