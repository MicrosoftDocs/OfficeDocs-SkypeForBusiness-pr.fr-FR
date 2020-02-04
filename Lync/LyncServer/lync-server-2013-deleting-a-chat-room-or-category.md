---
title: 'Lync Server 2013 : Suppression d’une catégorie ou d’une salle de conversation'
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
ms.openlocfilehash: 74cf41679a21612e67c4a793c09ae3484377ef6e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a>Suppression d’une catégorie ou d’une salle de conversation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Les salles de conversation permanente peuvent être supprimées. Si vous disposez d’une salle de conversation qui n’est plus utilisée, vous pouvez la désactiver. Pour plus d’informations, reportez-vous à [désactivation ou activation d’une salle de conversation dans Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).

Un administrateur de chat permanent peut interroger des salles de conversation désactivées et peut périodiquement effacer et supprimer définitivement les salles de conversation, à l’aide de l’applet de requête Windows PowerShell, **Remove-CsPersistentChatRoom**.

Les catégories peuvent être supprimées. Toutefois, pour supprimer une catégorie, vous devez d’abord supprimer toutes les salles de conversation ou les déplacer vers une nouvelle catégorie, en laissant une catégorie vide pour suppression. Le serveur Chat permanent ne vous permet pas de supprimer une catégorie contenant des salles de conversation. Pour plus d’informations, reportez-vous à [déplacement d’une salle de conversation d’une catégorie à une autre dans Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).

Pour plus d’informations sur la suppression des catégories vides à l’aide de l’interface de ligne de commande Windows PowerShell, voir « gestion des salles » dans [configuration du serveur de chat permanent à l’aide d’applets de commande Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Pour plus d’informations sur les salles de conversation et les catégories, voir [configurer des salles dans Lync server 2013](lync-server-2013-configure-rooms.md) et [configurer les catégories dans Lync Server 2013](lync-server-2013-configure-categories.md) dans la documentation de déploiement.

</div>

<span> </span>

</div>

</div>

</div>

