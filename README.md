# Mensa Dura — MVP site web
Projet pédagogique réalisé à partir du cahier des charges fourni. Stack : PHP 8+, MySQL/MariaDB, HTML, CSS, JavaScript.

## Fonctionnalités incluses dans ce starter
- Site vitrine responsive : accueil, services, catalogue, projets, contact.
- Catalogue alimenté par MySQL avec recherche, filtre de catégorie, disponibilité et tri de prix.
- Panier de demande stocké en session (pas de paiement en ligne).
- Envoi d'une demande de commande dans la base de données.
- Espace administration protégé : connexion, tableau de bord, gestion des produits et consultation / changement de statut des commandes.
- Statuts de commande conformes au cahier des charges.

## Prérequis
- PHP 8.0 ou supérieur, extension PDO MySQL activée.
- MySQL ou MariaDB.
- XAMPP, WAMP ou MAMP conseillé pour un projet étudiant.

## Installation locale (XAMPP)
1. Copier le dossier `mensa_dura_freelance` dans `htdocs/`.
2. Démarrer Apache et MySQL.
3. Ouvrir phpMyAdmin et importer `database.sql`.
4. Vérifier les identifiants dans `config.php` (par défaut utilisateur `root`, mot de passe vide en local XAMPP).
5. Ouvrir `http://localhost/mensa_dura_freelance/`.
6. Pour créer le premier compte administrateur, générer un hash avec PHP :
   `php -r "echo password_hash('ChangeMe_123!', PASSWORD_DEFAULT), PHP_EOL;"`
   Puis insérer ce hash dans la table `users` avec le rôle `admin`. Exemple SQL :
   `INSERT INTO users (name,email,password_hash,role) VALUES ('Administrateur','admin@example.com','COLLER_LE_HASH_ICI','admin');`
7. Se connecter via `http://localhost/mensa_dura_freelance/admin/login.php`.

## Parcours de démonstration
1. Visiter le catalogue et filtrer les produits.
2. Ajouter un ou plusieurs produits au panier.
3. Envoyer une demande avec nom, email et téléphone.
4. Se connecter au back-office.
5. Modifier un produit ou faire évoluer le statut d'une commande.

## Structure
- `index.php` : page d'accueil
- `catalogue.php` : catalogue, filtres et ajout au panier
- `panier.php` : panier et soumission de demande
- `projets.php`, `contact.php` : pages vitrines
- `config.php` : connexion PDO et configuration
- `includes/` : fonctions et en-tête/pied de page
- `admin/` : authentification, dashboard, produits et commandes
- `database.sql` : schéma + données de démonstration
- `assets/` : styles et scripts

## Limites et tâches avant livraison réelle
- Configurer SMTP pour l'email de vérification (la vérification par code est prévue dans le cahier des charges, mais n'est pas activée dans ce MVP).
- Ajouter la vérification CSRF aux formulaires, limitation des tentatives de connexion et journalisation.
- Tester sur les navigateurs et appareils cibles.
- Remplacer les images de démonstration par les photos autorisées du client.
- Vérifier les obligations légales locales (mentions légales, confidentialité, conservation des données).
- Déployer sur un hébergement HTTPS et modifier les identifiants par défaut.
- Le suivi client authentifié et la gestion des commandes fournisseurs restent des extensions à développer.
# test_web
