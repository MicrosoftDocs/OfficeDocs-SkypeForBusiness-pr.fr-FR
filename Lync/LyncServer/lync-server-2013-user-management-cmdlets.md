---
title: 'Lync Server 2013 : cmdlets de gestion des utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User management cmdlets
ms:assetid: 85312f3f-28e8-421c-b94c-e6ead1f5f755
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398677(v=OCS.15)
ms:contentKeyID: 48184702
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2396cb1a157b88d8beb9458006c1c8a44874dba3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="83d64-102">Cmdlets de gestion des utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83d64-102">User management cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83d64-103">_**Dernière modification de la rubrique :** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="83d64-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="83d64-104">Les applets de la gestion des utilisateurs inclus dans Microsoft Lync Server 2013 vous permettent d’activer, de désactiver et de modifier les comptes d’utilisateurs de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83d64-104">The user management cmdlets included in Microsoft Lync Server 2013 allow you to enable, disable, and modify Lync Server user accounts.</span></span>

<div>

## <a name="user-management-cmdlets"></a><span data-ttu-id="83d64-105">Cmdlets de gestion des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="83d64-105">User Management Cmdlets</span></span>

<span data-ttu-id="83d64-106">La plupart des tâches de gestion applicables aux utilisateurs et aux comptes d’utilisateurs peuvent être effectuées à partir du panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="83d64-106">Most management tasks that apply to users and user accounts can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="83d64-107">Les principales exceptions sont les applets de service qui gèrent les fournisseurs de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="83d64-107">The primary exceptions are the cmdlets that deal with audio conferencing providers.</span></span> <span data-ttu-id="83d64-108">Les tâches de gestion des utilisateurs peuvent être effectuées à l’aide des cmdlets de Lync Server Management Shell ou à partir d’un script.</span><span class="sxs-lookup"><span data-stu-id="83d64-108">User management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="83d64-109">À l’aide d’un script, vous pouvez automatiser certaines tâches.</span><span class="sxs-lookup"><span data-stu-id="83d64-109">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="83d64-110">Vous trouverez ci-dessous une liste des applets de commande qui concernent directement la gestion des utilisateurs et des comptes d’utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="83d64-110">The following is a list of cmdlets that relate directly to managing users and user accounts:</span></span>

  - <span></span>  
    [<span data-ttu-id="83d64-111">Get-CsAdContact</span><span class="sxs-lookup"><span data-stu-id="83d64-111">Get-CsAdContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdContact)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="83d64-112">Get-CsAdUser</span><span class="sxs-lookup"><span data-stu-id="83d64-112">Get-CsAdUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdUser)

<!-- end list -->

  - [<span data-ttu-id="83d64-113">Get-CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="83d64-113">Get-CsClientAccessLicense</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClientAccessLicense)

<!-- end list -->

  - [<span data-ttu-id="83d64-114">Get-CsEffectivePolicy</span><span class="sxs-lookup"><span data-stu-id="83d64-114">Get-CsEffectivePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsEffectivePolicy)

<!-- end list -->

  - [<span data-ttu-id="83d64-115">Invoke-CsUcsRollback</span><span class="sxs-lookup"><span data-stu-id="83d64-115">Invoke-CsUcsRollback</span></span>](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)

<!-- end list -->

  - [<span data-ttu-id="83d64-116">Debug-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="83d64-116">Debug-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Debug-CsUnifiedContactStore)

  - [<span data-ttu-id="83d64-117">Test-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="83d64-117">Test-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="83d64-118">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="83d64-118">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)

  - <span></span>  
    [<span data-ttu-id="83d64-119">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="83d64-119">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Enable-CsUser)

  - <span></span>  
    [<span data-ttu-id="83d64-120">Get-CsUser</span><span class="sxs-lookup"><span data-stu-id="83d64-120">Get-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)

  - <span></span>  
    [<span data-ttu-id="83d64-121">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="83d64-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)

  - <span></span>  
    [<span data-ttu-id="83d64-122">Set-CsUser</span><span class="sxs-lookup"><span data-stu-id="83d64-122">Set-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="83d64-123">Get-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="83d64-123">Get-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="83d64-124">Remove-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="83d64-124">Remove-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="83d64-125">Set-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="83d64-125">Set-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="83d64-126">Test-CsAudioConferencingProvider</span><span class="sxs-lookup"><span data-stu-id="83d64-126">Test-CsAudioConferencingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAudioConferencingProvider)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="83d64-127">Get-CsUserPoolInfo</span><span class="sxs-lookup"><span data-stu-id="83d64-127">Get-CsUserPoolInfo</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserPoolInfo)

<!-- end list -->

  - [<span data-ttu-id="83d64-128">Get-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="83d64-128">Get-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserServicesPolicy)

  - [<span data-ttu-id="83d64-129">Grant-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="83d64-129">Grant-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsUserServicesPolicy)

  - [<span data-ttu-id="83d64-130">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="83d64-130">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)

  - [<span data-ttu-id="83d64-131">Remove-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="83d64-131">Remove-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserServicesPolicy)

  - [<span data-ttu-id="83d64-132">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="83d64-132">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="83d64-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="83d64-133">See Also</span></span>


[<span data-ttu-id="83d64-134">Blog Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="83d64-134">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

