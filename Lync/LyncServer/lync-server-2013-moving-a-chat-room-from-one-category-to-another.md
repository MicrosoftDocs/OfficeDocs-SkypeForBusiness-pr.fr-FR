---
title: "Lync Server 2013 : Déplacement d’une salle de conv. d’une cat. vers une autre"
TOCTitle: Déplacement d’une salle de conversation d’une catégorie vers une autre
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ215877(v=OCS.15)
ms:contentKeyID: 49297872
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déplacement d’une salle de conversation d’une catégorie vers une autre dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Nous recommandons de ne pas changer la catégorie d’une salle de conversation permanente une fois la salle de conversation créée. Cependant, si le gestionnaire de la salle de conversation à des privilèges **Créateur** dans une autre catégorie, il peut déplacer la salle d’une catégorie à une autre. La salle n’est pas supprimée et recréée. Seule son association dans la base de données est modifiée.

La modification d’une catégorie de salle de conversation est très rare. Une catégorie détermine l’appartenance autorisée pour la salle de conversation, donc si une salle de conversation est déplacée vers une autre catégorie, toutes les listes de contrôle d’accès système (SACLs) qui ne sont plus prises en charge par la nouvelle catégorie sont vidées. Par exemple, si un utilisateur était membre de la salle et qu’il n’est plus un **AllowedMember** dans la nouvelle catégorie, l’appartenance de la salle sera modifiée et l’utilisateur sera supprimé de la salle.

Pour plus d’informations sur le déplacement d’une salle de conversation avec l’interface de ligne de commande Windows PowerShell, reportez-vous à « Gestion des salles » dans [Configuration du serveur de conversation permanentte avec les applets de commande Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Pour plus d’informations sur la configuration des salles de configuration, reportez-vous à [Configuration des salles dans in Lync Server 2013](lync-server-2013-configure-rooms.md) dans la documentation de déploiement.

