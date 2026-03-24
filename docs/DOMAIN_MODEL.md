# Domain Model - Projet SI

## 👥 Acteurs

- User : utilisateur connecté qui gère ses projets et tâches
- Admin : administrateur qui supervise et gère les utilisateurs

---

## 🎯 Cas d’usage (Use Cases)

- UC-01 : En tant que User, je veux créer un projet afin d’organiser mon travail.
- UC-02 : En tant que User, je veux lister mes projets afin de voir mes données.
- UC-03 : En tant que User, je veux ajouter une tâche à un projet afin de planifier mon travail.
- UC-04 : En tant que User, je veux changer le statut d’une tâche afin de suivre l’avancement.
- UC-05 : En tant que User, je veux ajouter un commentaire à une tâche afin de collaborer.
- UC-06 : En tant que User, je veux modifier une tâche afin de corriger ses informations.
- UC-07 : En tant que User, je veux supprimer une tâche afin de nettoyer ma liste.
- UC-08 : En tant que Admin, je veux gérer les utilisateurs afin de superviser la plateforme.
---

## 🧱 Entités

- User
- Project
- Task
- Comment

---

## 🧬 Attributs

### User
- id : Long
- email : String
- username : String
- passwordHash : String
- role : UserRole
- createdAt : Instant

### Project
- id : Long
- name : String
- description : String
- ownerId : Long
- createdAt : Instant
- updatedAt : Instant

### Task
- id : Long
- title : String
- description : String
- status : TaskStatus
- projectId : Long
- assigneeId : Long
- createdAt : Instant
- updatedAt : Instant

### Comment
- id : Long
- content : String
- taskId : Long
- authorId : Long
- createdAt : Instant

---

## 🔢 Eums

### TaskStatus
- TODO
- IN_PROGRESS
- DONE
- ARCHIVED

### UserRole
- USER
- ADMIN

---

## 🔗 Relations

- User 1..N Project (un utilisateur possède plusieurs projets)
- Project 1..N Task (un projet contient plusieurs tâches)
- Task 1..N Comment (une tâche contient plusieurs commentaires)
- User 1..N Comment (un utilisateur écrit plusieurs commentaires)
- User 1..N Task (assignation des tâches)

---

## 📏 Règles métier

### User
- email obligatoire et unique
- username obligatoire et unique
- passwordHash obligatoire
- un utilisateur a au moins un rôle

### Project
- name obligatoire (1 à 80 caractères)
- un projet a exactement un owner
- un projet appartient à un utilisateur

### Task
- title obligatoire (1 à 120 caractères)
- status obligatoire
- une tâche appartient à un projet
- une tâche peut être assignée à un utilisateur

### Comment
- content obligatoire (1 à 500 caractères)
- un commentaire appartient à une tâche
- un commentaire a un auteur

---

## 🔄 Workflow TaskStatus

Transitions autorisées :

- TODO → IN_PROGRESS
- IN_PROGRESS → DONE
- DONE → ARCHIVED
- TODO → ARCHIVED

Transitions interdites :

- DONE → TODO

---

## 📊 Diagramme de classes

```mermaid
classDiagram

User {
  Long id
  String email
  String username
  String passwordHash
}

Project {
  Long id
  String name
  String description
}

Task {
  Long id
  String title
  String description
  TaskStatus status
}

Comment {
  Long id
  String content
}

User "1" --> "0..*" Project : owns
Project "1" --> "0..*" Task : contains
Task "1" --> "0..*" Comment : has
User "1" --> "0..*" Comment : writes
User "1" --> "0..*" Task : assigned
