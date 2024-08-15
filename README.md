# VS Dockode

Dockode est un environnement de développement basé sur Docker qui utilise VS Code (code-server) pour éditer et gérer des projets de manière isolée. Chaque projet dispose de son propre conteneur avec des spécifications personnalisées (langage de programmation, dépendances, etc.), et un conteneur code-server central permet d’éditer les fichiers de ces projets via un réseau virtuel partagé.

## Fonctionnalités
- Isolation par projet : Chaque projet est exécuté dans un conteneur Docker distinct avec ses propres spécifications et dépendances.
- Édition à distance : Le conteneur code-server (VS Code) permet d'éditer les fichiers de chaque projet à distance, via un réseau virtuel sécurisé.
- Personnalisation : Chaque conteneur de projet est généré avec les spécifications demandées (langage de programmation, outils, etc.).
- Scalabilité : Ajoutez facilement de nouveaux projets ou conteneurs sans affecter les autres environnements.
- Simplicité d’utilisation : Une interface unifiée via VS Code pour gérer et développer tous vos projets.

## Installation
``` bash -c "$(wget -qLO - https://raw.githubusercontent.com/FirPic/VsDockode/main/install.sh)" ```

## Utilisation
