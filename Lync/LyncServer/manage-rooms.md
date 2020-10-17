---
title: Gérer les salles
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
ms.openlocfilehash: 0ddb9e074a0eb0bdd614abb3fa29cd0785d2df42
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527561"
---
# <a name="manage-rooms"></a><span data-ttu-id="509b2-102">Gérer les salles</span><span class="sxs-lookup"><span data-stu-id="509b2-102">Manage rooms</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="509b2-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="509b2-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="509b2-104">Pour créer une salle de serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="509b2-104">To create a new Persistent Chat Server room</span></span>

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="509b2-105">-PersistentChatPoolFqdn n’est pas requis si l’un des éléments suivants est vrai :</span><span class="sxs-lookup"><span data-stu-id="509b2-105">-PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="509b2-106">Il n’existe qu’un seul pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="509b2-106">There is only one Persistent Chat Server pool.</span></span></P>
> <LI>
> <P><span data-ttu-id="509b2-107">Vous fournissez un nom de domaine complet (FQDN) de pool à la catégorie.</span><span class="sxs-lookup"><span data-stu-id="509b2-107">You provide a pool FQDN to the category.</span></span></P>
> <LI>
> <P><span data-ttu-id="509b2-108">Vous fournissez un nom de domaine complet (FQDN) à l’ajout de la salle.</span><span class="sxs-lookup"><span data-stu-id="509b2-108">You provide a pool FQDN to adding the room.</span></span></P></LI></UL>



</div>

<span data-ttu-id="509b2-109">Pour modifier une salle de serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="509b2-109">To make changes to an existing Persistent Chat Server room</span></span>

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

<span data-ttu-id="509b2-110">Windows PowerShell : les membres, les responsables et les présentateurs peuvent être définis simultanément.</span><span class="sxs-lookup"><span data-stu-id="509b2-110">Windows PowerShell: Members, Managers and Presenters can be set simultaneously.</span></span> <span data-ttu-id="509b2-111">Ils doivent tous être le sous-ensemble de AllowedMembers moins DeniedMembers de la catégorie Hôte.</span><span class="sxs-lookup"><span data-stu-id="509b2-111">They all should be the subset of AllowedMembers minus DeniedMembers of the host Category.</span></span> <span data-ttu-id="509b2-112">Une chambre avec type=normal ne peut pas avoir de Présentateurs.</span><span class="sxs-lookup"><span data-stu-id="509b2-112">A room that is type=normal cannot include Presenters.</span></span>

<div>

## <a name="create-get-set-clear-or-remove-a-room"></a><span data-ttu-id="509b2-113">Créer, atteindre, configurer, effacer ou supprimer une salle</span><span class="sxs-lookup"><span data-stu-id="509b2-113">Create, Get, Set, Clear, or Remove a Room</span></span>

<span data-ttu-id="509b2-114">Pour créer une nouvelle salle</span><span class="sxs-lookup"><span data-stu-id="509b2-114">To create a new room</span></span>

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

<span data-ttu-id="509b2-115">Pour configurer une salle</span><span class="sxs-lookup"><span data-stu-id="509b2-115">To set a room</span></span>

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

<span data-ttu-id="509b2-116">Pour atteindre une salle</span><span class="sxs-lookup"><span data-stu-id="509b2-116">To get a room</span></span>

    Get-CsPersistentChatRoom -Identity <String>

<span data-ttu-id="509b2-117">ou</span><span class="sxs-lookup"><span data-stu-id="509b2-117">or</span></span>

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

<span data-ttu-id="509b2-118">où –le filtre ne prend en charge que le nom et la description, et vous permet de rechercher des salles dont le nom/la description correspond à la chaîne de mot clé.</span><span class="sxs-lookup"><span data-stu-id="509b2-118">where –filter supports only Name and Description and helps you find rooms whose Name/Description matches the keyword string.</span></span> <span data-ttu-id="509b2-119">PoolFqdn recherche dans un pool de serveurs de conversation permanente donné.</span><span class="sxs-lookup"><span data-stu-id="509b2-119">PoolFqdn searches in a given Persistent Chat Server pool.</span></span>

<span data-ttu-id="509b2-120">Pour effacer une salle et effacer les messages d’une salle</span><span class="sxs-lookup"><span data-stu-id="509b2-120">To clear a room and clear messages from a room</span></span>

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="509b2-121">ou</span><span class="sxs-lookup"><span data-stu-id="509b2-121">or</span></span>

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="509b2-122">Pour supprimer une salle</span><span class="sxs-lookup"><span data-stu-id="509b2-122">To remove a room</span></span>

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="509b2-123">ou</span><span class="sxs-lookup"><span data-stu-id="509b2-123">or</span></span>

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

