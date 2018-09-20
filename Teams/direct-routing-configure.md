---
title: Configurer le routage Direct
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: ''
description: Découvrez comment configurer le routage Direct de Microsoft Phone System.
ms.openlocfilehash: 7c33b6fcc2b903a656215d106ca3e89df6aa2f8e
ms.sourcegitcommit: 3a7d2131717327d9b2d16848758e31e10326a0bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/20/2018
ms.locfileid: "24057654"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="4325b-103">Configurer le routage Direct</span><span class="sxs-lookup"><span data-stu-id="4325b-103">Configure Direct Routing</span></span>

<span data-ttu-id="4325b-104">Si vous n’avez pas déjà fait, lisez la [Planifier le routage Direct](direct-routing-plan.md) pour les composants requis et pour passer en revue les autres étapes, vous devrez prendre avant de configurer votre réseau de système téléphonique de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4325b-104">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review  other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="4325b-105">Cet article explique comment configurer le routage Direct de Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="4325b-105">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="4325b-106">Il décrit en détail comment associer un contrôleur de bordure Session pris en charge (SBC) pour le routage Direct et configurer les utilisateurs de Microsoft Teams pour utiliser le routage directe pour se connecter à la Public téléphone réseau commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="4325b-106">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="4325b-107">Pour effectuer les étapes décrites dans cet article, les administrateurs doivent se familiariser avec les applets de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4325b-107">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="4325b-108">Pour plus d’informations sur l’utilisation de PowerShell, voir [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="4325b-108">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="4325b-109">Nous vous recommandons de vérifier que votre contrôleur SBC a déjà été configuré comme recommandé par votre fournisseur SBC :</span><span class="sxs-lookup"><span data-stu-id="4325b-109">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor's:</span></span> 

- <span data-ttu-id="4325b-110">Documentation de déploiement AudioCodes</span><span class="sxs-lookup"><span data-stu-id="4325b-110">AudioCodes deployment documentation</span></span> 
- <span data-ttu-id="4325b-111">Documentation de déploiement de Communications de ruban</span><span class="sxs-lookup"><span data-stu-id="4325b-111">Ribbon Communications deployment documentation</span></span>

<span data-ttu-id="4325b-112">Vous pouvez configurer votre système téléphonique de Microsoft et permettre aux utilisateurs d’utiliser le routage Direct, puis configurer Teams Microsoft en tant que client appelant par défaut en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="4325b-112">You can configure your Microsoft Phone System and enable  users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="4325b-113">Paire le contrôleur SBC avec un système téléphonique de Microsoft et valider l’appariement</span><span class="sxs-lookup"><span data-stu-id="4325b-113">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-direct-routing-service-of-phone-system)
- [<span data-ttu-id="4325b-114">Activer les utilisateurs pour le Service de routage Direct</span><span class="sxs-lookup"><span data-stu-id="4325b-114">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="4325b-115">Assurez-vous que Microsoft Teams est le client appelant par défaut pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4325b-115">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-users) 

## <a name="pair-the-sbc-to-direct-routing-service-of-phone-system"></a><span data-ttu-id="4325b-116">Paire le contrôleur SBC pour diriger le Service de routage du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="4325b-116">Pair the SBC to Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="4325b-117">Voici les trois étapes principales pour vous permettre de vous connecter, ou paire, le contrôleur SBC à l’interface de routage Direct :</span><span class="sxs-lookup"><span data-stu-id="4325b-117">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="4325b-118">Se connecter au centre d’administration de **Skype pour Business Online** à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="4325b-118">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="4325b-119">Paire le contrôleur SBC</span><span class="sxs-lookup"><span data-stu-id="4325b-119">Pair the SBC</span></span> 
- <span data-ttu-id="4325b-120">Valider l’appariement</span><span class="sxs-lookup"><span data-stu-id="4325b-120">Validate the pairing</span></span> 

### <a name="connect-to--skype-for-business-online-by-using-powershell"></a><span data-ttu-id="4325b-121">Se connecter à Skype pour Business Online à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="4325b-121">Connect to  Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="4325b-122">Vous pouvez utiliser une session PowerShell connectée au client pour le couplage le contrôleur SBC à l’interface de routage Direct.</span><span class="sxs-lookup"><span data-stu-id="4325b-122">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="4325b-123">Pour ouvrir une session PowerShell, suivez les étapes décrites dans la [configuration de votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="4325b-123">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="4325b-124">Après avoir établi une session PowerShell distante, vérifiez que vous pouvez voir les commandes pour gérer le contrôleur SBC.</span><span class="sxs-lookup"><span data-stu-id="4325b-124">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="4325b-125">Pour valider les commandes, tapez ou copier/coller dans ce qui suit dans la session PowerShell et appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="4325b-125">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
gcm *onlinePSTNGateway*
```

<span data-ttu-id="4325b-126">Votre commande renverra les quatre fonctions indiquées ici qui vous permet de gérer les SBCs.</span><span class="sxs-lookup"><span data-stu-id="4325b-126">Your command will return the four functions shown here that will let you manage the SBCs.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="4325b-127">Paire le contrôleur SBC au client</span><span class="sxs-lookup"><span data-stu-id="4325b-127">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="4325b-128">Pour associer le contrôleur SBC au client, dans la session PowerShell, tapez ce qui suit et appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="4325b-128">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="4325b-129">Nous vous recommandons la définition d’une limite pour le contrôleur SBC, en utilisant les informations que vous trouverez dans la documentation de SBC.</span><span class="sxs-lookup"><span data-stu-id="4325b-129">We highly recommend setting a limit for the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="4325b-130">La limite de déclencher une notification si le contrôleur SBC est au niveau de la capacité.</span><span class="sxs-lookup"><span data-stu-id="4325b-130">The limit will trigger a notification if SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="4325b-131">Vous pouvez uniquement paire le contrôleur SBC avec le nom de domaine complet, où la partie domaine du nom correspond à l’un des domaines enregistrés dans votre client, à l’exception de \*. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="4325b-131">You can only pair the SBC with FQDN, where the domain portion of the name matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="4325b-132">À l’aide de \*. omicrosoft.com les noms de domaine n’est pas pris en charge pour les noms FQDN SBC.</span><span class="sxs-lookup"><span data-stu-id="4325b-132">Using \*.omicrosoft.com domain names is not supported for the SBC FQDN names.</span></span> <span data-ttu-id="4325b-133">Par exemple, si vous avez deux noms de domaine :</span><span class="sxs-lookup"><span data-stu-id="4325b-133">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="4325b-134">.xyz **ABC**</span><span class="sxs-lookup"><span data-stu-id="4325b-134">**abc**.xyz</span></span><br/><span data-ttu-id="4325b-135">**ABC**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4325b-135">**abc**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="4325b-136">Pour le nom SBC, vous pouvez utiliser le nom sbc.abc.xyz.</span><span class="sxs-lookup"><span data-stu-id="4325b-136">For the SBC name, you can use the name sbc.abc.xyz.</span></span> <span data-ttu-id="4325b-137">Si vous essayez de paire le contrôleur SBC avec un nom de sbc.xyz.abc, le système ne vous permettra pas, comme le domaine n’est pas détenu par ce client.</span><span class="sxs-lookup"><span data-stu-id="4325b-137">If you try to pair the SBC with a name sbc.xyz.abc, the system will not let you, as the domain is not owned by this tenant.</span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="4325b-138">Propriété renvoie :</span><span class="sxs-lookup"><span data-stu-id="4325b-138">Returns:</span></span>
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
<span data-ttu-id="4325b-139">Il existe des options supplémentaires qui peuvent être définies lors de l’appariement.</span><span class="sxs-lookup"><span data-stu-id="4325b-139">There are additional options that can be set during the pairing.</span></span> <span data-ttu-id="4325b-140">Dans l’exemple précédent, toutefois, seulement la configuration minimale requise paramètres sont affichés.</span><span class="sxs-lookup"><span data-stu-id="4325b-140">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="4325b-141">Le tableau suivant répertorie les paramètres supplémentaires que vous pouvez utiliser dans la définition des paramètres de *New-CsOnlinePstnGateway*.</span><span class="sxs-lookup"><span data-stu-id="4325b-141">The following table lists the additional parameters that you can use in setting parameters for *New-CsOnlinePstnGateway*.</span></span> 

|<span data-ttu-id="4325b-142">Obligatoire ?</span><span class="sxs-lookup"><span data-stu-id="4325b-142">Required?</span></span>|<span data-ttu-id="4325b-143">Nom</span><span class="sxs-lookup"><span data-stu-id="4325b-143">Name</span></span>|<span data-ttu-id="4325b-144">Description</span><span class="sxs-lookup"><span data-stu-id="4325b-144">Description</span></span>|<span data-ttu-id="4325b-145">Par défaut</span><span class="sxs-lookup"><span data-stu-id="4325b-145">Default</span></span>|<span data-ttu-id="4325b-146">Valeurs possibles</span><span class="sxs-lookup"><span data-stu-id="4325b-146">Possible values</span></span>|<span data-ttu-id="4325b-147">Type et restrictions</span><span class="sxs-lookup"><span data-stu-id="4325b-147">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4325b-148">Oui</span><span class="sxs-lookup"><span data-stu-id="4325b-148">Yes</span></span>|<span data-ttu-id="4325b-149">FQDN</span><span class="sxs-lookup"><span data-stu-id="4325b-149">FQDN</span></span>|<span data-ttu-id="4325b-150">Le nom de domaine complet de le SBC</span><span class="sxs-lookup"><span data-stu-id="4325b-150">The FQDN name of the SBC</span></span> |<span data-ttu-id="4325b-151">Aucun</span><span class="sxs-lookup"><span data-stu-id="4325b-151">None</span></span>|<span data-ttu-id="4325b-152">Nom de NoneFQDN, limite 63 caractères</span><span class="sxs-lookup"><span data-stu-id="4325b-152">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="4325b-153">Chaîne, liste de caractères autorisés et non autorisés sur [les conventions d’attribution de noms dans Active Directory pour les ordinateurs, les domaines, les sites et les unités d’organisation](https://support.microsoft.com/help/909264)</span><span class="sxs-lookup"><span data-stu-id="4325b-153">String,  list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="4325b-154">Non</span><span class="sxs-lookup"><span data-stu-id="4325b-154">No</span></span>|<span data-ttu-id="4325b-155">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="4325b-155">MediaBypass</span></span> |<span data-ttu-id="4325b-156">Le paramètre est réservé pour une utilisation future.</span><span class="sxs-lookup"><span data-stu-id="4325b-156">The parameter reserved for future use.</span></span> <span data-ttu-id="4325b-157">Paramètre indiqué du contrôleur SBC prend en charge le contournement de média et l’administrateur souhaite l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="4325b-157">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="4325b-158">Aucun</span><span class="sxs-lookup"><span data-stu-id="4325b-158">None</span></span>|<span data-ttu-id="4325b-159">True</span><span class="sxs-lookup"><span data-stu-id="4325b-159">True</span></span><br/><span data-ttu-id="4325b-160">Faux</span><span class="sxs-lookup"><span data-stu-id="4325b-160">False</span></span>|<span data-ttu-id="4325b-161">Boléen</span><span class="sxs-lookup"><span data-stu-id="4325b-161">Boolean</span></span>|
|<span data-ttu-id="4325b-162">Oui</span><span class="sxs-lookup"><span data-stu-id="4325b-162">Yes</span></span>|<span data-ttu-id="4325b-163">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="4325b-163">SipSignallingPort</span></span> |<span data-ttu-id="4325b-164">Port d’écoute utilisé pour communiquer avec les services de routage Direct à l’aide du protocole de Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="4325b-164">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="4325b-165">Aucun</span><span class="sxs-lookup"><span data-stu-id="4325b-165">None</span></span>|<span data-ttu-id="4325b-166">N’importe quel port</span><span class="sxs-lookup"><span data-stu-id="4325b-166">Any port</span></span>|<span data-ttu-id="4325b-167">comprise entre 0 et 65535</span><span class="sxs-lookup"><span data-stu-id="4325b-167">0 to 65535</span></span> |
|<span data-ttu-id="4325b-168">Non</span><span class="sxs-lookup"><span data-stu-id="4325b-168">No</span></span>|<span data-ttu-id="4325b-169">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="4325b-169">FailoverTimeSeconds</span></span> |<span data-ttu-id="4325b-170">Lorsque la valeur 10 (valeur par défaut), les appels sortants qui ne sont pas traitées par la passerelle dans les 10 secondes sont routés vers le tronçon suivant disponible ; s’il n’y a aucune jonctions supplémentaires, l’appel est automatiquement supprimé.</span><span class="sxs-lookup"><span data-stu-id="4325b-170">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="4325b-171">Dans une organisation avec des réponses de passerelle ou réseau lentes, cela peut entraîner l’abandon de nombreux appels.</span><span class="sxs-lookup"><span data-stu-id="4325b-171">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="4325b-172">La valeur par défaut est 10.</span><span class="sxs-lookup"><span data-stu-id="4325b-172">The default value is 10.</span></span>|<span data-ttu-id="4325b-173">10</span><span class="sxs-lookup"><span data-stu-id="4325b-173">10</span></span>|<span data-ttu-id="4325b-174">Numéro</span><span class="sxs-lookup"><span data-stu-id="4325b-174">Number</span></span>|<span data-ttu-id="4325b-175">Int</span><span class="sxs-lookup"><span data-stu-id="4325b-175">Int</span></span>|
|<span data-ttu-id="4325b-176">Non</span><span class="sxs-lookup"><span data-stu-id="4325b-176">No</span></span>|<span data-ttu-id="4325b-177">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="4325b-177">ForwardCallHistory</span></span> |<span data-ttu-id="4325b-178">Indique si les informations d’historique d’appel sont transférées par le biais de la jonction.</span><span class="sxs-lookup"><span data-stu-id="4325b-178">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="4325b-179">Si activé, le Proxy de PSTN Office 365 envoie deux en-têtes : historique-info et visé par.</span><span class="sxs-lookup"><span data-stu-id="4325b-179">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="4325b-180">La valeur par défaut est **False** ($False).</span><span class="sxs-lookup"><span data-stu-id="4325b-180">The default value is **False** ($False).</span></span> |<span data-ttu-id="4325b-181">Faux</span><span class="sxs-lookup"><span data-stu-id="4325b-181">False</span></span>|<span data-ttu-id="4325b-182">True</span><span class="sxs-lookup"><span data-stu-id="4325b-182">True</span></span><br/><span data-ttu-id="4325b-183">Faux</span><span class="sxs-lookup"><span data-stu-id="4325b-183">False</span></span>|<span data-ttu-id="4325b-184">Boléen</span><span class="sxs-lookup"><span data-stu-id="4325b-184">Boolean</span></span>|
|<span data-ttu-id="4325b-185">Non</span><span class="sxs-lookup"><span data-stu-id="4325b-185">No</span></span>|<span data-ttu-id="4325b-186">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="4325b-186">ForwardPAI</span></span>|<span data-ttu-id="4325b-187">Indique si l’en-tête P-Asserted-Identity (PAI) sera transféré avec l’appel.</span><span class="sxs-lookup"><span data-stu-id="4325b-187">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="4325b-188">L’en-tête PAI est un moyen de vérifier l’identité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="4325b-188">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="4325b-189">La valeur par défaut est **False** ($False).</span><span class="sxs-lookup"><span data-stu-id="4325b-189">The default value is **False** ($False).</span></span>|<span data-ttu-id="4325b-190">Faux</span><span class="sxs-lookup"><span data-stu-id="4325b-190">False</span></span>|<span data-ttu-id="4325b-191">True</span><span class="sxs-lookup"><span data-stu-id="4325b-191">True</span></span><br/><span data-ttu-id="4325b-192">Faux</span><span class="sxs-lookup"><span data-stu-id="4325b-192">False</span></span>|<span data-ttu-id="4325b-193">Boléen</span><span class="sxs-lookup"><span data-stu-id="4325b-193">Boolean</span></span>|
|<span data-ttu-id="4325b-194">Non</span><span class="sxs-lookup"><span data-stu-id="4325b-194">No</span></span>|<span data-ttu-id="4325b-195">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="4325b-195">SendSIPOptions</span></span> |<span data-ttu-id="4325b-196">Définit si un contrôleur SBC sera ou n’envoie pas les options SIP.</span><span class="sxs-lookup"><span data-stu-id="4325b-196">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="4325b-197">Si désactivé, le contrôleur SBC sera exclu de système de surveillance et d’alerte.</span><span class="sxs-lookup"><span data-stu-id="4325b-197">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="4325b-198">Il est vivement recommandé d’activer les options de SIP.</span><span class="sxs-lookup"><span data-stu-id="4325b-198">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="4325b-199">Valeur par défaut est **True**.</span><span class="sxs-lookup"><span data-stu-id="4325b-199">Default value is **True**.</span></span> |<span data-ttu-id="4325b-200">True</span><span class="sxs-lookup"><span data-stu-id="4325b-200">True</span></span>|<span data-ttu-id="4325b-201">True</span><span class="sxs-lookup"><span data-stu-id="4325b-201">True</span></span><br/><span data-ttu-id="4325b-202">Faux</span><span class="sxs-lookup"><span data-stu-id="4325b-202">False</span></span>|<span data-ttu-id="4325b-203">Boléen</span><span class="sxs-lookup"><span data-stu-id="4325b-203">Boolean</span></span>|
|<span data-ttu-id="4325b-204">Non</span><span class="sxs-lookup"><span data-stu-id="4325b-204">No</span></span>|<span data-ttu-id="4325b-205">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="4325b-205">MaxConcurrentSessions</span></span> |<span data-ttu-id="4325b-206">Utilisé par le système d’alerte.</span><span class="sxs-lookup"><span data-stu-id="4325b-206">Used by alerting system.</span></span> <span data-ttu-id="4325b-207">Lorsqu’une valeur est définie, le système d’alerte génère une alerte à l’administrateur de clients lorsque le nombre de sessions simultanées est 90 % ou supérieure à cette valeur.</span><span class="sxs-lookup"><span data-stu-id="4325b-207">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="4325b-208">Si le paramètre n’est pas défini, les alertes ne sont pas générés.</span><span class="sxs-lookup"><span data-stu-id="4325b-208">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="4325b-209">Toutefois, le système de surveillance signalera nombre de sessions simultanées toutes les 24 heures.</span><span class="sxs-lookup"><span data-stu-id="4325b-209">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="4325b-210">Null</span><span class="sxs-lookup"><span data-stu-id="4325b-210">Null</span></span>|<span data-ttu-id="4325b-211">Null</span><span class="sxs-lookup"><span data-stu-id="4325b-211">Null</span></span><br/><span data-ttu-id="4325b-212">1 et 100 000</span><span class="sxs-lookup"><span data-stu-id="4325b-212">1 to 100,000</span></span> ||
|<span data-ttu-id="4325b-213">Non</span><span class="sxs-lookup"><span data-stu-id="4325b-213">No</span></span>|<span data-ttu-id="4325b-214">Activé \*</span><span class="sxs-lookup"><span data-stu-id="4325b-214">Enabled\*</span></span>|<span data-ttu-id="4325b-215">Permet d’activer cette SBC pour les appels sortants.</span><span class="sxs-lookup"><span data-stu-id="4325b-215">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="4325b-216">Peut être utilisée pour supprimer temporairement le contrôleur SBC, pendant qu’il est en cours de mise à jour ou lors de la maintenance.</span><span class="sxs-lookup"><span data-stu-id="4325b-216">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="4325b-217">Faux</span><span class="sxs-lookup"><span data-stu-id="4325b-217">False</span></span>|<span data-ttu-id="4325b-218">True</span><span class="sxs-lookup"><span data-stu-id="4325b-218">True</span></span><br/><span data-ttu-id="4325b-219">Faux</span><span class="sxs-lookup"><span data-stu-id="4325b-219">False</span></span>|<span data-ttu-id="4325b-220">Boléen</span><span class="sxs-lookup"><span data-stu-id="4325b-220">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="4325b-221">Vérifiez l’appariement SBC</span><span class="sxs-lookup"><span data-stu-id="4325b-221">Verify the SBC pairing</span></span> 

<span data-ttu-id="4325b-222">Vérifiez la connexion :</span><span class="sxs-lookup"><span data-stu-id="4325b-222">Verify the connection:</span></span> 
- <span data-ttu-id="4325b-223">Vérifiez si le contrôleur SBC est dans la liste des paires SBCs.</span><span class="sxs-lookup"><span data-stu-id="4325b-223">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="4325b-224">Valider les Options SIP.</span><span class="sxs-lookup"><span data-stu-id="4325b-224">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="4325b-225">Valider si SBC se trouve dans la liste des paires SBCs</span><span class="sxs-lookup"><span data-stu-id="4325b-225">Validate if SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="4325b-226">Après avoir paire le contrôleur SBC, vérifier que le contrôleur SBC est présent dans la liste des paires SBCs en exécutant la commande suivante dans une session PowerShell distante :`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="4325b-226">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command  in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="4325b-227">La passerelle couplée doit apparaissent dans la liste, comme illustré dans l’exemple ci-dessous, puis vérifiez que le paramètre *Enabled* affiche la valeur **True**.</span><span class="sxs-lookup"><span data-stu-id="4325b-227">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="4325b-228">Entrez :</span><span class="sxs-lookup"><span data-stu-id="4325b-228">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="4325b-229">Qui retourne :</span><span class="sxs-lookup"><span data-stu-id="4325b-229">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="4325b-230">Contrôler le flux d’Options SIP</span><span class="sxs-lookup"><span data-stu-id="4325b-230">Validate SIP Options flow</span></span> 

<span data-ttu-id="4325b-231">Pour valider l’association à l’aide des Options SIP sortant, utilisez l’interface de gestion SBC et voir que le contrôleur SBC 200 OK réponses aux OPTIONS sortantes.</span><span class="sxs-lookup"><span data-stu-id="4325b-231">To validate the pairing using outgoing SIP Options, use the SBC management interface and see that the SBC get 200 OK responses to the outgoing OPTIONS.</span></span>
  
<span data-ttu-id="4325b-232">Lorsque le routage Direct voit des OPTIONS entrantes, il démarre sortantes options d’envoi pour le nom de domaine complet SBC configuré dans le champ en-tête de Contact dans le message entrant d’OPTIONS.</span><span class="sxs-lookup"><span data-stu-id="4325b-232">When Direct Routing sees incoming OPTIONS, it will start sending outgoing options to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="4325b-233">Pour valider l’association à l’aide des Options SIP entrants, utilisez l’interface de gestion SBC et voir que le contrôleur SBC réponse sur les messages OPTIONS provenant routage Direct, et que le code de réponse est 200 OK.</span><span class="sxs-lookup"><span data-stu-id="4325b-233">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC gets reply on the OPTIONS messages coming in from Direct Routing and that the response code is 200 OK.</span></span>  

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="4325b-234">Activer les utilisateurs pour le Service de routage Direct</span><span class="sxs-lookup"><span data-stu-id="4325b-234">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="4325b-235">Lorsque vous êtes prêt à activer les utilisateurs pour le Service de routage Direct, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4325b-235">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="4325b-236">Créer un utilisateur dans Office 365 et attribuer une licence de système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="4325b-236">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="4325b-237">Assurez-vous que l’utilisateur est hébergé dans Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="4325b-237">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="4325b-238">Configurer le numéro de téléphone et activer la messagerie vocale et enterprise voice.</span><span class="sxs-lookup"><span data-stu-id="4325b-238">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="4325b-239">Configurer le routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="4325b-239">Configure voice routing.</span></span> <span data-ttu-id="4325b-240">L’itinéraire est automatiquement validé.</span><span class="sxs-lookup"><span data-stu-id="4325b-240">The route is automatically validated.</span></span>  

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="4325b-241">Créer un utilisateur dans Office 365 et attribuer la licence</span><span class="sxs-lookup"><span data-stu-id="4325b-241">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="4325b-242">Il existe deux options pour la création d’un nouvel utilisateur dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="4325b-242">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="4325b-243">Toutefois, nous conseillons de votre organisation sélectionner une option permet d’éviter les problèmes de routage :</span><span class="sxs-lookup"><span data-stu-id="4325b-243">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="4325b-244">Créer l’utilisateur dans Active Directory de locaux et synchroniser l’utilisateur vers le nuage.</span><span class="sxs-lookup"><span data-stu-id="4325b-244">Create the user in on-premise Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="4325b-245">Voir les [répertoires intégrer votre locale avec Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="4325b-245">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>  
- <span data-ttu-id="4325b-246">Créer l’utilisateur directement dans le portail d’administrateur Office 365.</span><span class="sxs-lookup"><span data-stu-id="4325b-246">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="4325b-247">Consultez la rubrique [Ajouter des utilisateurs individuellement ou par lot pour Office 365 - aide d’administration](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="4325b-247">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

  <span data-ttu-id="4325b-248">Si vous générez le système coexiste avec Skype pour Business 2015 ou Lync 2010/2013 locale, la seule option prise en charge consiste à créer l’utilisateur dans l’annuaire local et synchronisation de l’utilisateur vers le nuage (Option 1).</span><span class="sxs-lookup"><span data-stu-id="4325b-248">If you build the system that co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="4325b-249">Licences requises :</span><span class="sxs-lookup"><span data-stu-id="4325b-249">Required licenses:</span></span> 

- <span data-ttu-id="4325b-250">Office 365 entreprise E3 (y compris SfB Plan2, Plan2 Exchange et les équipes) + système de téléphone.</span><span class="sxs-lookup"><span data-stu-id="4325b-250">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>  
- <span data-ttu-id="4325b-251">Office 365 entreprise E5 (y compris SfB Plan2 Plan2 Exchange et les équipes système téléphonique)</span><span class="sxs-lookup"><span data-stu-id="4325b-251">Office 365 Enterprise E5  (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="4325b-252">Licences facultatifs :</span><span class="sxs-lookup"><span data-stu-id="4325b-252">Optional licenses:</span></span> 

- <span data-ttu-id="4325b-253">Appel de Plan</span><span class="sxs-lookup"><span data-stu-id="4325b-253">Calling Plan</span></span> 
- <span data-ttu-id="4325b-254">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="4325b-254">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="4325b-255">Assurez-vous que l’utilisateur est hébergé dans Skype pour Business Online</span><span class="sxs-lookup"><span data-stu-id="4325b-255">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="4325b-256">Routage direct, l’utilisateur doit être hébergé dans Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="4325b-256">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="4325b-257">Vous pouvez le vérifier en regardant le paramètre RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="4325b-257">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="4325b-258">Il doit avoir une valeur dans le domaine infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="4325b-258">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="4325b-259">Se connecter à PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="4325b-259">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="4325b-260">Exécutez la commande :</span><span class="sxs-lookup"><span data-stu-id="4325b-260">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="4325b-261">Configurer le numéro de téléphone et activer la messagerie vocale et enterprise voice</span><span class="sxs-lookup"><span data-stu-id="4325b-261">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="4325b-262">Après avoir créé l’utilisateur et attribué une licence, l’étape suivante consiste à configurer leur numéro de téléphone et la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="4325b-262">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="4325b-263">Pour cela, en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="4325b-263">This can be done in one step.</span></span> 

<span data-ttu-id="4325b-264">Pour ajouter le numéro de téléphone et activer pour la messagerie vocale :</span><span class="sxs-lookup"><span data-stu-id="4325b-264">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="4325b-265">Se connecter à une session PowerShell distante.</span><span class="sxs-lookup"><span data-stu-id="4325b-265">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="4325b-266">Entrez la commande :</span><span class="sxs-lookup"><span data-stu-id="4325b-266">Enter the command:</span></span> 
    
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+ phone number
```

<span data-ttu-id="4325b-267">Par exemple, pour ajouter un numéro de téléphone pour l’utilisateur « Spencer faible », entrez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="4325b-267">For example, to add a phone number for user “Spencer Low,” you would enter the following:</span></span> 

```
Set-CsUser - “Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="4325b-268">Le numéro de téléphone utilisé doit être configuré comme un numéro de téléphone E.164 complète avec le code de pays.</span><span class="sxs-lookup"><span data-stu-id="4325b-268">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="4325b-269">Si le numéro de téléphone de l’utilisateur est géré sur site, utilisez locale Skype pour Business Management Shell ou le panneau de configuration pour configurer le numéro de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4325b-269">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="4325b-270">Configurer le routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="4325b-270">Configure Voice Routing</span></span> 

<span data-ttu-id="4325b-271">Système téléphonique de Microsoft dispose d’un mécanisme de routage qui permet à un appel à envoyer à un SBC spécifique en fonction de :</span><span class="sxs-lookup"><span data-stu-id="4325b-271">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="4325b-272">Modèle de numéro appelé</span><span class="sxs-lookup"><span data-stu-id="4325b-272">Called number pattern</span></span> 
- <span data-ttu-id="4325b-273">Modèle de numéro appelé + utilisateur spécifique qui effectue l’appel</span><span class="sxs-lookup"><span data-stu-id="4325b-273">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="4325b-274">SBC peut être désignés comme actif et de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="4325b-274">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="4325b-275">Cela signifie que lorsque la SBC est configuré comme active pour ce modèle de numéro, ou un modèle de numéro + un utilisateur spécifique, n’est pas disponible, puis les appels sont acheminés vers un contrôleur SBC sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="4325b-275">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="4325b-276">Routage des appels est composé des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="4325b-276">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="4325b-277">Stratégie de routage voix – conteneur pour les utilisations RTC ; peuvent être attribuées à un utilisateur ou à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4325b-277">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="4325b-278">Utilisations PSTN – conteneur pour les itinéraires de communications vocales et les utilisations RTC ; peuvent être partagées dans différentes stratégies de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="4325b-278">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="4325b-279">Itinéraires-modèle de numéro et un ensemble de Online passerelles PSTN à utiliser pour les appels où l’appel de numéro correspond au modèle de voix</span><span class="sxs-lookup"><span data-stu-id="4325b-279">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="4325b-280">Passerelle PSTN Online - pointeur SBC, stocke également la configuration est appliquée lors de l’appel est passé via le contrôleur SBC, telles que le transfert P-Asserted-Identity (PAI) ou Codecs par défaut ; peuvent être ajoutés à des itinéraires de communications vocales</span><span class="sxs-lookup"><span data-stu-id="4325b-280">Online PSTN Gateway - pointer at SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="4325b-281">Création d’une stratégie de routage des communications vocales avec une seule utilisation PSTN</span><span class="sxs-lookup"><span data-stu-id="4325b-281">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="4325b-282">Le diagramme suivant illustre les deux exemples de stratégies de routage voix dans le flux d’appels.</span><span class="sxs-lookup"><span data-stu-id="4325b-282">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="4325b-283">**Appel flux 1 (à gauche) :** Si un utilisateur effectue un appel à XXX-XX-XX +1 425 ou XXX-XX-XX +1 206, l’appel est acheminé vers SBC sbc1<span></span>. contoso.biz ou sbc2<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="4325b-283">**Call Flow 1 (on the left):** If a user makes a call to  +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed  to SBC sbc1<span></span>.contoso.biz or sbc2<span></span>.contoso.biz.</span></span> <span data-ttu-id="4325b-284">Si ni sbc1<span></span>. contoso.biz, ni sbc2<span></span>. contoso.biz sont disponibles, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="4325b-284">If neither sbc1<span></span>.contoso.biz nor sbc2<span></span>.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="4325b-285">**Call flux 2 (à droite) :** Si un utilisateur effectue un appel à XXX-XX-XX +1 425 ou XXX-XX-XX +1 206, l’appel est tout d’abord dirigé vers SBC sbc1<span></span>. contoso.biz ou sbc2<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="4325b-285">**Call Flow 2 (on the right):** If a user makes a call to  +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1<span></span>.contoso.biz or sbc2<span></span>.contoso.biz.</span></span> <span data-ttu-id="4325b-286">Si aucun contrôleur SBC est disponible, l’itinéraire dont la priorité est tentée (sbc3<span></span>. contoso.biz et sbc4<span></span>. contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="4325b-286">If neither SBC is available, the route with lower priority will be tried (sbc3<span></span>.contoso.biz and sbc4<span></span>.contoso.biz).</span></span> <span data-ttu-id="4325b-287">Si aucune des SBCs n’est disponibles, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="4325b-287">If none of the SBCs are available, the call is dropped.</span></span> 

![Présente des exemples de stratégie de routage voix](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="4325b-289">Dans les deux exemples, tandis que l’itinéraire de communications vocales est assignée les priorités, les SBCs dans les itinéraires sont traités dans l’ordre aléatoire.</span><span class="sxs-lookup"><span data-stu-id="4325b-289">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4325b-290">À moins que l’utilisateur a également une licence Plan de l’appel de Microsoft, les appels vers n’importe quel nombre à l’exception des numéros qui correspondent à des modèles + XXX-XX-XX +1 425 ou +1 206 XXX XX XX dans l’exemple de configuration sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="4325b-290">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns + +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="4325b-291">Si l’utilisateur possède une licence de planifier l’appel, l’appel est acheminé automatiquement en fonction des stratégies de l’appel de Plan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4325b-291">If the user has a Calling Plan license, the call is automatically routed according to the policies of  the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="4325b-292">Le Plan d’appel de Microsoft s’applique automatiquement en tant que dernier à tous les utilisateurs dont la licence de l’appel de Plan de Microsoft et ne nécessite pas de configuration du routage des appels supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="4325b-292">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="4325b-293">Dans l’exemple illustré dans le diagramme suivant, un itinéraire de communications vocales est ajouté pour envoyer les appels vers tous les autres États-Unis et du Canada numéro (appels qui accèdent à un modèle de numéro appelé + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="4325b-293">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Stratégie de routage avec un itinéraire tiers de voix affiche](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="4325b-295">Si l’utilisateur a les deux licences (système téléphonique de Microsoft et Microsoft appel de Plan) itinéraire automatique est utilisée pour tous les autres appels.</span><span class="sxs-lookup"><span data-stu-id="4325b-295">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="4325b-296">Si rien ne correspond au numéros modèles créés par l’administrateur en ligne itinéraires des communications vocales, l’itinéraire par le biais de l’appel de Plan de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4325b-296">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="4325b-297">Si l’utilisateur a Microsoft Phone System, l’appel est supprimé, car aucune règle correspondante n’est disponibles.</span><span class="sxs-lookup"><span data-stu-id="4325b-297">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4325b-298">Valeur de la priorité d’itinéraire « Autres + 1 » n’a aucune importance dans ce cas, comme c’est le seul itinéraire qui correspond au modèle + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="4325b-298">The Priority value for route “Other +1” doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="4325b-299">Si un utilisateur effectue un appel à + 1 324 567 89 89 et à la fois sbc5.contoso.biz et sbc6.contoso.biz ne sont pas disponibles, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="4325b-299">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="4325b-300">Le tableau suivant récapitule la configuration à l’aide de trois itinéraires de communications vocales.</span><span class="sxs-lookup"><span data-stu-id="4325b-300">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="4325b-301">Dans cet exemple, tous les itinéraires de trois font partie de la même utilisation PSTN « Nous et Canada ».</span><span class="sxs-lookup"><span data-stu-id="4325b-301">In this example, all three routes are part of the same PSTN Usage “US and Canada”.</span></span>

|<span data-ttu-id="4325b-302">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="4325b-302">**PSTN usage**</span></span>|<span data-ttu-id="4325b-303">**Itinéraire de communications vocales**</span><span class="sxs-lookup"><span data-stu-id="4325b-303">**Voice route**</span></span>|<span data-ttu-id="4325b-304">**Schéma de numéro**</span><span class="sxs-lookup"><span data-stu-id="4325b-304">**Number pattern**</span></span>|<span data-ttu-id="4325b-305">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="4325b-305">**Priority**</span></span>|<span data-ttu-id="4325b-306">**SBC**</span><span class="sxs-lookup"><span data-stu-id="4325b-306">**SBC**</span></span>|<span data-ttu-id="4325b-307">**Description**</span><span class="sxs-lookup"><span data-stu-id="4325b-307">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4325b-308">Nous uniquement</span><span class="sxs-lookup"><span data-stu-id="4325b-308">US only</span></span>|<span data-ttu-id="4325b-309">« Redmond 1 »</span><span class="sxs-lookup"><span data-stu-id="4325b-309">“Redmond 1”</span></span>|<span data-ttu-id="4325b-310">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="4325b-310">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="4325b-311">1</span><span class="sxs-lookup"><span data-stu-id="4325b-311">1</span></span>|<span data-ttu-id="4325b-312">sbc1<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4325b-312">sbc1<span></span>.contoso.biz</span></span><br/><span data-ttu-id="4325b-313">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4325b-313">sbc2<span></span>.contoso.biz</span></span>|<span data-ttu-id="4325b-314">Itinéraire actif pour les numéros appelés XXX-XX-XX +1 425 ou XXX-XX-XX +1 206</span><span class="sxs-lookup"><span data-stu-id="4325b-314">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="4325b-315">Nous uniquement</span><span class="sxs-lookup"><span data-stu-id="4325b-315">US only</span></span>|<span data-ttu-id="4325b-316">« Redmond 2 »</span><span class="sxs-lookup"><span data-stu-id="4325b-316">“Redmond 2”</span></span>|<span data-ttu-id="4325b-317">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="4325b-317">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="4325b-318">2</span><span class="sxs-lookup"><span data-stu-id="4325b-318">2</span></span>|<span data-ttu-id="4325b-319">SBC3<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4325b-319">sbc3<span></span>.contoso.biz</span></span><br/><span data-ttu-id="4325b-320">sbc4<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4325b-320">sbc4<span></span>.contoso.biz</span></span>|<span data-ttu-id="4325b-321">Itinéraire alternatif pour les numéros appelés XXX-XX-XX +1 425 ou XXX-XX-XX +1 206</span><span class="sxs-lookup"><span data-stu-id="4325b-321">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="4325b-322">Nous uniquement</span><span class="sxs-lookup"><span data-stu-id="4325b-322">US only</span></span>|<span data-ttu-id="4325b-323">« Autres + 1 »</span><span class="sxs-lookup"><span data-stu-id="4325b-323">"Other +1”</span></span>|<span data-ttu-id="4325b-324">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="4325b-324">^\\+1(\d{10})$</span></span>|<span data-ttu-id="4325b-325">3</span><span class="sxs-lookup"><span data-stu-id="4325b-325">3</span></span>|<span data-ttu-id="4325b-326">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4325b-326">sbc5<span></span>.contoso.biz</span></span><br/><span data-ttu-id="4325b-327">sbc6<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4325b-327">sbc6<span></span>.contoso.biz</span></span>|<span data-ttu-id="4325b-328">Routage de numéros appelés + 1 XXX XXX XX XX (sauf XXX-XX-XX +1 425 ou XXX-XX-XX +1 206)</span><span class="sxs-lookup"><span data-stu-id="4325b-328">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="4325b-329">Tous les itinéraires sont associés à l’utilisation PSTN « Nous et Canada » et l’utilisation RTC est associée à la stratégie de routage voix « US uniquement ».</span><span class="sxs-lookup"><span data-stu-id="4325b-329">All routes are associated with the PSTN Usage “US and Canada” and the PSTN Usage is associated with the Voice Routing Policy “US Only.”</span></span> <span data-ttu-id="4325b-330">Dans cet exemple, la stratégie de routage voix est attribuée à l’utilisateur Spencer Low.</span><span class="sxs-lookup"><span data-stu-id="4325b-330">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="4325b-331">Exemples d’itinéraires d’appels</span><span class="sxs-lookup"><span data-stu-id="4325b-331">Examples of call routes</span></span>

<span data-ttu-id="4325b-332">Dans l’exemple suivant, nous vous montrer comment configurer des itinéraires, des utilisations PSTN et des stratégies de routage et nous attribuer la stratégie à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4325b-332">In the following example,  we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="4325b-333">**Étape 1 :** Créer l’utilisation PSTN « États-Unis et au Canada. »</span><span class="sxs-lookup"><span data-stu-id="4325b-333">**Step 1:** Create the PSTN Usage “US and Canada.”</span></span>

<span data-ttu-id="4325b-334">Dans un Skype de session Business Remote PowerShell, tapez :</span><span class="sxs-lookup"><span data-stu-id="4325b-334">In a  Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="4325b-335">Vérifiez que l’utilisation a été créée en entrant :</span><span class="sxs-lookup"><span data-stu-id="4325b-335">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="4325b-336">Qui retourne une liste de noms qui peuvent être tronqués :</span><span class="sxs-lookup"><span data-stu-id="4325b-336">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="4325b-337">Dans l’exemple ci-dessous, vous pouvez voir le résultat de l’exécution de la commande PowerShell *`(Get-CSOnlinePSTNUsage).usage`* pour afficher les noms complets (non tronquées).</span><span class="sxs-lookup"><span data-stu-id="4325b-337">In the example below, you can see the result of the running the PowerShell command *`(Get-CSOnlinePSTNUsage).usage`* to display full names (not truncated).</span></span>    
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

<span data-ttu-id="4325b-338">**Étape 2 :** Dans une session dans Skype pour Business Online PowerShell, créez des trois itinéraires : Redmond 1, Redmond 2 et autres + 1, comme indiqué dans le tableau précédent.</span><span class="sxs-lookup"><span data-stu-id="4325b-338">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other+1, as detailed in the previous table.</span></span> 

<span data-ttu-id="4325b-339">Pour créer l’itinéraire « Redmond 1 », entrez :</span><span class="sxs-lookup"><span data-stu-id="4325b-339">To create the “Redmond 1” route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="4325b-340">Qui retourne :</span><span class="sxs-lookup"><span data-stu-id="4325b-340">Which returns:</span></span>
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
<span data-ttu-id="4325b-341">Pour créer l’itinéraire Redmond 2, entrez :</span><span class="sxs-lookup"><span data-stu-id="4325b-341">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="4325b-342">Pour créer l’itinéraire de + 1 autres, entrez :</span><span class="sxs-lookup"><span data-stu-id="4325b-342">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="4325b-343">Assurez-vous que votre expression régulière dans l’attribut NumberPattern est une expression valide.</span><span class="sxs-lookup"><span data-stu-id="4325b-343">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="4325b-344">Vous pouvez tester à l’aide de ce site Web :[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="4325b-344">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="4325b-345">Dans certains cas, il est nécessaire pour acheminer tous les appels vers la même SBC ; Utilisez - NumberPattern «. \* »</span><span class="sxs-lookup"><span data-stu-id="4325b-345">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern “.\*”</span></span>

- <span data-ttu-id="4325b-346">Tous les appels vers la même SBC</span><span class="sxs-lookup"><span data-stu-id="4325b-346">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="4325b-347">Valider que vous avez correctement configuré l’itinéraire en exécutant la `Get-CSOnlineVoiceRoute` commande Powershell à l’aide des options comme :</span><span class="sxs-lookup"><span data-stu-id="4325b-347">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` Powershell command using options as shown:</span></span> 

```
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="4325b-348">Qui doit retourner :</span><span class="sxs-lookup"><span data-stu-id="4325b-348">Which should return:</span></span>
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
NumberPattern       : ^\\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

<span data-ttu-id="4325b-349">Dans l’exemple, l’itinéraire « Autres + 1 » a été attribué automatiquement priorité.</span><span class="sxs-lookup"><span data-stu-id="4325b-349">In the example, the route “Other +1” was automatically assigned priority.</span></span> 

<span data-ttu-id="4325b-350">**Étape 3 :** Créer une stratégie de routage voix « Nous uniquement » et l’ajouter à la stratégie de l’utilisation PSTN « États-Unis et au Canada. »</span><span class="sxs-lookup"><span data-stu-id="4325b-350">**Step 3:** Create a Voice Routing Policy  “US Only” and add to the policy the PSTN Usage “US and Canada.”</span></span>

<span data-ttu-id="4325b-351">Dans une session dans Skype pour Business Online PowerShell, tapez :</span><span class="sxs-lookup"><span data-stu-id="4325b-351">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="4325b-352">Le résultat est indiqué dans cet exemple :</span><span class="sxs-lookup"><span data-stu-id="4325b-352">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="4325b-353">**Étape 4 :** Accorder à l’utilisateur Spence Low une stratégie de routage voix à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4325b-353">**Step 4:** Grant to user Spence Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="4325b-354">Dans une session dans Skype pour Business Online Powershell, tapez :</span><span class="sxs-lookup"><span data-stu-id="4325b-354">In a Powershell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="4325b-355">Valider l’affectation de stratégie en entrant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4325b-355">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="4325b-356">Qui retourne :</span><span class="sxs-lookup"><span data-stu-id="4325b-356">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="4325b-357">Création d’une stratégie de routage des communications vocales avec plusieurs utilisations PSTN</span><span class="sxs-lookup"><span data-stu-id="4325b-357">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="4325b-358">La stratégie de routage des communications vocales créée précédemment n’autorise les appels vers les numéros de téléphone aux États-Unis et au Canada, sauf si la licence de l’appel de Plan de Microsoft est également affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4325b-358">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="4325b-359">Dans l’exemple qui suit, vous ne pouvez créer la stratégie de routage voix « Aucune restriction ».</span><span class="sxs-lookup"><span data-stu-id="4325b-359">In the example that follows, you can create the Voice Routing Policy “No Restrictions.”</span></span> <span data-ttu-id="4325b-360">La stratégie réutilise l’utilisation PSTN « Nous et Canada » créé dans l’exemple précédent, ainsi que la nouvelle utilisation PSTN « International ».</span><span class="sxs-lookup"><span data-stu-id="4325b-360">The policy reuses the PSTN Usage “US and Canada” created in the previous example, as well as the new PSTN Usage “International.”</span></span> 

<span data-ttu-id="4325b-361">Cela achemine tous les autres appels vers le sbc2 SBCs<span></span>. contoso.biz et sbc5<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="4325b-361">This routes all other calls to the SBCs sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz.</span></span> <span data-ttu-id="4325b-362">Les exemples figurent attribuer des États-Unis uniquement une stratégie à l’utilisateur « Spencer faible » et sans Restrictions à l’utilisateur « John Woods ».</span><span class="sxs-lookup"><span data-stu-id="4325b-362">The examples that are shown assign US Only policy to user “Spencer Low,” and No Restrictions to the user “John Woods.”</span></span>

<span data-ttu-id="4325b-363">Spencer faible – appels autorisés uniquement aux États-Unis et au Canada numéros.</span><span class="sxs-lookup"><span data-stu-id="4325b-363">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="4325b-364">Lors de l’appel à la plage de numéros de Redmond, le jeu spécifique de SBC doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="4325b-364">When calling to Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="4325b-365">Les numéros non US seront acheminés pas, sauf si la licence de planifier l’appel est attribuée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4325b-365">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="4325b-366">John Woods – appels autorisés à n’importe quel nombre.</span><span class="sxs-lookup"><span data-stu-id="4325b-366">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="4325b-367">Lors de l’appel à la plage de numéros de Redmond, le jeu spécifique de SBC doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="4325b-367">When calling to Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="4325b-368">Les numéros non US seront acheminés via sbc2<span></span>. contoso.biz et sbc5<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="4325b-368">Non-US numbers will be routed via sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz.</span></span>

![Indique la stratégie de routage voix attribuée à l’utilisateur Spencer Low](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="4325b-370">Si l’utilisateur a les deux licences (système téléphonique de Microsoft et Microsoft appel de Plan) itinéraire automatique est utilisée pour tous les autres appels.</span><span class="sxs-lookup"><span data-stu-id="4325b-370">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="4325b-371">Si rien ne correspond au numéros modèles créés par l’administrateur en ligne itinéraires des communications vocales, l’itinéraire par le biais de l’appel de Plan de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4325b-371">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="4325b-372">Si l’utilisateur a Microsoft Phone System, l’appel est supprimé, car aucune règle correspondante n’est disponibles.</span><span class="sxs-lookup"><span data-stu-id="4325b-372">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Indique la stratégie de routage voix attribuée à l’utilisateur John Woods](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="4325b-374">Le tableau suivant récapitule les itinéraires de communications vocales et de dénomination de l’utilisation de routage stratégie « No Restrictions ».</span><span class="sxs-lookup"><span data-stu-id="4325b-374">The following table  summarizes routing policy “No Restrictions” usage designations and voice routes.</span></span> 

|<span data-ttu-id="4325b-375">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="4325b-375">**PSTN usage**</span></span>|<span data-ttu-id="4325b-376">**Itinéraire de communications vocales**</span><span class="sxs-lookup"><span data-stu-id="4325b-376">**Voice route**</span></span>|<span data-ttu-id="4325b-377">**Schéma de numéro**</span><span class="sxs-lookup"><span data-stu-id="4325b-377">**Number pattern**</span></span>|<span data-ttu-id="4325b-378">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="4325b-378">**Priority**</span></span>|<span data-ttu-id="4325b-379">**SBC**</span><span class="sxs-lookup"><span data-stu-id="4325b-379">**SBC**</span></span>|<span data-ttu-id="4325b-380">**Description**</span><span class="sxs-lookup"><span data-stu-id="4325b-380">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4325b-381">Nous uniquement</span><span class="sxs-lookup"><span data-stu-id="4325b-381">US Only</span></span>|<span data-ttu-id="4325b-382">« Redmond 1 »</span><span class="sxs-lookup"><span data-stu-id="4325b-382">“Redmond 1”</span></span>|<span data-ttu-id="4325b-383">^ + 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="4325b-383">^+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="4325b-384">1</span><span class="sxs-lookup"><span data-stu-id="4325b-384">1</span></span>|<span data-ttu-id="4325b-385">sbc1<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4325b-385">sbc1<span></span>.contoso.biz</span></span><br/><span data-ttu-id="4325b-386">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4325b-386">sbc2<span></span>.contoso.biz</span></span>|<span data-ttu-id="4325b-387">Gamme active pour les numéros appelé XXX-XX-XX +1 425 ou XXX-XX-XX +1 206</span><span class="sxs-lookup"><span data-stu-id="4325b-387">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="4325b-388">Nous uniquement</span><span class="sxs-lookup"><span data-stu-id="4325b-388">US Only</span></span>|<span data-ttu-id="4325b-389">« Redmond 2 »</span><span class="sxs-lookup"><span data-stu-id="4325b-389">“Redmond 2”</span></span>|<span data-ttu-id="4325b-390">^ + 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="4325b-390">^+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="4325b-391">2</span><span class="sxs-lookup"><span data-stu-id="4325b-391">2</span></span>|<span data-ttu-id="4325b-392">SBC3<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4325b-392">sbc3<span></span>.contoso.biz</span></span><br/><span data-ttu-id="4325b-393">sbc4<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4325b-393">sbc4<span></span>.contoso.biz</span></span>|<span data-ttu-id="4325b-394">Itinéraire alternatif pour les numéros appelé XXX-XX-XX +1 425 ou XXX-XX-XX +1 206</span><span class="sxs-lookup"><span data-stu-id="4325b-394">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="4325b-395">Nous uniquement</span><span class="sxs-lookup"><span data-stu-id="4325b-395">US Only</span></span>|<span data-ttu-id="4325b-396">« Autres + 1 »</span><span class="sxs-lookup"><span data-stu-id="4325b-396">“Other +1”</span></span>|<span data-ttu-id="4325b-397">^ + 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="4325b-397">^+1(\d{10})$</span></span>|<span data-ttu-id="4325b-398">3</span><span class="sxs-lookup"><span data-stu-id="4325b-398">3</span></span>|<span data-ttu-id="4325b-399">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4325b-399">sbc5<span></span>.contoso.biz</span></span><br/><span data-ttu-id="4325b-400">sbc6<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4325b-400">sbc6<span></span>.contoso.biz</span></span>|<span data-ttu-id="4325b-401">Itinéraire pour appelé numéros + 1 XXX XXX XX XX (sauf XXX-XX-XX +1 425 ou XXX-XX-XX +1 206)</span><span class="sxs-lookup"><span data-stu-id="4325b-401">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="4325b-402">International</span><span class="sxs-lookup"><span data-stu-id="4325b-402">International</span></span>|<span data-ttu-id="4325b-403">International</span><span class="sxs-lookup"><span data-stu-id="4325b-403">International</span></span>|<span data-ttu-id="4325b-404">\d+</span><span class="sxs-lookup"><span data-stu-id="4325b-404">\d+</span></span>|<span data-ttu-id="4325b-405">4</span><span class="sxs-lookup"><span data-stu-id="4325b-405">4</span></span>|<span data-ttu-id="4325b-406">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4325b-406">sbc2<span></span>.contoso.biz</span></span><br/><span data-ttu-id="4325b-407">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="4325b-407">sbc5<span></span>.contoso.biz</span></span>|<span data-ttu-id="4325b-408">Itinéraire pour n’importe quel modèle de numéro</span><span class="sxs-lookup"><span data-stu-id="4325b-408">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="4325b-409">L’ordre des utilisations PSTN dans les stratégies de routage voix est essentielle.</span><span class="sxs-lookup"><span data-stu-id="4325b-409">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="4325b-410">Les utilisations sont appliquées dans l’ordre, et si une correspondance est trouvée dans la première utilisation, puis autres utilisations ne sont jamais évaluées.</span><span class="sxs-lookup"><span data-stu-id="4325b-410">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="4325b-411">L’utilisation PSTN « International » doit être placée après l’utilisation PSTN « Nous uniquement. »</span><span class="sxs-lookup"><span data-stu-id="4325b-411">The PSTN Usage “International” must be placed after the PSTN Usage “US Only.”</span></span> <span data-ttu-id="4325b-412">Pour modifier l’ordre des utilisations PSTN, exécutez le `Set-CSOnlineRouteRoutingPolicy` commande.</span><span class="sxs-lookup"><span data-stu-id="4325b-412">To change the order of the PSTN Usages, please run the `Set-CSOnlineRouteRoutingPolicy` command.</span></span> <br/><span data-ttu-id="4325b-413">Par exemple, pour modifier l’ordre de « Nous et Canada » deuxième prénom et « International » à l’ordre inverse exécutez :</span><span class="sxs-lookup"><span data-stu-id="4325b-413">For example, to change the order from “US and Canada” first and “International” second to the reverse order run:</span></span><br/>   `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="4325b-414">La priorité de « Autres + 1 » et « International » des itinéraires sont affectés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="4325b-414">The priority for  “Other +1” and “International” Voice routes are assigned automatically.</span></span> <span data-ttu-id="4325b-415">Ils n’a pas d’importance tant qu’ils ont des priorités inférieures à « Redmond 1 » et « Redmond 2 ».</span><span class="sxs-lookup"><span data-stu-id="4325b-415">They don’t matter as long as they have lower priorities than “Redmond 1” and “Redmond 2.”</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="4325b-416">Exemple de la stratégie de routage voix pour l’utilisateur John Woods</span><span class="sxs-lookup"><span data-stu-id="4325b-416">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="4325b-417">Stratégie de routage « No Restrictions, » vocale itinéraire « International », vocale à la procédure de création d’utilisation PSTN « International », et puis en l’affectant à l’utilisateur « John Woods » sont les suivantes.</span><span class="sxs-lookup"><span data-stu-id="4325b-417">The steps to create PSTN Usage “International”, voice route “International,” Voice Routing Policy “No Restrictions,” and then assigning it to the user “John Woods” are as follows.</span></span>


1.  <span data-ttu-id="4325b-418">Tout d’abord, créez l’utilisation PSTN « International ».</span><span class="sxs-lookup"><span data-stu-id="4325b-418">First, create the PSTN Usage “International."</span></span> <span data-ttu-id="4325b-419">Dans une session PowerShell distante dans Skype pour Business Online, entrez :</span><span class="sxs-lookup"><span data-stu-id="4325b-419">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

  ```
  Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="International"}
  ```

2.  <span data-ttu-id="4325b-420">Ensuite, créez l’itinéraire des communications vocales « International ».</span><span class="sxs-lookup"><span data-stu-id="4325b-420">Next, create the new voice route “International.”</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
  ```
  <span data-ttu-id="4325b-421">Qui retourne :</span><span class="sxs-lookup"><span data-stu-id="4325b-421">Which returns:</span></span>

  <pre>
  Identity                  : International 
  Priority                      : 5
  Description                   : 
  NumberPattern                 : \d+
  OnlinePstnUsages          : {International}    
  OnlinePstnGatewayList           : {sbc2.contoso.biz, sbc5.contoso.biz}
  Name                            : International
  SupressCallerId           :
  AlternateCallerId         :
</pre>
3.  <span data-ttu-id="4325b-422">Ensuite, ne créez une stratégie de routage voix « Aucune restriction ».</span><span class="sxs-lookup"><span data-stu-id="4325b-422">Next, create a Voice Routing Policy “No Restrictions”.</span></span> <span data-ttu-id="4325b-423">L’utilisation PSTN « Redmond 1 » et « Redmond » sont réutilisés dans cette stratégie de routage voix pour conserver les appels vers le numéro « +1 425 XX XXX XX » et « +1 206 XX XXX XX » comme des appels locaux ou dans les locaux de traitement particulier.</span><span class="sxs-lookup"><span data-stu-id="4325b-423">The PSTN Usage “Redmond 1” and “Redmond “ are reused in this voice routing policy to preserve special handling for calls to number “+1 425 XXX XX XX” and “+1 206 XXX XX XX” as local or on-premise calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”
```

    Take note of the order of PSTN Usages:

    a. If a call made to number “+1425 XXX XX XX” with the usages configured as in the following example, the call follows the route set in “US and Canada” usage and the special routing logic is applied. That is, the call is routed using  sbc1<span></span>.contoso.biz and sbc2<span></span>.contoso.biz first, and then  sbc3<span></span>.contoso.biz and sbc4<span></span>.contoso.biz as the backup routes. 

    b.  If “International” PSTN usage is before “US and Canada,” calls to + 1425 XXX XX XX are routed to sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”```

   <span data-ttu-id="4325b-424">Qui retourne</span><span class="sxs-lookup"><span data-stu-id="4325b-424">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4.  <span data-ttu-id="4325b-425">Attribuer la stratégie de routage voix à l’utilisateur « John Woods » à l’aide de la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="4325b-425">Assign the voice routing policy to the user “John Woods” using the following command.</span></span>

  ```
  Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
  ```

  <span data-ttu-id="4325b-426">Vérifiez l’affectation à l’aide de la commande :</span><span class="sxs-lookup"><span data-stu-id="4325b-426">Then verify the assignment using the command:</span></span>   

  ```
  Get CsOnlineUser “John Woods” | Select OnlineVoiceRoutingPolicy
  ```
  <span data-ttu-id="4325b-427">Qui retourne :</span><span class="sxs-lookup"><span data-stu-id="4325b-427">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="4325b-428">Le résultat est que la stratégie de voix appliquée aux appels de John Woods sont non restreint et doit suivre la logique de routage des appels disponible pour les États-Unis, au Canada et International appel.</span><span class="sxs-lookup"><span data-stu-id="4325b-428">The result is that the voice policy applied to John Woods’ calls are unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-users"></a><span data-ttu-id="4325b-429">Définir Teams Microsoft en tant que client appelant par défaut pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="4325b-429">Set Microsoft Teams as the preferred calling client for users</span></span>

<span data-ttu-id="4325b-430">Routage direct achemine uniquement les appels vers et depuis les utilisateurs s’ils utilisent le client d’équipes.</span><span class="sxs-lookup"><span data-stu-id="4325b-430">Direct Routing only routes calls to and from users if they use the Teams client.</span></span> <span data-ttu-id="4325b-431">Si votre organisation utilise uniquement des équipes, « Équipes uniquement » mode dans la stratégie de mise à niveau est recommandé de définir.</span><span class="sxs-lookup"><span data-stu-id="4325b-431">If your organization only uses Teams, setting "Teams Only" mode in upgrade policy is recommended.</span></span> <span data-ttu-id="4325b-432">Si votre organisation utilise Skype pour Business Server ou Skype pour Business Online, consultez l’article suivant pour plus d’informations et sélectionnez l’option appropriée : [comprendre la coexistence et voyage Skype pour professionnels et les équipes de mise à niveau](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="4325b-432">If you organization uses Skype for Business Server or Skype for Business Online, see the following article for more information and select the appropriate option:  [Understand coexistence and upgrade journey for Skype for Business and Teams](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 


## <a name="see-also"></a><span data-ttu-id="4325b-433">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4325b-433">See also</span></span>

[<span data-ttu-id="4325b-434">Planifier le routage Direct</span><span class="sxs-lookup"><span data-stu-id="4325b-434">Plan Direct Routing</span></span>](direct-routing-plan.md)
