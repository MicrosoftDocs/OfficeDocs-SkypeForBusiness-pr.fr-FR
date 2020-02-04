---
title: Gestion des salles
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Manage rooms
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205292(v=OCS.15)
ms:contentKeyID: 48185505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 416da390f277dfc7179a45e0b1dc989b240ab394
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-rooms"></a><span data-ttu-id="25085-102">Gestion des salles</span><span class="sxs-lookup"><span data-stu-id="25085-102">Manage rooms</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25085-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="25085-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="25085-104">Pour créer une salle serveur Chat permanent</span><span class="sxs-lookup"><span data-stu-id="25085-104">To create a new Persistent Chat Server room</span></span>

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="25085-105">-PersistentChatPoolFqdn n’est pas requis si l’un des éléments suivants est vrai :</span><span class="sxs-lookup"><span data-stu-id="25085-105">-PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="25085-106">Il n’y a qu’un seul pool de serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="25085-106">There is only one Persistent Chat Server pool.</span></span></P>
> <LI>
> <P><span data-ttu-id="25085-107">Vous fournissez un nom de domaine complet (FQDN) de pool à la catégorie.</span><span class="sxs-lookup"><span data-stu-id="25085-107">You provide a pool FQDN to the category.</span></span></P>
> <LI>
> <P><span data-ttu-id="25085-108">Vous fournissez un nom de domaine complet (FQDN) à l’ajout de la salle.</span><span class="sxs-lookup"><span data-stu-id="25085-108">You provide a pool FQDN to adding the room.</span></span></P></LI></UL>



</div>

<span data-ttu-id="25085-109">Pour apporter des modifications à une salle de serveur Chat permanent existante</span><span class="sxs-lookup"><span data-stu-id="25085-109">To make changes to an existing Persistent Chat Server room</span></span>

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

<span data-ttu-id="25085-110">Windows PowerShell : les membres, responsables et présentateurs peuvent être définis simultanément.</span><span class="sxs-lookup"><span data-stu-id="25085-110">Windows PowerShell: Members, Managers and Presenters can be set simultaneously.</span></span> <span data-ttu-id="25085-111">Tous doivent représenter le sous-ensemble de AllowedMembers moins DeniedMembers de la catégorie hôte.</span><span class="sxs-lookup"><span data-stu-id="25085-111">They all should be the subset of AllowedMembers minus DeniedMembers of the host Category.</span></span> <span data-ttu-id="25085-112">Une salle de type = normal ne peut pas inclure de présentateur.</span><span class="sxs-lookup"><span data-stu-id="25085-112">A room that is type=normal cannot include Presenters.</span></span>

<div>

## <a name="create-get-set-clear-or-remove-a-room"></a><span data-ttu-id="25085-113">Créer, obtenir, définir, effacer ou supprimer une salle</span><span class="sxs-lookup"><span data-stu-id="25085-113">Create, Get, Set, Clear, or Remove a Room</span></span>

<span data-ttu-id="25085-114">Pour créer une salle</span><span class="sxs-lookup"><span data-stu-id="25085-114">To create a new room</span></span>

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

<span data-ttu-id="25085-115">Pour définir une salle</span><span class="sxs-lookup"><span data-stu-id="25085-115">To set a room</span></span>

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

<span data-ttu-id="25085-116">Pour accéder à une salle</span><span class="sxs-lookup"><span data-stu-id="25085-116">To get a room</span></span>

    Get-CsPersistentChatRoom -Identity <String>

<span data-ttu-id="25085-117">ou</span><span class="sxs-lookup"><span data-stu-id="25085-117">or</span></span>

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

<span data-ttu-id="25085-118">emplacement – filtre ne prend en charge que le nom et la description, et vous permet de rechercher des salles dont le nom ou la description correspond à la chaîne du mot clé.</span><span class="sxs-lookup"><span data-stu-id="25085-118">where –filter supports only Name and Description and helps you find rooms whose Name/Description matches the keyword string.</span></span> <span data-ttu-id="25085-119">PoolFqdn effectue une recherche dans un pool de serveurs de chat permanent donné.</span><span class="sxs-lookup"><span data-stu-id="25085-119">PoolFqdn searches in a given Persistent Chat Server pool.</span></span>

<span data-ttu-id="25085-120">Pour vider une chambre et effacer les messages d’une pièce</span><span class="sxs-lookup"><span data-stu-id="25085-120">To clear a room and clear messages from a room</span></span>

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="25085-121">ou</span><span class="sxs-lookup"><span data-stu-id="25085-121">or</span></span>

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="25085-122">Pour supprimer une salle</span><span class="sxs-lookup"><span data-stu-id="25085-122">To remove a room</span></span>

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="25085-123">ou</span><span class="sxs-lookup"><span data-stu-id="25085-123">or</span></span>

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

