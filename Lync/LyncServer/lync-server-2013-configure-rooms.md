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
ms.openlocfilehash: 0d6d5fabe5b465fd2ecab3cfee7474aa64160210
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a><span data-ttu-id="d59fa-102">Configurer des salles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d59fa-102">Configure rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d59fa-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="d59fa-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="d59fa-104">La configuration des salles de conversation permanente est généralement gérée par les utilisateurs ou d’autres équipes centrale à l’aide de l’interface de ligne de commande Windows PowerShell ; un administrateur ne gère généralement pas les salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="d59fa-104">Configuring Persistent Chat rooms is commonly handled by users or other central teams by using Windows PowerShell command-line interface; an administrator typically does not manage chat rooms.</span></span> <span data-ttu-id="d59fa-105">Toutefois, si vous devez créer et gérer des salles de conversation, vous pouvez utiliser l’interface de ligne de commande Windows PowerShell ou vous ajouter en tant que membre à une salle de conversation et utiliser le client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d59fa-105">However, if you have to create and manage chat rooms, you can use the Windows PowerShell command-line interface, or add yourself as a member to a chat room and use the Lync 2013 client.</span></span>

<span data-ttu-id="d59fa-106">Pour plus d’informations sur la configuration des salles de conversation à l’aide de l’interface de ligne de commande Windows PowerShell, voir « gestion des salles » dans [Configuring persistent Chat Server by Using Windows PowerShell Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="d59fa-106">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<div>

## <a name="managing-data-in-chat-rooms"></a><span data-ttu-id="d59fa-107">Gestion des données dans les salles de conversation</span><span class="sxs-lookup"><span data-stu-id="d59fa-107">Managing Data in Chat Rooms</span></span>

<span data-ttu-id="d59fa-108">Le serveur de conversation permanente permet aux utilisateurs de collaborer en publiant des messages dans des salles de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="d59fa-108">Persistent Chat Server lets users collaborate by posting messages into Persistent Chat rooms.</span></span> <span data-ttu-id="d59fa-109">Les données sont persistantes sur le serveur et les membres de la salle peuvent y accéder, notamment aux données d’historique.</span><span class="sxs-lookup"><span data-stu-id="d59fa-109">The data is persisted on the server, and members of the room can have access to the data, including historical data.</span></span> <span data-ttu-id="d59fa-110">Cependant, les utilisateurs avec des rôles différents ont un accès différent aux données persistantes, comme indiqué dans la liste suivante.</span><span class="sxs-lookup"><span data-stu-id="d59fa-110">However, users with different roles have different access to the persisted data, as outlined in the following list.</span></span>

  - <span data-ttu-id="d59fa-p103">Les administrateurs peuvent supprimer du contenu précédant, par exemple du contenu publié avant une certaine date, d’une salle de conversation afin que la base de données ne devienne pas ingérable de part sa taille. Ou, ils peuvent supprimer ou remplacer des messages qu’ils considèrent inappropriés pour une salle de conversation spécifique.</span><span class="sxs-lookup"><span data-stu-id="d59fa-p103">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large. Or, they can remove or replace messages that are considered inappropriate for a particular chat room.</span></span>

  - <span data-ttu-id="d59fa-113">Les utilisateurs finaux, y compris les auteurs de messages, ne peuvent pas supprimer du contenu de salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="d59fa-113">End users, including message authors, cannot delete content from any chat room.</span></span>

  - <span data-ttu-id="d59fa-p104">Les gestionnaires de salle conversation peuvent désactiver des salles, mais ils ne peuvent pas les supprimer. Seuls les administrateurs peuvent supprimer une salle de conversation une fois qu’elle a été créée.</span><span class="sxs-lookup"><span data-stu-id="d59fa-p104">Chat room managers can disable rooms, but cannot delete rooms. Only administrators can delete a chat room after it has been created.</span></span>

<span data-ttu-id="d59fa-116">Quand un message est supprimé, vous ne pouvez pas annuler cette action.</span><span class="sxs-lookup"><span data-stu-id="d59fa-116">When a message is deleted, you cannot undo the action.</span></span> <span data-ttu-id="d59fa-117">Cependant, les messages supprimés peuvent être restaurés si une sauvegarde a été faite.</span><span class="sxs-lookup"><span data-stu-id="d59fa-117">However, deleted messages can be restored if there is a backup.</span></span> <span data-ttu-id="d59fa-118">Si un serveur de conformité de conversation permanente est activé, les anciens messages sont conservés dans la base de données de conformité.</span><span class="sxs-lookup"><span data-stu-id="d59fa-118">If a Persistent Chat Compliance server is enabled, old messages are persisted in the compliance database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d59fa-119">Cette utilisation des données de salle de conversation s’applique à l’application de l’API serveur de conversation permanente de Lync Server 2013, à l’exception du cas où le rôle d’administrateur est impliqué.</span><span class="sxs-lookup"><span data-stu-id="d59fa-119">This chat room data usage applies to the Lync Server 2013, Persistent Chat Server API application, except for the case when the administrator role is involved.</span></span> <span data-ttu-id="d59fa-120">L’API de serveur de conversation permanente ne peut pas être utilisée pour effectuer les opérations de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="d59fa-120">The Persistent Chat Server API cannot be used to do any of the administrator’s operations.</span></span> <span data-ttu-id="d59fa-121">Vous devez effectuer ces opérations dans Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d59fa-121">You must perform these operations in the Lync Server Management Shell.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

