# Guide de démarrage du serveur Django

Ce tutoriel vous guide pas à pas pour lancer votre serveur de développement Django.

## Prérequis

Avant de commencer, assurez-vous d'avoir installé :
- Python (version 3.8 ou supérieure recommandée)
- pip (gestionnaire de paquets Python)

## Étapes d'installation et de lancement

### 1. Créer l'environnement virtuel

Un environnement virtuel permet d'isoler les dépendances de votre projet.

```bash
python -m venv ynov_air
```

Cette commande crée un dossier `ynov_air` contenant l'environnement virtuel.

### 2. Activer l'environnement virtuel

**Sur Windows :**
```bash
ynov_air\Scripts\activate
```

**Sur macOS/Linux :**
```bash
source ynov_air/bin/activate
```

Une fois activé, vous verrez `(ynov_air)` apparaître au début de votre ligne de commande.

### 3. Installer les dépendances

Installez tous les packages Python nécessaires listés dans le fichier `requirements.txt` :

```bash
pip install -r requirements.txt
```

Cette étape peut prendre quelques minutes selon le nombre de dépendances.

### 4. Créer les migrations de base de données

Les migrations permettent de créer ou mettre à jour la structure de votre base de données :

```bash
python manage.py makemigrations
```

Cette commande génère les fichiers de migration basés sur vos modèles Django.

### 5. Appliquer les migrations

Appliquez les migrations pour créer les tables dans la base de données :

```bash
python manage.py migrate
```

### 6. Lancer le serveur de développement

Démarrez le serveur Django :

```bash
python manage.py runserver
```

Par défaut, le serveur démarre sur `http://127.0.0.1:8000/`

## Accéder à votre application

Ouvrez votre navigateur et rendez-vous sur :
```
http://127.0.0.1:8000/
```

ou

```
http://localhost:8000/
```

## Commandes utiles

### Arrêter le serveur
Appuyez sur `Ctrl + C` dans le terminal.

### Désactiver l'environnement virtuel
```bash
deactivate
```

### Lancer le serveur sur un port différent
```bash
python manage.py runserver 8080
```

### Créer un super utilisateur (admin)
```bash
python manage.py createsuperuser
```

## Résolution des problèmes courants

### Erreur "command not found: python"
Essayez d'utiliser `python3` au lieu de `python` :
```bash
python3 -m venv ynov_air
```

### Erreur de permissions sur Windows
Exécutez votre terminal en tant qu'administrateur ou modifiez la politique d'exécution PowerShell :
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

### Port déjà utilisé
Si le port 8000 est déjà occupé, utilisez un port différent :
```bash
python manage.py runserver 8001
```

## Notes importantes

- L'environnement virtuel doit être activé chaque fois que vous travaillez sur le projet
- Ne commitez jamais le dossier de l'environnement virtuel dans Git
- Le serveur de développement Django n'est **pas adapté pour la production**

---

**Bon développement ! 🚀**
