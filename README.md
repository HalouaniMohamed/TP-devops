# 🛠️ Projet DevOps - Microservices Spring Boot

## 📦 Description

Ce projet est une application composée de 3 microservices Java Spring Boot :

- `shopfront` : point d'entrée principal de l'application.
- `productcatalogue` : gère le catalogue des produits.
- `stockmanager` : gère les stocks des produits.

L’objectif est de mettre en œuvre une chaîne DevOps complète avec :
- Docker
- GitHub Actions pour CI/CD
- Docker Compose pour l’orchestration
- Gestion de tags Git dynamiques

---

## 🚀 Lancement de l'application

### 1. Prérequis

- Docker
- Docker Compose
- Git

### 2. Cloner le projet

```bash
git clone https://github.com/HalouaniMohamed/TP-devops.git
cd TP-devops
```

### 3. Lancer les services avec Docker Compose
```bash
docker-compose up --build
```
Les microservices seront accessibles sur :

- shopfront : http://localhost:8010

- productcatalogue : http://localhost:8020

- stockmanager : http://localhost:8030


Les images sont poussées vers Docker Hub :

- halouani/shopfront

- halouani/productcatalogue

- halouani/stockmanager

🔄 Intégration Continue (CI)
À chaque push sur la branche master :

    - Le projet est compilé (mvn clean install)

    - Une image Docker est construite et poussée

    - Un tag Git est généré automatiquement (ex: v1.0.1)

    - Une simulation de déploiement est affichée



### ❗ Problèmes rencontrés
    - Erreur de version Java dans GitHub Actions** : le script CI utilisait une version de Java incompatible avec le projet. Résolu en définissant la bonne version (temurin avec java-version: 8).
    - Erreur de chemin dans le Dockerfile : au début, les chemins relatifs dans le `Dockerfile` ne pointaient pas correctement vers les fichiers `.jar` générés par Maven. J’ai corrigé ça en ajustant le `COPY` pour viser le bon dossier `target/`.

          
### ✅ À faire fonctionner

docker-compose up

Ensuite, ouvrir localhost:8010 dans votre navigateur pour tester le microservice principal.

