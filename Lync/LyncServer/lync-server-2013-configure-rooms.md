---
title: 'Lync Server 2013 : Configuration des salles'
TOCTitle: Configuration des salles
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205067(v=OCS.15)
ms:contentKeyID: 49297980
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des salles dans in Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-06_

La configuration des salles de conversation permanente est généralement effectuée par les utilisateurs ou d’autres équipes centrales à l’aide de l’interface de ligne de commande Windows PowerShell ; un administrateur ne gère pas les salles de conversation. Cependant, si vous devez créer et gérer des salles de conversation, vous pouvez utiliser l’interface de ligne de commande Windows PowerShell, ou vous ajouter en tant que membre d’une salle de conversation et utiliser le client Lync 2013.

Pour plus d’informations sur la configuration des salles de conversation à l’aide de interface de ligne de commande Windows PowerShell, reportez-vous à « Gestion des salles » dans [Configuration du serveur de conversation permanentte avec les applets de commande Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

## Gestion des données dans les salles de conversation

Le serveur de conversations permanentes permet aux utilisateurs de collaborer en publiant des messages dans des salles de conversation permanente. Les données sont persistantes sur le serveur et les membres de la salle peuvent y accéder, notamment aux données d’historique. Cependant, les utilisateurs avec des rôles différents ont un accès différent aux données persistantes, comme indiqué dans la liste suivante.

  - Les administrateurs peuvent supprimer du contenu précédant, par exemple, du contenu publié avant une certaine date, d’une salle de conversation afin que la base de données ne devienne pas ingérable de part sa taille. Ou, ils peuvent supprimer ou remplacer des messages qu’ils considèrent inappropriés pour une salle de conversation spécifique.

  - Les utilisateurs finaux, y compris les auteurs de messages, ne peuvent pas supprimer du contenu de salle de conversation.

  - Les gestionnaires de salle conversation peuvent désactiver des salles, mais ils ne peuvent pas les supprimer. Seuls les administrateurs peuvent supprimer une salle de conversation une fois qu’elle a été créée.

Quand un message est supprimé, vous ne pouvez pas annuler cette action. Cependant, les messages supprimés peuvent être restaurés si une sauvegarde a été faite. Si un serveur de conformité de conversation permanente est activé, les anciens messages sont persistants dans la base de données de conformité.

> [!NOTE]  
> Cette utilisation des données de salle de conversation s’applique à Lync Server 2013, API du serveur de conversations permanentes, sauf dans les cas où le rôle administrateur est impliqué. L’API de serveur de conversations permanentes ne peut pas être utilisée pour des opérations d’administrateur. Vous devez effectuer ces opérations dans Lync Server Management Shell.
