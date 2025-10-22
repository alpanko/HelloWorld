# 📌 Liste des Tâches - Projet Gestion Comptable de l'Association

Ce document sert de feuille de route pour toute l'équipe. Chaque section
correspond à un domaine fonctionnel du projet (backend, frontend, sécurité,
déploiement) et liste les actions nécessaires pour livrer un système complet.
Les cases à cocher `- [ ]` permettent de suivre l'avancement des travaux. Dès
qu'une tâche est terminée, cochez-la dans ce fichier afin d'avoir une vision
partagée et à jour de la progression.

**Structure du document :**

1. **Environnement de développement** – Préparation des outils communs (GitLab,
   Docker, CI/CD).
2. **Backend** – Microservices Spring Boot par domaine métier (membres,
   transactions, prêts, fonds de caisse, tontine, authentification Keycloak).
3. **API Gateway** – Passerelle d'accès unique qui centralise la sécurité et le
   routage.
4. **Frontend React** – Interface utilisateur, organisée par grandes
   fonctionnalités.
5. **Déploiement & Tests** – Qualité logicielle, intégration continue et mise en
   production.

Utilisez cette hiérarchie pour identifier rapidement où se trouve chaque bloc
de travail et pour attribuer les responsabilités au sein de l'équipe.

## 1️⃣ Mise en place de l'environnement de développement
- [ ] Installer et configurer GitLab
- [ ] Créer les dépôts GitLab pour chaque microservice et le frontend
- [ ] Configurer GitLab CI/CD (fichier `.gitlab-ci.yml`)
- [ ] Configurer un environnement de développement local avec Docker
- [ ] Créer un fichier `docker-compose.yml` pour centraliser les services en local

## 2️⃣ Développement du Backend (Spring Boot)

### 2.1. Service Membres
- [ ] Créer le projet Spring Boot pour Service Membres
- [ ] Configurer PostgreSQL et Hibernate pour ce service
- [ ] Créer l’entité Membre et les rôles associés
- [ ] Implémenter les endpoints REST de gestion des membres (GET, POST, PUT, DELETE)
- [ ] Ajouter les tests unitaires pour la gestion des membres

### 2.2. Service Transactions
- [ ] Créer le projet Spring Boot pour Service Transactions
- [ ] Configurer PostgreSQL et Hibernate pour ce service
- [ ] Créer l’entité Transaction et les statuts associés
- [ ] Implémenter les endpoints REST de gestion des transactions
- [ ] Ajouter les tests unitaires pour la gestion des transactions

### 2.3. Service Prêts
- [ ] Créer le projet Spring Boot pour Service Prêts
- [ ] Configurer PostgreSQL et Hibernate pour ce service
- [ ] Créer l’entité Prêt et gérer le calcul des échéances
- [ ] Implémenter les endpoints REST de gestion des prêts et des remboursements
- [ ] Ajouter les tests unitaires pour la gestion des prêts

### 2.4. Service Fonds de Caisse
- [ ] Créer le projet Spring Boot pour Service Fonds de Caisse
- [ ] Configurer PostgreSQL et Hibernate pour ce service
- [ ] Créer l’entité Fonds de Caisse et suivre les paiements
- [ ] Implémenter les endpoints REST pour gérer les fonds de caisse
- [ ] Ajouter les tests unitaires pour la gestion des fonds de caisse

### 2.5. Service Tontine
- [ ] Créer le projet Spring Boot pour Service Tontine
- [ ] Configurer PostgreSQL et Hibernate pour ce service
- [ ] Créer l’entité Tontine et gérer les contributions et paiements
- [ ] Implémenter les endpoints REST pour la gestion des tontines
- [ ] Ajouter les tests unitaires pour la gestion des tontines

### 2.6. Service Authentification (Keycloak)
- [ ] Configurer Keycloak et créer les rôles utilisateurs (Admin, Membre, Trésorier)
- [ ] Mettre en place l’authentification JWT avec Keycloak dans les microservices
- [ ] Ajouter la gestion des permissions et des rôles pour sécuriser les endpoints

## 3️⃣ Développement de l'API Gateway (Spring Cloud Gateway)
- [ ] Créer le projet Spring Boot pour l’API Gateway
- [ ] Configurer les routes et le proxy des microservices
- [ ] Implémenter la gestion des tokens JWT avec Keycloak
- [ ] Configurer le logging des requêtes et la gestion des erreurs globales
- [ ] Tester la connectivité entre le frontend et les microservices via l’API Gateway

## 4️⃣ Développement du Frontend (React + TypeScript)

### 4.1. Configuration initiale
- [ ] Créer le projet React avec TypeScript
- [ ] Configurer les dépendances : Axios, React Router, Redux, Tailwind CSS
- [ ] Créer la structure des dossiers du projet

### 4.2. Authentification et Gestion des utilisateurs
- [ ] Implémenter la connexion et la gestion des rôles avec Keycloak
- [ ] Ajouter la gestion des tokens JWT côté frontend
- [ ] Créer un écran de connexion sécurisé

### 4.3. Tableau de bord et gestion des transactions
- [ ] Créer la page Dashboard avec les résumés financiers
- [ ] Implémenter l’affichage et la création des transactions

### 4.4. Gestion des prêts et remboursements
- [ ] Créer la page Prêts avec liste et formulaire d’ajout
- [ ] Ajouter l’affichage des échéances et remboursements

### 4.5. Gestion des tontines et du fonds de caisse
- [ ] Créer la page Tontine pour gérer les cycles et contributions
- [ ] Créer la page Fonds de Caisse pour le suivi des paiements

### 4.6. Notifications et Alertes
- [ ] Ajouter des notifications pour informer des actions importantes (paiement, retard, validation)
- [ ] Configurer l’envoi de notifications via WhatsApp et Email

## 5️⃣ Déploiement et Tests

### 5.1. Tests unitaires et d’intégration
- [ ] Écrire des tests unitaires pour chaque microservice
- [ ] Mettre en place des tests d’intégration API
- [ ] Configurer Cypress pour les tests frontend

### 5.2. Déploiement sur un environnement de test
- [ ] Créer un pipeline GitLab CI/CD pour automatiser les builds
- [ ] Déployer les microservices dans un environnement Docker Compose
- [ ] Tester la connectivité entre les services et le frontend

### 5.3. Déploiement en production
- [ ] Déployer les microservices et l’API Gateway sur Kubernetes
- [ ] Mettre en place la supervision avec Prometheus et Grafana
- [ ] Vérifier la scalabilité et la résilience du système
