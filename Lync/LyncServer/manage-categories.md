---
title: Gérer les catégories
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Manage categories
ms:assetid: 1b118d91-b4c4-4b2f-b842-b451417ec2c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204719(v=OCS.15)
ms:contentKeyID: 48183543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97b161ab9dce464bdab96432ed909ed48b7df19d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-categories"></a><span data-ttu-id="9e1f8-102">Gérer les catégories</span><span class="sxs-lookup"><span data-stu-id="9e1f8-102">Manage categories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e1f8-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="9e1f8-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="9e1f8-104">Pour créer une catégorie de serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="9e1f8-104">To create a new Persistent Chat Server Category</span></span>

    New-CsPersistentChatCategory -Name Foo -PersistentChatPoolFqdn client.contoso1b118d91-b4c4-4b2f-b842-b451417ec2c6.com [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9e1f8-105">PersistentChatPoolFqdn est nécessaire uniquement s’il existe plusieurs pools de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="9e1f8-105">PersistentChatPoolFqdn is needed only if there is more than one Persistent Chat Server pool.</span></span>



</div>

<span data-ttu-id="9e1f8-106">Pour modifier la catégorie de serveur de conversation permanente existante</span><span class="sxs-lookup"><span data-stu-id="9e1f8-106">To make changes to existing Persistent Chat Server Category</span></span>

    Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}

<span data-ttu-id="9e1f8-107">Windows PowerShell : AllowedMembers, membres refusés et créateurs peuvent être définis simultanément.</span><span class="sxs-lookup"><span data-stu-id="9e1f8-107">Windows PowerShell: AllowedMembers, DeniedMembers, and Creators can be set simultaneously.</span></span> <span data-ttu-id="9e1f8-108">Les créateurs doivent constituer le sous-ensemble des membres autorisés moins les membres non autorisés.</span><span class="sxs-lookup"><span data-stu-id="9e1f8-108">Creators should be the subset of AllowedMembers minus DeniedMembers.</span></span> <span data-ttu-id="9e1f8-109">Vous pouvez également définir les propriétés d’une catégorie en même temps que les membres et les créateurs.</span><span class="sxs-lookup"><span data-stu-id="9e1f8-109">You can also set the properties of a category at the same time as the members and creators.</span></span>

<div>

## <a name="create-get-set-or-remove-a-category"></a><span data-ttu-id="9e1f8-110">Créer, obtenir, définir ou supprimer une catégorie</span><span class="sxs-lookup"><span data-stu-id="9e1f8-110">Create, Get, Set, or Remove a Category</span></span>

<span data-ttu-id="9e1f8-111">Pour créer une catégorie</span><span class="sxs-lookup"><span data-stu-id="9e1f8-111">To create a new Category</span></span>

    New-CsPersistentChatCategory -Name <String> [-PersistentChatPoolFqdn <String>] [-Description <String>] [-EnableInvitations<Switch Parameter>] [-EnableFileUpload <Switch Parameter>] [-RemoveChatHistory <Switch Parameter>] [-MaxContentSize <Integer>]

<span data-ttu-id="9e1f8-112">Pour obtenir une catégorie</span><span class="sxs-lookup"><span data-stu-id="9e1f8-112">To get a Category</span></span>

    Get-CsPersistentChatCategory -Identity <String>

<span data-ttu-id="9e1f8-113">ou</span><span class="sxs-lookup"><span data-stu-id="9e1f8-113">or</span></span>

    Get-CsPersistentChatCategory -PersistentChatPoolFqdn <String>

<span data-ttu-id="9e1f8-114">Pour définir une catégorie</span><span class="sxs-lookup"><span data-stu-id="9e1f8-114">To set a Category</span></span>

    Set-CsPersistentChatCategory -Instance <CategoryObject> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="9e1f8-115">ou</span><span class="sxs-lookup"><span data-stu-id="9e1f8-115">or</span></span>

    Set-CsPersistentChatCategory [-Identity] <string> [-Name <string>] [-Description <string>] [-Invitations <bool>] [-FileUpload <bool>] [-ChatHistory <bool>] [-AllowedMembers <PSListModifier[string]>] [-DeniedMembers <PSListModifier[string]>] [-Creators <PSListModifier[string]>] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="9e1f8-116">Pour supprimer une catégorie</span><span class="sxs-lookup"><span data-stu-id="9e1f8-116">To remove a Category</span></span>

    Remove-CsPersistentChatCategory -Instance <CategoryObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="9e1f8-117">ou</span><span class="sxs-lookup"><span data-stu-id="9e1f8-117">or</span></span>

    Remove-CsPersistentChatCategory -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

