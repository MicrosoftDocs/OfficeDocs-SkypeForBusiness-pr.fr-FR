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
- M365-voice
appliesto:
- Microsoft Teams
description: Apprenez à configurer le routage direct du système Microsoft Phone.
ms.openlocfilehash: 3524d3d41db02dbc123700ae259386bb97257bbd
ms.sourcegitcommit: c15ab82834005b9a19247e06488f1f21161fc426
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/13/2019
ms.locfileid: "40020068"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="21f54-103">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="21f54-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="21f54-104">Regardez la session suivante pour en savoir plus sur les avantages du routage direct, la planification et le déploiement : [routage direct dans Microsoft teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="21f54-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="21f54-105">Si vous ne l’avez pas encore fait, lisez [planifier le routage direct](direct-routing-plan.md) pour les prérequis et passer en revue les autres étapes que vous devez effectuer avant de configurer votre réseau de systèmes Microsoft Phone.</span><span class="sxs-lookup"><span data-stu-id="21f54-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="21f54-106">Cet article décrit comment configurer le routage direct du système Microsoft Phone.</span><span class="sxs-lookup"><span data-stu-id="21f54-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="21f54-107">Il explique en détail comment jumeler une manette de frontière de session (SBC) prise en charge et configurer les utilisateurs de Microsoft teams pour se connecter au réseau téléphonique public commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="21f54-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="21f54-108">Pour suivre les étapes décrites dans cet article, les administrateurs doivent vous familiariser avec les applets de cmdlet PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21f54-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="21f54-109">Pour plus d’informations sur l’utilisation de PowerShell, voir [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="21f54-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="21f54-110">Nous vous conseillons de vérifier que votre SBC a déjà été configuré comme recommandé par votre fournisseur de SBC :</span><span class="sxs-lookup"><span data-stu-id="21f54-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="21f54-111">Documentation de déploiement AudioCodes</span><span class="sxs-lookup"><span data-stu-id="21f54-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="21f54-112">Documentation relative au déploiement d’Oracle</span><span class="sxs-lookup"><span data-stu-id="21f54-112">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="21f54-113">Documentation sur le déploiement des communications du ruban</span><span class="sxs-lookup"><span data-stu-id="21f54-113">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="21f54-114">Documentation sur le déploiement de TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="21f54-114">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="21f54-115">Vous pouvez configurer votre système Microsoft Phone et permettre aux utilisateurs d’utiliser le routage direct, puis configurer Microsoft teams en tant que client appelant préféré en exécutant les procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="21f54-115">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="21f54-116">Coupler une SBC avec un système Microsoft Phone et valider le jumelage</span><span class="sxs-lookup"><span data-stu-id="21f54-116">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [<span data-ttu-id="21f54-117">Activer les utilisateurs pour le service de routage direct</span><span class="sxs-lookup"><span data-stu-id="21f54-117">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- <span data-ttu-id="21f54-118">Vérifiez que Microsoft teams est le client appelant préféré pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="21f54-118">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="21f54-119">Coupler l’SBC au service de routage direct du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="21f54-119">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="21f54-120">Voici les trois principales étapes pour vous permettre de vous connecter, ou jumeler, l’interface SBC à l’interface de routage directe :</span><span class="sxs-lookup"><span data-stu-id="21f54-120">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="21f54-121">Se connecter au centre **d’administration de Skype entreprise Online** à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="21f54-121">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="21f54-122">Coupler l’SBC</span><span class="sxs-lookup"><span data-stu-id="21f54-122">Pair the SBC</span></span> 
- <span data-ttu-id="21f54-123">Valider le jumelage</span><span class="sxs-lookup"><span data-stu-id="21f54-123">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="21f54-124">Se connecter à Skype entreprise Online à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="21f54-124">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="21f54-125">Vous pouvez utiliser une session PowerShell connectée au client pour jumeler l’interface SBC à l’interface de routage directe.</span><span class="sxs-lookup"><span data-stu-id="21f54-125">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="21f54-126">Pour ouvrir une session PowerShell, suivez les étapes décrites dans [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="21f54-126">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="21f54-127">Après avoir établi une session PowerShell distante, vérifiez que vous pouvez voir les commandes pour gérer l’SBC.</span><span class="sxs-lookup"><span data-stu-id="21f54-127">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="21f54-128">Pour valider les commandes, tapez ou copiez/collez les éléments suivants dans la session PowerShell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="21f54-128">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="21f54-129">Votre commande renverra les quatre fonctions indiquées ici pour vous permettre de gérer l’SBC.</span><span class="sxs-lookup"><span data-stu-id="21f54-129">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="21f54-130">Coupler l’SBC au client</span><span class="sxs-lookup"><span data-stu-id="21f54-130">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="21f54-131">Pour jumeler l’SBC au client, dans la session PowerShell, entrez ce qui suit, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="21f54-131">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="21f54-132">Nous vous recommandons vivement de définir une limite d’appels maximale dans l’SBC en utilisant les informations qui figurent dans la documentation de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="21f54-132">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="21f54-133">La limite déclenche une notification si l’SBC a le niveau de capacité.</span><span class="sxs-lookup"><span data-stu-id="21f54-133">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="21f54-134">Vous pouvez uniquement jumeler l’SBC si la partie Domain de son nom de domaine complet correspond à l’un des domaines inscrits \*dans votre client, à l’exception de. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="21f54-134">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="21f54-135">L' \*utilisation des noms de domaine. onmicrosoft.com n’est pas prise en charge pour le nom de domaine complet SBC.</span><span class="sxs-lookup"><span data-stu-id="21f54-135">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="21f54-136">Par exemple, si vous avez deux noms de domaine :</span><span class="sxs-lookup"><span data-stu-id="21f54-136">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="21f54-137">**contoso**. com</span><span class="sxs-lookup"><span data-stu-id="21f54-137">**contoso**.com</span></span><br/><span data-ttu-id="21f54-138">**contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="21f54-138">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="21f54-139">Pour le nom SBC, vous pouvez utiliser le nom sbc.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="21f54-139">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="21f54-140">Si vous essayez de jumeler l’SBC avec un nom SBC. contoso. ABC, le système ne vous en permettra pas, car le domaine n’est pas détenu par ce client.</span><span class="sxs-lookup"><span data-stu-id="21f54-140">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span><br/>
  > <span data-ttu-id="21f54-141">Outre le domaine enregistré dans votre client, il est important qu’il existe un utilisateur avec ce domaine et qu’une licence E3 ou E5 lui est affectée.</span><span class="sxs-lookup"><span data-stu-id="21f54-141">In addition to the domain registered in your tenant, it is important that there is a user with that domain and an assigned E3 or E5 license.</span></span> <span data-ttu-id="21f54-142">Si ce n’est pas le cas, vous recevez le message d’erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="21f54-142">If not, you will receive the following error:</span></span><br/>
  <span data-ttu-id="21f54-143">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span><span class="sxs-lookup"><span data-stu-id="21f54-143"></span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="21f54-144">Renvoie</span><span class="sxs-lookup"><span data-stu-id="21f54-144">Returns:</span></span>
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
<span data-ttu-id="21f54-145">Il existe d’autres options qui peuvent être définies lors du processus de jumelage.</span><span class="sxs-lookup"><span data-stu-id="21f54-145">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="21f54-146">Dans l’exemple précédent, seuls les paramètres minimum requis apparaissent.</span><span class="sxs-lookup"><span data-stu-id="21f54-146">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="21f54-147">Le tableau suivant répertorie les paramètres supplémentaires que vous pouvez utiliser pour ```New-CsOnlinePstnGateway```définir les paramètres.</span><span class="sxs-lookup"><span data-stu-id="21f54-147">The following table lists the additional parameters that you can use in setting parameters for ```New-CsOnlinePstnGateway```.</span></span>

|<span data-ttu-id="21f54-148">Obligatoire?</span><span class="sxs-lookup"><span data-stu-id="21f54-148">Required?</span></span>|<span data-ttu-id="21f54-149">Nom</span><span class="sxs-lookup"><span data-stu-id="21f54-149">Name</span></span>|<span data-ttu-id="21f54-150">Description</span><span class="sxs-lookup"><span data-stu-id="21f54-150">Description</span></span>|<span data-ttu-id="21f54-151">Par défaut</span><span class="sxs-lookup"><span data-stu-id="21f54-151">Default</span></span>|<span data-ttu-id="21f54-152">Valeurs possibles</span><span class="sxs-lookup"><span data-stu-id="21f54-152">Possible values</span></span>|<span data-ttu-id="21f54-153">Type et restrictions</span><span class="sxs-lookup"><span data-stu-id="21f54-153">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="21f54-154">Oui</span><span class="sxs-lookup"><span data-stu-id="21f54-154">Yes</span></span>|<span data-ttu-id="21f54-155">FQDN</span><span class="sxs-lookup"><span data-stu-id="21f54-155">FQDN</span></span>|<span data-ttu-id="21f54-156">Nom de domaine complet du SBC</span><span class="sxs-lookup"><span data-stu-id="21f54-156">The FQDN name of the SBC</span></span> |<span data-ttu-id="21f54-157">Aucun</span><span class="sxs-lookup"><span data-stu-id="21f54-157">None</span></span>|<span data-ttu-id="21f54-158">Nom NoneFQDN, limiter 63 caractères</span><span class="sxs-lookup"><span data-stu-id="21f54-158">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="21f54-159">Chaîne, liste de caractères autorisés et non autorisés sur [les conventions d’appellation dans Active Directory pour les ordinateurs, domaines, sites et UO](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="21f54-159">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="21f54-160">Non</span><span class="sxs-lookup"><span data-stu-id="21f54-160">No</span></span>|<span data-ttu-id="21f54-161">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="21f54-161">MediaBypass</span></span> |<span data-ttu-id="21f54-162">Le paramètre indiqué par l’élément SBC prend en charge la dérivation multimédia et l’administrateur veut l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="21f54-162">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="21f54-163">Aucun</span><span class="sxs-lookup"><span data-stu-id="21f54-163">None</span></span>|<span data-ttu-id="21f54-164">Vrai</span><span class="sxs-lookup"><span data-stu-id="21f54-164">True</span></span><br/><span data-ttu-id="21f54-165">False</span><span class="sxs-lookup"><span data-stu-id="21f54-165">False</span></span>|<span data-ttu-id="21f54-166">Boolean</span><span class="sxs-lookup"><span data-stu-id="21f54-166">Boolean</span></span>|
|<span data-ttu-id="21f54-167">Oui</span><span class="sxs-lookup"><span data-stu-id="21f54-167">Yes</span></span>|<span data-ttu-id="21f54-168">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="21f54-168">SipSignallingPort</span></span> |<span data-ttu-id="21f54-169">Port d’écoute utilisé pour la communication avec les services de routage directe à l’aide du protocole TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="21f54-169">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="21f54-170">Aucun</span><span class="sxs-lookup"><span data-stu-id="21f54-170">None</span></span>|<span data-ttu-id="21f54-171">Tout port</span><span class="sxs-lookup"><span data-stu-id="21f54-171">Any port</span></span>|<span data-ttu-id="21f54-172">entre 0 et 65535</span><span class="sxs-lookup"><span data-stu-id="21f54-172">0 to 65535</span></span> |
|<span data-ttu-id="21f54-173">Non</span><span class="sxs-lookup"><span data-stu-id="21f54-173">No</span></span>|<span data-ttu-id="21f54-174">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="21f54-174">FailoverTimeSeconds</span></span> |<span data-ttu-id="21f54-175">Lorsque la valeur est définie sur 10 (valeur par défaut), les appels sortants pour lesquels la passerelle ne répond pas dans un délai de 10 secondes sont routés vers le Trunk disponible suivant ; s’il n’y a pas de lignes supplémentaires, l’appel est automatiquement interrompu.</span><span class="sxs-lookup"><span data-stu-id="21f54-175">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="21f54-176">Dans une organisation avec des réponses de passerelle ou réseau lentes, cela peut entraîner l’abandon de nombreux appels.</span><span class="sxs-lookup"><span data-stu-id="21f54-176">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="21f54-177">La valeur par défaut est 10.</span><span class="sxs-lookup"><span data-stu-id="21f54-177">The default value is 10.</span></span>|<span data-ttu-id="21f54-178">0,10</span><span class="sxs-lookup"><span data-stu-id="21f54-178">10</span></span>|<span data-ttu-id="21f54-179">Numéro</span><span class="sxs-lookup"><span data-stu-id="21f54-179">Number</span></span>|<span data-ttu-id="21f54-180">Ent</span><span class="sxs-lookup"><span data-stu-id="21f54-180">Int</span></span>|
|<span data-ttu-id="21f54-181">Non</span><span class="sxs-lookup"><span data-stu-id="21f54-181">No</span></span>|<span data-ttu-id="21f54-182">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="21f54-182">ForwardCallHistory</span></span> |<span data-ttu-id="21f54-183">Indique si les informations d’historique d’appel sont transférées par le biais de la jonction.</span><span class="sxs-lookup"><span data-stu-id="21f54-183">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="21f54-184">Si cette option est activée, le Proxy RTC Office 365 envoie deux en-têtes : History-Info et expertisé.</span><span class="sxs-lookup"><span data-stu-id="21f54-184">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="21f54-185">La valeur par défaut est **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="21f54-185">The default value is **False** ($False).</span></span> |<span data-ttu-id="21f54-186">False</span><span class="sxs-lookup"><span data-stu-id="21f54-186">False</span></span>|<span data-ttu-id="21f54-187">Vrai</span><span class="sxs-lookup"><span data-stu-id="21f54-187">True</span></span><br/><span data-ttu-id="21f54-188">False</span><span class="sxs-lookup"><span data-stu-id="21f54-188">False</span></span>|<span data-ttu-id="21f54-189">Boolean</span><span class="sxs-lookup"><span data-stu-id="21f54-189">Boolean</span></span>|
|<span data-ttu-id="21f54-190">Non</span><span class="sxs-lookup"><span data-stu-id="21f54-190">No</span></span>|<span data-ttu-id="21f54-191">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="21f54-191">ForwardPAI</span></span>|<span data-ttu-id="21f54-192">Indique si l’en-tête P-Asserted-Identity (PAI) sera transféré avec l’appel.</span><span class="sxs-lookup"><span data-stu-id="21f54-192">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="21f54-193">L’en-tête PAI permet de vérifier l’identité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="21f54-193">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="21f54-194">Si vous avez activé l’en-tête d’ID vie privée : il est également envoyé.</span><span class="sxs-lookup"><span data-stu-id="21f54-194">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="21f54-195">La valeur par défaut est **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="21f54-195">The default value is **False** ($False).</span></span>|<span data-ttu-id="21f54-196">False</span><span class="sxs-lookup"><span data-stu-id="21f54-196">False</span></span>|<span data-ttu-id="21f54-197">Vrai</span><span class="sxs-lookup"><span data-stu-id="21f54-197">True</span></span><br/><span data-ttu-id="21f54-198">False</span><span class="sxs-lookup"><span data-stu-id="21f54-198">False</span></span>|<span data-ttu-id="21f54-199">Boolean</span><span class="sxs-lookup"><span data-stu-id="21f54-199">Boolean</span></span>|
|<span data-ttu-id="21f54-200">Non</span><span class="sxs-lookup"><span data-stu-id="21f54-200">No</span></span>|<span data-ttu-id="21f54-201">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="21f54-201">SendSIPOptions</span></span> |<span data-ttu-id="21f54-202">Définit si une SBC va ou non envoyer les options SIP.</span><span class="sxs-lookup"><span data-stu-id="21f54-202">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="21f54-203">S’il est désactivé, l’SBC sera exclu du système de surveillance et d’alerte.</span><span class="sxs-lookup"><span data-stu-id="21f54-203">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="21f54-204">Nous vous recommandons vivement d’activer les options SIP.</span><span class="sxs-lookup"><span data-stu-id="21f54-204">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="21f54-205">La valeur par défaut est **true**.</span><span class="sxs-lookup"><span data-stu-id="21f54-205">Default value is **True**.</span></span> |<span data-ttu-id="21f54-206">Vrai</span><span class="sxs-lookup"><span data-stu-id="21f54-206">True</span></span>|<span data-ttu-id="21f54-207">Vrai</span><span class="sxs-lookup"><span data-stu-id="21f54-207">True</span></span><br/><span data-ttu-id="21f54-208">False</span><span class="sxs-lookup"><span data-stu-id="21f54-208">False</span></span>|<span data-ttu-id="21f54-209">Boolean</span><span class="sxs-lookup"><span data-stu-id="21f54-209">Boolean</span></span>|
|<span data-ttu-id="21f54-210">Non</span><span class="sxs-lookup"><span data-stu-id="21f54-210">No</span></span>|<span data-ttu-id="21f54-211">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="21f54-211">MaxConcurrentSessions</span></span> |<span data-ttu-id="21f54-212">Utilisé par le système d’alerte.</span><span class="sxs-lookup"><span data-stu-id="21f54-212">Used by alerting system.</span></span> <span data-ttu-id="21f54-213">Lorsque n’importe quelle valeur est définie, le système d’alerte génère une alerte auprès de l’administrateur client lorsque le nombre de sessions simultanées est 90% ou une valeur supérieure à celle-ci.</span><span class="sxs-lookup"><span data-stu-id="21f54-213">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="21f54-214">Si paramètre n’est pas défini, les alertes ne le sont pas.</span><span class="sxs-lookup"><span data-stu-id="21f54-214">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="21f54-215">Toutefois, le système de surveillance rapportera le nombre de sessions simultanées toutes les 24 heures.</span><span class="sxs-lookup"><span data-stu-id="21f54-215">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="21f54-216">Valeur</span><span class="sxs-lookup"><span data-stu-id="21f54-216">Null</span></span>|<span data-ttu-id="21f54-217">Valeur</span><span class="sxs-lookup"><span data-stu-id="21f54-217">Null</span></span><br/><span data-ttu-id="21f54-218">1 à 100 000</span><span class="sxs-lookup"><span data-stu-id="21f54-218">1 to 100,000</span></span> ||
|<span data-ttu-id="21f54-219">Non</span><span class="sxs-lookup"><span data-stu-id="21f54-219">No</span></span>|<span data-ttu-id="21f54-220">MediaRelayRoutingLocationOverride</span><span class="sxs-lookup"><span data-stu-id="21f54-220">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="21f54-221">Permet de sélectionner manuellement le chemin pour le média.</span><span class="sxs-lookup"><span data-stu-id="21f54-221">Allows selecting path for media manually.</span></span> <span data-ttu-id="21f54-222">Le routage direct affecte un centre de contenus multimédia pour le chemin multimédia en fonction de l’adresse IP publique de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="21f54-222">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="21f54-223">Nous cherchons toujours le plus près du centre de centres SBC.</span><span class="sxs-lookup"><span data-stu-id="21f54-223">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="21f54-224">Toutefois, dans certains cas, il est possible d’attribuer une adresse IP publique de la part d’une SBC située en Europe, par exemple.</span><span class="sxs-lookup"><span data-stu-id="21f54-224">However, in some cases a public IP from for example a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="21f54-225">Dans ce cas, nous n’utiliserons pas le chemin multimédia.</span><span class="sxs-lookup"><span data-stu-id="21f54-225">In this case we will be using not optimal media path.</span></span> <span data-ttu-id="21f54-226">Ce paramètre permet de définir manuellement la région préférée pour le trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="21f54-226">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="21f54-227">Nous vous conseillons de définir ce paramètre uniquement si les journaux d’appels indiquent clairement que l’attribution automatique du centre de fichiers de média pour le chemin multimédia n’affecte pas le plus proche au centre de médias SBC.</span><span class="sxs-lookup"><span data-stu-id="21f54-227">We only recommend setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="21f54-228">Aucun</span><span class="sxs-lookup"><span data-stu-id="21f54-228">None</span></span>|<span data-ttu-id="21f54-229">Codes de pays au format ISO</span><span class="sxs-lookup"><span data-stu-id="21f54-229">Country codes in ISO format</span></span>||
|<span data-ttu-id="21f54-230">Non</span><span class="sxs-lookup"><span data-stu-id="21f54-230">No</span></span>|<span data-ttu-id="21f54-231">Activé</span><span class="sxs-lookup"><span data-stu-id="21f54-231">Enabled</span></span>|<span data-ttu-id="21f54-232">Utilisé pour activer cet SBC pour les appels sortants.</span><span class="sxs-lookup"><span data-stu-id="21f54-232">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="21f54-233">Peut être utilisé pour supprimer temporairement l’SBC, pendant sa mise à jour ou lors de la maintenance.</span><span class="sxs-lookup"><span data-stu-id="21f54-233">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="21f54-234">False</span><span class="sxs-lookup"><span data-stu-id="21f54-234">False</span></span>|<span data-ttu-id="21f54-235">Vrai</span><span class="sxs-lookup"><span data-stu-id="21f54-235">True</span></span><br/><span data-ttu-id="21f54-236">False</span><span class="sxs-lookup"><span data-stu-id="21f54-236">False</span></span>|<span data-ttu-id="21f54-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="21f54-237">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="21f54-238">Vérifier le jumelage des SBC</span><span class="sxs-lookup"><span data-stu-id="21f54-238">Verify the SBC pairing</span></span> 

<span data-ttu-id="21f54-239">Vérifiez la connexion :</span><span class="sxs-lookup"><span data-stu-id="21f54-239">Verify the connection:</span></span> 
- <span data-ttu-id="21f54-240">Vérifiez si la SBC est sur la liste de SBCs couplés.</span><span class="sxs-lookup"><span data-stu-id="21f54-240">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="21f54-241">Valider les options SIP.</span><span class="sxs-lookup"><span data-stu-id="21f54-241">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="21f54-242">Vérifier si la SBC est sur la liste de SBCs couplés</span><span class="sxs-lookup"><span data-stu-id="21f54-242">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="21f54-243">Une fois que vous avez couplé l’SBC, validez la présence de l’SBC dans la liste des éléments SBCs couplés en exécutant la commande suivante dans une session PowerShell distante :`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="21f54-243">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="21f54-244">La passerelle couplée doit apparaître dans la liste, comme illustré dans l’exemple ci-dessous, et vérifier que le paramètre **Enabled** affiche la valeur **true**.</span><span class="sxs-lookup"><span data-stu-id="21f54-244">The paired gateway should appear in the list as shown in the example below, and verify that the **Enabled** parameter  displays a value of **True**.</span></span> <span data-ttu-id="21f54-245">Spécifi</span><span class="sxs-lookup"><span data-stu-id="21f54-245">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="21f54-246">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="21f54-246">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="21f54-247">Valider le flux d’options SIP</span><span class="sxs-lookup"><span data-stu-id="21f54-247">Validate SIP Options flow</span></span> 

<span data-ttu-id="21f54-248">Pour valider le jumelage à l’aide des options SIP sortants, utilisez l’interface de gestion des SBC et confirmez que l’SBC reçoit les réponses 200 OK à ses messages d’OPTIONS sortants.</span><span class="sxs-lookup"><span data-stu-id="21f54-248">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="21f54-249">Lorsque le routage direct voit les OPTIONS entrantes, il commence à envoyer des messages d’options SIP sortants au nom de domaine complet SBC configuré dans le champ d’en-tête de contact du message OPTIONS entrantes.</span><span class="sxs-lookup"><span data-stu-id="21f54-249">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="21f54-250">Pour valider le jumelage à l’aide des options SIP entrantes, utilisez l’interface de gestion des SBC et voyez que l’SBC envoie une réponse aux messages d’OPTIONS provenant du routage direct et que le code de réponse qu’il envoie est 200 OK.</span><span class="sxs-lookup"><span data-stu-id="21f54-250">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="21f54-251">Activer les utilisateurs pour le service de routage direct</span><span class="sxs-lookup"><span data-stu-id="21f54-251">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="21f54-252">Lorsque vous êtes prêt à activer les utilisateurs pour le service de routage direct, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="21f54-252">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="21f54-253">Créez un utilisateur dans Office 365 et attribuez une licence de système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="21f54-253">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="21f54-254">Assurez-vous que l’utilisateur est bien immobilier dans Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="21f54-254">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="21f54-255">Configurez le numéro de téléphone et activez voix entreprise et boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="21f54-255">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="21f54-256">Configurer le routage de la voix.</span><span class="sxs-lookup"><span data-stu-id="21f54-256">Configure voice routing.</span></span> <span data-ttu-id="21f54-257">L’itinéraire est validé automatiquement.</span><span class="sxs-lookup"><span data-stu-id="21f54-257">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="21f54-258">Créer un utilisateur dans Office 365 et affecter la licence</span><span class="sxs-lookup"><span data-stu-id="21f54-258">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="21f54-259">Deux options s’offrent à vous pour créer un utilisateur dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="21f54-259">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="21f54-260">Toutefois, nous recommandons que votre organisation sélectionne et utilise une option pour éviter les problèmes de routage :</span><span class="sxs-lookup"><span data-stu-id="21f54-260">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="21f54-261">Créer l’utilisateur dans l’annuaire Active Directory local et synchroniser l’utilisateur avec le Cloud.</span><span class="sxs-lookup"><span data-stu-id="21f54-261">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="21f54-262">Voir [intégrer vos annuaires locaux avec Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="21f54-262">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="21f54-263">Créer l’utilisateur directement dans le portail d’administration Office 365.</span><span class="sxs-lookup"><span data-stu-id="21f54-263">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="21f54-264">Pour plus d' [informations, voir ajouter des utilisateurs individuellement ou en bloc à Office 365-aide de l’administrateur](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="21f54-264">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="21f54-265">Si votre déploiement de Skype entreprise Online co-existe avec Skype entreprise 2015 ou Lync 2010/2013 local, la seule option prise en charge consiste à créer l’utilisateur dans Active Directory local et à synchroniser l’utilisateur dans le Cloud (option 1).</span><span class="sxs-lookup"><span data-stu-id="21f54-265">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="21f54-266">Licences requises :</span><span class="sxs-lookup"><span data-stu-id="21f54-266">Required licenses:</span></span> 

- <span data-ttu-id="21f54-267">Office 365 entreprise E3 (y compris marketing Plan2, Exchange Plan2 et Teams) + Téléphone</span><span class="sxs-lookup"><span data-stu-id="21f54-267">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="21f54-268">Office 365 entreprise E5 (y compris marketing Plan2, Exchange Plan2, équipes et système téléphonique)</span><span class="sxs-lookup"><span data-stu-id="21f54-268">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="21f54-269">Licences facultatives :</span><span class="sxs-lookup"><span data-stu-id="21f54-269">Optional licenses:</span></span> 

- <span data-ttu-id="21f54-270">Forfait d’appels</span><span class="sxs-lookup"><span data-stu-id="21f54-270">Calling Plan</span></span> 
- <span data-ttu-id="21f54-271">Audioconférence,</span><span class="sxs-lookup"><span data-stu-id="21f54-271">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="21f54-272">Vérifier que l’utilisateur est bien immobilier dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="21f54-272">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="21f54-273">Le routage direct nécessite que l’utilisateur soit hébergé dans Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="21f54-273">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="21f54-274">Pour cela, vous pouvez consulter le paramètre RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="21f54-274">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="21f54-275">Il doit avoir une valeur dans le domaine infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="21f54-275">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="21f54-276">Connectez-vous à Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21f54-276">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="21f54-277">Émettez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="21f54-277">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="21f54-278">Configuration du numéro de téléphone et activation de la voix et de la boîte vocale entreprise</span><span class="sxs-lookup"><span data-stu-id="21f54-278">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="21f54-279">Une fois que vous avez créé l’utilisateur et attribué une licence, l’étape suivante consiste à configurer son numéro de téléphone et sa boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="21f54-279">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="21f54-280">Cette opération peut être réalisée en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="21f54-280">This can be done in one step.</span></span> 

<span data-ttu-id="21f54-281">Pour ajouter le numéro de téléphone et l’activer pour la boîte vocale, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="21f54-281">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="21f54-282">Se connecter à une session PowerShell distante.</span><span class="sxs-lookup"><span data-stu-id="21f54-282">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="21f54-283">Entrez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="21f54-283">Enter the command:</span></span> 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="21f54-284">Par exemple, pour ajouter un numéro de téléphone pour l’utilisateur « Beaune Low », entrez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="21f54-284">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="21f54-285">Le numéro de téléphone utilisé doit être configuré en tant que numéro de téléphone avec l’indicatif du pays.</span><span class="sxs-lookup"><span data-stu-id="21f54-285">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="21f54-286">Si le numéro de téléphone de l’utilisateur est géré en local, utilisez l’interpréteur de commandes ou le panneau de configuration Skype entreprise local pour configurer le numéro de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="21f54-286">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="21f54-287">Configurer le routage de la voix</span><span class="sxs-lookup"><span data-stu-id="21f54-287">Configure Voice Routing</span></span> 

<span data-ttu-id="21f54-288">Le système Microsoft Phone possède un mécanisme de routage qui permet d’envoyer un appel à un SBC spécifique en fonction de :</span><span class="sxs-lookup"><span data-stu-id="21f54-288">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="21f54-289">Modèle de nombre appelé</span><span class="sxs-lookup"><span data-stu-id="21f54-289">Called number pattern</span></span> 
- <span data-ttu-id="21f54-290">Appel de modèle de numéro + utilisateur spécifique qui effectue l’appel</span><span class="sxs-lookup"><span data-stu-id="21f54-290">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="21f54-291">SBCs peut être désignée comme active et Backup.</span><span class="sxs-lookup"><span data-stu-id="21f54-291">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="21f54-292">Cela signifie que lorsque l’SBC configuré comme étant actif pour ce modèle de nombre, ou un modèle de nombre (utilisateur spécifique) n’est pas disponible, les appels sont dirigés vers un SBC de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="21f54-292">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="21f54-293">Le routage des appels se compose des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="21f54-293">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="21f54-294">Politique de routage de la voix-conteneur d’utilisation PSTN ; peuvent être affectés à un utilisateur ou à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="21f54-294">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="21f54-295">Usages PSTN : conteneur des itinéraires vocaux et des utilisations PSTN ; peuvent être partagés dans différentes politiques de routage vocal</span><span class="sxs-lookup"><span data-stu-id="21f54-295">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="21f54-296">Itinéraires vocaux : modèle numérique et ensemble de passerelles RTC en ligne à utiliser pour les appels dans lesquels le numéro de téléphone correspond au modèle</span><span class="sxs-lookup"><span data-stu-id="21f54-296">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="21f54-297">Passerelle RTC en ligne-pointeur vers une SBC, qui stocke également la configuration appliquée lors de l’appel via SBC, telle que l’envoi d’identité P-assertion (PAI) ou de codecs préférés. peuvent être ajoutés aux itinéraires vocaux</span><span class="sxs-lookup"><span data-stu-id="21f54-297">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="21f54-298">Création d’une stratégie de routage de la voix avec une utilisation PSTN</span><span class="sxs-lookup"><span data-stu-id="21f54-298">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="21f54-299">Le schéma suivant montre deux exemples de stratégies de routage de voix dans le flux d’appels.</span><span class="sxs-lookup"><span data-stu-id="21f54-299">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="21f54-300">**Flux d’appels 1 (à gauche) :** Si un utilisateur effectue un appel vers + 1 425 XXX XX XX ou + 1 206 XXX XX XX, l’appel est acheminé vers SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="21f54-300">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="21f54-301">Si les sbc1.contoso.biz et sbc2.contoso.biz ne sont pas disponibles, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="21f54-301">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="21f54-302">**Flux d’appels 2 (sur la droite) :** Si un utilisateur effectue un appel vers + 1 425 XX XX XX ou + 1 206 XXX XX XX, l’appel est d’abord routé vers SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="21f54-302">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="21f54-303">Si aucun SBC n’est disponible, l’itinéraire dont la priorité est faible est essayé (sbc3.contoso.biz et sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="21f54-303">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="21f54-304">Si aucune des SBCs n’est disponible, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="21f54-304">If none of the SBCs are available, the call is dropped.</span></span> 

![Exemples de stratégies de routage vocale](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="21f54-306">Dans les deux exemples, si les priorités de l’itinéraire vocal sont affectées, les éléments SBCs dans les itinéraires sont essayés dans un ordre aléatoire.</span><span class="sxs-lookup"><span data-stu-id="21f54-306">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="21f54-307">À moins que l’utilisateur ne dispose d’une licence de plan d’appel Microsoft, les appels vers n’importe quel numéro, à l’exception des numéros correspondant aux modèles + 1 425 XXX XX XX ou + 1 206 XXX XX XX dans l’exemple de configuration sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="21f54-307">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="21f54-308">Si l’utilisateur dispose d’une licence de plan d’appel, l’appel est automatiquement acheminé conformément aux politiques du forfait d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="21f54-308">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="21f54-309">Le plan d’appel Microsoft s’applique automatiquement en tant que dernier itinéraire à tous les utilisateurs dotés de la licence de plan d’appel Microsoft et ne nécessite pas de configuration du routage des appels supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="21f54-309">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="21f54-310">Dans l’exemple ci-dessous, un itinéraire vocal est ajouté pour envoyer les appels vers tous les autres États-Unis et le numéro canadien (appels vers le modèle de numéro + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="21f54-310">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Affiche la politique de routage téléphonique avec un troisième itinéraire](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="21f54-312">Pour tous les autres appels, si un utilisateur possède les deux licences (système Microsoft Phone et forfait d’appel Microsoft), un itinéraire automatique est utilisé.</span><span class="sxs-lookup"><span data-stu-id="21f54-312">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="21f54-313">S’il ne correspond pas aux modèles de nombre dans les itinéraires vocaux en ligne créés par l’administrateur, route via un forfait d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="21f54-313">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="21f54-314">Si l’utilisateur dispose uniquement du système Microsoft Phone, l’appel est abandonné, car aucune règle de correspondance n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="21f54-314">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="21f54-315">La valeur de priorité pour l’itinéraire « Other + 1 » n’a pas d’importance dans ce cas, car il n’y a qu’un seul itinéraire correspondant au modèle + 1 XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="21f54-315">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="21f54-316">Si un utilisateur effectue un appel à + 1 324 567 89 89 et que les sbc5.contoso.biz et sbc6.contoso.biz ne sont pas disponibles, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="21f54-316">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="21f54-317">Le tableau suivant résume la configuration à l’aide de trois itinéraires vocaux.</span><span class="sxs-lookup"><span data-stu-id="21f54-317">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="21f54-318">Dans cet exemple, les trois itinéraires font partie de la même utilisation PSTN « États-Unis et Canada ».</span><span class="sxs-lookup"><span data-stu-id="21f54-318">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="21f54-319">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="21f54-319">**PSTN usage**</span></span>|<span data-ttu-id="21f54-320">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="21f54-320">**Voice route**</span></span>|<span data-ttu-id="21f54-321">**Schéma de numéro**</span><span class="sxs-lookup"><span data-stu-id="21f54-321">**Number pattern**</span></span>|<span data-ttu-id="21f54-322">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="21f54-322">**Priority**</span></span>|<span data-ttu-id="21f54-323">**SBC**</span><span class="sxs-lookup"><span data-stu-id="21f54-323">**SBC**</span></span>|<span data-ttu-id="21f54-324">**Description**</span><span class="sxs-lookup"><span data-stu-id="21f54-324">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="21f54-325">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="21f54-325">US only</span></span>|<span data-ttu-id="21f54-326">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="21f54-326">"Redmond 1"</span></span>|<span data-ttu-id="21f54-327">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="21f54-327">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="21f54-328">1</span><span class="sxs-lookup"><span data-stu-id="21f54-328">1</span></span>|<span data-ttu-id="21f54-329">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="21f54-329">sbc1.contoso.biz</span></span><br/><span data-ttu-id="21f54-330">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="21f54-330">sbc2.contoso.biz</span></span>|<span data-ttu-id="21f54-331">Itinéraire actif pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="21f54-331">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="21f54-332">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="21f54-332">US only</span></span>|<span data-ttu-id="21f54-333">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="21f54-333">"Redmond 2"</span></span>|<span data-ttu-id="21f54-334">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="21f54-334">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="21f54-335">deuxième</span><span class="sxs-lookup"><span data-stu-id="21f54-335">2</span></span>|<span data-ttu-id="21f54-336">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="21f54-336">sbc3.contoso.biz</span></span><br/><span data-ttu-id="21f54-337">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="21f54-337">sbc4.contoso.biz</span></span>|<span data-ttu-id="21f54-338">Itinéraire de sauvegarde pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="21f54-338">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="21f54-339">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="21f54-339">US only</span></span>|<span data-ttu-id="21f54-340">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="21f54-340">"Other +1"</span></span>|<span data-ttu-id="21f54-341">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="21f54-341">^\\+1(\d{10})$</span></span>|<span data-ttu-id="21f54-342">3</span><span class="sxs-lookup"><span data-stu-id="21f54-342">3</span></span>|<span data-ttu-id="21f54-343">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="21f54-343">sbc5.contoso.biz</span></span><br/><span data-ttu-id="21f54-344">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="21f54-344">sbc6.contoso.biz</span></span>|<span data-ttu-id="21f54-345">Itinéraire pour les numéros appelés + 1 XXX XXX XX XX (sauf + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="21f54-345">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="21f54-346">Tous les itinéraires sont associés à l’utilisation RTC « États-Unis et Canada » et l’utilisation RTC est associée à la politique de routage de la voix « États-Unis uniquement ».</span><span class="sxs-lookup"><span data-stu-id="21f54-346">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="21f54-347">Dans cet exemple, la stratégie de routage de la voix est affectée à user Spencer Low.</span><span class="sxs-lookup"><span data-stu-id="21f54-347">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="21f54-348">Exemples d’itinéraires d’appels</span><span class="sxs-lookup"><span data-stu-id="21f54-348">Examples of call routes</span></span>

<span data-ttu-id="21f54-349">Dans l’exemple suivant, nous montrons comment configurer des itinéraires, des utilisations RTC et des stratégies de routage, et nous affectons la stratégie à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="21f54-349">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="21f54-350">**Étape 1 :** Créez l’utilisation RTC « États-Unis et Canada ».</span><span class="sxs-lookup"><span data-stu-id="21f54-350">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="21f54-351">Dans une session PowerShell distante Skype entreprise, tapez :</span><span class="sxs-lookup"><span data-stu-id="21f54-351">In a Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="21f54-352">Vérifiez que l’utilisation a été créée en entrant :</span><span class="sxs-lookup"><span data-stu-id="21f54-352">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="21f54-353">Qui renvoie une liste de noms qui risquent d’être tronqués :</span><span class="sxs-lookup"><span data-stu-id="21f54-353">Which returns a list of names that may be truncated:</span></span>
```
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="21f54-354">Dans l’exemple ci-dessous, vous pouvez voir le résultat de l’exécution de `(Get-CSOnlinePSTNUsage).usage` la commande PowerShell pour afficher les noms complets (sans troncature).</span><span class="sxs-lookup"><span data-stu-id="21f54-354">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span>

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

<span data-ttu-id="21f54-355">**Étape 2 :** Dans une session PowerShell dans Skype entreprise Online, créez trois itinéraires : Redmond 1, Redmond 2 et autres + 1, comme décrit dans le tableau précédent.</span><span class="sxs-lookup"><span data-stu-id="21f54-355">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="21f54-356">Pour créer l’itinéraire « Redmond 1 », entrez :</span><span class="sxs-lookup"><span data-stu-id="21f54-356">To create the "Redmond 1" route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="21f54-357">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="21f54-357">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
<span data-ttu-id="21f54-358">Pour créer l’itinéraire de Redmond 2, entrez :</span><span class="sxs-lookup"><span data-stu-id="21f54-358">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="21f54-359">Pour créer l’autre itinéraire + 1, entrez :</span><span class="sxs-lookup"><span data-stu-id="21f54-359">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="21f54-360">Assurez-vous que votre expression régulière dans l’attribut NumberPattern est une expression valide.</span><span class="sxs-lookup"><span data-stu-id="21f54-360">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="21f54-361">Vous pouvez le tester à l’aide du site Web suivant :[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="21f54-361">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="21f54-362">Dans certains cas, il est nécessaire de router tous les appels vers le même SBC ; Utilisez-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="21f54-362">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

<span data-ttu-id="21f54-363">Acheminez tous les appels vers le même SBC.</span><span class="sxs-lookup"><span data-stu-id="21f54-363">Route all calls to same SBC.</span></span>

```
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="21f54-364">Vérifiez que vous avez correctement configuré l’itinéraire en exécutant la `Get-CSOnlineVoiceRoute` commande PowerShell en utilisant les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="21f54-364">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="21f54-365">Qui doit retourner :</span><span class="sxs-lookup"><span data-stu-id="21f54-365">Which should return:</span></span>
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

<span data-ttu-id="21f54-366">Dans l’exemple, l’itinéraire « Other + 1 » a automatiquement la priorité 4.</span><span class="sxs-lookup"><span data-stu-id="21f54-366">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="21f54-367">**Étape 3 :** Créez une stratégie de routage de la voix « États-Unis uniquement » et ajoutez-la à la politique « États-Unis et Canada ».</span><span class="sxs-lookup"><span data-stu-id="21f54-367">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="21f54-368">Dans une session PowerShell dans Skype entreprise Online, tapez :</span><span class="sxs-lookup"><span data-stu-id="21f54-368">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="21f54-369">Le résultat est affiché dans cet exemple :</span><span class="sxs-lookup"><span data-stu-id="21f54-369">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="21f54-370">**Étape 4 :** Accordez à l’utilisateur la politique de routage de la voix de faible utilisation par PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21f54-370">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

<span data-ttu-id="21f54-371">Dans une session PowerShell dans Skype entreprise Online, tapez :</span><span class="sxs-lookup"><span data-stu-id="21f54-371">In a PowerShell session in Skype for Business Online, type:</span></span>

```
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="21f54-372">Validez l’affectation de stratégie en entrant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="21f54-372">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="21f54-373">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="21f54-373">Which returns:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="21f54-374">Création d’une stratégie de routage de la voix avec plusieurs utilisations PSTN</span><span class="sxs-lookup"><span data-stu-id="21f54-374">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="21f54-375">La politique de routage vocale créée auparavant n’autorise que les appels vers des numéros de téléphone aux États-Unis et au Canada, sauf si la licence de plan d’appel Microsoft est également affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="21f54-375">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="21f54-376">Dans l’exemple qui suit, vous pouvez créer la stratégie de routage téléphonique « aucune restriction ».</span><span class="sxs-lookup"><span data-stu-id="21f54-376">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="21f54-377">La stratégie réutilise l’utilisation RTC « États-Unis et Canada » créée dans l’exemple précédent, ainsi que la nouvelle utilisation RTC « international ».</span><span class="sxs-lookup"><span data-stu-id="21f54-377">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="21f54-378">Cela achemine tous les autres appels vers l’SBCs sbc2.contoso.biz et sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="21f54-378">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="21f54-379">Les exemples qui s’affichent affectent la politique américaine uniquement à l’utilisateur « Beaune Low » et aucune restriction à l’utilisateur « Jean bois ».</span><span class="sxs-lookup"><span data-stu-id="21f54-379">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="21f54-380">Spencer Low – appels uniquement autorisés vers les États-Unis et le Canada.</span><span class="sxs-lookup"><span data-stu-id="21f54-380">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="21f54-381">Lorsque vous appelez la gamme de numéros Redmond, l’ensemble spécifique de SBC doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="21f54-381">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="21f54-382">Les numéros non US ne seront pas routés sauf si la licence de plan d’appel est affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="21f54-382">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="21f54-383">Jean bois – appels autorisés vers n’importe quel numéro.</span><span class="sxs-lookup"><span data-stu-id="21f54-383">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="21f54-384">Lorsque vous appelez la gamme de numéros Redmond, l’ensemble spécifique de SBC doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="21f54-384">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="21f54-385">Les numéros non US seront routés par le biais de sbc2.contoso.biz et sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="21f54-385">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Affiche la politique de routage vocale affectée à l’utilisateur Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="21f54-387">Pour tous les autres appels, si un utilisateur possède les deux licences (système Microsoft Phone et forfait d’appel Microsoft), un itinéraire automatique est utilisé.</span><span class="sxs-lookup"><span data-stu-id="21f54-387">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="21f54-388">S’il ne correspond pas aux modèles de nombre dans les itinéraires vocaux en ligne créés par l’administrateur, route via un forfait d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="21f54-388">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="21f54-389">Si l’utilisateur dispose uniquement du système Microsoft Phone, l’appel est abandonné, car aucune règle de correspondance n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="21f54-389">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Politique de routage de la voix attribuée à l’utilisateur Jean bois](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="21f54-391">Le tableau suivant récapitule les concepteurs d’utilisation et les itinéraires vocaux de la stratégie de routage « aucune restriction ».</span><span class="sxs-lookup"><span data-stu-id="21f54-391">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="21f54-392">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="21f54-392">**PSTN usage**</span></span>|<span data-ttu-id="21f54-393">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="21f54-393">**Voice route**</span></span>|<span data-ttu-id="21f54-394">**Schéma de numéro**</span><span class="sxs-lookup"><span data-stu-id="21f54-394">**Number pattern**</span></span>|<span data-ttu-id="21f54-395">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="21f54-395">**Priority**</span></span>|<span data-ttu-id="21f54-396">**SBC**</span><span class="sxs-lookup"><span data-stu-id="21f54-396">**SBC**</span></span>|<span data-ttu-id="21f54-397">**Description**</span><span class="sxs-lookup"><span data-stu-id="21f54-397">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="21f54-398">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="21f54-398">US Only</span></span>|<span data-ttu-id="21f54-399">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="21f54-399">"Redmond 1"</span></span>|<span data-ttu-id="21f54-400">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="21f54-400">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="21f54-401">1</span><span class="sxs-lookup"><span data-stu-id="21f54-401">1</span></span>|<span data-ttu-id="21f54-402">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="21f54-402">sbc1.contoso.biz</span></span><br/><span data-ttu-id="21f54-403">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="21f54-403">sbc2.contoso.biz</span></span>|<span data-ttu-id="21f54-404">Itinéraire actif pour les numéros d’appelant + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="21f54-404">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="21f54-405">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="21f54-405">US Only</span></span>|<span data-ttu-id="21f54-406">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="21f54-406">"Redmond 2"</span></span>|<span data-ttu-id="21f54-407">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="21f54-407">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="21f54-408">deuxième</span><span class="sxs-lookup"><span data-stu-id="21f54-408">2</span></span>|<span data-ttu-id="21f54-409">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="21f54-409">sbc3.contoso.biz</span></span><br/><span data-ttu-id="21f54-410">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="21f54-410">sbc4.contoso.biz</span></span>|<span data-ttu-id="21f54-411">Itinéraire de sauvegarde pour les numéros des appelants + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="21f54-411">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="21f54-412">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="21f54-412">US Only</span></span>|<span data-ttu-id="21f54-413">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="21f54-413">"Other +1"</span></span>|<span data-ttu-id="21f54-414">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="21f54-414">^\\+1(\d{10})$</span></span>|<span data-ttu-id="21f54-415">3</span><span class="sxs-lookup"><span data-stu-id="21f54-415">3</span></span>|<span data-ttu-id="21f54-416">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="21f54-416">sbc5.contoso.biz</span></span><br/><span data-ttu-id="21f54-417">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="21f54-417">sbc6>.contoso.biz</span></span>|<span data-ttu-id="21f54-418">Itinéraire pour les numéros d’appelant + 1 XXX XXX XX XX (sauf + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="21f54-418">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="21f54-419">International</span><span class="sxs-lookup"><span data-stu-id="21f54-419">International</span></span>|<span data-ttu-id="21f54-420">International</span><span class="sxs-lookup"><span data-stu-id="21f54-420">International</span></span>|<span data-ttu-id="21f54-421">\d +</span><span class="sxs-lookup"><span data-stu-id="21f54-421">\d+</span></span>|<span data-ttu-id="21f54-422">4</span><span class="sxs-lookup"><span data-stu-id="21f54-422">4</span></span>|<span data-ttu-id="21f54-423">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="21f54-423">sbc2.contoso.biz</span></span><br/><span data-ttu-id="21f54-424">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="21f54-424">sbc5.contoso.biz</span></span>|<span data-ttu-id="21f54-425">Itinéraire pour n’importe quel modèle numérique</span><span class="sxs-lookup"><span data-stu-id="21f54-425">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="21f54-426">L’ordre des utilisations RTC dans les stratégies de routage vocale est essentiel.</span><span class="sxs-lookup"><span data-stu-id="21f54-426">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="21f54-427">Les utilisations sont appliquées dans l’ordre et, si une correspondance est trouvée dans la première utilisation, les autres utilisations ne sont jamais évaluées.</span><span class="sxs-lookup"><span data-stu-id="21f54-427">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="21f54-428">L’utilisation RTC « international » doit être placée après l’utilisation RTC « États-Unis uniquement ».</span><span class="sxs-lookup"><span data-stu-id="21f54-428">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="21f54-429">Pour modifier l’ordre des utilisations RTC, exécutez la `Set-CSOnlineVoiceRoutingPolicy` commande.</span><span class="sxs-lookup"><span data-stu-id="21f54-429">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="21f54-430">Par exemple, pour passer de l’ordre « États-Unis et Canada » et inversement, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="21f54-430">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="21f54-431">Le niveau de priorité des itinéraires vocaux « Other + 1 » et « international » est automatiquement attribué.</span><span class="sxs-lookup"><span data-stu-id="21f54-431">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="21f54-432">Il n’y a pas d’importance tant qu’il dispose de priorités inférieures à « Redmond 1 » et « Redmond 2 ».</span><span class="sxs-lookup"><span data-stu-id="21f54-432">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="21f54-433">Exemple de politique de routage vocale pour les bois des utilisateurs de Jean</span><span class="sxs-lookup"><span data-stu-id="21f54-433">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="21f54-434">Les étapes à suivre pour créer une utilisation PSTN « international », un itinéraire vocal « international », « stratégie de routage vocale » n’est pas soumis à des restrictions», puis l’affecter à l’utilisateur « Jean bois » est le suivant.</span><span class="sxs-lookup"><span data-stu-id="21f54-434">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


<span data-ttu-id="21f54-435">**Étape 1**: créer une utilisation PSTN internationale.</span><span class="sxs-lookup"><span data-stu-id="21f54-435">**Step 1**: Create the PSTN Usage "International."</span></span> 

<span data-ttu-id="21f54-436">Dans une session PowerShell distante dans Skype entreprise Online, entrez :</span><span class="sxs-lookup"><span data-stu-id="21f54-436">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

<span data-ttu-id="21f54-437">**Étape 2**: créer le nouvel itinéraire vocal « international »</span><span class="sxs-lookup"><span data-stu-id="21f54-437">**Step 2**:  Create the new voice route "International."</span></span>

```
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="21f54-438">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="21f54-438">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

<span data-ttu-id="21f54-439">**Étape 3**: créer une stratégie de routage téléphonique « aucune restriction ».</span><span class="sxs-lookup"><span data-stu-id="21f54-439">**Step 3**: Create a Voice Routing Policy "No Restrictions".</span></span> 

<span data-ttu-id="21f54-440">L’utilisation RTC « Redmond 1 » et « Redmond » sont réutilisées dans cette politique de routage vocale pour garantir une gestion spéciale des appels au numéro « + 1 425 XXX XX XX » et « + 1 206 XXX XX XX » en tant qu’appels locaux ou locaux.</span><span class="sxs-lookup"><span data-stu-id="21f54-440">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

   ```
   New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
   ```

<span data-ttu-id="21f54-441">Prenez note de l’ordre des utilisations RTC :</span><span class="sxs-lookup"><span data-stu-id="21f54-441">Take note of the order of PSTN Usages:</span></span>

<span data-ttu-id="21f54-442">a.</span><span class="sxs-lookup"><span data-stu-id="21f54-442">a.</span></span> <span data-ttu-id="21f54-443">Si un appel a été effectué pour le numéro « + 1 425 XXX XX XX » avec les utilisations configurées comme dans l’exemple suivant, l’appel suit le routage défini dans utilisation des États-Unis et du Canada et la logique de routage spécial est appliquée.</span><span class="sxs-lookup"><span data-stu-id="21f54-443">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="21f54-444">C’est la première fois que l’appel est routé à l’aide de sbc1.contoso.biz et sbc2.contoso.biz, puis de sbc3.contoso.biz et d’sbc4.contoso.biz de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="21f54-444">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

<span data-ttu-id="21f54-445">b.</span><span class="sxs-lookup"><span data-stu-id="21f54-445">b.</span></span> <span data-ttu-id="21f54-446">S’il s’agit d’une utilisation PSTN « internationale », les appels vers + 1 425 XXX XX XX sont routés vers sbc2.contoso.biz et sbc5.contoso.biz dans le cadre de la logique de routage.</span><span class="sxs-lookup"><span data-stu-id="21f54-446">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="21f54-447">Entrez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="21f54-447">Enter the command:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

<span data-ttu-id="21f54-448">Qui renvoie</span><span class="sxs-lookup"><span data-stu-id="21f54-448">Which returns</span></span>

<pre>
Identity              : International 
OnlinePstnUsages : {US and Canada, International}    
Description      :  
RouteType             : BYOT
</pre>

<span data-ttu-id="21f54-449">**Étape 4**: affectez la stratégie de routage téléphonique à l’utilisateur « Jean bois » à l’aide de la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="21f54-449">**Step 4**: Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

```
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

<span data-ttu-id="21f54-450">Vérifiez ensuite le devoir à l’aide de la commande :</span><span class="sxs-lookup"><span data-stu-id="21f54-450">Then verify the assignment using the command:</span></span> 

```
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="21f54-451">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="21f54-451">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="21f54-452">Le résultat est que la stratégie vocale appliquée aux appels de Jean-Martin n’est pas restreinte et qu’elle respecte la logique du routage des appels disponible aux États-Unis, au Canada et au service d’appels internationaux.</span><span class="sxs-lookup"><span data-stu-id="21f54-452">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="21f54-453">Attribuer le mode d’affectation uniquement aux utilisateurs pour s’assurer des appels terrestres dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="21f54-453">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="21f54-454">Le routage direct exige que les utilisateurs soient en mode d’équipe uniquement pour s’assurer que les appels entrants sont présents dans le client Teams.</span><span class="sxs-lookup"><span data-stu-id="21f54-454">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="21f54-455">Pour faire en sorte que les utilisateurs en mode équipes uniquement, attribuez-leur l’instance « UpgradeToTeams » de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="21f54-455">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="21f54-456">Si votre organisation utilise Skype entreprise Server ou Skype entreprise Online, reportez-vous à l’article suivant pour l’interopérabilité des informations entre Skype et teams : [instructions de migration et d’interopérabilité pour les entreprises utilisant teams conjointement avec Skype entreprise](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="21f54-456">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information interoperability between Skype and Teams: [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 

## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="21f54-457">Configurer l’envoi d’appels directement à la boîte vocale</span><span class="sxs-lookup"><span data-stu-id="21f54-457">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="21f54-458">Le routage direct vous permet de mettre fin à l’appel d’un utilisateur et de l’envoyer directement à la boîte vocale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="21f54-458">Direct Routing allows you to end the call to a user and send it directly to the users' voicemail.</span></span> <span data-ttu-id="21f54-459">Si vous voulez envoyer l’appel directement à la boîte vocale, attachez opaque = application : boîte vocale dans l’en-tête de demande d’URI.</span><span class="sxs-lookup"><span data-stu-id="21f54-459">If you want to send the call directly to voicemail, please attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="21f54-460">Par exemple, « SIP : user@yourdomain. com ; opaque = application : boîte vocale ».</span><span class="sxs-lookup"><span data-stu-id="21f54-460">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span>
<span data-ttu-id="21f54-461">Si tel est le cas, l’utilisateur teams n’aura pas reçu la notification d’appel, l’appel est alors directement connecté à la messagerie vocale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="21f54-461">In this case the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="translate-caller-and-callee-numbers-for-outbound-and-inbound-calls-to-an-alternate-format"></a><span data-ttu-id="21f54-462">Traduire des numéros d’appelant et de contact pour les appels sortants et entrants vers un autre format</span><span class="sxs-lookup"><span data-stu-id="21f54-462">Translate caller and callee numbers for outbound and inbound calls to an alternate format</span></span>

<span data-ttu-id="21f54-463">Il arrive que les administrateurs de clients souhaitent changer le numéro de l’appelant ou de l’appelant pour les appels sortants et/ou entrants en fonction des modèles qu’ils ont créés pour garantir l’interopérabilité avec SBCs.</span><span class="sxs-lookup"><span data-stu-id="21f54-463">Sometimes tenant administrators may want to change the callee or caller number for outbound and/or inbound calls based on the patterns they created to ensure interoperability with SBCs.</span></span> <span data-ttu-id="21f54-464">Vous pouvez définir une stratégie de règles de traduction numérique pour traduire les numéros d’appelant ou d’appelant dans un autre format.</span><span class="sxs-lookup"><span data-stu-id="21f54-464">You can set a Number Translation Rules policy to translate callee or caller numbers to an alternate format.</span></span> <span data-ttu-id="21f54-465">Vous pouvez utiliser la stratégie pour traduire des numéros pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="21f54-465">You can use the policy to translate numbers for the following:</span></span>

- <span data-ttu-id="21f54-466">Appels entrants : appels d’un point de terminaison PSTN (appelant) vers un client Teams (appelé).</span><span class="sxs-lookup"><span data-stu-id="21f54-466">Inbound calls: Calls from a PSTN endpoint (caller) to a Teams client (callee).</span></span>
- <span data-ttu-id="21f54-467">Appels sortants : appels passés d’un client teams vers un point de terminaison PSTN (appelé appelant).</span><span class="sxs-lookup"><span data-stu-id="21f54-467">Outbound calls: Calls from a Teams client (caller) to a PSTN endpoint (callee).</span></span>

<span data-ttu-id="21f54-468">La stratégie est appliquée au niveau du SBC.</span><span class="sxs-lookup"><span data-stu-id="21f54-468">The policy is applied at the SBC level.</span></span> <span data-ttu-id="21f54-469">Vous pouvez affecter plusieurs règles de traduction à une SBC, qui sont appliquées dans l’ordre dans lequel elles apparaissent lorsque vous les affichez dans PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21f54-469">You can assign multiple translation rules to a SBC, which are applied in the order that they appear when you list them in PowerShell.</span></span> <span data-ttu-id="21f54-470">Vous pouvez également modifier l’ordre des règles dans la stratégie.</span><span class="sxs-lookup"><span data-stu-id="21f54-470">You can also change the order of the rules in the policy.</span></span>

<span data-ttu-id="21f54-471">Pour créer, modifier, afficher et supprimer des règles de manipulation de nombre, utilisez les applets de TeamsTranslationRule, Set-TeamsTranslationRule, Get-TeamsTranslationRule et Remove-TeamsTranslationRule.</span><span class="sxs-lookup"><span data-stu-id="21f54-471">To create, modify, view, and delete number manipulation rules, use the New-TeamsTranslationRule, Set-TeamsTranslationRule, Get-TeamsTranslationRule, and Remove-TeamsTranslationRule cmdlets.</span></span>

<span data-ttu-id="21f54-472">Pour attribuer, configurer et répertorier des règles de manipulation de numéros sur SBCS, utilisez les applets de [nouvelle-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) et [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) conjointement ```OutboundTeamsNumberTranslationRules```avec ```OutboundPSTNNumberTranslationRules```les ```InboundTeamsNumberTranslationRulesList``` ```InboundTeamsNumberTranslationRules```paramètres ```InboundPSTNNumberTranslationRulesList```, ```OutboundTeamsNumberTranslationRulesList``` ```InboundPSTNNumberTranslationRules```,, ```OutboundPSTNNumberTranslationRulesList``` ,, et.</span><span class="sxs-lookup"><span data-stu-id="21f54-472">To assign, configure, and list number manipulation rules on SBCs, use the [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) and [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlets together with the  ```InboundTeamsNumberTranslationRules```, ```InboundPSTNNumberTranslationRules```, ```OutboundTeamsNumberTranslationRules```, ```OutboundPSTNNumberTranslationRules```, ```InboundTeamsNumberTranslationRulesList```, ```InboundPSTNNumberTranslationRulesList```, ```OutboundTeamsNumberTranslationRulesList```, and ```OutboundPSTNNumberTranslationRulesList``` parameters.</span></span>

### <a name="examples"></a><span data-ttu-id="21f54-473">Exemples</span><span class="sxs-lookup"><span data-stu-id="21f54-473">Examples</span></span>

#### <a name="example-sbc-configuration"></a><span data-ttu-id="21f54-474">Exemple de configuration de SBC</span><span class="sxs-lookup"><span data-stu-id="21f54-474">Example SBC configuration</span></span>

<span data-ttu-id="21f54-475">Dans les exemples de scénarios, nous exécutons l' ```New-CsOnlinePSTNGateway``` applet de commande pour créer la configuration SBC suivante.</span><span class="sxs-lookup"><span data-stu-id="21f54-475">For the example scenarios, we run the ```New-CsOnlinePSTNGateway``` cmdlet to create the following SBC configuration.</span></span>

```
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignallingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

<span data-ttu-id="21f54-476">Le tableau suivant répertorie les règles de traduction affectées à l’SBC.</span><span class="sxs-lookup"><span data-stu-id="21f54-476">The translation rules assigned to the SBC are summarized in the following table.</span></span>

|<span data-ttu-id="21f54-477">Nom</span><span class="sxs-lookup"><span data-stu-id="21f54-477">Name</span></span>  |<span data-ttu-id="21f54-478">Modèle</span><span class="sxs-lookup"><span data-stu-id="21f54-478">Pattern</span></span> |<span data-ttu-id="21f54-479">Conversion</span><span class="sxs-lookup"><span data-stu-id="21f54-479">Translation</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="21f54-480">AddPlus1</span><span class="sxs-lookup"><span data-stu-id="21f54-480">AddPlus1</span></span>     |<span data-ttu-id="21f54-481">^ (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="21f54-481">^(\d{10})$</span></span>          |<span data-ttu-id="21f54-482">+1$1</span><span class="sxs-lookup"><span data-stu-id="21f54-482">+1$1</span></span>          |
|<span data-ttu-id="21f54-483">AddE164SeattleAreaCode</span><span class="sxs-lookup"><span data-stu-id="21f54-483">AddE164SeattleAreaCode</span></span>      |<span data-ttu-id="21f54-484">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="21f54-484">^(\d{4})$</span></span>          | <span data-ttu-id="21f54-485">commande + 1206555 $1</span><span class="sxs-lookup"><span data-stu-id="21f54-485">+1206555$1</span></span>         |
|<span data-ttu-id="21f54-486">AddSeattleAreaCode</span><span class="sxs-lookup"><span data-stu-id="21f54-486">AddSeattleAreaCode</span></span>    |<span data-ttu-id="21f54-487">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="21f54-487">^(\d{4})$</span></span>          | <span data-ttu-id="21f54-488">425555 $1</span><span class="sxs-lookup"><span data-stu-id="21f54-488">425555$1</span></span>         |
|<span data-ttu-id="21f54-489">StripPlus1</span><span class="sxs-lookup"><span data-stu-id="21f54-489">StripPlus1</span></span>    |<span data-ttu-id="21f54-490">^ + 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="21f54-490">^+1(\d{10})$</span></span>          | <span data-ttu-id="21f54-491">$1</span><span class="sxs-lookup"><span data-stu-id="21f54-491">$1</span></span>         |

<span data-ttu-id="21f54-492">Dans ces exemples de scénarios, nous avons deux utilisateurs, Alice et Bob.</span><span class="sxs-lookup"><span data-stu-id="21f54-492">In these example scenarios, we have two users, Alice and Bob.</span></span> <span data-ttu-id="21f54-493">Alice est un utilisateur de teams et son numéro est + 1 206 555 0100.</span><span class="sxs-lookup"><span data-stu-id="21f54-493">Alice is a Teams user and her number is +1 206 555 0100.</span></span> <span data-ttu-id="21f54-494">Bob est un utilisateur RTC et son numéro est + 1 425 555 0100.</span><span class="sxs-lookup"><span data-stu-id="21f54-494">Bob is a PSTN user and his number is +1 425 555 0100.</span></span>

#### <a name="example-1-inbound-call-to-a-ten-digit-number"></a><span data-ttu-id="21f54-495">Exemple 1 : appel entrant vers un numéro à dix chiffres</span><span class="sxs-lookup"><span data-stu-id="21f54-495">Example 1: Inbound call to a ten-digit number</span></span>

<span data-ttu-id="21f54-496">Bob appelle Alice en utilisant un numéro à 10 chiffres non-E. 164.</span><span class="sxs-lookup"><span data-stu-id="21f54-496">Bob calls Alice using a non-E.164 ten-digit number.</span></span> <span data-ttu-id="21f54-497">Bob compose 2065550100 pour joindre Alice.</span><span class="sxs-lookup"><span data-stu-id="21f54-497">Bob dials 2065550100 to reach Alice.</span></span>
<span data-ttu-id="21f54-498">SBC utilise 2065550100 dans le RequestURI et les en-têtes et 4255550100 dans l’en-tête de.</span><span class="sxs-lookup"><span data-stu-id="21f54-498">SBC uses 2065550100 in the RequestURI and To headers and 4255550100 in the From header.</span></span>

|<span data-ttu-id="21f54-499">Titre</span><span class="sxs-lookup"><span data-stu-id="21f54-499">Header</span></span>  |<span data-ttu-id="21f54-500">Langue source</span><span class="sxs-lookup"><span data-stu-id="21f54-500">Original</span></span> |<span data-ttu-id="21f54-501">En-tête traduit</span><span class="sxs-lookup"><span data-stu-id="21f54-501">Translated header</span></span> |<span data-ttu-id="21f54-502">Paramètre et règle appliqués</span><span class="sxs-lookup"><span data-stu-id="21f54-502">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="21f54-503">RequestURI</span><span class="sxs-lookup"><span data-stu-id="21f54-503">RequestURI</span></span>  |<span data-ttu-id="21f54-504">INVITER sip :2065550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="21f54-504">INVITE sip:2065550100@sbc.contoso.com</span></span>|<span data-ttu-id="21f54-505">INVITER sip :+12065550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="21f54-505">INVITE sip:+12065550100@sbc.contoso.com</span></span>|<span data-ttu-id="21f54-506">InboundTeamsNumberTranslationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="21f54-506">InboundTeamsNumberTranslationRulesList ‘AddPlus1’</span></span>|
|<span data-ttu-id="21f54-507">À</span><span class="sxs-lookup"><span data-stu-id="21f54-507">TO</span></span>    |<span data-ttu-id="21f54-508">À : \<SIP :2065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="21f54-508">TO: \<sip:2065550100@sbc.contoso.com></span></span>|<span data-ttu-id="21f54-509">À : \<SIP :+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="21f54-509">TO: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="21f54-510">InboundTeamsNumberTranlationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="21f54-510">InboundTeamsNumberTranlationRulesList ‘AddPlus1’</span></span>|
|<span data-ttu-id="21f54-511">De</span><span class="sxs-lookup"><span data-stu-id="21f54-511">FROM</span></span>   |<span data-ttu-id="21f54-512">À partir \<de : SIP :4255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="21f54-512">FROM: \<sip:4255550100@sbc.contoso.com></span></span>|<span data-ttu-id="21f54-513">À partir \<de : SIP :+14255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="21f54-513">FROM: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="21f54-514">InboundPSTNNumberTranslationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="21f54-514">InboundPSTNNumberTranslationRulesList ‘AddPlus1’</span></span>|

#### <a name="example-2-inbound-call-to-a-four-digit-number"></a><span data-ttu-id="21f54-515">Exemple 2 : appel entrant vers un numéro à quatre chiffres</span><span class="sxs-lookup"><span data-stu-id="21f54-515">Example 2: Inbound call to a four-digit number</span></span>

<span data-ttu-id="21f54-516">Bob appelle Alice en utilisant un numéro à quatre chiffres.</span><span class="sxs-lookup"><span data-stu-id="21f54-516">Bob calls Alice using a four-digit number.</span></span> <span data-ttu-id="21f54-517">Bob compose 0100 pour joindre Alice.</span><span class="sxs-lookup"><span data-stu-id="21f54-517">Bob dials 0100 to reach Alice.</span></span>
<span data-ttu-id="21f54-518">SBC utilise 0100 dans le RequestURI et les en-têtes et 4255550100 dans l’en-tête de.</span><span class="sxs-lookup"><span data-stu-id="21f54-518">SBC uses 0100 in the RequestURI and To headers and 4255550100 in the From header.</span></span>

|<span data-ttu-id="21f54-519">Titre</span><span class="sxs-lookup"><span data-stu-id="21f54-519">Header</span></span>  |<span data-ttu-id="21f54-520">Langue source</span><span class="sxs-lookup"><span data-stu-id="21f54-520">Original</span></span> |<span data-ttu-id="21f54-521">En-tête traduit</span><span class="sxs-lookup"><span data-stu-id="21f54-521">Translated header</span></span> |<span data-ttu-id="21f54-522">Paramètre et règle appliqués</span><span class="sxs-lookup"><span data-stu-id="21f54-522">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="21f54-523">RequestURI</span><span class="sxs-lookup"><span data-stu-id="21f54-523">RequestURI</span></span>  |<span data-ttu-id="21f54-524">INVITER sip :0100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="21f54-524">INVITE sip:0100@sbc.contoso.com</span></span>          |<span data-ttu-id="21f54-525">INVITER sip :+12065550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="21f54-525">INVITE sip:+12065550100@sbc.contoso.com</span></span>           |<span data-ttu-id="21f54-526">InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="21f54-526">InboundTeamsNumberTranlationRulesList ‘AddE164SeattleAreaCode’</span></span>        |
|<span data-ttu-id="21f54-527">À</span><span class="sxs-lookup"><span data-stu-id="21f54-527">TO</span></span>    |<span data-ttu-id="21f54-528">À : \<SIP :0100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="21f54-528">TO: \<sip:0100@sbc.contoso.com></span></span>|<span data-ttu-id="21f54-529">À : \<SIP :+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="21f54-529">TO: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="21f54-530">InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="21f54-530">InboundTeamsNumberTranlationRulesList ‘AddE164SeattleAreaCode’</span></span>         |
|<span data-ttu-id="21f54-531">De</span><span class="sxs-lookup"><span data-stu-id="21f54-531">FROM</span></span>   |<span data-ttu-id="21f54-532">À partir \<de : SIP :4255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="21f54-532">FROM: \<sip:4255550100@sbc.contoso.com></span></span>|<span data-ttu-id="21f54-533">À partir \<de : SIP :+14255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="21f54-533">FROM: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="21f54-534">InboundPSTNNumberTranlationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="21f54-534">InboundPSTNNumberTranlationRulesList ‘AddPlus1’</span></span>        |

#### <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a><span data-ttu-id="21f54-535">Exemple 3 : appel sortant avec un numéro à dix chiffres non-E. 164</span><span class="sxs-lookup"><span data-stu-id="21f54-535">Example 3: Outbound call using a ten-digit non-E.164 number</span></span>

<span data-ttu-id="21f54-536">Alice appelle Bob par le biais d’un numéro à dix chiffres.</span><span class="sxs-lookup"><span data-stu-id="21f54-536">Alice calls Bob using a ten-digit number.</span></span> <span data-ttu-id="21f54-537">Alice compose le numéro 425 555 0100 pour joindre Bob.</span><span class="sxs-lookup"><span data-stu-id="21f54-537">Alice dials 425 555 0100 to reach Bob.</span></span>
<span data-ttu-id="21f54-538">SBC est configuré de manière à utiliser des numéros non-E. 164 à dix chiffres pour les équipes et les utilisateurs PSTN.</span><span class="sxs-lookup"><span data-stu-id="21f54-538">SBC is configured to use non-E.164 ten-digit numbers for both Teams and PSTN users.</span></span>

<span data-ttu-id="21f54-539">Dans ce scénario, un plan de numérotation traduit le numéro avant de l’envoyer à l’interface de routage directe.</span><span class="sxs-lookup"><span data-stu-id="21f54-539">In this scenario, a dial plan translates the number before sending it to the Direct Routing interface.</span></span> <span data-ttu-id="21f54-540">Lorsque Alice entre 425 555 0100 dans le client Teams, le numéro est converti en + 14255550100 par le plan de numérotation pays.</span><span class="sxs-lookup"><span data-stu-id="21f54-540">When Alice enters 425 555 0100 in the Teams client, the number is translated to +14255550100 by the country dial plan.</span></span> <span data-ttu-id="21f54-541">Les numéros obtenus sont une normalisation cumulative des règles de plan de numérotation et des règles de traduction d’équipes.</span><span class="sxs-lookup"><span data-stu-id="21f54-541">The resulting numbers are a cumulative normalization of the dial plan rules and Teams translation rules.</span></span> <span data-ttu-id="21f54-542">Les règles de traduction des équipes suppriment le « + 1 » ajouté par le plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="21f54-542">The Teams translation rules remove the "+1" that was added by the dial plan.</span></span>

|<span data-ttu-id="21f54-543">Titre</span><span class="sxs-lookup"><span data-stu-id="21f54-543">Header</span></span>  |<span data-ttu-id="21f54-544">Langue source</span><span class="sxs-lookup"><span data-stu-id="21f54-544">Original</span></span> |<span data-ttu-id="21f54-545">En-tête traduit</span><span class="sxs-lookup"><span data-stu-id="21f54-545">Translated header</span></span> |<span data-ttu-id="21f54-546">Paramètre et règle appliqués</span><span class="sxs-lookup"><span data-stu-id="21f54-546">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="21f54-547">RequestURI</span><span class="sxs-lookup"><span data-stu-id="21f54-547">RequestURI</span></span>  |<span data-ttu-id="21f54-548">INVITER sip :+14255550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="21f54-548">INVITE sip:+14255550100@sbc.contoso.com</span></span>          |<span data-ttu-id="21f54-549">INVITER sip :4255550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="21f54-549">INVITE sip:4255550100@sbc.contoso.com</span></span>       |<span data-ttu-id="21f54-550">OutboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="21f54-550">OutboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span>         |
|<span data-ttu-id="21f54-551">À</span><span class="sxs-lookup"><span data-stu-id="21f54-551">TO</span></span>    |<span data-ttu-id="21f54-552">À : \<SIP :+14255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="21f54-552">TO: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="21f54-553">À : \<SIP :4255555555@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="21f54-553">TO: \<sip:4255555555@sbc.contoso.com></span></span>|<span data-ttu-id="21f54-554">OutboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="21f54-554">OutboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span>       |
|<span data-ttu-id="21f54-555">De</span><span class="sxs-lookup"><span data-stu-id="21f54-555">FROM</span></span>   |<span data-ttu-id="21f54-556">À partir \<de : SIP :+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="21f54-556">FROM: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="21f54-557">À partir \<de : SIP :2065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="21f54-557">FROM: \<sip:2065550100@sbc.contoso.com></span></span>|<span data-ttu-id="21f54-558">OutboundTeamsNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="21f54-558">OutboundTeamsNumberTranlationRulesList ‘StripPlus1’</span></span>         |

#### <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a><span data-ttu-id="21f54-559">Exemple 4 : appel sortant avec un numéro à quatre chiffres non-E. 164</span><span class="sxs-lookup"><span data-stu-id="21f54-559">Example 4: Outbound call using a four-digit non-E.164 number</span></span>

<span data-ttu-id="21f54-560">Alice appelle Bob par le biais d’un numéro à quatre chiffres.</span><span class="sxs-lookup"><span data-stu-id="21f54-560">Alice calls Bob using a four-digit number.</span></span> <span data-ttu-id="21f54-561">Alice utilise 0100 pour joindre Bob depuis les appels ou à l’aide d’un contact.</span><span class="sxs-lookup"><span data-stu-id="21f54-561">Alice uses 0100 to reach Bob from Calls or by using a contact.</span></span>
<span data-ttu-id="21f54-562">SBC est configuré pour utiliser des numéros à quatre chiffres non-E. 164 pour les utilisateurs de teams et des numéros à dix chiffres pour les utilisateurs PSTN.</span><span class="sxs-lookup"><span data-stu-id="21f54-562">SBC is configured to use non-E.164 four-digit numbers for Teams users and ten-digit numbers for PSTN users.</span></span> <span data-ttu-id="21f54-563">Le plan de numérotation n’est pas appliqué dans ce scénario.</span><span class="sxs-lookup"><span data-stu-id="21f54-563">The dial plan isn't applied in this scenario.</span></span>

|<span data-ttu-id="21f54-564">Titre</span><span class="sxs-lookup"><span data-stu-id="21f54-564">Header</span></span>  |<span data-ttu-id="21f54-565">Langue source</span><span class="sxs-lookup"><span data-stu-id="21f54-565">Original</span></span> |<span data-ttu-id="21f54-566">En-tête traduit</span><span class="sxs-lookup"><span data-stu-id="21f54-566">Translated header</span></span> |<span data-ttu-id="21f54-567">Paramètre et règle appliqués</span><span class="sxs-lookup"><span data-stu-id="21f54-567">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="21f54-568">RequestURI</span><span class="sxs-lookup"><span data-stu-id="21f54-568">RequestURI</span></span>  |<span data-ttu-id="21f54-569">INVITER sip :0100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="21f54-569">INVITE sip:0100@sbc.contoso.com</span></span>           |<span data-ttu-id="21f54-570">INVITER sip :4255550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="21f54-570">INVITE sip:4255550100@sbc.contoso.com</span></span>       |<span data-ttu-id="21f54-571">InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="21f54-571">InboundTeamsNumberTranlationRulesList ‘AddSeattleAreaCode’</span></span>         |
|<span data-ttu-id="21f54-572">À</span><span class="sxs-lookup"><span data-stu-id="21f54-572">TO</span></span>    |<span data-ttu-id="21f54-573">À : \<SIP :0100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="21f54-573">TO: \<sip:0100@sbc.contoso.com></span></span>|<span data-ttu-id="21f54-574">À : \<SIP :4255555555@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="21f54-574">TO: \<sip:4255555555@sbc.contoso.com></span></span>|<span data-ttu-id="21f54-575">InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="21f54-575">InboundTeamsNumberTranlationRulesList ‘AddSeattleAreaCode’</span></span>       |
|<span data-ttu-id="21f54-576">De</span><span class="sxs-lookup"><span data-stu-id="21f54-576">FROM</span></span>   |<span data-ttu-id="21f54-577">À partir \<de : SIP :+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="21f54-577">FROM: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="21f54-578">À partir \<de : SIP :2065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="21f54-578">FROM: \<sip:2065550100@sbc.contoso.com></span></span>| <span data-ttu-id="21f54-579">InboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="21f54-579">InboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span> |

## <a name="see-also"></a><span data-ttu-id="21f54-580">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="21f54-580">See also</span></span>

[<span data-ttu-id="21f54-581">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="21f54-581">Plan Direct Routing</span></span>](direct-routing-plan.md)
