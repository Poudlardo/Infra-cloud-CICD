# **Projet : Déploiement du CMS PythonCMS**
---

## **1. Contexte du projet**

### **Objectif**
Déployer une instance de [PythonCMS](https://github.com/shopyo/pythoncms) dans un conteneur Docker, automatiquement déployé sur une VM Ubuntu pré-paramétrée. L’objectif est de fournir une solution de gestion de contenu scalable, sécurisée et facile à maintenir, adaptée aux besoins des équipes techniques et métiers.

### **Périmètre**
- Déploiement automatisé via une pipeline CI/CD GitHub Action.
- Approche IaC : Provisionnement de ma machine virtuel avec Open Tofu, et configuration avec Ansible.
- Intégration d’outils de monitoring et de logging pour assurer la stabilité et la performance.
- Mise en place de mesures de sécurité : pare-feu, durcissement SSH du serveur.

---

## **2. Intervenant**

### **Rôle et responsabilités**

- **Administrateur Système DevOps** :
  - Pilotage global du projet
  - Responsable de la configuration IaC (Ansible/Terraform), des scripts de déploiement, et de la mise en place de la pipeline CI/CD.
  - Gestion de la VM Ubuntu, configuration de la sécurité, mise en place du monitoring (Prometheus, Grafana) et des sauvegardes.
  - Intégration et adaptation de PythonCMS, rédaction des tests, optimisation des performances.


### **Outils de collaboration**
- Communication : Slack, Microsoft Teams.
- Gestion de code : GitHub/GitLab.
- Documentation : Markdown, Confluence (si disponible).

---

## **3. Aspects techniques**

### **Moyens**
- **VM Ubuntu** : Machine virtuelle pré-paramétrée avec Docker, Python, Nginx et Certbot pour la gestion des certificats SSL.
- **CI/CD** : Utilisation de GitHub Actions ou GitLab CI pour automatiser les tests, la construction des images Docker et le déploiement.
- **Infrastructure as Code (IaC)** : Ansible pour la configuration de la VM et des services, Terraform pour le provisionnement (optionnel selon les besoins).
- **Monitoring** : Prometheus pour la collecte des métriques, Grafana pour la visualisation, et ELK (Elasticsearch, Logstash, Kibana) pour la centralisation des logs.

### **Outils et technologies**
- **Docker (via docker-compose)** (version 24.x) : Conteneurisation de l’application PythonCMS et de ses dépendances.
- **Ansible** : Automatisation de la configuration de la VM et des outils associés.
- **GitHub Actions** : Pipeline pour le déploiement continu.
- **Nginx** : Serveur web et reverse proxy pour la gestion du trafic HTTPS.
- **PythonCMS** : Application CMS déployé.

---

## **4. Product Backlog**

### Déterminer les besoins
- [x] Mettre en place un repo Gitlab
- [x] Dessiner le schéma d'infrastructure sur Excalidraw.io
- [ ] product_backlog.md
- [ ] Écrire le backlog sur Taiga
- [ ] Écrire le README.md

### Préparer mon infrastructure
- [ ] Coder un script pour déployer un VPS sur OVH avec OpenTofu

### Configurer mon environnement
- [ ] Rédiger les fichiers de configuration Ansible
- [ ] Rédiger le Dockerfile lié à notre CMS
- [ ] Rédiger une configuration CI/CD avec Github

### Automatiser mon déploiement
- [ ] Comment inclure la séparation dev et main ?
- [ ] Rédiger un fichier github cicd.yml avec test build deploy ?

### Mettre sur pied une supervision
- [ ] Brancher un node_exporter lié à mon app, ou autre ?
- [ ] Configurer prometheus et grafana au sein d'un rôle Ansible

### Inclure une séparation Dev et Prod dans mes fichiers de configuration
- [ ] Séparation dev et prod au niveau de l'application
- [ ] Dockerfile.dev et Dockerfile.prod + docker-compose.yml dev et prod
- [ ] Script de déploiement à la racine du projet (version dev et prod)
- [ ] .env.prod et .env.dev à la racine du projet (si nécessaire)
- [ ] Dossiers env/ et prod/ sur OpenTofu


### **User Stories et Tâches**

---

## **5. Infrastructure**

### **Schéma d’architecture**
![Schéma d’architecture][../checkpoint4_schema.png]