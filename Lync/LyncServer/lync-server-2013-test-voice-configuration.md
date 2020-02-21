---
title: 'Lync Server 2013 : test de la configuration des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3bd2e9b86ee0c14d8fd9e2bbe386d48398d2418
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a><span data-ttu-id="98c41-102">Tester la configuration de la voix dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98c41-102">Test voice configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98c41-103">_**Dernière modification de la rubrique :** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="98c41-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98c41-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="98c41-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="98c41-105">Tous les mois</span><span class="sxs-lookup"><span data-stu-id="98c41-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c41-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="98c41-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="98c41-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="98c41-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98c41-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="98c41-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="98c41-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="98c41-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="98c41-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-applet csvoicetestconfiguration.</span><span class="sxs-lookup"><span data-stu-id="98c41-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceTestConfiguration cmdlet.</span></span> <span data-ttu-id="98c41-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="98c41-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="98c41-112">Description</span><span class="sxs-lookup"><span data-stu-id="98c41-112">Description</span></span>

<span data-ttu-id="98c41-113">Lync Server inclut plusieurs applets de commande Windows PowerShell (telles que test-CsVoiceRoute et test-CsVoicePolicy, test-applet cstrunkconfiguration) qui vous permettent de vérifier que les composants individuels de votre infrastructure voix entreprise-itinéraires vocaux, voix les stratégies, les jonctions SIP fonctionnent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="98c41-113">Lync Server includes several Windows PowerShell cmdlets (such as Test-CsVoiceRoute and Test-CsVoicePolicy, Test-CsTrunkConfiguration) that enable you to verify that the individual pieces of your Enterprise Voice infrastructure – voice routes, voice policies, SIP trunks – are working as expected.</span></span>

<span data-ttu-id="98c41-114">Bien qu’il soit important d’utiliser la voix entreprise, tous les éléments individuels fonctionnent : il est possible de disposer d’un itinéraire de communications vocales valide, d’une stratégie de voix valide et d’une jonction SIP valide, tout en permettant aux utilisateurs de ne pas passer ou recevoir des appels téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="98c41-114">While it’s important with Enterprise Voice that all the individual pieces work: it’s possible to have a valid voice route, a valid voice policy, and a valid SIP trunk, but still have users unable to make or receive phone calls.</span></span> <span data-ttu-id="98c41-115">De ce fait, Lync Server offre également la possibilité de créer des configurations de test vocales.</span><span class="sxs-lookup"><span data-stu-id="98c41-115">Because of that, Lync Server also provides the ability to create voice test configurations.</span></span> <span data-ttu-id="98c41-116">Les configurations de test vocales représentent des scénarios de voix entreprise courants : vous pouvez spécifier des éléments tels que l’itinéraire des communications vocales, une stratégie de voix et un plan de numérotation, puis vérifier que ces éléments individuels fonctionnent ensemble pour fournir un service téléphonique.</span><span class="sxs-lookup"><span data-stu-id="98c41-116">Voice test configurations represent common Enterprise Voice scenarios: you can specify such things as a voice route, a voice policy, and a dial plan, and then verify that those individual items are work able to work together to provide phone service.</span></span> <span data-ttu-id="98c41-117">En outre, vous pouvez valider vos attentes dans un scénario donné.</span><span class="sxs-lookup"><span data-stu-id="98c41-117">In addition, you can validate your expectations in a given scenario.</span></span> <span data-ttu-id="98c41-118">Par exemple, supposons que vous vous attendiez à ce que la combinaison du plan de numérotation A et de la stratégie de voix B entraîne l’acheminement des appels par le biais de l’itinéraire des communications vocales C. Vous pouvez entrer l’itinéraire des communications vocales C comme ExpectedRoute.</span><span class="sxs-lookup"><span data-stu-id="98c41-118">For example, suppose that you expect that the combination of dial plan A and voice policy B would result in calls being routed over voice route C. You can enter voice route C as the ExpectedRoute.</span></span> <span data-ttu-id="98c41-119">Lorsque vous exécutez le test, si l’itinéraire vocal C n’est pas employé, le test est marqué comme ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="98c41-119">When you run the test, if voice route C is not employed then the test will be marked as having failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="98c41-120">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="98c41-120">Running the test</span></span>

<span data-ttu-id="98c41-121">Avant de tester les collections de configuration des communications vocales à l’aide de Windows PowerShell, vous devez d’abord utiliser la cmdlet Get-applet csvoicetestconfiguration pour récupérer une instance de ces paramètres de configuration.</span><span class="sxs-lookup"><span data-stu-id="98c41-121">Before testing Voice configuration collections using Windows PowerShell, you must first use the Get-CsVoiceTestConfiguration cmdlet to retrieve an instance of these configuration settings.</span></span> <span data-ttu-id="98c41-122">Cette instance doit ensuite être redirigée vers le test-applet csvoicetestconfiguration.</span><span class="sxs-lookup"><span data-stu-id="98c41-122">That instance must then be piped to the Test-CsVoiceTestConfiguration.</span></span> <span data-ttu-id="98c41-123">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="98c41-123">For example:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="98c41-124">Pour valider tous les paramètres de configuration des tests vocaux en même temps, utilisez plutôt cette commande :</span><span class="sxs-lookup"><span data-stu-id="98c41-124">To validate all the voice test configuration settings at the same time, use this command instead:</span></span>

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

<span data-ttu-id="98c41-125">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande test-applet csvoicetestconfiguration.</span><span class="sxs-lookup"><span data-stu-id="98c41-125">For more information, see the Help documentation for the Test-CsVoiceTestConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="98c41-126">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="98c41-126">Determining success or failure</span></span>

<span data-ttu-id="98c41-127">L’applet de commande test-applet csvoicetestconfiguration signale si un test a échoué ou réussi, et fournit des informations supplémentaires sur chaque test réussi, comme la règle de traduction, l’itinéraire de communications vocales et l’utilisation PSTN utilisée pour effectuer la tâche :</span><span class="sxs-lookup"><span data-stu-id="98c41-127">The Test-CsVoiceTestConfiguration cmdlet reports whether a test failed or succeeded, and provides additional information about each successful test, such as the translation rule, voice route, and PSTN usage used to complete the task:</span></span>

<span data-ttu-id="98c41-128">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="98c41-128">Result:             Success</span></span>

<span data-ttu-id="98c41-129">TranslatedNumber : + 15551234</span><span class="sxs-lookup"><span data-stu-id="98c41-129">TranslatedNumber:   +15551234</span></span>

<span data-ttu-id="98c41-130">MatchingRule : description =; Modèle = ^ (\\d{4}) $; Translation = + 1\\d ; Name = test ; IsInternalExtension = false</span><span class="sxs-lookup"><span data-stu-id="98c41-130">MatchingRule:       Description=;Pattern=^(\\d{4})$;Translation=+1\\d;Name=Test;IsInternalExtension=False</span></span>

<span data-ttu-id="98c41-131">FirstMatchingRoute : site : Redmond</span><span class="sxs-lookup"><span data-stu-id="98c41-131">FirstMatchingRoute: site:Redmond</span></span>

<span data-ttu-id="98c41-132">MatchingUsage : local</span><span class="sxs-lookup"><span data-stu-id="98c41-132">MatchingUsage:      Local</span></span>

<span data-ttu-id="98c41-133">Si le test échoue, le résultat est signalé comme étant échec :</span><span class="sxs-lookup"><span data-stu-id="98c41-133">If the test fails then the result is reported as Fail:</span></span>

<span data-ttu-id="98c41-134">Résultat : échec</span><span class="sxs-lookup"><span data-stu-id="98c41-134">Result:             Fail</span></span>

<span data-ttu-id="98c41-135">TranslatedNumber:</span><span class="sxs-lookup"><span data-stu-id="98c41-135">TranslatedNumber:</span></span>   

<span data-ttu-id="98c41-136">FirstMatchingRoute:</span><span class="sxs-lookup"><span data-stu-id="98c41-136">FirstMatchingRoute:</span></span>

<span data-ttu-id="98c41-137">MatchingUsage:</span><span class="sxs-lookup"><span data-stu-id="98c41-137">MatchingUsage:</span></span>      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="98c41-138">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="98c41-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="98c41-139">Étant donné que les tests de configuration des tests vocaux testent plusieurs éléments différents, notamment les stratégies de voix, les plans de numérotation, les itinéraires de communications vocales, etc., il existe plusieurs facteurs qui peuvent entraîner l’échec d’un test.</span><span class="sxs-lookup"><span data-stu-id="98c41-139">Because voice test configuration testing tests several different items – including voice policies, dial plans, voice routes, and so on – there are several different factors that could result in a failed test.</span></span> <span data-ttu-id="98c41-140">Si un test échoue, la première étape consiste à passer en revue les paramètres de configuration eux-mêmes à l’aide de la cmdlet Get-applet csvoicetestconfiguration :</span><span class="sxs-lookup"><span data-stu-id="98c41-140">If a test fails, your first step should be to review the configuration settings themselves by using the Get-CsVoiceTestConfiguration cmdlet:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

<span data-ttu-id="98c41-141">Si les paramètres semblent être configurés correctement, réexécutez le test en incluant le paramètre Verbose :</span><span class="sxs-lookup"><span data-stu-id="98c41-141">If the settings seem to be configured correctly, re-run the test while including the Verbose parameter:</span></span>

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

<span data-ttu-id="98c41-142">Le paramètre Verbose fournit un compte pas à pas de chaque action effectuée par test-applet csvoicetestconfiguration, comme illustré dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="98c41-142">The Verbose parameter will provide a step-by-step account of each action taken by Test-CsVoiceTestConfiguration as shown in this example:</span></span>

<span data-ttu-id="98c41-143">VERBOSe : chargement du plan de numérotation : « global »</span><span class="sxs-lookup"><span data-stu-id="98c41-143">VERBOSE: Loading dial plan: "Global"</span></span>

<span data-ttu-id="98c41-144">VERBOSe : chargement de la stratégie de voix : « RedmondDialPlan »</span><span class="sxs-lookup"><span data-stu-id="98c41-144">VERBOSE: Loading voice policy: "RedmondDialPlan"</span></span>

<span data-ttu-id="98c41-145">Ce compte pas à pas peut fournir un indice utile quant à l’endroit où le test a échoué.</span><span class="sxs-lookup"><span data-stu-id="98c41-145">This step-by-step account might provide a useful clue as to where the test actually failed.</span></span> <span data-ttu-id="98c41-146">Si ce n’est pas le cas, vous pouvez utiliser d’autres applets de commande Windows PowerShell (par exemple, test-CsVoicePolicy) et méthodiquement commencer à vérifier les composants individuels inclus dans les paramètres de configuration des tests vocaux.</span><span class="sxs-lookup"><span data-stu-id="98c41-146">If not, you can then use other Windows PowerShell cmdlets (such as Test-CsVoicePolicy) and methodically begin to verify the individual components that are included in the voice test configuration settings.</span></span>

<span data-ttu-id="98c41-147">En outre, sachez qu’il est possible qu’un test puisse acheminer un appel et qu’il soit toujours marqué comme ayant échoué ; Cela peut se produire si vous entrez des valeurs pour ExpectedRoute, ExpectedTranslatedNumber et ExpectedUsage, et que ces attentes ne sont pas satisfaites.</span><span class="sxs-lookup"><span data-stu-id="98c41-147">In addition to that, be aware that it’s possible for a test to be able to route a call and yet still be marked as a failure; that can occur if you enter values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage, and any of those expectations are not met.</span></span> <span data-ttu-id="98c41-148">Par exemple, supposons que vous entriez l’itinéraire des communications vocales C comme itinéraire des communications vocales prévu, mais que le test termine effectivement l’appel à l’aide de l’itinéraire des communications vocales D. Dans ce cas, le test est marqué comme ayant échoué, car l’itinéraire des communications vocales attendu n’a pas été utilisé.</span><span class="sxs-lookup"><span data-stu-id="98c41-148">For example, suppose that you enter voice route C as your expected voice route, but the test actually completes the call using voice route D. In that case the test will be marked as Failed because the expected voice route was not used.</span></span> <span data-ttu-id="98c41-149">Si un test échoue, vous pouvez supprimer les valeurs de ExpectedRoute, ExpectedTranslatedNumber et ExpectedUsage, puis réexécuter le test.</span><span class="sxs-lookup"><span data-stu-id="98c41-149">If a test fails, you might remove the values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage and then re-run the test.</span></span> <span data-ttu-id="98c41-150">Cela vous permettra de déterminer si l’échec de l’appel a échoué, ou si vous attendiez une chose et que vous en recevez une autre.</span><span class="sxs-lookup"><span data-stu-id="98c41-150">That will help you determine whether the failure was because the call couldn't be completed, or because you expect one thing and actually received another.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="98c41-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="98c41-151">See Also</span></span>


[<span data-ttu-id="98c41-152">Test-applet csvoicetestconfiguration</span><span class="sxs-lookup"><span data-stu-id="98c41-152">Test-CsVoiceTestConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

