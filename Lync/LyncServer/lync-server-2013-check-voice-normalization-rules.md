---
title: 'Lync Server 2013 : vérifier les règles de normalisation vocale'
description: 'Lync Server 2013 : Vérifiez les règles de normalisation vocale.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f68bbde24a3dc7d8e8214dcfe506d4b8112fbbb3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543530"
---
# <a name="check-voice-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="b5df6-103">Vérifier les règles de normalisation vocale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5df6-103">Check voice normalization rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5df6-104">_**Dernière modification de la rubrique :** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="b5df6-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5df6-105">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="b5df6-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b5df6-106">Mensuelle</span><span class="sxs-lookup"><span data-stu-id="b5df6-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5df6-107">Outil de test</span><span class="sxs-lookup"><span data-stu-id="b5df6-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b5df6-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5df6-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5df6-109">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="b5df6-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b5df6-110">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b5df6-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b5df6-111">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui sont autorisés à exécuter l’applet de commande Test-CsVoiceNormalizationRule.</span><span class="sxs-lookup"><span data-stu-id="b5df6-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceNormalizationRule cmdlet.</span></span> <span data-ttu-id="b5df6-112">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="b5df6-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b5df6-113">Description</span><span class="sxs-lookup"><span data-stu-id="b5df6-113">Description</span></span>

<span data-ttu-id="b5df6-114">Les règles de normalisation vocale sont utilisées pour convertir un numéro de téléphone composé par un utilisateur (par exemple, 2065551219) au format E. 164 utilisé par Lync Server (+ 12065551219).</span><span class="sxs-lookup"><span data-stu-id="b5df6-114">Voice normalization rules are used to convert a phone number dialed by a user (for example, 2065551219) to the E.164 format that is used by Lync Server (+12065551219).</span></span> <span data-ttu-id="b5df6-115">Par exemple, si les utilisateurs sont à l’habitude de composer un numéro de téléphone sans inclure le code du pays ou l’indicatif régional (par exemple, 5551219), vous devez disposer d’une règle de normalisation vocale pouvant convertir ce numéro au format E. 164 : + 12065551219.</span><span class="sxs-lookup"><span data-stu-id="b5df6-115">For example, if users are in the habit of dialing a phone number without including the country code or the area code (e.g., 5551219) then you must have a voice normalization rule that can convert that number to the E.164 format: +12065551219.</span></span> <span data-ttu-id="b5df6-116">Sans cette règle, l’utilisateur ne peut pas appeler 555-1219.</span><span class="sxs-lookup"><span data-stu-id="b5df6-116">Without such a rule, the user won't be able to call 555-1219.</span></span>

<span data-ttu-id="b5df6-117">L’applet de commande Test-CsVoiceNormalizationRule vérifie qu’une règle de normalisation vocale spécifiée peut convertir un numéro de téléphone spécifié.</span><span class="sxs-lookup"><span data-stu-id="b5df6-117">The Test-CsVoiceNormalizationRule cmdlet verifies that a specified voice normalization rule can successfully convert a specified phone number.</span></span> <span data-ttu-id="b5df6-118">Par exemple, cette commande vérifie si la règle de normalisation NoAreaCode peut normaliser et convertir la chaîne de numérotation 5551219.</span><span class="sxs-lookup"><span data-stu-id="b5df6-118">For example, this command checks whether the global normalization rule NoAreaCode can normalize and convert the dial string 5551219.</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b5df6-119">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="b5df6-119">Running the test</span></span>

<span data-ttu-id="b5df6-120">Pour exécuter l’applet de commande Test-CsVoiceNormalizationRule, vous devez d’abord utiliser la cmdlet Get-CsVoiceNormalizationRule pour récupérer une instance de la règle testée, puis canaliser cette instance à test-CsVoiceNormalizationRule.</span><span class="sxs-lookup"><span data-stu-id="b5df6-120">To run the Test-CsVoiceNormalizationRule cmdlet, you must first use the Get-CsVoiceNormalizationRule cmdlet to retrieve an instance of the rule being tested, and then pipe that instance to Test-CsVoiceNormalizationRule.</span></span> <span data-ttu-id="b5df6-121">Une syntaxe similaire à celle-ci ne fonctionnera pas :</span><span class="sxs-lookup"><span data-stu-id="b5df6-121">Syntax similar to this won't work:</span></span>

<span data-ttu-id="b5df6-122">Test-CsVoiceNormalizationRule-DialedNumber "12065551219" – NormalizationRule "Global/prefix All"</span><span class="sxs-lookup"><span data-stu-id="b5df6-122">Test-CsVoiceNormalizationRule -DialedNumber "12065551219" –NormalizationRule "global/Prefix All"</span></span>

<span data-ttu-id="b5df6-123">À la place, utilisez une syntaxe telle que la suivante, qui combine les applets de commande Get-CsVoiceNormalizationRule et Test-CsVoiceNormalizationRule :</span><span class="sxs-lookup"><span data-stu-id="b5df6-123">Instead, use syntax such as the following, which combines both the Get-CsVoiceNormalizationRule and the Test-CsVoiceNormalizationRule cmdlets:</span></span>

<span data-ttu-id="b5df6-124">Get-CsVoiceNormalizationRule-Identity « global/prefix All » | Test-CsVoiceNormalizationRule-DialedNumber « 12065551219 »</span><span class="sxs-lookup"><span data-stu-id="b5df6-124">Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Test-CsVoiceNormalizationRule -DialedNumber "12065551219"</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b5df6-125">.</span><span class="sxs-lookup"><span data-stu-id="b5df6-125">.</span></span> <span data-ttu-id="b5df6-126">Vous pouvez également utiliser cette approche pour récupérer une instance d’une règle, puis la tester sur un numéro de téléphone spécifié :</span><span class="sxs-lookup"><span data-stu-id="b5df6-126">Or, you can also use this approach to retrieve an instance of a rule and then test that rule against a specified phone number:</span></span>



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

<span data-ttu-id="b5df6-127">Entrez la valeur du paramètre DialedNumber exactement comme vous prévoyez que ce numéro doit être composé.</span><span class="sxs-lookup"><span data-stu-id="b5df6-127">Enter the value for the DialedNumber parameter exactly as you expect that number to be dialed.</span></span> <span data-ttu-id="b5df6-128">Par exemple, si la règle de normalisation vocale spécifiée est censée ajouter automatiquement le code du pays (1 initiale dans la valeur 12065551219), vous devez laisser le code du pays :</span><span class="sxs-lookup"><span data-stu-id="b5df6-128">For example, if the specified voice normalization rule is supposed to automatically add the country code (the initial 1 in the value 12065551219) then you should leave off the country code:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="b5df6-129">Si la règle est configurée correctement, elle ajoute automatiquement le code du pays lors de la conversion du numéro au format E. 164 utilisé par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5df6-129">If the rule is configured correctly, it will automatically add the country code when translating the number to the E.164 format that is used by Lync Server.</span></span>

<span data-ttu-id="b5df6-130">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande Test-CsVoiceNormalizationRule.</span><span class="sxs-lookup"><span data-stu-id="b5df6-130">For more information, see the Help documentation for the Test-CsVoiceNormalizationRule cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b5df6-131">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="b5df6-131">Determining success or failure</span></span>

<span data-ttu-id="b5df6-132">Si la règle de normalisation vocale spécifiée peut traduire le numéro fourni, le numéro traduit s’affiche à l’écran :</span><span class="sxs-lookup"><span data-stu-id="b5df6-132">If the specified voice normalization rule can translate the supplied number then the translated number will be displayed on-screen:</span></span>

<span data-ttu-id="b5df6-133">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="b5df6-133">TranslatedNumber</span></span>

\----------------

<span data-ttu-id="b5df6-134">\+12065551219</span><span class="sxs-lookup"><span data-stu-id="b5df6-134">\+12065551219</span></span>

<span data-ttu-id="b5df6-135">Si le test échoue, un numéro traduit vide est renvoyé :</span><span class="sxs-lookup"><span data-stu-id="b5df6-135">If the test fails then a blank translated number will be returned:</span></span>

<span data-ttu-id="b5df6-136">TranslatedNumber</span><span class="sxs-lookup"><span data-stu-id="b5df6-136">TranslatedNumber</span></span>

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b5df6-137">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="b5df6-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="b5df6-138">Si le Test-CsVoiceNormalizationRule renvoie un numéro traduit, cela signifie que la règle de normalisation vocale spécifiée n’a pas pu convertir le numéro de téléphone fourni au format E. 164 utilisé par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5df6-138">If the Test-CsVoiceNormalizationRule does return a translated number that means that the specified voice normalization rule was unable to translate the supplied telephone number into the E.164 format that is used by Lync Server.</span></span> <span data-ttu-id="b5df6-139">Pour vérifier que vous avez correctement tapé le numéro de téléphone, vérifiez tout d’abord que vous avez tapé le numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="b5df6-139">To verify that, first make sure that you typed the telephone number in correctly.</span></span> <span data-ttu-id="b5df6-140">Par exemple, vous pouvez vous attendre à ce que votre règle de normalisation vocale ait des problèmes de traduction d’un numéro semblable à celui-ci :</span><span class="sxs-lookup"><span data-stu-id="b5df6-140">For example, you would expect your voice normalization rule to have problems translating a number similar to this:</span></span>

`-DialedNumber "1"`

<span data-ttu-id="b5df6-141">En supposant que le numéro a été saisi correctement, l’étape suivante consiste à vérifier que la règle de normalisation spécifiée est conçue pour gérer ce numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="b5df6-141">Assuming the number was entered correctly, your next step should be to verify that the specified normalization rule is designed to handle that phone number.</span></span> <span data-ttu-id="b5df6-142">Par exemple, une règle de normalisation peut être conçue pour gérer le format 12065551219, mais une deuxième règle peut être conçue pour gérer le numéro 2065551219.</span><span class="sxs-lookup"><span data-stu-id="b5df6-142">For example, one normalization rule might be designed to handle the format 12065551219, but a second rule might be designed to handle the number 2065551219.</span></span> <span data-ttu-id="b5df6-143">(Il s’agit du même numéro de téléphone, moins le code pays 1 au début.) Pour renvoyer des informations détaillées sur une règle de normalisation vocale, exécutez une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="b5df6-143">(That’s the same phone number, minus the country code 1 at the very beginning.) To return detailed information about a voice normalization rule, run a command similar to this:</span></span>

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

<span data-ttu-id="b5df6-144">Pour renvoyer des informations détaillées sur toutes les règles de normalisation vocale, exécutez cette commande à la place :</span><span class="sxs-lookup"><span data-stu-id="b5df6-144">To return detailed information about all the voice normalization rules, run this command instead:</span></span>

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b5df6-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b5df6-145">See Also</span></span>


[<span data-ttu-id="b5df6-146">Test-CsVoiceNormalizationRule</span><span class="sxs-lookup"><span data-stu-id="b5df6-146">Test-CsVoiceNormalizationRule</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

