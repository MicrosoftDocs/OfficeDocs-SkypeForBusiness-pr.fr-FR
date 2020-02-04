---
title: 'Lync Server 2013 : tester les règles vocales, les itinéraires et les stratégies'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c3b2d98846e537a9a416eaabaf6b02627c7273f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a><span data-ttu-id="f750c-102">Tester les règles vocales, les itinéraires et les stratégies dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f750c-102">Test voice rules, routes, and policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f750c-103">_**Dernière modification de la rubrique :** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="f750c-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f750c-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="f750c-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f750c-105">Mois</span><span class="sxs-lookup"><span data-stu-id="f750c-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f750c-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="f750c-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f750c-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f750c-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f750c-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="f750c-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f750c-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f750c-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f750c-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsVoiceUser.</span><span class="sxs-lookup"><span data-stu-id="f750c-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceUser cmdlet.</span></span> <span data-ttu-id="f750c-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="f750c-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f750c-112">Description</span><span class="sxs-lookup"><span data-stu-id="f750c-112">Description</span></span>

<span data-ttu-id="f750c-113">Lorsqu’un utilisateur effectue un appel téléphonique, le routage de l’appel prend pour atteindre sa destination dépend des stratégies et des plans de numérotation attribués à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f750c-113">When a user makes a phone call, the route the call takes to reach its destination depends on both the policies and dial plans assigned to that user.</span></span> <span data-ttu-id="f750c-114">À partir de l’adresse SIP et du numéro de téléphone d’un utilisateur, l’applet de contrôle test-CsVoiceUser vérifie si l’utilisateur en question peut effectuer un appel à ce numéro.</span><span class="sxs-lookup"><span data-stu-id="f750c-114">Given a user’s SIP address and a phone number, the Test-CsVoiceUser cmdlet verifies whether the user in question can complete a call to that number.</span></span> <span data-ttu-id="f750c-115">Si le test réussit, test-CsVoiceUser renvoie la valeur suivante :</span><span class="sxs-lookup"><span data-stu-id="f750c-115">If the test succeeds, Test-CsVoiceUser returns the following:</span></span>

  - <span data-ttu-id="f750c-116">Le numéro a été converti au format E. 164 (en fonction du plan de numérotation de l’utilisateur).</span><span class="sxs-lookup"><span data-stu-id="f750c-116">The number translated to E.164 format (based on the user’s dial plan)</span></span>

  - <span data-ttu-id="f750c-117">Règle de normalisation ayant fourni cette traduction</span><span class="sxs-lookup"><span data-stu-id="f750c-117">The normalization rule that supplied that translation</span></span>

  - <span data-ttu-id="f750c-118">La gamme vocale utilisée (en fonction de la priorité de l’itinéraire);</span><span class="sxs-lookup"><span data-stu-id="f750c-118">The voice route used (based on route priority);</span></span>

  - <span data-ttu-id="f750c-119">L’utilisation du téléphone qui a lié la politique vocale de l’utilisateur à l’itinéraire vocal.</span><span class="sxs-lookup"><span data-stu-id="f750c-119">The phone usage that linked the user’s voice policy to the voice route.</span></span>

<span data-ttu-id="f750c-120">Test-CsVoiceUser vous permet de déterminer si un numéro de téléphone spécifique sera routé et traduit comme prévu et peut vous aider à résoudre les problèmes liés aux appels rencontrés par les utilisateurs individuels.</span><span class="sxs-lookup"><span data-stu-id="f750c-120">Test-CsVoiceUser enables you to determine whether a specific phone number will route and translate as expected, and can help troubleshoot call-related problems that are experienced by individual users.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f750c-121">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="f750c-121">Running the test</span></span>

<span data-ttu-id="f750c-122">Lorsque vous exécutez l’applet de contrôle test-CsVoiceUser, vous devez fournir deux éléments d’information : le numéro numéroté (DialedNumber) et l’identité du compte d’utilisateur testé.</span><span class="sxs-lookup"><span data-stu-id="f750c-122">When running the Test-CsVoiceUser cmdlet you must supply two pieces of information: the number being dialed (DialedNumber) and the Identity of the user account being tested.</span></span> <span data-ttu-id="f750c-123">Par exemple, la commande suivante teste la capacité de l’utilisateur qui dispose de l’adresse sip :kenmyer@litwareinc.com pour effectuer un appel vers le numéro de téléphone + 1206555-1219 :</span><span class="sxs-lookup"><span data-stu-id="f750c-123">For example, this command tests the ability of the user who has the SIP address sip:kenmyer@litwareinc.com to make a call to the phone number +1206555-1219:</span></span>

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

<span data-ttu-id="f750c-124">Le numéro de téléphone doit être mis en forme comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="f750c-124">The phone number should be formatted in the way that you expect it to be dialed.</span></span> <span data-ttu-id="f750c-125">Par exemple, si les utilisateurs n’entrent pas en principe le 1er avant de passer un appel longue distance, utilisez ce format :</span><span class="sxs-lookup"><span data-stu-id="f750c-125">For example, if users typically do not dial the 1 before placing a long distance call then you should use this format:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="f750c-126">Bien entendu, dans ce cas, le test échoue si vous n’avez pas de règle de normalisation qui peut traduire correctement le numéro 2065551219 au format de téléphone E. 164 utilisé par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f750c-126">Of course, in that case, the test will fail if you do not have a normalization rule that can correctly translate the number 2065551219 into the E.164 telephone format that is used by Lync Server.</span></span> <span data-ttu-id="f750c-127">Pour plus d’informations, consultez la rubrique d’aide New-CsVoiceNormalizationRule cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f750c-127">For more information, see the help topic New-CsVoiceNormalizationRule cmdlet.</span></span>

<span data-ttu-id="f750c-128">Si vous souhaitez exécuter ce test sur chacun de vos comptes d’utilisateurs, vous pouvez utiliser une commande semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f750c-128">If you want to run this same test against each of your user accounts, you can use a command similar to the following:</span></span>

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

<span data-ttu-id="f750c-129">Pour plus d’informations, consultez la documentation d’aide de l’applet de contrôle test-CsVoiceUser.</span><span class="sxs-lookup"><span data-stu-id="f750c-129">For more information, see the Help documentation for the Test-CsVoiceUser cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f750c-130">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="f750c-130">Determining success or failure</span></span>

<span data-ttu-id="f750c-131">Si le test est effectué avec succès (autrement dit, si l’utilisateur peut effectuer un appel téléphonique au numéro spécifié), la sortie affiche des informations telles que le numéro de téléphone traduit et la règle de normalisation et l’itinéraire vocaux correspondants :</span><span class="sxs-lookup"><span data-stu-id="f750c-131">If the test is completed successfully (that is, if the user can make a phone call to the specified number), the output will show information like the translated phone number and the matching normalization rule and voice route:</span></span>

<span data-ttu-id="f750c-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="f750c-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span></span>

<span data-ttu-id="f750c-133">\----------------    ------------    ------------------    -------------</span><span class="sxs-lookup"><span data-stu-id="f750c-133">\----------------    ------------    ------------------    -------------</span></span>

<span data-ttu-id="f750c-134">\+12065551219 descripteur...    LocalRoute local</span><span class="sxs-lookup"><span data-stu-id="f750c-134">\+12065551219        Descripti...    LocalRoute            Local</span></span>

<span data-ttu-id="f750c-135">En raison des limitations de l’écran Windows PowerShell, il est possible que certaines informations renvoyées (en particulier la description complète de la règle de normalisation correspondante) n’apparaissent pas à l’écran.</span><span class="sxs-lookup"><span data-stu-id="f750c-135">Because of the limitations of the Windows PowerShell screen, at least some returned information (most notably the full description of the matching normalization rule) might not appear on-screen.</span></span> <span data-ttu-id="f750c-136">Si vous êtes uniquement intéressé par la réussite ou l’échec du test, cela peut avoir un problème.</span><span class="sxs-lookup"><span data-stu-id="f750c-136">If you are only interested in the success or failure of the test, then this might not matter.</span></span> <span data-ttu-id="f750c-137">Si vous préférez afficher tous les détails des données renvoyées, vous pouvez les canalr dans la cmdlet Format-List lors de l’exécution du test :</span><span class="sxs-lookup"><span data-stu-id="f750c-137">If you would prefer to see the full details of the returned data then pipe the output to the Format-List cmdlet when running the test:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

<span data-ttu-id="f750c-138">La sortie s’affichera dans un autre format compatible avec le lecteur :</span><span class="sxs-lookup"><span data-stu-id="f750c-138">That will display the output in a more reader-friendly format:</span></span>

<span data-ttu-id="f750c-139">TranslatedNumber : + 12065551219</span><span class="sxs-lookup"><span data-stu-id="f750c-139">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="f750c-140">MatchingRule : description =; Pattern = ^ (\\d{11}) $; Traduction = + $1 ;</span><span class="sxs-lookup"><span data-stu-id="f750c-140">MatchingRule : Description=;Pattern=^(\\d{11})$;Translation=+$1;</span></span>

<span data-ttu-id="f750c-141">Nom = préfixe tout ; IsInternalExtension = faux</span><span class="sxs-lookup"><span data-stu-id="f750c-141">Name=Prefix All;IsInternalExtension=False</span></span>

<span data-ttu-id="f750c-142">FirsMatchingRoute : LocalRoute</span><span class="sxs-lookup"><span data-stu-id="f750c-142">FirsMatchingRoute : LocalRoute</span></span>

<span data-ttu-id="f750c-143">MatchingUsage : local</span><span class="sxs-lookup"><span data-stu-id="f750c-143">MatchingUsage : Local</span></span>

<span data-ttu-id="f750c-144">Si le test échoue, test-CsVoiceUser renvoie un ensemble vide de valeurs de propriété :</span><span class="sxs-lookup"><span data-stu-id="f750c-144">If the test fails, Test-CsVoiceUser will return an empty set of property values:</span></span>

<span data-ttu-id="f750c-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="f750c-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="f750c-146">\---------------- ------------ ------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="f750c-146">\---------------- ------------ ------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f750c-147">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="f750c-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="f750c-148">L’applet de commande test-CsVoiceUser peut échouer pour différentes raisons : il est possible qu’il n’y ait pas de règle de normalisation qui peut traduire le numéro de téléphone fourni.</span><span class="sxs-lookup"><span data-stu-id="f750c-148">There are any number of reasons why the Test-CsVoiceUser cmdlet might fail: there might not be a normalization rule that can translate the provided phone number.</span></span> <span data-ttu-id="f750c-149">Il y a peut-être des problèmes avec l’itinéraire vocal.</span><span class="sxs-lookup"><span data-stu-id="f750c-149">There could be problems with the voice route.</span></span> <span data-ttu-id="f750c-150">Il y a peut-être un problème de configuration avec le plan de numérotation affecté à l’utilisateur en question.</span><span class="sxs-lookup"><span data-stu-id="f750c-150">There could be a configuration issue with the dial plan assigned to the user in question.</span></span> <span data-ttu-id="f750c-151">Pour cette raison, vous souhaiterez peut-être inclure le paramètre Verbose lorsque vous exécutez l’applet de contrôle de test-CsVoiceUser :</span><span class="sxs-lookup"><span data-stu-id="f750c-151">Because of that, you might want to include the Verbose parameter when you are running the Test-CsVoiceUser cmdlet:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

<span data-ttu-id="f750c-152">Lorsque l’applet de demande détaillée est incluse, test-CsVoiceUser émet un compte détaillé de toutes les étapes de la procédure de vérification.</span><span class="sxs-lookup"><span data-stu-id="f750c-152">When the Verbose cmdlet is included, Test-CsVoiceUser will issue a detailed account of all the steps in takes when conducting its checks.</span></span> <span data-ttu-id="f750c-153">Par exemple, il se peut que vous voyiez des étapes semblables à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f750c-153">For example, you might see steps similar to these:</span></span> 

<span data-ttu-id="f750c-154">DÉTAILLÉ : localisation de l’utilisateur avec l’identité « sip :kenmyer@litwareinc.com »</span><span class="sxs-lookup"><span data-stu-id="f750c-154">VERBOSE: Locating user with identity "sip:kenmyer@litwareinc.com"</span></span>

<span data-ttu-id="f750c-155">DÉTAILLÉ : Téléchargement d’un plan de numérotation : « RedmondDialPlan »</span><span class="sxs-lookup"><span data-stu-id="f750c-155">VERBOSE: Loading dial plan: "RedmondDialPlan"</span></span>

<span data-ttu-id="f750c-156">Les informations supplémentaires suivantes peuvent fournir des conseils sur les mesures que vous pouvez prendre pour identifier la cause du problème.</span><span class="sxs-lookup"><span data-stu-id="f750c-156">This additional information can provide hints as to the steps that you can take to pinpoint the cause of the failure.</span></span> <span data-ttu-id="f750c-157">Par exemple, la sortie détaillée présentée ici nous indique que l’utilisateur testé a été affecté au plan de numérotation RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="f750c-157">For example, the verbose output shown here tells us that the user being tested was assigned the dial plan RedmondDialPlan.</span></span> <span data-ttu-id="f750c-158">Si le test échoue, une étape suivante logique consiste à vérifier que RedmondDialPlan peut traduire le numéro de téléphone fourni.</span><span class="sxs-lookup"><span data-stu-id="f750c-158">If the test has failed, one logical next step would be to verify that RedmondDialPlan can translate the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f750c-159">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f750c-159">See Also</span></span>


[<span data-ttu-id="f750c-160">Test-CsVoiceUser</span><span class="sxs-lookup"><span data-stu-id="f750c-160">Test-CsVoiceUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

