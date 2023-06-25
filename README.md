# Rapport de la Partie Backend de l'Application Web "Digital Banking"

Ce document décrit la structure et la mise en œuvre de la partie backend de l'application "Digital Banking", une application de gestion de comptes bancaires construite avec le framework Spring Boot.

## Table des matières

1. [Architecture Backend](#architecture-backend)
2. [Création du Projet](#création-du-projet)
3. [Couche Service, DTOs et RestController](#couche-service-dtos-et-restcontroller)
4. [Conclusion](#conclusion)

## Architecture Backend

L'architecture backend de "Digital Banking" suit une structure multicouche, favorisant une séparation claire des responsabilités, facilitant la maintenance, et permettant l'évolutivité. Les couches principales sont :

- *Couche DAO (Data Access Object)* : Gère l'accès aux données via les interfaces JPA Repository qui fournissent des opérations essentielles pour interagir avec les entités persistantes.
- *Entités JPA* : Les entités JPA, qui correspondent aux objets métier de l'application, sont mappées aux tables de la base de données. Les entités de "Digital Banking" incluent :
  - Customer: Représentant un client de la banque.
  - BankAccount: Classe abstraite représentant un compte bancaire. Les sous-classes de BankAccount sont CurrentAccount et SavingAccount.
  - CurrentAccount: Représentant un compte courant avec une autorisation de découvert.
  - SavingAccount: Représentant un compte épargne avec un taux d'intérêt.
  - AccountOperation: Représentant une opération effectuée sur un compte bancaire.
- *Couche Service* : Héberge la logique métier de l'application, offrant des services pour effectuer des opérations sur les comptes bancaires.
- *DTOs (Data Transfer Objects)* : Ces objets permettent le transfert de données entre les différentes couches de l'application.
- *RestController* : Ces composants exposent les services de l'application via des API REST.
- *Exceptions métier* : Utilisées pour gérer les erreurs spécifiques à l'application.

## Création du Projet

Dans cette section, nous discutons de la création du projet, incluant les entités et les interfaces JPA.

## Couche Service, DTOs et RestController

La couche Service abrite la logique métier, les DTOs aident au transfert de données entre les couches, et le RestController expose les services via des API REST.

## Conclusion

L'architecture backend de l'application "Digital Banking", qui est basée sur Spring Boot, suit une structure multicouche pour une meilleure séparation des responsabilités. L'application est capable de gérer les comptes bancaires, effectuer des opérations et manipuler les données grâce à l'interaction entre les couches DAO, Service, et RestController. Les entités JPA sont utilisées pour représenter les objets métier et sont mappées aux tables de la base de données, tandis que les DTOs servent à transférer les données entre les différentes couches.

L'application utilise pleinement Spring Boot pour simplifier le développement, la configuration, et la gestion. De plus, l'utilisation des annotations (@Entity, @Repository, @Service, @RestController) définissent clairement le rôle des différents composants.

Grâce à cette architecture, il est possible d'ajouter de nouvelles fonctionnalités à l'application Digital Banking tout en maintenant un code clair et modulaire.
