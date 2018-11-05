---
title: Sauvegarde de bases de données de conversation permanente
TOCTitle: Sauvegarde de bases de données de conversation permanente
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945646(v=OCS.15)
ms:contentKeyID: 53095510
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sauvegarde de bases de données de conversation permanente

 

_**Dernière rubrique modifiée :** 2013-02-17_

Le contenu des salles de conversation permanente est stocké dans la base de données de conversation permanente (Mgc.mdf). Il s’agit de données vitales qui doivent être sauvegardées régulièrement. Outre le contenu des salles de conversation, la base de données conversation permanente stocke également des informations sur les principaux (tels que les utilisateurs et les groupes), ainsi que les rôles et l’accès dont ils disposent aux salles de conversation et à leur contenu.

Il existe deux manières de sauvegarder des données conversation permanente

  - Sauvegarde SQL Server

  - L’applet de commande `Export-CsPersistentChatData`, qui exporte les données de conversation permanente dans un fichier

Les données créées à l’aide de la sauvegarde SQL Server nécessitent beaucoup plus d’espace disque (jusqu’à 20 fois plus) que celles créées par `Export-CsPersistentChatData`, mais la sauvegarde SQL Server est sans doute une procédure plus familière aux administrateurs.

