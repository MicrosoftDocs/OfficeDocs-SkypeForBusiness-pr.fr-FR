---
title: 'Lync Server 2013 : applets de applet voix entreprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice cmdlets
ms:assetid: 7d7c6d94-3ead-4d99-95f7-c31b448ab9e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415658(v=OCS.15)
ms:contentKeyID: 48184613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc1c5516c80ed38839b795c92a5521be93711cad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-cmdlets-in-lync-server-2013"></a><span data-ttu-id="2a79c-102">Cmdlets voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a79c-102">Enterprise Voice cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a79c-103">_**Dernière modification de la rubrique :** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="2a79c-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="2a79c-104">Voix entreprise est l’implémentation Microsoft de VoIP (Voice over IP).</span><span class="sxs-lookup"><span data-stu-id="2a79c-104">Enterprise Voice is the Microsoft implementation of Voice over IP (VoIP).</span></span> <span data-ttu-id="2a79c-105">Les applets de connexion disponibles pour gérer les voix entreprise dans Microsoft Lync Server 2013 vous permettent de créer et de modifier les plans de numérotation (auparavant appelés profils d’emplacement), les stratégies de voix, les itinéraires et les règles de normalisation.</span><span class="sxs-lookup"><span data-stu-id="2a79c-105">The cmdlets available for managing Enterprise Voice in Microsoft Lync Server 2013 will allow you to create and modify dial plans (formerly known as location profiles), voice policies, routes, and normalization rules.</span></span>

<div>

## <a name="enterprise-voice-cmdlets"></a><span data-ttu-id="2a79c-106">Cmdlets voix entreprise</span><span class="sxs-lookup"><span data-stu-id="2a79c-106">Enterprise Voice Cmdlets</span></span>

<span data-ttu-id="2a79c-107">La plupart des tâches de gestion qui s’appliquent à voix entreprise peuvent être effectuées à partir du panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2a79c-107">Most management tasks that apply to Enterprise Voice can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="2a79c-108">Ces mêmes tâches peuvent être effectuées à l’aide d’applets de gestion Lync Server Management Shell ou à partir d’un script, ce qui vous permet d’automatiser certaines tâches.</span><span class="sxs-lookup"><span data-stu-id="2a79c-108">These same tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script, allowing you to automate certain tasks.</span></span> <span data-ttu-id="2a79c-109">Voici une liste des applets de commande qui se rapportent directement à la gestion de la voix entreprise :</span><span class="sxs-lookup"><span data-stu-id="2a79c-109">The following is a list of cmdlets that relate directly to managing Enterprise Voice:</span></span>

<span data-ttu-id="2a79c-110">**[Résoudre les problèmes de cmdlet voix entreprise dans Lync Server 2013](lync-server-2013-troubleshooting-enterprise-voice-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="2a79c-110">**[Troubleshooting Enterprise Voice cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-enterprise-voice-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-111">[Get-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-111">[Get-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-112">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-112">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398804(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-113">[Set-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-113">[Set-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398967(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2a79c-114">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-114">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-115">[Nouveau-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398961(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-115">[New-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398961(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-116">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-116">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-117">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398614(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-117">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398614(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-118">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398260(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-118">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398260(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2a79c-119">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-119">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2a79c-120">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-120">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2a79c-121">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-121">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2a79c-122">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-122">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2a79c-123">[Test-CsVoiceUser](https://technet.microsoft.com/en-us/library/Gg413013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-123">[Test-CsVoiceUser](https://technet.microsoft.com/en-us/library/Gg413013(v=OCS.15))</span></span>

<span data-ttu-id="2a79c-124">**[Cmdlets de règles de normalisation vocale dans Lync Server 2013](lync-server-2013-voice-normalization-rules-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="2a79c-124">**[Voice normalization rules cmdlets in Lync Server 2013](lync-server-2013-voice-normalization-rules-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-125">[Get-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398393(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-125">[Get-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398393(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-126">[Nouveau-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398240(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-126">[New-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398240(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-127">[Remove-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398501(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-127">[Remove-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398501(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-128">[Set-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398491(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-128">[Set-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398491(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-129">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-129">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2a79c-130">[Nouveau-CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-130">[New-CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))</span></span>

<span data-ttu-id="2a79c-131">**[Cmdlets de la stratégie vocale dans Lync Server 2013](lync-server-2013-voice-policy-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="2a79c-131">**[Voice policy cmdlets in Lync Server 2013](lync-server-2013-voice-policy-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-132">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg413043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-132">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg413043(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-133">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398547(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-133">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398547(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-134">[New-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg425860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-134">[New-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg425860(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-135">[Remove-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398791(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-135">[Remove-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398791(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-136">[Set-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398644(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-136">[Set-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398644(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-137">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-137">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2a79c-138">[Get-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-138">[Get-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-139">[Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-139">[Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2a79c-140">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398101(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-140">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398101(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-141">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398828(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-141">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398828(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-142">[Nouveau-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg425856(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-142">[New-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg425856(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-143">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398309(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-143">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398309(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-144">[Set-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg399021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-144">[Set-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg399021(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-145">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-145">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span></span>

<span data-ttu-id="2a79c-146">**[Cmdlets de routage vocal dans Lync Server 2013](lync-server-2013-voice-routing-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="2a79c-146">**[Voice routing cmdlets in Lync Server 2013](lync-server-2013-voice-routing-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-147">[Get-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-147">[Get-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-148">[Nouveau-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-148">[New-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-149">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-149">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-150">[Set-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-150">[Set-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2a79c-151">[Get-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-151">[Get-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-152">[Nouveau-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-152">[New-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-153">[Remove-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-153">[Remove-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-154">[Set-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-154">[Set-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2a79c-155">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2a79c-155">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2a79c-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2a79c-156">See Also</span></span>


[<span data-ttu-id="2a79c-157">Applets de applet voix entreprise avancées dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a79c-157">Advanced Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-advanced-enterprise-voice-cmdlets.md)  
[<span data-ttu-id="2a79c-158">Cmdlets de l’application vocale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a79c-158">Voice application cmdlets in Lync Server 2013</span></span>](lync-server-2013-voice-application-cmdlets.md)  


[<span data-ttu-id="2a79c-159">Blog Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="2a79c-159">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

