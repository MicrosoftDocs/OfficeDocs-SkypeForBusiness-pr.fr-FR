---
title: 'Lync Server 2013: test du numéro de téléphone par rapport à un itinéraire vocal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed50971c9656d454a44eeee627de95c187ef008f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="46882-102">Testez le numéro de téléphone par rapport à un itinéraire vocal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46882-102">Test telephone number against a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46882-103">_**Dernière modification de la rubrique:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="46882-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46882-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="46882-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="46882-105">Mois</span><span class="sxs-lookup"><span data-stu-id="46882-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46882-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="46882-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="46882-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="46882-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46882-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="46882-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="46882-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="46882-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="46882-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsVoiceRoute.</span><span class="sxs-lookup"><span data-stu-id="46882-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceRoute cmdlet.</span></span> <span data-ttu-id="46882-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="46882-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="46882-112">Description</span><span class="sxs-lookup"><span data-stu-id="46882-112">Description</span></span>

<span data-ttu-id="46882-113">Les itinéraires vocaux fonctionnent conjointement avec les politiques vocales pour vous permettre d’acheminer les appels voix entreprise vers le réseau PSTN.</span><span class="sxs-lookup"><span data-stu-id="46882-113">Voice routes work together with voice policies to help route Enterprise Voice calls to the PSTN network.</span></span> <span data-ttu-id="46882-114">Chaque itinéraire vocal inclut une expression régulière (un modèle de nombre) qui identifie les numéros de téléphone qui seront routés par le biais d’un itinéraire vocal donné: l’itinéraire sera en mesure de gérer les numéros de téléphone correspondant à cette expression régulière.</span><span class="sxs-lookup"><span data-stu-id="46882-114">Each voice route includes a regular expression (a number pattern) that identifies the phone numbers that will be routed through a given voice route: the route will be able to handle any phone numbers that match this regular expression.</span></span> <span data-ttu-id="46882-115">Par exemple, un itinéraire vocal peut avoir une expression régulière qui lui permet de gérer tout numéro à 10 chiffres.</span><span class="sxs-lookup"><span data-stu-id="46882-115">For example, a voice route might have a regular expression that enables it to handle any 10-digit number.</span></span> <span data-ttu-id="46882-116">Cela signifie que l’itinéraire peut gérer un numéro de téléphone tel que celui-ci:</span><span class="sxs-lookup"><span data-stu-id="46882-116">That means the route would be able to handle a phone number such as this:</span></span>

  - <span data-ttu-id="46882-117">2065551219</span><span class="sxs-lookup"><span data-stu-id="46882-117">2065551219</span></span>

<span data-ttu-id="46882-118">L’itinéraire ne peut pas gérer l’un ou l’autre des deux nombres suivants, aucun des deux chiffres:</span><span class="sxs-lookup"><span data-stu-id="46882-118">The route would not be able to handle either of the following two numbers, neither of which has 10 digits:</span></span>

  - <span data-ttu-id="46882-119">5551219</span><span class="sxs-lookup"><span data-stu-id="46882-119">5551219</span></span>

  - <span data-ttu-id="46882-120">12065551219</span><span class="sxs-lookup"><span data-stu-id="46882-120">12065551219</span></span>

<span data-ttu-id="46882-121">L’applet de contrôle test-CsVoiceRoute vérifie si un itinéraire vocal donné peut acheminer un numéro de téléphone spécifié.</span><span class="sxs-lookup"><span data-stu-id="46882-121">The Test-CsVoiceRoute cmdlet verifies whether a given voice route can route a specified phone number.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="46882-122">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="46882-122">Running the test</span></span>

<span data-ttu-id="46882-123">Le processus en deux étapes permet de vérifier que la capacité d’un itinéraire vocal est d’acheminer un numéro de téléphone spécifié.</span><span class="sxs-lookup"><span data-stu-id="46882-123">Verifying the ability of a voice route to route a specified phone number is a two-step process.</span></span> <span data-ttu-id="46882-124">Tout d’abord, vous devez utiliser l’applet de contrôle Get-CsVoiceRoute pour renvoyer une instance de ce routage, puis vous devez utiliser l’applet de contrôle CsVoiceRoute de test pour vérifier la capacité de cet itinéraire à gérer le numéro de téléphone cible.</span><span class="sxs-lookup"><span data-stu-id="46882-124">First you have to use the Get-CsVoiceRoute cmdlet to return an instance of that voice route, and then you have to use the Test-CsVoiceRoute cmdlet to verify the ability of that route to handle the target phone number.</span></span> <span data-ttu-id="46882-125">Par exemple, si vous avez la possibilité de vérifier si l’itinéraire vocal de RedmondVoiceRoute peut acheminer le numéro de téléphone 2065551219:</span><span class="sxs-lookup"><span data-stu-id="46882-125">For example, this command verifies whether the RedmondVoiceRoute voice route can route the phone number 2065551219:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="46882-126">Notez que le numéro de téléphone doit être tapé pour que les utilisateurs puissent composer ce numéro.</span><span class="sxs-lookup"><span data-stu-id="46882-126">Note that the phone number should be typed as you expect users to dial that number.</span></span> <span data-ttu-id="46882-127">Par exemple, si vous ne pensez pas que les utilisateurs incluent l’indicatif du pays et l’indicatif de la région lorsque vous composez, utilisez une syntaxe semblable à celle-ci:</span><span class="sxs-lookup"><span data-stu-id="46882-127">For example, if you do not expect users to include the country code and area code when dialing, then use syntax similar to this:</span></span>

`-TargetNumber "5551219"`

<span data-ttu-id="46882-128">Dans le cas présent, le numéro de la cible quitte le code de pays et l’indicatif de la région.</span><span class="sxs-lookup"><span data-stu-id="46882-128">In this case, the target number leaves out both the country code and the area code.</span></span>

<span data-ttu-id="46882-129">Pour utiliser une seule commande pour tester tous les itinéraires vocaux sur un numéro cible spécifié, utilisez la syntaxe suivante:</span><span class="sxs-lookup"><span data-stu-id="46882-129">To use a single command to test all the voice routes against a specified target number, use syntax such as the following:</span></span>

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="46882-130">Pour plus d’informations, consultez la documentation d’aide de l’applet de contrôle test-CsVoiceRoute.</span><span class="sxs-lookup"><span data-stu-id="46882-130">For more information, see the Help documentation for the Test-CsVoiceRoute cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="46882-131">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="46882-131">Determining success or failure</span></span>

<span data-ttu-id="46882-132">Si l’itinéraire vocal peut router le numéro de téléphone cible, l’applet de contrôle de test-CsVoiceRoute renvoie uniquement la valeur true:</span><span class="sxs-lookup"><span data-stu-id="46882-132">If the voice route can route the target phone number the Test-CsVoiceRoute cmdlet just returns the value True:</span></span>

<span data-ttu-id="46882-133">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="46882-133">MatchesPattern</span></span>

\--------------

<span data-ttu-id="46882-134">True</span><span class="sxs-lookup"><span data-stu-id="46882-134">True</span></span>

<span data-ttu-id="46882-135">Cela signifie que l’itinéraire peut gérer des nombres similaires au numéro cible.</span><span class="sxs-lookup"><span data-stu-id="46882-135">That means that route can handle numbers similar to the target number.</span></span> <span data-ttu-id="46882-136">Si l’itinéraire vocal ne peut pas gérer le numéro cible, test-CsVoiceRoute renvoie la valeur false:</span><span class="sxs-lookup"><span data-stu-id="46882-136">If the voice route is can't handle the target number then Test-CsVoiceRoute returns the value False:</span></span>

<span data-ttu-id="46882-137">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="46882-137">MatchesPattern</span></span>

\--------------

<span data-ttu-id="46882-138">False</span><span class="sxs-lookup"><span data-stu-id="46882-138">False</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="46882-139">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="46882-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="46882-140">Lors du test des itinéraires vocaux, «Failure» est un terme relatif.</span><span class="sxs-lookup"><span data-stu-id="46882-140">When testing voice routes, “failure” is a relative term.</span></span> <span data-ttu-id="46882-141">Dans ce cas, cela ne veut pas dire que l’itinéraire est quelque peu «rompu», ce qui signifie que l’itinéraire ne peut pas gérer le numéro cible.</span><span class="sxs-lookup"><span data-stu-id="46882-141">In this case, it doesn’t mean that the route is somehow “broken;” instead, it just means that the route can't handle the target number.</span></span> <span data-ttu-id="46882-142">Cela peut être dû au fait que l’itinéraire vocal a été configuré de manière incorrecte.</span><span class="sxs-lookup"><span data-stu-id="46882-142">That could be because the voice route was configured incorrectly.</span></span> <span data-ttu-id="46882-143">Cela peut également signifier que l’itinéraire n’était jamais destiné à gérer des nombres à l’aide de ce modèle.</span><span class="sxs-lookup"><span data-stu-id="46882-143">It could also mean that the route was never intended to handle numbers using this pattern.</span></span> <span data-ttu-id="46882-144">Par exemple, si vous ne souhaitez pas acheminer les appels vers d’autres pays sur un itinéraire donné, il est possible que l’itinéraire soit configuré pour rejeter tous les numéros de téléphone incluant un code de pays.</span><span class="sxs-lookup"><span data-stu-id="46882-144">For example, if you do not want to route calls to other countries over a given route that route might be configured to reject all phone numbers that include a country code.</span></span> <span data-ttu-id="46882-145">Si test-CsVoiceRoute renvoie la valeur faux lorsque vous vous attendiez à ce qu’il retourne vrai, vérifiez que vous avez correctement tapé le numéro cible.</span><span class="sxs-lookup"><span data-stu-id="46882-145">If Test-CsVoiceRoute returns False when you expected it to return True, verify that you typed the target number in correctly.</span></span> <span data-ttu-id="46882-146">Si tel est le cas, utilisez une commande similaire à celle-ci pour afficher le NumberPattern configuré pour l’itinéraire:</span><span class="sxs-lookup"><span data-stu-id="46882-146">If you did, then use a command similar to this one to view the NumberPattern configured for the route:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46882-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="46882-147">See Also</span></span>


[<span data-ttu-id="46882-148">Test-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="46882-148">Test-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

