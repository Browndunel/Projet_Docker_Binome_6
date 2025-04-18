# Docker Web App avec Nginx et MySQL

Ce projet utilise Docker pour orchestrer trois services principaux :
1. **MySQL** : Serveur de base de données.
2. **Application Flask** : Application web connectée à MySQL.
3. **Nginx** : Reverse Proxy dirigeant le trafic vers l'application Flask.

## Démarrer le Projet

### Partie 1 : Script Manuel (`setup_manual.ps1`)

Le script PowerShell crée les réseaux et volumes nécessaires, construit les images et lance les conteneurs dans un ordre logique.

1. **Exécuter le script PowerShell** :

```powershell
./setup_manual.ps1
Cela va :

Créer les réseaux Docker nécessaires.

Construire les images pour MySQL, l'application Flask et Nginx.

Démarrer les conteneurs dans le bon ordre.

Partie 2 : Lancer avec Docker Compose (compose.yaml)
Pour la partie 2, nous utilisons Docker Compose pour orchestrer les services. Suivez les étapes ci-dessous :

Construire et lancer les services avec Docker Compose :

bash
Copier
Modifier
docker compose up --build -d
Cela va construire les images et démarrer les conteneurs en arrière-plan.

Accéder à l'Application
L'application sera accessible à l'adresse suivante :

bash
Copier
Modifier
http://localhost:5423
Routes de l'Application :
/health : Vérifie la santé du service.

/data : Affiche des données provenant de la base MySQL.

Arrêter les Conteneurs
Pour arrêter tous les conteneurs et nettoyer l'environnement, exécute :
docker compose down

##Structure du Projet##
docker_project_binome/
├── app/
│   ├── Dockerfile
│   ├── conf/
│   └── src/
├── mysql/
│   ├── Dockerfile
│   └── conf/
├── nginx/
│   ├── Dockerfile
│   └── conf/
├── compose.yaml
├── setup_manual.ps1
└── README.md

#### 5. **Vérifier les Critères d'Évaluation**

Avant de soumettre ton projet, assure-toi que tout est conforme aux critères d'évaluation :

- **Partie 1** : Le script PowerShell doit construire les images et lancer les conteneurs dans le bon ordre.
- **Partie 2** : Le fichier `compose.yaml` doit définir correctement les services, les réseaux, les volumes, les ports, les dépendances, etc.
- **Healthcheck** : Vérifie que la configuration de santé de MySQL et de l'application Flask est correcte.
- **Nginx** : Assure-toi que Nginx est configuré comme reverse proxy et fonctionne correctement.
- **MySQL** : Vérifie que la base de données MySQL persiste entre les redémarrages des conteneurs.

#### 6. **Publier le Dépôt**

Une fois que tout est configuré et vérifié, assure-toi de bien pousser les derniers changements sur GitHub :

```bash
git add .
git commit -m "Final project submission"
git push
