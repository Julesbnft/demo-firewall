### Étape 1 : Préparation de l’environnement

- Création du dossier de travail : OK
- Configuration de Vagrant pour deux VMs Debian : OK
- Démarrage des VMs : OK
- Vérification de la connexion entre les machines : OK

### Étape 2 : Mise en place du serveur Web

- Installation de Nginx et nginx-extras sur la VM serveur : OK
- Création d’une page statique pour tester Nginx : OK
- Test de l’accès via `curl` depuis la VM client : OK

### Étape 3 : Sécurisation du serveur Web

- Désactivation des versions Nginx : OK
- Ajout des headers de sécurité : OK
- Restriction des méthodes HTTP : OK
- Automatisation via `secure_nginx.sh` : OK

### Étape 4 : Implémentation du Firewall (UFW)

- Installation et activation de UFW : OK
- Blocage du trafic entrant et sortant par défaut : OK
- Autorisation des connexions SSH uniquement depuis la VM client : OK
- Autorisation des connexions HTTP : OK
- Vérification du firewall avec `nmap` : OK

