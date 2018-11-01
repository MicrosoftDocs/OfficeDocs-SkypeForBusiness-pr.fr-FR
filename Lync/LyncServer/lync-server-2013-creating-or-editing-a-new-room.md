---
title: 'Lync Server 2013 : Création ou modification d’une salle'
TOCTitle: Création ou modification d’une salle
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ215880(v=OCS.15)
ms:contentKeyID: 49298477
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Création ou modification d’une salle dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-19_

La configuration des salles de conversation permanente est couramment gérée par les utilisateurs ; en règle générale, la configuration et la gestion des salles de conversation ne sont pas assurées par un administrateur de conversation permanente. Les applets de commande Windows PowerShell de gestion des salles sont disponibles uniquement aux administrateurs **CsPersistentChatAdministrator**.

Les utilisateurs qui sont des **Créateurs** dans une catégorie donnée peuvent utiliser le client Lync pour créer et gérer des salles. Les utilisateurs qui ont été désignés comme responsables d’une salle de conversation spécifique peuvent également assurer la gestion continue de la salle, par exemple, modifier ses propriétés ou son appartenance.

> [!TIP]  
> Les administrateurs de conversation permanente peuvent également être des Créateurs et ne sont pas soumis aux restrictions imposées sur les Créateurs.

Si vous êtes administrateur de conversation permanente, vous pouvez éventuellement avoir recours à une interface utilisateur pour créer et gérer des salles de conversation plutôt qu’utiliser des applets de commande Windows PowerShell. Pour cela, activez un administrateur pour SIP pour la serveur de conversations permanentes, puis utilisez le client Lync pour créer et gérer les salles de conversation.

Si vous souhaitez créer un flux de travail de gestion de salle personnalisé pour vos utilisateurs, vous pouvez définir la propriété **RoomManagementUrl** sur votre configuration de serveur de conversations permanentes de façon à rediriger les utilisateurs vers votre solution personnalisée à partir du client Lync.

Pour plus d’informations sur la configuration des salles de conversation à l’aide de interface de ligne de commande Windows PowerShell, reportez-vous à « Gestion des salles » dans [Configuration du serveur de conversation permanentte avec les applets de commande Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Pour plus d’informations sur la configuration des salles de configuration, reportez-vous à [Configuration des salles dans in Lync Server 2013](lync-server-2013-configure-rooms.md) dans la documentation de déploiement.

