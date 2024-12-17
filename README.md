# Guide d'Apprentissage Docker de A à Z avec Docker Compose et WordPress

Ce guide complet est conçu pour apprendre **Docker** depuis les bases les plus simples jusqu'à des projets plus avancés. Vous apprendrez à utiliser Docker sur **Windows** et **macOS**, avec des exemples clairs et des commandes adaptées à chaque système.

---

## Table des Matières

1. [Introduction](#introduction)
2. [Installation de Docker](#installation-de-docker)
3. [Gestion des Images Docker](#gestion-des-images-docker)
4. [Gestion des Conteneurs Docker](#gestion-des-conteneurs-docker)
5. [Flags de la Commande `docker run`](#flags-de-la-commande-docker-run)
6. [Gestion des Réseaux Docker](#gestion-des-reseaux-docker)
7. [Exécution de Commandes dans un Conteneur](#execution-de-commandes-dans-un-conteneur)
8. [Volumes Docker : Gestion et Utilisation](#volumes-docker-gestion-et-utilisation)
9. [Introduction à Docker Compose](#introduction-a-docker-compose)
10. [Exemple Pratique : Déploiement de Services avec Docker Compose](#exemple-pratique-deploiement-de-services-avec-docker-compose)
11. [Déploiement Multi-Conteneurs avec Docker Compose](#deploiement-multi-conteneurs-avec-docker-compose)
12. [Résumé des Commandes Utiles](#resume-des-commandes-utiles)
13. [Nettoyage des Ressources](#nettoyage-des-ressources)

---

## Introduction
Docker est un outil puissant qui permet de conteneuriser des applications pour qu'elles soient faciles à déployer et à exécuter, peu importe l'environnement. L'objectif de ce guide est de :

- Apprendre **pas à pas** Docker.
- Fournir des exemples concrets pour **Windows** et **macOS**.
- Créer un projet **WordPress** à l'aide de Docker Compose.

---

## Installation de Docker

### Windows
1. Téléchargez **Docker Desktop** depuis le site officiel : [Docker Desktop for Windows](https://docs.docker.com/desktop/install/windows/).
2. Lancez l'installation en suivant les instructions.
3. Redémarrez votre ordinateur si nécessaire.
4. Vérifiez l'installation avec :
   ```powershell
   docker --version
   ```

### macOS
1. Téléchargez **Docker Desktop for Mac** depuis le site officiel : [Docker Desktop for Mac](https://docs.docker.com/desktop/install/mac/).
2. Ouvrez le fichier téléchargé et faites glisser Docker dans le dossier Applications.
3. Lancez Docker et acceptez les permissions.
4. Vérifiez l'installation avec :
   ```bash
   docker --version
   ```

---

## Gestion des Images Docker

Les images Docker sont essentielles pour créer des conteneurs. Voici les commandes de base pour gérer les images :

### Télécharger des Images
- **Windows/macOS :**
   ```bash
   docker pull hello-world:latest
   docker pull ghost:alpine
   docker pull python:3.13.0a4-slim
   docker pull alpine:latest
   docker pull debian:bookworm-slim
   ```

### Lister les Images
- **Windows/macOS :**
   ```bash
   docker images
   docker image ls
   ```

### Supprimer des Images
- **Windows/macOS :**
   ```bash
   docker image rm hello-world:latest
   docker image prune -a
   ```

---

## Gestion des Conteneurs Docker

Un conteneur est une instance en cours d'exécution d'une image Docker.

### Créer un Conteneur
- **Windows/macOS :**
   ```bash
   docker run hello-world:latest
   docker run -d ghost:alpine
   ```

### Lister les Conteneurs
- **Windows/macOS :**
   ```bash
   docker ps
   docker ps -a
   ```

### Lire les Logs d'un Conteneur
- **Windows/macOS :**
   ```bash
   docker logs <ID_du_conteneur>
   ```

### Démarrer/Arrêter un Conteneur
- **Windows/macOS :**
   ```bash
   docker start <ID_du_conteneur>
   docker stop <ID_du_conteneur>
   ```

### Supprimer un Conteneur
- **Windows/macOS :**
   ```bash
   docker rm <ID_du_conteneur>
   ```

### Nettoyer les Conteneurs Arrêtés
- **Windows/macOS :**
   ```bash
   docker container prune
   ```

---

## Flags de la Commande `docker run`

### Exposer un Port
- **Windows/macOS :**
   ```bash
   docker run -p 8080:80 nginx
   ```

### Définir une Variable d'Environnement
- **Windows/macOS :**
   ```bash
   docker run -e APP_ENV=production -d node:14
   ```

### Ajouter un Nom au Conteneur
- **Windows/macOS :**
   ```bash
   docker run --name mon_conteneur -d nginx
   ```

---

## Gestion des Réseaux Docker

### Créer un Réseau
- **Windows/macOS :**
   ```bash
   docker network create mon-reseau
   ```

### Connecter un Conteneur à un Réseau
- **Windows/macOS :**
   ```bash
   docker run --network mon-reseau --name mon-conteneur -d nginx
   ```

---

## Exécution de Commandes dans un Conteneur

### Exécuter des Commandes Simples
- **Windows/macOS :**
   ```bash
   docker exec mon-conteneur ls /app
   ```

---

## Volumes Docker : Gestion et Utilisation

### Créer un Volume Nommé
- **Windows/macOS :**
   ```bash
   docker volume create mon-volume
   ```

---

## Introduction à Docker Compose

Docker Compose permet de gérer plusieurs conteneurs à partir d'un fichier de configuration **`docker-compose.yaml`**.

---

## Exemple Pratique : Déploiement de Services avec Docker Compose

### Créer un Projet Compose
- **Windows/macOS :**
   ```bash
   mkdir wordpress-project
   cd wordpress-project
   touch docker-compose.yaml
   ```

---

## Déploiement Multi-Conteneurs avec Docker Compose

### Objectif du Projet
Déployer **Gitea** avec une base de données **PostgreSQL**.

### Rédaction du Fichier Compose
- **Windows/macOS :**
   ```bash
   nano docker-compose.yaml
   ```
Ajoutez le contenu YAML pour Gitea et PostgreSQL.

---

## Résumé des Commandes Utiles

| **Commande**                          | **Description**                           |
|---------------------------------------|------------------------------------------|
| `docker ps -a`                        | Lister tous les conteneurs.              |
| `docker images`                       | Lister les images disponibles.           |
| `docker compose up -d`                | Démarrer les services avec Docker Compose.|

---

## Nettoyage des Ressources

```bash
docker system prune -a
```
