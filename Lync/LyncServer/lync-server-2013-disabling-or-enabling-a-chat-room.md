---
title: 'Lync Server 2013 : désactivation ou activation d’une salle de conversation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96ad55bd6396cdac9b30441eb8b41bebaba834ff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a>Désactivation ou activation d’une salle de conversation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-05_

Si le sujet d’une salle de conversation permanente n’est plus pertinent, vous pouvez désactiver la salle de conversation pour les utilisateurs. Lorsqu’une salle de conversation est désactivée, tous les membres sont immédiatement déconnectés de la salle. Une fois une salle de conversation désactivée, les utilisateurs ne peuvent ni la rejoindre, ni la trouver lors de recherches de salles de conversation.

Une salle de conversation désactivée peut être activée ultérieurement par un administrateur de conversation permanente. Si une salle de conversation est désactivée, sa liste d’adhésion et d’autres paramètres sont conservés. Si vous la réactivez, vous n’avez pas besoin de recréer manuellement les paramètres.

Si l’historique de la salle de conversation est conservé (la conservation de l’historique d’une salle de conversation est un paramètre facultatif lié à une catégorie qui s’applique à toutes les salles au sein de la catégorie ; par défaut, il est conservé, mais l’option peut être désactivée en définissant le paramètre **Activer l’historique des conversations** de la catégorie sur false), le contenu est conservé si la salle est désactivée. Toutefois, le contenu n’apparaîtra pas dans les recherches tant que la salle de conversation demeurera dans son état de désactivation. Si vous activez ensuite la salle de conversation, les utilisateurs peuvent alors rechercher des messages ayant été publiés avant la désactivation de la salle.

Pour plus d’informations sur la désactivation et l’activation des salles de conversation à l’aide de l’interface de ligne de commande Windows PowerShell, voir « gestion des salles » dans [Configuring persistent Chat Server by Using Windows PowerShell Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md). Pour désactiver une salle de conversation, utilisez une commande semblable à celle-ci :

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

Pour activer une salle de conversation, affectez la valeur false à la propriété Disabled :

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

Notez que les salles de conversation ne peuvent pas être activées ou désactivées à l’aide du panneau de configuration Lync Server.

Pour plus d’informations sur la configuration des salles de conversation, voir [configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) dans la documentation de déploiement.

</div>

<span> </span>

</div>

</div>

</div>

