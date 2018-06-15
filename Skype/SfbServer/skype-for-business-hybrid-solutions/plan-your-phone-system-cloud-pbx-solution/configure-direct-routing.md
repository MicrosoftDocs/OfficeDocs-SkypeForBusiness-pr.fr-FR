---
title: Configurer le routage Direct
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/15/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Découvrez comment configurer le routage Direct de Microsoft Phone System.
ms.openlocfilehash: 8b132174a305e55d79b935ceec5105fcfc1fc2e6
ms.sourcegitcommit: 6c3bf5f453188bc951e92aa26b5562bf6680d4d7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2018
ms.locfileid: "19907943"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="f806d-103">Configurer le routage Direct</span><span class="sxs-lookup"><span data-stu-id="f806d-103">Configure Direct Routing</span></span>

  > [!NOTE]
  > <span data-ttu-id="f806d-104">Il s’agit d’une version préliminaire de routage Direct de Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="f806d-104">This is a preview release of Microsoft Phone System Direct Routing.</span></span>  <span data-ttu-id="f806d-105">Documentation et des fonctionnalités du produit peuvent être modifiées.</span><span class="sxs-lookup"><span data-stu-id="f806d-105">Product functionality and documentation are subject to change.</span></span>

<span data-ttu-id="f806d-106">Si vous n’avez pas déjà fait, lisez la [Planifier le routage Direct](plan-direct-routing.md) pour les composants requis et pour passer en revue les autres étapes, vous devrez prendre avant de configurer votre réseau de système téléphonique de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f806d-106">If you have not already done so, read [Plan Direct Routing](plan-direct-routing.md) for prerequisites and to review  other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="f806d-107">Ce document est destiné aux professionnels de l’informatique.</span><span class="sxs-lookup"><span data-stu-id="f806d-107">This document is intended for IT professionals.</span></span>  

<span data-ttu-id="f806d-108">Cet article explique comment configurer le routage Direct de Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="f806d-108">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="f806d-109">Il décrit en détail comment associer un contrôleur de bordure Session pris en charge (SBC) pour le routage Direct et configurer les utilisateurs de Microsoft Teams pour utiliser le routage directe pour se connecter à la Public téléphone réseau commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="f806d-109">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="f806d-110">Pour effectuer les étapes décrites dans cet article, les administrateurs doivent se familiariser avec les applets de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f806d-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="f806d-111">Pour plus d’informations sur l’utilisation de PowerShell, voir [configurer votre ordinateur pour Windows PowerShell](https://technet.microsoft.com/library/dn362831.aspx).</span><span class="sxs-lookup"><span data-stu-id="f806d-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831.aspx).</span></span> 

<span data-ttu-id="f806d-112">Nous vous recommandons de vérifier que votre contrôleur SBC a déjà été configuré comme recommandé par votre fournisseur SBC :</span><span class="sxs-lookup"><span data-stu-id="f806d-112">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor's:</span></span> 

- <span data-ttu-id="f806d-113">Documentation de déploiement AudioCodes</span><span class="sxs-lookup"><span data-stu-id="f806d-113">AudioCodes deployment documentation</span></span> 
- <span data-ttu-id="f806d-114">Documentation de déploiement du ruban</span><span class="sxs-lookup"><span data-stu-id="f806d-114">Ribbon deployment documentation</span></span>

<span data-ttu-id="f806d-115">Vous pouvez configurer votre système téléphonique de Microsoft et permettre aux utilisateurs d’utiliser le routage Direct, puis configurer Teams Microsoft en tant que client appelant par défaut en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="f806d-115">You can configure your Microsoft Phone System and enable  users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="f806d-116">Paire le contrôleur SBC avec un système téléphonique de Microsoft et valider l’appariement</span><span class="sxs-lookup"><span data-stu-id="f806d-116">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-direct-routing-service-of-phone-system)
- [<span data-ttu-id="f806d-117">Activer les utilisateurs pour le Service de routage Direct</span><span class="sxs-lookup"><span data-stu-id="f806d-117">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- [<span data-ttu-id="f806d-118">Assurez-vous que Microsoft Teams est le client appelant par défaut pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f806d-118">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>](#set-microsoft-teams-as-the-preferred-calling-client-for-the-users) 

## <a name="pair-the-sbc-to-direct-routing-service-of-phone-system"></a><span data-ttu-id="f806d-119">Paire le contrôleur SBC pour diriger le Service de routage du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="f806d-119">Pair the SBC to Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="f806d-120">Voici les trois étapes principales pour vous permettre de vous connecter, ou paire, le contrôleur SBC à l’interface de routage Direct :</span><span class="sxs-lookup"><span data-stu-id="f806d-120">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

- <span data-ttu-id="f806d-121">Se connecter au centre d’administration de **Skype pour Business Online** à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="f806d-121">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
- <span data-ttu-id="f806d-122">Paire le contrôleur SBC</span><span class="sxs-lookup"><span data-stu-id="f806d-122">Pair the SBC</span></span> 
- <span data-ttu-id="f806d-123">Valider l’appariement</span><span class="sxs-lookup"><span data-stu-id="f806d-123">Validate the pairing</span></span> 

### <a name="connect-to--skype-for-business-online-by-using-powershell"></a><span data-ttu-id="f806d-124">Se connecter à Skype pour Business Online à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="f806d-124">Connect to  Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="f806d-125">Vous pouvez utiliser une session PowerShell connectée au client pour le couplage le contrôleur SBC à l’interface de routage Direct.</span><span class="sxs-lookup"><span data-stu-id="f806d-125">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="f806d-126">Pour ouvrir une session PowerShell, suivez les étapes décrites dans la [configuration de votre ordinateur pour Windows PowerShell](https://technet.microsoft.com/library/dn362831.aspx).</span><span class="sxs-lookup"><span data-stu-id="f806d-126">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831.aspx).</span></span> 
 
<span data-ttu-id="f806d-127">Après avoir établi une session PowerShell distante, vérifiez que vous pouvez voir les commandes pour gérer le contrôleur SBC.</span><span class="sxs-lookup"><span data-stu-id="f806d-127">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="f806d-128">Pour valider les commandes, tapez ou copier/coller dans ce qui suit dans la session PowerShell et appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="f806d-128">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```
gcm *onlinePSTNGateway*
```

<span data-ttu-id="f806d-129">Votre commande renverra les quatre fonctions indiquées ici qui vous permet de gérer les SBCs.</span><span class="sxs-lookup"><span data-stu-id="f806d-129">Your command will return the four functions shown here that will let you manage the SBCs.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="f806d-130">Paire le contrôleur SBC au client</span><span class="sxs-lookup"><span data-stu-id="f806d-130">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="f806d-131">Pour associer le contrôleur SBC au client, dans la session PowerShell, tapez ce qui suit et appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="f806d-131">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="f806d-132">Nous vous recommandons la définition d’une limite pour le contrôleur SBC, en utilisant les informations que vous trouverez dans la documentation de SBC.</span><span class="sxs-lookup"><span data-stu-id="f806d-132">We highly recommend setting a limit for the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="f806d-133">La limite de déclencher une notification si le contrôleur SBC est au niveau de la capacité.</span><span class="sxs-lookup"><span data-stu-id="f806d-133">The limit will trigger a notification if SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="f806d-134">Vous pouvez uniquement paire le contrôleur SBC avec le nom de domaine complet, où la partie domaine du nom correspond à l’un des domaines enregistrés dans votre client, à l’exception de \*. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="f806d-134">You can only pair the SBC with FQDN, where the domain portion of the name matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="f806d-135">À l’aide de \*. omicrosoft.com les noms de domaine n’est pas pris en charge pour les noms FQDN SBC.</span><span class="sxs-lookup"><span data-stu-id="f806d-135">Using \*.omicrosoft.com domain names is not supported for the SBC FQDN names.</span></span> <span data-ttu-id="f806d-136">Par exemple, si vous avez deux noms de domaine :</span><span class="sxs-lookup"><span data-stu-id="f806d-136">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="f806d-137">.xyz **ABC**</span><span class="sxs-lookup"><span data-stu-id="f806d-137">**abc**.xyz</span></span><br/><span data-ttu-id="f806d-138">**ABC**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="f806d-138">**abc**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="f806d-139">Pour le nom SBC, vous pouvez utiliser le nom sbc.abc.xyz.</span><span class="sxs-lookup"><span data-stu-id="f806d-139">For the SBC name, you can use the name sbc.abc.xyz.</span></span> <span data-ttu-id="f806d-140">Si vous essayez de paire le contrôleur SBC avec un nom de sbc.xyz.abc, le système ne vous permettra pas, comme le domaine n’est pas détenu par ce client.</span><span class="sxs-lookup"><span data-stu-id="f806d-140">If you try to pair the SBC with a name sbc.xyz.abc, the system will not let you, as the domain is not owned by this tenant.</span></span>

```
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="f806d-141">Propriété renvoie :</span><span class="sxs-lookup"><span data-stu-id="f806d-141">Returns:</span></span>
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
<span data-ttu-id="f806d-142">Il existe des options supplémentaires qui peuvent être définies lors de l’appariement.</span><span class="sxs-lookup"><span data-stu-id="f806d-142">There are additional options that can be set during the pairing.</span></span> <span data-ttu-id="f806d-143">Dans l’exemple précédent, toutefois, seulement la configuration minimale requise paramètres sont affichés.</span><span class="sxs-lookup"><span data-stu-id="f806d-143">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="f806d-144">Le tableau suivant répertorie les paramètres supplémentaires que vous pouvez utiliser dans la définition des paramètres de *New-CsOnlinePstnGateway*.</span><span class="sxs-lookup"><span data-stu-id="f806d-144">The following table lists the additional parameters that you can use in setting parameters for *New-CsOnlinePstnGateway*.</span></span> 

|<span data-ttu-id="f806d-145">Obligatoire ?</span><span class="sxs-lookup"><span data-stu-id="f806d-145">Required?</span></span>|<span data-ttu-id="f806d-146">Nom</span><span class="sxs-lookup"><span data-stu-id="f806d-146">Name</span></span>|<span data-ttu-id="f806d-147">Description</span><span class="sxs-lookup"><span data-stu-id="f806d-147">Description</span></span>|<span data-ttu-id="f806d-148">Par défaut</span><span class="sxs-lookup"><span data-stu-id="f806d-148">Default</span></span>|<span data-ttu-id="f806d-149">Valeurs possibles</span><span class="sxs-lookup"><span data-stu-id="f806d-149">Possible values</span></span>|<span data-ttu-id="f806d-150">Type et restrictions</span><span class="sxs-lookup"><span data-stu-id="f806d-150">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f806d-151">Oui</span><span class="sxs-lookup"><span data-stu-id="f806d-151">Yes</span></span>|<span data-ttu-id="f806d-152">FQDN</span><span class="sxs-lookup"><span data-stu-id="f806d-152">FQDN</span></span>|<span data-ttu-id="f806d-153">Le nom de domaine complet de le SBC</span><span class="sxs-lookup"><span data-stu-id="f806d-153">The FQDN name of the SBC</span></span> |<span data-ttu-id="f806d-154">Aucun</span><span class="sxs-lookup"><span data-stu-id="f806d-154">None</span></span>|<span data-ttu-id="f806d-155">Nom de NoneFQDN, limite 63 caractères</span><span class="sxs-lookup"><span data-stu-id="f806d-155">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="f806d-156">Chaîne, liste de caractères autorisés et non autorisés sur [les conventions d’attribution de noms dans Active Directory pour les ordinateurs, les domaines, les sites et les unités d’organisation](https://support.microsoft.com/en-us/help/909264)</span><span class="sxs-lookup"><span data-stu-id="f806d-156">String,  list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/en-us/help/909264)</span></span>|
|<span data-ttu-id="f806d-157">Non</span><span class="sxs-lookup"><span data-stu-id="f806d-157">No</span></span>|<span data-ttu-id="f806d-158">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="f806d-158">MediaBypass</span></span> |<span data-ttu-id="f806d-159">Le paramètre est réservé pour une utilisation future.</span><span class="sxs-lookup"><span data-stu-id="f806d-159">The parameter reserved for future use.</span></span> <span data-ttu-id="f806d-160">Paramètre indiqué du contrôleur SBC prend en charge le contournement de média et l’administrateur souhaite l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="f806d-160">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="f806d-161">Aucun</span><span class="sxs-lookup"><span data-stu-id="f806d-161">None</span></span>|<span data-ttu-id="f806d-162">True</span><span class="sxs-lookup"><span data-stu-id="f806d-162">True</span></span><br/><span data-ttu-id="f806d-163">Faux</span><span class="sxs-lookup"><span data-stu-id="f806d-163">False</span></span>|<span data-ttu-id="f806d-164">Boléen</span><span class="sxs-lookup"><span data-stu-id="f806d-164">Boolean</span></span>|
|<span data-ttu-id="f806d-165">Oui</span><span class="sxs-lookup"><span data-stu-id="f806d-165">Yes</span></span>|<span data-ttu-id="f806d-166">SipSignallingPort</span><span class="sxs-lookup"><span data-stu-id="f806d-166">SipSignallingPort</span></span> |<span data-ttu-id="f806d-167">Port d’écoute utilisé pour communiquer avec les services de routage Direct à l’aide du protocole de Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="f806d-167">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="f806d-168">Aucun</span><span class="sxs-lookup"><span data-stu-id="f806d-168">None</span></span>|<span data-ttu-id="f806d-169">N’importe quel port</span><span class="sxs-lookup"><span data-stu-id="f806d-169">Any port</span></span>|<span data-ttu-id="f806d-170">comprise entre 0 et 65535</span><span class="sxs-lookup"><span data-stu-id="f806d-170">0 to 65535</span></span> |
|<span data-ttu-id="f806d-171">Non</span><span class="sxs-lookup"><span data-stu-id="f806d-171">No</span></span>|<span data-ttu-id="f806d-172">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="f806d-172">FailoverTimeSeconds</span></span> |<span data-ttu-id="f806d-173">Lorsque la valeur 10 (valeur par défaut), les appels sortants qui ne sont pas traitées par la passerelle dans les 10 secondes sont routés vers le tronçon suivant disponible ; s’il n’y a aucune jonctions supplémentaires, l’appel est automatiquement supprimé.</span><span class="sxs-lookup"><span data-stu-id="f806d-173">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="f806d-174">Dans une organisation avec des réponses de passerelle ou réseau lentes, cela peut entraîner l’abandon de nombreux appels.</span><span class="sxs-lookup"><span data-stu-id="f806d-174">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="f806d-175">La valeur par défaut est 10.</span><span class="sxs-lookup"><span data-stu-id="f806d-175">The default value is 10.</span></span>|<span data-ttu-id="f806d-176">10</span><span class="sxs-lookup"><span data-stu-id="f806d-176">10</span></span>|<span data-ttu-id="f806d-177">Numéro</span><span class="sxs-lookup"><span data-stu-id="f806d-177">Number</span></span>|<span data-ttu-id="f806d-178">Int</span><span class="sxs-lookup"><span data-stu-id="f806d-178">Int</span></span>|
|<span data-ttu-id="f806d-179">Non</span><span class="sxs-lookup"><span data-stu-id="f806d-179">No</span></span>|<span data-ttu-id="f806d-180">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="f806d-180">ForwardCallHistory</span></span> |<span data-ttu-id="f806d-181">Indique si les informations d’historique d’appel sont transférées par le biais de la jonction.</span><span class="sxs-lookup"><span data-stu-id="f806d-181">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="f806d-182">Si activé, le Proxy de PSTN Office 365 envoie deux en-têtes : historique-info et visé par.</span><span class="sxs-lookup"><span data-stu-id="f806d-182">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="f806d-183">La valeur par défaut est **False** ($False).</span><span class="sxs-lookup"><span data-stu-id="f806d-183">The default value is **False** ($False).</span></span> |<span data-ttu-id="f806d-184">Faux</span><span class="sxs-lookup"><span data-stu-id="f806d-184">False</span></span>|<span data-ttu-id="f806d-185">True</span><span class="sxs-lookup"><span data-stu-id="f806d-185">True</span></span><br/><span data-ttu-id="f806d-186">Faux</span><span class="sxs-lookup"><span data-stu-id="f806d-186">False</span></span>|<span data-ttu-id="f806d-187">Boléen</span><span class="sxs-lookup"><span data-stu-id="f806d-187">Boolean</span></span>|
|<span data-ttu-id="f806d-188">Non</span><span class="sxs-lookup"><span data-stu-id="f806d-188">No</span></span>|<span data-ttu-id="f806d-189">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="f806d-189">ForwardPAI</span></span>|<span data-ttu-id="f806d-190">Indique si l’en-tête P-Asserted-Identity (PAI) sera transféré avec l’appel.</span><span class="sxs-lookup"><span data-stu-id="f806d-190">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="f806d-191">L’en-tête PAI est un moyen de vérifier l’identité de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="f806d-191">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="f806d-192">La valeur par défaut est **False** ($False).</span><span class="sxs-lookup"><span data-stu-id="f806d-192">The default value is **False** ($False).</span></span>|<span data-ttu-id="f806d-193">Faux</span><span class="sxs-lookup"><span data-stu-id="f806d-193">False</span></span>|<span data-ttu-id="f806d-194">True</span><span class="sxs-lookup"><span data-stu-id="f806d-194">True</span></span><br/><span data-ttu-id="f806d-195">Faux</span><span class="sxs-lookup"><span data-stu-id="f806d-195">False</span></span>|<span data-ttu-id="f806d-196">Boléen</span><span class="sxs-lookup"><span data-stu-id="f806d-196">Boolean</span></span>|
|<span data-ttu-id="f806d-197">Non</span><span class="sxs-lookup"><span data-stu-id="f806d-197">No</span></span>|<span data-ttu-id="f806d-198">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="f806d-198">SendSIPOptions</span></span> |<span data-ttu-id="f806d-199">Définit si un contrôleur SBC sera ou n’envoie pas les options SIP.</span><span class="sxs-lookup"><span data-stu-id="f806d-199">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="f806d-200">Si désactivé, le contrôleur SBC sera exclu de système de surveillance et d’alerte.</span><span class="sxs-lookup"><span data-stu-id="f806d-200">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="f806d-201">Il est vivement recommandé d’activer les options de SIP.</span><span class="sxs-lookup"><span data-stu-id="f806d-201">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="f806d-202">Valeur par défaut est **True**.</span><span class="sxs-lookup"><span data-stu-id="f806d-202">Default value is **True**.</span></span> |<span data-ttu-id="f806d-203">True</span><span class="sxs-lookup"><span data-stu-id="f806d-203">True</span></span>|<span data-ttu-id="f806d-204">True</span><span class="sxs-lookup"><span data-stu-id="f806d-204">True</span></span><br/><span data-ttu-id="f806d-205">Faux</span><span class="sxs-lookup"><span data-stu-id="f806d-205">False</span></span>|<span data-ttu-id="f806d-206">Boléen</span><span class="sxs-lookup"><span data-stu-id="f806d-206">Boolean</span></span>|
|<span data-ttu-id="f806d-207">Non</span><span class="sxs-lookup"><span data-stu-id="f806d-207">No</span></span>|<span data-ttu-id="f806d-208">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="f806d-208">MaxConcurrentSessions</span></span> |<span data-ttu-id="f806d-209">Utilisé par le système d’alerte.</span><span class="sxs-lookup"><span data-stu-id="f806d-209">Used by alerting system.</span></span> <span data-ttu-id="f806d-210">Lorsqu’une valeur est définie, le système d’alerte génère une alerte à l’administrateur de clients lorsque le nombre de sessions simultanées est 90 % ou supérieure à cette valeur.</span><span class="sxs-lookup"><span data-stu-id="f806d-210">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="f806d-211">Si le paramètre n’est pas défini, les alertes ne sont pas générés.</span><span class="sxs-lookup"><span data-stu-id="f806d-211">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="f806d-212">Toutefois, le système de surveillance signalera nombre de sessions simultanées toutes les 24 heures.</span><span class="sxs-lookup"><span data-stu-id="f806d-212">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="f806d-213">Null</span><span class="sxs-lookup"><span data-stu-id="f806d-213">Null</span></span>|<span data-ttu-id="f806d-214">Null</span><span class="sxs-lookup"><span data-stu-id="f806d-214">Null</span></span><br/><span data-ttu-id="f806d-215">1 et 100 000</span><span class="sxs-lookup"><span data-stu-id="f806d-215">1 to 100,000</span></span> ||
|<span data-ttu-id="f806d-216">Non</span><span class="sxs-lookup"><span data-stu-id="f806d-216">No</span></span>|<span data-ttu-id="f806d-217">Activé \*</span><span class="sxs-lookup"><span data-stu-id="f806d-217">Enabled\*</span></span>|<span data-ttu-id="f806d-218">Permet d’activer cette SBC pour les appels sortants.</span><span class="sxs-lookup"><span data-stu-id="f806d-218">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="f806d-219">Peut être utilisée pour supprimer temporairement le contrôleur SBC, pendant qu’il est en cours de mise à jour ou lors de la maintenance.</span><span class="sxs-lookup"><span data-stu-id="f806d-219">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="f806d-220">Faux</span><span class="sxs-lookup"><span data-stu-id="f806d-220">False</span></span>|<span data-ttu-id="f806d-221">True</span><span class="sxs-lookup"><span data-stu-id="f806d-221">True</span></span><br/><span data-ttu-id="f806d-222">Faux</span><span class="sxs-lookup"><span data-stu-id="f806d-222">False</span></span>|<span data-ttu-id="f806d-223">Boléen</span><span class="sxs-lookup"><span data-stu-id="f806d-223">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="f806d-224">Vérifiez l’appariement SBC</span><span class="sxs-lookup"><span data-stu-id="f806d-224">Verify the SBC pairing</span></span> 

<span data-ttu-id="f806d-225">Vérifiez la connexion :</span><span class="sxs-lookup"><span data-stu-id="f806d-225">Verify the connection:</span></span> 
- <span data-ttu-id="f806d-226">Vérifiez si le contrôleur SBC est dans la liste des paires SBCs.</span><span class="sxs-lookup"><span data-stu-id="f806d-226">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="f806d-227">Valider les Options SIP.</span><span class="sxs-lookup"><span data-stu-id="f806d-227">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="f806d-228">Valider si SBC se trouve dans la liste des paires SBCs</span><span class="sxs-lookup"><span data-stu-id="f806d-228">Validate if SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="f806d-229">Après avoir paire le contrôleur SBC, vérifier que le contrôleur SBC est présent dans la liste des paires SBCs en exécutant la commande suivante dans une session PowerShell distante :`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="f806d-229">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command  in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="f806d-230">La passerelle couplée doit apparaissent dans la liste, comme illustré dans l’exemple ci-dessous, puis vérifiez que le paramètre *Enabled* affiche la valeur **True**.</span><span class="sxs-lookup"><span data-stu-id="f806d-230">The paired gateway should appear in the list as shown in the example below, and verify that the parameter *Enabled* displays the value **True**.</span></span> <span data-ttu-id="f806d-231">Entrez :</span><span class="sxs-lookup"><span data-stu-id="f806d-231">Enter:</span></span>

```
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="f806d-232">Qui retourne :</span><span class="sxs-lookup"><span data-stu-id="f806d-232">Which returns:</span></span>
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

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="f806d-233">Contrôler le flux d’Options SIP</span><span class="sxs-lookup"><span data-stu-id="f806d-233">Validate SIP Options flow</span></span> 

<span data-ttu-id="f806d-234">Pour valider l’association à l’aide des Options SIP sortant, utilisez l’interface de gestion SBC et voir que le contrôleur SBC 200 OK réponses aux OPTIONS sortantes.</span><span class="sxs-lookup"><span data-stu-id="f806d-234">To validate the pairing using outgoing SIP Options, use the SBC management interface and see that the SBC get 200 OK responses to the outgoing OPTIONS.</span></span>
  
<span data-ttu-id="f806d-235">Lorsque le routage Direct voit des OPTIONS entrantes, il démarre sortantes options d’envoi pour le nom de domaine complet SBC configuré dans le champ en-tête de Contact dans le message entrant d’OPTIONS.</span><span class="sxs-lookup"><span data-stu-id="f806d-235">When Direct Routing sees incoming OPTIONS, it will start sending outgoing options to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="f806d-236">Pour valider l’association à l’aide des Options SIP entrants, utilisez l’interface de gestion SBC et voir que le contrôleur SBC réponse sur les messages OPTIONS provenant routage Direct, et que le code de réponse est 200 OK.</span><span class="sxs-lookup"><span data-stu-id="f806d-236">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC gets reply on the OPTIONS messages coming in from Direct Routing and that the response code is 200 OK.</span></span>  

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="f806d-237">Activer les utilisateurs pour le Service de routage Direct</span><span class="sxs-lookup"><span data-stu-id="f806d-237">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="f806d-238">Lorsque vous êtes prêt à activer les utilisateurs pour le Service de routage Direct, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f806d-238">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="f806d-239">Créer un utilisateur dans Office 365 et attribuer une licence de système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="f806d-239">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="f806d-240">Assurez-vous que l’utilisateur est hébergé dans Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="f806d-240">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="f806d-241">Configurer le numéro de téléphone et activer la messagerie vocale et enterprise voice.</span><span class="sxs-lookup"><span data-stu-id="f806d-241">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="f806d-242">Configurer le routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="f806d-242">Configure voice routing.</span></span> <span data-ttu-id="f806d-243">L’itinéraire est automatiquement validé.</span><span class="sxs-lookup"><span data-stu-id="f806d-243">The route is automatically validated.</span></span>  

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="f806d-244">Créer un utilisateur dans Office 365 et attribuer la licence</span><span class="sxs-lookup"><span data-stu-id="f806d-244">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="f806d-245">Il existe deux options pour la création d’un nouvel utilisateur dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="f806d-245">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="f806d-246">Toutefois, nous conseillons de votre organisation sélectionner une option permet d’éviter les problèmes de routage :</span><span class="sxs-lookup"><span data-stu-id="f806d-246">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="f806d-247">Créer l’utilisateur dans Active Directory de locaux et synchroniser l’utilisateur vers le nuage.</span><span class="sxs-lookup"><span data-stu-id="f806d-247">Create the user in on-premise Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="f806d-248">Voir les [répertoires intégrer votre locale avec Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="f806d-248">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span></span>  
- <span data-ttu-id="f806d-249">Créer l’utilisateur directement dans le portail d’administrateur Office 365.</span><span class="sxs-lookup"><span data-stu-id="f806d-249">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="f806d-250">Consultez la rubrique [Ajouter des utilisateurs individuellement ou par lot pour Office 365 - aide d’administration](https://support.office.com/en-us/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="f806d-250">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/en-us/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

  <span data-ttu-id="f806d-251">Si vous générez le système coexiste avec Skype pour Business 2015 ou Lync 2010/2013 locale, la seule option prise en charge consiste à créer l’utilisateur dans l’annuaire local et synchronisation de l’utilisateur vers le nuage (Option 1).</span><span class="sxs-lookup"><span data-stu-id="f806d-251">If you build the system that co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="f806d-252">Licences requises :</span><span class="sxs-lookup"><span data-stu-id="f806d-252">Required licenses:</span></span> 

- <span data-ttu-id="f806d-253">Office 365 entreprise E3 (y compris SfB Plan2, Plan2 Exchange et les équipes) + système de téléphone.</span><span class="sxs-lookup"><span data-stu-id="f806d-253">Office 365 Enterprise E3 (including SfB Plan2, Exchange Plan2, and Teams) + Phone System</span></span>  
- <span data-ttu-id="f806d-254">Office 365 entreprise E5 (y compris SfB Plan2 Plan2 Exchange et les équipes système téléphonique)</span><span class="sxs-lookup"><span data-stu-id="f806d-254">Office 365 Enterprise E5  (including SfB Plan2, Exchange Plan2, Teams, and Phone System)</span></span> 

<span data-ttu-id="f806d-255">Licences facultatifs :</span><span class="sxs-lookup"><span data-stu-id="f806d-255">Optional licenses:</span></span> 

- <span data-ttu-id="f806d-256">Appel de Plan</span><span class="sxs-lookup"><span data-stu-id="f806d-256">Calling Plan</span></span> 
- <span data-ttu-id="f806d-257">Audioconférence</span><span class="sxs-lookup"><span data-stu-id="f806d-257">Audio Conferencing</span></span> 

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="f806d-258">Assurez-vous que l’utilisateur est hébergé dans Skype pour Business Online</span><span class="sxs-lookup"><span data-stu-id="f806d-258">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="f806d-259">Routage direct, l’utilisateur doit être hébergé dans Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="f806d-259">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="f806d-260">Vous pouvez le vérifier en regardant le paramètre RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="f806d-260">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="f806d-261">Il doit avoir une valeur dans le domaine infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="f806d-261">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="f806d-262">Se connecter à PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="f806d-262">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="f806d-263">Exécutez la commande :</span><span class="sxs-lookup"><span data-stu-id="f806d-263">Issue the command:</span></span> 

```
Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="f806d-264">Configurer le numéro de téléphone et activer la messagerie vocale et enterprise voice</span><span class="sxs-lookup"><span data-stu-id="f806d-264">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="f806d-265">Après avoir créé l’utilisateur et attribué une licence, l’étape suivante consiste à configurer leur numéro de téléphone et la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="f806d-265">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="f806d-266">Pour cela, en une seule étape.</span><span class="sxs-lookup"><span data-stu-id="f806d-266">This can be done in one step.</span></span> 

<span data-ttu-id="f806d-267">Pour ajouter le numéro de téléphone et activer pour la messagerie vocale :</span><span class="sxs-lookup"><span data-stu-id="f806d-267">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="f806d-268">Se connecter à une session PowerShell distante.</span><span class="sxs-lookup"><span data-stu-id="f806d-268">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="f806d-269">Entrez la commande :</span><span class="sxs-lookup"><span data-stu-id="f806d-269">Enter the command:</span></span> 
    
```
Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+ phone number
```

<span data-ttu-id="f806d-270">Par exemple, pour ajouter un numéro de téléphone pour l’utilisateur « Spencer faible », entrez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="f806d-270">For example, to add a phone number for user “Spencer Low,” you would enter the following:</span></span> 

```
Set-CsUser - “Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

<span data-ttu-id="f806d-271">Le numéro de téléphone utilisé doit être configuré comme un numéro de téléphone E.164 complète avec le code de pays.</span><span class="sxs-lookup"><span data-stu-id="f806d-271">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

  > [!NOTE]
  > <span data-ttu-id="f806d-272">Si le numéro de téléphone de l’utilisateur est géré sur site, utilisez locale Skype pour Business Management Shell ou le panneau de configuration pour configurer le numéro de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f806d-272">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="f806d-273">Configurer le routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="f806d-273">Configure Voice Routing</span></span> 

<span data-ttu-id="f806d-274">Système téléphonique de Microsoft dispose d’un mécanisme de routage qui permet à un appel à envoyer à un SBC spécifique en fonction de :</span><span class="sxs-lookup"><span data-stu-id="f806d-274">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="f806d-275">Modèle de numéro appelé</span><span class="sxs-lookup"><span data-stu-id="f806d-275">Called number pattern</span></span> 
- <span data-ttu-id="f806d-276">Modèle de numéro appelé + utilisateur spécifique qui effectue l’appel</span><span class="sxs-lookup"><span data-stu-id="f806d-276">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="f806d-277">SBC peut être désignés comme actif et de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="f806d-277">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="f806d-278">Cela signifie que lorsque la SBC est configuré comme active pour ce modèle de numéro, ou un modèle de numéro + un utilisateur spécifique, n’est pas disponible, puis les appels sont acheminés vers un contrôleur SBC sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="f806d-278">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="f806d-279">Routage des appels est composé des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="f806d-279">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="f806d-280">Stratégie de routage voix – conteneur pour les utilisations RTC ; peuvent être attribuées à un utilisateur ou à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f806d-280">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="f806d-281">Utilisations PSTN – conteneur pour les itinéraires de communications vocales et les utilisations RTC ; peuvent être partagées dans différentes stratégies de routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="f806d-281">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="f806d-282">Itinéraires-modèle de numéro et un ensemble de Online passerelles PSTN à utiliser pour les appels où l’appel de numéro correspond au modèle de voix</span><span class="sxs-lookup"><span data-stu-id="f806d-282">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="f806d-283">Passerelle PSTN Online - pointeur SBC, stocke également la configuration est appliquée lors de l’appel est passé via le contrôleur SBC, telles que le transfert P-Asserted-Identity (PAI) ou Codecs par défaut ; peuvent être ajoutés à des itinéraires de communications vocales</span><span class="sxs-lookup"><span data-stu-id="f806d-283">Online PSTN Gateway - pointer at SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="f806d-284">Création d’une stratégie de routage des communications vocales avec une seule utilisation PSTN</span><span class="sxs-lookup"><span data-stu-id="f806d-284">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="f806d-285">Le diagramme suivant illustre les deux exemples de stratégies de routage voix dans le flux d’appels.</span><span class="sxs-lookup"><span data-stu-id="f806d-285">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="f806d-286">**Appel flux 1 (à gauche) :** Si un utilisateur effectue un appel à XXX-XX-XX +1 425 ou XXX-XX-XX +1 206, l’appel est acheminé vers SBC sbc1<span></span>. contoso.biz ou sbc2<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="f806d-286">**Call Flow 1 (on the left):** If a user makes a call to  +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed  to SBC sbc1<span></span>.contoso.biz or sbc2<span></span>.contoso.biz.</span></span> <span data-ttu-id="f806d-287">Si ni sbc1<span></span>. contoso.biz, ni sbc2<span></span>. contoso.biz sont disponibles, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="f806d-287">If neither sbc1<span></span>.contoso.biz nor sbc2<span></span>.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="f806d-288">**Call flux 2 (à droite) :** Si un utilisateur effectue un appel à XXX-XX-XX +1 425 ou XXX-XX-XX +1 206, l’appel est tout d’abord dirigé vers SBC sbc1<span></span>. contoso.biz ou sbc2<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="f806d-288">**Call Flow 2 (on the right):** If a user makes a call to  +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1<span></span>.contoso.biz or sbc2<span></span>.contoso.biz.</span></span> <span data-ttu-id="f806d-289">Si aucun contrôleur SBC est disponible, l’itinéraire dont la priorité est tentée (sbc3<span></span>. contoso.biz et sbc4<span></span>. contoso.biz).</span><span class="sxs-lookup"><span data-stu-id="f806d-289">If neither SBC is available, the route with lower priority will be tried (sbc3<span></span>.contoso.biz and sbc4<span></span>.contoso.biz).</span></span> <span data-ttu-id="f806d-290">Si aucune des SBCs n’est disponibles, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="f806d-290">If none of the SBCs are available, the call is dropped.</span></span> 

![Présente des exemples de stratégie de routage voix](../../media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="f806d-292">Dans les deux exemples, tandis que l’itinéraire de communications vocales est assignée les priorités, les SBCs dans les itinéraires sont traités dans l’ordre aléatoire.</span><span class="sxs-lookup"><span data-stu-id="f806d-292">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="f806d-293">À moins que l’utilisateur a également une licence Plan de l’appel de Microsoft, les appels vers n’importe quel nombre à l’exception des numéros qui correspondent à des modèles + XXX-XX-XX +1 425 ou +1 206 XXX XX XX dans l’exemple de configuration sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="f806d-293">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns + +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="f806d-294">Si l’utilisateur possède une licence de planifier l’appel, l’appel est acheminé automatiquement en fonction des stratégies de l’appel de Plan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f806d-294">If the user has a Calling Plan license, the call is automatically routed according to the policies of  the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="f806d-295">Le Plan d’appel de Microsoft s’applique automatiquement en tant que dernier à tous les utilisateurs dont la licence de l’appel de Plan de Microsoft et ne nécessite pas de configuration du routage des appels supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="f806d-295">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="f806d-296">Dans l’exemple illustré dans le diagramme suivant, un itinéraire de communications vocales est ajouté pour envoyer les appels vers tous les autres États-Unis et du Canada numéro (appels qui accèdent à un modèle de numéro appelé + 1 XXX XXX XX XX).</span><span class="sxs-lookup"><span data-stu-id="f806d-296">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![Stratégie de routage avec un itinéraire tiers de voix affiche](../../media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="f806d-298">Si l’utilisateur a les deux licences (système téléphonique de Microsoft et Microsoft appel de Plan) itinéraire automatique est utilisée pour tous les autres appels.</span><span class="sxs-lookup"><span data-stu-id="f806d-298">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="f806d-299">Si rien ne correspond au numéros modèles créés par l’administrateur en ligne itinéraires des communications vocales, l’itinéraire par le biais de l’appel de Plan de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f806d-299">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="f806d-300">Si l’utilisateur a Microsoft Phone System, l’appel est supprimé, car aucune règle correspondante n’est disponibles.</span><span class="sxs-lookup"><span data-stu-id="f806d-300">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="f806d-301">Valeur de la priorité d’itinéraire « Autres + 1 » n’a aucune importance dans ce cas, comme c’est le seul itinéraire qui correspond au modèle + 1 XXX XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="f806d-301">The Priority value for route “Other +1” doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="f806d-302">Si un utilisateur effectue un appel à + 1 324 567 89 89 et à la fois sbc5.contoso.biz et sbc6.contoso.biz ne sont pas disponibles, l’appel est abandonné.</span><span class="sxs-lookup"><span data-stu-id="f806d-302">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="f806d-303">Le tableau suivant récapitule la configuration à l’aide de trois itinéraires de communications vocales.</span><span class="sxs-lookup"><span data-stu-id="f806d-303">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="f806d-304">Dans cet exemple, tous les itinéraires de trois font partie de la même utilisation PSTN « Nous et Canada ».</span><span class="sxs-lookup"><span data-stu-id="f806d-304">In this example, all three routes are part of the same PSTN Usage “US and Canada”.</span></span>

|<span data-ttu-id="f806d-305">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="f806d-305">**PSTN usage**</span></span>|<span data-ttu-id="f806d-306">**Itinéraire de communications vocales**</span><span class="sxs-lookup"><span data-stu-id="f806d-306">**Voice route**</span></span>|<span data-ttu-id="f806d-307">**Schéma de numéro**</span><span class="sxs-lookup"><span data-stu-id="f806d-307">**Number pattern**</span></span>|<span data-ttu-id="f806d-308">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="f806d-308">**Priority**</span></span>|<span data-ttu-id="f806d-309">**SBC**</span><span class="sxs-lookup"><span data-stu-id="f806d-309">**SBC**</span></span>|<span data-ttu-id="f806d-310">**Description**</span><span class="sxs-lookup"><span data-stu-id="f806d-310">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f806d-311">Nous uniquement</span><span class="sxs-lookup"><span data-stu-id="f806d-311">US only</span></span>|<span data-ttu-id="f806d-312">« Redmond 1 »</span><span class="sxs-lookup"><span data-stu-id="f806d-312">“Redmond 1”</span></span>|<span data-ttu-id="f806d-313">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="f806d-313">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="f806d-314">1</span><span class="sxs-lookup"><span data-stu-id="f806d-314">1</span></span>|<span data-ttu-id="f806d-315">sbc1<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f806d-315">sbc1<span></span>.contoso.biz</span></span><br/><span data-ttu-id="f806d-316">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f806d-316">sbc2<span></span>.contoso.biz</span></span>|<span data-ttu-id="f806d-317">Itinéraire actif pour les numéros appelés XXX-XX-XX +1 425 ou XXX-XX-XX +1 206</span><span class="sxs-lookup"><span data-stu-id="f806d-317">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="f806d-318">Nous uniquement</span><span class="sxs-lookup"><span data-stu-id="f806d-318">US only</span></span>|<span data-ttu-id="f806d-319">« Redmond 2 »</span><span class="sxs-lookup"><span data-stu-id="f806d-319">“Redmond 2”</span></span>|<span data-ttu-id="f806d-320">^\\+ 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="f806d-320">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="f806d-321">2</span><span class="sxs-lookup"><span data-stu-id="f806d-321">2</span></span>|<span data-ttu-id="f806d-322">SBC3<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f806d-322">sbc3<span></span>.contoso.biz</span></span><br/><span data-ttu-id="f806d-323">sbc4<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f806d-323">sbc4<span></span>.contoso.biz</span></span>|<span data-ttu-id="f806d-324">Itinéraire alternatif pour les numéros appelés XXX-XX-XX +1 425 ou XXX-XX-XX +1 206</span><span class="sxs-lookup"><span data-stu-id="f806d-324">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="f806d-325">Nous uniquement</span><span class="sxs-lookup"><span data-stu-id="f806d-325">US only</span></span>|<span data-ttu-id="f806d-326">« Autres + 1 »</span><span class="sxs-lookup"><span data-stu-id="f806d-326">"Other +1”</span></span>|<span data-ttu-id="f806d-327">^\\+ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="f806d-327">^\\+1(\d{10})$</span></span>|<span data-ttu-id="f806d-328">3</span><span class="sxs-lookup"><span data-stu-id="f806d-328">3</span></span>|<span data-ttu-id="f806d-329">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f806d-329">sbc5<span></span>.contoso.biz</span></span><br/><span data-ttu-id="f806d-330">sbc6<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f806d-330">sbc6<span></span>.contoso.biz</span></span>|<span data-ttu-id="f806d-331">Routage de numéros appelés + 1 XXX XXX XX XX (sauf XXX-XX-XX +1 425 ou XXX-XX-XX +1 206)</span><span class="sxs-lookup"><span data-stu-id="f806d-331">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="f806d-332">Tous les itinéraires sont associés à l’utilisation PSTN « Nous et Canada » et l’utilisation RTC est associée à la stratégie de routage voix « US uniquement ».</span><span class="sxs-lookup"><span data-stu-id="f806d-332">All routes are associated with the PSTN Usage “US and Canada” and the PSTN Usage is associated with the Voice Routing Policy “US Only.”</span></span> <span data-ttu-id="f806d-333">Dans cet exemple, la stratégie de routage voix est attribuée à l’utilisateur Spencer Low.</span><span class="sxs-lookup"><span data-stu-id="f806d-333">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="f806d-334">Exemples d’itinéraires d’appels</span><span class="sxs-lookup"><span data-stu-id="f806d-334">Examples of call routes</span></span>

<span data-ttu-id="f806d-335">Dans l’exemple suivant, nous vous montrer comment configurer des itinéraires, des utilisations PSTN et des stratégies de routage et nous attribuer la stratégie à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f806d-335">In the following example,  we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="f806d-336">**Étape 1 :** Créer l’utilisation PSTN « États-Unis et au Canada. »</span><span class="sxs-lookup"><span data-stu-id="f806d-336">**Step 1:** Create the PSTN Usage “US and Canada.”</span></span>

<span data-ttu-id="f806d-337">Dans un Skype de session Business Remote PowerShell, tapez :</span><span class="sxs-lookup"><span data-stu-id="f806d-337">In a  Skype for Business Remote PowerShell session, type:</span></span>

```
Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="f806d-338">Vérifiez que l’utilisation a été créée en entrant :</span><span class="sxs-lookup"><span data-stu-id="f806d-338">Validate that the usage was created by entering:</span></span> 
```
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="f806d-339">Qui retourne une liste de noms qui peuvent être tronqués :</span><span class="sxs-lookup"><span data-stu-id="f806d-339">Which returns a list of names that may be truncated:</span></span>
```
  Identity  : Global
  Usage     : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="f806d-340">Dans l’exemple ci-dessous, vous pouvez voir le résultat de l’exécution de la commande PowerShell *`(Get-CSOnlinePSTNUsage).usage`* pour afficher les noms complets (non tronquées).</span><span class="sxs-lookup"><span data-stu-id="f806d-340">In the example below, you can see the result of the running the PowerShell command *`(Get-CSOnlinePSTNUsage).usage`* to display full names (not truncated).</span></span>    
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

<span data-ttu-id="f806d-341">**Étape 2 :** Dans une session dans Skype pour Business Online PowerShell, créez des trois itinéraires : Redmond 1, Redmond 2 et autres + 1, comme indiqué dans le tableau précédent.</span><span class="sxs-lookup"><span data-stu-id="f806d-341">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other+1, as detailed in the previous table.</span></span> 

<span data-ttu-id="f806d-342">Pour créer l’itinéraire « Redmond 1 », entrez :</span><span class="sxs-lookup"><span data-stu-id="f806d-342">To create the “Redmond 1” route, enter:</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^+1(425|206)
  (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
  ```

<span data-ttu-id="f806d-343">Qui retourne :</span><span class="sxs-lookup"><span data-stu-id="f806d-343">Which returns:</span></span>
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
<span data-ttu-id="f806d-344">Pour créer l’itinéraire Redmond 2, entrez :</span><span class="sxs-lookup"><span data-stu-id="f806d-344">To create the Redmond 2 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="f806d-345">Pour créer l’itinéraire de + 1 autres, entrez :</span><span class="sxs-lookup"><span data-stu-id="f806d-345">To create the Other +1 route, enter:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="f806d-346">Assurez-vous que votre expression régulière dans l’attribut NumberPattern est une expression valide.</span><span class="sxs-lookup"><span data-stu-id="f806d-346">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="f806d-347">Vous pouvez tester à l’aide de ce site Web :[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="f806d-347">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="f806d-348">Dans certains cas, il est nécessaire pour acheminer tous les appels vers la même SBC ; Utilisez - NumberPattern «. \* »</span><span class="sxs-lookup"><span data-stu-id="f806d-348">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern “.\*”</span></span>

- <span data-ttu-id="f806d-349">Tous les appels vers la même SBC</span><span class="sxs-lookup"><span data-stu-id="f806d-349">Route all calls to same SBC</span></span>

    ```
    Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" 
     -OnlinePstnGatewayList sbc1.contoso.biz
    ```

<span data-ttu-id="f806d-350">Valider que vous avez correctement configuré l’itinéraire en exécutant la `Get-CSOnlineVoiceRoute` commande Powershell à l’aide des options comme :</span><span class="sxs-lookup"><span data-stu-id="f806d-350">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` Powershell command using options as shown:</span></span> 

```
New-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="f806d-351">Qui doit retourner :</span><span class="sxs-lookup"><span data-stu-id="f806d-351">Which should return:</span></span>
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

<span data-ttu-id="f806d-352">Dans l’exemple, l’itinéraire « Autres + 1 » a été attribué automatiquement priorité.</span><span class="sxs-lookup"><span data-stu-id="f806d-352">In the example, the route “Other +1” was automatically assigned priority.</span></span> 

<span data-ttu-id="f806d-353">**Étape 3 :** Créer une stratégie de routage voix « Nous uniquement » et l’ajouter à la stratégie de l’utilisation PSTN « États-Unis et au Canada. »</span><span class="sxs-lookup"><span data-stu-id="f806d-353">**Step 3:** Create a Voice Routing Policy  “US Only” and add to the policy the PSTN Usage “US and Canada.”</span></span>

<span data-ttu-id="f806d-354">Dans une session dans Skype pour Business Online PowerShell, tapez :</span><span class="sxs-lookup"><span data-stu-id="f806d-354">In a PowerShell session in Skype for Business Online, type:</span></span>

```
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="f806d-355">Le résultat est indiqué dans cet exemple :</span><span class="sxs-lookup"><span data-stu-id="f806d-355">The result is shown in this example:</span></span>

<pre>
Identity        : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="f806d-356">**Étape 4 :** Accorder à l’utilisateur Spence Low une stratégie de routage voix à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f806d-356">**Step 4:** Grant to user Spence Low a voice routing policy by using PowerShell.</span></span>

- <span data-ttu-id="f806d-357">Dans une session dans Skype pour Business Online Powershell, tapez :</span><span class="sxs-lookup"><span data-stu-id="f806d-357">In a Powershell session in Skype for Business Online, type:</span></span>

    ```Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"```

- <span data-ttu-id="f806d-358">Valider l’affectation de stratégie en entrant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f806d-358">Validate the policy assignment by entering this command:</span></span>

```
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```
<span data-ttu-id="f806d-359">Qui retourne :</span><span class="sxs-lookup"><span data-stu-id="f806d-359">Which returns:</span></span>
<pre>
    OnlineVoiceRoutingPolicy
    ---------------------
    US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="f806d-360">Création d’une stratégie de routage des communications vocales avec plusieurs utilisations PSTN</span><span class="sxs-lookup"><span data-stu-id="f806d-360">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="f806d-361">La stratégie de routage des communications vocales créée précédemment n’autorise les appels vers les numéros de téléphone aux États-Unis et au Canada, sauf si la licence de l’appel de Plan de Microsoft est également affectée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f806d-361">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="f806d-362">Dans l’exemple qui suit, vous ne pouvez créer la stratégie de routage voix « Aucune restriction ».</span><span class="sxs-lookup"><span data-stu-id="f806d-362">In the example that follows, you can create the Voice Routing Policy “No Restrictions.”</span></span> <span data-ttu-id="f806d-363">La stratégie réutilise l’utilisation PSTN « Nous et Canada » créé dans l’exemple précédent, ainsi que la nouvelle utilisation PSTN « International ».</span><span class="sxs-lookup"><span data-stu-id="f806d-363">The policy reuses the PSTN Usage “US and Canada” created in the previous example, as well as the new PSTN Usage “International.”</span></span> 

<span data-ttu-id="f806d-364">Cela achemine tous les autres appels vers le sbc2 SBCs<span></span>. contoso.biz et sbc5<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="f806d-364">This routes all other calls to the SBCs sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz.</span></span> <span data-ttu-id="f806d-365">Les exemples figurent attribuer des États-Unis uniquement une stratégie à l’utilisateur « Spencer faible » et sans Restrictions à l’utilisateur « John Woods ».</span><span class="sxs-lookup"><span data-stu-id="f806d-365">The examples that are shown assign US Only policy to user “Spencer Low,” and No Restrictions to the user “John Woods.”</span></span>

<span data-ttu-id="f806d-366">Spencer faible – appels autorisés uniquement aux États-Unis et au Canada numéros.</span><span class="sxs-lookup"><span data-stu-id="f806d-366">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="f806d-367">Lors de l’appel à la plage de numéros de Redmond, le jeu spécifique de SBC doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="f806d-367">When calling to Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="f806d-368">Les numéros non US seront acheminés pas, sauf si la licence de planifier l’appel est attribuée à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f806d-368">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="f806d-369">John Woods – appels autorisés à n’importe quel nombre.</span><span class="sxs-lookup"><span data-stu-id="f806d-369">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="f806d-370">Lors de l’appel à la plage de numéros de Redmond, le jeu spécifique de SBC doit être utilisé.</span><span class="sxs-lookup"><span data-stu-id="f806d-370">When calling to Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="f806d-371">Les numéros non US seront acheminés via sbc2<span></span>. contoso.biz et sbc5<span></span>. contoso.biz.</span><span class="sxs-lookup"><span data-stu-id="f806d-371">Non-US numbers will be routed via sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz.</span></span>

![Indique la stratégie de routage voix attribuée à l’utilisateur Spencer Low](../../media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="f806d-373">Si l’utilisateur a les deux licences (système téléphonique de Microsoft et Microsoft appel de Plan) itinéraire automatique est utilisée pour tous les autres appels.</span><span class="sxs-lookup"><span data-stu-id="f806d-373">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="f806d-374">Si rien ne correspond au numéros modèles créés par l’administrateur en ligne itinéraires des communications vocales, l’itinéraire par le biais de l’appel de Plan de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f806d-374">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="f806d-375">Si l’utilisateur a Microsoft Phone System, l’appel est supprimé, car aucune règle correspondante n’est disponibles.</span><span class="sxs-lookup"><span data-stu-id="f806d-375">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![Indique la stratégie de routage voix attribuée à l’utilisateur John Woods](../../media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="f806d-377">Le tableau suivant récapitule les itinéraires de communications vocales et de dénomination de l’utilisation de routage stratégie « No Restrictions ».</span><span class="sxs-lookup"><span data-stu-id="f806d-377">The following table  summarizes routing policy “No Restrictions” usage designations and voice routes.</span></span> 

|<span data-ttu-id="f806d-378">**Utilisation PSTN**</span><span class="sxs-lookup"><span data-stu-id="f806d-378">**PSTN usage**</span></span>|<span data-ttu-id="f806d-379">**Itinéraire de communications vocales**</span><span class="sxs-lookup"><span data-stu-id="f806d-379">**Voice route**</span></span>|<span data-ttu-id="f806d-380">**Schéma de numéro**</span><span class="sxs-lookup"><span data-stu-id="f806d-380">**Number pattern**</span></span>|<span data-ttu-id="f806d-381">**Priorité**</span><span class="sxs-lookup"><span data-stu-id="f806d-381">**Priority**</span></span>|<span data-ttu-id="f806d-382">**SBC**</span><span class="sxs-lookup"><span data-stu-id="f806d-382">**SBC**</span></span>|<span data-ttu-id="f806d-383">**Description**</span><span class="sxs-lookup"><span data-stu-id="f806d-383">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f806d-384">Nous uniquement</span><span class="sxs-lookup"><span data-stu-id="f806d-384">US Only</span></span>|<span data-ttu-id="f806d-385">« Redmond 1 »</span><span class="sxs-lookup"><span data-stu-id="f806d-385">“Redmond 1”</span></span>|<span data-ttu-id="f806d-386">^ + 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="f806d-386">^+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="f806d-387">1</span><span class="sxs-lookup"><span data-stu-id="f806d-387">1</span></span>|<span data-ttu-id="f806d-388">sbc1<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f806d-388">sbc1<span></span>.contoso.biz</span></span><br/><span data-ttu-id="f806d-389">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f806d-389">sbc2<span></span>.contoso.biz</span></span>|<span data-ttu-id="f806d-390">Gamme active pour les numéros appelé XXX-XX-XX +1 425 ou XXX-XX-XX +1 206</span><span class="sxs-lookup"><span data-stu-id="f806d-390">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="f806d-391">Nous uniquement</span><span class="sxs-lookup"><span data-stu-id="f806d-391">US Only</span></span>|<span data-ttu-id="f806d-392">« Redmond 2 »</span><span class="sxs-lookup"><span data-stu-id="f806d-392">“Redmond 2”</span></span>|<span data-ttu-id="f806d-393">^ + 1 (425\|206)(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="f806d-393">^+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="f806d-394">2</span><span class="sxs-lookup"><span data-stu-id="f806d-394">2</span></span>|<span data-ttu-id="f806d-395">SBC3<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f806d-395">sbc3<span></span>.contoso.biz</span></span><br/><span data-ttu-id="f806d-396">sbc4<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f806d-396">sbc4<span></span>.contoso.biz</span></span>|<span data-ttu-id="f806d-397">Itinéraire alternatif pour les numéros appelé XXX-XX-XX +1 425 ou XXX-XX-XX +1 206</span><span class="sxs-lookup"><span data-stu-id="f806d-397">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="f806d-398">Nous uniquement</span><span class="sxs-lookup"><span data-stu-id="f806d-398">US Only</span></span>|<span data-ttu-id="f806d-399">« Autres + 1 »</span><span class="sxs-lookup"><span data-stu-id="f806d-399">“Other +1”</span></span>|<span data-ttu-id="f806d-400">^ + 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="f806d-400">^+1(\d{10})$</span></span>|<span data-ttu-id="f806d-401">3</span><span class="sxs-lookup"><span data-stu-id="f806d-401">3</span></span>|<span data-ttu-id="f806d-402">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f806d-402">sbc5<span></span>.contoso.biz</span></span><br/><span data-ttu-id="f806d-403">sbc6<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f806d-403">sbc6<span></span>.contoso.biz</span></span>|<span data-ttu-id="f806d-404">Itinéraire pour appelé numéros + 1 XXX XXX XX XX (sauf XXX-XX-XX +1 425 ou XXX-XX-XX +1 206)</span><span class="sxs-lookup"><span data-stu-id="f806d-404">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="f806d-405">International</span><span class="sxs-lookup"><span data-stu-id="f806d-405">International</span></span>|<span data-ttu-id="f806d-406">International</span><span class="sxs-lookup"><span data-stu-id="f806d-406">International</span></span>|<span data-ttu-id="f806d-407">\d+</span><span class="sxs-lookup"><span data-stu-id="f806d-407">\d+</span></span>|<span data-ttu-id="f806d-408">4</span><span class="sxs-lookup"><span data-stu-id="f806d-408">4</span></span>|<span data-ttu-id="f806d-409">sbc2<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f806d-409">sbc2<span></span>.contoso.biz</span></span><br/><span data-ttu-id="f806d-410">sbc5<span></span>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="f806d-410">sbc5<span></span>.contoso.biz</span></span>|<span data-ttu-id="f806d-411">Itinéraire pour n’importe quel modèle de numéro</span><span class="sxs-lookup"><span data-stu-id="f806d-411">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="f806d-412">L’ordre des utilisations PSTN dans les stratégies de routage voix est essentielle.</span><span class="sxs-lookup"><span data-stu-id="f806d-412">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="f806d-413">Les utilisations sont appliquées dans l’ordre, et si une correspondance est trouvée dans la première utilisation, puis autres utilisations ne sont jamais évaluées.</span><span class="sxs-lookup"><span data-stu-id="f806d-413">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="f806d-414">L’utilisation PSTN « International » doit être placée après l’utilisation PSTN « Nous uniquement. »</span><span class="sxs-lookup"><span data-stu-id="f806d-414">The PSTN Usage “International” must be placed after the PSTN Usage “US Only.”</span></span> <span data-ttu-id="f806d-415">Pour modifier l’ordre des utilisations PSTN, exécutez le `Set-CSOnlineRouteRoutingPolicy` commande.</span><span class="sxs-lookup"><span data-stu-id="f806d-415">To change the order of the PSTN Usages, please run the `Set-CSOnlineRouteRoutingPolicy` command.</span></span> <br/><span data-ttu-id="f806d-416">Par exemple, pour modifier l’ordre de « Nous et Canada » deuxième prénom et « International » à l’ordre inverse exécutez :</span><span class="sxs-lookup"><span data-stu-id="f806d-416">For example, to change the order from “US and Canada” first and “International” second to the reverse order run:</span></span><br/>   `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="f806d-417">La priorité de « Autres + 1 » et « International » des itinéraires sont affectés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="f806d-417">The priority for  “Other +1” and “International” Voice routes are assigned automatically.</span></span> <span data-ttu-id="f806d-418">Ils n’a pas d’importance tant qu’ils ont des priorités inférieures à « Redmond 1 » et « Redmond 2 ».</span><span class="sxs-lookup"><span data-stu-id="f806d-418">They don’t matter as long as they have lower priorities than “Redmond 1” and “Redmond 2.”</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="f806d-419">Exemple de la stratégie de routage voix pour l’utilisateur John Woods</span><span class="sxs-lookup"><span data-stu-id="f806d-419">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="f806d-420">Stratégie de routage « No Restrictions, » vocale itinéraire « International », vocale à la procédure de création d’utilisation PSTN « International », et puis en l’affectant à l’utilisateur « John Woods » sont les suivantes.</span><span class="sxs-lookup"><span data-stu-id="f806d-420">The steps to create PSTN Usage “International”, voice route “International,” Voice Routing Policy “No Restrictions,” and then assigning it to the user “John Woods” are as follows.</span></span>


1.  <span data-ttu-id="f806d-421">Tout d’abord, créez l’utilisation PSTN « International ».</span><span class="sxs-lookup"><span data-stu-id="f806d-421">First, create the PSTN Usage “International."</span></span> <span data-ttu-id="f806d-422">Dans une session PowerShell distante dans Skype pour Business Online, entrez :</span><span class="sxs-lookup"><span data-stu-id="f806d-422">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

  ```
  Set-CsOnlinePstnUsage  -Identity Global -Usage @{Add="International"}
  ```

2.  <span data-ttu-id="f806d-423">Ensuite, créez l’itinéraire des communications vocales « International ».</span><span class="sxs-lookup"><span data-stu-id="f806d-423">Next, create the new voice route “International.”</span></span>

  ```
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
  ```
  <span data-ttu-id="f806d-424">Qui retourne :</span><span class="sxs-lookup"><span data-stu-id="f806d-424">Which returns:</span></span>

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
3.  <span data-ttu-id="f806d-425">Ensuite, ne créez une stratégie de routage voix « Aucune restriction ».</span><span class="sxs-lookup"><span data-stu-id="f806d-425">Next, create a Voice Routing Policy “No Restrictions”.</span></span> <span data-ttu-id="f806d-426">L’utilisation PSTN « Redmond 1 » et « Redmond » sont réutilisés dans cette stratégie de routage voix pour conserver les appels vers le numéro « +1 425 XX XXX XX » et « +1 206 XX XXX XX » comme des appels locaux ou dans les locaux de traitement particulier.</span><span class="sxs-lookup"><span data-stu-id="f806d-426">The PSTN Usage “Redmond 1” and “Redmond “ are reused in this voice routing policy to preserve special handling for calls to number “+1 425 XXX XX XX” and “+1 206 XXX XX XX” as local or on-premise calls.</span></span>

```
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”
```

    Take note of the order of PSTN Usages:

    a. If a call made to number “+1425 XXX XX XX” with the usages configured as in the following example, the call follows the route set in “US and Canada” usage and the special routing logic is applied. That is, the call is routed using  sbc1<span></span>.contoso.biz and sbc2<span></span>.contoso.biz first, and then  sbc3<span></span>.contoso.biz and sbc4<span></span>.contoso.biz as the backup routes. 

    b.  If “International” PSTN usage is before “US and Canada,” calls to + 1425 XXX XX XX are routed to sbc2<span></span>.contoso.biz and sbc5<span></span>.contoso.biz as part of the routing logic. Enter the command:

    ```New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", ”International”```

   <span data-ttu-id="f806d-427">Qui retourne</span><span class="sxs-lookup"><span data-stu-id="f806d-427">Which returns</span></span>

  <pre>
   Identity     : International 
   OnlinePstnUsages     : {US and Canada, International}     
   Description      :  
   RouteType        : BYOT
  </pre>

4.  <span data-ttu-id="f806d-428">Attribuer la stratégie de routage voix à l’utilisateur « John Woods » à l’aide de la commande suivante.</span><span class="sxs-lookup"><span data-stu-id="f806d-428">Assign the voice routing policy to the user “John Woods” using the following command.</span></span>

  ```
  Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
  ```

  <span data-ttu-id="f806d-429">Vérifiez l’affectation à l’aide de la commande :</span><span class="sxs-lookup"><span data-stu-id="f806d-429">Then verify the assignment using the command:</span></span>   

  ```
  Get CsOnlineUser “John Woods” | Select OnlineVoiceRoutingPolicy
  ```
  <span data-ttu-id="f806d-430">Qui retourne :</span><span class="sxs-lookup"><span data-stu-id="f806d-430">Which returns:</span></span>

<pre>
    OnlineVoiceRoutingPolicy
    ------------------------
    No Restrictions
</pre>

<span data-ttu-id="f806d-431">Le résultat est que la stratégie de voix appliquée aux appels de John Woods sont non restreint et doit suivre la logique de routage des appels disponible pour les États-Unis, au Canada et International appel.</span><span class="sxs-lookup"><span data-stu-id="f806d-431">The result is that the voice policy applied to John Woods’ calls are unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="enable-calling-for-microsoft-teams"></a><span data-ttu-id="f806d-432">Activer les appels pour les équipes Microsoft</span><span class="sxs-lookup"><span data-stu-id="f806d-432">Enable Calling for Microsoft Teams</span></span>

<span data-ttu-id="f806d-433">Avant d’un utilisateur d’afficher l’onglet appels dans Microsoft Teams, vous devez activer l’appel privé pour le client dans Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f806d-433">Before a user can see the Calls tab in Microsoft Teams, you need to enable private calling for the tenant in Microsoft Teams.</span></span> <span data-ttu-id="f806d-434">Pour ce faire :</span><span class="sxs-lookup"><span data-stu-id="f806d-434">To do this:</span></span>

1.  <span data-ttu-id="f806d-435">Connectez-vous en tant qu’administrateur client sur le centre d’administration d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="f806d-435">Sign in as tenant administrator on the Office 365 Admin center.</span></span>
2.  <span data-ttu-id="f806d-436">Accédez à **paramètres et Services et des compléments** et sélectionnez les **Équipes Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="f806d-436">Go to **Settings and Services and add-ins** and select **Microsoft Teams**.</span></span> 
3.  <span data-ttu-id="f806d-437">Développez des **appels et les réunions** et vérifiez que **Autoriser privée appelant** se trouve **sur**.</span><span class="sxs-lookup"><span data-stu-id="f806d-437">Expand **Calls and meetings** and verify that **Allow private calling** is **On**.</span></span>

    ![Capture d’écran montrant autoriser appel privé est activé.](../../media/ConfigDirectRouting-CallsandMeetingsDialog.png)

## <a name="set-microsoft-teams-as-the-preferred-calling-client-for-the-users"></a><span data-ttu-id="f806d-439">Définissez Teams Microsoft en tant que client appelant par défaut pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f806d-439">Set Microsoft Teams as the preferred calling client for the users</span></span>

<span data-ttu-id="f806d-440">Routage direct achemine uniquement les appels aux Teams Microsoft, vous devez vous assurer que Microsoft Teams est le client appelant par défaut pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f806d-440">Direct Routing will route calls only to Microsoft Teams, so you need to make sure that Microsoft Teams is the preferred calling client for the users.</span></span> <span data-ttu-id="f806d-441">Ceci est contrôlé par la TeamsCallingPolicy et le TeamsInteropPolicy.</span><span class="sxs-lookup"><span data-stu-id="f806d-441">This is controlled by the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span> 

1. <span data-ttu-id="f806d-442">Tout d’abord, utilisez l’applet de commande suivante dans une session PowerShell distante dans le Skype pour le centre d’administration Business en ligne pour afficher les stratégies de l’utilisateur a été affecté.</span><span class="sxs-lookup"><span data-stu-id="f806d-442">First, use the following cmdlet in a remote PowerShell session in the Skype for Business Online admin center to see which policies the user has been assigned.</span></span> 

  ```
  Get-CsOnlineUser -identity <User Name> | fl *teams*
  ```
 
2. <span data-ttu-id="f806d-443">Ensuite, passez en revue les instances de stratégie différent.</span><span class="sxs-lookup"><span data-stu-id="f806d-443">Next, review the different policy instances.</span></span> 

  ```
  Get-CsTeamsCallingPolicy
  ``` 
<span data-ttu-id="f806d-444"> et </span><span class="sxs-lookup"><span data-stu-id="f806d-444">and</span></span>

  ```
  Get-CsTeamsInteropPolicy
  ``` 

<span data-ttu-id="f806d-445">Avant que les utilisateurs de Microsoft Teams peuvent utiliser le service, des étapes supplémentaires, que vous devrez peut-être suivre pour appliquer la stratégie d’appel et autoriser les appels.</span><span class="sxs-lookup"><span data-stu-id="f806d-445">Before Microsoft Teams users can use the service, there are additional steps you may need to take to apply the calling policy and allow calls.</span></span>

### <a name="teams-calling-policy"></a><span data-ttu-id="f806d-446">Appel de stratégie des équipes</span><span class="sxs-lookup"><span data-stu-id="f806d-446">Teams Calling Policy</span></span>

<span data-ttu-id="f806d-447">Vous devez vous assurer que l’utilisateur dispose d’un TeamsCallingPolicy avec AllowCalling = True.</span><span class="sxs-lookup"><span data-stu-id="f806d-447">You need to make sure that the user has a TeamsCallingPolicy with AllowCalling = True.</span></span> <span data-ttu-id="f806d-448">Cette stratégie peut être la stratégie globale de votre client ou une stratégie spécifique accordées à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f806d-448">This policy can either be the Global policy in your tenant or a specific policy granted to the user.</span></span> <span data-ttu-id="f806d-449">Si vous devez accorder à un utilisateur une stratégie spécifique, vous pouvez utiliser l’applet de commande :</span><span class="sxs-lookup"><span data-stu-id="f806d-449">If you need to grant a user a specific policy, you can use the cmdlet:</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName <policy> -Identity <User Name>
```

### <a name="teams-interop-policy"></a><span data-ttu-id="f806d-450">Stratégie d’interopérabilité de base équipes</span><span class="sxs-lookup"><span data-stu-id="f806d-450">Teams Interop Policy</span></span>

<span data-ttu-id="f806d-451">Assurez-vous que l’utilisateur a la valeur Microsoft Teams du client par défaut.</span><span class="sxs-lookup"><span data-stu-id="f806d-451">Make sure that the user has the preferred calling client to set to Microsoft Teams.</span></span> <span data-ttu-id="f806d-452">Il est possible de deux manières :</span><span class="sxs-lookup"><span data-stu-id="f806d-452">This can be done in two ways:</span></span>

- <span data-ttu-id="f806d-453">L’utilisateur définit le client appelant par défaut dans le client Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f806d-453">The user sets the preferred calling client in the Microsoft Teams client.</span></span>
- <span data-ttu-id="f806d-454">L’utilisateur a reçu une stratégie qui définit le client appelant par défaut.</span><span class="sxs-lookup"><span data-stu-id="f806d-454">The user has been assigned a policy that sets the preferred calling client.</span></span>

<span data-ttu-id="f806d-455">Pour affecter une stratégie qui définit Teams Microsoft en tant que client appelant par défaut, assurez-vous que l’utilisateur bénéficie d’une stratégie avec CallingDefaultClient = équipes.</span><span class="sxs-lookup"><span data-stu-id="f806d-455">To assign a policy that sets Microsoft Teams as the preferred calling client, make sure that the user is granted a policy with CallingDefaultClient = Teams.</span></span> <span data-ttu-id="f806d-456">Vous trouverez ci-dessous un exemple de commande :</span><span class="sxs-lookup"><span data-stu-id="f806d-456">An example cmdlet is shown below:</span></span>

```
Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity “<User Name>”
```

## <a name="see-also"></a><span data-ttu-id="f806d-457">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f806d-457">See also</span></span>

[<span data-ttu-id="f806d-458">Planifier le routage Direct</span><span class="sxs-lookup"><span data-stu-id="f806d-458">Plan Direct Routing</span></span>](plan-direct-routing.md)
