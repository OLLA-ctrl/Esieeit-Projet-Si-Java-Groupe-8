# Backlog Produit - Projet SI Java

## 🎯 Pitch produit

Notre application permet à un utilisateur de gérer ses projets et ses tâches facilement.
Elle s’adresse aux étudiants ou équipes souhaitant organiser leur travail.
Elle propose une API simple et structurée pour créer, suivre et modifier des tâches.

## Contraintes

- Projet Java (Gradle)
- API backend
- Authentification obligatoire (login/register)

## Acteurs
- Visiteur : utilisateur non connecté
- Utilisateur : utilisateur connecté
- Admin : supervision (bonus)

## 📦 Modules / Features

- A. Authentification & Profil
- B. Gestion des projets
- C. Gestion des tâches
- D. Recherche / Filtre
- E. Administration (bonus)

## 📋 User Stories

| ID | Module | User Story | Priorité | Estim |
|---|---|---|---|---|
| NOUS-01 | Auth | En tant que Visiteur, je veux créer un compte afin d’accéder à l’application. | Must | M |
| NOUS-02 | Auth | En tant que Utilisateur, je veux me connecter afin de retrouver mes projets. | Must | M |
| NOUS-03 | Auth | En tant que Utilisateur, je veux me déconnecter afin de sécuriser ma session. | Should | S |
| NOUS-04 | Auth | En tant que Utilisateur, je veux modifier mon profil afin de mettre à jour mes informations. | Should | M |
| NOUS-05 | Projet | En tant que Utilisateur, je veux créer un projet afin de structurer mon travail. | Must | M |
| NOUS-06 | Projet | En tant que Utilisateur, je veux lister mes projets afin de voir mes données. | Must | S |
| NOUS-07 | Projet | En tant que Utilisateur, je veux modifier un projet afin de corriger ses informations. | Must | M |
| NOUS-08 | Projet | En tant que Utilisateur, je veux supprimer un projet afin de nettoyer ma liste. | Should | S |
| NOUS-09 | Tâche | En tant que Utilisateur, je veux ajouter une tâche afin de planifier mon travail. | Must | M |
| NOUS-10 | Tâche | En tant que Utilisateur, je veux changer le statut d’une tâche afin de suivre l’avancement. | Must | S |
| NOUS-11 | Tâche | En tant que Utilisateur, je veux modifier une tâche afin de l’ajuster. | Should | M |
| NOUS-12 | Tâche | En tant que Utilisateur, je veux supprimer une tâche afin de supprimer les inutiles. | Should | S |
| NOUS-13 | Recherche | En tant que Utilisateur, je veux filtrer les tâches afin de me concentrer sur les urgences. | Nice | S |
| NOUS-14 | Recherche | En tant que Utilisateur, je veux rechercher une tâche afin de retrouver une information. | Nice | S |
| NOUS-15 | Admin | En tant que Admin, je veux lister les utilisateurs afin de superviser. | Nice | M |

## Critères d’acceptation

### NOUS-01 - Inscription

- Given je suis sur la page d'inscription
- When je saisis un email valide et un mot de passe valide
- Then mon compte est créé

### NOUS-05 - Créer projet

- Given je suis connecté
- When je crée un projet
- Then le projet est enregistré

### NOUS-09 - Ajouter tâche

- Given je suis connecté
- When j’ajoute une tâche
- Then elle apparaît dans la liste
