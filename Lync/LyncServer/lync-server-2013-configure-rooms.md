---
title: 'Lync Server 2013 : Configuration des salles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d08b7cb0146f96b151af021a63ef97a485a0a9dc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a>Configuration des salles dans in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-06_

La configuration des salles de conversation permanente est généralement gérée par des utilisateurs ou d’autres équipes centrales en utilisant l’interface de ligne de commande Windows PowerShell; en règle générale, un administrateur ne gère pas les salles de conversation. Toutefois, si vous devez créer et gérer des salles de conversation, vous pouvez utiliser l’interface de ligne de commande Windows PowerShell ou vous ajouter vous-même en tant que membre d’une salle de conversation et utiliser le client 2013 Lync.

Pour plus d’informations sur la configuration des salles de conversation à l’aide de l’interface de ligne de commande Windows PowerShell, voir «gestion des salles» dans [configuration du serveur de chat permanent à l’aide d’applets de commande Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

<div>

## <a name="managing-data-in-chat-rooms"></a>Gestion des données dans des salles de conversation

Le serveur Chat permanent permet aux utilisateurs de collaborer en publiant des messages dans des salles de conversation permanentes. Les données sont conservées sur le serveur, et les membres de la salle peuvent avoir accès aux données, y compris les données historiques. Toutefois, les utilisateurs dotés de rôles différents disposent d’un accès différent aux données persistantes, comme indiqué dans la liste suivante.

  - Les administrateurs peuvent supprimer un contenu précédant (par exemple, du contenu publié avant une certaine date) d’une salle de conversation afin de conserver une taille de base de données raisonnable. Ils peuvent ainsi supprimer ou remplacer les messages qui sont considérés comme inappropriés pour une salle de conversation particulière.

  - Les utilisateurs finaux, y compris les auteurs de messages, ne peuvent pas supprimer du contenu de salle de conversation.

  - Les gestionnaires de salle de conversation peuvent désactiver des salles, mais ne peuvent pas les supprimer. Seuls les administrateurs peuvent supprimer une salle de conversation après la création de celle-ci.

Quand un message est supprimé, vous ne pouvez pas annuler l’action. Toutefois, les messages supprimés peuvent être restaurés s’il y a une sauvegarde. Si un serveur de conformité des conversations permanent est activé, les anciens messages sont conservés dans la base de données de conformité.

<div>


> [!NOTE]  
> L’utilisation des données de salle de conversation s’applique aux applications Lync Server 2013 et aux API serveur de chat permanent, sauf si le rôle d’administrateur est impliqué. L’API serveur Chat permanent ne peut pas être utilisée pour effectuer les opérations de l’administrateur. Vous devez effectuer ces opérations dans Lync Server Management Shell.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

