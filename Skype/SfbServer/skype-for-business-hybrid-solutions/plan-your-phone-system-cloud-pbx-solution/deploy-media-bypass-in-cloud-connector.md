---
title: Déployer le contournement de média dans le nuage connecteur Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Lisez cette rubrique pour en savoir plus sur les étapes nécessaires pour déployer le contournement de média avec le nuage connecteur Edition version 2.0 et versions ultérieure.
ms.openlocfilehash: f4ea5449e7a324ae206241af25d12ecabf9c5259
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878048"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="c3bd7-103">Déployer le contournement de média dans le nuage connecteur Edition</span><span class="sxs-lookup"><span data-stu-id="c3bd7-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="c3bd7-104">Lisez cette rubrique pour en savoir plus sur les étapes nécessaires pour déployer le contournement de média avec le nuage connecteur Edition version 2.0 et versions ultérieure.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-104">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="c3bd7-105">Le contournement de média permet au client d’envoyer des données multimédia directement au saut suivant Public réseau de téléphonique commuté (RTC) — une passerelle ou un contrôleur de Session en périphérie (SBC) — et d’éliminer le composant nuage connecteur Edition à partir du chemin d’accès des médias.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-105">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="c3bd7-106">Voir aussi [Plan pour le média de contournement dans le nuage connecteur Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="c3bd7-106">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="c3bd7-107">Activer la déviation du trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="c3bd7-107">Enable media bypass</span></span>

<span data-ttu-id="c3bd7-108">Pour activer la déviation du trafic multimédia, vous devez configurer le nom DNS du service web de déviation du trafic multimédia et activer la déviation du trafic multimédia dans la configuration de client.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-108">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="c3bd7-109">Le service web de déviation du trafic multimédia se déploie automatiquement sur chaque serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-109">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="c3bd7-110">Un administrateur de client doit choisir un nom pour un service de voix hybride (site) et ce nom doit provenir d'un domaine SIP inscrit pour la voix hybride.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-110">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="c3bd7-111">Le nom du service doit être la même sur tous les appareils de nuage connecteur et tous les sites PSTN quel que soit l’emplacement du client.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-111">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="c3bd7-112">Le service web doit être disponible uniquement en interne sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-112">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="c3bd7-113">Un administrateur client doit configurer un enregistrement DNS A dans la production interne Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-113">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="c3bd7-114">Si vous avez un environnement complexe de plusieurs site, consultez l’exemple dans [exemple : site web les enregistrements DNS dans les environnements multisites du contournement de média](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="c3bd7-114">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="c3bd7-115">L'enregistrement DNS doit uniquement résoudre les clients du réseau interne, il ne doit pas résoudre les clients du réseau externe.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-115">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="c3bd7-116">Après avoir configuré le DNS, connectez-vous à Skype Entreprise Online en utilisant PowerShell à distance avec les informations d'identification d'administrateur Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-116">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="c3bd7-117">Pour plus d’informations, voir [configurer votre ordinateur pour Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span><span class="sxs-lookup"><span data-stu-id="c3bd7-117">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="c3bd7-118">Dans la session PowerShell, entrez les commandes suivantes pour activer la déviation du trafic multimédia :</span><span class="sxs-lookup"><span data-stu-id="c3bd7-118">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="c3bd7-119">Activer la déviation du trafic multimédia en deux étapes.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-119">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="c3bd7-120">L'applet de commande New-CsNetworkMedia n'enregistre pas immédiatement la nouvelle configuration, elle crée uniquement les paramètres en mémoire.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-120">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="c3bd7-121">L'objet créé par cette applet de commande doit être enregistré vers une variable, puis affecté à la propriété MediaBypassSettings de la configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-121">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="c3bd7-122">Pour plus d’informations, voir [exemple : site web les enregistrements DNS dans les environnements multisites du contournement de média](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="c3bd7-122">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="c3bd7-123">La réplication entre les composants locaux et en ligne peut prendre jusqu'à 24 heures, c'est pourquoi Microsoft vous recommande d'exécuter les commandes nécessaires avant d'activer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-123">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="c3bd7-124">Confirmer les paramètres de déviation du trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="c3bd7-124">Confirm media bypass settings</span></span>

<span data-ttu-id="c3bd7-125">Vous pouvez vérifier les paramètres de déviation du trafic multimédia comme suit. </span><span class="sxs-lookup"><span data-stu-id="c3bd7-125">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="c3bd7-126">Pour vérifier la réplication en ligne pour votre pool de client, exécutez la commande suivante dans PowerShell distant :</span><span class="sxs-lookup"><span data-stu-id="c3bd7-126">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="c3bd7-127">Pour vérifier la réplication locale, se connecter aux serveurs de médiation de connecteur dans le nuage, exécutez la commande suivante dans PowerShell et confirmez que Enabled = True et AlwaysBypass = True</span><span class="sxs-lookup"><span data-stu-id="c3bd7-127">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="c3bd7-128">Pour vérifier les paramètres du client, vous déconnecter le Skype pour client d’entreprise, vous reconnecter et vérifiez que le client a reçu l’URL de service comme suit :</span><span class="sxs-lookup"><span data-stu-id="c3bd7-128">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="c3bd7-129">Ouvrez %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-129">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="c3bd7-130">Recherchez hybridconfigserviceinternalurl et confirmez que l'URL correspond à celle que vous avez définie.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-130">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="c3bd7-131">Modifier les paramètres de déviation du trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="c3bd7-131">Change media bypass parameters</span></span>

<span data-ttu-id="c3bd7-132">Les administrateurs clients peuvent modifier le nom DNS du service web en exécutant l'applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c3bd7-132">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="c3bd7-133">Les clients doivent se déconnecter et se reconnecter pour voir le nouveau nom de service et observer les modifications. </span><span class="sxs-lookup"><span data-stu-id="c3bd7-133">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="c3bd7-134">Désactiver la déviation du trafic multimédia temporairement</span><span class="sxs-lookup"><span data-stu-id="c3bd7-134">Temporarily disable media bypass</span></span>

<span data-ttu-id="c3bd7-p106">Ce scénario peut être utile pour la résolution des problèmes et la maintenance. Pour désactiver le service, exécutez les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3bd7-p106">This scenario might be useful for troubleshooting or maintenance. To disable the service, run the following cmdlets:</span></span>
  
```
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="c3bd7-137">Après avoir effectué la modification, la réplication de toutes les modifications sur tous les Cloud Connectors peut prendre du temps.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-137">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="c3bd7-138">Pour vérifier l’état de réplication, exécutez la cmdlet suivante dans PowerShell sur les serveurs de médiation de connecteur dans le nuage :</span><span class="sxs-lookup"><span data-stu-id="c3bd7-138">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="c3bd7-139">Lorsque les modifications sont répliquées, le service web sur le serveur de médiation commencera à rejeter les demandes des clients pour le service de déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-139">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="c3bd7-140">Désactiver la déviation du trafic multimédia de façon permanente</span><span class="sxs-lookup"><span data-stu-id="c3bd7-140">Disable media bypass permanently</span></span>

<span data-ttu-id="c3bd7-141">Pour désactiver la déviation du trafic multimédia de façon permanente, un administrateur client doit exécuter les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3bd7-141">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="c3bd7-142">Un administrateur devra également supprimer les adresses web pour la déviation du trafic multimédia des serveurs DNS internes.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-142">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="c3bd7-143">Après avoir apporté les modifications, elle peut prendre du temps pour les modifications soient répliquées dans tous les appareils de nuage connecteur.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-143">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="c3bd7-144">Exemple : enregistrements DNS de sites seb de déviation du trafic multimédia dans des environnements multisites complexes</span><span class="sxs-lookup"><span data-stu-id="c3bd7-144">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="c3bd7-145"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="c3bd7-145"></span></span>

<span data-ttu-id="c3bd7-146">Les clients recevront l'adresse web du service web de déviation du trafic multimédia depuis un serveur DNS interne.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-146">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="c3bd7-147">Le nom du service web sera la même pour tous les appareils nuage connecteur et sites nuage connecteur PSTN.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-147">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="c3bd7-148">Dans un environnement multisite complexe, nous vous recommandons d'utiliser la stratégie DNS de gestion du trafic basée sur la géolocalisation de Windows Server 2016 afin que les clients puissent être redirigés vers le service web local de leur réseau.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-148">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="c3bd7-149">Pour plus d’informations sur les stratégies de DNS Windows 2016, voir [Utiliser la stratégie DNS pour la gestion d’un trafic en fonction de géolocalisation avec les serveurs principaux](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span><span class="sxs-lookup"><span data-stu-id="c3bd7-149">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="c3bd7-150">Voici un exemple de configuration pour une entreprise avec plusieurs sites utilisant une stratégie DNS de gestion du trafic basée sur la géolocalisation de Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-150">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="c3bd7-151">Le nom du service de contournement de média est « hybridvoice.adatum.biz ».</span><span class="sxs-lookup"><span data-stu-id="c3bd7-151">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="c3bd7-152">Le site à Amsterdam comporte quatre appliances nuage connecteur déployés avec les adresses IP de serveur de médiation suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3bd7-152">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="c3bd7-153">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="c3bd7-153">192.168.1.45</span></span>
    
- <span data-ttu-id="c3bd7-154">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="c3bd7-154">192.168.1.46</span></span>
    
- <span data-ttu-id="c3bd7-155">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="c3bd7-155">192.168.1.47</span></span>
    
- <span data-ttu-id="c3bd7-156">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="c3bd7-156">192.168.1.48</span></span>
    
<span data-ttu-id="c3bd7-157">Le site de Seattle a trois appliances nuage connecteur déployés avec les adresses IP de serveur de médiation suivantes :</span><span class="sxs-lookup"><span data-stu-id="c3bd7-157">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="c3bd7-158">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="c3bd7-158">10.10.1.8</span></span>
    
- <span data-ttu-id="c3bd7-159">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="c3bd7-159">10.10.1.9</span></span>
    
- <span data-ttu-id="c3bd7-160">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="c3bd7-160">10.10.1.10</span></span>
    
<span data-ttu-id="c3bd7-161">En utilisant la gestion du trafic basée sur la géolocalisation, les serveurs DNS seraient configurés comme suit :</span><span class="sxs-lookup"><span data-stu-id="c3bd7-161">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="c3bd7-162">créez des sous-réseaux client DNS pour les réseaux d'Amsterdam et de Seattle.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-162">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="c3bd7-163">Créez des étendues de zone DNS pour adatum.biz pour Amsterdam et Seattle.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-163">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="c3bd7-164">Créez des enregistrements DNS dans chaque étendue de zone DNS.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-164">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="c3bd7-165">Amsterdam</span><span class="sxs-lookup"><span data-stu-id="c3bd7-165">Amsterdam</span></span>
    
   - <span data-ttu-id="c3bd7-166">Type A ;</span><span class="sxs-lookup"><span data-stu-id="c3bd7-166">Type A;</span></span>
    
   - <span data-ttu-id="c3bd7-167">Nom : hybridvoice dans l'étendue de zone DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="c3bd7-167">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="c3bd7-168">Cible : 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="c3bd7-168">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="c3bd7-169">Créez des enregistrements supplémentaires pour les serveurs de médiation supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c3bd7-169">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="c3bd7-170">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="c3bd7-170">192.168.1.46</span></span>
    
   - <span data-ttu-id="c3bd7-171">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="c3bd7-171">192.168.1.47</span></span>
    
   - <span data-ttu-id="c3bd7-172">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="c3bd7-172">192.168.1.48</span></span>
    
     <span data-ttu-id="c3bd7-173">Seattle</span><span class="sxs-lookup"><span data-stu-id="c3bd7-173">Seattle</span></span>
    
   - <span data-ttu-id="c3bd7-174">Type A</span><span class="sxs-lookup"><span data-stu-id="c3bd7-174">Type A</span></span>
    
   - <span data-ttu-id="c3bd7-175">Nom : hybridvoice dans l'étendue de zone DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="c3bd7-175">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="c3bd7-176">Cible : 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="c3bd7-176">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="c3bd7-177">Créez des enregistrements supplémentaires pour les serveurs de médiation supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c3bd7-177">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="c3bd7-178">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="c3bd7-178">10.10.1.9</span></span>
    
   - <span data-ttu-id="c3bd7-179">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="c3bd7-179">10.10.1.10</span></span>
    
4. <span data-ttu-id="c3bd7-180">Créez une stratégie DNS qui relie les sous-réseaux du client à l'étendue de zone appropriée pour assurer la résolution DNS souhaitée.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-180">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="c3bd7-181">À ce stade, les clients effectuant des requêtes DNS depuis le sous-réseau d'Amsterdam pour hybridvoice.adatum.biz renvoient les adresses 192.168.1.45, 192.168.1.46, 192.168.1.47 et 192.168.1.48, tandis que les clients effectuant des requêtes DNS depuis Seattle renvoient les adresses 10.10.1.8, 10.10.1.9 et 10.10.1.10.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-181">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="c3bd7-182">Si l’appliance CCE ne semble pas obtenir les paramètres de mise à jour, vérifiez si elle n’est pas en mesure de contacter le client par le biais de PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-182">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="c3bd7-183">Vous pouvez utiliser PowerShell à distance pour vérifier l’état d’application avec Get-CsHybridPSTNAppliance ou comment utiliser PowerShell sur l’hôte CCE pour vérifier l’état avec Get-CcApplianceStatus.</span><span class="sxs-lookup"><span data-stu-id="c3bd7-183">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="c3bd7-184">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c3bd7-184">See also</span></span>
<span data-ttu-id="c3bd7-185"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="c3bd7-185"></span></span>

[<span data-ttu-id="c3bd7-186">Planifier le contournement de média dans Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="c3bd7-186">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
