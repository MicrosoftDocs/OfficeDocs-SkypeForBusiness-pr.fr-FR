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
ms.openlocfilehash: a15b679dfa5ac74c6c78242ac40b00e2f24f75a4
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572222"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="270f4-103">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="270f4-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="270f4-104">Regardez la session suivante pour en savoir plus sur les avantages du routage direct, la planification et le déploiement : [routage direct dans Microsoft teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="270f4-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="270f4-105">Si vous ne l’avez pas encore fait, lisez [planifier le routage direct](direct-routing-plan.md) pour les prérequis et passer en revue les autres étapes que vous devez effectuer avant de configurer votre réseau de systèmes Microsoft Phone.</span><span class="sxs-lookup"><span data-stu-id="270f4-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="270f4-106">Cet article décrit comment configurer le routage direct du système Microsoft Phone.</span><span class="sxs-lookup"><span data-stu-id="270f4-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="270f4-107">Il explique en détail comment jumeler une manette de frontière de session (SBC) prise en charge et configurer les utilisateurs de Microsoft teams pour se connecter au réseau téléphonique public commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="270f4-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="270f4-108">Pour suivre les étapes décrites dans cet article, les administrateurs doivent vous familiariser avec les applets de cmdlet PowerShell.</span><span class="sxs-lookup"><span data-stu-id="270f4-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="270f4-109">Pour plus d’informations sur l’utilisation de PowerShell, voir [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="270f4-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="270f4-110">Nous vous conseillons de vérifier que votre SBC a déjà été configuré comme recommandé par votre fournisseur de SBC :</span><span class="sxs-lookup"><span data-stu-id="270f4-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="270f4-111">Documentation de déploiement AudioCodes</span><span class="sxs-lookup"><span data-stu-id="270f4-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="270f4-112">Documentation relative au déploiement d’Oracle</span><span class="sxs-lookup"><span data-stu-id="270f4-112">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="270f4-113">Documentation sur le déploiement des communications du ruban</span><span class="sxs-lookup"><span data-stu-id="270f4-113">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="270f4-114">Documentation sur le déploiement de TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="270f4-114">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="270f4-115">Vous pouvez configurer votre système Microsoft Phone et permettre aux utilisateurs d’utiliser le routage direct, puis configurer Microsoft teams en tant que client appelant préféré en exécutant les procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="270f4-115">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="270f4-116">Coupler une SBC avec un système Microsoft Phone et valider le jumelage</span><span class="sxs-lookup"><span data-stu-id="270f4-116">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [<span data-ttu-id="270f4-117">Activer les utilisateurs pour le service de routage direct</span><span class="sxs-lookup"><span data-stu-id="270f4-117">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- <span data-ttu-id="270f4-118">Vérifiez que Microsoft teams est le client appelant préféré pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="270f4-118">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="270f4-119">Coupler l’SBC au service de routage direct du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="270f4-119">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="270f4-120">Voici les trois principales étapes pour vous permettre de vous connecter, ou jumeler, l’interface SBC à l’interface de routage directe :</span><span class="sxs-lookup"><span data-stu-id="270f4-120">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="270f4-121">Se connecter au centre **d’administration de Skype entreprise Online** à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="270f4-121">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="270f4-122">Coupler l’SBC</span><span class="sxs-lookup"><span data-stu-id="270f4-122">Pair the SBC</span></span> 
- <span data-ttu-id="270f4-123">Valider le jumelage</span><span class="sxs-lookup"><span data-stu-id="270f4-123">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="270f4-124">Se connecter à Skype entreprise Online à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="270f4-124">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="270f4-125">Vous pouvez utiliser une session PowerShell connectée au client pour jumeler l’interface SBC à l’interface de routage directe.</span><span class="sxs-lookup"><span data-stu-id="270f4-125">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="270f4-126">Pour ouvrir une session PowerShell, suivez les étapes décrites dans [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="270f4-126">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="270f4-127">Après avoir établi une session PowerShell distante, vérifiez que vous pouvez voir les commandes pour gérer l’SBC.</span><span class="sxs-lookup"><span data-stu-id="270f4-127">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="270f4-128">Pour valider les commandes, tapez ou copiez/collez les éléments suivants dans la session PowerShell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="270f4-128">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="270f4-129">Votre commande renverra les quatre fonctions indiquées ici pour vous permettre de gérer l’SBC.</span><span class="sxs-lookup"><span data-stu-id="270f4-129">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="270f4-130">Coupler l’SBC au client</span><span class="sxs-lookup"><span data-stu-id="270f4-130">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="270f4-131">Pour jumeler l’SBC au client, dans la session PowerShell, entrez ce qui suit, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="270f4-131">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="270f4-132">Nous vous recommandons vivement de définir une limite d’appels maximale dans l’SBC en utilisant les informations qui figurent dans la documentation de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="270f4-132">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="270f4-133">La limite déclenche une notification si l’SBC a le niveau de capacité.</span><span class="sxs-lookup"><span data-stu-id="270f4-133">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="270f4-134">Vous pouvez uniquement jumeler l’SBC si la partie Domain de son nom de domaine complet correspond à l’un des domaines inscrits \*dans votre client, à l’exception de. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="270f4-134">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="270f4-135">L' \*utilisation des noms de domaine. onmicrosoft.com n’est pas prise en charge pour le nom de domaine complet SBC.</span><span class="sxs-lookup"><span data-stu-id="270f4-135">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="270f4-136">Par exemple, si vous avez deux noms de domaine :</span><span class="sxs-lookup"><span data-stu-id="270f4-136">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="270f4-137">**contoso**. com</span><span class="sxs-lookup"><span data-stu-id="270f4-137">**contoso**.com</span></span><br/><span data-ttu-id="270f4-138">**contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="270f4-138">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="270f4-139">Pour le nom SBC, vous pouvez utiliser le nom sbc.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="270f4-139">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="270f4-140">Si vous essayez de jumeler l’SBC avec un nom SBC. contoso. ABC, le système ne vous en permettra pas, car le domaine n’est pas détenu par ce client.</span><span class="sxs-lookup"><span data-stu-id="270f4-140">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span><br/>
  > <span data-ttu-id="270f4-141">Outre le domaine enregistré dans votre client, il est important qu’il existe un utilisateur avec ce domaine et qu’une licence E3 ou E5 lui est affectée.</span><span class="sxs-lookup"><span data-stu-id="270f4-141">In addition to the domain registered in your tenant, it is important that there is a user with that domain and an assigned E3 or E5 license.</span></span> <span data-ttu-id="270f4-142">Si ce n’est pas le cas, vous recevez le message d’erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="270f4-142">If not, you will receive the following error:</span></span><br/>
  <span data-ttu-id="270f4-143">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span><span class="sxs-lookup"><span data-stu-id="270f4-143"></span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="270f4-144">Renvoie</span><span class="sxs-lookup"><span data-stu-id="270f4-144">Returns:</span></span>
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
<span data-ttu-id="270f4-145">Il existe d’autres options qui peuvent être définies lors du processus de jumelage.</span><span class="sxs-lookup"><span data-stu-id="270f4-145">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="270f4-146">Dans l’exemple précédent, seuls les paramètres minimum requis apparaissent.</span><span class="sxs-lookup"><span data-stu-id="270f4-146">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="270f4-147">Le tableau suivant répertorie les paramètres supplémentaires que vous pouvez utiliser dans les paramètres de configuration de`New-CsOnlinePstnGateway`</span><span class="sxs-lookup"><span data-stu-id="270f4-147">The following table lists the additional parameters that you can use in setting parameters for `New-CsOnlinePstnGateway`</span></span>

|<span data-ttu-id="270f4-148">Obligatoire?</span><span class="sxs-lookup"><span data-stu-id="270f4-148">Required?</span></span>|<span data-ttu-id="270f4-149">Nom</span><span class="sxs-lookup"><span data-stu-id="270f4-149">Name</span></span>|<span data-ttu-id="270f4-150">Description</span><span class="sxs-lookup"><span data-stu-id="270f4-150">Description</span></span>|<span data-ttu-id="270f4-151">Par défaut</span><span class="sxs-lookup"><span data-stu-id="270f4-151">Default</span></span>|<span data-ttu-id="270f4-152">Valeurs possibles</span><span class="sxs-lookup"><span data-stu-id="270f4-152">Possible values</span></span>|<span data-ttu-id="270f4-153">Type et restrictions</span><span class="sxs-lookup"><span data-stu-id="270f4-153">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="270f4-154">Oui</span><span class="sxs-lookup"><span data-stu-id="270f4-154">Yes</span></span>|<span data-ttu-id="270f4-155">FQDN</span><span class="sxs-lookup"><span data-stu-id="270f4-155">FQDN</span></span>|<span data-ttu-id="270f4-156">Nom de domaine complet du SBC</span><span class="sxs-lookup"><span data-stu-id="270f4-156">The FQDN name of the SBC</span></span> |<span data-ttu-id="270f4-157">Aucun</span><span class="sxs-lookup"><span data-stu-id="270f4-157">None</span></span>|<span data-ttu-id="270f4-158">Nom NoneFQDN, limiter 63 caractères</span><span class="sxs-lookup"><span data-stu-id="270f4-158">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="270f4-159">Chaîne, liste de caractères autorisés et non autorisés sur [les conventions d’appellation dans Active Directory pour les ordinateurs, domaines, sites et UO](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="270f4-159">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="270f4-160">Non</span><span class="sxs-lookup"><span data-stu-id="270f4-160">No</span></span>|<span data-ttu-id="270f4-161">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="270f4-161">MediaBypass</span></span> |<span data-ttu-id="270f4-162">Le paramètre indiqué par l’élément SBC prend en charge la dérivation multimédia et l’administrateur veut l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="270f4-162">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="270f4-163">Aucun</span><span class="sxs-lookup"><span data-stu-id="270f4-163">None</span></span>|<span data-ttu-id="270f4-164">Vrai</span><span class="sxs-lookup"><span data-stu-id="270f4-164">True</span></span><br/><span data-ttu-id="270f4-165">False</span><span class="sxs-lookup"><span data-stu-id="270f4-165">False</span></span>|<span data-ttu-id="270f4-166">Boolean</span><span class="sxs-lookup"><span data-stu-id="270f4-166">Boolean</span></span>|
|<span data-ttu-id="270f4-167">Oui</span><span class="sxs-lookup"><span data-stu-id="270f4-167">Yes</span></span>|<span data-ttu-id="270f4-168">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="270f4-168">SipSignallingPort</span></span> |<span data-ttu-id="270f4-169">Port d’écoute utilisé pour la communication avec les services de routage directe à l’aide du protocole TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="270f4-169">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="270f4-170">Aucun</span><span class="sxs-lookup"><span data-stu-id="270f4-170">None</span></span>|<span data-ttu-id="270f4-171">Tout port</span><span class="sxs-lookup"><span data-stu-id="270f4-171">Any port</span></span>|<span data-ttu-id="270f4-172">entre 0 et 65535</span><span class="sxs-lookup"><span data-stu-id="270f4-172">0 to 65535</span></span> |
|<span data-ttu-id="270f4-173">Non</span><span class="sxs-lookup"><span data-stu-id="270f4-173">No</span></span>|<span data-ttu-id="270f4-174">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="270f4-174">FailoverTimeSeconds</span></span> |<span data-ttu-id="270f4-175">Lorsque la valeur est définie sur 10 (valeur par défaut), les appels sortants pour lesquels la passerelle ne répond pas dans un délai de 10 secondes sont routés vers le Trunk disponible suivant ; s’il n’y a pas de lignes supplémentaires, l’appel est automatiquement interrompu.</span><span class="sxs-lookup"><span data-stu-id="270f4-175">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="270f4-176">Dans une organisation avec des réponses de passerelle ou réseau lentes, cela peut entraîner l’abandon de nombreux appels.</span><span class="sxs-lookup"><span data-stu-id="270f4-176">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="270f4-177">La valeur par défaut est 10.</span><span class="sxs-lookup"><span data-stu-id="270f4-177">The default value is 10.</span></span>|<span data-ttu-id="270f4-178">0,10</span><span class="sxs-lookup"><span data-stu-id="270f4-178">10</span></span>|<span data-ttu-id="270f4-179">Numéro</span><span class="sxs-lookup"><span data-stu-id="270f4-179">Number</span></span>|<span data-ttu-id="270f4-180">Ent</span><span class="sxs-lookup"><span data-stu-id="270f4-180">Int</span></span>|
|<span data-ttu-id="270f4-181">Non</span><span class="sxs-lookup"><span data-stu-id="270f4-181">No</span></span>|<span data-ttu-id="270f4-182">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="270f4-182">ForwardCallHistory</span></span> |<span data-ttu-id="270f4-183">Indique si les informations d’historique d’appel sont transférées par le biais de la jonction.</span><span class="sxs-lookup"><span data-stu-id="270f4-183">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="270f4-184">Si cette option est activée, le Proxy RTC Office 365 envoie deux en-têtes : History-Info et expertisé.</span><span class="sxs-lookup"><span data-stu-id="270f4-184">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="270f4-185">La valeur par défaut est **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="270f4-185">The default value is **False** ($False).</span></span> |<span data-ttu-id="270f4-186">False</span><span class="sxs-lookup"><span data-stu-id="270f4-186">False</span></span>|<span data-ttu-id="270f4-187">Vrai</span><span class="sxs-lookup"><span data-stu-id="270f4-187">True</span></span><br/><span data-ttu-id="270f4-188">False</span><span class="sxs-lookup"><span data-stu-id="270f4-188">False</span></span>|<span data-ttu-id="270f4-189">Boolean</span><span class="sxs-lookup"><span data-stu-id="270f4-189">Boolean</span></span>|
|<span data-ttu-id="270f4-190">Non</span><span class="sxs-lookup"><span data-stu-id="270f4-190">No</span></span>|<span data-ttu-id="270f4-191">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="270f4-191">ForwardPAI</span></span>|<span data-ttu-id="270f4-192">Indique si l’en-tête P-Asserted-Identity (PAI) sera transféré avec l’appel.</span><span class="sxs-lookup"><span data-stu-id="270f4-192">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="270f4-193">L’en-tête PAI permet de vérifier l’identité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="270f4-193">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="270f4-194">Si vous avez activé l’en-tête d’ID vie privée : il est également envoyé.</span><span class="sxs-lookup"><span data-stu-id="270f4-194">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="270f4-195">La valeur par défaut est **false** ($false).</span><span class="sxs-lookup"><span data-stu-id="270f4-195">The default value is **False** ($False).</span></span>|<span data-ttu-id="270f4-196">False</span><span class="sxs-lookup"><span data-stu-id="270f4-196">False</span></span>|<span data-ttu-id="270f4-197">Vrai</span><span class="sxs-lookup"><span data-stu-id="270f4-197">True</span></span><br/><span data-ttu-id="270f4-198">False</span><span class="sxs-lookup"><span data-stu-id="270f4-198">False</span></span>|<span data-ttu-id="270f4-199">Boolean</span><span class="sxs-lookup"><span data-stu-id="270f4-199">Boolean</span></span>|
|<span data-ttu-id="270f4-200">Non</span><span class="sxs-lookup"><span data-stu-id="270f4-200">No</span></span>|<span data-ttu-id="270f4-201">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="270f4-201">SendSIPOptions</span></span> |<span data-ttu-id="270f4-202">Définit si une SBC va ou non envoyer les options SIP.</span><span class="sxs-lookup"><span data-stu-id="270f4-202">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="270f4-203">S’il est désactivé, l’SBC sera exclu du système de surveillance et d’alerte.</span><span class="sxs-lookup"><span data-stu-id="270f4-203">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="270f4-204">Nous vous recommandons vivement d’activer les options SIP.</span><span class="sxs-lookup"><span data-stu-id="270f4-204">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="270f4-205">La valeur par défaut est **true**.</span><span class="sxs-lookup"><span data-stu-id="270f4-205">Default value is **True**.</span></span> |<span data-ttu-id="270f4-206">Vrai</span><span class="sxs-lookup"><span data-stu-id="270f4-206">True</span></span>|<span data-ttu-id="270f4-207">Vrai</span><span class="sxs-lookup"><span data-stu-id="270f4-207">True</span></span><br/><span data-ttu-id="270f4-208">False</span><span class="sxs-lookup"><span data-stu-id="270f4-208">False</span></span>|<span data-ttu-id="270f4-209">Boolean</span><span class="sxs-lookup"><span data-stu-id="270f4-209">Boolean</span></span>|
|<span data-ttu-id="270f4-210">Non</span><span class="sxs-lookup"><span data-stu-id="270f4-210">No</span></span>|<span data-ttu-id="270f4-211">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="270f4-211">MaxConcurrentSessions</span></span> |<span data-ttu-id="270f4-212">Utilisé par le système d’alerte.</span><span class="sxs-lookup"><span data-stu-id="270f4-212">Used by alerting system.</span></span> <span data-ttu-id="270f4-213">Lorsque n’importe quelle valeur est définie, le système d’alerte génère une alerte auprès de l’administrateur client lorsque le nombre de sessions simultanées est 90% ou une valeur supérieure à celle-ci.</span><span class="sxs-lookup"><span data-stu-id="270f4-213">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="270f4-214">Si paramètre n’est pas défini, les alertes ne le sont pas.</span><span class="sxs-lookup"><span data-stu-id="270f4-214">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="270f4-215">Toutefois, le système de surveillance rapportera le nombre de sessions simultanées toutes les 24 heures.</span><span class="sxs-lookup"><span data-stu-id="270f4-215">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="270f4-216">Valeur</span><span class="sxs-lookup"><span data-stu-id="270f4-216">Null</span></span>|<span data-ttu-id="270f4-217">Valeur</span><span class="sxs-lookup"><span data-stu-id="270f4-217">Null</span></span><br/><span data-ttu-id="270f4-218">1 à 100 000</span><span class="sxs-lookup"><span data-stu-id="270f4-218">1 to 100,000</span></span> ||
|<span data-ttu-id="270f4-219">Non</span><span class="sxs-lookup"><span data-stu-id="270f4-219">No</span></span>|<span data-ttu-id="270f4-220">MediaRelayRoutingLocationOverride</span><span class="sxs-lookup"><span data-stu-id="270f4-220">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="270f4-221">Permet de sélectionner manuellement le chemin pour le média.</span><span class="sxs-lookup"><span data-stu-id="270f4-221">Allows selecting path for media manually.</span></span> <span data-ttu-id="270f4-222">Le routage direct affecte un centre de contenus multimédia pour le chemin multimédia en fonction de l’adresse IP publique de l’SBC.</span><span class="sxs-lookup"><span data-stu-id="270f4-222">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="270f4-223">Nous cherchons toujours le plus près du centre de centres SBC.</span><span class="sxs-lookup"><span data-stu-id="270f4-223">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="270f4-224">Toutefois, dans certains cas, il est possible d’attribuer une adresse IP publique de la part d’une SBC située en Europe, par exemple.</span><span class="sxs-lookup"><span data-stu-id="270f4-224">However, in some cases a public IP from for example a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="270f4-225">Dans ce cas, nous n’utiliserons pas le chemin multimédia.</span><span class="sxs-lookup"><span data-stu-id="270f4-225">In this case we will be using not optimal media path.</span></span> <span data-ttu-id="270f4-226">Ce paramètre permet de définir manuellement la région préférée pour le trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="270f4-226">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="270f4-227">Nous vous conseillons de définir ce paramètre uniquement si les journaux d’appels indiquent clairement que l’attribution automatique du centre de fichiers de média pour le chemin multimédia n’affecte pas le plus proche au centre de médias SBC.</span><span class="sxs-lookup"><span data-stu-id="270f4-227">We only recommend setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="270f4-228">Aucun</span><span class="sxs-lookup"><span data-stu-id="270f4-228">None</span></span>|<span data-ttu-id="270f4-229">Codes de pays au format ISO</span><span class="sxs-lookup"><span data-stu-id="270f4-229">Country codes in ISO format</span></span>||
|<span data-ttu-id="270f4-230">Non</span><span class="sxs-lookup"><span data-stu-id="270f4-230">No</span></span>|<span data-ttu-id="270f4-231">Activé</span><span class="sxs-lookup"><span data-stu-id="270f4-231">Enabled</span></span>|<span data-ttu-id="270f4-232">Utilisé pour activer cet SBC pour les appels sortants.</span><span class="sxs-lookup"><span data-stu-id="270f4-232">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="270f4-233">Peut être utilisé pour supprimer temporairement l’SBC, pendant sa mise à jour ou lors de la maintenance.</span><span class="sxs-lookup"><span data-stu-id="270f4-233">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="270f4-234">False</span><span class="sxs-lookup"><span data-stu-id="270f4-234">False</span></span>|<span data-ttu-id="270f4-235">Vrai</span><span class="sxs-lookup"><span data-stu-id="270f4-235">True</span></span><br/><span data-ttu-id="270f4-236">False</span><span class="sxs-lookup"><span data-stu-id="270f4-236">False</span></span>|<span data-ttu-id="270f4-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="270f4-237">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="270f4-238">Vérifier le jumelage des SBC</span><span class="sxs-lookup"><span data-stu-id="270f4-238">Verify the SBC pairing</span></span> 

<span data-ttu-id="270f4-239">Vérifiez la connexion :</span><span class="sxs-lookup"><span data-stu-id="270f4-239">Verify the connection:</span></span> 
- <span data-ttu-id="270f4-240">Vérifiez si la SBC est sur la liste de SBCs couplés.</span><span class="sxs-lookup"><span data-stu-id="270f4-240">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="270f4-241">Valider les options SIP.</span><span class="sxs-lookup"><span data-stu-id="270f4-241">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="270f4-242">Vérifier si la SBC est sur la liste de SBCs couplés</span><span class="sxs-lookup"><span data-stu-id="270f4-242">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="270f4-243">Une fois que vous avez couplé l’SBC, validez la présence de l’SBC dans la liste des éléments SBCs couplés en exécutant la commande suivante dans une session PowerShell distante :`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="270f4-243">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="270f4-244">La passerelle couplée doit apparaître dans la liste, comme illustré dans l’exemple ci-dessous, et vérifier que le paramètre *Enabled* affiche la valeur **true**.</span><span class="sxs-lookup"><span data-stu-id="270f4-244">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="270f4-245">Spécifi</span><span class="sxs-lookup"><span data-stu-id="270f4-245">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="270f4-246">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="270f4-246">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="270f4-247">Valider le flux d’options SIP</span><span class="sxs-lookup"><span data-stu-id="270f4-247">Validate SIP Options flow</span></span> 

<span data-ttu-id="270f4-248">Pour valider le jumelage à l’aide des options SIP sortants, utilisez l’interface de gestion des SBC et confirmez que l’SBC reçoit les réponses 200 OK à ses messages d’OPTIONS sortants.</span><span class="sxs-lookup"><span data-stu-id="270f4-248">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="270f4-249">Lorsque le routage direct voit les OPTIONS entrantes, il commence à envoyer des messages d’options SIP sortants au nom de domaine complet SBC configuré dans le champ d’en-tête de contact du message OPTIONS entrantes.</span><span class="sxs-lookup"><span data-stu-id="270f4-249">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="270f4-250">Pour valider le jumelage à l’aide des options SIP entrantes, utilisez l’interface de gestion des SBC et voyez que l’SBC envoie une réponse aux messages d’OPTIONS provenant du routage direct et que le code de réponse qu’il envoie est 200 OK.</span><span class="sxs-lookup"><span data-stu-id="270f4-250">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="270f4-251">Activer les utilisateurs pour le service de routage direct</span><span class="sxs-lookup"><span data-stu-id="270f4-251">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="270f4-252">Lorsque vous êtes prêt à activer les utilisateurs pour le service de routage direct, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="270f4-252">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="270f4-253">Créez un utilisateur dans Office 365 et attribuez une licence de système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="270f4-253">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="270f4-254">Assurez-vous que l’utilisateur est bien immobilier dans Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="270f4-254">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="270f4-255">Configurez le numéro de téléphone et activez voix entreprise et boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="270f4-255">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="270f4-256">Configurer le routage de la voix.</span><span class="sxs-lookup"><span data-stu-id="270f4-256">Configure voice routing.</span></span> <span data-ttu-id="270f4-257">L’itinéraire est validé automatiquement.</span><span class="sxs-lookup"><span data-stu-id="270f4-257">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="270f4-258">Créer un utilisateur dans Office 365 et affecter la licence</span><span class="sxs-lookup"><span data-stu-id="270f4-258">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="270f4-259">Deux options s’offrent à vous pour créer un utilisateur dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="270f4-259">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="270f4-260">Toutefois, nous recommandons que votre organisation sélectionne et utilise une option pour éviter les problèmes de routage :</span><span class="sxs-lookup"><span data-stu-id="270f4-260">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="270f4-261">Créer l’utilisateur dans l’annuaire Active Directory local et synchroniser l’utilisateur avec le Cloud.</span><span class="sxs-lookup"><span data-stu-id="270f4-261">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="270f4-262">Voir [intégrer vos annuaires locaux avec Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="270f4-262">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="270f4-263">Créer l’utilisateur directement dans le portail d’administration Office 365.</span><span class="sxs-lookup"><span data-stu-id="270f4-263">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="270f4-264">Pour plus d' [informations, voir ajouter des utilisateurs individuellement ou en bloc à Office 365-aide de l’administrateur](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="270f4-264">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="270f4-265">Si votre déploiement de Skype entreprise Online co-existe avec Skype entreprise 2015 ou Lync 2010/2013 local, la seule option prise en charge consiste à créer l’utilisateur dans Active Directory local et à synchroniser l’utilisateur dans le Cloud (option 1).</span><span class="sxs-lookup"><span data-stu-id="270f4-265">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="270f4-266">Licences requises :</span><span class="sxs-lookup"><span data-stu-id="270f4-266">Required licenses:</span></span> 

- <span data-ttu-id="270f4-267">Office 365 entreprise E3 (y compris marketing Plan2, Exchange Plan2 et Teams) + Téléphone</span><span class="sxs-lookup"><span data-stu-id="270f4-267">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>
- <span data-ttu-id="270f4-268">Office 365 entreprise E5 (y compris marketing Plan2, Exchange Plan2, équipes et système téléphonique)</span><span class="sxs-lookup"><span data-stu-id="270f4-268">Office 365 Enterprise E5 (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="270f4-269">Licences facultatives :</span><span class="sxs-lookup"><span data-stu-id="270f4-269">Optional licenses:</span></span> 

- <span data-ttu-id="270f4-270">Forfait d’appels</span><span class="sxs-lookup"><span data-stu-id="270f4-270">Calling Plan</span></span> 
- <span data-ttu-id="270f4-271">Audioconférence,</span><span class="sxs-lookup"><span data-stu-id="270f4-271">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="270f4-272">Vérifier que l’utilisateur est bien immobilier dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="270f4-272">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="270f4-273">Le routage direct nécessite que l’utilisateur soit hébergé dans Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="270f4-273">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="270f4-274">Pour cela, vous pouvez consulter le paramètre RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="270f4-274">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="270f4-275">Il doit avoir une valeur dans le domaine infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="270f4-275">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="270f4-276">Connectez-vous à Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="270f4-276">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="270f4-277">Émettez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="270f4-277">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="270f4-278">Configuration du numéro de téléphone et activation de la voix et de la boîte vocale entreprise</span><span class="sxs-lookup"><span data-stu-id="270f4-278">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="270f4-279">Une fois que vous avez créé l’utilisateur et attribué une licence, l’étape suivante consiste à configurer son numéro de téléphone et sa boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="270f4-279">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="270f4-280">Cette opération peut être réalisée en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="270f4-280">This can be done in one step.</span></span> 

<span data-ttu-id="270f4-281">Pour ajouter le numéro de téléphone et l’activer pour la boîte vocale, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="270f4-281">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="270f4-282">Se connecter à une session PowerShell distante.</span><span class="sxs-lookup"><span data-stu-id="270f4-282">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="270f4-283">Entrez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="270f4-283">Enter the command:</span></span> 
 
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
```

<span data-ttu-id="270f4-284">Par exemple, pour ajouter un numéro de téléphone pour l’utilisateur « Beaune Low », entrez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="270f4-284">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

```
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="270f4-285">Le numéro de téléphone utilisé doit être configuré en tant que numéro de téléphone avec l’indicatif du pays.</span><span class="sxs-lookup"><span data-stu-id="270f4-285">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="270f4-286">Si le numéro de téléphone de l’utilisateur est géré en local, utilisez l’interpréteur de commandes ou le panneau de configuration Skype entreprise local pour configurer le numéro de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="270f4-286">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="270f4-287">Configurer le routage de la voix</span><span class="sxs-lookup"><span data-stu-id="270f4-287">Configure Voice Routing</span></span> 

<span data-ttu-id="270f4-288">Le système Microsoft Phone possède un mécanisme de routage qui permet d’envoyer un appel à un SBC spécifique en fonction de :</span><span class="sxs-lookup"><span data-stu-id="270f4-288">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="270f4-289">Modèle de nombre appelé</span><span class="sxs-lookup"><span data-stu-id="270f4-289">Called number pattern</span></span> 
- <span data-ttu-id="270f4-290">Appel de modèle de numéro + utilisateur spécifique qui effectue l’appel</span><span class="sxs-lookup"><span data-stu-id="270f4-290">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="270f4-291">SBCs peut être désignée comme active et Backup.</span><span class="sxs-lookup"><span data-stu-id="270f4-291">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="270f4-292">Cela signifie que lorsque l’SBC configuré comme étant actif pour ce modèle de nombre, ou un modèle de nombre (utilisateur spécifique) n’est pas disponible, les appels sont dirigés vers un SBC de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="270f4-292">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="270f4-293">Le routage des appels se compose des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="270f4-293">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="270f4-294">Politique de routage de la voix-conteneur d’utilisation PSTN ; peuvent être affectés à un utilisateur ou à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="270f4-294">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="270f4-295">Usages PSTN : conteneur des itinéraires vocaux et des utilisations PSTN ; peuvent être partagés dans différentes politiques de routage vocal</span><span class="sxs-lookup"><span data-stu-id="270f4-295">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="270f4-296">Itinéraires vocaux : modèle numérique et ensemble de passerelles RTC en ligne à utiliser pour les appels dans lesquels le numéro de téléphone correspond au modèle</span><span class="sxs-lookup"><span data-stu-id="270f4-296">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="270f4-297">Passerelle RTC en ligne-pointeur vers une SBC, qui stocke également la configuration appliquée lors de l’appel via SBC, telle que l’envoi d’identité P-assertion (PAI) ou de codecs préférés. peuvent être ajoutés aux itinéraires vocaux</span><span class="sxs-lookup"><span data-stu-id="270f4-297">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="270f4-298">Création d’une stratégie de routage de la voix avec une utilisation PSTN</span><span class="sxs-lookup"><span data-stu-id="270f4-298">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="270f4-299">Le schéma suivant montre deux exemples de stratégies de routage de voix dans le flux d’appels.</span><span class="sxs-lookup"><span data-stu-id="270f4-299">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="270f4-300">**Flux d’appels 1 (à gauche) :** Si un utilisateur effectue un appel vers + 1 425 XXX XX XX ou + 1 206 XXX XX XX, l’appel est acheminé vers SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="270f4-300">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="270f4-301">Si les sbc1.contoso.biz et sbc2.contoso.biz ne sont pas disponibles, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="270f4-301">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="270f4-302">**Flux d’appels 2 (sur la droite) :** Si un utilisateur effectue un appel vers + 1 425 XX XX XX ou + 1 206 XXX XX XX, l’appel est d’abord routé vers SBC sbc1.contoso.biz ou sbc2.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="270f4-302">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="270f4-303">Si aucun SBC n’est disponible, l’itinéraire dont la priorité est faible est essayé (sbc3.contoso.biz et sbc4.contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="270f4-303">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="270f4-304">Si aucune des SBCs n’est disponible, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="270f4-304">If none of the SBCs are available, the call is dropped.</span></span> 

![Exemples de stratégies de routage vocale](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="270f4-306">Dans les deux exemples, si les priorités de l’itinéraire vocal sont affectées, les éléments SBCs dans les itinéraires sont essayés dans un ordre aléatoire.</span><span class="sxs-lookup"><span data-stu-id="270f4-306">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="270f4-307">À moins que l’utilisateur ne dispose d’une licence de plan d’appel Microsoft, les appels vers n’importe quel numéro, à l’exception des numéros correspondant aux modèles + 1 425 XXX XX XX ou + 1 206 XXX XX XX dans l’exemple de configuration sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="270f4-307">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="270f4-308">Si l’utilisateur dispose d’une licence de plan d’appel, l’appel est automatiquement acheminé conformément aux politiques du forfait d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="270f4-308">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="270f4-309">Le plan d’appel Microsoft s’applique automatiquement en tant que dernier itinéraire à tous les utilisateurs dotés de la licence de plan d’appel Microsoft et ne nécessite pas de configuration du routage des appels supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="270f4-309">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="270f4-310">Dans l’exemple ci-dessous, un itinéraire vocal est ajouté pour envoyer les appels vers tous les autres États-Unis et le numéro canadien (appels vers le modèle de numéro + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="270f4-310">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Affiche la politique de routage téléphonique avec un troisième itinéraire](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="270f4-312">Pour tous les autres appels, si un utilisateur possède les deux licences (système Microsoft Phone et forfait d’appel Microsoft), un itinéraire automatique est utilisé.</span><span class="sxs-lookup"><span data-stu-id="270f4-312">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="270f4-313">S’il ne correspond pas aux modèles de nombre dans les itinéraires vocaux en ligne créés par l’administrateur, route via un forfait d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="270f4-313">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="270f4-314">Si l’utilisateur dispose uniquement du système Microsoft Phone, l’appel est abandonné, car aucune règle de correspondance n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="270f4-314">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="270f4-315">La valeur de priorité pour l’itinéraire « Other + 1 » n’a pas d’importance dans ce cas, car il n’y a qu’un seul itinéraire correspondant au modèle + 1 XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="270f4-315">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="270f4-316">Si un utilisateur effectue un appel à + 1 324 567 89 89 et que les sbc5.contoso.biz et sbc6.contoso.biz ne sont pas disponibles, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="270f4-316">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="270f4-317">Le tableau suivant résume la configuration à l’aide de trois itinéraires vocaux.</span><span class="sxs-lookup"><span data-stu-id="270f4-317">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="270f4-318">Dans cet exemple, les trois itinéraires font partie de la même utilisation PSTN « États-Unis et Canada ».</span><span class="sxs-lookup"><span data-stu-id="270f4-318">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="270f4-319">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="270f4-319">**PSTN usage**</span></span>|<span data-ttu-id="270f4-320">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="270f4-320">**Voice route**</span></span>|<span data-ttu-id="270f4-321">**Schéma de numéro**</span><span class="sxs-lookup"><span data-stu-id="270f4-321">**Number pattern**</span></span>|<span data-ttu-id="270f4-322">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="270f4-322">**Priority**</span></span>|<span data-ttu-id="270f4-323">**SBC**</span><span class="sxs-lookup"><span data-stu-id="270f4-323">**SBC**</span></span>|<span data-ttu-id="270f4-324">**Description**</span><span class="sxs-lookup"><span data-stu-id="270f4-324">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="270f4-325">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="270f4-325">US only</span></span>|<span data-ttu-id="270f4-326">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="270f4-326">"Redmond 1"</span></span>|<span data-ttu-id="270f4-327">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="270f4-327">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="270f4-328">1</span><span class="sxs-lookup"><span data-stu-id="270f4-328">1</span></span>|<span data-ttu-id="270f4-329">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="270f4-329">sbc1.contoso.biz</span></span><br/><span data-ttu-id="270f4-330">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="270f4-330">sbc2.contoso.biz</span></span>|<span data-ttu-id="270f4-331">Itinéraire actif pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="270f4-331">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="270f4-332">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="270f4-332">US only</span></span>|<span data-ttu-id="270f4-333">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="270f4-333">"Redmond 2"</span></span>|<span data-ttu-id="270f4-334">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="270f4-334">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="270f4-335">2</span><span class="sxs-lookup"><span data-stu-id="270f4-335">2</span></span>|<span data-ttu-id="270f4-336">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="270f4-336">sbc3.contoso.biz</span></span><br/><span data-ttu-id="270f4-337">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="270f4-337">sbc4.contoso.biz</span></span>|<span data-ttu-id="270f4-338">Itinéraire de sauvegarde pour les numéros appelés + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="270f4-338">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="270f4-339">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="270f4-339">US only</span></span>|<span data-ttu-id="270f4-340">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="270f4-340">"Other +1"</span></span>|<span data-ttu-id="270f4-341">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="270f4-341">^\\+1(\d{10})$</span></span>|<span data-ttu-id="270f4-342">3</span><span class="sxs-lookup"><span data-stu-id="270f4-342">3</span></span>|<span data-ttu-id="270f4-343">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="270f4-343">sbc5.contoso.biz</span></span><br/><span data-ttu-id="270f4-344">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="270f4-344">sbc6.contoso.biz</span></span>|<span data-ttu-id="270f4-345">Itinéraire pour les numéros appelés + 1 XXX XXX XX XX (sauf + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="270f4-345">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="270f4-346">Tous les itinéraires sont associés à l’utilisation RTC « États-Unis et Canada » et l’utilisation RTC est associée à la politique de routage de la voix « États-Unis uniquement ».</span><span class="sxs-lookup"><span data-stu-id="270f4-346">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="270f4-347">Dans cet exemple, la stratégie de routage de la voix est affectée à user Spencer Low.</span><span class="sxs-lookup"><span data-stu-id="270f4-347">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="270f4-348">Exemples d’itinéraires d’appels</span><span class="sxs-lookup"><span data-stu-id="270f4-348">Examples of call routes</span></span>

<span data-ttu-id="270f4-349">Dans l’exemple suivant, nous montrons comment configurer des itinéraires, des utilisations RTC et des stratégies de routage, et nous affectons la stratégie à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="270f4-349">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="270f4-350">**Étape 1 :** Créez l’utilisation RTC « États-Unis et Canada ».</span><span class="sxs-lookup"><span data-stu-id="270f4-350">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="270f4-351">Dans une session PowerShell distante Skype entreprise, tapez :</span><span class="sxs-lookup"><span data-stu-id="270f4-351">In a Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="270f4-352">Vérifiez que l’utilisation a été créée en entrant :</span><span class="sxs-lookup"><span data-stu-id="270f4-352">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="270f4-353">Qui renvoie une liste de noms qui risquent d’être tronqués :</span><span class="sxs-lookup"><span data-stu-id="270f4-353">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="270f4-354">Dans l’exemple ci-dessous, vous pouvez voir le résultat de l’exécution de `(Get-CSOnlinePSTNUsage).usage` la commande PowerShell pour afficher les noms complets (sans troncature).</span><span class="sxs-lookup"><span data-stu-id="270f4-354">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span> 
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

<span data-ttu-id="270f4-355">**Étape 2 :** Dans une session PowerShell dans Skype entreprise Online, créez trois itinéraires : Redmond 1, Redmond 2 et autres + 1, comme décrit dans le tableau précédent.</span><span class="sxs-lookup"><span data-stu-id="270f4-355">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="270f4-356">Pour créer l’itinéraire « Redmond 1 », entrez :</span><span class="sxs-lookup"><span data-stu-id="270f4-356">To create the "Redmond 1" route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="270f4-357">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="270f4-357">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority            : 1
Description         :
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
</pre>
<span data-ttu-id="270f4-358">Pour créer l’itinéraire de Redmond 2, entrez :</span><span class="sxs-lookup"><span data-stu-id="270f4-358">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="270f4-359">Pour créer l’autre itinéraire + 1, entrez :</span><span class="sxs-lookup"><span data-stu-id="270f4-359">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="270f4-360">Assurez-vous que votre expression régulière dans l’attribut NumberPattern est une expression valide.</span><span class="sxs-lookup"><span data-stu-id="270f4-360">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="270f4-361">Vous pouvez le tester à l’aide du site Web suivant :[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="270f4-361">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="270f4-362">Dans certains cas, il est nécessaire de router tous les appels vers le même SBC ; Utilisez-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="270f4-362">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

- <span data-ttu-id="270f4-363">Acheminer tous les appels vers le même SBC</span><span class="sxs-lookup"><span data-stu-id="270f4-363">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="270f4-364">Vérifiez que vous avez correctement configuré l’itinéraire en exécutant la `Get-CSOnlineVoiceRoute` commande PowerShell en utilisant les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="270f4-364">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="270f4-365">Qui doit retourner :</span><span class="sxs-lookup"><span data-stu-id="270f4-365">Which should return:</span></span>
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

<span data-ttu-id="270f4-366">Dans l’exemple, l’itinéraire « Other + 1 » a automatiquement la priorité 4.</span><span class="sxs-lookup"><span data-stu-id="270f4-366">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="270f4-367">**Étape 3 :** Créez une stratégie de routage de la voix « États-Unis uniquement » et ajoutez-la à la politique « États-Unis et Canada ».</span><span class="sxs-lookup"><span data-stu-id="270f4-367">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="270f4-368">Dans une session PowerShell dans Skype entreprise Online, tapez :</span><span class="sxs-lookup"><span data-stu-id="270f4-368">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="270f4-369">Le résultat est affiché dans cet exemple :</span><span class="sxs-lookup"><span data-stu-id="270f4-369">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="270f4-370">**Étape 4 :** Accordez à l’utilisateur la politique de routage de la voix de faible utilisation par PowerShell.</span><span class="sxs-lookup"><span data-stu-id="270f4-370">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="270f4-371">Dans une session PowerShell dans Skype entreprise Online, tapez :</span><span class="sxs-lookup"><span data-stu-id="270f4-371">In a PowerShell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="270f4-372">Validez l’affectation de stratégie en entrant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="270f4-372">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="270f4-373">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="270f4-373">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="270f4-374">Création d’une stratégie de routage de la voix avec plusieurs utilisations PSTN</span><span class="sxs-lookup"><span data-stu-id="270f4-374">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="270f4-375">La politique de routage vocale créée auparavant n’autorise que les appels vers des numéros de téléphone aux États-Unis et au Canada, sauf si la licence de plan d’appel Microsoft est également affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="270f4-375">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="270f4-376">Dans l’exemple qui suit, vous pouvez créer la stratégie de routage téléphonique « aucune restriction ».</span><span class="sxs-lookup"><span data-stu-id="270f4-376">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="270f4-377">La stratégie réutilise l’utilisation RTC « États-Unis et Canada » créée dans l’exemple précédent, ainsi que la nouvelle utilisation RTC « international ».</span><span class="sxs-lookup"><span data-stu-id="270f4-377">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="270f4-378">Cela achemine tous les autres appels vers l’SBCs sbc2.contoso.biz et sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="270f4-378">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="270f4-379">Les exemples qui s’affichent affectent la politique américaine uniquement à l’utilisateur « Beaune Low » et aucune restriction à l’utilisateur « Jean bois ».</span><span class="sxs-lookup"><span data-stu-id="270f4-379">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="270f4-380">Spencer Low – appels uniquement autorisés vers les États-Unis et le Canada.</span><span class="sxs-lookup"><span data-stu-id="270f4-380">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="270f4-381">Lorsque vous appelez la gamme de numéros Redmond, l’ensemble spécifique de SBC doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="270f4-381">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="270f4-382">Les numéros non US ne seront pas routés sauf si la licence de plan d’appel est affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="270f4-382">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="270f4-383">Jean bois – appels autorisés vers n’importe quel numéro.</span><span class="sxs-lookup"><span data-stu-id="270f4-383">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="270f4-384">Lorsque vous appelez la gamme de numéros Redmond, l’ensemble spécifique de SBC doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="270f4-384">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="270f4-385">Les numéros non US seront routés par le biais de sbc2.contoso.biz et sbc5.contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="270f4-385">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![Affiche la politique de routage vocale affectée à l’utilisateur Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="270f4-387">Pour tous les autres appels, si un utilisateur possède les deux licences (système Microsoft Phone et forfait d’appel Microsoft), un itinéraire automatique est utilisé.</span><span class="sxs-lookup"><span data-stu-id="270f4-387">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="270f4-388">S’il ne correspond pas aux modèles de nombre dans les itinéraires vocaux en ligne créés par l’administrateur, route via un forfait d’appel Microsoft.</span><span class="sxs-lookup"><span data-stu-id="270f4-388">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="270f4-389">Si l’utilisateur dispose uniquement du système Microsoft Phone, l’appel est abandonné, car aucune règle de correspondance n’est disponible.</span><span class="sxs-lookup"><span data-stu-id="270f4-389">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Politique de routage de la voix attribuée à l’utilisateur Jean bois](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="270f4-391">Le tableau suivant récapitule les concepteurs d’utilisation et les itinéraires vocaux de la stratégie de routage « aucune restriction ».</span><span class="sxs-lookup"><span data-stu-id="270f4-391">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="270f4-392">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="270f4-392">**PSTN usage**</span></span>|<span data-ttu-id="270f4-393">**Route vocale**</span><span class="sxs-lookup"><span data-stu-id="270f4-393">**Voice route**</span></span>|<span data-ttu-id="270f4-394">**Schéma de numéro**</span><span class="sxs-lookup"><span data-stu-id="270f4-394">**Number pattern**</span></span>|<span data-ttu-id="270f4-395">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="270f4-395">**Priority**</span></span>|<span data-ttu-id="270f4-396">**SBC**</span><span class="sxs-lookup"><span data-stu-id="270f4-396">**SBC**</span></span>|<span data-ttu-id="270f4-397">**Description**</span><span class="sxs-lookup"><span data-stu-id="270f4-397">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="270f4-398">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="270f4-398">US Only</span></span>|<span data-ttu-id="270f4-399">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="270f4-399">"Redmond 1"</span></span>|<span data-ttu-id="270f4-400">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="270f4-400">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="270f4-401">1</span><span class="sxs-lookup"><span data-stu-id="270f4-401">1</span></span>|<span data-ttu-id="270f4-402">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="270f4-402">sbc1.contoso.biz</span></span><br/><span data-ttu-id="270f4-403">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="270f4-403">sbc2.contoso.biz</span></span>|<span data-ttu-id="270f4-404">Itinéraire actif pour les numéros d’appelant + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="270f4-404">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="270f4-405">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="270f4-405">US Only</span></span>|<span data-ttu-id="270f4-406">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="270f4-406">"Redmond 2"</span></span>|<span data-ttu-id="270f4-407">^\\+ 1 (425\|206) (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="270f4-407">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="270f4-408">2</span><span class="sxs-lookup"><span data-stu-id="270f4-408">2</span></span>|<span data-ttu-id="270f4-409">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="270f4-409">sbc3.contoso.biz</span></span><br/><span data-ttu-id="270f4-410">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="270f4-410">sbc4.contoso.biz</span></span>|<span data-ttu-id="270f4-411">Itinéraire de sauvegarde pour les numéros des appelants + 1 425 XXX XX XX ou + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="270f4-411">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="270f4-412">États-Unis uniquement</span><span class="sxs-lookup"><span data-stu-id="270f4-412">US Only</span></span>|<span data-ttu-id="270f4-413">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="270f4-413">"Other +1"</span></span>|<span data-ttu-id="270f4-414">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="270f4-414">^\\+1(\d{10})$</span></span>|<span data-ttu-id="270f4-415">3</span><span class="sxs-lookup"><span data-stu-id="270f4-415">3</span></span>|<span data-ttu-id="270f4-416">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="270f4-416">sbc5.contoso.biz</span></span><br/><span data-ttu-id="270f4-417">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="270f4-417">sbc6>.contoso.biz</span></span>|<span data-ttu-id="270f4-418">Itinéraire pour les numéros d’appelant + 1 XXX XXX XX XX (sauf + 1 425 XXX XX XX ou + 1 206 XXX XX XX)</span><span class="sxs-lookup"><span data-stu-id="270f4-418">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="270f4-419">International</span><span class="sxs-lookup"><span data-stu-id="270f4-419">International</span></span>|<span data-ttu-id="270f4-420">International</span><span class="sxs-lookup"><span data-stu-id="270f4-420">International</span></span>|<span data-ttu-id="270f4-421">\d +</span><span class="sxs-lookup"><span data-stu-id="270f4-421">\d+</span></span>|<span data-ttu-id="270f4-422">4</span><span class="sxs-lookup"><span data-stu-id="270f4-422">4</span></span>|<span data-ttu-id="270f4-423">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="270f4-423">sbc2.contoso.biz</span></span><br/><span data-ttu-id="270f4-424">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="270f4-424">sbc5.contoso.biz</span></span>|<span data-ttu-id="270f4-425">Itinéraire pour n’importe quel modèle numérique</span><span class="sxs-lookup"><span data-stu-id="270f4-425">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="270f4-426">L’ordre des utilisations RTC dans les stratégies de routage vocale est essentiel.</span><span class="sxs-lookup"><span data-stu-id="270f4-426">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="270f4-427">Les utilisations sont appliquées dans l’ordre et, si une correspondance est trouvée dans la première utilisation, les autres utilisations ne sont jamais évaluées.</span><span class="sxs-lookup"><span data-stu-id="270f4-427">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="270f4-428">L’utilisation RTC « international » doit être placée après l’utilisation RTC « États-Unis uniquement ».</span><span class="sxs-lookup"><span data-stu-id="270f4-428">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="270f4-429">Pour modifier l’ordre des utilisations RTC, exécutez la `Set-CSOnlineVoiceRoutingPolicy` commande.</span><span class="sxs-lookup"><span data-stu-id="270f4-429">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="270f4-430">Par exemple, pour passer de l’ordre « États-Unis et Canada » et inversement, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="270f4-430">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="270f4-431">Le niveau de priorité des itinéraires vocaux « Other + 1 » et « international » est automatiquement attribué.</span><span class="sxs-lookup"><span data-stu-id="270f4-431">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="270f4-432">Il n’y a pas d’importance tant qu’il dispose de priorités inférieures à « Redmond 1 » et « Redmond 2 ».</span><span class="sxs-lookup"><span data-stu-id="270f4-432">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="270f4-433">Exemple de politique de routage vocale pour les bois des utilisateurs de Jean</span><span class="sxs-lookup"><span data-stu-id="270f4-433">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="270f4-434">Les étapes à suivre pour créer une utilisation PSTN « international », un itinéraire vocal « international », « stratégie de routage vocale » n’est pas soumis à des restrictions», puis l’affecter à l’utilisateur « Jean bois » est le suivant.</span><span class="sxs-lookup"><span data-stu-id="270f4-434">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>


1. <span data-ttu-id="270f4-435">Tout d’abord, créez l’utilisation RTC « international ».</span><span class="sxs-lookup"><span data-stu-id="270f4-435">First, create the PSTN Usage "International."</span></span> <span data-ttu-id="270f4-436">Dans une session PowerShell distante dans Skype entreprise Online, entrez :</span><span class="sxs-lookup"><span data-stu-id="270f4-436">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

   ```
   Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
   ```

2. <span data-ttu-id="270f4-437">Ensuite, créez le nouveau message vocal « international ».</span><span class="sxs-lookup"><span data-stu-id="270f4-437">Next, create the new voice route "International."</span></span>

   ```
   New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
   ```
   <span data-ttu-id="270f4-438">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="270f4-438">Which returns:</span></span>

   <pre>
   Identity                  : International 
   Priority                      : 5
   Description                   : 
   NumberPattern                 : .*
   OnlinePstnUsages          : {International} 
   OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
   Name                            : International
   </pre>
3. <span data-ttu-id="270f4-439">Ensuite, créez une stratégie de routage téléphonique « aucune restriction ».</span><span class="sxs-lookup"><span data-stu-id="270f4-439">Next, create a Voice Routing Policy "No Restrictions".</span></span> <span data-ttu-id="270f4-440">L’utilisation RTC « Redmond 1 » et « Redmond » sont réutilisées dans cette politique de routage vocale pour garantir une gestion spéciale des appels au numéro « + 1 425 XXX XX XX » et « + 1 206 XXX XX XX » en tant qu’appels locaux ou locaux.</span><span class="sxs-lookup"><span data-stu-id="270f4-440">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

    Take note of the order of PSTN Usages:

    a. If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied. That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes. 

    b.  If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"```

   <span data-ttu-id="270f4-441">Qui renvoie</span><span class="sxs-lookup"><span data-stu-id="270f4-441">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4. <span data-ttu-id="270f4-442">Attribuez la politique de routage de la voix à l’utilisateur « Jean bois » à l’aide de la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="270f4-442">Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

   ```
   Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
   ```

   <span data-ttu-id="270f4-443">Vérifiez ensuite le devoir à l’aide de la commande :</span><span class="sxs-lookup"><span data-stu-id="270f4-443">Then verify the assignment using the command:</span></span> 

   ```
   Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
   ```
   <span data-ttu-id="270f4-444">Qui renvoie :</span><span class="sxs-lookup"><span data-stu-id="270f4-444">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="270f4-445">Le résultat est que la stratégie vocale appliquée aux appels de Jean-Martin n’est pas restreinte et qu’elle respecte la logique du routage des appels disponible aux États-Unis, au Canada et au service d’appels internationaux.</span><span class="sxs-lookup"><span data-stu-id="270f4-445">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="270f4-446">Attribuer le mode d’affectation uniquement aux utilisateurs pour s’assurer des appels terrestres dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="270f4-446">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="270f4-447">Le routage direct exige que les utilisateurs soient en mode d’équipe uniquement pour s’assurer que les appels entrants sont présents dans le client Teams.</span><span class="sxs-lookup"><span data-stu-id="270f4-447">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="270f4-448">Pour faire en sorte que les utilisateurs en mode équipes uniquement, attribuez-leur l’instance « UpgradeToTeams » de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="270f4-448">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="270f4-449">Si votre organisation utilise Skype entreprise Server ou Skype entreprise Online, reportez-vous à l’article suivant pour l’interopérabilité des informations entre Skype et teams : [instructions de migration et d’interopérabilité pour les entreprises utilisant teams conjointement avec Skype pour les entreprises](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="270f4-449">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information interoperability between Skype and Teams: [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="270f4-450">Configurer l’envoi d’appels directement à la boîte vocale</span><span class="sxs-lookup"><span data-stu-id="270f4-450">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="270f4-451">Le routage direct vous permet de mettre fin à l’appel d’un utilisateur et de l’envoyer directement à la boîte vocale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="270f4-451">Direct Routing allows you to end the call to a user and send it directly to the users' voicemail.</span></span> <span data-ttu-id="270f4-452">Si vous voulez envoyer l’appel directement à la boîte vocale, attachez opaque = application : boîte vocale dans l’en-tête de demande d’URI.</span><span class="sxs-lookup"><span data-stu-id="270f4-452">If you want to send the call directly to voicemail, please attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="270f4-453">Par exemple, « SIP : user@yourdomain.com ; opaque = application : boîte vocale ».</span><span class="sxs-lookup"><span data-stu-id="270f4-453">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span>
<span data-ttu-id="270f4-454">Si tel est le cas, l’utilisateur teams n’aura pas reçu la notification d’appel, l’appel est alors directement connecté à la messagerie vocale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="270f4-454">In this case the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="see-also"></a><span data-ttu-id="270f4-455">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="270f4-455">See also</span></span>

[<span data-ttu-id="270f4-456">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="270f4-456">Plan Direct Routing</span></span>](direct-routing-plan.md)
