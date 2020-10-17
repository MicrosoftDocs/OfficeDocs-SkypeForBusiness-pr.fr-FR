---
title: 'Lync Server 2013 : créer des stratégies d’emplacement'
description: 'Lync Server 2013 : créer des stratégies d’emplacement.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 464ea9893890ab6185f180434e2dad13818123d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562260"
---
# <a name="create-location-policies-in-lync-server-2013"></a><span data-ttu-id="1de1d-103">Créer des stratégies d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1de1d-103">Create location policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1de1d-104">_**Dernière modification de la rubrique :** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="1de1d-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="1de1d-105">Lync Server utilise une stratégie d’emplacement pour activer les clients Lync pour E9-1-1 lors de l’inscription du client.</span><span class="sxs-lookup"><span data-stu-id="1de1d-105">Lync Server uses a location policy to enable Lync clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="1de1d-106">Une stratégie d’emplacement contient les paramètres qui définissent comment E9-1-1 sera implémenté.</span><span class="sxs-lookup"><span data-stu-id="1de1d-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span>

<span data-ttu-id="1de1d-107">Vous pouvez modifier la stratégie d’emplacement globale et créer des stratégies d’emplacement marquées.</span><span class="sxs-lookup"><span data-stu-id="1de1d-107">You can edit the global location policy and create new tagged location policies.</span></span> <span data-ttu-id="1de1d-108">Un client obtient une stratégie globale lorsqu’il ne se trouve pas dans un sous-réseau avec une stratégie d’emplacement associée, ou lorsque le client n’a pas reçu directement une stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="1de1d-108">A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy.</span></span> <span data-ttu-id="1de1d-109">Les stratégies marquées sont affectées à des sous-réseaux ou des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1de1d-109">Tagged policies are assigned to subnets or users.</span></span>

<span data-ttu-id="1de1d-110">Pour créer une stratégie d’emplacement, vous devez utiliser un compte membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administration CsVoiceAdministrator, ou dispose de droits et d’autorisations d’administrateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="1de1d-110">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="1de1d-111">Pour obtenir une description complète des stratégies d’emplacement, voir [définition de la stratégie d’emplacement pour Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="1de1d-111">For a complete description of Location policies, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span> <span data-ttu-id="1de1d-112">Dans cette procédure, les cmdlets utilisent une stratégie d’emplacement définie à l’aide des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="1de1d-112">Cmdlets in this procedure use a location policy defined using the following values:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1de1d-113">Élément</span><span class="sxs-lookup"><span data-stu-id="1de1d-113">Element</span></span></th>
<th><span data-ttu-id="1de1d-114">Valeur</span><span class="sxs-lookup"><span data-stu-id="1de1d-114">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1de1d-115">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="1de1d-115">EnhancedEmergencyServicesEnabled</span></span></p></td>
<td><p><span data-ttu-id="1de1d-116"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="1de1d-116"><strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1de1d-117">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="1de1d-117">LocationRequired</span></span></p></td>
<td><p><span data-ttu-id="1de1d-118"><strong>Clause d’exclusion de responsabilité</strong></span><span class="sxs-lookup"><span data-stu-id="1de1d-118"><strong>Disclaimer</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1de1d-119">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="1de1d-119">EnhancedEmergencyServiceDisclaimer</span></span></p></td>
<td><p><span data-ttu-id="1de1d-120">La stratégie de votre entreprise exige que vous définiez un emplacement.</span><span class="sxs-lookup"><span data-stu-id="1de1d-120">Your company policy requires you to set a location.</span></span> <span data-ttu-id="1de1d-121">Si vous ne définissez pas d’emplacement, les services d’urgence ne seront pas en mesure de vous localiser en cas d’urgence.</span><span class="sxs-lookup"><span data-stu-id="1de1d-121">If you do not set a location, emergency services will not be able to locate you in an emergency.</span></span> <span data-ttu-id="1de1d-122">Définissez un emplacement.</span><span class="sxs-lookup"><span data-stu-id="1de1d-122">Please set a location.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1de1d-123">Uselocationfore911only était</span><span class="sxs-lookup"><span data-stu-id="1de1d-123">UseLocationForE911Only</span></span></p></td>
<td><p><span data-ttu-id="1de1d-124"><strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="1de1d-124"><strong>False</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1de1d-125">Pstnusage ne figure</span><span class="sxs-lookup"><span data-stu-id="1de1d-125">PstnUsage</span></span></p></td>
<td><p><span data-ttu-id="1de1d-126"><strong>EmergencyUsage</strong></span><span class="sxs-lookup"><span data-stu-id="1de1d-126"><strong>EmergencyUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1de1d-127">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="1de1d-127">EmergencyDialString</span></span></p></td>
<td><p><span data-ttu-id="1de1d-128"><strong>911</strong></span><span class="sxs-lookup"><span data-stu-id="1de1d-128"><strong>911</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1de1d-129">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="1de1d-129">EmergencyDialMask</span></span></p></td>
<td><p><span data-ttu-id="1de1d-130"><strong>112</strong></span><span class="sxs-lookup"><span data-stu-id="1de1d-130"><strong>112</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1de1d-131">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="1de1d-131">NotificationUri</span></span></p></td>
<td><p><span data-ttu-id="1de1d-132"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="1de1d-132"><strong>sip:security@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1de1d-133">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="1de1d-133">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="1de1d-134"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="1de1d-134"><strong>sip:+14255550123@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1de1d-135">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="1de1d-135">ConferenceMode</span></span></p></td>
<td><p><span data-ttu-id="1de1d-136"><strong>bilatéral</strong></span><span class="sxs-lookup"><span data-stu-id="1de1d-136"><strong>twoway</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1de1d-137">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="1de1d-137">LocationRefreshInterval</span></span></p></td>
<td><p><span data-ttu-id="1de1d-138"><strong>2</strong></span><span class="sxs-lookup"><span data-stu-id="1de1d-138"><strong>2</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1de1d-139">Pour plus d’informations sur l’utilisation des stratégies d’emplacement, voir la documentation de Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="1de1d-139">For details about working with location policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="1de1d-140">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="1de1d-140">New-CsLocationPolicy</span></span>

  - <span data-ttu-id="1de1d-141">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="1de1d-141">Get-CsLocationPolicy</span></span>

  - <span data-ttu-id="1de1d-142">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="1de1d-142">Set-CsLocationPolicy</span></span>

  - <span data-ttu-id="1de1d-143">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="1de1d-143">Remove-CsLocationPolicy</span></span>

  - <span data-ttu-id="1de1d-144">Grant-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="1de1d-144">Grant-CsLocationPolicy</span></span>

<div>

## <a name="to-create-location-policies"></a><span data-ttu-id="1de1d-145">Pour créer des stratégies d’emplacement</span><span class="sxs-lookup"><span data-stu-id="1de1d-145">To create location policies</span></span>

1.  <span data-ttu-id="1de1d-146">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1de1d-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1de1d-147">CsLocationPolicy échoue si le paramètre de <STRONG>pstnusage ne figure</STRONG> n’est pas déjà dans la liste globale des PstnUsages.</span><span class="sxs-lookup"><span data-stu-id="1de1d-147">CsLocationPolicy will fail if the setting for <STRONG>PstnUsage</STRONG> is not already in the Global list of PstnUsages.</span></span>

    
    </div>

2.  <span data-ttu-id="1de1d-148">Si vous le souhaitez, exécutez l’applet de commande suivante pour modifier la stratégie d’emplacement globale :</span><span class="sxs-lookup"><span data-stu-id="1de1d-148">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  <span data-ttu-id="1de1d-149">Exécutez la commande suivante pour créer une stratégie d’emplacement étiquetée.</span><span class="sxs-lookup"><span data-stu-id="1de1d-149">Run the following to create a tagged Location Policy.</span></span>
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  <span data-ttu-id="1de1d-150">Exécutez l’applet de commande suivante pour appliquer la stratégie d’emplacement marquée créée à l’étape 3 à une stratégie utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1de1d-150">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

