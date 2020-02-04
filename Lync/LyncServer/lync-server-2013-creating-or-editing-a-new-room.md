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

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a><span data-ttu-id="7ad8e-102">Création ou modification d’une salle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ad8e-102">Creating or editing a new room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ad8e-103">_**Dernière modification de la rubrique :** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="7ad8e-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="7ad8e-104">La configuration des salles de conversation permanente est généralement gérée par les utilisateurs. en règle générale, un administrateur de chat permanent ne peut pas configurer ou gérer des salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="7ad8e-104">Configuring Persistent Chat rooms is commonly handled by users; a Persistent Chat administrator typically does not configure or manage chat rooms.</span></span> <span data-ttu-id="7ad8e-105">Les applets de cmdlet Windows PowerShell pour gérer des salles sont disponibles uniquement pour les administrateurs **CsPersistentChatAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="7ad8e-105">Windows PowerShell cmdlets to manage rooms are available only to **CsPersistentChatAdministrator** Administrators.</span></span>

<span data-ttu-id="7ad8e-106">Les utilisateurs qui sont des **créateurs** dans une catégorie donnée peuvent utiliser le client Lync pour créer et gérer des salles.</span><span class="sxs-lookup"><span data-stu-id="7ad8e-106">Users who are **Creators** in any given category can use the Lync client to create and manage rooms.</span></span> <span data-ttu-id="7ad8e-107">Les utilisateurs qui ont été désignés comme responsables pour une salle de conversation spécifique peuvent également effectuer une gestion en continu de la salle, comme la modification des propriétés de la salle ou de l’appartenance.</span><span class="sxs-lookup"><span data-stu-id="7ad8e-107">Users who have been designated as managers for a specific chat room can also perform ongoing management of the room, such as editing the room properties or membership.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="7ad8e-108">Ils peuvent également être créateurs de messages permanents et ne sont pas soumis aux restrictions imposées par les créateurs.</span><span class="sxs-lookup"><span data-stu-id="7ad8e-108">Persistent Chat administrators can also be Creators, and they are not subject to the restrictions placed on Creators.</span></span>



</div>

<span data-ttu-id="7ad8e-109">Si vous êtes un administrateur de chat permanent, vous pouvez également utiliser une interface utilisateur pour créer et gérer des salles de conversation au lieu d’utiliser des cmdlets Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ad8e-109">Optionally, if you are a Persistent Chat administrator, you can employ a user interface to create and manage chat rooms instead of using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="7ad8e-110">Pour ce faire, SIP : activez un administrateur pour le serveur de chat permanent, puis utilisez le client Lync pour créer et gérer des salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="7ad8e-110">To do this, SIP-enable an administrator for Persistent Chat Server, and then use the Lync client to create and manage chat rooms.</span></span>

<span data-ttu-id="7ad8e-111">Si vous voulez créer un flux de travail de gestion des salles personnalisé pour vos utilisateurs, vous pouvez définir la propriété **RoomManagementUrl** sur votre configuration serveur de chat permanent pour rediriger les utilisateurs vers votre solution personnalisée du client Lync.</span><span class="sxs-lookup"><span data-stu-id="7ad8e-111">If you want to create a custom room management workflow for your users, you can set the **RoomManagementUrl** property on your Persistent Chat Server configuration to redirect users to your custom solution from the Lync client.</span></span>

<span data-ttu-id="7ad8e-112">Pour plus d’informations sur la configuration des salles de conversation à l’aide de l’interface de ligne de commande Windows PowerShell, voir « gestion des salles » dans [configuration du serveur de chat permanent à l’aide d’applets de commande Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="7ad8e-112">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="7ad8e-113">Pour plus d’informations sur la configuration des salles de conversation, voir [configurer des salles dans Lync Server 2013](lync-server-2013-configure-rooms.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="7ad8e-113">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7ad8e-114">Serveur Chat permanent permet aux utilisateurs de créer et de gérer des salles de conversation pour un site spécifique.</span><span class="sxs-lookup"><span data-stu-id="7ad8e-114">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="7ad8e-115">Toutefois, les utilisateurs ne peuvent pas créer ou gérer des salles de conversation sur d’autres sites au sein de la même topologie.</span><span class="sxs-lookup"><span data-stu-id="7ad8e-115">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="7ad8e-116">Veillez à spécifier des créateurs et des gestionnaires de salle de conversation pour tous les sites de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="7ad8e-116">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="7ad8e-117">Les utilisateurs qui sont hébergés sur une unité de branchement Survivable Lync Server ne peuvent pas créer de nouvelles salles de conversation ou afficher la carte de la salle pour les salles existantes.</span><span class="sxs-lookup"><span data-stu-id="7ad8e-117">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

