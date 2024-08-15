# VS Dockode

Dockode est un environnement de développement basé sur Docker qui utilise VS Code (code-server) pour éditer et gérer des projets de manière isolée. Chaque projet dispose de son propre conteneur avec des spécifications personnalisées (langage de programmation, dépendances, etc.), et un conteneur code-server central permet d’éditer les fichiers de ces projets via un réseau virtuel partagé.

## Fonctionnalités
- Isolation par projet : Chaque projet est exécuté dans un conteneur Docker distinct avec ses propres spécifications et dépendances.
- Édition à distance : Le conteneur code-server (VS Code) permet d'éditer les fichiers de chaque projet à distance, via un réseau virtuel sécurisé.
- Personnalisation : Chaque conteneur de projet est généré avec les spécifications demandées (langage de programmation, outils, etc.).
- Scalabilité : Ajoutez facilement de nouveaux projets ou conteneurs sans affecter les autres environnements.
- Simplicité d’utilisation : Une interface unifiée via VS Code pour gérer et développer tous vos projets.

## Installation
```bash
 bash -c "$(wget -qLO - https://raw.githubusercontent.com/FirPic/VsDockode/main/install.sh)" 
 ```

## Utilisation
1. Lancer VS Dockode

Une fois l'installation terminée, tu peux démarrer VS Dockode avec la commande suivante :
```bash
vsdockode start
```

Cette commande initialise le conteneur code-server ainsi que tous les conteneurs projet configurés.

2. Créer un Nouveau Projet

Pour créer un nouveau projet avec des spécifications personnalisées (par exemple, un projet Python), utilise la commande :

```bash
vsdockode create --name mon_projet --lang python@3.10
```

Cette commande génère un nouveau conteneur avec Python 3.10 et configure les dépendances spécifiques dans le fichier Dockerfile du conteneur.

3. Accéder à l’Interface VS Code

Ouvre ton navigateur web et accède à l'interface de code-server en utilisant l'adresse suivante :

```http
http://mon-domain.fr
```

## Options

## Gérer les Conteneurs

VS Dockode permet de gérer les conteneurs via les commandes suivantes :

- Lister les projets actifs : ```vsdockode list```
- Arrêter un projet : ```vsdockode stop --name mon_projet```
- Redémarrer un projet : ```vsdockode restart --name mon_projet```

### Sauvegarder et Exporter

Pour sauvegarder l'état d'un projet ou l'exporter pour une utilisation future, tu peux utiliser :

```bash
vsdockode save --name mon_projet --output mon_projet_backup.tar
```

### Restaurer un Projet
Pour restaurer un projet précédement sauvegardé, tu peu utiliser :
```bash
vsdockode restore --file mon_projet_backup.tar
```

### Supprimer un Projet

Si tu n'as plus besoin d'un projet, tu peux supprimer le conteneur associé avec :

```bash
vsdockode delete --name mon_projet
```