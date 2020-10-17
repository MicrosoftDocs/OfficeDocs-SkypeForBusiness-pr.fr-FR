---
title: 'Lync Server 2013 : test du plan de numérotation'
description: 'Lync Server 2013 : test du plan de numérotation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ef2e3fce9d1fbbb0186b1b7aef608834145d3e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556170"
---
# <a name="testing-the-dial-plan-in-lync-server-2013"></a><span data-ttu-id="976e2-103">Test du plan de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="976e2-103">Testing the dial plan in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="976e2-104">_**Dernière modification de la rubrique :** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="976e2-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="976e2-105">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="976e2-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="976e2-106">Journalière</span><span class="sxs-lookup"><span data-stu-id="976e2-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="976e2-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="976e2-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="976e2-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="976e2-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="976e2-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="976e2-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="976e2-110">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="976e2-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="976e2-111">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsDialPlan.</span><span class="sxs-lookup"><span data-stu-id="976e2-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialPlan cmdlet.</span></span> <span data-ttu-id="976e2-112">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="976e2-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="976e2-113">Description</span><span class="sxs-lookup"><span data-stu-id="976e2-113">Description</span></span>

<span data-ttu-id="976e2-114">L’applet de commande Test-CsDialPlan vous permet d’afficher les résultats de l’application d’un plan de numérotation à un numéro de téléphone donné.</span><span class="sxs-lookup"><span data-stu-id="976e2-114">The Test-CsDialPlan cmdlet enables you to see the results of applying a dial plan to a given telephone number.</span></span> <span data-ttu-id="976e2-115">Les plans de numérotation fournissent des informations, telles que la manière dont les règles de normalisation sont appliquées, requises pour permettre aux utilisateurs de voix entreprise d’effectuer des appels téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="976e2-115">Dial plans provide information, such as how normalization rules are applied, required to enable Enterprise Voice users to make telephone calls.</span></span> <span data-ttu-id="976e2-116">Dotée d’un numéro composé et d’un plan de numérotation, cette applet de commande vérifiera la règle de normalisation qui sera appliquée au sein du plan de numérotation et quel sera le numéro traduit.</span><span class="sxs-lookup"><span data-stu-id="976e2-116">Given a dialed number and a dial plan, this cmdlet will verify which normalization rule within the dial plan will be applied and what the translated number will be.</span></span>

<span data-ttu-id="976e2-117">Vous pouvez utiliser cette applet de commande pour résoudre les problèmes liés aux traductions de numéros ou pour vérifier comment appliquer des règles à certains numéros.</span><span class="sxs-lookup"><span data-stu-id="976e2-117">You can use this cmdlet for troubleshooting issues with number translations, or for verifying how to apply rules against certain numbers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="976e2-118">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="976e2-118">Running the test</span></span>

<span data-ttu-id="976e2-119">L’applet de commande Test-CsDialPlan vous oblige à effectuer deux opérations.</span><span class="sxs-lookup"><span data-stu-id="976e2-119">The Test-CsDialPlan cmdlet requires you to do two things.</span></span> <span data-ttu-id="976e2-120">Tout d’abord, vous devez obtenir une instance du plan de numérotation testé ; Cela peut être réalisé à l’aide de l’applet de commande Get-CsDialPlan.</span><span class="sxs-lookup"><span data-stu-id="976e2-120">First, you must obtain an instance of the dial plan being tested; that can be done by using the Get-CsDialPlan cmdlet.</span></span> <span data-ttu-id="976e2-121">Deuxièmement, vous devez spécifier le numéro de téléphone qui doit être normalisé.</span><span class="sxs-lookup"><span data-stu-id="976e2-121">Second, you must specify the phone number that has to be normalized.</span></span> <span data-ttu-id="976e2-122">Le format utilisé pour le numéro de téléphone doit correspondre au numéro composé par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="976e2-122">The format that is used for the phone number should match the number as dialed/entered by a user.</span></span> <span data-ttu-id="976e2-123">Par exemple, cette commande extrait une instance du plan de numérotation, RedmondDialPlan, et vérifie si le numéro de téléphone 12065551219 peut être normalisé :</span><span class="sxs-lookup"><span data-stu-id="976e2-123">For example, this command retrieves an instance of the dial plan, RedmondDialPlan, and checks whether the phone number 12065551219 can be normalized:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

<span data-ttu-id="976e2-124">Si vous disposez d’une règle de normalisation qui ajoute automatiquement le code du pays (dans cet exemple, 1) et l’indicatif régional (206), vous pouvez vérifier le numéro de téléphone 5551219, comme suit :</span><span class="sxs-lookup"><span data-stu-id="976e2-124">If you have a normalization rule that automatically adds the country code (in this example, 1) and the area code (206), then you might want to check the phone number 5551219, as follows:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

<span data-ttu-id="976e2-125">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) .</span><span class="sxs-lookup"><span data-stu-id="976e2-125">For more information, see the Help documentation for the [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="976e2-126">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="976e2-126">Determining success or failure</span></span>

<span data-ttu-id="976e2-127">Test-CsDialPlan diffère de la plupart des cmdlets de test Lync Server car il indique uniquement indirectement si un test a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="976e2-127">Test-CsDialPlan differs from many of the Lync Server test cmdlets because it only indirectly indicates whether a test succeeded or failed.</span></span> <span data-ttu-id="976e2-128">Lors de l’utilisation de Test-CsDialPlan vous ne recevez pas de sortie similaire à celle-ci avec le résultat clairement étiqueté :</span><span class="sxs-lookup"><span data-stu-id="976e2-128">When using Test-CsDialPlan you do not receive back output similar to this with the Result clearly labeled:</span></span>

<span data-ttu-id="976e2-129">TargetFqdn : atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="976e2-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="976e2-130">Résultat : opération réussie</span><span class="sxs-lookup"><span data-stu-id="976e2-130">Result : Success</span></span>

<span data-ttu-id="976e2-131">Latence : 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="976e2-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="976e2-132">«</span><span class="sxs-lookup"><span data-stu-id="976e2-132">Error :</span></span>

<span data-ttu-id="976e2-133">Diagnostique</span><span class="sxs-lookup"><span data-stu-id="976e2-133">Diagnosis :</span></span>

<span data-ttu-id="976e2-134">Au lieu de cela, si Test-CsDialPlan réussit, vous recevrez des informations sur la règle de normalisation qui a réussi à traduire et à utiliser le numéro de téléphone spécifié :</span><span class="sxs-lookup"><span data-stu-id="976e2-134">Instead, if Test-CsDialPlan succeeds, then you'll receive information about the normalization rule that was able to successfully translate and use the specified phone number:</span></span>

<span data-ttu-id="976e2-135">TranslatedNumber : + 12065551219</span><span class="sxs-lookup"><span data-stu-id="976e2-135">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="976e2-136">MatchingRule : description =; Modèle = ^ ( \\ d (11)) $; Translation = + $1 ;</span><span class="sxs-lookup"><span data-stu-id="976e2-136">MatchingRule : Description=;Pattern=^(\\d(11))$;Translation=+$1;</span></span>

<span data-ttu-id="976e2-137">Nom = préfixe tout ; IsInternalExtension = false</span><span class="sxs-lookup"><span data-stu-id="976e2-137">Name=Prefix All; IsInternalExtension=False</span></span>

<span data-ttu-id="976e2-138">Si Test-CsDialPlan échoue (c’est-à-dire, si le plan de numérotation ne dispose pas d’une règle de normalisation qui peut traduire le numéro de téléphone spécifié), vous recevrez simplement la sortie « vide » comme suit :</span><span class="sxs-lookup"><span data-stu-id="976e2-138">If Test-CsDialPlan fails (that is, if the dial plan does not have a normalization rule that can translate the specified phone number), you'll just receive “empty” output as follows:</span></span>

<span data-ttu-id="976e2-139">TranslatedNumber :</span><span class="sxs-lookup"><span data-stu-id="976e2-139">TranslatedNumber :</span></span>

<span data-ttu-id="976e2-140">MatchingRule :</span><span class="sxs-lookup"><span data-stu-id="976e2-140">MatchingRule :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="976e2-141">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="976e2-141">Reasons why the test might have failed</span></span>

<span data-ttu-id="976e2-142">Voici quelques raisons courantes pour lesquelles Test-CsDialPlan peut échouer :</span><span class="sxs-lookup"><span data-stu-id="976e2-142">Here are some common reasons why Test-CsDialPlan might fail:</span></span>

  - <span data-ttu-id="976e2-143">Vous avez peut-être utilisé un format incorrect lors de la spécification du numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="976e2-143">You might have used an incorrect format when specifying the phone number.</span></span> <span data-ttu-id="976e2-144">Les plans de numérotation incluent des règles de normalisation qui permettent à Lync Server de traduire les numéros de téléphone composés ou entrés par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="976e2-144">Dial plans include normalization rules that enable Lync Server to translate the phone numbers dialed or entered by a user.</span></span> <span data-ttu-id="976e2-145">Par conséquent, votre plan de numérotation doit avoir des règles de normalisation qui correspondent aux numéros susceptibles d’être composés par les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="976e2-145">Therefore, your dial plan should have normalization rules that match the numbers users are likely to dial.</span></span> <span data-ttu-id="976e2-146">Par exemple, si les utilisateurs peuvent composer le code du pays, l’indicatif régional, puis le numéro de téléphone lui-même, cela signifie que votre plan de numérotation doit disposer d’une règle de normalisation pour gérer les numéros de téléphone comme ceci :</span><span class="sxs-lookup"><span data-stu-id="976e2-146">For example, if users might dial the country code, area code, and then the phone number itself, that means that your dial plan should have a normalization rule to handle phone numbers such as this:</span></span>
    
    <span data-ttu-id="976e2-147">12065551219</span><span class="sxs-lookup"><span data-stu-id="976e2-147">12065551219</span></span>
    
    <span data-ttu-id="976e2-148">Toutefois, si vous entrez un numéro de téléphone incorrect (par exemple, en ne laissant pas le chiffre final), Test-CsDialPlan échouera.</span><span class="sxs-lookup"><span data-stu-id="976e2-148">However, if you enter an incorrect phone number (for example, leaving off the final digit), then Test-CsDialPlan will fail.</span></span> <span data-ttu-id="976e2-149">Cela n’est pas dû au fait que le plan de numérotation est défectueux mais parce que vous avez entré un numéro de téléphone qui ne peut pas être interprété.</span><span class="sxs-lookup"><span data-stu-id="976e2-149">That’s not because the dial plan is faulty but because you have entered a phone number than can’t be interpreted.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

