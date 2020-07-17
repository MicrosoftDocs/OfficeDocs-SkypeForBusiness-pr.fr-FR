---
title: Configuration du pavé de numérotation teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: Apprenez-en davantage sur la configuration du pavé de numérotation dans le client teams pour permettre aux utilisateurs d’accéder à la fonctionnalité de réseau téléphonique commuté (RTC).
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012415"
---
# <a name="dial-pad-configuration"></a><span data-ttu-id="eb173-103">Configuration du pavé de numérotation</span><span class="sxs-lookup"><span data-stu-id="eb173-103">Dial pad configuration</span></span>

<span data-ttu-id="eb173-104">Dans le client Microsoft Teams, le pavé de numérotation permet aux utilisateurs d’accéder à la fonctionnalité de réseau téléphonique commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="eb173-104">In the Teams client, the dial pad enables users to access Public Switched Telephone Network (PSTN) functionality.</span></span> <span data-ttu-id="eb173-105">Le pavé de numérotation est disponible pour les utilisateurs disposant d’une licence de système téléphonique, à condition qu’ils soient correctement configurés.</span><span class="sxs-lookup"><span data-stu-id="eb173-105">The dial pad is available for users with a Phone System license, provided they are configured properly.</span></span> <span data-ttu-id="eb173-106">Pour afficher le pavé de numérotation, vous devez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="eb173-106">The following criteria are all required for the dial pad to show:</span></span>

- <span data-ttu-id="eb173-107">L’utilisateur a une licence de système téléphonique (« MCOEV ») activée</span><span class="sxs-lookup"><span data-stu-id="eb173-107">User has an enabled Phone System (“MCOEV”) license</span></span>
- <span data-ttu-id="eb173-108">L’utilisateur a un forfait d’appel Microsoft ou est activé pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="eb173-108">User has Microsoft Calling Plan or is enabled for Direct Routing</span></span>
- <span data-ttu-id="eb173-109">L’utilisateur est doté de la voix entreprise activée</span><span class="sxs-lookup"><span data-stu-id="eb173-109">User has Enterprise Voice enabled</span></span>
- <span data-ttu-id="eb173-110">L’utilisateur est connecté en ligne et non dans Skype entreprise sur site</span><span class="sxs-lookup"><span data-stu-id="eb173-110">User is homed online and not in Skype for Business on premises</span></span>
- <span data-ttu-id="eb173-111">La stratégie d’appel des équipes est activée pour l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="eb173-111">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="eb173-112">Les sections suivantes décrivent comment utiliser PowerShell pour vérifier les critères.</span><span class="sxs-lookup"><span data-stu-id="eb173-112">The following sections describe how to use PowerShell to check the criteria.</span></span> <span data-ttu-id="eb173-113">Dans la plupart des cas, vous devez examiner diverses propriétés dans la sortie de l’applet de passe Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="eb173-113">In most cases, you need to look at various properties in the output of the Get-CsOnlineUser cmdlet.</span></span> <span data-ttu-id="eb173-114">Les exemples présupposent que le $user est l’adresse UPN ou la adresse SIP de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="eb173-114">Examples assume $user is either the UPN or sip address of the user.</span></span>

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a><span data-ttu-id="eb173-115">L’utilisateur a une licence de système téléphonique (« MCOEV ») activée</span><span class="sxs-lookup"><span data-stu-id="eb173-115">User has an enabled Phone System (“MCOEV”) license</span></span>

<span data-ttu-id="eb173-116">Vous devez vous assurer que le plan affecté pour l’utilisateur indique l' **attribut CapabilityStatus défini sur Enabled** et que le **plan de fonctionnalités a la valeur MCOEV** (licence du système téléphonique).</span><span class="sxs-lookup"><span data-stu-id="eb173-116">You must ensure that the assigned plan for the user shows the **CapabilityStatus attribute set to Enabled** and the **Capability Plan set to MCOEV** (Phone System license).</span></span> <span data-ttu-id="eb173-117">Vous pouvez voir MCOEV, MCOEV1, etc.</span><span class="sxs-lookup"><span data-stu-id="eb173-117">You might see MCOEV, MCOEV1, and so on.</span></span> <span data-ttu-id="eb173-118">Tous sont acceptables : tant que le plan de fonctionnalité commence par MCOEV.</span><span class="sxs-lookup"><span data-stu-id="eb173-118">All are acceptable--as long as the Capability Plan starts with MCOEV.</span></span>

<span data-ttu-id="eb173-119">Pour vérifier que les attributs sont correctement définis, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="eb173-119">To check that the attributes are set correctly, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="eb173-120">La sortie ressemblera à ce qui suit.</span><span class="sxs-lookup"><span data-stu-id="eb173-120">The output will look like the following.</span></span> <span data-ttu-id="eb173-121">Il vous suffit de vérifier les attributs **CapabilityStatus** et de **plan de fonctionnalité** :</span><span class="sxs-lookup"><span data-stu-id="eb173-121">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

```
<Plan SubscribedPlanId="2f9eda01-4630-4a5c-bdb3-cf195f22d240"  
   ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
   CapabilityStatus="Enabled"  
   AssignedTimestamp="2020-04-21T18:31:13Z" 
   ServicePlanId="4828c8ec-dc2e-4779-b502-87ac9ce28ab7" 
   xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11"> 
  <Capability> 
     <Capability Plan="MCOEV" 
     xmlns="http://schemas.microsoft.com/online/MCO/2009/01"/> 
  </Capability>
</Plan>
```


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a><span data-ttu-id="eb173-122">L’utilisateur a un forfait d’appel Microsoft ou est activé pour le routage direct</span><span class="sxs-lookup"><span data-stu-id="eb173-122">User has Microsoft Calling Plan OR is enabled for Direct Routing</span></span>

<span data-ttu-id="eb173-123">**Si l’utilisateur a un plan d’appel Microsoft**, vous devez vous assurer que l' **attribut CapabilityStatus est défini sur Enabled**, et que le **plan de capacité est défini sur MCOPSTN**.</span><span class="sxs-lookup"><span data-stu-id="eb173-123">**If the user has Microsoft Calling Plan**, you must ensure that the **CapabilityStatus attribute is set to Enabled**, and that the **Capability Plan is set to MCOPSTN**.</span></span> <span data-ttu-id="eb173-124">Vous pouvez voir MCOPSTN1, MCOPSTN2, etc.</span><span class="sxs-lookup"><span data-stu-id="eb173-124">You might see MCOPSTN1, MCOPSTN2, and so on.</span></span> <span data-ttu-id="eb173-125">Tous sont acceptables : tant que le plan de fonctionnalité commence par MCOPSTN.</span><span class="sxs-lookup"><span data-stu-id="eb173-125">All are acceptable--as long as the Capability Plan starts with MCOPSTN.</span></span>

<span data-ttu-id="eb173-126">Pour vérifier les attributs, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="eb173-126">To check the attributes, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="eb173-127">La sortie ressemblera à ce qui suit.</span><span class="sxs-lookup"><span data-stu-id="eb173-127">The output will look like the following.</span></span> <span data-ttu-id="eb173-128">Il vous suffit de vérifier les attributs **CapabilityStatus** et de **plan de fonctionnalité** :</span><span class="sxs-lookup"><span data-stu-id="eb173-128">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

```  
<Plan SubscribedPlanId="71d1258e-a4e6-443f-884e-0f3d6f644bb1" 
ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
CapabilityStatus="Enabled"    
AssignedTimestamp="2018-09-18T18:41:42Z" 
ServicePlanId="5a10155d-f5c1-411a-a8ec-e99aae125390" 
xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11">
 <Capability>
    <Capability Plan="MCOPSTN2" 
    xmlns="http://schemas.microsoft.com/online/MCO/2009/01" />
 </Capability>
</Plan>
  ```

<span data-ttu-id="eb173-129">**Si l’utilisateur est activé pour le routage direct**, l’utilisateur doit être affecté d’une valeur non null pour OnlineVoiceRoutingPolicy.</span><span class="sxs-lookup"><span data-stu-id="eb173-129">**If the user is enabled for Direct Routing**, the user must be assigned a non-null value for OnlineVoiceRoutingPolicy.</span></span> <span data-ttu-id="eb173-130">Pour vérifier l’attribut, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="eb173-130">To check the attribute, use the following command:</span></span>
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

<span data-ttu-id="eb173-131">La sortie doit avoir une valeur non null, par exemple :</span><span class="sxs-lookup"><span data-stu-id="eb173-131">The output should have a non-null value, for example:</span></span>

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a><span data-ttu-id="eb173-132">L’utilisateur est doté de la voix entreprise activée</span><span class="sxs-lookup"><span data-stu-id="eb173-132">User has Enterprise Voice enabled</span></span>

<span data-ttu-id="eb173-133">Pour vérifier si l’utilisateur est doté de la voix entreprise activée, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="eb173-133">To check if the user has Enterprise Voice enabled, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

<span data-ttu-id="eb173-134">Le résultat doit ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="eb173-134">The output should look like:</span></span>

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a><span data-ttu-id="eb173-135">L’utilisateur est connecté en ligne et non dans Skype entreprise sur site</span><span class="sxs-lookup"><span data-stu-id="eb173-135">User is homed online and not in Skype for Business on premises</span></span>

<span data-ttu-id="eb173-136">Pour vous assurer que l’utilisateur est en ligne et qu’il n’est pas disponible dans Skype entreprise sur site, la RegistrarPool ne doit pas être nulle et HostingProvider doit contenir une valeur commençant par « sipfed. online ».</span><span class="sxs-lookup"><span data-stu-id="eb173-136">To ensure the user is homed online and not in Skype for Business on premises, the RegistrarPool must not be null and the HostingProvider must contain a value that starts with “sipfed.online.”</span></span>  <span data-ttu-id="eb173-137">Pour vérifier les valeurs, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="eb173-137">To check the values, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

<span data-ttu-id="eb173-138">Le résultat doit ressembler à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="eb173-138">The output should be similar to:</span></span>

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a><span data-ttu-id="eb173-139">La stratégie d’appel des équipes est activée pour l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="eb173-139">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="eb173-140">Le TeamsCallingPolicy effectif de l’utilisateur doit avoir la valeur true pour AllowPrivateCalling.</span><span class="sxs-lookup"><span data-stu-id="eb173-140">The user’s effective TeamsCallingPolicy must have AllowPrivateCalling set to true.</span></span>  <span data-ttu-id="eb173-141">Par défaut, les utilisateurs héritent de la stratégie globale, dont la valeur par défaut est AllowPrivateCallingPolicy.</span><span class="sxs-lookup"><span data-stu-id="eb173-141">By default, users inherit the global policy, which has AllowPrivateCallingPolicy set to true by default.</span></span>

<span data-ttu-id="eb173-142">Pour obtenir le TeamsCallingPolicy d’un utilisateur et vérifier que AllowPrivateCalling est défini sur true, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="eb173-142">To get the TeamsCallingPolicy for a user and to check that AllowPrivateCalling is set to true, use the following command:</span></span>

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

<span data-ttu-id="eb173-143">Le résultat doit ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="eb173-143">The output should look like:</span></span>

```
Identity                   : Global
Description                :
AllowPrivateCalling        : True
AllowWebPSTNCalling        : True
AllowVoicemail             : UserOverride
AllowCallGroups            : True
AllowDelegation            : True
AllowCallForwardingToUser  : True
AllowCallForwardingToPhone : True
PreventTollBypass          : False
BusyOnBusyEnabledType      : Disabled
MusicOnHoldEnabledType     : Enabled
``` 

## <a name="additional-notes"></a><span data-ttu-id="eb173-144">Remarques supplémentaires</span><span class="sxs-lookup"><span data-stu-id="eb173-144">Additional notes</span></span>

-   <span data-ttu-id="eb173-145">Après avoir effectué ces modifications de configuration, vous devrez éventuellement redémarrer le client Teams.</span><span class="sxs-lookup"><span data-stu-id="eb173-145">You may need to restart the Teams client after making any of these configuration changes.</span></span>

-   <span data-ttu-id="eb173-146">Si vous avez récemment mis à jour l’un des critères ci-dessus, vous devrez peut-être patienter quelques heures avant que le client ne reçoive les nouveaux paramètres.</span><span class="sxs-lookup"><span data-stu-id="eb173-146">If you recently updated any of the above criteria, you may need to wait a few hours for the client to receive the new settings.</span></span>

-   <span data-ttu-id="eb173-147">Si vous ne voyez toujours pas le pavé de numérotation, vérifiez qu’il y a une erreur de mise en service à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="eb173-147">If you still don’t see the dial pad, check if there is a provisioning error by using the following command:</span></span>

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    <span data-ttu-id="eb173-148">S’il s’agit de plus de 24 heures et que vous rencontrez toujours des problèmes, contactez le support technique.</span><span class="sxs-lookup"><span data-stu-id="eb173-148">If it has been more than 24 hours and you are still seeing problems, contact Support.</span></span>


