---
title: 'Lync Server 2013 : configuration des salles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3521e533dee1ff995fae417b8a7f29a75a77ac63
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a>Configurer des salles dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

La configuration des salles de conversation permanente est généralement gérée par les utilisateurs ou d’autres équipes centrale à l’aide de l’interface de ligne de commande Windows PowerShell ; un administrateur ne gère généralement pas les salles de conversation. Toutefois, si vous devez créer et gérer des salles de conversation, vous pouvez utiliser l’interface de ligne de commande Windows PowerShell ou vous ajouter en tant que membre à une salle de conversation et utiliser le client Lync 2013.

Pour plus d’informations sur la configuration des salles de conversation à l’aide de l’interface de ligne de commande Windows PowerShell, voir « gestion des salles » dans [Configuring persistent Chat Server by Using Windows PowerShell Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

<div>

## <a name="managing-data-in-chat-rooms"></a>Gestion des données dans les salles de conversation

Le serveur de conversation permanente permet aux utilisateurs de collaborer en publiant des messages dans des salles de conversation permanente. Les données sont persistantes sur le serveur et les membres de la salle peuvent y accéder, notamment aux données d’historique. Cependant, les utilisateurs avec des rôles différents ont un accès différent aux données persistantes, comme indiqué dans la liste suivante.

  - Les administrateurs peuvent supprimer du contenu précédant, par exemple du contenu publié avant une certaine date, d’une salle de conversation afin que la base de données ne devienne pas ingérable de part sa taille. Ou, ils peuvent supprimer ou remplacer des messages qu’ils considèrent inappropriés pour une salle de conversation spécifique.

  - Les utilisateurs finaux, y compris les auteurs de messages, ne peuvent pas supprimer du contenu de salle de conversation.

  - Les gestionnaires de salle conversation peuvent désactiver des salles, mais ils ne peuvent pas les supprimer. Seuls les administrateurs peuvent supprimer une salle de conversation une fois qu’elle a été créée.

Quand un message est supprimé, vous ne pouvez pas annuler cette action. Cependant, les messages supprimés peuvent être restaurés si une sauvegarde a été faite. Si un serveur de conformité de conversation permanente est activé, les anciens messages sont conservés dans la base de données de conformité.

<div>


> [!NOTE]  
> Cette utilisation des données de salle de conversation s’applique à l’application de l’API serveur de conversation permanente de Lync Server 2013, à l’exception du cas où le rôle d’administrateur est impliqué. L’API de serveur de conversation permanente ne peut pas être utilisée pour effectuer les opérations de l’administrateur. Vous devez effectuer ces opérations dans Lync Server Management Shell.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

