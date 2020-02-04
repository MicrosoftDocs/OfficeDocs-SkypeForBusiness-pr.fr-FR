---
title: 'Lync Server 2013 : Configuration des salles'
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
ms.openlocfilehash: 06fea4fcda27eaedd671d833a4f53ed0ddec67c6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a><span data-ttu-id="60af6-102">Configuration des salles dans in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60af6-102">Configure rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60af6-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="60af6-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="60af6-104">La configuration des salles de conversation permanente est généralement gérée par des utilisateurs ou d’autres équipes centrales en utilisant l’interface de ligne de commande Windows PowerShell ; en règle générale, un administrateur ne gère pas les salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="60af6-104">Configuring Persistent Chat rooms is commonly handled by users or other central teams by using Windows PowerShell command-line interface; an administrator typically does not manage chat rooms.</span></span> <span data-ttu-id="60af6-105">Toutefois, si vous devez créer et gérer des salles de conversation, vous pouvez utiliser l’interface de ligne de commande Windows PowerShell ou vous ajouter vous-même en tant que membre d’une salle de conversation et utiliser le client 2013 Lync.</span><span class="sxs-lookup"><span data-stu-id="60af6-105">However, if you have to create and manage chat rooms, you can use the Windows PowerShell command-line interface, or add yourself as a member to a chat room and use the Lync 2013 client.</span></span>

<span data-ttu-id="60af6-106">Pour plus d’informations sur la configuration des salles de conversation à l’aide de l’interface de ligne de commande Windows PowerShell, voir « gestion des salles » dans [configuration du serveur de chat permanent à l’aide d’applets de commande Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="60af6-106">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<div>

## <a name="managing-data-in-chat-rooms"></a><span data-ttu-id="60af6-107">Gestion des données dans des salles de conversation</span><span class="sxs-lookup"><span data-stu-id="60af6-107">Managing Data in Chat Rooms</span></span>

<span data-ttu-id="60af6-108">Le serveur Chat permanent permet aux utilisateurs de collaborer en publiant des messages dans des salles de conversation permanentes.</span><span class="sxs-lookup"><span data-stu-id="60af6-108">Persistent Chat Server lets users collaborate by posting messages into Persistent Chat rooms.</span></span> <span data-ttu-id="60af6-109">Les données sont conservées sur le serveur, et les membres de la salle peuvent avoir accès aux données, y compris les données historiques.</span><span class="sxs-lookup"><span data-stu-id="60af6-109">The data is persisted on the server, and members of the room can have access to the data, including historical data.</span></span> <span data-ttu-id="60af6-110">Toutefois, les utilisateurs dotés de rôles différents disposent d’un accès différent aux données persistantes, comme indiqué dans la liste suivante.</span><span class="sxs-lookup"><span data-stu-id="60af6-110">However, users with different roles have different access to the persisted data, as outlined in the following list.</span></span>

  - <span data-ttu-id="60af6-111">Les administrateurs peuvent supprimer un contenu précédant (par exemple, du contenu publié avant une certaine date) d’une salle de conversation afin de conserver une taille de base de données raisonnable.</span><span class="sxs-lookup"><span data-stu-id="60af6-111">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="60af6-112">Ils peuvent ainsi supprimer ou remplacer les messages qui sont considérés comme inappropriés pour une salle de conversation particulière.</span><span class="sxs-lookup"><span data-stu-id="60af6-112">Or, they can remove or replace messages that are considered inappropriate for a particular chat room.</span></span>

  - <span data-ttu-id="60af6-113">Les utilisateurs finaux, y compris les auteurs de messages, ne peuvent pas supprimer du contenu de salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="60af6-113">End users, including message authors, cannot delete content from any chat room.</span></span>

  - <span data-ttu-id="60af6-114">Les gestionnaires de salle de conversation peuvent désactiver des salles, mais ne peuvent pas les supprimer.</span><span class="sxs-lookup"><span data-stu-id="60af6-114">Chat room managers can disable rooms, but cannot delete rooms.</span></span> <span data-ttu-id="60af6-115">Seuls les administrateurs peuvent supprimer une salle de conversation après la création de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="60af6-115">Only administrators can delete a chat room after it has been created.</span></span>

<span data-ttu-id="60af6-116">Quand un message est supprimé, vous ne pouvez pas annuler l’action.</span><span class="sxs-lookup"><span data-stu-id="60af6-116">When a message is deleted, you cannot undo the action.</span></span> <span data-ttu-id="60af6-117">Toutefois, les messages supprimés peuvent être restaurés s’il y a une sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="60af6-117">However, deleted messages can be restored if there is a backup.</span></span> <span data-ttu-id="60af6-118">Si un serveur de conformité des conversations permanent est activé, les anciens messages sont conservés dans la base de données de conformité.</span><span class="sxs-lookup"><span data-stu-id="60af6-118">If a Persistent Chat Compliance server is enabled, old messages are persisted in the compliance database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60af6-119">L’utilisation des données de salle de conversation s’applique aux applications Lync Server 2013 et aux API serveur de chat permanent, sauf si le rôle d’administrateur est impliqué.</span><span class="sxs-lookup"><span data-stu-id="60af6-119">This chat room data usage applies to the Lync Server 2013, Persistent Chat Server API application, except for the case when the administrator role is involved.</span></span> <span data-ttu-id="60af6-120">L’API serveur Chat permanent ne peut pas être utilisée pour effectuer les opérations de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="60af6-120">The Persistent Chat Server API cannot be used to do any of the administrator’s operations.</span></span> <span data-ttu-id="60af6-121">Vous devez effectuer ces opérations dans Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="60af6-121">You must perform these operations in the Lync Server Management Shell.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

