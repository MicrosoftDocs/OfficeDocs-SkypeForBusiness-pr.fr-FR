---
title: 'Lync Server 2013: vérifier la configuration de Trunk par rapport à un numéro de téléphone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b667f43e430b5047f72e2d8352f57337f0849055
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a><span data-ttu-id="a9a00-102">Vérifier la configuration de Trunk par rapport à un numéro de téléphone dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9a00-102">Check trunk configuration against a phone number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9a00-103">_**Dernière modification de la rubrique:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="a9a00-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9a00-104">Échéancier de vérification</span><span class="sxs-lookup"><span data-stu-id="a9a00-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a9a00-105">Mois</span><span class="sxs-lookup"><span data-stu-id="a9a00-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9a00-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="a9a00-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a9a00-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9a00-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9a00-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="a9a00-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a9a00-109">Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a9a00-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a9a00-110">Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="a9a00-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="a9a00-111">Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a9a00-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a9a00-112">Description</span><span class="sxs-lookup"><span data-stu-id="a9a00-112">Description</span></span>

<span data-ttu-id="a9a00-113">Les ISL SIP connectent le réseau d’entreprise voix interne de Lync Server à l’un des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="a9a00-113">SIP trunks connect the Lync Server internal Enterprise Voice network to any of the following:</span></span>

  - <span data-ttu-id="a9a00-114">Le réseau téléphonique public commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="a9a00-114">The Public Switched Telephone network (PSTN).</span></span>

  - <span data-ttu-id="a9a00-115">Un échange de succursale public IP (PBX).</span><span class="sxs-lookup"><span data-stu-id="a9a00-115">An IP-public branch exchange (PBX).</span></span>

  - <span data-ttu-id="a9a00-116">Contrôleur de bordure de session (SBC).</span><span class="sxs-lookup"><span data-stu-id="a9a00-116">A Session Border Controller (SBC).</span></span>

<span data-ttu-id="a9a00-117">L’applet de contrôle test-CsTrunkConfiguration vérifie qu’un numéro de téléphone (tel qu’un appel) peut être converti en réseau E. 164 et routé sur une ligne SIP spécifiée.</span><span class="sxs-lookup"><span data-stu-id="a9a00-117">The Test-CsTrunkConfiguration cmdlet verifies that a phone number (as dialed by a user) can be converted to the E.164 network and routed over a specified SIP trunk.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a9a00-118">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="a9a00-118">Running the test</span></span>

<span data-ttu-id="a9a00-119">Pour exécuter l’applet de contrôle test-CsTrunkConfiguration, vous devez d’abord utiliser l’applet de contrôle Get-CsTrunkConfiguration pour récupérer une instance de vos paramètres de configuration de Trunk SIP. cette instance est alors canalisée vers test-CsTrunkConfiguration:</span><span class="sxs-lookup"><span data-stu-id="a9a00-119">To run the Test-CsTrunkConfiguration cmdlet you must first use the Get-CsTrunkConfiguration cmdlet to retrieve an instance of your SIP trunk configuration settings; that instance is then piped to Test-CsTrunkConfiguration:</span></span>

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="a9a00-120">L’exécution de test-CsTrunkConfiguration sans avoir d’abord exécuté Get-CsTrunkConfiguration ne fonctionne pas.</span><span class="sxs-lookup"><span data-stu-id="a9a00-120">Running Test-CsTrunkConfiguration without first running Get-CsTrunkConfiguration won't work.</span></span> <span data-ttu-id="a9a00-121">Par exemple, cette commande échoue sans renvoyer de données:</span><span class="sxs-lookup"><span data-stu-id="a9a00-121">For example, this command will fail without returning any data:</span></span>

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

<span data-ttu-id="a9a00-122">Si vous avez plusieurs collections de paramètres de configuration de Trunk SIP, vous pouvez utiliser une commande similaire à celle qui suit pour tester chaque collection sur le même numéro de téléphone:</span><span class="sxs-lookup"><span data-stu-id="a9a00-122">If you have multiple collections of SIP trunk configuration settings, you can use a command similar to the following to at the same time test each collection against the same phone number:</span></span>

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="a9a00-123">Pour plus d’informations, consultez la documentation d’aide de l’applet de contrôle test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="a9a00-123">For more information, see the Help documentation for the Test-CsTrunkConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a9a00-124">Détermination du succès ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="a9a00-124">Determining success or failure</span></span>

<span data-ttu-id="a9a00-125">Si test-CsTrunkConfiguration peut émettre un appel vers le numéro composé, le numéro de téléphone traduit (au format E. 164) et la règle utilisée pour traduire ce numéro de téléphone s’affichent à l’écran.</span><span class="sxs-lookup"><span data-stu-id="a9a00-125">If Test-CsTrunkConfiguration can place a call to the dialed number then the translated phone number (in the E.164 format) and the rule used to translate that phone number will both be displayed on screen:</span></span>

<span data-ttu-id="a9a00-126">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="a9a00-126">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="a9a00-127">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="a9a00-127"></span></span>

<span data-ttu-id="a9a00-128">\+12065551219 global/Redmond</span><span class="sxs-lookup"><span data-stu-id="a9a00-128">\+12065551219 Global/Redmond</span></span>

<span data-ttu-id="a9a00-129">Si le test échoue, test-CsTrunkConfiguration renvoie les valeurs de propriété vides:</span><span class="sxs-lookup"><span data-stu-id="a9a00-129">If the test fails, Test-CsTrunkConfiguration will return empty property values:</span></span>

<span data-ttu-id="a9a00-130">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="a9a00-130">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="a9a00-131">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="a9a00-131"></span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a9a00-132">Raisons pour lesquelles le test peut avoir échoué</span><span class="sxs-lookup"><span data-stu-id="a9a00-132">Reasons why the test might have failed</span></span>

<span data-ttu-id="a9a00-133">Si test-CsTrunkConfiguration ne renvoie aucune correspondance qui signifie généralement que les paramètres de configuration de Trunk en cours de test ne disposent pas d’une règle de traduction de numéro de téléphone prenant en charge la conversion du numéro numéroté au format E. 164.</span><span class="sxs-lookup"><span data-stu-id="a9a00-133">If Test-CsTrunkConfiguration does not return a match that typically means that the trunk configuration settings being test do not have an outgoing calling number translation rule capable to converting the dialed number to the E.164 format.</span></span> <span data-ttu-id="a9a00-134">Pour récupérer les règles de traduction affectées à un ensemble de paramètres de configuration de Trunk, vous pouvez utiliser une syntaxe similaire à celle-ci:</span><span class="sxs-lookup"><span data-stu-id="a9a00-134">To retrieve the translation rules assigned to a collection of trunk configuration settings, you can use syntax similar to this:</span></span>

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

<span data-ttu-id="a9a00-135">Cela renvoie des informations similaires à ce qui suit pour chaque règle de traduction:</span><span class="sxs-lookup"><span data-stu-id="a9a00-135">That returns information similar to this for each translation rule:</span></span>

<span data-ttu-id="a9a00-136">Description: numéros de téléphone sans code de pays ou indicatif régional.</span><span class="sxs-lookup"><span data-stu-id="a9a00-136">Description : Phone numbers without a country code or area code.</span></span>

<span data-ttu-id="a9a00-137">Modèle: ^\\+ (\\d\*) $</span><span class="sxs-lookup"><span data-stu-id="a9a00-137">Pattern : ^\\+(\\d\*)$</span></span>

`Translation : $1`

<span data-ttu-id="a9a00-138">Nom: NoAreaCode</span><span class="sxs-lookup"><span data-stu-id="a9a00-138">Name : NoAreaCode</span></span>

<span data-ttu-id="a9a00-139">À ce stade, vous vérifiez la valeur de la propriété Pattern (qui est une chaîne d' [expression régulière](http://go.microsoft.com/fwlink/?linkid=400464) ) pour vérifier si une des règles de traduction est configurée pour gérer le numéro numéroté.</span><span class="sxs-lookup"><span data-stu-id="a9a00-139">At that point, you check the value of the Pattern property (which is a [regular expression](http://go.microsoft.com/fwlink/?linkid=400464) string) to see whether any of the translation rules are configured to handle the dialed number.</span></span> <span data-ttu-id="a9a00-140">Si ce n’est pas le cas, vous devrez modifier une des règles existantes (Set-CsOutboundTranslationRule) ou utiliser l’applet de nouvelle applet de nouveau-CsOutboundTranslationRule pour ajouter une nouvelle règle à la collection.</span><span class="sxs-lookup"><span data-stu-id="a9a00-140">If not, you'll either have to change one of the existing rules (Set-CsOutboundTranslationRule) or use the New-CsOutboundTranslationRule cmdlet to add a new rule to the collection.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a9a00-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a9a00-141">See Also</span></span>


[<span data-ttu-id="a9a00-142">Test-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="a9a00-142">Test-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

