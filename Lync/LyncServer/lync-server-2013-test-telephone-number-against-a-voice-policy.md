---
title: 'Lync Server 2013 : test du numéro de téléphone par rapport à une stratégie de voix'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d22c801c7d08c3df663f69df07a6c73a5f17f858
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a><span data-ttu-id="47316-102">Tester le numéro de téléphone par rapport à une stratégie de voix dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47316-102">Test telephone number against a voice policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47316-103">_**Dernière modification de la rubrique :** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="47316-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47316-104">Planification de la vérification</span><span class="sxs-lookup"><span data-stu-id="47316-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="47316-105">Tous les mois</span><span class="sxs-lookup"><span data-stu-id="47316-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47316-106">Outil de test</span><span class="sxs-lookup"><span data-stu-id="47316-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="47316-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="47316-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47316-108">Autorisations requises</span><span class="sxs-lookup"><span data-stu-id="47316-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="47316-109">Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="47316-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="47316-110">Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="47316-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="47316-111">Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="47316-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="47316-112">Description</span><span class="sxs-lookup"><span data-stu-id="47316-112">Description</span></span>

<span data-ttu-id="47316-113">Possibilité pour les utilisateurs de voix entreprise d’effectuer des appels téléphoniques sortants sur les charnières de réseau téléphonique commuté (PSTN), en grande partie, sur trois points :</span><span class="sxs-lookup"><span data-stu-id="47316-113">The ability of Enterprise Voice users to make outgoing phone calls over the Public Switched Telephone network (PSTN) hinges, in large part, on three things:</span></span>

  - <span data-ttu-id="47316-114">Stratégie de voix attribuée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="47316-114">The voice policy assigned to the user.</span></span>

  - <span data-ttu-id="47316-115">Itinéraires des communications vocales utilisés pour acheminer les appels depuis Lync Server vers le réseau RTC.</span><span class="sxs-lookup"><span data-stu-id="47316-115">The voice routes used to route calls from Lync Server to the PSTN network.</span></span>

  - <span data-ttu-id="47316-116">L’utilisation RTC, une propriété Lync Server qui connecte une stratégie de voix à un itinéraire de communications vocales.</span><span class="sxs-lookup"><span data-stu-id="47316-116">The PSTN usage, a Lync Server property that connects a voice policy to a voice route.</span></span>

<span data-ttu-id="47316-117">L’utilisation RTC est particulièrement importante : il s’agit de la propriété qui connecte une stratégie de voix à un itinéraire de communications vocales.</span><span class="sxs-lookup"><span data-stu-id="47316-117">The PSTN usage is especially important: it’s the property that connects a voice policy to a voice route.</span></span> <span data-ttu-id="47316-118">(Une stratégie de voix et un itinéraire de communications vocales sont appelés connectés s’ils disposent d’au moins une utilisation RTC en commun.) Les stratégies de voix peuvent être configurées sans spécifier d’utilisation PSTN.</span><span class="sxs-lookup"><span data-stu-id="47316-118">(A voice policy and a voice route are said to be connected if they have at least one PSTN usage in common.) Voice policies can be configured without specifying a PSTN usage.</span></span> <span data-ttu-id="47316-119">Dans ce cas, les utilisateurs auxquels cette stratégie a été attribuée ne peuvent pas effectuer d’appels sortants sur le réseau RTC.</span><span class="sxs-lookup"><span data-stu-id="47316-119">In that case, users who were assigned that policy won't be able to make outgoing calls over the PSTN network.</span></span> <span data-ttu-id="47316-120">De même, les itinéraires de communications vocales qui n’ont pas au moins une utilisation PSTN spécifiée ne pourront pas acheminer les appels vers le réseau RTC.</span><span class="sxs-lookup"><span data-stu-id="47316-120">Likewise, voice routes that do not have at least one specified PSTN usage will be unable to route calls to the PSTN network.</span></span>

<span data-ttu-id="47316-121">L’applet de commande test-CsVoicePolicy vérifie qu’une stratégie de voix donnée a une utilisation PSTN et que l’utilisation est partagée par au moins un itinéraire de communications vocales.</span><span class="sxs-lookup"><span data-stu-id="47316-121">The Test-CsVoicePolicy cmdlet verifies that a given voice policy has a PSTN usage and that the usage is shared by at least one voice route.</span></span> <span data-ttu-id="47316-122">Si la vérification exécutée par test-CsVoicePolicy réussit, l’applet de commande affiche le nom du premier itinéraire de communications vocales valide, ainsi que le nom de l’utilisation PSTN qui connecte la stratégie à l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="47316-122">If the verification run by Test-CsVoicePolicy succeeds, the cmdlet will report back the name of the first valid voice route it finds, and also the name of the PSTN usage that connects the policy to the route.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="47316-123">Exécution du test</span><span class="sxs-lookup"><span data-stu-id="47316-123">Running the test</span></span>

<span data-ttu-id="47316-124">Pour exécuter la cmdlet Test-CsVoicePolicy, vous devez d’abord utiliser l’applet de commande Get-CsVoicePolicy pour récupérer une instance de la stratégie de voix à tester ; cette instance doit ensuite être redirigée vers test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="47316-124">To run the Test-CsVoicePolicy cmdlet you must first use the Get-CsVoicePolicy cmdlet retrieve an instance of the voice policy to be tested; that instance must then be piped to Test-CsVoicePolicy.</span></span> <span data-ttu-id="47316-125">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="47316-125">For example:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="47316-126">Notez que cette commande, qui n’utilise pas Get-CsVoicePolicy pour récupérer une instance de stratégie de voix, échoue :</span><span class="sxs-lookup"><span data-stu-id="47316-126">Note that this command, which does not use Get-CsVoicePolicy to retrieve a voice policy instance, will fail:</span></span>

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

<span data-ttu-id="47316-127">Si vous souhaitez vérifier toutes les stratégies de voix sur un numéro de téléphone spécifié, utilisez une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="47316-127">If you want to check all the voice policies against a specified phone number then use a command similar to this:</span></span>

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

<span data-ttu-id="47316-128">Notez que le TargetNumber doit être spécifié à l’aide du format E. 164.</span><span class="sxs-lookup"><span data-stu-id="47316-128">Note that the TargetNumber must be specified by using the E.164 format.</span></span> <span data-ttu-id="47316-129">Test-CsVoicePolicy n’essaiera pas de normaliser ou de traduire les numéros de téléphone au format E. 164.</span><span class="sxs-lookup"><span data-stu-id="47316-129">Test-CsVoicePolicy won't attempt to normalize or translate phone numbers into the E.164 format.</span></span>

<span data-ttu-id="47316-130">Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande test-CsVoicePolicy.</span><span class="sxs-lookup"><span data-stu-id="47316-130">For more information, see the Help documentation for the Test-CsVoicePolicy cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="47316-131">Détermination de la réussite ou de l’échec</span><span class="sxs-lookup"><span data-stu-id="47316-131">Determining success or failure</span></span>

<span data-ttu-id="47316-132">Si la stratégie de voix peut trouver un itinéraire de communications vocales correspondant et une utilisation PSTN correspondante, l’itinéraire et l’utilisation seront affichés à l’écran :</span><span class="sxs-lookup"><span data-stu-id="47316-132">If the voice policy can find both a matching voice route and a matching PSTN usage, then both the route and the usage will be displayed on-screen:</span></span>

<span data-ttu-id="47316-133">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="47316-133">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="47316-134">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="47316-134">\------------------ -------------</span></span>

<span data-ttu-id="47316-135">RedmondVoiceRoute RedmondPstnUsage</span><span class="sxs-lookup"><span data-stu-id="47316-135">RedmondVoiceRoute RedmondPstnUsage</span></span>

<span data-ttu-id="47316-136">Si un itinéraire de communications vocales approprié ou une utilisation PSTN appropriée est introuvable, les valeurs de propriétés vides s’affichent à l’écran :</span><span class="sxs-lookup"><span data-stu-id="47316-136">If either an appropriate voice route or an appropriate PSTN usage cannot be found then blank property values will be displayed on-screen:</span></span>

<span data-ttu-id="47316-137">FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="47316-137">FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="47316-138">\------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="47316-138">\------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="47316-139">Raisons pour lesquelles le test a pu échouer</span><span class="sxs-lookup"><span data-stu-id="47316-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="47316-140">Si test-CsVoicePolicy ne renvoie pas de correspondance, cela signifie que la stratégie de voix ne partage pas une utilisation PSTN avec un itinéraire de communications vocales.</span><span class="sxs-lookup"><span data-stu-id="47316-140">If Test-CsVoicePolicy does not return a match that could mean that the voice policy does not share a PSTN usage with a voice route.</span></span> <span data-ttu-id="47316-141">Pour vérifier que, utilisez une cmdlet semblable à la suivante pour vérifier que les utilisations PSTN affectées à la stratégie de voix :</span><span class="sxs-lookup"><span data-stu-id="47316-141">To verify that, use a cmdlet similar to the following to verify that PSTN usages assigned to the voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

<span data-ttu-id="47316-142">Ensuite, exécutez la commande suivante pour déterminer les utilisations RTC attribuées à chacun de vos itinéraires vocaux :</span><span class="sxs-lookup"><span data-stu-id="47316-142">Next, run this command to determine the PSTN usages assign to each of your voice routes:</span></span>

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

<span data-ttu-id="47316-143">Si vous voyez des correspondances (c’est-à-dire, si vous voyez un ou plusieurs itinéraires vocaux qui partagent au moins une utilisation PSTN avec votre stratégie de voix), vous devez ensuite exécuter l’applet de commande test-CsVoiceRoute pour vérifier que l’itinéraire des communications vocales peut composer le numéro de téléphone fourni.</span><span class="sxs-lookup"><span data-stu-id="47316-143">If you see any matches (that is, if you see one or more voice routes that share at least one PSTN usage with your voice policy), you should then run the Test-CsVoiceRoute cmdlet to verify that the voice route can dial the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="47316-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="47316-144">See Also</span></span>


[<span data-ttu-id="47316-145">Test-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="47316-145">Test-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

