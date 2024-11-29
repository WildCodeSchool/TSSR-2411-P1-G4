
# TSSR-2411-P1-G4
![image](https://github.com/user-attachments/assets/2db2c224-2580-4ddd-971b-ec89129633b4)


# Présentation du Projet : Attaque par Dictionnaire sur Mot de Passe 


## Objectif

Tester la vulnérabilité d'un mot de passe de fichier zippé chiffré sur un serveur Windows Server 2022 à l'aide d'une attaque par dictionnaire. Utiliser les outils John the Ripper ou Hashcat sur une machine cliente Ubuntu pour mener cette attaque, puis étendre l'analyse à un compte local du serveur.

## Étape 1 : Mise en place de l'Environnement

### Serveur :
* Installation de Windows Server 2022 : Suivre les instructions officielles de Microsoft pour une installation propre.
* Configuration du serveur : Mettre en place le protocol pour faire les actions sur le fichier zippé chiffré .

### Client :
* Installation d'Ubuntu 22.04/24.04 LTS : Utiliser les images ISO officielles et suivre les guides d'installation.
* Installation de John the Ripper ou Hashcat : Utiliser les gestionnaires de paquets apt ou les sources pour installer le logiciel choisi.
* Configuration de l'outil : Configurer les chemins d'accès aux fichiers, les types de hachage à tester et le dictionnaire d'attaque.

## Étape 2 : Attaque par Dictionnaire sur le Fichier Zippé

* **Récupération du hachage :** Extraire le hachage du mot de passe à partir du fichier zippé chiffré.
* **Lancement de l'attaque :** Exécuter John the Ripper ou Hashcat en spécifiant le hachage, le type de hachage et le dictionnaire.
* **Analyse des résultats :** Examiner les résultats de l'attaque pour déterminer si le mot de passe a été craqué.

## Étape 3 : Attaque sur un Compte Local du Serveur

* **Récupération des hashes :** Utiliser des outils comme `samdump2` pour extraire les hashes des comptes locaux du serveur.
* **Lancement de l'attaque :** Exécuter John the Ripper ou Hashcat avec les hashes extraits et le dictionnaire.
* **Analyse des résultats :** Évaluer la sécurité des comptes locaux en fonction des résultats de l'attaque.

 

# Équipe du Projet

- 🏆 **Maxime** : *Scrum Master*
  - Responsable de la mise en place de la méthode Scrum
  - Coordination des étapes de test et d'installation des systèmes

- 🛠️ **Adel** : *Membre de l'équipe*
  - Mise en application pratique
  - Réalisation des tests et des installations

- 🔧 **Ismail** : *Membre de l'équipe*
  - Mise en application des processus d'installation
  - Support technique pour les procédures d'implémentation

- 📋 **Xavier** : *Product Owner*
  - Rédaction de la documentation technique
  - Mise en forme et structuration des documents de test systèmes


Semaine 1

| Difficultés | Solutions |
|------------|-----------|
| Installation de la VM Ubuntu bloquée | Augmenter la mémoire vive (RAM) dans les options de configuration de la machine virtuelle |
| Installation de Windows Server difficile | - Rechercher et utiliser des documentations et tutoriels détaillés<br>- Formation et acquisition de connaissances préalables<br>- Pratique et tests multiples |
| Installation de John the Ripper | - Acquisition de connaissances sur le logiciel<br>- Étude des procédures d'installation<br>- Tests de plusieurs méthodes d'installation<br>- Consultation de documentation technique |
| Partage de fichiers entre un client Linux et un serveur Windows | - Recherche de documentation sur les procédures de partage<br>- Étude des protocoles de transfert de fichiers<br>- Tests et configuration des paramètres de partage |

Ce tableau récapitule les principales difficultés rencontrées lors du projet et propose des solutions concrètes pour les surmonter. Chaque ligne présente un défi spécifique et les approches recommandées pour le résoudre.
