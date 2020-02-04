---
title: 'Lync Server 2013 : Création ou modification d’une salle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bd0fdbce300f417764e093fec3acb8705b2d17b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a>Création ou modification d’une salle dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-03-19_

La configuration des salles de conversation permanente est généralement gérée par les utilisateurs. en règle générale, un administrateur de chat permanent ne peut pas configurer ou gérer des salles de conversation. Les applets de cmdlet Windows PowerShell pour gérer des salles sont disponibles uniquement pour les administrateurs **CsPersistentChatAdministrator** .

Les utilisateurs qui sont des **créateurs** dans une catégorie donnée peuvent utiliser le client Lync pour créer et gérer des salles. Les utilisateurs qui ont été désignés comme responsables pour une salle de conversation spécifique peuvent également effectuer une gestion en continu de la salle, comme la modification des propriétés de la salle ou de l’appartenance.

<div>


> [!TIP]  
> Ils peuvent également être créateurs de messages permanents et ne sont pas soumis aux restrictions imposées par les créateurs.



</div>

Si vous êtes un administrateur de chat permanent, vous pouvez également utiliser une interface utilisateur pour créer et gérer des salles de conversation au lieu d’utiliser des cmdlets Windows PowerShell. Pour ce faire, SIP : activez un administrateur pour le serveur de chat permanent, puis utilisez le client Lync pour créer et gérer des salles de conversation.

Si vous voulez créer un flux de travail de gestion des salles personnalisé pour vos utilisateurs, vous pouvez définir la propriété **RoomManagementUrl** sur votre configuration serveur de chat permanent pour rediriger les utilisateurs vers votre solution personnalisée du client Lync.

Pour plus d’informations sur la configuration des salles de conversation à l’aide de l’interface de ligne de commande Windows PowerShell, voir « gestion des salles » dans [configuration du serveur de chat permanent à l’aide d’applets de commande Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Pour plus d’informations sur la configuration des salles de conversation, voir [configurer des salles dans Lync Server 2013](lync-server-2013-configure-rooms.md) dans la documentation de déploiement.

<div>


> [!NOTE]  
> Serveur Chat permanent permet aux utilisateurs de créer et de gérer des salles de conversation pour un site spécifique. Toutefois, les utilisateurs ne peuvent pas créer ou gérer des salles de conversation sur d’autres sites au sein de la même topologie. Veillez à spécifier des créateurs et des gestionnaires de salle de conversation pour tous les sites de votre organisation.



</div>

<div>


> [!NOTE]  
> Les utilisateurs qui sont hébergés sur une unité de branchement Survivable Lync Server ne peuvent pas créer de nouvelles salles de conversation ou afficher la carte de la salle pour les salles existantes.



</div>

</div>

<span> </span>

</div>

</div>

</div>

