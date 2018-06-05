---
title: Création de stratégies d’emplacement dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Lisez cette rubrique pour savoir comment configurer améliorée des stratégies d’emplacement de service d’urgence (E9-1-1) dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 6687e5ac8d414ef9db49c2fccdde9dceedb93889
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568296"
---
# <a name="create-location-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="89eb5-103">Création de stratégies d’emplacement dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="89eb5-103">Create location policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="89eb5-104">Lisez cette rubrique pour savoir comment configurer améliorée des stratégies d’emplacement de service d’urgence (E9-1-1) dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="89eb5-104">Read this topic to learn how to configure enhanced emergency service (E9-1-1) location policies in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="89eb5-105">Skype pour Business Server utilise une stratégie d’emplacement pour activer Skype pour les clients d’entreprise pour E9-1-1 au cours de l’inscription du client.</span><span class="sxs-lookup"><span data-stu-id="89eb5-105">Skype for Business Server uses a location policy to enable Skype for Business clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="89eb5-106">Une stratégie d’emplacement contient les paramètres qui définissent les modalités de mise en œuvre du système E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="89eb5-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span> <span data-ttu-id="89eb5-107">Pour plus d’informations, voir [planifier des stratégies d’emplacement pour Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="89eb5-107">For more information, see [Plan location policies for Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span>
  
<span data-ttu-id="89eb5-108">Vous définissez des stratégies d’emplacement à l’aide de la Skype pour Business le panneau de configuration ou à l’aide de l’applet de commande [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="89eb5-108">You define location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="89eb5-109">Skype pour Business Server prend désormais en charge la configuration de plusieurs numéros d’urgence pour un client.</span><span class="sxs-lookup"><span data-stu-id="89eb5-109">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="89eb5-110">Si vous souhaitez configurer plusieurs numéros d’urgence, vous devez suivre les informations de [planifier plusieurs numéros d’urgence dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) et [configurer plusieurs numéros d’urgence dans Skype pour Business 2015](configure-multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="89eb5-110">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business 2015](configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="89eb5-p103">Vous pouvez modifier la stratégie d’emplacement globale et créer des stratégies d’emplacement avec balise. Un client obtient une stratégie globale lorsqu’il ne se situe pas dans un sous-réseau auquel une stratégie d’emplacement est associée ou lorsque le client n’a pas été affecté directement à une stratégie d’emplacement. Les stratégies avec balise sont affectées aux sous-réseaux ou aux utilisateurs.  </span><span class="sxs-lookup"><span data-stu-id="89eb5-p103">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span> 
  
<span data-ttu-id="89eb5-114">Pour créer une stratégie d’emplacement, vous devez utiliser un compte membre du groupe RTCUniversalServerAdmins, membre du rôle administratif CsVoiceAdministrator ou possédant des droits et des autorisations d’administrateur équivalents.</span><span class="sxs-lookup"><span data-stu-id="89eb5-114">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>
  
<span data-ttu-id="89eb5-115">Pour plus d’informations, voir [planifier des stratégies d’emplacement pour Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="89eb5-115">For more information, see [Plan location policies for Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span> <span data-ttu-id="89eb5-116">Les applets de commande dans cette procédure utilisent une stratégie d'emplacement définie à l'aide des valeurs suivantes.</span><span class="sxs-lookup"><span data-stu-id="89eb5-116">Cmdlets in this procedure use a location policy defined using the following values.</span></span> <span data-ttu-id="89eb5-117">Pour obtenir une description complète des paramètres de l’applet de commande et les valeurs, voir [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="89eb5-117">For a complete description of cmdlet parameters and values, see [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span></span>
  
|<span data-ttu-id="89eb5-118">**Élément**</span><span class="sxs-lookup"><span data-stu-id="89eb5-118">**Element**</span></span>|<span data-ttu-id="89eb5-119">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="89eb5-119">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="89eb5-120">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="89eb5-120">EnhancedEmergencyServicesEnabled</span></span>  <br/> |<span data-ttu-id="89eb5-121">**True**</span><span class="sxs-lookup"><span data-stu-id="89eb5-121">**True**</span></span> <br/> |
|<span data-ttu-id="89eb5-122">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="89eb5-122">LocationRequired</span></span>  <br/> |<span data-ttu-id="89eb5-123">**Clause d’exclusion**</span><span class="sxs-lookup"><span data-stu-id="89eb5-123">**Disclaimer**</span></span> <br/> |
|<span data-ttu-id="89eb5-124">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="89eb5-124">EnhancedEmergencyServiceDisclaimer</span></span>  <br/> |<span data-ttu-id="89eb5-p105">La stratégie de votre société exige que vous définissiez un emplacement. Si vous ne le faites pas, les services d’urgence ne pourront pas vous localiser en cas d’urgence. Définissez un emplacement.</span><span class="sxs-lookup"><span data-stu-id="89eb5-p105">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span>  <br/> |
|<span data-ttu-id="89eb5-128">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="89eb5-128">UseLocationForE911Only</span></span>  <br/> |<span data-ttu-id="89eb5-129">**False**</span><span class="sxs-lookup"><span data-stu-id="89eb5-129">**False**</span></span> <br/> |
|<span data-ttu-id="89eb5-130">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="89eb5-130">PstnUsage</span></span>  <br/> |<span data-ttu-id="89eb5-131">**EmergencyUsage**</span><span class="sxs-lookup"><span data-stu-id="89eb5-131">**EmergencyUsage**</span></span> <br/> |
|<span data-ttu-id="89eb5-132">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="89eb5-132">EmergencyDialString</span></span>  <br/> |<span data-ttu-id="89eb5-133">**911**</span><span class="sxs-lookup"><span data-stu-id="89eb5-133">**911**</span></span> <br/> |
|<span data-ttu-id="89eb5-134">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="89eb5-134">EmergencyDialMask</span></span>  <br/> |<span data-ttu-id="89eb5-135">**112**</span><span class="sxs-lookup"><span data-stu-id="89eb5-135">**112**</span></span> <br/> |
|<span data-ttu-id="89eb5-136">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="89eb5-136">NotificationUri</span></span>  <br/> |<span data-ttu-id="89eb5-137">**SIP:Security@litwareinc.com**</span><span class="sxs-lookup"><span data-stu-id="89eb5-137">**sip:security@litwareinc.com**</span></span> <br/> |
|<span data-ttu-id="89eb5-138">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="89eb5-138">ConferenceUri</span></span>  <br/> |<span data-ttu-id="89eb5-139">**SIP:+14255550123@litwareinc.com**</span><span class="sxs-lookup"><span data-stu-id="89eb5-139">**sip:+14255550123@litwareinc.com**</span></span> <br/> |
|<span data-ttu-id="89eb5-140">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="89eb5-140">ConferenceMode</span></span>  <br/> |<span data-ttu-id="89eb5-141">**twoway**</span><span class="sxs-lookup"><span data-stu-id="89eb5-141">**twoway**</span></span> <br/> |
|<span data-ttu-id="89eb5-142">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="89eb5-142">LocationRefreshInterval</span></span>  <br/> |<span data-ttu-id="89eb5-143">**2**</span><span class="sxs-lookup"><span data-stu-id="89eb5-143">**2**</span></span> <br/> |
   
### <a name="to-create-location-policies"></a><span data-ttu-id="89eb5-144">Pour créer des stratégies d’emplacement</span><span class="sxs-lookup"><span data-stu-id="89eb5-144">To create location policies</span></span>

1. <span data-ttu-id="89eb5-145">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="89eb5-145">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="89eb5-146">CsLocationPolicy échouera si le paramètre pour **PstnUsage** ne figure pas déjà dans la liste Global de PstnUsages.</span><span class="sxs-lookup"><span data-stu-id="89eb5-146">CsLocationPolicy will fail if the setting for **PstnUsage** is not already in the Global list of PstnUsages.</span></span>
  
2. <span data-ttu-id="89eb5-147">Si vous le souhaitez, exécutez l’applet de commande ci-dessous pour modifier la stratégie d’emplacement globale :</span><span class="sxs-lookup"><span data-stu-id="89eb5-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>
    
   ```
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. <span data-ttu-id="89eb5-148">Pour créer une stratégie d’emplacement avec balise, exécutez l’opération ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="89eb5-148">Run the following to create a tagged Location Policy.</span></span>
    
   ```
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. <span data-ttu-id="89eb5-149">Exécutez l’applet de commande ci-dessous pour appliquer la stratégie d’emplacement avec balise créée lors de l’étape 3 à une stratégie d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="89eb5-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>
    
   ```
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```