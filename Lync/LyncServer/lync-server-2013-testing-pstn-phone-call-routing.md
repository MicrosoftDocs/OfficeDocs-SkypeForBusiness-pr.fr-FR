---
title: 'Lync Server 2013 : test du routage des appels de téléphonie RTC'
description: 'Lync Server 2013 : test du routage des appels RTC.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call routing
ms:assetid: 301dd44d-03e9-41cd-9722-54e00365aa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727302(v=OCS.15)
ms:contentKeyID: 63969598
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da931b43176932a9b6781fa27318e83e6994548c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556270"
---
# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="6ca7a-103">Test du routage des appels RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ca7a-103">Testing PSTN phone call routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ca7a-104">_**Dernière modification de la rubrique :** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="6ca7a-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ca7a-105">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="6ca7a-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6ca7a-106">Journalière</span><span class="sxs-lookup"><span data-stu-id="6ca7a-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ca7a-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="6ca7a-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6ca7a-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ca7a-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ca7a-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="6ca7a-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6ca7a-110">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6ca7a-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6ca7a-111">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet <strong>test-CsInterTrunkRouting</strong> .</span><span class="sxs-lookup"><span data-stu-id="6ca7a-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="6ca7a-112">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="6ca7a-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6ca7a-113">Description</span><span class="sxs-lookup"><span data-stu-id="6ca7a-113">Description</span></span>

<span data-ttu-id="6ca7a-114">L’applet de commande **test-CsInterTrunkRouting** vérifie que les appels peuvent être acheminés d’un SIP à un autre.</span><span class="sxs-lookup"><span data-stu-id="6ca7a-114">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="6ca7a-115">Pour ce faire, l’applet de commande reçoit un numéro de téléphone et une configuration de jonction.</span><span class="sxs-lookup"><span data-stu-id="6ca7a-115">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="6ca7a-116">**Test-CsInterTrunkRouting** indique alors les itinéraires correspondants et les utilisations RTC correspondantes pour le numéro spécifié.</span><span class="sxs-lookup"><span data-stu-id="6ca7a-116">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="6ca7a-117">Notez que les appels peuvent être routés entre des segments uniquement si ceux-ci ont un modèle de numéro qui correspond au numéro de téléphone spécifié et uniquement s’ils partagent au moins une utilisation PSTN.</span><span class="sxs-lookup"><span data-stu-id="6ca7a-117">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6ca7a-118">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="6ca7a-118">Running the test</span></span>

<span data-ttu-id="6ca7a-119">Les commandes indiquées ci-dessous renvoient les itinéraires correspondants et les utilisations téléphoniques correspondantes qui permettent aux utilisateurs d’appeler le numéro de téléphone 1-206-555-1219 à l’aide des paramètres de configuration de jonction pour le site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="6ca7a-119">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6ca7a-120">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="6ca7a-120">Determining success or failure</span></span>

<span data-ttu-id="6ca7a-121">Si les appels peuvent être acheminés d’un SIP à un autre, vous recevrez un résultat semblable à celui-ci :</span><span class="sxs-lookup"><span data-stu-id="6ca7a-121">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="6ca7a-122">FirstMatchingRoute MatchingUsage MatchingRoutes</span><span class="sxs-lookup"><span data-stu-id="6ca7a-122">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="6ca7a-123">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="6ca7a-123">\------------------ ------------- --------------</span></span>

<span data-ttu-id="6ca7a-124">RedmondRoute LocalUsage {RedmondRoute}</span><span class="sxs-lookup"><span data-stu-id="6ca7a-124">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="6ca7a-125">Si le test a échoué, vous recevrez un résultat similaire à celui-ci :</span><span class="sxs-lookup"><span data-stu-id="6ca7a-125">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="6ca7a-126">Test-CsInterTrunkRouting : impossible de traiter la transformation d’argument sur le paramètre</span><span class="sxs-lookup"><span data-stu-id="6ca7a-126">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="6ca7a-127">« TrunkConfiguration ».</span><span class="sxs-lookup"><span data-stu-id="6ca7a-127">'TrunkConfiguration'.</span></span> <span data-ttu-id="6ca7a-128">TrunkConfigurationsetting non valide (paramètre).</span><span class="sxs-lookup"><span data-stu-id="6ca7a-128">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="6ca7a-129">Spécifier une</span><span class="sxs-lookup"><span data-stu-id="6ca7a-129">Specify a</span></span>

<span data-ttu-id="6ca7a-130">paramètre valide (paramètre), puis réessayez.</span><span class="sxs-lookup"><span data-stu-id="6ca7a-130">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="6ca7a-131">À la ligne : 1 char : 79</span><span class="sxs-lookup"><span data-stu-id="6ca7a-131">At line:1 char:79</span></span>

<span data-ttu-id="6ca7a-132">\+ Test-CsInterTrunkRouting-TargetNumber "Tél : + 12065551219"</span><span class="sxs-lookup"><span data-stu-id="6ca7a-132">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="6ca7a-133">\-TrunkConfiguration $t...</span><span class="sxs-lookup"><span data-stu-id="6ca7a-133">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="6ca7a-134">\+ CategoryInfo : InvalidData : ( :) \[ Test-CsInterTrunkRouting \] , par</span><span class="sxs-lookup"><span data-stu-id="6ca7a-134">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="6ca7a-135">ameterBindingArgumentTransformationException</span><span class="sxs-lookup"><span data-stu-id="6ca7a-135">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="6ca7a-136">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError, Microsoft. R</span><span class="sxs-lookup"><span data-stu-id="6ca7a-136">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="6ca7a-137">TC. Management. Voice. cmdlets. TestOcsInterTrunkRoutingCmdlet</span><span class="sxs-lookup"><span data-stu-id="6ca7a-137">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6ca7a-138">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="6ca7a-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="6ca7a-139">Voici quelques-unes des causes courantes de l’échec **de test-CsInterTrunkRouting** :</span><span class="sxs-lookup"><span data-stu-id="6ca7a-139">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="6ca7a-140">Vous avez spécifié des paramètres non valides.</span><span class="sxs-lookup"><span data-stu-id="6ca7a-140">You specified invalid parameters.</span></span> <span data-ttu-id="6ca7a-141">La jonction n’est peut-être pas encore correctement configurée et le numéro cible spécifié est peut-être incorrect ou non valide.</span><span class="sxs-lookup"><span data-stu-id="6ca7a-141">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6ca7a-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6ca7a-142">See Also</span></span>


[<span data-ttu-id="6ca7a-143">Get-CsTrunk</span><span class="sxs-lookup"><span data-stu-id="6ca7a-143">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="6ca7a-144">Get-applet cstrunkconfiguration</span><span class="sxs-lookup"><span data-stu-id="6ca7a-144">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

