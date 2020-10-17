---
title: 'Lync Server 2013 : suppression d’une catégorie ou d’une salle de conversation'
description: 'Lync Server 2013 : suppression d’une salle de conversation ou d’une catégorie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ef89802171a1eeca7de18ff0a4eb8eb3895f1b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555370"
---
# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a>Suppression d’une salle de conversation ou d’une catégorie dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Les salles de conversation permanente peuvent être supprimées. Si vous disposez d’une salle de conversation qui n’est plus utilisée, vous pouvez la désactiver. Pour plus d’informations, reportez-vous à [la rubrique désactivation ou activation d’une salle de conversation dans Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).

Un administrateur de conversation permanente peut rechercher des salles de conversation désactivées et peut régulièrement purger et supprimer définitivement les salles de conversation à l’aide de l’applet de commande Windows PowerShell, **Remove-applet cspersistentchatroom**.

Les catégories peuvent être supprimées. Toutefois, pour supprimer une catégorie, vous devez d’abord soit supprimer les salles de conversation subordonnées, soit déplacer toutes les salles de conversation vers une autre catégorie, ce qui laisse une catégorie vide pour permettre sa suppression. Le serveur de conversation permanente ne vous permet pas de supprimer une catégorie contenant des salles de conversation. Pour plus d’informations, reportez-vous à [la rubrique migration d’une salle de conversation d’une catégorie vers une autre dans Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).

Pour plus d’informations sur la suppression de catégories vides à l’aide de l’interface de ligne de commande Windows PowerShell, voir « gestion des salles » dans [Configuring persistent Chat Server by Using Windows PowerShell Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Pour plus d’informations sur les salles de conversation et les catégories, voir [configure rooms in Lync server 2013](lync-server-2013-configure-rooms.md) et [configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) dans la documentation de déploiement.

</div>

<span> </span>

</div>

</div>

</div>

