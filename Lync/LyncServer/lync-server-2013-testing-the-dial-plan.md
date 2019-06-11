---
title: 'Lync Server 2013: test du plan de numérotation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2815248084e7591c11157cde3fb4851722315073
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a><span data-ttu-id="de5df-102">Test du plan de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de5df-102">Testing the dial plan in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de5df-103">_**Dernière modification de la rubrique:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="de5df-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de5df-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="de5df-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="de5df-105">Jour</span><span class="sxs-lookup"><span data-stu-id="de5df-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de5df-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="de5df-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="de5df-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="de5df-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de5df-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="de5df-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="de5df-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="de5df-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="de5df-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsDialPlan.</span><span class="sxs-lookup"><span data-stu-id="de5df-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsDialPlan cmdlet.</span></span> <span data-ttu-id="de5df-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="de5df-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="de5df-112">Description</span><span class="sxs-lookup"><span data-stu-id="de5df-112">Description</span></span>

<span data-ttu-id="de5df-113">L’applet de contrôle test-CsDialPlan vous permet d’afficher les résultats de l’application d’un plan de numérotation à un numéro de téléphone donné.</span><span class="sxs-lookup"><span data-stu-id="de5df-113">The Test-CsDialPlan cmdlet enables you to see the results of applying a dial plan to a given telephone number.</span></span> <span data-ttu-id="de5df-114">Les plans de numérotation fournissent des informations, telles que les règles de normalisation, requises pour permettre aux utilisateurs d’entreprise Voice d’effectuer des appels téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="de5df-114">Dial plans provide information, such as how normalization rules are applied, required to enable Enterprise Voice users to make telephone calls.</span></span> <span data-ttu-id="de5df-115">À partir d’un numéro composé et d’un plan de numérotation, cette applet de contrôle vérifie quelle règle de normalisation du plan de numérotation sera appliquée et quel sera le numéro traduit.</span><span class="sxs-lookup"><span data-stu-id="de5df-115">Given a dialed number and a dial plan, this cmdlet will verify which normalization rule within the dial plan will be applied and what the translated number will be.</span></span>

<span data-ttu-id="de5df-116">Vous pouvez utiliser cette cmdlet pour résoudre les problèmes liés aux traductions de nombres ou pour vérifier l’application de règles à certains numéros.</span><span class="sxs-lookup"><span data-stu-id="de5df-116">You can use this cmdlet for troubleshooting issues with number translations, or for verifying how to apply rules against certain numbers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="de5df-117">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="de5df-117">Running the test</span></span>

<span data-ttu-id="de5df-118">L’applet de contrôle test-CsDialPlan vous demande d’effectuer deux actions.</span><span class="sxs-lookup"><span data-stu-id="de5df-118">The Test-CsDialPlan cmdlet requires you to do two things.</span></span> <span data-ttu-id="de5df-119">Tout d’abord, vous devez obtenir une instance du plan de numérotation testé. pour ce faire, vous pouvez utiliser l’applet de passe Get-CsDialPlan.</span><span class="sxs-lookup"><span data-stu-id="de5df-119">First, you must obtain an instance of the dial plan being tested; that can be done by using the Get-CsDialPlan cmdlet.</span></span> <span data-ttu-id="de5df-120">Deuxièmement, vous devez spécifier le numéro de téléphone qui doit être normalisé.</span><span class="sxs-lookup"><span data-stu-id="de5df-120">Second, you must specify the phone number that has to be normalized.</span></span> <span data-ttu-id="de5df-121">Le format utilisé pour le numéro de téléphone doit correspondre au numéro composé par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="de5df-121">The format that is used for the phone number should match the number as dialed/entered by a user.</span></span> <span data-ttu-id="de5df-122">Par exemple, cette commande récupère une instance du plan de numérotation, RedmondDialPlan et vérifie si le numéro de téléphone 12065551219 peut être normalisé:</span><span class="sxs-lookup"><span data-stu-id="de5df-122">For example, this command retrieves an instance of the dial plan, RedmondDialPlan, and checks whether the phone number 12065551219 can be normalized:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

<span data-ttu-id="de5df-123">Si vous disposez d’une règle de normalisation qui ajoute automatiquement le code du pays (dans cet exemple, 1) et l’indicatif de la région (206), vous pouvez vérifier le numéro de téléphone 5551219 comme suit:</span><span class="sxs-lookup"><span data-stu-id="de5df-123">If you have a normalization rule that automatically adds the country code (in this example, 1) and the area code (206), then you might want to check the phone number 5551219, as follows:</span></span>

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

<span data-ttu-id="de5df-124">Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) .</span><span class="sxs-lookup"><span data-stu-id="de5df-124">For more information, see the Help documentation for the [Test-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="de5df-125">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="de5df-125">Determining success or failure</span></span>

<span data-ttu-id="de5df-126">Test-CsDialPlan est différent de la plupart des cmdlets de test du serveur Lync, car il n’indique qu’un test a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="de5df-126">Test-CsDialPlan differs from many of the Lync Server test cmdlets because it only indirectly indicates whether a test succeeded or failed.</span></span> <span data-ttu-id="de5df-127">Lors de l’utilisation de test-CsDialPlan, vous ne recevez pas de sortie semblable à celle-ci avec le résultat clairement libellé:</span><span class="sxs-lookup"><span data-stu-id="de5df-127">When using Test-CsDialPlan you do not receive back output similar to this with the Result clearly labeled:</span></span>

<span data-ttu-id="de5df-128">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="de5df-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="de5df-129">Résultat: réussite</span><span class="sxs-lookup"><span data-stu-id="de5df-129">Result : Success</span></span>

<span data-ttu-id="de5df-130">Latence: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="de5df-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="de5df-131">Error</span><span class="sxs-lookup"><span data-stu-id="de5df-131">Error :</span></span>

<span data-ttu-id="de5df-132">Diagnostic</span><span class="sxs-lookup"><span data-stu-id="de5df-132">Diagnosis :</span></span>

<span data-ttu-id="de5df-133">Si test-CsDialPlan réussit, vous recevez des informations sur la règle de normalisation qui a pu traduire et utiliser le numéro de téléphone spécifié.</span><span class="sxs-lookup"><span data-stu-id="de5df-133">Instead, if Test-CsDialPlan succeeds, then you'll receive information about the normalization rule that was able to successfully translate and use the specified phone number:</span></span>

<span data-ttu-id="de5df-134">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="de5df-134">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="de5df-135">MatchingRule: description =; Modèle = ^ (\\j (11)) $; Traduction = + $1;</span><span class="sxs-lookup"><span data-stu-id="de5df-135">MatchingRule : Description=;Pattern=^(\\d(11))$;Translation=+$1;</span></span>

<span data-ttu-id="de5df-136">Nom = tout préfixe; IsInternalExtension = false</span><span class="sxs-lookup"><span data-stu-id="de5df-136">Name=Prefix All; IsInternalExtension=False</span></span>

<span data-ttu-id="de5df-137">Si test-CsDialPlan échoue (autrement dit, si le plan de numérotation ne dispose pas d’une règle de normalisation qui peut traduire le numéro de téléphone spécifié), il vous suffit de recevoir la sortie «vider» comme suit:</span><span class="sxs-lookup"><span data-stu-id="de5df-137">If Test-CsDialPlan fails (that is, if the dial plan does not have a normalization rule that can translate the specified phone number), you'll just receive “empty” output as follows:</span></span>

<span data-ttu-id="de5df-138">TranslatedNumber :</span><span class="sxs-lookup"><span data-stu-id="de5df-138">TranslatedNumber :</span></span>

<span data-ttu-id="de5df-139">MatchingRule :</span><span class="sxs-lookup"><span data-stu-id="de5df-139">MatchingRule :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="de5df-140">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="de5df-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="de5df-141">Voici quelques raisons courantes pour lesquelles les tests-CsDialPlan peuvent échouer:</span><span class="sxs-lookup"><span data-stu-id="de5df-141">Here are some common reasons why Test-CsDialPlan might fail:</span></span>

  - <span data-ttu-id="de5df-142">Vous avez peut-être déjà utilisé un format incorrect lorsque vous spécifiez le numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="de5df-142">You might have used an incorrect format when specifying the phone number.</span></span> <span data-ttu-id="de5df-143">Les plans de numérotation incluent des règles de normalisation qui permettent à Lync Server de traduire les numéros de téléphone numérotés ou entrés par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="de5df-143">Dial plans include normalization rules that enable Lync Server to translate the phone numbers dialed or entered by a user.</span></span> <span data-ttu-id="de5df-144">Par conséquent, votre plan de numérotation doit être doté de règles de normalisation correspondant aux numéros que les utilisateurs peuvent composer.</span><span class="sxs-lookup"><span data-stu-id="de5df-144">Therefore, your dial plan should have normalization rules that match the numbers users are likely to dial.</span></span> <span data-ttu-id="de5df-145">Par exemple, si les utilisateurs peuvent composer le code de pays, l’indicatif régional et le numéro de téléphone lui-même, cela signifie que votre plan de numérotation doit être doté d’une règle de normalisation pour gérer les numéros de téléphone comme suit:</span><span class="sxs-lookup"><span data-stu-id="de5df-145">For example, if users might dial the country code, area code, and then the phone number itself, that means that your dial plan should have a normalization rule to handle phone numbers such as this:</span></span>
    
    <span data-ttu-id="de5df-146">12065551219</span><span class="sxs-lookup"><span data-stu-id="de5df-146">12065551219</span></span>
    
    <span data-ttu-id="de5df-147">Toutefois, si vous entrez un numéro de téléphone incorrect (par exemple, en ne disquittant pas le dernier chiffre), test-CsDialPlan échoue.</span><span class="sxs-lookup"><span data-stu-id="de5df-147">However, if you enter an incorrect phone number (for example, leaving off the final digit), then Test-CsDialPlan will fail.</span></span> <span data-ttu-id="de5df-148">Ce n’est pas parce que le plan de numérotation est défectueux, car vous avez entré un numéro de téléphone qui ne peut pas être interprété.</span><span class="sxs-lookup"><span data-stu-id="de5df-148">That’s not because the dial plan is faulty but because you have entered a phone number than can’t be interpreted.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

