---
title: 'Lync Server 2013 : test des règles, des itinéraires et des stratégies de voix'
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
ms.openlocfilehash: bbf04728db30bada37e43f14b33420ede1ce9258
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a><span data-ttu-id="a4239-102">Test des règles, des itinéraires et des stratégies de voix dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4239-102">Test voice rules, routes, and policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4239-103">_**Dernière modification de la rubrique :** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="a4239-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4239-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="a4239-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a4239-105">Tous les mois</span><span class="sxs-lookup"><span data-stu-id="a4239-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4239-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="a4239-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a4239-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4239-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4239-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="a4239-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a4239-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a4239-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a4239-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsVoiceUser.</span><span class="sxs-lookup"><span data-stu-id="a4239-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceUser cmdlet.</span></span> <span data-ttu-id="a4239-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="a4239-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a4239-112">Description</span><span class="sxs-lookup"><span data-stu-id="a4239-112">Description</span></span>

<span data-ttu-id="a4239-113">Lorsqu’un utilisateur passe un appel téléphonique, l’itinéraire emprunté par l’appel pour atteindre sa destination dépend à la fois des stratégies et des plans de numérotation attribués à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a4239-113">When a user makes a phone call, the route the call takes to reach its destination depends on both the policies and dial plans assigned to that user.</span></span> <span data-ttu-id="a4239-114">À partir de l’adresse SIP d’un utilisateur et d’un numéro de téléphone, l’applet de commande test-CsVoiceUser vérifie si l’utilisateur en question peut effectuer un appel à ce numéro.</span><span class="sxs-lookup"><span data-stu-id="a4239-114">Given a user’s SIP address and a phone number, the Test-CsVoiceUser cmdlet verifies whether the user in question can complete a call to that number.</span></span> <span data-ttu-id="a4239-115">Si le test réussit, test-CsVoiceUser renvoie les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a4239-115">If the test succeeds, Test-CsVoiceUser returns the following:</span></span>

  - <span data-ttu-id="a4239-116">Le nombre est traduit au format E. 164 (basé sur le plan de numérotation de l’utilisateur)</span><span class="sxs-lookup"><span data-stu-id="a4239-116">The number translated to E.164 format (based on the user’s dial plan)</span></span>

  - <span data-ttu-id="a4239-117">Règle de normalisation qui a fourni cette traduction</span><span class="sxs-lookup"><span data-stu-id="a4239-117">The normalization rule that supplied that translation</span></span>

  - <span data-ttu-id="a4239-118">Itinéraire des communications vocales utilisé (en fonction de la priorité de l’itinéraire);</span><span class="sxs-lookup"><span data-stu-id="a4239-118">The voice route used (based on route priority);</span></span>

  - <span data-ttu-id="a4239-119">L’utilisation téléphonique qui a lié la stratégie de voix de l’utilisateur à l’itinéraire des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="a4239-119">The phone usage that linked the user’s voice policy to the voice route.</span></span>

<span data-ttu-id="a4239-120">Test-CsVoiceUser vous permet de déterminer si un numéro de téléphone spécifique achemine et traduit comme prévu, et peut vous aider à résoudre les problèmes liés aux appels rencontrés par les utilisateurs individuels.</span><span class="sxs-lookup"><span data-stu-id="a4239-120">Test-CsVoiceUser enables you to determine whether a specific phone number will route and translate as expected, and can help troubleshoot call-related problems that are experienced by individual users.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a4239-121">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="a4239-121">Running the test</span></span>

<span data-ttu-id="a4239-122">Lors de l’exécution de la cmdlet Test-CsVoiceUser, vous devez fournir deux informations : le numéro composé (DialedNumber) et l’identité du compte d’utilisateur en cours de test.</span><span class="sxs-lookup"><span data-stu-id="a4239-122">When running the Test-CsVoiceUser cmdlet you must supply two pieces of information: the number being dialed (DialedNumber) and the Identity of the user account being tested.</span></span> <span data-ttu-id="a4239-123">Par exemple, cette commande teste la capacité de l’utilisateur qui a l’adresse SIP sip :kenmyer@litwareinc.com à appeler le numéro de téléphone + 1206555-1219 :</span><span class="sxs-lookup"><span data-stu-id="a4239-123">For example, this command tests the ability of the user who has the SIP address sip:kenmyer@litwareinc.com to make a call to the phone number +1206555-1219:</span></span>

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

<span data-ttu-id="a4239-124">Le numéro de téléphone doit être mis en forme de la manière dont vous pensez qu’il est composé.</span><span class="sxs-lookup"><span data-stu-id="a4239-124">The phone number should be formatted in the way that you expect it to be dialed.</span></span> <span data-ttu-id="a4239-125">Par exemple, si les utilisateurs ne composent généralement pas le 1 avant d’effectuer un appel longue distance, vous devez utiliser ce format :</span><span class="sxs-lookup"><span data-stu-id="a4239-125">For example, if users typically do not dial the 1 before placing a long distance call then you should use this format:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="a4239-126">Bien entendu, dans ce cas, le test échoue si vous n’avez pas de règle de normalisation qui peut convertir correctement le numéro 2065551219 au format de téléphone E. 164 utilisé par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a4239-126">Of course, in that case, the test will fail if you do not have a normalization rule that can correctly translate the number 2065551219 into the E.164 telephone format that is used by Lync Server.</span></span> <span data-ttu-id="a4239-127">Pour plus d’informations, consultez la rubrique d’aide New-CsVoiceNormalizationRule cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a4239-127">For more information, see the help topic New-CsVoiceNormalizationRule cmdlet.</span></span>

<span data-ttu-id="a4239-128">Si vous souhaitez exécuter le même test sur chacun de vos comptes d’utilisateur, vous pouvez utiliser une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="a4239-128">If you want to run this same test against each of your user accounts, you can use a command similar to the following:</span></span>

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

<span data-ttu-id="a4239-129">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande test-CsVoiceUser.</span><span class="sxs-lookup"><span data-stu-id="a4239-129">For more information, see the Help documentation for the Test-CsVoiceUser cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a4239-130">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="a4239-130">Determining success or failure</span></span>

<span data-ttu-id="a4239-131">Si le test est réussi (c’est-à-dire, si l’utilisateur peut effectuer un appel téléphonique vers le numéro spécifié), le résultat affiche des informations telles que le numéro de téléphone traduit et la règle de normalisation correspondante et l’itinéraire des communications vocales :</span><span class="sxs-lookup"><span data-stu-id="a4239-131">If the test is completed successfully (that is, if the user can make a phone call to the specified number), the output will show information like the translated phone number and the matching normalization rule and voice route:</span></span>

<span data-ttu-id="a4239-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="a4239-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span></span>

<span data-ttu-id="a4239-133">\----------------    ------------    ------------------    -------------</span><span class="sxs-lookup"><span data-stu-id="a4239-133">\----------------    ------------    ------------------    -------------</span></span>

<span data-ttu-id="a4239-134">\+12065551219 descripti...    LocalRoute local</span><span class="sxs-lookup"><span data-stu-id="a4239-134">\+12065551219        Descripti...    LocalRoute            Local</span></span>

<span data-ttu-id="a4239-135">En raison des limites de l’écran Windows PowerShell, il se peut qu’au moins une partie des informations renvoyées (notamment la description complète de la règle de normalisation correspondante) ne s’affiche pas à l’écran.</span><span class="sxs-lookup"><span data-stu-id="a4239-135">Because of the limitations of the Windows PowerShell screen, at least some returned information (most notably the full description of the matching normalization rule) might not appear on-screen.</span></span> <span data-ttu-id="a4239-136">Si vous êtes intéressé uniquement par la réussite ou l’échec du test, cela n’a pas d’importance.</span><span class="sxs-lookup"><span data-stu-id="a4239-136">If you are only interested in the success or failure of the test, then this might not matter.</span></span> <span data-ttu-id="a4239-137">Si vous préférez afficher les détails complets des données renvoyées, redirigez la sortie vers la cmdlet Format-List lors de l’exécution du test :</span><span class="sxs-lookup"><span data-stu-id="a4239-137">If you would prefer to see the full details of the returned data then pipe the output to the Format-List cmdlet when running the test:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

<span data-ttu-id="a4239-138">Cela permet d’afficher la sortie dans un format plus facile à lire :</span><span class="sxs-lookup"><span data-stu-id="a4239-138">That will display the output in a more reader-friendly format:</span></span>

<span data-ttu-id="a4239-139">TranslatedNumber : + 12065551219</span><span class="sxs-lookup"><span data-stu-id="a4239-139">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="a4239-140">MatchingRule : description =; Modèle = ^ (\\d{11}) $; Translation = + $1 ;</span><span class="sxs-lookup"><span data-stu-id="a4239-140">MatchingRule : Description=;Pattern=^(\\d{11})$;Translation=+$1;</span></span>

<span data-ttu-id="a4239-141">Nom = préfixe tout ; IsInternalExtension = false</span><span class="sxs-lookup"><span data-stu-id="a4239-141">Name=Prefix All;IsInternalExtension=False</span></span>

<span data-ttu-id="a4239-142">FirsMatchingRoute : LocalRoute</span><span class="sxs-lookup"><span data-stu-id="a4239-142">FirsMatchingRoute : LocalRoute</span></span>

<span data-ttu-id="a4239-143">MatchingUsage : local</span><span class="sxs-lookup"><span data-stu-id="a4239-143">MatchingUsage : Local</span></span>

<span data-ttu-id="a4239-144">Si le test échoue, test-CsVoiceUser renvoie un ensemble vide de valeurs de propriété :</span><span class="sxs-lookup"><span data-stu-id="a4239-144">If the test fails, Test-CsVoiceUser will return an empty set of property values:</span></span>

<span data-ttu-id="a4239-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="a4239-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="a4239-146">\---------------- ------------ ------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="a4239-146">\---------------- ------------ ------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a4239-147">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="a4239-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="a4239-148">Il existe un certain nombre de raisons pour lesquelles la cmdlet Test-CsVoiceUser peut échouer : il se peut qu’il n’existe pas de règle de normalisation pouvant traduire le numéro de téléphone fourni.</span><span class="sxs-lookup"><span data-stu-id="a4239-148">There are any number of reasons why the Test-CsVoiceUser cmdlet might fail: there might not be a normalization rule that can translate the provided phone number.</span></span> <span data-ttu-id="a4239-149">Il peut y avoir des problèmes avec l’itinéraire des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="a4239-149">There could be problems with the voice route.</span></span> <span data-ttu-id="a4239-150">Il peut y avoir un problème de configuration avec le plan de numérotation affecté à l’utilisateur en question.</span><span class="sxs-lookup"><span data-stu-id="a4239-150">There could be a configuration issue with the dial plan assigned to the user in question.</span></span> <span data-ttu-id="a4239-151">Pour cette raison, vous souhaiterez peut-être inclure le paramètre Verbose lorsque vous exécutez la cmdlet Test-CsVoiceUser :</span><span class="sxs-lookup"><span data-stu-id="a4239-151">Because of that, you might want to include the Verbose parameter when you are running the Test-CsVoiceUser cmdlet:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

<span data-ttu-id="a4239-152">Lorsque la cmdlet verbose est incluse, test-CsVoiceUser émettra un compte détaillé de toutes les étapes de la procédure à suivre lors de la réalisation de ses vérifications.</span><span class="sxs-lookup"><span data-stu-id="a4239-152">When the Verbose cmdlet is included, Test-CsVoiceUser will issue a detailed account of all the steps in takes when conducting its checks.</span></span> <span data-ttu-id="a4239-153">Par exemple, vous pouvez voir des étapes similaires à celles-ci :</span><span class="sxs-lookup"><span data-stu-id="a4239-153">For example, you might see steps similar to these:</span></span> 

<span data-ttu-id="a4239-154">VERBOSe : localisation de l’utilisateur avec l’identité « sip :kenmyer@litwareinc.com »</span><span class="sxs-lookup"><span data-stu-id="a4239-154">VERBOSE: Locating user with identity "sip:kenmyer@litwareinc.com"</span></span>

<span data-ttu-id="a4239-155">VERBOSe : chargement du plan de numérotation : « RedmondDialPlan »</span><span class="sxs-lookup"><span data-stu-id="a4239-155">VERBOSE: Loading dial plan: "RedmondDialPlan"</span></span>

<span data-ttu-id="a4239-156">Ces informations supplémentaires peuvent fournir des indications sur les étapes à suivre pour identifier la cause de l’échec.</span><span class="sxs-lookup"><span data-stu-id="a4239-156">This additional information can provide hints as to the steps that you can take to pinpoint the cause of the failure.</span></span> <span data-ttu-id="a4239-157">Par exemple, la sortie détaillée indiquée ici nous indique que le plan de numérotation est affecté à l’utilisateur testé RedmondDialPlan.</span><span class="sxs-lookup"><span data-stu-id="a4239-157">For example, the verbose output shown here tells us that the user being tested was assigned the dial plan RedmondDialPlan.</span></span> <span data-ttu-id="a4239-158">Si le test a échoué, une étape suivante logique consiste à vérifier que RedmondDialPlan peut traduire le numéro de téléphone fourni.</span><span class="sxs-lookup"><span data-stu-id="a4239-158">If the test has failed, one logical next step would be to verify that RedmondDialPlan can translate the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a4239-159">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a4239-159">See Also</span></span>


[<span data-ttu-id="a4239-160">Test-CsVoiceUser</span><span class="sxs-lookup"><span data-stu-id="a4239-160">Test-CsVoiceUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

