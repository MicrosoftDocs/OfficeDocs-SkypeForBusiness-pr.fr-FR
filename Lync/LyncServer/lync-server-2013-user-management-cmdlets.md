---
title: 'Lync Server 2013 : applets de commande de gestion des utilisateurs'
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
ms.openlocfilehash: 4a672eea92c820970b3cc4cc1c112c15fcffd641
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="b0cfe-102">Applets de commande de gestion des utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0cfe-102">User management cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0cfe-103">_**Dernière modification de la rubrique :** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="b0cfe-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="b0cfe-104">Les cmdlets de gestion des utilisateurs incluses dans Microsoft Lync Server 2013 vous permettent d’activer, de désactiver et de modifier des comptes d’utilisateurs Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b0cfe-104">The user management cmdlets included in Microsoft Lync Server 2013 allow you to enable, disable, and modify Lync Server user accounts.</span></span>

<div>

## <a name="user-management-cmdlets"></a><span data-ttu-id="b0cfe-105">Applets de commande de gestion des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="b0cfe-105">User Management Cmdlets</span></span>

<span data-ttu-id="b0cfe-106">La plupart des tâches de gestion qui s’appliquent aux utilisateurs et aux comptes d’utilisateur peuvent être effectuées à partir du panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b0cfe-106">Most management tasks that apply to users and user accounts can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="b0cfe-107">Les principales exceptions concernent les applets de commande utilisables avec les fournisseurs de services d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="b0cfe-107">The primary exceptions are the cmdlets that deal with audio conferencing providers.</span></span> <span data-ttu-id="b0cfe-108">Les tâches de gestion des utilisateurs peuvent être réalisées à l’aide d’applets de commande de Lync Server Management Shell ou à partir d’un script.</span><span class="sxs-lookup"><span data-stu-id="b0cfe-108">User management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="b0cfe-109">En utilisant un script, vous pouvez automatiser certaines tâches.</span><span class="sxs-lookup"><span data-stu-id="b0cfe-109">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="b0cfe-110">Vous trouverez ci-dessous une liste des applets de commande qui sont directement liées à la gestion des utilisateurs et des comptes d’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="b0cfe-110">The following is a list of cmdlets that relate directly to managing users and user accounts:</span></span>

  - <span></span>  
    [<span data-ttu-id="b0cfe-111">Get-CsAdContact</span><span class="sxs-lookup"><span data-stu-id="b0cfe-111">Get-CsAdContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdContact)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="b0cfe-112">Get-CsAdUser</span><span class="sxs-lookup"><span data-stu-id="b0cfe-112">Get-CsAdUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdUser)

<!-- end list -->

  - [<span data-ttu-id="b0cfe-113">Get-applet csclientaccesslicense</span><span class="sxs-lookup"><span data-stu-id="b0cfe-113">Get-CsClientAccessLicense</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClientAccessLicense)

<!-- end list -->

  - [<span data-ttu-id="b0cfe-114">Get-CsEffectivePolicy</span><span class="sxs-lookup"><span data-stu-id="b0cfe-114">Get-CsEffectivePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsEffectivePolicy)

<!-- end list -->

  - [<span data-ttu-id="b0cfe-115">Invoke-CsUcsRollback</span><span class="sxs-lookup"><span data-stu-id="b0cfe-115">Invoke-CsUcsRollback</span></span>](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)

<!-- end list -->

  - [<span data-ttu-id="b0cfe-116">Debug-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="b0cfe-116">Debug-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Debug-CsUnifiedContactStore)

  - [<span data-ttu-id="b0cfe-117">Test-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="b0cfe-117">Test-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="b0cfe-118">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="b0cfe-118">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)

  - <span></span>  
    [<span data-ttu-id="b0cfe-119">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="b0cfe-119">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Enable-CsUser)

  - <span></span>  
    [<span data-ttu-id="b0cfe-120">Get-CsUser</span><span class="sxs-lookup"><span data-stu-id="b0cfe-120">Get-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)

  - <span></span>  
    [<span data-ttu-id="b0cfe-121">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="b0cfe-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)

  - <span></span>  
    [<span data-ttu-id="b0cfe-122">Set-CsUser</span><span class="sxs-lookup"><span data-stu-id="b0cfe-122">Set-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="b0cfe-123">Get-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="b0cfe-123">Get-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="b0cfe-124">Remove-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="b0cfe-124">Remove-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="b0cfe-125">Set-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="b0cfe-125">Set-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="b0cfe-126">Test-CsAudioConferencingProvider</span><span class="sxs-lookup"><span data-stu-id="b0cfe-126">Test-CsAudioConferencingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAudioConferencingProvider)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="b0cfe-127">Get-CsUserPoolInfo</span><span class="sxs-lookup"><span data-stu-id="b0cfe-127">Get-CsUserPoolInfo</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserPoolInfo)

<!-- end list -->

  - [<span data-ttu-id="b0cfe-128">Get-applet csuserservicespolicy</span><span class="sxs-lookup"><span data-stu-id="b0cfe-128">Get-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserServicesPolicy)

  - [<span data-ttu-id="b0cfe-129">Grant-applet csuserservicespolicy</span><span class="sxs-lookup"><span data-stu-id="b0cfe-129">Grant-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsUserServicesPolicy)

  - [<span data-ttu-id="b0cfe-130">New-applet csuserservicespolicy</span><span class="sxs-lookup"><span data-stu-id="b0cfe-130">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)

  - [<span data-ttu-id="b0cfe-131">Remove-applet csuserservicespolicy</span><span class="sxs-lookup"><span data-stu-id="b0cfe-131">Remove-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserServicesPolicy)

  - [<span data-ttu-id="b0cfe-132">Set-applet csuserservicespolicy</span><span class="sxs-lookup"><span data-stu-id="b0cfe-132">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b0cfe-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b0cfe-133">See Also</span></span>


[<span data-ttu-id="b0cfe-134">Blog Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0cfe-134">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

