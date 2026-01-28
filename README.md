# ynov-ad-ds1

Cours Active Directory DS 1 : configuration initiale (59H00) pour Ynov
Ce repo contiendra ici toutes les ressources et fiches de cours concernant le cours Active Directory.

# Planning

## Jour 1

- Histoire de Windows Server
- Principes théoriques et organisation d'une entreprise sur un AD
- Partie chiante et théorique (mais nécessaire) sur le fonctionnement d'un AD
- On installe un Windows Server 2022 et un W11 optimisés
  - Explication également des différents hyperviseurs pour l'installation
- On lie les deux ensemble dans le même domaine
  - On passe le WS2022 en tant que contrôleur de domaine
  - On joint le W11 dans le domaine

## Jour 2

- Si on a pas fini d'intégrer au domaine le client, on le fait
- La hiérarchie d'un Active Directory
- Attributs d'un objet AD
- Un peu de Powershell pour lire des attributs
- Tiering d'un AD et sécurité
- On fait un joli AD bien hiérarchisé et on crée des éléments dedans 

## Jour 3

- Si c'est pas fini, on hiérarchise l'AD comme il faut

- Un peu de GPO avec le tiering

- Présentation des différents rôles d'un AD
  
  - Serveur de fichiers
  
  - DNS
  
  - DHCP
  
  - RemoteApps et Broker RDS

- On met en place un serveur de fichiers

- On définit un accès à certains dossiers à certains groupes autorisés

## Jour 4

- Explication de la délégation de contrôle

- Explication du problème du double hop

- On fait des p'tits scripts Powershell et on cherche à donner des droits mais pas trop

## Jour 5

- KAHOOT boum ça fait une note

- On explique les GPO, sacré morceau

- Les GPO essentielles

- Attention à ne pas avoir trop de GPO

- Granularité des GPO

- Pourquoi les GPO c'est vraiment pas fou en fait

- On fait des GPO simples

## Jour 6

- Explication des anciennes GPO de mots de passe

- Explication du nouveau système de mots de passe granulaires

- On fait des GPO plus complexes

## Jour 7

- On fait de l'automatisation

- On déploie des applis en RemoteApp

## Jour 8

- TP de montage d'un AD de A à Z en légende
  
  - Grille de notation donnée bien sûr

## Jour 9 (dernière demi-journée)

- On corrige le TP

- On fait ce que vous voulez
