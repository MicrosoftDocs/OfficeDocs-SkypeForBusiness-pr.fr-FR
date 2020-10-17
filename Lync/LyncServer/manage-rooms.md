---
title: Gérer les salles
description: Gérer les salles.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Manage rooms
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205292(v=OCS.15)
ms:contentKeyID: 48185505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be093e14a68639fdde73b58936e1b2f5cf4424cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544590"
---
# <a name="manage-rooms"></a><span data-ttu-id="3769f-103">Gérer les salles</span><span class="sxs-lookup"><span data-stu-id="3769f-103">Manage rooms</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3769f-104">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="3769f-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="3769f-105">Pour créer une salle de serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="3769f-105">To create a new Persistent Chat Server room</span></span>

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3769f-106">-PersistentChatPoolFqdn n’est pas requis si l’un des éléments suivants est vrai :</span><span class="sxs-lookup"><span data-stu-id="3769f-106">-PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="3769f-107">Il n’existe qu’un seul pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="3769f-107">There is only one Persistent Chat Server pool.</span></span></P>
> <LI>
> <P><span data-ttu-id="3769f-108">Vous fournissez un nom de domaine complet (FQDN) de pool à la catégorie.</span><span class="sxs-lookup"><span data-stu-id="3769f-108">You provide a pool FQDN to the category.</span></span></P>
> <LI>
> <P><span data-ttu-id="3769f-109">Vous fournissez un nom de domaine complet (FQDN) à l’ajout de la salle.</span><span class="sxs-lookup"><span data-stu-id="3769f-109">You provide a pool FQDN to adding the room.</span></span></P></LI></UL>



</div>

<span data-ttu-id="3769f-110">Pour modifier une salle de serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="3769f-110">To make changes to an existing Persistent Chat Server room</span></span>

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

<span data-ttu-id="3769f-111">Windows PowerShell : les membres, les responsables et les présentateurs peuvent être définis simultanément.</span><span class="sxs-lookup"><span data-stu-id="3769f-111">Windows PowerShell: Members, Managers and Presenters can be set simultaneously.</span></span> <span data-ttu-id="3769f-112">Ils doivent tous être le sous-ensemble de AllowedMembers moins DeniedMembers de la catégorie Hôte.</span><span class="sxs-lookup"><span data-stu-id="3769f-112">They all should be the subset of AllowedMembers minus DeniedMembers of the host Category.</span></span> <span data-ttu-id="3769f-113">Une chambre avec type=normal ne peut pas avoir de Présentateurs.</span><span class="sxs-lookup"><span data-stu-id="3769f-113">A room that is type=normal cannot include Presenters.</span></span>

<div>

## <a name="create-get-set-clear-or-remove-a-room"></a><span data-ttu-id="3769f-114">Créer, atteindre, configurer, effacer ou supprimer une salle</span><span class="sxs-lookup"><span data-stu-id="3769f-114">Create, Get, Set, Clear, or Remove a Room</span></span>

<span data-ttu-id="3769f-115">Pour créer une nouvelle salle</span><span class="sxs-lookup"><span data-stu-id="3769f-115">To create a new room</span></span>

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

<span data-ttu-id="3769f-116">Pour configurer une salle</span><span class="sxs-lookup"><span data-stu-id="3769f-116">To set a room</span></span>

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

<span data-ttu-id="3769f-117">Pour atteindre une salle</span><span class="sxs-lookup"><span data-stu-id="3769f-117">To get a room</span></span>

    Get-CsPersistentChatRoom -Identity <String>

<span data-ttu-id="3769f-118">ou</span><span class="sxs-lookup"><span data-stu-id="3769f-118">or</span></span>

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

<span data-ttu-id="3769f-119">où –le filtre ne prend en charge que le nom et la description, et vous permet de rechercher des salles dont le nom/la description correspond à la chaîne de mot clé.</span><span class="sxs-lookup"><span data-stu-id="3769f-119">where –filter supports only Name and Description and helps you find rooms whose Name/Description matches the keyword string.</span></span> <span data-ttu-id="3769f-120">PoolFqdn recherche dans un pool de serveurs de conversation permanente donné.</span><span class="sxs-lookup"><span data-stu-id="3769f-120">PoolFqdn searches in a given Persistent Chat Server pool.</span></span>

<span data-ttu-id="3769f-121">Pour effacer une salle et effacer les messages d’une salle</span><span class="sxs-lookup"><span data-stu-id="3769f-121">To clear a room and clear messages from a room</span></span>

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="3769f-122">ou</span><span class="sxs-lookup"><span data-stu-id="3769f-122">or</span></span>

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="3769f-123">Pour supprimer une salle</span><span class="sxs-lookup"><span data-stu-id="3769f-123">To remove a room</span></span>

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="3769f-124">ou</span><span class="sxs-lookup"><span data-stu-id="3769f-124">or</span></span>

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

