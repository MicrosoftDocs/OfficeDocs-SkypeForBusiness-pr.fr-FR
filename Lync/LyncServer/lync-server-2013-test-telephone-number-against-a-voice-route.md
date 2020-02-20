---
title: 'Lync Server 2013 : test du numéro de téléphone par rapport à un itinéraire des communications vocales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dc2b921d4e0d487c26532ad1e6102ab32d0162e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="ed848-102">Tester le numéro de téléphone par rapport à un itinéraire des communications vocales dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed848-102">Test telephone number against a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed848-103">_**Dernière modification de la rubrique :** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="ed848-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed848-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="ed848-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ed848-105">Tous les mois</span><span class="sxs-lookup"><span data-stu-id="ed848-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed848-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="ed848-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ed848-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed848-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed848-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="ed848-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ed848-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ed848-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ed848-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsVoiceRoute.</span><span class="sxs-lookup"><span data-stu-id="ed848-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceRoute cmdlet.</span></span> <span data-ttu-id="ed848-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="ed848-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ed848-112">Description</span><span class="sxs-lookup"><span data-stu-id="ed848-112">Description</span></span>

<span data-ttu-id="ed848-113">Les itinéraires des communications vocales fonctionnent avec les stratégies de voix pour acheminer les appels voix entreprise vers le réseau RTC.</span><span class="sxs-lookup"><span data-stu-id="ed848-113">Voice routes work together with voice policies to help route Enterprise Voice calls to the PSTN network.</span></span> <span data-ttu-id="ed848-114">Chaque itinéraire des communications vocales inclut une expression régulière (un modèle numérique) qui identifie les numéros de téléphone qui seront acheminés via un itinéraire de communications vocales donné : l’itinéraire sera en mesure de gérer les numéros de téléphone qui correspondent à cette expression régulière.</span><span class="sxs-lookup"><span data-stu-id="ed848-114">Each voice route includes a regular expression (a number pattern) that identifies the phone numbers that will be routed through a given voice route: the route will be able to handle any phone numbers that match this regular expression.</span></span> <span data-ttu-id="ed848-115">Par exemple, un itinéraire des communications vocales peut avoir une expression régulière qui lui permet de gérer n’importe quel nombre à 10 chiffres.</span><span class="sxs-lookup"><span data-stu-id="ed848-115">For example, a voice route might have a regular expression that enables it to handle any 10-digit number.</span></span> <span data-ttu-id="ed848-116">Cela signifie que l’itinéraire peut traiter un numéro de téléphone tel que celui-ci :</span><span class="sxs-lookup"><span data-stu-id="ed848-116">That means the route would be able to handle a phone number such as this:</span></span>

  - <span data-ttu-id="ed848-117">2065551219</span><span class="sxs-lookup"><span data-stu-id="ed848-117">2065551219</span></span>

<span data-ttu-id="ed848-118">L’itinéraire ne sera pas en mesure de gérer l’un ou l’autre des deux nombres suivants, aucun n’ayant 10 chiffres :</span><span class="sxs-lookup"><span data-stu-id="ed848-118">The route would not be able to handle either of the following two numbers, neither of which has 10 digits:</span></span>

  - <span data-ttu-id="ed848-119">5551219</span><span class="sxs-lookup"><span data-stu-id="ed848-119">5551219</span></span>

  - <span data-ttu-id="ed848-120">12065551219</span><span class="sxs-lookup"><span data-stu-id="ed848-120">12065551219</span></span>

<span data-ttu-id="ed848-121">L’applet de commande test-CsVoiceRoute vérifie si un itinéraire des communications vocales donné peut acheminer un numéro de téléphone spécifié.</span><span class="sxs-lookup"><span data-stu-id="ed848-121">The Test-CsVoiceRoute cmdlet verifies whether a given voice route can route a specified phone number.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ed848-122">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="ed848-122">Running the test</span></span>

<span data-ttu-id="ed848-123">La vérification de la capacité d’un itinéraire des communications vocales à acheminer un numéro de téléphone spécifié est un processus en deux étapes.</span><span class="sxs-lookup"><span data-stu-id="ed848-123">Verifying the ability of a voice route to route a specified phone number is a two-step process.</span></span> <span data-ttu-id="ed848-124">Tout d’abord, vous devez utiliser la cmdlet Get-CsVoiceRoute pour retourner une instance de cet itinéraire de communications vocales, puis utiliser l’applet de commande test-CsVoiceRoute pour vérifier la capacité de cet itinéraire à gérer le numéro de téléphone cible.</span><span class="sxs-lookup"><span data-stu-id="ed848-124">First you have to use the Get-CsVoiceRoute cmdlet to return an instance of that voice route, and then you have to use the Test-CsVoiceRoute cmdlet to verify the ability of that route to handle the target phone number.</span></span> <span data-ttu-id="ed848-125">Par exemple, cette commande vérifie si l’itinéraire de communications vocales RedmondVoiceRoute peut acheminer le numéro de téléphone 2065551219 :</span><span class="sxs-lookup"><span data-stu-id="ed848-125">For example, this command verifies whether the RedmondVoiceRoute voice route can route the phone number 2065551219:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="ed848-126">Notez que le numéro de téléphone doit être tapé comme vous souhaitez que les utilisateurs composent ce numéro.</span><span class="sxs-lookup"><span data-stu-id="ed848-126">Note that the phone number should be typed as you expect users to dial that number.</span></span> <span data-ttu-id="ed848-127">Par exemple, si vous ne prévoyez pas que les utilisateurs doivent inclure le code du pays et l’indicatif régional lors de la numérotation, utilisez une syntaxe similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="ed848-127">For example, if you do not expect users to include the country code and area code when dialing, then use syntax similar to this:</span></span>

`-TargetNumber "5551219"`

<span data-ttu-id="ed848-128">Dans ce cas, le numéro cible exclut le code du pays et l’indicatif régional.</span><span class="sxs-lookup"><span data-stu-id="ed848-128">In this case, the target number leaves out both the country code and the area code.</span></span>

<span data-ttu-id="ed848-129">Pour utiliser une commande unique afin de tester tous les itinéraires des communications vocales par rapport à un numéro cible spécifié, utilisez une syntaxe semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="ed848-129">To use a single command to test all the voice routes against a specified target number, use syntax such as the following:</span></span>

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="ed848-130">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande test-CsVoiceRoute.</span><span class="sxs-lookup"><span data-stu-id="ed848-130">For more information, see the Help documentation for the Test-CsVoiceRoute cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ed848-131">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="ed848-131">Determining success or failure</span></span>

<span data-ttu-id="ed848-132">Si l’itinéraire des communications vocales peut acheminer le numéro de téléphone cible, la cmdlet Test-CsVoiceRoute renvoie simplement la valeur true :</span><span class="sxs-lookup"><span data-stu-id="ed848-132">If the voice route can route the target phone number the Test-CsVoiceRoute cmdlet just returns the value True:</span></span>

<span data-ttu-id="ed848-133">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="ed848-133">MatchesPattern</span></span>

\--------------

<span data-ttu-id="ed848-134">Vrai</span><span class="sxs-lookup"><span data-stu-id="ed848-134">True</span></span>

<span data-ttu-id="ed848-135">Cela signifie que le routage peut gérer des nombres similaires au numéro cible.</span><span class="sxs-lookup"><span data-stu-id="ed848-135">That means that route can handle numbers similar to the target number.</span></span> <span data-ttu-id="ed848-136">Si l’itinéraire des communications vocales ne peut pas gérer le numéro cible, la méthode test-CsVoiceRoute renvoie la valeur false :</span><span class="sxs-lookup"><span data-stu-id="ed848-136">If the voice route is can't handle the target number then Test-CsVoiceRoute returns the value False:</span></span>

<span data-ttu-id="ed848-137">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="ed848-137">MatchesPattern</span></span>

\--------------

<span data-ttu-id="ed848-138">False</span><span class="sxs-lookup"><span data-stu-id="ed848-138">False</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ed848-139">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="ed848-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="ed848-140">Lors du test des itinéraires des communications vocales, « échec » est un terme relatif.</span><span class="sxs-lookup"><span data-stu-id="ed848-140">When testing voice routes, “failure” is a relative term.</span></span> <span data-ttu-id="ed848-141">Dans ce cas, cela ne signifie pas que l’itinéraire est quelque peu « brisé »; à la place, il signifie simplement que l’itinéraire ne peut pas gérer le numéro cible.</span><span class="sxs-lookup"><span data-stu-id="ed848-141">In this case, it doesn’t mean that the route is somehow “broken;” instead, it just means that the route can't handle the target number.</span></span> <span data-ttu-id="ed848-142">Cela peut être dû à une configuration incorrecte de l’itinéraire des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="ed848-142">That could be because the voice route was configured incorrectly.</span></span> <span data-ttu-id="ed848-143">Cela peut également signifier que l’itinéraire n’était jamais destiné à gérer les numéros à l’aide de ce modèle.</span><span class="sxs-lookup"><span data-stu-id="ed848-143">It could also mean that the route was never intended to handle numbers using this pattern.</span></span> <span data-ttu-id="ed848-144">Par exemple, si vous ne souhaitez pas acheminer les appels vers d’autres pays sur un itinéraire donné, celui-ci peut être configuré pour refuser tous les numéros de téléphone incluant un code pays.</span><span class="sxs-lookup"><span data-stu-id="ed848-144">For example, if you do not want to route calls to other countries over a given route that route might be configured to reject all phone numbers that include a country code.</span></span> <span data-ttu-id="ed848-145">Si test-CsVoiceRoute retourne la valeur false lorsque vous attendiez qu’il renvoie la valeur true, vérifiez que vous avez tapé le numéro cible correctement.</span><span class="sxs-lookup"><span data-stu-id="ed848-145">If Test-CsVoiceRoute returns False when you expected it to return True, verify that you typed the target number in correctly.</span></span> <span data-ttu-id="ed848-146">Si vous l’avez fait, utilisez une commande semblable à celle-ci pour afficher les NumberPattern configurés pour l’itinéraire :</span><span class="sxs-lookup"><span data-stu-id="ed848-146">If you did, then use a command similar to this one to view the NumberPattern configured for the route:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ed848-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ed848-147">See Also</span></span>


[<span data-ttu-id="ed848-148">Test-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="ed848-148">Test-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

