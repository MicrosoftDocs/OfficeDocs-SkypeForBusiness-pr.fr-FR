---
title: 'Lync Server 2013 : Désactivation ou activation d’une salle de conversation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f89862b4f7e38a637fa183641f8cdc75e0491379
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a>Désactivation ou activation d’une salle de conversation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-02-05_

Si le sujet d’une salle de conversation permanente n’est plus pertinent, vous pouvez rendre la salle de conversation non disponible pour les utilisateurs en la désactivant. Lorsqu’une salle de conversation est désactivée, tous les membres sont immédiatement déconnectés de la salle. Une fois qu’une salle de conversation est désactivée, les utilisateurs ne peuvent ni la rejoindre, ni la trouver lors de recherches de salles de conversation.

Une salle de conversation désactivée peut être activée ultérieurement par un administrateur de chat permanent. Si une salle de conversation est désactivée, sa liste d’adhésion et d’autres paramètres sont conservés. Si vous réactivez la salle, vous n’avez pas besoin de recréer les paramètres manuellement.

Si l’historique de la salle de conversation persiste (la persistance de l’historique des salles de conversation est un paramètre facultatif sur une catégorie qui s’applique à toutes les pièces au sein de la catégorie; la valeur par défaut est conservée, mais peut être désactivée en définissant l' **historique de conversation** de la catégorie sur faux), le contenu est conservé lorsque la salle de conversation est désactivée. Cependant, le contenu ne s’affichera pas dans les recherches tant que la salle de conversation demeurera désactivée. Si vous activez ensuite la salle de conversation, les utilisateurs peuvent alors rechercher des messages ayant été publiés avant la désactivation de la salle.

Pour plus d’informations sur la désactivation et l’activation de salles de conversation à l’aide de l’interface de ligne de commande Windows PowerShell, voir «gestion des salles» dans [configuration du serveur de chat permanent à l’aide des applets de commande Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md). Pour désactiver une salle de conversation, utilisez une commande semblable à celle-ci:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

Pour activer une salle de conversation, définissez la propriété disabled sur false:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

Notez que les salles de conversation ne peuvent pas être activées ou désactivées à l’aide du panneau de configuration de Lync Server.

Pour plus d’informations sur la configuration des salles de conversation, voir [configurer des salles dans Lync Server 2013](lync-server-2013-configure-rooms.md) dans la documentation de déploiement.

</div>

<span> </span>

</div>

</div>

</div>

