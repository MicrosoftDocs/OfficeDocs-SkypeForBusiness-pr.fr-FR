---
title: Gestion des compléments
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Manage add-ins
ms:assetid: b84f868e-b36e-4ab4-b284-7db212d401c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205193(v=OCS.15)
ms:contentKeyID: 48185204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f77c0bc46054cd3cb045c07be0d8aac99c81947a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508451"
---
# <a name="manage-add-ins"></a><span data-ttu-id="1bb6b-102">Gestion des compléments</span><span class="sxs-lookup"><span data-stu-id="1bb6b-102">Manage add-ins</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bb6b-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="1bb6b-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="1bb6b-104">Pour créer un complément de serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="1bb6b-104">To create a new Persistent Chat Server Add-in</span></span>

    New-CsPersistentChatAddin -Name Contoso -PersistentChatPoolFqdn client.contoso.com -Url http://contoso.com 

<div>

## <a name="create-get-set-or-remove-an-add-in"></a><span data-ttu-id="1bb6b-105">Créer, obtenir, définir ou supprimer un complément</span><span class="sxs-lookup"><span data-stu-id="1bb6b-105">Create, Get, Set, or Remove an Add-in</span></span>

<span data-ttu-id="1bb6b-106">Pour créer un nouveau complément</span><span class="sxs-lookup"><span data-stu-id="1bb6b-106">To create a new Add-in</span></span>

    New-CsPersistentChatAddin -PersistentChatPoolFqdn <String> -Name <String> -Url<String>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1bb6b-107">La &lt; chaîne PersistentChatPoolFqdn &gt; est requise uniquement s’il existe plusieurs pools de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="1bb6b-107">PersistentChatPoolFqdn &lt;String&gt; is required only if there is more than one Persistent Chat Server pool.</span></span>



</div>

<span data-ttu-id="1bb6b-108">Pour obtenir un complément</span><span class="sxs-lookup"><span data-stu-id="1bb6b-108">To get an Add-in</span></span>

    Get-CsPersistentChatAddin -Identity <String>]

<span data-ttu-id="1bb6b-109">ou</span><span class="sxs-lookup"><span data-stu-id="1bb6b-109">or</span></span>

    Get-CsPersistentChatAddin -PersistentChatPoolFqdn <String>

<span data-ttu-id="1bb6b-110">Pour définir un complément</span><span class="sxs-lookup"><span data-stu-id="1bb6b-110">To set an Add-in</span></span>

    Set-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="1bb6b-111">ou</span><span class="sxs-lookup"><span data-stu-id="1bb6b-111">or</span></span>

    Set-CsPersistentChatAddIn -Identity <String> [-Name <String>] [-Url<String>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="1bb6b-112">Pour supprimer un complément</span><span class="sxs-lookup"><span data-stu-id="1bb6b-112">To remove an Add-in</span></span>

    Remove-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="1bb6b-113">ou</span><span class="sxs-lookup"><span data-stu-id="1bb6b-113">or</span></span>

    Remove-CsPersistentChatAddIn -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

