---
title: Processus de planification des grandes réunions
TOCTitle: Processus de planification des grandes réunions
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205334(v=OCS.15)
ms:contentKeyID: 49299063
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Processus de planification des grandes réunions

 

_**Dernière rubrique modifiée :** 2012-10-22_

Comme une seule grande réunion à la fois est prise en charge sur le pool de grandes réunions, il est recommandé d’implémenter un processus de planification de grandes réunions afin d’empêcher les conflits de grandes réunions. L’objectif d’un tel processus de planification est de faciliter la configuration de grandes réunions. Cette fonctionnalité n’est pas fournie directement par les clients Lync Server ou Lync Server. Une façon d’implémenter un tel processus consiste à utiliser le système de tickets de l’équipe de support de votre organisation le cas échéant.

Pour les organisateurs de grandes réunions, la planification d’une grande réunion implique de suivre les étapes suivantes :

1.  L’organisateur de réunion ou le délégué détermine l’heure, la durée et la taille d’une prochaine réunion, en plus de la liste de présentateurs. Si la taille de réunion anticipée dépasse 250 utilisateurs ou pour garantir la meilleure expérience pour une réunion de moins de 250 utilisateurs, l’organisateur ou le délégué soumet une demande pour une grande réunion.

2.  Le personnel en charge de la planification vérifie si la date et l’heure demandées sont disponibles. Comme nous ne prenons en charge qu’une seule grande réunion à la fois sur le pool dédié, le personnel de planification doit vérifier le calendrier de grandes réunions pour déterminer si une autre réunion est planifiée pour la date et l’heure demandées. Si l’heure demandée est disponible, le personnel approuve la demande de réunion.

3.  Si la demande est approuvée, le personnel de planification (à l’aide des informations d’identification sur le pool dédié) utilise le complément de réunion en ligne pour Lync 2013 avec Outlook pour configurer une réunion sur le pool de grandes réunions dédié. L’URL à utiliser pour participer à la réunion est fournie par le demandeur dans le cadre de l’avis d’approbation.

4.  L’organisateur de réunion ou le délégué utilise Outlook pour planifier la prochaine réunion, en ajoutant à l’invitation à la réunion l’URL pour y participer. L’organisateur de réunion ou le délégué spécifie alors les utilisateurs à inviter et envoie les invitations à la réunion.
    
    La figure suivante illustre un flux de travail de demande et d’approbation typique pour la planification de grandes réunions.
    
    ![Workflow de planification de conférence](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "Workflow de planification de conférence")

