---
title: Déployer le contournement de média dans Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Lisez cette rubrique pour en savoir plus sur les étapes de déploiement du contournement de média avec La version 2.0 de Cloud Connector et versions ultérieures.
ms.openlocfilehash: c9dc79a3079fd27e8901d31abf1a27310d18ed28
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119363"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="a4572-103">Déployer le contournement de média dans Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="a4572-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="a4572-104">Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="a4572-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="a4572-105">Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams à l’aide du [routage direct.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="a4572-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="a4572-106">Lisez cette rubrique pour en savoir plus sur les étapes de déploiement de la déviation du média avec La version 2.0 de Cloud Connector et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="a4572-106">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="a4572-107">La déviation du trafic multimédia permet à un client d’envoyer du trafic multimédia directement au saut suivant du réseau téléphonique commuté (PSTN) (passerelle ou contrôleur SBC) et d’éliminer le composant Cloud Connector Edition du chemin d’accès du média.</span><span class="sxs-lookup"><span data-stu-id="a4572-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="a4572-108">Voir aussi [Planifier le contournement de média dans Cloud Connector Edition.](plan-for-media-bypass-in-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="a4572-108">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="a4572-109">Activer le contournement de média</span><span class="sxs-lookup"><span data-stu-id="a4572-109">Enable media bypass</span></span>

<span data-ttu-id="a4572-110">Pour activer la déviation du trafic multimédia, vous devez configurer le nom DNS du service web de déviation du trafic multimédia et activer la déviation du trafic multimédia dans la configuration du client.</span><span class="sxs-lookup"><span data-stu-id="a4572-110">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="a4572-111">Le service web de déviation du trafic multimédia se déploie automatiquement sur chaque serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="a4572-111">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="a4572-112">Un administrateur client doit choisir un nom pour un service vocal hybride (site), et ce nom doit être issu d’un domaine SIP enregistré pour la voix hybride.</span><span class="sxs-lookup"><span data-stu-id="a4572-112">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="a4572-113">Le nom du service doit être le même pour toutes les appliances Cloud Connector et tous les sites PSTN, quel que soit l’emplacement du client.</span><span class="sxs-lookup"><span data-stu-id="a4572-113">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="a4572-114">Le service web doit uniquement être disponible en interne sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="a4572-114">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="a4572-115">Un administrateur client doit configurer un enregistrement DNS A dans active Directory de production interne.</span><span class="sxs-lookup"><span data-stu-id="a4572-115">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="a4572-116">Si vous avez un environnement multis site complexe, voir l’exemple dans l’exemple : enregistrements DNS de site web de déviation du trafic multimédia dans des [environnements multisesses complexes.](deploy-media-bypass-in-cloud-connector.md#Example)</span><span class="sxs-lookup"><span data-stu-id="a4572-116">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="a4572-117">L’enregistrement DNS doit uniquement être résolu pour les clients réseau internes ; il ne doit pas être résolu pour les clients réseau externes.</span><span class="sxs-lookup"><span data-stu-id="a4572-117">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="a4572-118">Après avoir configuré le DNS, connectez-vous à Skype Entreprise Online à l’aide de PowerShell à distance avec les informations d’identification de l’administrateur Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="a4572-118">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="a4572-119">Pour plus d’informations, voir [Configurer votre ordinateur pour Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span><span class="sxs-lookup"><span data-stu-id="a4572-119">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="a4572-120">Dans la session PowerShell, entrez les commandes suivantes pour activer le contournement de média :</span><span class="sxs-lookup"><span data-stu-id="a4572-120">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="a4572-121">L’activation du contournement de média est un processus en deux étapes.</span><span class="sxs-lookup"><span data-stu-id="a4572-121">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="a4572-122">LNew-CsNetworkMedia cmdlet n’enregistre pas immédiatement la nouvelle configuration . Il crée uniquement les paramètres en mémoire.</span><span class="sxs-lookup"><span data-stu-id="a4572-122">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="a4572-123">L’objet créé par cette cmdlet doit être enregistré dans une variable, puis affecté à la propriété MediaBypassSettings de la configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="a4572-123">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="a4572-124">Pour plus d’informations, voir l’exemple : enregistrements DNS de site web de déviation du trafic multimédia dans des [environnements multisesses complexes.](deploy-media-bypass-in-cloud-connector.md#Example)</span><span class="sxs-lookup"><span data-stu-id="a4572-124">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="a4572-125">La réplication entre les composants locaux et en ligne peut prendre jusqu’à 24 heures. Microsoft vous recommande donc d’exécuter les commandes nécessaires avant d’activer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a4572-125">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="a4572-126">Confirmer les paramètres de déviation du média</span><span class="sxs-lookup"><span data-stu-id="a4572-126">Confirm media bypass settings</span></span>

<span data-ttu-id="a4572-127">Vous pouvez vérifier les paramètres de déviation du média comme suit.</span><span class="sxs-lookup"><span data-stu-id="a4572-127">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="a4572-128">Pour vérifier la réplication en ligne dans votre pool de locataires, exécutez la commande suivante dans PowerShell à distance :</span><span class="sxs-lookup"><span data-stu-id="a4572-128">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="a4572-129">Pour vérifier la réplication sur site, connectez-vous aux serveurs de médiation Cloud Connector, exécutez la commande suivante dans PowerShell et vérifiez que Enabled=True et AlwaysBypass=True</span><span class="sxs-lookup"><span data-stu-id="a4572-129">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="a4572-130">Pour vérifier les paramètres du client, connectez-vous au client Skype Entreprise, confirmez que le client a reçu l’URL du service comme suit :</span><span class="sxs-lookup"><span data-stu-id="a4572-130">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="a4572-131">Ouvrez %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span><span class="sxs-lookup"><span data-stu-id="a4572-131">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="a4572-132">Recherchez hybridconfigserviceinternalurl et confirmez que l’URL correspond à celle que vous avez définie.</span><span class="sxs-lookup"><span data-stu-id="a4572-132">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="a4572-133">Modifier les paramètres de déviation du média</span><span class="sxs-lookup"><span data-stu-id="a4572-133">Change media bypass parameters</span></span>

<span data-ttu-id="a4572-134">Les administrateurs clients peuvent modifier le nom DNS du service web en exécutant l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="a4572-134">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="a4572-135">Les clients doivent se signer et se connectent pour obtenir le nouveau nom de service et reconnaître la modification.</span><span class="sxs-lookup"><span data-stu-id="a4572-135">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="a4572-136">Désactiver temporairement le contournement de média</span><span class="sxs-lookup"><span data-stu-id="a4572-136">Temporarily disable media bypass</span></span>

<span data-ttu-id="a4572-137">Ce scénario peut être utile pour la résolution des problèmes ou la maintenance.</span><span class="sxs-lookup"><span data-stu-id="a4572-137">This scenario might be useful for troubleshooting or maintenance.</span></span> <span data-ttu-id="a4572-138">Pour désactiver le service, exécutez les cmdlets suivantes :</span><span class="sxs-lookup"><span data-stu-id="a4572-138">To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="a4572-139">Après avoir apporté la modification, la réplication des modifications sur tous les connecteurs cloud peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="a4572-139">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="a4572-140">Pour vérifier l’état de la réplication, exécutez la cmdlet suivante dans PowerShell sur les serveurs de médiation Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="a4572-140">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="a4572-141">Une fois les modifications répliquées, le service web sur le serveur de médiation commence à rejeter les demandes des clients pour le service de déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="a4572-141">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="a4572-142">Désactiver définitivement le contournement de média</span><span class="sxs-lookup"><span data-stu-id="a4572-142">Disable media bypass permanently</span></span>

<span data-ttu-id="a4572-143">Pour désactiver définitivement le contournement de média, un administrateur client doit exécuter les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a4572-143">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="a4572-144">Un administrateur devra également supprimer les adresses web pour la déviation du trafic multimédia des serveurs DNS internes.</span><span class="sxs-lookup"><span data-stu-id="a4572-144">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="a4572-145">Après avoir apporté la modification, la réplication des modifications sur toutes les appliances Cloud Connector peut prendre un certain temps.</span><span class="sxs-lookup"><span data-stu-id="a4572-145">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="a4572-146">Exemple : enregistrements DNS de site web de déviation du trafic multimédia dans des environnements multis sites complexes</span><span class="sxs-lookup"><span data-stu-id="a4572-146">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="a4572-147"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="a4572-147"><a name="Example"> </a></span></span>

<span data-ttu-id="a4572-148">Les clients recevront l’adresse web du service web de déviation du trafic multimédia à partir d’un serveur DNS interne.</span><span class="sxs-lookup"><span data-stu-id="a4572-148">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="a4572-149">Le nom du service web sera le même sur l’ensemble des appliances Cloud Connector et des sites PSTN Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a4572-149">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="a4572-150">Dans un environnement multisession complexe, nous vous recommandons d’utiliser la stratégie DNS Windows 2016 pour la gestion du trafic basé sur Geo-Location, afin que les clients soient redirigés vers le service web local pour leur réseau.</span><span class="sxs-lookup"><span data-stu-id="a4572-150">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="a4572-151">Pour plus d’informations sur les stratégies DNS Windows 2016, voir Utiliser la stratégie [DNS](/windows-server/networking/dns/deploy/primary-geo-location)pour Geo-Location gestion du trafic basée sur les serveurs principaux.</span><span class="sxs-lookup"><span data-stu-id="a4572-151">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="a4572-152">Voici un exemple de configuration pour une entreprise avec plusieurs sites utilisant la stratégie DNS Windows 2016 pour Geo-Location de trafic basé sur la gestion du trafic.</span><span class="sxs-lookup"><span data-stu-id="a4572-152">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="a4572-153">Le nom du service de contournement est « hybridvoice.adatum.biz ».</span><span class="sxs-lookup"><span data-stu-id="a4572-153">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="a4572-154">Le site à Amsterdam dispose de quatre appliances Cloud Connector déployées avec les adresses IP du serveur de médiation suivantes :</span><span class="sxs-lookup"><span data-stu-id="a4572-154">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="a4572-155">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="a4572-155">192.168.1.45</span></span>
    
- <span data-ttu-id="a4572-156">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="a4572-156">192.168.1.46</span></span>
    
- <span data-ttu-id="a4572-157">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="a4572-157">192.168.1.47</span></span>
    
- <span data-ttu-id="a4572-158">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="a4572-158">192.168.1.48</span></span>
    
<span data-ttu-id="a4572-159">Le site de Seattle dispose de trois appliances Cloud Connector déployées avec les adresses IP du serveur de médiation suivantes :</span><span class="sxs-lookup"><span data-stu-id="a4572-159">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="a4572-160">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="a4572-160">10.10.1.8</span></span>
    
- <span data-ttu-id="a4572-161">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="a4572-161">10.10.1.9</span></span>
    
- <span data-ttu-id="a4572-162">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="a4572-162">10.10.1.10</span></span>
    
<span data-ttu-id="a4572-163">À lGeo-Location de trafic basé sur la gestion du trafic, les serveurs DNS sont configurés comme suit :</span><span class="sxs-lookup"><span data-stu-id="a4572-163">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="a4572-164">Créez des sous-réseaux clients DNS pour les sous-réseaux Amsterdam et Seattle.</span><span class="sxs-lookup"><span data-stu-id="a4572-164">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="a4572-165">Créez des étendues de zone DNS adatum.biz pour Amsterdam et Seattle.</span><span class="sxs-lookup"><span data-stu-id="a4572-165">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="a4572-166">Créez des enregistrements DNS dans chaque étendue de zone DNS.</span><span class="sxs-lookup"><span data-stu-id="a4572-166">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="a4572-167">Amsterdam</span><span class="sxs-lookup"><span data-stu-id="a4572-167">Amsterdam</span></span>
    
   - <span data-ttu-id="a4572-168">Tapez A ;</span><span class="sxs-lookup"><span data-stu-id="a4572-168">Type A;</span></span>
    
   - <span data-ttu-id="a4572-169">Name : hybridvoice dans la zone adatum.biz DNS</span><span class="sxs-lookup"><span data-stu-id="a4572-169">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="a4572-170">Cible : 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="a4572-170">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="a4572-171">Créer des enregistrements supplémentaires pour des serveurs de médiation supplémentaires</span><span class="sxs-lookup"><span data-stu-id="a4572-171">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="a4572-172">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="a4572-172">192.168.1.46</span></span>
    
   - <span data-ttu-id="a4572-173">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="a4572-173">192.168.1.47</span></span>
    
   - <span data-ttu-id="a4572-174">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="a4572-174">192.168.1.48</span></span>
    
     <span data-ttu-id="a4572-175">Seattle</span><span class="sxs-lookup"><span data-stu-id="a4572-175">Seattle</span></span>
    
   - <span data-ttu-id="a4572-176">Type A</span><span class="sxs-lookup"><span data-stu-id="a4572-176">Type A</span></span>
    
   - <span data-ttu-id="a4572-177">Name : hybridvoice dans adatum.biz zone DNS</span><span class="sxs-lookup"><span data-stu-id="a4572-177">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="a4572-178">Cible : 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="a4572-178">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="a4572-179">Créer des enregistrements supplémentaires pour des serveurs de médiation supplémentaires</span><span class="sxs-lookup"><span data-stu-id="a4572-179">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="a4572-180">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="a4572-180">10.10.1.9</span></span>
    
   - <span data-ttu-id="a4572-181">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="a4572-181">10.10.1.10</span></span>
    
4. <span data-ttu-id="a4572-182">Créez la stratégie DNS qui connecte les sous-réseaux clients aux étendues de zone appropriées pour garantir la résolution DNS souhaitée.</span><span class="sxs-lookup"><span data-stu-id="a4572-182">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="a4572-183">À ce stade, les clients qui font des requêtes DNS à partir du sous-réseau d’Amsterdam pour hybridvoice.adatum.biz retourneront le 192.168.1.45, 192.168.1.46, 192.168.1.47 et 192.168.1.48, tandis que les clients qui font le même formulaire de requête Seattle retournent 10.10.1.8, 10.10.1.9 et 10.10.1.10.</span><span class="sxs-lookup"><span data-stu-id="a4572-183">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="a4572-184">Si l’appliance CCE ne semble pas obtenir les paramètres mis à jour, vérifiez si l’appliance est en mesure de contacter le client via PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="a4572-184">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="a4572-185">Vous pouvez utiliser Remote PowerShell pour vérifier l’état de l’appliance avec Get-CsHybridPSTNAppliance ou utiliser PowerShell sur l’hôte CCE pour vérifier l’état avec Get-CcApplianceStatus.</span><span class="sxs-lookup"><span data-stu-id="a4572-185">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="a4572-186">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a4572-186">See also</span></span>
<span data-ttu-id="a4572-187"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="a4572-187"><a name="Example"> </a></span></span>

[<span data-ttu-id="a4572-188">Planifier le contournement de média dans Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="a4572-188">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)