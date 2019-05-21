---
title: Configurer le routage direct
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Apprenez à configurer le routage direct du système Microsoft Phone.
ms.openlocfilehash: ce3fff5205a2cb78c1d409ae8595a50c73f70aaf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290444"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="2cde5-103">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="2cde5-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="2cde5-104">Regardez la session suivante pour en savoir plus sur les avantages du routage direct, la planification et le déploiement: [routage direct dans Microsoft teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="2cde5-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="2cde5-105">Si vous ne l’avez pas encore fait, lisez [planifier le routage direct](direct-routing-plan.md) pour les prérequis et passer en revue les autres étapes que vous devez effectuer avant de configurer votre réseau de systèmes Microsoft Phone.</span><span class="sxs-lookup"><span data-stu-id="2cde5-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="2cde5-106">Cet article décrit comment configurer le routage direct du système Microsoft Phone.</span><span class="sxs-lookup"><span data-stu-id="2cde5-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="2cde5-107">Il explique en détail comment jumeler une manette de frontière de session (SBC) prise en charge et configurer les utilisateurs de Microsoft teams pour se connecter au réseau téléphonique public commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="2cde5-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="2cde5-108">Pour suivre les étapes décrites dans cet article, les administrateurs doivent vous familiariser avec les applets de cmdlet PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cde5-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="2cde5-109">Pour plus d’informations sur l’utilisation de PowerShell, voir [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="2cde5-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="2cde5-110">Nous vous conseillons de vérifier que votre SBC a déjà été configuré comme recommandé par votre fournisseur de SBC:</span><span class="sxs-lookup"><span data-stu-id="2cde5-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="2cde5-111">Documentation de déploiement AudioCodes</span><span class="sxs-lookup"><span data-stu-id="2cde5-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="2cde5-112">Documentation sur le déploiement des communications du ruban</span><span class="sxs-lookup"><span data-stu-id="2cde5-112">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)

<span data-ttu-id="2cde5-113">Vous pouvez configurer votre système Microsoft Phone et permettre aux utilisateurs d’utiliser le routage direct, puis configurer Microsoft teams en tant que client appelant préféré en exécutant les procédures suivantes:</span><span class="sxs-lookup"><span data-stu-id="2cde5-113">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="2cde5-114">Coupler une SBC avec un système Microsoft Phone et valider le jumelage</span><span class="sxs-lookup"><span data-stu-id="2cde5-114">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-direct-routing-service-of-phone-system)
- [<span data-ttu-id="2cde5-115">Activer les utilisateurs pour le service de routage direct</span><span class="sxs-lookup"><span data-stu-id="2cde5-115">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="2cde5-116">Vérifiez que Microsoft teams est le client appelant préféré pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="2cde5-116">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="2cde5-117">Coupler l’SBC au service de routage direct du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="2cde5-117">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="2cde5-118">Voici les trois principales étapes pour vous permettre de vous connecter, ou jumeler, l’interface SBC à l’interface de routage directe:</span><span class="sxs-lookup"><span data-stu-id="2cde5-118">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="2cde5-119">Se connecter au centre **d’administration de Skype entreprise Online** à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="2cde5-119">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="2cde5-120">Coupler l’SBC</span><span class="sxs-lookup"><span data-stu-id="2cde5-120">Pair the SBC</span></span> 
- <span data-ttu-id="2cde5-121">Valider le jumelage</span><span class="sxs-lookup"><span data-stu-id="2cde5-121">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="2cde5-122">Se connecter à Skype entreprise Online à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="2cde5-122">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="2cde5-123">Vous pouvez utiliser une session PowerShell connectée au client pour jumeler l’interface SBC à l’interface de routage directe.</span><span class="sxs-lookup"><span data-stu-id="2cde5-123">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="2cde5-124">Pour ouvrir une session PowerShell, suivez les étapes décrites dans [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="2cde5-124">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="2cde5-125">Après avoir établi une session PowerShell distante, vérifiez que vous pouvez voir les commandes pour gérer l’SBC.</span><span class="sxs-lookup"><span data-stu-id="2cde5-125">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="2cde5-126">Pour valider les commandes, tapez ou copiez/collez les éléments suivants dans la session PowerShell, puis appuyez sur entrée:</span><span class="sxs-lookup"><span data-stu-id="2cde5-126">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="2cde5-127">Votre commande renverra les quatre fonctions indiquées ici pour vous permettre de gérer l’SBC.</span><span class="sxs-lookup"><span data-stu-id="2cde5-127">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="2cde5-128">Coupler l’SBC au client</span><span class="sxs-lookup"><span data-stu-id="2cde5-128">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="2cde5-129">Pour jumeler l’SBC au client, dans la session PowerShell, entrez ce qui suit, puis appuyez sur entrée:</span><span class="sxs-lookup"><span data-stu-id="2cde5-129">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="2cde5-130">Nous vous recommandons vivement de définir une limite d’appels maximale dans l’SBC en utilisant les informations qui figurent dans la documentation de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="2cde5-130">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="2cde5-131">La limite déclenche une notification si l’SBC a le niveau de capacité.</span><span class="sxs-lookup"><span data-stu-id="2cde5-131">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="2cde5-132">Vous pouvez uniquement jumeler l’SBC si la partie Domain de son nom de domaine complet correspond à l’un des domaines inscrits \*dans votre client, à l’exception de. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2cde5-132">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="2cde5-133">L' \*utilisation des noms de domaine. onmicrosoft.com n’est pas prise en charge pour le nom de domaine complet SBC.</span><span class="sxs-lookup"><span data-stu-id="2cde5-133">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="2cde5-134">Par exemple, si vous avez deux noms de domaine:</span><span class="sxs-lookup"><span data-stu-id="2cde5-134">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="2cde5-135">**contoso**. com</span><span class="sxs-lookup"><span data-stu-id="2cde5-135">**contoso**.com</span></span><br/><span data-ttu-id="2cde5-136">**contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2cde5-136">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="2cde5-137">Pour le nom SBC, vous pouvez utiliser le nom sbc.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2cde5-137">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="2cde5-138">Si vous essayez de jumeler l’SBC avec un nom SBC. contoso. ABC, le système ne vous en permettra pas, car le domaine n’est pas détenu par ce client.</span><span class="sxs-lookup"><span data-stu-id="2cde5-138">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="2cde5-139">Renvoie</span><span class="sxs-lookup"><span data-stu-id="2cde5-139">Returns:</span></span>
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
<span data-ttu-id="2cde5-140">Il existe d’autres options qui peuvent être définies lors du processus de jumelage.</span><span class="sxs-lookup"><span data-stu-id="2cde5-140">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="2cde5-141">Dans l’exemple précédent, seuls les paramètres minimum requis apparaissent.</span><span class="sxs-lookup"><span data-stu-id="2cde5-141">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="2cde5-142">Le tableau suivant répertorie les paramètres supplémentaires que vous pouvez utiliser dans les paramètres de configuration de`New-CsOnlinePstnGateway`</span><span class="sxs-lookup"><span data-stu-id="2cde5-142">The following table lists the additional parameters that you can use in setting parameters for `New-CsOnlinePstnGateway`</span></span>

|<span data-ttu-id="2cde5-143">Obligatoire?</span><span class="sxs-lookup"><span data-stu-id="2cde5-143">Required?</span></span>|<span data-ttu-id="2cde5-144">Nom</span><span class="sxs-lookup"><span data-stu-id="2cde5-144">Name</span></span>|<span data-ttu-id="2cde5-145">Description</span><span class="sxs-lookup"><span data-stu-id="2cde5-145">Description</span></span>|<span data-ttu-id="2cde5-146">Par défaut</span><span class="sxs-lookup"><span data-stu-id="2cde5-146">Default</span></span>|<span data-ttu-id="2cde5-147">Valeurs possibles</span><span class="sxs-lookup"><span data-stu-id="2cde5-147">Possible values</span></span>|<span data-ttu-id="2cde5-148">Type et restrictions</span><span class="sxs-lookup"><span data-stu-id="2cde5-148">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2cde5-149">Oui</span><span class="sxs-lookup"><span data-stu-id="2cde5-149">Yes</span></span>|<span data-ttu-id="2cde5-150">FQDN</span><span class="sxs-lookup"><span data-stu-id="2cde5-150">FQDN</span></span>|<span data-ttu-id="2cde5-151">Nom de domaine complet du SBC</span><span class="sxs-lookup"><span data-stu-id="2cde5-151">The FQDN name of the SBC</span></span> |<span data-ttu-id="2cde5-152">Aucun</span><span class="sxs-lookup"><span data-stu-id="2cde5-152">None</span></span>|<span data-ttu-id="2cde5-153">Nom NoneFQDN, limiter 63 caractères</span><span class="sxs-lookup"><span data-stu-id="2cde5-153">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="2cde5-154">Chaîne, liste de caractères autorisés et non autorisés sur [les conventions d’appellation dans Active Directory pour les ordinateurs, domaines, sites et UO](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="2cde5-154">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="2cde5-155">Non</span><span class="sxs-lookup"><span data-stu-id="2cde5-155">No</span></span>|<span data-ttu-id="2cde5-156">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="2cde5-156">MediaBypass</span></span> |<span data-ttu-id="2cde5-157">Paramètre réservé pour une utilisation ultérieure.</span><span class="sxs-lookup"><span data-stu-id="2cde5-157">The parameter reserved for future use.</span></span> <span data-ttu-id="2cde5-158">Le paramètre indiqué par l’élément SBC prend en charge la dérivation multimédia et l’administrateur veut l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="2cde5-158">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="2cde5-159">Aucun</span><span class="sxs-lookup"><span data-stu-id="2cde5-159">None</span></span>|<span data-ttu-id="2cde5-160">True</span><span class="sxs-lookup"><span data-stu-id="2cde5-160">True</span></span><br/><span data-ttu-id="2cde5-161">False</span><span class="sxs-lookup"><span data-stu-id="2cde5-161">False</span></span>|<span data-ttu-id="2cde5-162">Boolean</span><span class="sxs-lookup"><span data-stu-id="2cde5-162">Boolean</span></span>|
|<span data-ttu-id="2cde5-163">Oui</span><span class="sxs-lookup"><span data-stu-id="2cde5-163">Yes</span></span>|<span data-ttu-id="2cde5-164">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="2cde5-164">SipSignallingPort</span></span> |<span data-ttu-id="2cde5-165">Port d’écoute utilisé pour la communication avec les services de routage directe à l’aide du protocole TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="2cde5-165">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="2cde5-166">Aucun</span><span class="sxs-lookup"><span data-stu-id="2cde5-166">None</span></span>|<span data-ttu-id="2cde5-167">Tout port</span><span class="sxs-lookup"><span data-stu-id="2cde5-167">Any port</span></span>|<span data-ttu-id="2cde5-168">entre 0 et 65535</span><span class="sxs-lookup"><span data-stu-id="2cde5-168">0 to 65535</span></span> |
|<span data-ttu-id="2cde5-169">Non</span><span class="sxs-lookup"><span data-stu-id="2cde5-169">No</span></span>|<span data-ttu-id="2cde5-170">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="2cde5-170">FailoverTimeSeconds</span></span> |<span data-ttu-id="2cde5-171">Lorsque la valeur est définie sur 10 (valeur par défaut), les appels sortants pour lesquels la passerelle ne répond pas dans un délai de 10 secondes sont routés vers le Trunk disponible suivant; s’il n’y a pas de lignes supplémentaires, l’appel est automatiquement interrompu.</span><span class="sxs-lookup"><span data-stu-id="2cde5-171">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="2cde5-172">Dans une organisation avec des réponses de passerelle ou réseau lentes, cela peut entraîner l’abandon de nombreux appels.</span><span class="sxs-lookup"><span data-stu-id="2cde5-172">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="2cde5-173">La valeur par défaut est 10.</span><span class="sxs-lookup"><span data-stu-id="2cde5-173">The default value is 10.</span></span>|<span data-ttu-id="2cde5-174">0,10</span><span class="sxs-lookup"><span data-stu-id="2cde5-174">10</span></span>|<span data-ttu-id="2cde5-175">Numéro</span><span class="sxs-lookup"><span data-stu-id="2cde5-175">Number</span></span>|<span data-ttu-id="2cde5-176">Ent</span><span class="sxs-lookup"><span data-stu-id="2cde5-176">Int</span></span>|
|<span data-ttu-id="2cde5-177">Non</span><span class="sxs-lookup"><span data-stu-id="2cde5-177">No</span></span>|<span data-ttu-id="2cde5-178">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="2cde5-178">ForwardCallHistory</span></span> |<span data-ttu-id="2cde5-179">Indique si les informations d’historique d’appel sont transférées par le biais de la jonction.</span><span class="sxs-lookup"><span data-stu-id="2cde5-179">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="2cde5-180">Si cette option est activée, le Proxy RTC Office 365 envoie deux en-têtes: History-Info et expertisé.</span><span class="sxs-lookup"><span data-stu-id="2cde5-180">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="2cde5-181">La valeur par défaut \*\*\*\* est false ($false).</span><span class="sxs-lookup"><span data-stu-id="2cde5-181">The default value is **False** ($False).</span></span> |<span data-ttu-id="2cde5-182">False</span><span class="sxs-lookup"><span data-stu-id="2cde5-182">False</span></span>|<span data-ttu-id="2cde5-183">True</span><span class="sxs-lookup"><span data-stu-id="2cde5-183">True</span></span><br/><span data-ttu-id="2cde5-184">False</span><span class="sxs-lookup"><span data-stu-id="2cde5-184">False</span></span>|<span data-ttu-id="2cde5-185">Boolean</span><span class="sxs-lookup"><span data-stu-id="2cde5-185">Boolean</span></span>|
|<span data-ttu-id="2cde5-186">Non</span><span class="sxs-lookup"><span data-stu-id="2cde5-186">No</span></span>|<span data-ttu-id="2cde5-187">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="2cde5-187">ForwardPAI</span></span>|<span data-ttu-id="2cde5-188">Indique si l’en-tête P-Asserted-Identity (PAI) sera transféré avec l’appel.</span><span class="sxs-lookup"><span data-stu-id="2cde5-188">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="2cde5-189">L’en-tête PAI permet de vérifier l’identité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="2cde5-189">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="2cde5-190">Si vous avez activé l’en-tête d’ID vie privée: il est également envoyé.</span><span class="sxs-lookup"><span data-stu-id="2cde5-190">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="2cde5-191">La valeur par défaut \*\*\*\* est false ($false).</span><span class="sxs-lookup"><span data-stu-id="2cde5-191">The default value is **False** ($False).</span></span>|<span data-ttu-id="2cde5-192">False</span><span class="sxs-lookup"><span data-stu-id="2cde5-192">False</span></span>|<span data-ttu-id="2cde5-193">True</span><span class="sxs-lookup"><span data-stu-id="2cde5-193">True</span></span><br/><span data-ttu-id="2cde5-194">False</span><span class="sxs-lookup"><span data-stu-id="2cde5-194">False</span></span>|<span data-ttu-id="2cde5-195">Boolean</span><span class="sxs-lookup"><span data-stu-id="2cde5-195">Boolean</span></span>|
|<span data-ttu-id="2cde5-196">Non</span><span class="sxs-lookup"><span data-stu-id="2cde5-196">No</span></span>|<span data-ttu-id="2cde5-197">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="2cde5-197">SendSIPOptions</span></span> |<span data-ttu-id="2cde5-198">Définit si une SBC va ou non envoyer les options SIP.</span><span class="sxs-lookup"><span data-stu-id="2cde5-198">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="2cde5-199">S’il est désactivé, l’SBC sera exclu du système de surveillance et d’alerte.</span><span class="sxs-lookup"><span data-stu-id="2cde5-199">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="2cde5-200">Nous vous recommandons vivement d’activer les options SIP.</span><span class="sxs-lookup"><span data-stu-id="2cde5-200">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="2cde5-201">La valeur par défaut est **true**.</span><span class="sxs-lookup"><span data-stu-id="2cde5-201">Default value is **True**.</span></span> |<span data-ttu-id="2cde5-202">True</span><span class="sxs-lookup"><span data-stu-id="2cde5-202">True</span></span>|<span data-ttu-id="2cde5-203">True</span><span class="sxs-lookup"><span data-stu-id="2cde5-203">True</span></span><br/><span data-ttu-id="2cde5-204">False</span><span class="sxs-lookup"><span data-stu-id="2cde5-204">False</span></span>|<span data-ttu-id="2cde5-205">Boolean</span><span class="sxs-lookup"><span data-stu-id="2cde5-205">Boolean</span></span>|
|<span data-ttu-id="2cde5-206">Non</span><span class="sxs-lookup"><span data-stu-id="2cde5-206">No</span></span>|<span data-ttu-id="2cde5-207">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="2cde5-207">MaxConcurrentSessions</span></span> |<span data-ttu-id="2cde5-208">Utilisé par le système d’alerte.</span><span class="sxs-lookup"><span data-stu-id="2cde5-208">Used by alerting system.</span></span> <span data-ttu-id="2cde5-209">Lorsque n’importe quelle valeur est définie, le système d’alerte génère une alerte auprès de l’administrateur client lorsque le nombre de sessions simultanées est 90% ou une valeur supérieure à celle-ci.</span><span class="sxs-lookup"><span data-stu-id="2cde5-209">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="2cde5-210">Si paramètre n’est pas défini, les alertes ne le sont pas.</span><span class="sxs-lookup"><span data-stu-id="2cde5-210">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="2cde5-211">Toutefois, le système de surveillance rapportera le nombre de sessions simultanées toutes les 24 heures.</span><span class="sxs-lookup"><span data-stu-id="2cde5-211">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="2cde5-212">Valeur</span><span class="sxs-lookup"><span data-stu-id="2cde5-212">Null</span></span>|<span data-ttu-id="2cde5-213">Valeur</span><span class="sxs-lookup"><span data-stu-id="2cde5-213">Null</span></span><br/><span data-ttu-id="2cde5-214">1 à 100 000</span><span class="sxs-lookup"><span data-stu-id="2cde5-214">1 to 100,000</span></span> ||
|<span data-ttu-id="2cde5-215">Non</span><span class="sxs-lookup"><span data-stu-id="2cde5-215">No</span></span>|<span data-ttu-id="2cde5-216">Activation</span><span class="sxs-lookup"><span data-stu-id="2cde5-216">Enabled\*</span></span>|<span data-ttu-id="2cde5-217">Utilisé pour activer cet SBC pour les appels sortants.</span><span class="sxs-lookup"><span data-stu-id="2cde5-217">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="2cde5-218">Peut être utilisé pour supprimer temporairement l’SBC, pendant sa mise à jour ou lors de la maintenance.</span><span class="sxs-lookup"><span data-stu-id="2cde5-218">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="2cde5-219">False</span><span class="sxs-lookup"><span data-stu-id="2cde5-219">False</span></span>|<span data-ttu-id="2cde5-220">True</span><span class="sxs-lookup"><span data-stu-id="2cde5-220">True</span></span><br/><span data-ttu-id="2cde5-221">False</span><span class="sxs-lookup"><span data-stu-id="2cde5-221">False</span></span>|<span data-ttu-id="2cde5-222">Boolean</span><span class="sxs-lookup"><span data-stu-id="2cde5-222">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="2cde5-223">Vérifier le jumelage des SBC</span><span class="sxs-lookup"><span data-stu-id="2cde5-223">Verify the SBC pairing</span></span> 

<span data-ttu-id="2cde5-224">Vérifiez la connexion:</span><span class="sxs-lookup"><span data-stu-id="2cde5-224">Verify the connection:</span></span> 
- <span data-ttu-id="2cde5-225">Vérifiez si la SBC est sur la liste de SBCs couplés.</span><span class="sxs-lookup"><span data-stu-id="2cde5-225">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="2cde5-226">Valider les options SIP.</span><span class="sxs-lookup"><span data-stu-id="2cde5-226">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="2cde5-227">Vérifier si la SBC est sur la liste de SBCs couplés</span><span class="sxs-lookup"><span data-stu-id="2cde5-227">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="2cde5-228">Une fois que vous avez couplé l’SBC, validez la présence de l’SBC dans la liste des éléments SBCs couplés en exécutant la commande suivante dans une session PowerShell distante:`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="2cde5-228">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="2cde5-229">La passerelle couplée doit apparaître dans la liste, comme illustré dans l’exemple ci-dessous, et vérifier que le paramètre *Enabled* affiche la valeur **true**.</span><span class="sxs-lookup"><span data-stu-id="2cde5-229">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="2cde5-230">Spécifi</span><span class="sxs-lookup"><span data-stu-id="2cde5-230">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="2cde5-231">Qui renvoie:</span><span class="sxs-lookup"><span data-stu-id="2cde5-231">Which returns:</span></span>
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="2cde5-232">Valider le flux d’options SIP</span><span class="sxs-lookup"><span data-stu-id="2cde5-232">Validate SIP Options flow</span></span> 

<span data-ttu-id="2cde5-233">Pour valider le jumelage à l’aide des options SIP sortants, utilisez l’interface de gestion des SBC et confirmez que l’SBC reçoit les réponses 200 OK à ses messages d’OPTIONS sortants.</span><span class="sxs-lookup"><span data-stu-id="2cde5-233">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="2cde5-234">Lorsque le routage direct voit les OPTIONS entrantes, il commence à envoyer des messages d’options SIP sortants au nom de domaine complet SBC configuré dans le champ d’en-tête de contact du message OPTIONS entrantes.</span><span class="sxs-lookup"><span data-stu-id="2cde5-234">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="2cde5-235">Pour valider le jumelage à l’aide des options SIP entrantes, utilisez l’interface de gestion des SBC et voyez que l’SBC envoie une réponse aux messages d’OPTIONS provenant du routage direct et que le code de réponse qu’il envoie est 200 OK.</span><span class="sxs-lookup"><span data-stu-id="2cde5-235">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="2cde5-236">Activer les utilisateurs pour le service de routage direct</span><span class="sxs-lookup"><span data-stu-id="2cde5-236">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="2cde5-237">Lorsque vous êtes prêt à activer les utilisateurs pour le service de routage direct, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="2cde5-237">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="2cde5-238">Créez un utilisateur dans Office 365 et attribuez une licence de système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="2cde5-238">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="2cde5-239">Assurez-vous que l’utilisateur est bien immobilier dans Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="2cde5-239">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="2cde5-240">Configurez le numéro de téléphone et activez voix entreprise et boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="2cde5-240">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="2cde5-241">Configurer le routage de la voix.</span><span class="sxs-lookup"><span data-stu-id="2cde5-241">Configure voice routing.</span></span> <span data-ttu-id="2cde5-242">L’itinéraire est validé automatiquement.</span><span class="sxs-lookup"><span data-stu-id="2cde5-242">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="2cde5-243">Créer un utilisateur dans Office 365 et affecter la licence</span><span class="sxs-lookup"><span data-stu-id="2cde5-243">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="2cde5-244">Deux options s’offrent à vous pour créer un utilisateur dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="2cde5-244">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="2cde5-245">Toutefois, nous recommandons que votre organisation sélectionne et utilise une option pour éviter les problèmes de routage:</span><span class="sxs-lookup"><span data-stu-id="2cde5-245">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="2cde5-246">Créer l’utilisateur dans l’annuaire Active Directory local et synchroniser l’utilisateur avec le Cloud.</span><span class="sxs-lookup"><span data-stu-id="2cde5-246">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="2cde5-247">Voir [intégrer vos annuaires locaux avec Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="2cde5-247">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="2cde5-248">Créer l’utilisateur directement dans le portail d’administration Office 365.</span><span class="sxs-lookup"><span data-stu-id="2cde5-248">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="2cde5-249">Pour plus d' [informations, voir ajouter des utilisateurs individuellement ou en bloc à Office 365-aide de l’administrateur](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="2cde5-249">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="2cde5-250">Si votre déploiement de Skype entreprise Online co-existe avec Skype entreprise 2015 ou Lync 2010/2013 local, la seule option prise en charge consiste à créer l’utilisateur dans Active Directory local et à synchroniser l’utilisateur dans le Cloud (option 1).</span><span class="sxs-lookup"><span data-stu-id="2cde5-250">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="2cde5-251">Licences requises:</span><span class="sxs-lookup"><span data-stu-id="2cde5-251">Required licenses:</span></span> 

- <span data-ttu-id="2cde5-252">Office 365 entreprise E3 (y compris marketing Plan2, Exchange Plan2 et Teams) + Téléphone</span><span class="sxs-lookup"><span data-stu-id="2cde5-252">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="2cde5-253">Office 365 entreprise E5 (y compris marketing Plan2, Exchange Plan2, équipes et système téléphonique)</span><span class="sxs-lookup"><span data-stu-id="2cde5-253">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="2cde5-254">Licences facultatives:</span><span class="sxs-lookup"><span data-stu-id="2cde5-254">Optional licenses:</span></span> 

- <span data-ttu-id="2cde5-255">Forfait d’appels</span><span class="sxs-lookup"><span data-stu-id="2cde5-255">Calling Plan</span></span> 
- <span data-ttu-id="2cde5-256">Audioconférence,</span><span class="sxs-lookup"><span data-stu-id="2cde5-256">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="2cde5-257">Vérifier que l’utilisateur est bien immobilier dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="2cde5-257">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="2cde5-258">Le routage direct nécessite que l’utilisateur soit hébergé dans Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="2cde5-258">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="2cde5-259">Pour cela, vous pouvez consulter le paramètre RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="2cde5-259">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="2cde5-260">Il doit avoir une valeur dans le domaine infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="2cde5-260">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="2cde5-261">Connectez-vous à Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cde5-261">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="2cde5-262">Émettez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="2cde5-262">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="2cde5-263">Configuration du numéro de téléphone et activation de la voix et de la boîte vocale entreprise</span><span class="sxs-lookup"><span data-stu-id="2cde5-263">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="2cde5-264">Une fois que vous avez créé l’utilisateur et attribué une licence, l’étape suivante consiste à configurer son numéro de téléphone et sa boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="2cde5-264">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="2cde5-265">Cette opération peut être réalisée en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="2cde5-265">This can be done in one step.</span></span> 

<span data-ttu-id="2cde5-266">Pour ajouter le numéro de téléphone et l’activer pour la boîte vocale, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="2cde5-266">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="2cde5-267">Se connecter à une session PowerShell distante.</span><span class="sxs-lookup"><span data-stu-id="2cde5-267">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="2cde5-268">Entrez la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="2cde5-268">Enter the command:</span></span> 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="2cde5-269">Par exemple, pour ajouter un numéro de téléphone pour l’utilisateur «Beaune Low», entrez ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="2cde5-269">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="2cde5-270">Le numéro de téléphone utilisé doit être configuré en tant que numéro de téléphone avec l’indicatif du pays.</span><span class="sxs-lookup"><span data-stu-id="2cde5-270">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="2cde5-271">Si le numéro de téléphone de l’utilisateur est géré en local, utilisez l’interpréteur de commandes ou le panneau de configuration Skype entreprise local pour configurer le numéro de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2cde5-271">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="2cde5-272">Configurer le routage de la voix</span><span class="sxs-lookup"><span data-stu-id="2cde5-272">Configure Voice Routing</span></span> 

<span data-ttu-id="2cde5-273">Le système Microsoft Phone possède un mécanisme de routage qui permet d’envoyer un appel à un SBC spécifique en fonction de:</span><span class="sxs-lookup"><span data-stu-id="2cde5-273">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="2cde5-274">Modèle de nombre appelé</span><span class="sxs-lookup"><span data-stu-id="2cde5-274">Called number pattern</span></span> 
- <span data-ttu-id="2cde5-275">Appel de modèle de numéro + utilisateur spécifique qui effectue l’appel</span><span class="sxs-lookup"><span data-stu-id="2cde5-275">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="2cde5-276">SBCs peut être désignée comme active et Backup.</span><span class="sxs-lookup"><span data-stu-id="2cde5-276">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="2cde5-277">Cela signifie que lorsque l’SBC configuré comme étant actif pour ce modèle de nombre, ou un modèle de nombre (utilisateur spécifique) n’est pas disponible, les appels sont dirigés vers un SBC de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="2cde5-277">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="2cde5-278">Le routage des appels se compose des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="2cde5-278">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="2cde5-279">Politique de routage de la voix-conteneur d’utilisation PSTN; peuvent être affectés à un utilisateur ou à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="2cde5-279">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="2cde5-280">Usages PSTN: conteneur des itinéraires vocaux et des utilisations PSTN; peuvent être partagés dans différentes politiques de routage vocal</span><span class="sxs-lookup"><span data-stu-id="2cde5-280">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="2cde5-281">Itinéraires vocaux: modèle numérique et ensemble de passerelles RTC en ligne à utiliser pour les appels dans lesquels le numéro de téléphone correspond au modèle</span><span class="sxs-lookup"><span data-stu-id="2cde5-281">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="2cde5-282">Passerelle RTC en ligne-pointeur vers une SBC, qui stocke également la configuration appliquée lors de l’appel via SBC, telle que l’envoi d’identité P-assertion (PAI) ou de codecs préférés. peuvent être ajoutés aux itinéraires vocaux</span><span class="sxs-lookup"><span data-stu-id="2cde5-282">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="2cde5-283">Création d’une stratégie de routage de la voix avec une utilisation PSTN</span><span class="sxs-lookup"><span data-stu-id="2cde5-283">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="2cde5-284">Le schéma suivant montre deux exemples de stratégies de routage de voix dans le flux d’appels.</span><span class="sxs-lookup"><span data-stu-id="2cde5-284">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="2cde5-285">**Flux d’appels 1 (à gauche):** Si un utilisateur effectue un appel vers + 1 425 XXX XX XX ou + 1 206 XXX XX XX, l’appel est acheminé vers SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="2cde5-285">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="2cde5-286">Si les sbc1.contoso.biz et sbc2.contoso.biz ne sont pas disponibles, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="2cde5-286">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="2cde5-287">**Flux d’appels 2 (sur la droite):** Si un utilisateur effectue un appel vers + 1 425 XX XX XX ou + 1 206 XXX XX XX, l’appel est d’abord routé vers SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="2cde5-287">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="2cde5-288">Si aucun SBC n’est disponible, l’itinéraire dont la priorité est faible est essayé (sbc3.contoso.biz et sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="2cde5-288">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="2cde5-289">Si aucune des SBCs n’est disponible, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="2cde5-289">If none of the SBCs are available, the call is dropped.</span></span> 

![Exemples de stratégies de routage vocale](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="2cde5-291">Dans les deux exemples, si les priorités de l’itinéraire vocal sont affectées, les éléments SBCs dans les itinéraires sont essayés dans un ordre aléatoire.</span><span class="sxs-lookup"><span data-stu-id="2cde5-291">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2cde5-292">À moins que l’utilisateur ne dispose d’une licence de plan d’appel Microsoft, les appels vers n’importe quel numéro, à l’exception des numéros correspondant aux modèles + 1 425 XXX XX XX ou + 1 206 XXX XX XX dans l’exemple de configuration sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="2cde5-292">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="2cde5-293">Si l’utilisateur dispose d’une licence de plan d’appel, l’appel est automatiquement acheminé conformément aux politiques du forfait d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2cde5-293">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="2cde5-294">Le plan d’appel Microsoft s’applique automatiquement en tant que dernier itinéraire à tous les utilisateurs dotés de la licence de plan d’appel Microsoft et ne nécessite pas de configuration du routage des appels supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="2cde5-294">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="2cde5-295">Dans l’exemple ci-dessous, un itinéraire vocal est ajouté pour envoyer les appels vers tous les autres États-Unis et le numéro canadien (appels vers le modèle de numéro + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="2cde5-295">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Affiche la politique de routage téléphonique avec un troisième itinéraire](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="2cde5-297">Pour tous les autres appels, si un utilisateur possède les deux licences (système Microsoft Phone et forfait d’appel Microsoft), un itinéraire automatique est utilisé.</span><span class="sxs-lookup"><span data-stu-id="2cde5-297">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="2cde5-298">S’il ne correspond pas aux modèles de nombre dans les itinéraires vocaux en ligne créés par l’administrateur, route via un forfait d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2cde5-298">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="2cde5-299">Si l’utilisateur dispose uniquement du système Microsoft Phone, l’appel est abandonné, car aucune règle de correspondance n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="2cde5-299">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="2cde5-300">La valeur de priorité pour l’itinéraire «Other + 1» n’a pas d’importance dans ce cas, car il n’y a qu’un seul itinéraire correspondant au modèle + 1 XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="2cde5-300">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="2cde5-301">Si un utilisateur effectue un appel à + 1 324 567 89 89 et que les sbc5.contoso.biz et sbc6.contoso.biz ne sont pas disponibles, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="2cde5-301">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="2cde5-302">Le tableau suivant résume la configuration à l’aide de trois itinéraires vocaux.</span><span class="sxs-lookup"><span data-stu-id="2cde5-302">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="2cde5-303">Dans cet exemple, les trois itinéraires font partie de la même utilisation PSTN «États-Unis et Canada».</span><span class="sxs-lookup"><span data-stu-id="2cde5-303">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="2cde5-304">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="2cde5-304">**PSTN usage**</span></span>|<span data-ttu-id="2cde5-305">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="2cde5-305">**Voice route**</span></span>|<span data-ttu-id="2cde5-306">**Schéma de numéro**</span><span class="sxs-lookup"><span data-stu-id="2cde5-306">**Number pattern**</span></span>|<span data-ttu-id="2cde5-307">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="2cde5-307">**Priority**</span></span>|<span data-ttu-id="2cde5-308">**SBC**</span><span class="sxs-lookup"><span data-stu-id="2cde5-308">**SBC**</span></span>|<span data-ttu-id="2cde5-309">**Description**</span><span class="sxs-lookup"><span data-stu-id="2cde5-309">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2cde5-310">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="2cde5-310">US only</span></span>|<span data-ttu-id="2cde5-311">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="2cde5-311">"Redmond 1"</span></span>|<span data-ttu-id="2cde5-312">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="2cde5-312">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="2cde5-313">1</span><span class="sxs-lookup"><span data-stu-id="2cde5-313">1</span></span>|<span data-ttu-id="2cde5-314">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cde5-314">sbc1.contoso.biz</span></span><br/><span data-ttu-id="2cde5-315">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cde5-315">sbc2.contoso.biz</span></span>|<span data-ttu-id="2cde5-316">Itinéraire actif pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="2cde5-316">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="2cde5-317">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="2cde5-317">US only</span></span>|<span data-ttu-id="2cde5-318">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="2cde5-318">"Redmond 2"</span></span>|<span data-ttu-id="2cde5-319">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="2cde5-319">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="2cde5-320">2</span><span class="sxs-lookup"><span data-stu-id="2cde5-320">2</span></span>|<span data-ttu-id="2cde5-321">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cde5-321">sbc3.contoso.biz</span></span><br/><span data-ttu-id="2cde5-322">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cde5-322">sbc4.contoso.biz</span></span>|<span data-ttu-id="2cde5-323">Itinéraire de sauvegarde pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="2cde5-323">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="2cde5-324">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="2cde5-324">US only</span></span>|<span data-ttu-id="2cde5-325">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="2cde5-325">"Other +1"</span></span>|<span data-ttu-id="2cde5-326">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="2cde5-326">^\\+1(\d{10})$</span></span>|<span data-ttu-id="2cde5-327">3</span><span class="sxs-lookup"><span data-stu-id="2cde5-327">3</span></span>|<span data-ttu-id="2cde5-328">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cde5-328">sbc5.contoso.biz</span></span><br/><span data-ttu-id="2cde5-329">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cde5-329">sbc6.contoso.biz</span></span>|<span data-ttu-id="2cde5-330">Itinéraire pour les numéros appelés + 1 XXX XXX XX XX (sauf + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="2cde5-330">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="2cde5-331">Tous les itinéraires sont associés à l’utilisation RTC «États-Unis et Canada» et l’utilisation RTC est associée à la politique de routage de la voix «États-Unis uniquement».</span><span class="sxs-lookup"><span data-stu-id="2cde5-331">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="2cde5-332">Dans cet exemple, la stratégie de routage de la voix est affectée à user Spencer Low.</span><span class="sxs-lookup"><span data-stu-id="2cde5-332">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="2cde5-333">Exemples d’itinéraires d’appels</span><span class="sxs-lookup"><span data-stu-id="2cde5-333">Examples of call routes</span></span>

<span data-ttu-id="2cde5-334">Dans l’exemple suivant, nous montrons comment configurer des itinéraires, des utilisations RTC et des stratégies de routage, et nous affectons la stratégie à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2cde5-334">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="2cde5-335">**Étape 1:** Créez l’utilisation RTC «États-Unis et Canada».</span><span class="sxs-lookup"><span data-stu-id="2cde5-335">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="2cde5-336">Dans une session PowerShell distante Skype entreprise, tapez:</span><span class="sxs-lookup"><span data-stu-id="2cde5-336">In a Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="2cde5-337">Vérifiez que l’utilisation a été créée en entrant:</span><span class="sxs-lookup"><span data-stu-id="2cde5-337">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="2cde5-338">Qui renvoie une liste de noms qui risquent d’être tronqués:</span><span class="sxs-lookup"><span data-stu-id="2cde5-338">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="2cde5-339">Dans l’exemple ci-dessous, vous pouvez voir le résultat de l’exécution de `(Get-CSOnlinePSTNUsage).usage` la commande PowerShell pour afficher les noms complets (sans troncature).</span><span class="sxs-lookup"><span data-stu-id="2cde5-339">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span> 
<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

<span data-ttu-id="2cde5-340">**Étape 2:** Dans une session PowerShell dans Skype entreprise Online, créez trois itinéraires: Redmond 1, Redmond 2 et autres + 1, comme décrit dans le tableau précédent.</span><span class="sxs-lookup"><span data-stu-id="2cde5-340">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="2cde5-341">Pour créer l’itinéraire «Redmond 1», entrez:</span><span class="sxs-lookup"><span data-stu-id="2cde5-341">To create the "Redmond 1" route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="2cde5-342">Qui renvoie:</span><span class="sxs-lookup"><span data-stu-id="2cde5-342">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
SuppressCallerId    :
AlternateCallerId   :
</pre>
<span data-ttu-id="2cde5-343">Pour créer l’itinéraire de Redmond 2, entrez:</span><span class="sxs-lookup"><span data-stu-id="2cde5-343">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="2cde5-344">Pour créer l’autre itinéraire + 1, entrez:</span><span class="sxs-lookup"><span data-stu-id="2cde5-344">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="2cde5-345">Assurez-vous que votre expression régulière dans l’attribut NumberPattern est une expression valide.</span><span class="sxs-lookup"><span data-stu-id="2cde5-345">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="2cde5-346">Vous pouvez le tester à l’aide du site Web suivant:[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="2cde5-346">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="2cde5-347">Dans certains cas, il est nécessaire de router tous les appels vers le même SBC; Utilisez-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="2cde5-347">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

- <span data-ttu-id="2cde5-348">Acheminer tous les appels vers le même SBC</span><span class="sxs-lookup"><span data-stu-id="2cde5-348">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="2cde5-349">Vérifiez que vous avez correctement configuré l’itinéraire en exécutant la `Get-CSOnlineVoiceRoute` commande PowerShell en utilisant les options suivantes:</span><span class="sxs-lookup"><span data-stu-id="2cde5-349">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="2cde5-350">Qui doit retourner:</span><span class="sxs-lookup"><span data-stu-id="2cde5-350">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

<span data-ttu-id="2cde5-351">Dans l’exemple, l’itinéraire «Other + 1» a automatiquement la priorité 4.</span><span class="sxs-lookup"><span data-stu-id="2cde5-351">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="2cde5-352">**Étape 3:** Créez une stratégie de routage de la voix «États-Unis uniquement» et ajoutez-la à la politique «États-Unis et Canada».</span><span class="sxs-lookup"><span data-stu-id="2cde5-352">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="2cde5-353">Dans une session PowerShell dans Skype entreprise Online, tapez:</span><span class="sxs-lookup"><span data-stu-id="2cde5-353">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="2cde5-354">Le résultat est affiché dans cet exemple:</span><span class="sxs-lookup"><span data-stu-id="2cde5-354">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="2cde5-355">**Étape 4:** Accordez à l’utilisateur la politique de routage de la voix de faible utilisation par PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cde5-355">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="2cde5-356">Dans une session PowerShell dans Skype entreprise Online, tapez:</span><span class="sxs-lookup"><span data-stu-id="2cde5-356">In a PowerShell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="2cde5-357">Validez l’affectation de stratégie en entrant la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="2cde5-357">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="2cde5-358">Qui renvoie:</span><span class="sxs-lookup"><span data-stu-id="2cde5-358">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="2cde5-359">Création d’une stratégie de routage de la voix avec plusieurs utilisations PSTN</span><span class="sxs-lookup"><span data-stu-id="2cde5-359">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="2cde5-360">La politique de routage vocale créée auparavant n’autorise que les appels vers des numéros de téléphone aux États-Unis et au Canada, sauf si la licence de plan d’appel Microsoft est également affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2cde5-360">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="2cde5-361">Dans l’exemple qui suit, vous pouvez créer la stratégie de routage téléphonique «aucune restriction».</span><span class="sxs-lookup"><span data-stu-id="2cde5-361">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="2cde5-362">La stratégie réutilise l’utilisation RTC «États-Unis et Canada» créée dans l’exemple précédent, ainsi que la nouvelle utilisation RTC «international».</span><span class="sxs-lookup"><span data-stu-id="2cde5-362">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="2cde5-363">Cela achemine tous les autres appels vers l’SBCs sbc2.contoso.biz et sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="2cde5-363">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="2cde5-364">Les exemples qui s’affichent affectent la politique américaine uniquement à l’utilisateur «Beaune Low» et aucune restriction à l’utilisateur «Jean bois».</span><span class="sxs-lookup"><span data-stu-id="2cde5-364">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="2cde5-365">Spencer Low – appels uniquement autorisés vers les États-Unis et le Canada.</span><span class="sxs-lookup"><span data-stu-id="2cde5-365">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="2cde5-366">Lorsque vous appelez la gamme de numéros Redmond, l’ensemble spécifique de SBC doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="2cde5-366">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="2cde5-367">Les numéros non US ne seront pas routés sauf si la licence de plan d’appel est affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2cde5-367">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="2cde5-368">Jean bois – appels autorisés vers n’importe quel numéro.</span><span class="sxs-lookup"><span data-stu-id="2cde5-368">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="2cde5-369">Lorsque vous appelez la gamme de numéros Redmond, l’ensemble spécifique de SBC doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="2cde5-369">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="2cde5-370">Les numéros non US seront routés par le biais de sbc2.contoso.biz et sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="2cde5-370">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Affiche la politique de routage vocale affectée à l’utilisateur Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="2cde5-372">Pour tous les autres appels, si un utilisateur possède les deux licences (système Microsoft Phone et forfait d’appel Microsoft), un itinéraire automatique est utilisé.</span><span class="sxs-lookup"><span data-stu-id="2cde5-372">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="2cde5-373">S’il ne correspond pas aux modèles de nombre dans les itinéraires vocaux en ligne créés par l’administrateur, route via un forfait d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2cde5-373">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="2cde5-374">Si l’utilisateur dispose uniquement du système Microsoft Phone, l’appel est abandonné, car aucune règle de correspondance n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="2cde5-374">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Politique de routage de la voix attribuée à l’utilisateur Jean bois](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="2cde5-376">Le tableau suivant récapitule les concepteurs d’utilisation et les itinéraires vocaux de la stratégie de routage «aucune restriction».</span><span class="sxs-lookup"><span data-stu-id="2cde5-376">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="2cde5-377">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="2cde5-377">**PSTN usage**</span></span>|<span data-ttu-id="2cde5-378">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="2cde5-378">**Voice route**</span></span>|<span data-ttu-id="2cde5-379">**Schéma de numéro**</span><span class="sxs-lookup"><span data-stu-id="2cde5-379">**Number pattern**</span></span>|<span data-ttu-id="2cde5-380">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="2cde5-380">**Priority**</span></span>|<span data-ttu-id="2cde5-381">**SBC**</span><span class="sxs-lookup"><span data-stu-id="2cde5-381">**SBC**</span></span>|<span data-ttu-id="2cde5-382">**Description**</span><span class="sxs-lookup"><span data-stu-id="2cde5-382">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2cde5-383">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="2cde5-383">US Only</span></span>|<span data-ttu-id="2cde5-384">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="2cde5-384">"Redmond 1"</span></span>|<span data-ttu-id="2cde5-385">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="2cde5-385">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="2cde5-386">1</span><span class="sxs-lookup"><span data-stu-id="2cde5-386">1</span></span>|<span data-ttu-id="2cde5-387">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cde5-387">sbc1.contoso.biz</span></span><br/><span data-ttu-id="2cde5-388">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cde5-388">sbc2.contoso.biz</span></span>|<span data-ttu-id="2cde5-389">Itinéraire actif pour les numéros d’appelant + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="2cde5-389">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="2cde5-390">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="2cde5-390">US Only</span></span>|<span data-ttu-id="2cde5-391">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="2cde5-391">"Redmond 2"</span></span>|<span data-ttu-id="2cde5-392">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="2cde5-392">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="2cde5-393">2</span><span class="sxs-lookup"><span data-stu-id="2cde5-393">2</span></span>|<span data-ttu-id="2cde5-394">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cde5-394">sbc3.contoso.biz</span></span><br/><span data-ttu-id="2cde5-395">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cde5-395">sbc4.contoso.biz</span></span>|<span data-ttu-id="2cde5-396">Itinéraire de sauvegarde pour les numéros des appelants + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="2cde5-396">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="2cde5-397">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="2cde5-397">US Only</span></span>|<span data-ttu-id="2cde5-398">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="2cde5-398">"Other +1"</span></span>|<span data-ttu-id="2cde5-399">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="2cde5-399">^\\+1(\d{10})$</span></span>|<span data-ttu-id="2cde5-400">3</span><span class="sxs-lookup"><span data-stu-id="2cde5-400">3</span></span>|<span data-ttu-id="2cde5-401">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cde5-401">sbc5.contoso.biz</span></span><br/><span data-ttu-id="2cde5-402">sbc6>. contoso. biz</span><span class="sxs-lookup"><span data-stu-id="2cde5-402">sbc6>.contoso.biz</span></span>|<span data-ttu-id="2cde5-403">Itinéraire pour les numéros d’appelant + 1 XXX XXX XX XX (sauf + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="2cde5-403">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="2cde5-404">International</span><span class="sxs-lookup"><span data-stu-id="2cde5-404">International</span></span>|<span data-ttu-id="2cde5-405">International</span><span class="sxs-lookup"><span data-stu-id="2cde5-405">International</span></span>|<span data-ttu-id="2cde5-406">\d +</span><span class="sxs-lookup"><span data-stu-id="2cde5-406">\d+</span></span>|<span data-ttu-id="2cde5-407">4</span><span class="sxs-lookup"><span data-stu-id="2cde5-407">4</span></span>|<span data-ttu-id="2cde5-408">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cde5-408">sbc2.contoso.biz</span></span><br/><span data-ttu-id="2cde5-409">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="2cde5-409">sbc5.contoso.biz</span></span>|<span data-ttu-id="2cde5-410">Itinéraire pour n’importe quel modèle numérique</span><span class="sxs-lookup"><span data-stu-id="2cde5-410">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="2cde5-411">L’ordre des utilisations RTC dans les stratégies de routage vocale est essentiel.</span><span class="sxs-lookup"><span data-stu-id="2cde5-411">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="2cde5-412">Les utilisations sont appliquées dans l’ordre et, si une correspondance est trouvée dans la première utilisation, les autres utilisations ne sont jamais évaluées.</span><span class="sxs-lookup"><span data-stu-id="2cde5-412">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="2cde5-413">L’utilisation RTC «international» doit être placée après l’utilisation RTC «États-Unis uniquement».</span><span class="sxs-lookup"><span data-stu-id="2cde5-413">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="2cde5-414">Pour modifier l’ordre des utilisations RTC, exécutez la `Set-CSOnlineVoiceRoutingPolicy` commande.</span><span class="sxs-lookup"><span data-stu-id="2cde5-414">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="2cde5-415">Par exemple, pour passer de l’ordre «États-Unis et Canada» et inversement, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="2cde5-415">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="2cde5-416">Le niveau de priorité des itinéraires vocaux «Other + 1» et «international» est automatiquement attribué.</span><span class="sxs-lookup"><span data-stu-id="2cde5-416">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="2cde5-417">Il n’y a pas d’importance tant qu’il dispose de priorités inférieures à «Redmond 1» et «Redmond 2».</span><span class="sxs-lookup"><span data-stu-id="2cde5-417">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="2cde5-418">Exemple de politique de routage vocale pour les bois des utilisateurs de Jean</span><span class="sxs-lookup"><span data-stu-id="2cde5-418">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="2cde5-419">Les étapes à suivre pour créer une utilisation PSTN «international», un itinéraire vocal «international», «stratégie de routage vocale» n’est pas soumis à des restrictions», puis l’affecter à l’utilisateur «Jean bois» est le suivant.</span><span class="sxs-lookup"><span data-stu-id="2cde5-419">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


1. <span data-ttu-id="2cde5-420">Tout d’abord, créez l’utilisation RTC «international».</span><span class="sxs-lookup"><span data-stu-id="2cde5-420">First, create the PSTN Usage "International."</span></span> <span data-ttu-id="2cde5-421">Dans une session PowerShell distante dans Skype entreprise Online, entrez:</span><span class="sxs-lookup"><span data-stu-id="2cde5-421">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. <span data-ttu-id="2cde5-422">Ensuite, créez le nouveau message vocal «international».</span><span class="sxs-lookup"><span data-stu-id="2cde5-422">Next, create the new voice route "International."</span></span>

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   <span data-ttu-id="2cde5-423">Qui renvoie:</span><span class="sxs-lookup"><span data-stu-id="2cde5-423">Which returns:</span></span>

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : .*
   OnlinePstnUsages          : {International} 
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   SuppressCallerId          :
   AlternateCallerId         :
   </pre>
3. <span data-ttu-id="2cde5-424">Ensuite, créez une stratégie de routage téléphonique «aucune restriction».</span><span class="sxs-lookup"><span data-stu-id="2cde5-424">Next, create a Voice Routing Policy "No Restrictions".</span></span> <span data-ttu-id="2cde5-425">L’utilisation RTC «Redmond 1» et «Redmond» sont réutilisées dans cette politique de routage vocale pour garantir une gestion spéciale des appels au numéro «+ 1 425 XXX XX XX» et «+ 1 206 XXX XX XX» en tant qu’appels locaux ou locaux.</span><span class="sxs-lookup"><span data-stu-id="2cde5-425">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   <span data-ttu-id="2cde5-426">Qui renvoie</span><span class="sxs-lookup"><span data-stu-id="2cde5-426">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. <span data-ttu-id="2cde5-427">Attribuez la politique de routage de la voix à l’utilisateur «Jean bois» à l’aide de la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="2cde5-427">Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   <span data-ttu-id="2cde5-428">Vérifiez ensuite le devoir à l’aide de la commande:</span><span class="sxs-lookup"><span data-stu-id="2cde5-428">Then verify the assignment using the command:</span></span> 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   <span data-ttu-id="2cde5-429">Qui renvoie:</span><span class="sxs-lookup"><span data-stu-id="2cde5-429">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="2cde5-430">Le résultat est que la stratégie vocale appliquée aux appels de Jean-Martin n’est pas restreinte et qu’elle respecte la logique du routage des appels disponible aux États-Unis, au Canada et au service d’appels internationaux.</span><span class="sxs-lookup"><span data-stu-id="2cde5-430">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a><span data-ttu-id="2cde5-431">Définir Microsoft teams en tant que client appelant préféré pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="2cde5-431">Set Microsoft Teams as the preferred calling client for users</span></span>

<span data-ttu-id="2cde5-432">Le routage direct achemine uniquement les appels vers et depuis les utilisateurs s’ils utilisent le client Teams.</span><span class="sxs-lookup"><span data-stu-id="2cde5-432">Direct Routing only routes calls to and from users if they use the Teams client.</span></span> <span data-ttu-id="2cde5-433">Si votre organisation utilise uniquement Teams, il est recommandé de définir le mode «équipes uniquement» dans la stratégie de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="2cde5-433">If your organization only uses Teams, setting "Teams Only" mode in upgrade policy is recommended.</span></span> <span data-ttu-id="2cde5-434">Si votre organisation utilise Skype entreprise Server ou Skype entreprise Online, reportez-vous à l’article suivant pour plus d’informations et sélectionnez l’option appropriée: présentation de la coexistence et de la [mise à niveau de Skype entreprise et équipes](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="2cde5-434">If you organization uses Skype for Business Server or Skype for Business Online, see the following article for more information and select the appropriate option: [Understand coexistence and upgrade journey for Skype for Business and Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="see-also"></a><span data-ttu-id="2cde5-435">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2cde5-435">See also</span></span>

[<span data-ttu-id="2cde5-436">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="2cde5-436">Plan Direct Routing</span></span>](direct-routing-plan.md)
