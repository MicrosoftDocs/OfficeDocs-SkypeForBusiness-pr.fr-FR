---
title: 'Lync Server 2013 : création ou modification d’une nouvelle salle'
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
ms.openlocfilehash: d5c6292b38bbc02eb2230b8746ec331b7bd1e6ec
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a>Création ou modification d’une nouvelle salle dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-03-19_

La configuration des salles de conversation permanente est généralement gérée par les utilisateurs ; un administrateur de conversation permanente ne configure pas ou ne gère généralement pas les salles de conversation. Les applets de commande Windows PowerShell pour gérer les salles sont disponibles uniquement pour les administrateurs **CsPersistentChatAdministrator** .

Les utilisateurs qui sont des **créateurs** dans une catégorie donnée peuvent utiliser le client Lync pour créer et gérer des salles. Les utilisateurs qui ont été désignés comme responsables d’une salle de conversation spécifique peuvent également assurer la gestion continue de la salle, par exemple modifier ses propriétés ou son appartenance.

<div>


> [!TIP]  
> Les administrateurs de conversation permanente peuvent également être créateurs, et ils ne sont pas soumis aux restrictions imposées aux créateurs.



</div>

Si vous êtes un administrateur de conversation permanente, vous pouvez également utiliser une interface utilisateur pour créer et gérer des salles de conversation au lieu d’utiliser des applets de commande Windows PowerShell. Pour ce faire, activez un administrateur pour le serveur de conversation permanente, puis utilisez le client Lync pour créer et gérer des salles de conversation.

Si vous souhaitez créer un flux de travail de gestion de salle personnalisé pour vos utilisateurs, vous pouvez définir la propriété **RoomManagementUrl** sur votre configuration de serveur de conversation permanente afin de rediriger les utilisateurs vers votre solution personnalisée à partir du client Lync.

Pour plus d’informations sur la configuration des salles de conversation à l’aide de l’interface de ligne de commande Windows PowerShell, voir « gestion des salles » dans [Configuring persistent Chat Server by Using Windows PowerShell Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Pour plus d’informations sur la configuration des salles de conversation, voir [configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) dans la documentation de déploiement.

<div>


> [!NOTE]  
> Le serveur de conversation permanente permet aux utilisateurs de créer et de gérer une salle de conversation pour un site spécifique. Toutefois, les utilisateurs ne peuvent pas créer ou gérer des salles de conversation sur d’autres sites au sein de la même topologie. Veillez à spécifier des créateurs et des responsables de salle de conversation pour tous les sites de votre organisation.



</div>

<div>


> [!NOTE]  
> Les utilisateurs hébergés sur une appliance Survivable Branch Lync Server ne peuvent pas créer de nouvelles salles de conversation ni afficher la carte de salle pour les salles existantes.



</div>

</div>

<span> </span>

</div>

</div>

</div>

