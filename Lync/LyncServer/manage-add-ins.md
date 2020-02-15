---
title: Gérer les compléments
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Manage add-ins
ms:assetid: b84f868e-b36e-4ab4-b284-7db212d401c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205193(v=OCS.15)
ms:contentKeyID: 48185204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11b30c4edba62873eddf89ce1967e9d158fee1bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-add-ins"></a><span data-ttu-id="db51e-102">Gérer les compléments</span><span class="sxs-lookup"><span data-stu-id="db51e-102">Manage add-ins</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db51e-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="db51e-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="db51e-104">Pour créer un complément de serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="db51e-104">To create a new Persistent Chat Server Add-in</span></span>

    New-CsPersistentChatAddin -Name Contoso -PersistentChatPoolFqdn client.contoso.com -Url http://contoso.com 

<div>

## <a name="create-get-set-or-remove-an-add-in"></a><span data-ttu-id="db51e-105">Créer, obtenir, définir ou supprimer un complément</span><span class="sxs-lookup"><span data-stu-id="db51e-105">Create, Get, Set, or Remove an Add-in</span></span>

<span data-ttu-id="db51e-106">Pour créer un nouveau complément</span><span class="sxs-lookup"><span data-stu-id="db51e-106">To create a new Add-in</span></span>

    New-CsPersistentChatAddin -PersistentChatPoolFqdn <String> -Name <String> -Url<String>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="db51e-107">La &lt;chaîne&gt; PersistentChatPoolFqdn est requise uniquement s’il existe plusieurs pools de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="db51e-107">PersistentChatPoolFqdn &lt;String&gt; is required only if there is more than one Persistent Chat Server pool.</span></span>



</div>

<span data-ttu-id="db51e-108">Pour obtenir un complément</span><span class="sxs-lookup"><span data-stu-id="db51e-108">To get an Add-in</span></span>

    Get-CsPersistentChatAddin -Identity <String>]

<span data-ttu-id="db51e-109">ou</span><span class="sxs-lookup"><span data-stu-id="db51e-109">or</span></span>

    Get-CsPersistentChatAddin -PersistentChatPoolFqdn <String>

<span data-ttu-id="db51e-110">Pour définir un complément</span><span class="sxs-lookup"><span data-stu-id="db51e-110">To set an Add-in</span></span>

    Set-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="db51e-111">ou</span><span class="sxs-lookup"><span data-stu-id="db51e-111">or</span></span>

    Set-CsPersistentChatAddIn -Identity <String> [-Name <String>] [-Url<String>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="db51e-112">Pour supprimer un complément</span><span class="sxs-lookup"><span data-stu-id="db51e-112">To remove an Add-in</span></span>

    Remove-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

<span data-ttu-id="db51e-113">ou</span><span class="sxs-lookup"><span data-stu-id="db51e-113">or</span></span>

    Remove-CsPersistentChatAddIn -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

