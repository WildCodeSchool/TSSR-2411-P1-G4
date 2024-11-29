
Je vais reformuler et améliorer le texte en markdown pour créer une introduction claire et structurée pour votre documentation de projet :

# 📘 Guide Complet d'Installation et de Déploiement du Projet

## 🎯 Objectif du Document

Ce document vise à fournir une documentation exhaustive et détaillée couvrant l'intégralité du processus d'installation et de configuration de notre projet. Il servira de référence technique pour :

- 💻 L'installation des systèmes d'exploitation
- 🔧 La configuration des environnements logiciels
- 📋 Les procédures pas à pas de déploiement
- 🛠️ Les commandes essentielles pour une mise en œuvre réussie

## 🗂️ Contenu Détaillé

### 1. Captures d'Écran Explicatives
- Illustrations visuelles de chaque étape clé
- Annotations précises pour guider l'utilisateur
- Repères visuels facilitant la compréhension

### 2. Procédures d'Installation
- **Systèmes d'Exploitation**
  - Choix et préparation des OS
  - Étapes d'installation pas à pas
  - Configurations recommandées

- **Logiciels Essentiels**
  - Liste des logiciels requis
  - Méthodes d'installation
  - Configurations et paramétrages

### 3. Commandes Techniques
- Commandes shell/terminal
- Scripts d'automatisation
- Procédures de vérification et de test

## 🚀 Principes Directeurs
- **Clarté** : Chaque étape sera claire et compréhensible
- **Exhaustivité** : Couverture complète du processus
- **Reproductibilité** : Permettre une installation standardisée

## 📝 Recommandations
- Suivre les étapes séquentiellement
- Consulter les captures d'écran en parallèle
- Effectuer des vérifications à chaque étape

---
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
![](https://github.com/WildCodeSchool/TSSR-2411-P1-G4/blob/main/Pictures/samba/samba%20ubuntu1.png)
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
![](https://github.com/WildCodeSchool/TSSR-2411-P1-G4/blob/main/Pictures/samba/samba3.png)  
### 🗂️ Objectif de la Commande
- Création d'un nouveau dossier nommé "partage"
- Localisation dans le répertoire `/srv/`
#### Détails Techniques
- `sudo` : Exécution avec les privilèges administrateur
- `mkdir` : Commande pour créer un répertoire
- `/srv/` : Répertoire standard pour héberger des données de services
  
### 🔐 Gestion des Propriétaires du Dossier

#### Options de la Commande
- `chown` : Change Owner (modifier le propriétaire)
- `-R` : Récursif (s'applique au dossier et à tous ses sous-éléments)
- `nobody:nogroup` : Utilisateur et groupe système sans privilèges spécifiques

#### Objectifs
- Retirer toute propriété personnelle
- Préparer le dossier pour un usage générique/partagé
- Augmenter la sécurité en limitant les droits
### 🔓 Configuration des Permissions

#### Signification des Paramètres
- `chmod` : Change Mode (modifier les permissions)
- `-R` : Récursif (s'applique au dossier et à tous ses sous-éléments)
- `777` : Permissions maximales
  - 1er chiffre Propriétaire : Lecture, Écriture, Exécution
  - 2eme chiffre Groupe : Lecture, Écriture, Exécution
  - 3eme chiffre Autres : Lecture, Écriture, Exécution

#### ⚠️ Points de Vigilance
- Permissions `777` sont très ouvertes
- À utiliser avec précaution
- Recommandé uniquement pour des environnements contrôlés et sécurisés

  
### Configuration du Fichier Samba

sudo nano /etc/samba/smb.conf


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
![](https://github.com/WildCodeSchool/TSSR-2411-P1-G4/blob/main/Pictures/samba/samba4.png)  

!!Attention a bien sauvegerader votre fichier!!  

📋 Analyse Détaillée de la Configuration de Partage Samba
🔍 Bloc de Configuration 
1. [PartageDocuments]

🏷️ Nom du partage réseau
Identifiant unique pour ce point de partage
Sera visible par les clients réseau
Le nom entre crochets définit comment le partage apparaîtra

a. path = /srv/partage

📂 Chemin du dossier physique sur le serveur Linux
Localisation réelle des fichiers à partager
/srv/ : Convention pour les données de services
Indique exactement où sont stockés les fichiers partagés

b. browsable = yes

🌐 Rend le partage visible dans la liste des partages réseau
Permet aux utilisateurs de découvrir le partage
Facilite la navigation dans l'explorateur réseau

c. read only = no

✍️ Autorise les modifications de fichiers
Possibilité de :

Créer des fichiers
Modifier des fichiers existants
Supprimer des fichiers


no signifie lecture et écriture activées

d. guest ok = no

🔒 Interdit l'accès anonyme/invité
Authentification obligatoire
Sécurisation de l'accès au partage
Nécessite des identifiants valides

e. create mask = 0755

📝 Permissions par défaut pour les nouveaux fichiers
0755 signifie :

Propriétaire : lecture, écriture, exécution
Groupe : lecture, exécution
Autres : lecture, exécution

f. directory mask = 0755

📁 Permissions par défaut pour les nouveaux dossiers
Similaire à create mask
Contrôle les droits de création de répertoires

g. valid users = @smbusers

👥 Restreint l'accès aux membres du groupe smbusers
@ indique un groupe système
Seuls les utilisateurs de ce groupe peuvent accéder au partage

## 📊 Tableau Comparatif des Permissions

| Valeur | Propriétaire | Groupe | Autres | Niveau de Sécurité |
|--------|--------------|--------|--------|-------------------|
| 777    | RWX          | RWX    | RWX    | Très Ouvert       |
| 755    | RWX          | R-X    | R-X    | Recommandé        |
| 700    | RWX          | ---    | ---    | Restrictif        |

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
![](https://github.com/WildCodeSchool/TSSR-2411-P1-G4/blob/main/Pictures/samba/samba5.png) 

### 🔐 Explication Détaillée des Commandes de Gestion de Groupe et d'Utilisateur

### a. `sudo groupadd smbusers`

#### 🆕 Création d'un Nouveau Groupe

##### Fonction de la Commande
- `groupadd` : Commande pour créer un nouveau groupe sur le système Linux
- `smbusers` : Nom du groupe créé

##### Détails Techniques
- `sudo` : Exécution avec privilèges administrateur
- Le groupe est immédiatement disponible pour attribution

#### 🎯 Objectifs
- Regrouper des utilisateurs ayant des droits de partage Samba
- Simplifier la gestion des permissions
- Permettre un contrôle centralisé des accès

### b. `sudo usermod -aG smbusers wilder`

#### 👤 Ajout d'un Utilisateur à un Groupe

##### Options de la Commande
- `usermod` : Commande pour modifier les propriétés d'un compte utilisateur
- `-a` : Add (ajouter sans supprimer les autres appartenances)
- `-G` : Définir les groupes secondaires
- `smbusers` : Groupe cible
- `wilder` : Nom de l'utilisateur

##### Signification Technique
- Ajoute l'utilisateur `wilder` au groupe `smbusers`
- L'utilisateur conserve son groupe principal
- Obtient les permissions associées au groupe `smbusers`
  
## 4. Configuration du Pare-Feu
```bash
sudo ufw allow from 172.16.10.10/24 to any port 445
sudo ufw allow from 172.16.10.10/24 to any port 139
sudo ufw enable
```
**Décomposition des commandes:**

* **`sudo`:** Exécute la commande avec les privilèges d'administrateur.
* **`ufw allow`:** Autorise le trafic entrant.
* **`from 172.16.10.10/24`:** Spécifie le réseau source (toutes les adresses IP de 172.16.10.0 à 172.16.10.255).
* **`to any port 445/139`:** Spécifie les ports destination (445 et 139).

![](https://github.com/WildCodeSchool/TSSR-2411-P1-G4/blob/main/Pictures/samba/samba6.png)

## 5. Redémarrer les Services Samba
```bash
sudo systemctl restart smbd
sudo systemctl restart nmbd
sudo systemctl enable smbd
sudo systemctl enable nmbd
```
![](https://github.com/WildCodeSchool/TSSR-2411-P1-G4/blob/main/Pictures/samba/samba7.png)
### Redémarrer les services SMB/CIFS
* **sudo systemctl restart smbd:**
    - `sudo`: Exécute la commande avec les privilèges d'administrateur.
    - `systemctl restart smbd`: Redémarre le service `smbd`. Ce service gère le partage de fichiers et d'imprimantes sur le réseau.

* **sudo systemctl restart nmbd:**
    - `sudo`: Exécute la commande avec les privilèges d'administrateur.
    - `systemctl restart nmbd`: Redémarre le service `nmbd`. Ce service gère la publication des informations de partage sur le réseau.

### Activer les services SMB/CIFS au démarrage
* **sudo systemctl enable smbd:**
    - `sudo`: Exécute la commande avec les privilèges d'administrateur.
    - `systemctl enable smbd`: Configure le service `smbd` pour qu'il démarre automatiquement au démarrage du système.

* **sudo systemctl enable nmbd:**
    - `sudo`: Exécute la commande avec les privilèges d'administrateur.
    - `systemctl enable nmbd`: Configure le service `nmbd` pour qu'il démarre automatiquement au démarrage du système.
## 6. Vérification de la Configuration
```bash
# Vérifier le statut de Samba
sudo systemctl status smbd 


# Lister les partages
sudo smbclient -L localhost -U wilder
```
![](https://github.com/WildCodeSchool/TSSR-2411-P1-G4/blob/main/Pictures/samba/samba%208.png)

![](https://github.com/WildCodeSchool/TSSR-2411-P1-G4/blob/main/Pictures/samba/samba%209.png)

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
