# SAE Sécurité Informatique : Mise en place d’un Firewall et durcissement d’un serveur Web

## Description

Ce projet a pour objectif de mettre en place un firewall sur un serveur Debian et de sécuriser un serveur web Nginx. L'ensemble est déployé via Vagrant et testé à l'aide de différentes commandes de diagnostic réseau.

## Architecture

L'infrastructure repose sur deux machines virtuelles Debian configurées avec Vagrant :
- **Server (192.168.56.10)** : héberge le serveur web Nginx et le firewall UFW
- **Client (192.168.56.11)** : utilisé pour tester la connectivité et la sécurité du serveur

Un troisième hôte pourra être ajouté pour démontrer la mise en place d’une DMZ.

## Technologies utilisées

- Vagrant pour l'automatisation des machines virtuelles
- Debian 12 (Bookworm) comme système d’exploitation
- Nginx pour le serveur web
- UFW (Uncomplicated Firewall) pour la configuration du pare-feu
- Outils de test réseau : `curl`, `nmap`

## Installation et utilisation

### Prérequis

- **Vagrant** et **VirtualBox** doivent être installés sur votre machine hôte.

### Étapes d’installation

1. **Cloner le dépôt**
   ```bash
   git clone https://github.com/Julesbnft/demo-firewall2.git
   cd demo-firewall2
   ```

2. **Démarrer les machines virtuelles**
   ```bash
   vagrant up
   ```

3. **Accéder aux machines**
   - Serveur :  
     ```bash
     vagrant ssh server
     ```
   - Client :  
     ```bash
     vagrant ssh client
     ```

4. **Configurer le serveur et le firewall**
   ```bash
   cd /vagrant
   chmod +x setup.sh firewall.sh
   sudo ./setup.sh
   sudo ./firewall.sh
   ```

5. **Tester l'accès depuis le client**
   ```bash
   curl -I 192.168.56.10
   ```

## Scripts et fonctionnalités

### `setup.sh`
Ce script installe et configure le serveur Nginx sur la VM serveur.

### `firewall.sh`
Script qui applique les règles UFW pour sécuriser le serveur.

### `test.sh`
Permet de tester la connectivité et l’accès aux services depuis la VM client.

## Tests et validation

### Vérification du firewall

Depuis la VM client :
```bash
nmap -p 22,80 192.168.56.10
```
Ce test doit montrer que le port 80 est ouvert et le port 22 fermé sauf pour le client.

### Vérification du serveur web

Depuis la VM client :
```bash
curl -I 192.168.56.10
```
La réponse doit contenir `HTTP/1.1 200 OK`, prouvant que le serveur web fonctionne.

## Journal de bord

Toutes les étapes de mise en place et de configuration sont documentées dans `journal.md`.
