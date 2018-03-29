---
title: Déployer le contournement de média dans le nuage lien édition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Lisez cette rubrique pour en savoir plus sur les étapes à suivre pour déployer, media de contournement avec connecteur de nuage Edition version 2.0 et ultérieure.
ms.openlocfilehash: a9f03d1d83d398a6aa78f90a4741d0010ea50392
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="40cd6-103">Déployer le contournement de média dans le nuage lien édition</span><span class="sxs-lookup"><span data-stu-id="40cd6-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="40cd6-104">Lisez cette rubrique pour en savoir plus sur les étapes à suivre pour déployer, media de contournement avec connecteur de nuage Edition version 2.0 et ultérieure.</span><span class="sxs-lookup"><span data-stu-id="40cd6-104">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="40cd6-105">Le contournement de média permet au client d’envoyer le CD directement sur le tronçon suivant de commutation de téléphone RTPC (réseau Public), une passerelle ou un contrôleur de Session en périphérie (SBC) — et d’éliminer le composant d’édition de connecteur de nuage du chemin d’accès de média.</span><span class="sxs-lookup"><span data-stu-id="40cd6-105">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="40cd6-106">Voir aussi le [Plan de support ignorer dans le nuage lien édition](plan-for-media-bypass-in-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="40cd6-106">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="40cd6-107">Activer la déviation du trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="40cd6-107">Enable media bypass</span></span>

<span data-ttu-id="40cd6-108">Pour activer le contournement de média, vous devez configurer le nom DNS du service web de contournement de média et activer le contournement de média dans la configuration des clients.</span><span class="sxs-lookup"><span data-stu-id="40cd6-108">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="40cd6-109">Le service web de contournement media déploie automatiquement sur chaque serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="40cd6-109">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="40cd6-110">Un administrateur doit choisir un nom pour un service de voix hybride (site), et ce nom doit être d’un domaine SIP enregistré pour les voix hybride.</span><span class="sxs-lookup"><span data-stu-id="40cd6-110">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="40cd6-111">Le nom du service doit être le même sur tous les appareils du connecteur du nuage et de tous les sites de RTPC, quel que soit l’emplacement du client.</span><span class="sxs-lookup"><span data-stu-id="40cd6-111">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="40cd6-112">Le service web doit uniquement être disponible en interne sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="40cd6-112">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="40cd6-113">Un administrateur doit configurer un enregistrement DNS A dans la production interne de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="40cd6-113">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="40cd6-114">Si vous disposez d’un environnement complexe de plusieurs sites, consultez l’exemple dans [exemple : media ignore les enregistrements DNS de site web dans des environnements complexes sur plusieurs sites](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="40cd6-114">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="40cd6-115">L’enregistrement DNS doit résoudre uniquement pour les clients du réseau interne ; Il ne doit pas résolu pour les clients du réseau externe.</span><span class="sxs-lookup"><span data-stu-id="40cd6-115">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="40cd6-116">Après la configuration du service DNS, connecter à Skype pour entreprise en ligne à l’aide du PowerShell distant avec Skype pour les informations d’identification de l’administrateur de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="40cd6-116">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="40cd6-117">Pour plus d’informations, consultez [connexion à Skype pour entreprise en ligne à l’aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="40cd6-117">For more information, see [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="40cd6-118">Dans la session PowerShell, entrez les commandes suivantes pour activer la déviation du trafic multimédia :</span><span class="sxs-lookup"><span data-stu-id="40cd6-118">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="40cd6-119">Activer le contournement de média est un processus en deux étapes.</span><span class="sxs-lookup"><span data-stu-id="40cd6-119">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="40cd6-120">L’applet de commande New-CsNetworkMedia n’enregistre pas immédiatement la nouvelle configuration ; Il crée les paramètres dans la mémoire.</span><span class="sxs-lookup"><span data-stu-id="40cd6-120">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="40cd6-121">L’objet créé par cette applet de commande doit être enregistré dans une variable et ensuite assignée à la propriété MediaBypassSettings de la configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="40cd6-121">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="40cd6-122">Pour plus d’informations, consultez [exemple : media ignore les enregistrements DNS de site web dans des environnements complexes sur plusieurs sites](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="40cd6-122">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="40cd6-123">La réplication entre les locaux et les composants en ligne peut prendre jusqu'à 24 heures, afin que Microsoft recommande d’exécuter les commandes nécessaires avant d’activer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="40cd6-123">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="40cd6-124">Confirmer les paramètres de déviation du trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="40cd6-124">Confirm media bypass settings</span></span>

<span data-ttu-id="40cd6-125">Vous pouvez vérifier les paramètres de déviation du trafic multimédia comme suit. </span><span class="sxs-lookup"><span data-stu-id="40cd6-125">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="40cd6-126">Pour vérifier la réplication en ligne pour votre pool de client, exécutez la commande suivante dans PowerShell distant :</span><span class="sxs-lookup"><span data-stu-id="40cd6-126">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore

```

<span data-ttu-id="40cd6-127">Pour vérifier la réplication locale, de se connecter aux serveurs de médiation de connecteur de nuage, exécutez la commande suivante dans PowerShell et confirmer que Enabled = True et AlwaysBypass = True</span><span class="sxs-lookup"><span data-stu-id="40cd6-127">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="40cd6-128">Pour vérifier les paramètres du client, se déconnecter de la Skype pour client d’entreprise, vous reconnecter et confirmer que le client a reçu l’URL de service comme suit :</span><span class="sxs-lookup"><span data-stu-id="40cd6-128">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="40cd6-129">Ouvrez %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. </span><span class="sxs-lookup"><span data-stu-id="40cd6-129">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="40cd6-130">Recherchez hybridconfigserviceinternalurl et confirmez l’URL correspond à celui que vous avez défini.</span><span class="sxs-lookup"><span data-stu-id="40cd6-130">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="40cd6-131">Modifier les paramètres de déviation du trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="40cd6-131">Change media bypass parameters</span></span>

<span data-ttu-id="40cd6-132">Les administrateurs clients peuvent modifier le nom DNS du service web en exécutant l'applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="40cd6-132">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="40cd6-133">Les clients doivent se déconnecter et se reconnecter pour voir le nouveau nom de service et observer les modifications. </span><span class="sxs-lookup"><span data-stu-id="40cd6-133">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="40cd6-134">Désactiver la déviation du trafic multimédia temporairement</span><span class="sxs-lookup"><span data-stu-id="40cd6-134">Temporarily disable media bypass</span></span>

<span data-ttu-id="40cd6-p106">Ce scénario peut être utile pour la résolution des problèmes et la maintenance. Pour désactiver le service, exécutez les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="40cd6-p106">This scenario might be useful for troubleshooting or maintenance. To disable the service, run the following cmdlets:</span></span>
  
```
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="40cd6-137">Après avoir apporté la modification, il peut prendre un certain temps pour que les modifications à répliquer sur tous les connecteurs de nuage.</span><span class="sxs-lookup"><span data-stu-id="40cd6-137">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="40cd6-138">Pour vérifier l’état de la réplication, exécutez l’applet de commande suivant dans PowerShell sur les serveurs de médiation de connecteur de nuage :</span><span class="sxs-lookup"><span data-stu-id="40cd6-138">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="40cd6-139">Lorsque les modifications sont répliquées, le service web sur le serveur de médiation commencera à rejeter les demandes des clients pour le service de déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="40cd6-139">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="40cd6-140">Désactiver la déviation du trafic multimédia de façon permanente</span><span class="sxs-lookup"><span data-stu-id="40cd6-140">Disable media bypass permanently</span></span>

<span data-ttu-id="40cd6-141">Pour désactiver la déviation du trafic multimédia de façon permanente, un administrateur client doit exécuter les commandes suivantes : </span><span class="sxs-lookup"><span data-stu-id="40cd6-141">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="40cd6-142">Un administrateur devra également à supprimer les adresses web de contournement de média à partir de serveurs DNS internes.</span><span class="sxs-lookup"><span data-stu-id="40cd6-142">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="40cd6-143">Après avoir apporté la modification, il peut prendre un certain temps pour que les modifications à répliquer sur tous les appareils de connecteur de nuage.</span><span class="sxs-lookup"><span data-stu-id="40cd6-143">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="40cd6-144">Exemple : enregistrements DNS de sites seb de déviation du trafic multimédia dans des environnements multisites complexes</span><span class="sxs-lookup"><span data-stu-id="40cd6-144">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="40cd6-145"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="40cd6-145"></span></span>

<span data-ttu-id="40cd6-146">Les clients recevront l’adresse web du service web de contournement de média à partir d’un serveur DNS interne.</span><span class="sxs-lookup"><span data-stu-id="40cd6-146">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="40cd6-147">Le nom du service web sera la même sur tous les appareils du connecteur du nuage et sites de nuage connecteur PSTN.</span><span class="sxs-lookup"><span data-stu-id="40cd6-147">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="40cd6-148">Dans un environnement multisite complexe, nous vous recommandons d’à l’aide de la stratégie de DNS Windows 2016 pour la gestion du trafic en fonction de géolocalisation, afin que les clients peuvent être redirigés vers le service web qui est local pour leur réseau.</span><span class="sxs-lookup"><span data-stu-id="40cd6-148">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="40cd6-149">Pour plus d’informations sur les stratégies de DNS Windows 2016, voir [Utiliser une stratégie DNS de géolocalisation en fonction de la gestion du trafic avec les serveurs principaux](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location).</span><span class="sxs-lookup"><span data-stu-id="40cd6-149">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="40cd6-150">Voici un exemple de configuration pour une entreprise avec plusieurs sites utilisant une stratégie DNS de gestion du trafic basée sur la géolocalisation de Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="40cd6-150">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="40cd6-151">Le nom du service de contournement est 'hybridvoice.adatum.biz'.</span><span class="sxs-lookup"><span data-stu-id="40cd6-151">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="40cd6-152">Le site d’Amsterdam a quatre appliances de connecteur de nuage déployés avec les adresses IP de serveur de médiation suivantes :</span><span class="sxs-lookup"><span data-stu-id="40cd6-152">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="40cd6-153">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="40cd6-153">192.168.1.45</span></span>
    
- <span data-ttu-id="40cd6-154">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="40cd6-154">192.168.1.46</span></span>
    
- <span data-ttu-id="40cd6-155">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="40cd6-155">192.168.1.47</span></span>
    
- <span data-ttu-id="40cd6-156">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="40cd6-156">192.168.1.48</span></span>
    
<span data-ttu-id="40cd6-157">Le site de Seattle a trois appareils de connecteur de nuage déployés avec les adresses IP de serveur de médiation suivantes :</span><span class="sxs-lookup"><span data-stu-id="40cd6-157">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="40cd6-158">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="40cd6-158">10.10.1.8</span></span>
    
- <span data-ttu-id="40cd6-159">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="40cd6-159">10.10.1.9</span></span>
    
- <span data-ttu-id="40cd6-160">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="40cd6-160">10.10.1.10</span></span>
    
<span data-ttu-id="40cd6-161">En utilisant la gestion du trafic basée sur la géolocalisation, les serveurs DNS seraient configurés comme suit :</span><span class="sxs-lookup"><span data-stu-id="40cd6-161">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="40cd6-162">créez des sous-réseaux client DNS pour les réseaux d'Amsterdam et de Seattle.</span><span class="sxs-lookup"><span data-stu-id="40cd6-162">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="40cd6-163">Créez des étendues de zone DNS pour adatum.biz pour Amsterdam et Seattle.</span><span class="sxs-lookup"><span data-stu-id="40cd6-163">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="40cd6-164">Créez des enregistrements DNS dans chaque étendue de zone DNS.</span><span class="sxs-lookup"><span data-stu-id="40cd6-164">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="40cd6-165">Amsterdam</span><span class="sxs-lookup"><span data-stu-id="40cd6-165">Amsterdam</span></span>
    
  - <span data-ttu-id="40cd6-166">Type A ;</span><span class="sxs-lookup"><span data-stu-id="40cd6-166">Type A;</span></span>
    
  - <span data-ttu-id="40cd6-167">Nom : hybridvoice dans l'étendue de zone DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="40cd6-167">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
  - <span data-ttu-id="40cd6-168">Cible : 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="40cd6-168">Target: 192.168.1.45</span></span>
    
    <span data-ttu-id="40cd6-169">Créez des enregistrements supplémentaires pour les serveurs de médiation supplémentaires</span><span class="sxs-lookup"><span data-stu-id="40cd6-169">Create additional records for additional mediation servers</span></span>
    
  - <span data-ttu-id="40cd6-170">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="40cd6-170">192.168.1.46</span></span>
    
  - <span data-ttu-id="40cd6-171">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="40cd6-171">192.168.1.47</span></span>
    
  - <span data-ttu-id="40cd6-172">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="40cd6-172">192.168.1.48</span></span>
    
    <span data-ttu-id="40cd6-173">Seattle</span><span class="sxs-lookup"><span data-stu-id="40cd6-173">Seattle</span></span>
    
  - <span data-ttu-id="40cd6-174">Type A</span><span class="sxs-lookup"><span data-stu-id="40cd6-174">Type A</span></span>
    
  - <span data-ttu-id="40cd6-175">Nom : hybridvoice dans l'étendue de zone DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="40cd6-175">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
  - <span data-ttu-id="40cd6-176">Cible : 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="40cd6-176">Target: 10.10.1.8</span></span>
    
    <span data-ttu-id="40cd6-177">Créez des enregistrements supplémentaires pour les serveurs de médiation supplémentaires</span><span class="sxs-lookup"><span data-stu-id="40cd6-177">Create additional records for additional mediation servers</span></span>
    
  - <span data-ttu-id="40cd6-178">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="40cd6-178">10.10.1.9</span></span>
    
  - <span data-ttu-id="40cd6-179">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="40cd6-179">10.10.1.10</span></span>
    
4. <span data-ttu-id="40cd6-180">Créez une stratégie DNS qui relie les sous-réseaux du client à l'étendue de zone appropriée pour assurer la résolution DNS souhaitée.</span><span class="sxs-lookup"><span data-stu-id="40cd6-180">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="40cd6-181">À ce stade, les clients effectuant des requêtes DNS depuis le sous-réseau d'Amsterdam pour hybridvoice.adatum.biz renvoient les adresses 192.168.1.45, 192.168.1.46, 192.168.1.47 et 192.168.1.48, tandis que les clients effectuant des requêtes DNS depuis Seattle renvoient les adresses 10.10.1.8, 10.10.1.9 et 10.10.1.10.</span><span class="sxs-lookup"><span data-stu-id="40cd6-181">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="40cd6-182">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="40cd6-182">See also</span></span>
<span data-ttu-id="40cd6-183"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="40cd6-183"></span></span>

#### 

[<span data-ttu-id="40cd6-184">Planifier le contournement de média dans le nuage lien édition</span><span class="sxs-lookup"><span data-stu-id="40cd6-184">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)

