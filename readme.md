# SAE Sécurité Informatique : Mise en place d’un Firewall et durcissement d’un serveur Web

## Dates du projet
- **Début :** [03/03/2025]
- **Fin :** [14/03/2025]

## Objectif du projet
Ce projet a pour objectif de **mettre en place un firewall** sur un serveur Debian et de **sécuriser un serveur web Nginx**.  
L’ensemble a été déployé via Vagrant et testé à l’aide d’outils de diagnostic réseau.

## Architecture

L’infrastructure repose sur deux machines virtuelles Debian configurées avec Vagrant :
- **Server (192.168.56.10)** : héberge le serveur web Nginx et le firewall UFW
- **Client (192.168.56.11)** : utilisé pour tester la connectivité et la sécurité du serveur

## Technologies utilisées

- **Vagrant** : pour l’automatisation des machines virtuelles
- **Debian 12 (Bookworm)** : système d’exploitation stable et sécurisé
- **Nginx** : serveur web
- **UFW (Uncomplicated Firewall)** : configuration du pare-feu
- **Outils de test réseau** : `curl`, `nmap`

## Étapes principales

1. **Préparation de l’environnement** :  
   Création de deux VMs avec Vagrant et VirtualBox, configuration réseau, et tests de connectivité.

2. **Installation de Nginx** :  
   Déploiement et configuration de Nginx sur la VM serveur, vérification des accès depuis la VM client.

3. **Mise en place du Firewall** :  
   Installation et activation de UFW, définition des règles de sécurité (blocage par défaut, autorisation de HTTP/SSH).

4. **Sécurisation du serveur web** :  
   Ajout de headers de sécurité (HSTS, X-Frame-Options, etc.), restriction des méthodes HTTP.

5. **Mise en place d’une DMZ** :  
   Création d’une troisième VM représentant une DMZ, tentative de configuration pour isoler la DMZ.

## Résultats obtenus

- Serveur Nginx fonctionnel et accessible en HTTP.
- Firewall actif bloquant les connexions non autorisées.
- Headers de sécurité HTTP appliqués pour limiter les risques d’attaques.

## Problèmes rencontrés

- Difficulté à maintenir l’accès SSH après certaines modifications des règles UFW.
- Impossibilité de poursuivre la configuration de la DMZ au-delà d’un certain point à cause de ces restrictions.

## Possibilités d’amélioration

- Compléter la mise en place de la DMZ et la vérification de son isolement.
- Ajouter un système de détection d’intrusion (IDS).
- Créer un script unique pour automatiser toutes les étapes de configuration.

---

## Journal de bord
Toutes les étapes sont documentées dans [journal.md](./journal.md).

## Commandes utiles

accéder aux machines : 
vagrant ssh server
vagrant ssh client

Tester l’accès au serveur :
curl -I http://192.168.56.10

Vérifier le firewall :
nmap -p 22,80 192.168.56.10

### Démarrer les VMs :
```bash
vagrant up

