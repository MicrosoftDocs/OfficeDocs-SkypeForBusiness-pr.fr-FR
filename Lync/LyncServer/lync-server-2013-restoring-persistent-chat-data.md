---
title: Restauration de données de conversation permanente
TOCTitle: Restauration de données de conversation permanente
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945649(v=OCS.15)
ms:contentKeyID: 53095520
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restauration de données de conversation permanente

 

_**Dernière rubrique modifiée :** 2013-02-18_

Le contenu des salles de conversation permanente est stocké dans la base de données de conversation permanente (mgc.mdf). Il s’agit de données vitales qui doivent être sauvegardées régulièrement. Outre le contenu des salles de conversation, les principaux (tels que les utilisateurs et les groupes), ainsi que les rôles et l’accès dont ils disposent aux salles de conversation et à leur contenu, sont également stockés dans la base de données conversation permanente.

La façon dont vous restaurez vos données conversation permanente dépend de la méthode utilisée pour les sauvegarder.

  - Si vous avez utilisé des procédures de sauvegarde SQL Server, vous devez utiliser des procédures de restauration SQL Server.

  - Si vous avez utilisé l’applet de commande **Export-CsPersistentChatData** pour sauvegarder les données de conversation permanente, vous devez utiliser l’applet de commande **Import-CsPersistentChatData** pour restaurer les données.

