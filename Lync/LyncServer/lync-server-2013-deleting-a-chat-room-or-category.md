---
title: 'Lync Server 2013 : Suppression d’une catégorie ou d’une salle de conversation'
TOCTitle: Suppression d’une catégorie ou d’une salle de conversation
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ215881(v=OCS.15)
ms:contentKeyID: 49298538
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Suppression d’une catégorie ou d’une salle de conversation dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-11-01_

Les salles de conversation permanente peuvent être supprimées. Si vous disposez d’une salle de conversation qui n’est plus utilisée, vous pouvez la désactiver. Pour plus d’informations, reportez-vous à [Désactivation ou activation d’une salle de conversation dans Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).

Un administrateur de conversation permanente peut rechercher les salles de conversation désactivées. Il peut également vider régulièrement et supprimer définitivement les salles de conversation, à l’aide de l’applet de commande Windows PowerShell**Remove-CsPersistentChatRoom**.

Les catégories peuvent être supprimées. Cependant, pour supprimer une catégorie, vous devez d’abord soit supprimer les salles de conversation subordonnées, soit déplacer toutes les salles de conversation vers une autre catégorie, ce qui laisse une catégorie vide pour permettre sa suppression. Le serveur de conversations permanentes ne vous permet pas de supprimer une catégorie qui contient des salles de conversation. Pour plus d’informations, reportez-vous à [Déplacement d’une salle de conversation d’une catégorie vers une autre dans Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).

Pour plus d’informations sur la suppression de catégories vides à l’aide de l’interface de ligne de commande Windows PowerShell, reportez-vous à « Gestion des salles » dans [Configuration du serveur de conversation permanentte avec les applets de commande Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Pour plus d’informations sur les salles de conversation et les catégories, reportez-vous à [Configuration des salles dans in Lync Server 2013](lync-server-2013-configure-rooms.md) et [Configuration des catégories dans Lync Server 2013](lync-server-2013-configure-categories.md) dans la documentation du déploiement.

