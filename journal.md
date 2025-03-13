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

### Étape 5 : Expérimentation et démonstration

- Vérification des ports ouverts avec `nmap` : OK
- Vérification de l’accès au serveur web avec `curl` : OK
- Blocage des méthodes HTTP non autorisées (`DELETE`, `PUT`...) : OK
- Test du firewall UFW : SSH restreint, HTTP ouvert, HTTPS filtré : OK
- Firewall efficace et bloque bien les accès non autorisés : OK

### Étape 6 : Mise en place d’une DMZ

- Ajout d’une troisième VM pour représenter la DMZ : OK
- Configuration du réseau et attribution d’une IP fixe : OK
- Vérification de la connectivité avant firewall : OK
- Implémentation du firewall pour isoler la DMZ : OK
- Test de l’isolement réseau (ping, HTTP, SSH) : OK
