# SAE Sécurité Informatique : Firewall et Durcissement Serveur Web

##  Dates du projet
- **Début :** [03/03/2015]
- **Fin :** [14/03/2025]

##  Objectif du projet
Ce projet consiste à **mettre en place un firewall et sécuriser un serveur web** pour une PME, en suivant un cahier des charges précis :
- Déployer un **pare-feu UFW**.
- Sécuriser **Nginx** contre les attaques courantes.
- Mettre en place une **DMZ** pour isoler le serveur.
- Tester la sécurité avec **nmap, curl et d'autres outils**.

---

##  **Étape 1 : Préparation de l’environnement**
 **Tâches réalisées :**
- Installation de **Vagrant** et **VirtualBox**.
- Création du dossier de travail `sae-firewall`.
- Configuration du **Vagrantfile** avec :
  - **VM Server** (`192.168.56.10`)
  - **VM Client** (`192.168.56.11`)
- Lancement des machines avec `vagrant up`.
- Test de connexion avec `ping -c 4 192.168.56.10`.

 **Résultat :** Les deux machines communiquent correctement.

---

##  **Étape 2 : Installation de Nginx sur le serveur**
 **Tâches réalisées :**
- Installation de **Nginx** sur la VM `server`.
- Configuration du serveur pour servir une **page statique**.
- Vérification de l’accès depuis `client` avec `curl http://192.168.56.10`.

 **Résultat :** Le serveur web est fonctionnel.

---

##  **Étape 3 : Mise en place du Firewall**
 **Tâches réalisées :**
- Installation et activation d'**UFW**.
- Blocage de tout le trafic par défaut.
- Autorisation de **SSH**, **HTTP**, et **HTTPS**.
- Test avec **nmap** pour vérifier les règles.

 **Résultat :** Les connexions non autorisées sont bloquées.

---

##  **Étape 4 : Sécurisation du serveur Web**
 **Tâches réalisées :**
- Désactivation des **méthodes HTTP dangereuses**.
- Activation des **headers de sécurité** (X-Frame-Options, X-XSS-Protection…).
- Restriction des accès à certaines ressources.

 **Résultat :** Nginx est plus sécurisé contre les attaques courantes.

---

##  **Étape 5 : Mise en place d’une DMZ**
 **Tâches réalisées :**
- Ajout d’une **troisième VM** représentant la DMZ.
- Configuration du firewall pour isoler le réseau interne.
- Vérification des connexions entre les machines.

 **Résultat :** La DMZ est fonctionnelle.

---

##  **Étape 6 : Automatisation et Scripts**
 **Tâches réalisées :**
- Création de **scripts de configuration** pour automatiser l’installation.
- Script de test de firewall (`firewall-test.sh`).
- Script de test de sécurité (`security-test.sh`).

 **Résultat :** Tout peut être déployé et testé automatiquement.

---

##  **Étape 7 : Tests et démonstration**
 **Tâches réalisées :**
- Scan avec **nmap** pour tester les règles du firewall.
- Attaques simulées pour tester la robustesse du serveur.
- Capture des résultats avant/après activation du firewall.

 **Résultat :** Les règles de sécurité sont bien appliquées.

---

##  **Étape 8 : Finalisation et soutenance**
 **Tâches réalisées :**
- Création du **diaporama** de présentation.
- Préparation du **script de démonstration**.
- Répétition de la présentation en respectant le **timing de 8-10 minutes**.

 **Résultat :** Prêt pour la soutenance.

---

##  **Conclusion**
Ce projet nous a permis de :
- Comprendre l’**importance d’un firewall** dans une architecture réseau.
- Automatiser le déploiement d’un serveur sécurisé.
- Expérimenter les attaques et défenses réseau.

**Possibilités d’amélioration :**
- Ajouter un **IDS (Intrusion Detection System)**.
- Mettre en place un **Load Balancer** pour améliorer la résilience.

---

##  **Commandes utiles**
```bash
# Démarrer les VMs
vagrant up

# Se connecter aux machines
vagrant ssh server
vagrant ssh client

# Lancer le test de firewall
./firewall-test.sh
