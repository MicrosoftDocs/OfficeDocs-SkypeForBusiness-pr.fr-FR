---
title: 'Lync Server 2013 : test du routage des appels téléphoniques PSTN'
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
ms.openlocfilehash: 2dabe54fb2ba4df864d172015efb62ef161c77cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-routing-in-lync-server-2013"></a><span data-ttu-id="8a360-102">Test de l’acheminement des appels téléphoniques RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a360-102">Testing PSTN phone call routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a360-103">_**Dernière modification de la rubrique :** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="8a360-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a360-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="8a360-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8a360-105">Jour</span><span class="sxs-lookup"><span data-stu-id="8a360-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a360-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="8a360-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8a360-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a360-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a360-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="8a360-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8a360-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8a360-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8a360-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande <strong>test-CsInterTrunkRouting</strong> .</span><span class="sxs-lookup"><span data-stu-id="8a360-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsInterTrunkRouting</strong> cmdlet.</span></span> <span data-ttu-id="8a360-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="8a360-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsInterTrunkRouting&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8a360-112">Description</span><span class="sxs-lookup"><span data-stu-id="8a360-112">Description</span></span>

<span data-ttu-id="8a360-113">L’applet de **contrôle test-CsInterTrunkRouting** vérifie que les appels peuvent être routés d’un SIP à un autre.</span><span class="sxs-lookup"><span data-stu-id="8a360-113">The **Test-CsInterTrunkRouting** cmdlet verifies that calls can be routed from one SIP to another.</span></span> <span data-ttu-id="8a360-114">Pour ce faire, l’applet de action reçoit un numéro de téléphone et une configuration de Trunk.</span><span class="sxs-lookup"><span data-stu-id="8a360-114">To do this, the cmdlet is given a phone number and a trunk configuration.</span></span> <span data-ttu-id="8a360-115">**Test-CsInterTrunkRouting** va ensuite signaler les itinéraires correspondants et les utilisations RTC correspondantes pour le numéro spécifié.</span><span class="sxs-lookup"><span data-stu-id="8a360-115">**Test-CsInterTrunkRouting** will then report back matching routes and matching PSTN usages for the specified number.</span></span> <span data-ttu-id="8a360-116">Notez que les appels peuvent être routés entre des segments uniquement si ceux-ci ont un modèle de numéro qui correspond au numéro de téléphone spécifié et uniquement s’ils partagent au moins une utilisation PSTN.</span><span class="sxs-lookup"><span data-stu-id="8a360-116">Note that calls can be routed between trunks only if the trunks have a number pattern that matches the specified phone number and only if the trunks share at least one PSTN usage.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8a360-117">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="8a360-117">Running the test</span></span>

<span data-ttu-id="8a360-118">Les commandes illustrées ci-dessous retournent les itinéraires correspondants et les utilisations de téléphone correspondantes qui permettent aux utilisateurs d’appeler le numéro de téléphone 1-206-555-1219 à l’aide des paramètres de configuration de Trunk pour le site de Redmond.</span><span class="sxs-lookup"><span data-stu-id="8a360-118">The commands shown below return the matching routes and matching phone usages that enable users to call the phone number 1-206-555-1219 using the trunk configuration settings for the Redmond site.</span></span>

    $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
    
    Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219" -TrunkConfiguration $trunk

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8a360-119">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="8a360-119">Determining success or failure</span></span>

<span data-ttu-id="8a360-120">Si les appels peuvent être routés d’un SIP à un autre, vous recevrez une sortie semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="8a360-120">If calls can be routed from one SIP to another, you'll receive output similar to this:</span></span>

<span data-ttu-id="8a360-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span><span class="sxs-lookup"><span data-stu-id="8a360-121">FirstMatchingRoute MatchingUsage MatchingRoutes</span></span>

<span data-ttu-id="8a360-122">\------------------ ------------- --------------</span><span class="sxs-lookup"><span data-stu-id="8a360-122">\------------------ ------------- --------------</span></span>

<span data-ttu-id="8a360-123">RedmondRoute LocalUsage {RedmondRoute}</span><span class="sxs-lookup"><span data-stu-id="8a360-123">RedmondRoute LocalUsage {RedmondRoute}</span></span>

<span data-ttu-id="8a360-124">Si le test échoue, vous recevrez une sortie semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="8a360-124">If the test did not succeed, you'll receive output similar to this:</span></span>

<span data-ttu-id="8a360-125">Test-CsInterTrunkRouting : impossible de traiter la transformation d’argument sur le paramètre</span><span class="sxs-lookup"><span data-stu-id="8a360-125">Test-CsInterTrunkRouting : Cannot process argument transformation on parameter</span></span>

<span data-ttu-id="8a360-126">'TrunkConfiguration'.</span><span class="sxs-lookup"><span data-stu-id="8a360-126">'TrunkConfiguration'.</span></span> <span data-ttu-id="8a360-127">TrunkConfigurationsetting non valide (paramètre).</span><span class="sxs-lookup"><span data-stu-id="8a360-127">Invalid TrunkConfigurationsetting (parameter).</span></span> <span data-ttu-id="8a360-128">Spécifier une</span><span class="sxs-lookup"><span data-stu-id="8a360-128">Specify a</span></span>

<span data-ttu-id="8a360-129">paramètre valide (paramètre), puis réessayez.</span><span class="sxs-lookup"><span data-stu-id="8a360-129">valid setting (parameter) and then try again.</span></span>

<span data-ttu-id="8a360-130">À la ligne : 1 car : 79</span><span class="sxs-lookup"><span data-stu-id="8a360-130">At line:1 char:79</span></span>

<span data-ttu-id="8a360-131">\+Test-CsInterTrunkRouting-TargetNumber "Tél : + 12065551219"</span><span class="sxs-lookup"><span data-stu-id="8a360-131">\+ Test-CsInterTrunkRouting -TargetNumber "tel:+12065551219"</span></span>

<span data-ttu-id="8a360-132">\-TrunkConfiguration $t...</span><span class="sxs-lookup"><span data-stu-id="8a360-132">\-TrunkConfiguration $t ...</span></span>

\+

~~

<span data-ttu-id="8a360-133">\+CategoryInfo : InvalidData : ( :) \[Test-CsInterTrunkRouting\], par</span><span class="sxs-lookup"><span data-stu-id="8a360-133">\+ CategoryInfo : InvalidData: (:) \[Test-CsInterTrunkRouting\], Par</span></span>

<span data-ttu-id="8a360-134">ameterBindingArgumentTransformationException</span><span class="sxs-lookup"><span data-stu-id="8a360-134">ameterBindingArgumentTransformationException</span></span>

<span data-ttu-id="8a360-135">\+FullyQualifiedErrorId : ParameterArgumentTransformationError, Microsoft. R</span><span class="sxs-lookup"><span data-stu-id="8a360-135">\+ FullyQualifiedErrorId : ParameterArgumentTransformationError,Microsoft.R</span></span>

<span data-ttu-id="8a360-136">TC. Gestion. Voice. applets. TestOcsInterTrunkRoutingCmdlet</span><span class="sxs-lookup"><span data-stu-id="8a360-136">tc.Management.Voice.Cmdlets.TestOcsInterTrunkRoutingCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8a360-137">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="8a360-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="8a360-138">Voici quelques raisons courantes pour lesquelles **les tests-CsInterTrunkRouting** peuvent échouer :</span><span class="sxs-lookup"><span data-stu-id="8a360-138">Here are some common reasons why **Test-CsInterTrunkRouting** might fail:</span></span>

  - <span data-ttu-id="8a360-139">Vous avez spécifié des paramètres non valides.</span><span class="sxs-lookup"><span data-stu-id="8a360-139">You specified invalid parameters.</span></span> <span data-ttu-id="8a360-140">Le Trunk n’est peut-être pas encore correctement configuré et le numéro de cible spécifié est peut-être incorrect ou non valide.</span><span class="sxs-lookup"><span data-stu-id="8a360-140">The trunk might not yet be correctly configured and the specified target number might be incorrect or invalid.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8a360-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8a360-141">See Also</span></span>


[<span data-ttu-id="8a360-142">Get-CsTrunk</span><span class="sxs-lookup"><span data-stu-id="8a360-142">Get-CsTrunk</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk)  
[<span data-ttu-id="8a360-143">Get-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="8a360-143">Get-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

