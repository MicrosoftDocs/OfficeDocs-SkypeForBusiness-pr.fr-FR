---
title: 'Lync Server 2013 : suppression d’un message ou purge de messages obsolètes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a message or purging obsolete messages
ms:assetid: 3f0c612d-6dfd-41a4-a5fe-5ff3448eb0ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215874(v=OCS.15)
ms:contentKeyID: 48706000
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db44ca77d217c1b7bc0bc4d05c56cb9b6ff99ea4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525451"
---
# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a><span data-ttu-id="d4982-102">Suppression d’un message ou purge de messages obsolètes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4982-102">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4982-103">_**Dernière modification de la rubrique :** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="d4982-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="d4982-104">Un administrateur de conversation permanente peut supprimer un message d’une salle de conversation permanente (et, éventuellement, le remplacer par un autre message).</span><span class="sxs-lookup"><span data-stu-id="d4982-104">A Persistent Chat administrator can delete a message from a Persistent Chat room (and, optionally, can replace it with another message).</span></span> <span data-ttu-id="d4982-105">De même, les administrateurs peuvent vider les messages obsolètes dans le cadre de la maintenance régulière afin de limiter la croissance de la base de données.</span><span class="sxs-lookup"><span data-stu-id="d4982-105">Administrators can also purge obsolete messages as part of ongoing maintenance, to minimize growth of the database.</span></span> <span data-ttu-id="d4982-106">Par exemple, cette commande Windows PowerShell supprime tous les messages de la salle de conversation ITChatRoom qui ont été publiés par l’utilisateur kenmyer@litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="d4982-106">For example, this Windows PowerShell command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@litwareinc.com:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="d4982-107">Et cet exemple remplace les messages supprimés par la remarque indiquant que le message n’est plus disponible :</span><span class="sxs-lookup"><span data-stu-id="d4982-107">And this example replaces any removed messages with the note that the message is no longer available:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

<span data-ttu-id="d4982-108">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-cspersistentchatmessage ne](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) .</span><span class="sxs-lookup"><span data-stu-id="d4982-108">For more information, see the help topic for the [Remove-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

