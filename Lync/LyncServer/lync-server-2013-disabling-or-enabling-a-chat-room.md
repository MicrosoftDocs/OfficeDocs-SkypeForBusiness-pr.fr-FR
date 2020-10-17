---
title: 'Lync Server 2013 : désactivation ou activation d’une salle de conversation'
description: 'Lync Server 2013 : désactivation ou activation d’une salle de conversation.'
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
ms.openlocfilehash: 9b81ce2614cebcf554c0390369068d8fd8b8f932
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568150"
---
# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a><span data-ttu-id="5f72a-103">Désactivation ou activation d’une salle de conversation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f72a-103">Disabling or enabling a chat room in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f72a-104">_**Dernière modification de la rubrique :** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="5f72a-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="5f72a-105">Si le sujet d’une salle de conversation permanente n’est plus pertinent, vous pouvez désactiver la salle de conversation pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="5f72a-105">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="5f72a-106">Lorsqu’une salle de conversation est désactivée, tous les membres sont immédiatement déconnectés de la salle.</span><span class="sxs-lookup"><span data-stu-id="5f72a-106">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="5f72a-107">Une fois une salle de conversation désactivée, les utilisateurs ne peuvent ni la rejoindre, ni la trouver lors de recherches de salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="5f72a-107">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>

<span data-ttu-id="5f72a-108">Une salle de conversation désactivée peut être activée ultérieurement par un administrateur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="5f72a-108">A disabled chat room can be enabled later by a Persistent Chat administrator.</span></span> <span data-ttu-id="5f72a-109">Si une salle de conversation est désactivée, sa liste d’adhésion et d’autres paramètres sont conservés.</span><span class="sxs-lookup"><span data-stu-id="5f72a-109">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="5f72a-110">Si vous la réactivez, vous n’avez pas besoin de recréer manuellement les paramètres.</span><span class="sxs-lookup"><span data-stu-id="5f72a-110">If you enable the room again, you do not need to manually re-create the settings.</span></span>

<span data-ttu-id="5f72a-p103">Si l’historique de la salle de conversation est conservé (la conservation de l’historique d’une salle de conversation est un paramètre facultatif lié à une catégorie qui s’applique à toutes les salles au sein de la catégorie ; par défaut, il est conservé, mais l’option peut être désactivée en définissant le paramètre **Activer l’historique des conversations** de la catégorie sur false), le contenu est conservé si la salle est désactivée. Toutefois, le contenu n’apparaîtra pas dans les recherches tant que la salle de conversation demeurera dans son état de désactivation. Si vous activez ensuite la salle de conversation, les utilisateurs peuvent alors rechercher des messages ayant été publiés avant la désactivation de la salle.</span><span class="sxs-lookup"><span data-stu-id="5f72a-p103">If the chat room’s history persists (chat room history persistence is an optional setting on a category that applies to all rooms within the category; the default is that it is persisted, but can be turned off by setting the category’s **Enable Chat History** to false), the content is preserved when the chat room is disabled. However, that content will not appear in searches during the time that the chat room remains in a disabled state. If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span>

<span data-ttu-id="5f72a-114">Pour plus d’informations sur la désactivation et l’activation des salles de conversation à l’aide de l’interface de ligne de commande Windows PowerShell, voir « gestion des salles » dans [Configuring persistent Chat Server by Using Windows PowerShell Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="5f72a-114">For details about disabling and enabling chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span> <span data-ttu-id="5f72a-115">Pour désactiver une salle de conversation, utilisez une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="5f72a-115">To disable a chat room, use a command similar to this:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

<span data-ttu-id="5f72a-116">Pour activer une salle de conversation, affectez la valeur false à la propriété Disabled :</span><span class="sxs-lookup"><span data-stu-id="5f72a-116">To enabled a chat room, set the Disabled property to False:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

<span data-ttu-id="5f72a-117">Notez que les salles de conversation ne peuvent pas être activées ou désactivées à l’aide du panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f72a-117">Note that chat rooms cannot be enabled or disabled by using the Lync Server Control Panel.</span></span>

<span data-ttu-id="5f72a-118">Pour plus d’informations sur la configuration des salles de conversation, voir [configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="5f72a-118">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

