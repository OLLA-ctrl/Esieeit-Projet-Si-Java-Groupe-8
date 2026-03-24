# Package Structure - Projet SI Java

## 🎯 Objectif

Organiser le projet en couches claires pour séparer les responsabilités et faciliter la maintenance.

---

## 📦 Structure des packages

com.esieeit.projetsi
├── domain
│   ├── model          # entités métier (User, Project, Task, Comment)
│   ├── enums          # TaskStatus, UserRole
│   └── exception      # exceptions métier (optionnel)
├── application
│   ├── service        # logique métier / cas d’usage
│   └── port           # interfaces (optionnel)
├── api
│   ├── controller     # endpoints REST
│   └── dto            # objets d’échange (request/response)
└── infrastructure
    ├── persistence    # base de données (JPA plus tard)
    └── config         # configuration (sécurité, ...)
---

## 🔒 Règles d’architecture

- api peut dépendre de application
- application peut dépendre de domain
- domain ne dépend de personne (pas de Spring dans domain)
- infrastructure dépend de application et domain

---

## 🧠 Principe

Chaque couche a un rôle précis :

- domain : contient le métier (cœur du projet)
- application : orchestre les cas d’usage
- api : expose les fonctionnalités (REST)
- infrastructure : gère la technique (base de données, config)

