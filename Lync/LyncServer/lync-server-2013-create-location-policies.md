---
title: 'Lync Server 2013: création de stratégies d’emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f420d3b634df79411bbc72cd4c029f9b5d97e19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-location-policies-in-lync-server-2013"></a><span data-ttu-id="b0541-102">Créer des stratégies d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0541-102">Create location policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0541-103">_**Dernière modification de la rubrique:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="b0541-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="b0541-104">Lync Server utilise une stratégie d’emplacement pour permettre aux clients Lync pour E9-1-1 lors de l’inscription du client.</span><span class="sxs-lookup"><span data-stu-id="b0541-104">Lync Server uses a location policy to enable Lync clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="b0541-105">Une stratégie d’emplacement contient les paramètres qui définissent les modalités de mise en œuvre du système E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="b0541-105">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span>

<span data-ttu-id="b0541-p102">Vous pouvez modifier la stratégie d’emplacement globale et créer des stratégies d’emplacement avec balise. Un client obtient une stratégie globale lorsqu’il ne se situe pas dans un sous-réseau auquel une stratégie d’emplacement est associée ou lorsque le client n’a pas été affecté directement à une stratégie d’emplacement. Les stratégies avec balise sont affectées aux sous-réseaux ou aux utilisateurs.  </span><span class="sxs-lookup"><span data-stu-id="b0541-p102">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span>

<span data-ttu-id="b0541-109">Pour créer une stratégie d’emplacement, vous devez utiliser un compte membre du groupe RTCUniversalServerAdmins, membre du rôle administratif CsVoiceAdministrator ou possédant des droits et des autorisations d’administrateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="b0541-109">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="b0541-110">Pour obtenir une description complète des stratégies d’emplacement, voir [définition de la stratégie d’emplacement pour Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="b0541-110">For a complete description of Location policies, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span> <span data-ttu-id="b0541-111">Dans cette procédure, les applets de commande utilisent une stratégie d’emplacement définie en utilisant les valeurs suivantes:</span><span class="sxs-lookup"><span data-stu-id="b0541-111">Cmdlets in this procedure use a location policy defined using the following values:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0541-112">Élément</span><span class="sxs-lookup"><span data-stu-id="b0541-112">Element</span></span></th>
<th><span data-ttu-id="b0541-113">Valeur</span><span class="sxs-lookup"><span data-stu-id="b0541-113">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0541-114">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="b0541-114">EnhancedEmergencyServicesEnabled</span></span></p></td>
<td><p><span data-ttu-id="b0541-115"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="b0541-115"><strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0541-116">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="b0541-116">LocationRequired</span></span></p></td>
<td><p><span data-ttu-id="b0541-117"><strong>Clause d’exclusion</strong></span><span class="sxs-lookup"><span data-stu-id="b0541-117"><strong>Disclaimer</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0541-118">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="b0541-118">EnhancedEmergencyServiceDisclaimer</span></span></p></td>
<td><p><span data-ttu-id="b0541-p104">La stratégie de votre société exige que vous définissiez un emplacement. Si vous ne le faites pas, les services d’urgence ne pourront pas vous localiser en cas d’urgence. Définissez un emplacement.</span><span class="sxs-lookup"><span data-stu-id="b0541-p104">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0541-122">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="b0541-122">UseLocationForE911Only</span></span></p></td>
<td><p><span data-ttu-id="b0541-123"><strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="b0541-123"><strong>False</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0541-124">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="b0541-124">PstnUsage</span></span></p></td>
<td><p><span data-ttu-id="b0541-125"><strong>EmergencyUsage</strong></span><span class="sxs-lookup"><span data-stu-id="b0541-125"><strong>EmergencyUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0541-126">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="b0541-126">EmergencyDialString</span></span></p></td>
<td><p><span data-ttu-id="b0541-127"><strong>911</strong></span><span class="sxs-lookup"><span data-stu-id="b0541-127"><strong>911</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0541-128">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="b0541-128">EmergencyDialMask</span></span></p></td>
<td><p><span data-ttu-id="b0541-129"><strong>112</strong></span><span class="sxs-lookup"><span data-stu-id="b0541-129"><strong>112</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0541-130">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="b0541-130">NotificationUri</span></span></p></td>
<td><p><span data-ttu-id="b0541-131"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="b0541-131"><strong>sip:security@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0541-132">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="b0541-132">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="b0541-133"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="b0541-133"><strong>sip:+14255550123@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0541-134">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="b0541-134">ConferenceMode</span></span></p></td>
<td><p><span data-ttu-id="b0541-135"><strong>twoway</strong></span><span class="sxs-lookup"><span data-stu-id="b0541-135"><strong>twoway</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0541-136">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="b0541-136">LocationRefreshInterval</span></span></p></td>
<td><p><span data-ttu-id="b0541-137"><strong>2</strong></span><span class="sxs-lookup"><span data-stu-id="b0541-137"><strong>2</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b0541-138">Pour plus d’informations sur l’utilisation des stratégies d’emplacement, voir la documentation Lync Server Management Shell pour les applets de commande suivantes:</span><span class="sxs-lookup"><span data-stu-id="b0541-138">For details about working with location policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="b0541-139">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="b0541-139">New-CsLocationPolicy</span></span>

  - <span data-ttu-id="b0541-140">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="b0541-140">Get-CsLocationPolicy</span></span>

  - <span data-ttu-id="b0541-141">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="b0541-141">Set-CsLocationPolicy</span></span>

  - <span data-ttu-id="b0541-142">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="b0541-142">Remove-CsLocationPolicy</span></span>

  - <span data-ttu-id="b0541-143">Grant-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="b0541-143">Grant-CsLocationPolicy</span></span>

<div>

## <a name="to-create-location-policies"></a><span data-ttu-id="b0541-144">Pour créer des stratégies d’emplacement</span><span class="sxs-lookup"><span data-stu-id="b0541-144">To create location policies</span></span>

1.  <span data-ttu-id="b0541-145">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b0541-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b0541-146">CsLocationPolicy échouera si le paramètre pour <STRONG>PstnUsage</STRONG> ne figure pas déjà dans la liste Global de PstnUsages.</span><span class="sxs-lookup"><span data-stu-id="b0541-146">CsLocationPolicy will fail if the setting for <STRONG>PstnUsage</STRONG> is not already in the Global list of PstnUsages.</span></span>

    
    </div>

2.  <span data-ttu-id="b0541-147">Si vous le souhaitez, exécutez l’applet de commande ci-dessous pour modifier la stratégie d’emplacement globale :</span><span class="sxs-lookup"><span data-stu-id="b0541-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  <span data-ttu-id="b0541-148">Pour créer une stratégie d’emplacement avec balise, exécutez l’opération ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="b0541-148">Run the following to create a tagged Location Policy.</span></span>
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  <span data-ttu-id="b0541-149">Exécutez l’applet de commande ci-dessous pour appliquer la stratégie d’emplacement avec balise créée lors de l’étape 3 à une stratégie d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b0541-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

