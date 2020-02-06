---
title: Contournement du déploiement multimédia dans la version Cloud Connector
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
description: Pour plus d’informations sur la procédure de déploiement d’une dérivation multimédia avec la version 2,0 et les versions ultérieures, voir la rubrique.
ms.openlocfilehash: 771d3a7294fde38b032e4cd9a281f70156280d3a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802344"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="d0a8e-103">Contournement du déploiement multimédia dans la version Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="d0a8e-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="d0a8e-104">Pour plus d’informations sur la procédure de déploiement d’une dérivation multimédia avec la version 2,0 et les versions ultérieures, voir la rubrique.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-104">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="d0a8e-105">Bypass Media permet à un client d’envoyer des contenus multimédias directement sur le tronçon de réseau téléphonique commuté (PSTN), une passerelle ou un contrôleur de bordure de session (SBC), et d’éliminer le composant Cloud Connector édition sur le chemin multimédia.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-105">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="d0a8e-106">Voir aussi [plan de contournement multimédia dans la version Cloud Connector](plan-for-media-bypass-in-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="d0a8e-106">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="d0a8e-107">Activer la déviation du trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="d0a8e-107">Enable media bypass</span></span>

<span data-ttu-id="d0a8e-108">Pour activer la déviation du trafic multimédia, vous devez configurer le nom DNS du service web de déviation du trafic multimédia et activer la déviation du trafic multimédia dans la configuration de client.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-108">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="d0a8e-109">Le service web de déviation du trafic multimédia se déploie automatiquement sur chaque serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-109">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="d0a8e-110">Un administrateur de client doit choisir un nom pour un service de voix hybride (site) et ce nom doit provenir d'un domaine SIP inscrit pour la voix hybride.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-110">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="d0a8e-111">Le nom du service doit être identique sur tous les appareils Cloud Connector et sur tous les sites RTC, quel que soit l’emplacement du client.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-111">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="d0a8e-112">Le service web doit être disponible uniquement en interne sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-112">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="d0a8e-113">Un administrateur client doit configurer un enregistrement DNS A dans la production interne Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-113">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="d0a8e-114">Si vous disposez d’un environnement multisite complexe, reportez-vous à l’exemple [ci-dessous : enregistrements DNS du site Web bypass dans les environnements multisites complexes](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="d0a8e-114">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="d0a8e-115">L'enregistrement DNS doit uniquement résoudre les clients du réseau interne, il ne doit pas résoudre les clients du réseau externe.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-115">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="d0a8e-116">Après avoir configuré le DNS, connectez-vous à Skype Entreprise Online en utilisant PowerShell à distance avec les informations d'identification d'administrateur Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-116">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="d0a8e-117">Pour plus d’informations, voir [configurer votre ordinateur pour Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span><span class="sxs-lookup"><span data-stu-id="d0a8e-117">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="d0a8e-118">Dans la session PowerShell, entrez les commandes suivantes pour activer la déviation du trafic multimédia :</span><span class="sxs-lookup"><span data-stu-id="d0a8e-118">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="d0a8e-119">Activer la déviation du trafic multimédia en deux étapes.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-119">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="d0a8e-120">L'applet de commande New-CsNetworkMedia n'enregistre pas immédiatement la nouvelle configuration, elle crée uniquement les paramètres en mémoire.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-120">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="d0a8e-121">L'objet créé par cette applet de commande doit être enregistré vers une variable, puis affecté à la propriété MediaBypassSettings de la configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-121">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="d0a8e-122">Pour plus d’informations, reportez-vous à la section [exemple : Media Bypass site Web Records dans les environnements multisites complexes](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="d0a8e-122">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="d0a8e-123">La réplication entre les composants locaux et en ligne peut prendre jusqu'à 24 heures, c'est pourquoi Microsoft vous recommande d'exécuter les commandes nécessaires avant d'activer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-123">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="d0a8e-124">Confirmer les paramètres de déviation du trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="d0a8e-124">Confirm media bypass settings</span></span>

<span data-ttu-id="d0a8e-125">Vous pouvez vérifier les paramètres de déviation du trafic multimédia comme suit. </span><span class="sxs-lookup"><span data-stu-id="d0a8e-125">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="d0a8e-126">Pour vérifier la réplication en ligne vers votre pool de clients, exécutez la commande suivante dans PowerShell distant :</span><span class="sxs-lookup"><span data-stu-id="d0a8e-126">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="d0a8e-127">Pour vérifier la réplication locale, connectez-vous aux serveurs de médiation Cloud Connector, exécutez la commande suivante dans PowerShell et confirmez que enabled = true et AlwaysBypass = true</span><span class="sxs-lookup"><span data-stu-id="d0a8e-127">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="d0a8e-128">Pour vérifier les paramètres du client, déconnectez-vous du client Skype entreprise, reconnectez-vous, puis vérifiez que le client a reçu l’URL du service comme suit :</span><span class="sxs-lookup"><span data-stu-id="d0a8e-128">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="d0a8e-129">Ouvrez %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-129">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="d0a8e-130">Recherchez hybridconfigserviceinternalurl et confirmez que l'URL correspond à celle que vous avez définie.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-130">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="d0a8e-131">Modifier les paramètres de déviation du trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="d0a8e-131">Change media bypass parameters</span></span>

<span data-ttu-id="d0a8e-132">Les administrateurs clients peuvent modifier le nom DNS du service web en exécutant l'applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d0a8e-132">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="d0a8e-133">Les clients doivent se déconnecter et se reconnecter pour voir le nouveau nom de service et observer les modifications. </span><span class="sxs-lookup"><span data-stu-id="d0a8e-133">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="d0a8e-134">Désactiver la déviation du trafic multimédia temporairement</span><span class="sxs-lookup"><span data-stu-id="d0a8e-134">Temporarily disable media bypass</span></span>

<span data-ttu-id="d0a8e-p106">Ce scénario peut être utile pour la résolution des problèmes et la maintenance. Pour désactiver le service, exécutez les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="d0a8e-p106">This scenario might be useful for troubleshooting or maintenance. To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="d0a8e-137">Après avoir effectué la modification, la réplication de toutes les modifications sur tous les Cloud Connectors peut prendre du temps.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-137">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="d0a8e-138">Pour vérifier l’état de la réplication, exécutez l’applet de commande suivante dans PowerShell sur les serveurs de médiation Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="d0a8e-138">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="d0a8e-139">Lorsque les modifications sont répliquées, le service web sur le serveur de médiation commencera à rejeter les demandes des clients pour le service de déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-139">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="d0a8e-140">Désactiver la déviation du trafic multimédia de façon permanente</span><span class="sxs-lookup"><span data-stu-id="d0a8e-140">Disable media bypass permanently</span></span>

<span data-ttu-id="d0a8e-141">Pour désactiver la déviation du trafic multimédia de façon permanente, un administrateur client doit exécuter les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="d0a8e-141">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="d0a8e-142">Un administrateur devra également supprimer les adresses web pour la déviation du trafic multimédia des serveurs DNS internes.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-142">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="d0a8e-143">Après avoir effectué la modification, il est possible que les modifications soient répliquées sur tous les appareils Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-143">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="d0a8e-144">Exemple : enregistrements DNS de sites seb de déviation du trafic multimédia dans des environnements multisites complexes</span><span class="sxs-lookup"><span data-stu-id="d0a8e-144">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="d0a8e-145"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="d0a8e-145"><a name="Example"> </a></span></span>

<span data-ttu-id="d0a8e-146">Les clients recevront l'adresse web du service web de déviation du trafic multimédia depuis un serveur DNS interne.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-146">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="d0a8e-147">Le nom du service Web sera le même sur tous les appareils Cloud Connector et sur les sites RTC du Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-147">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="d0a8e-148">Dans un environnement multisite complexe, nous vous recommandons d'utiliser la stratégie DNS de gestion du trafic basée sur la géolocalisation de Windows Server 2016 afin que les clients puissent être redirigés vers le service web local de leur réseau.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-148">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="d0a8e-149">Pour plus d’informations sur les stratégies DNS de Windows 2016, voir [utilisation de la stratégie DNS pour la gestion du trafic basée sur la géolocalisation avec les serveurs principaux](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span><span class="sxs-lookup"><span data-stu-id="d0a8e-149">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="d0a8e-150">Voici un exemple de configuration pour une entreprise avec plusieurs sites utilisant une stratégie DNS de gestion du trafic basée sur la géolocalisation de Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-150">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="d0a8e-151">Le nom du service de contournement est « hybridvoice.adatum.biz ».</span><span class="sxs-lookup"><span data-stu-id="d0a8e-151">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="d0a8e-152">Le site d’Amsterdam comporte quatre appareils Cloud Connector déployés avec les adresses IP du serveur de médiation suivantes :</span><span class="sxs-lookup"><span data-stu-id="d0a8e-152">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="d0a8e-153">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="d0a8e-153">192.168.1.45</span></span>
    
- <span data-ttu-id="d0a8e-154">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="d0a8e-154">192.168.1.46</span></span>
    
- <span data-ttu-id="d0a8e-155">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="d0a8e-155">192.168.1.47</span></span>
    
- <span data-ttu-id="d0a8e-156">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="d0a8e-156">192.168.1.48</span></span>
    
<span data-ttu-id="d0a8e-157">Le site de Seattle comporte trois appareils Cloud Connector déployés avec les adresses IP du serveur de médiation suivantes :</span><span class="sxs-lookup"><span data-stu-id="d0a8e-157">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="d0a8e-158">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="d0a8e-158">10.10.1.8</span></span>
    
- <span data-ttu-id="d0a8e-159">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="d0a8e-159">10.10.1.9</span></span>
    
- <span data-ttu-id="d0a8e-160">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="d0a8e-160">10.10.1.10</span></span>
    
<span data-ttu-id="d0a8e-161">En utilisant la gestion du trafic basée sur la géolocalisation, les serveurs DNS seraient configurés comme suit :</span><span class="sxs-lookup"><span data-stu-id="d0a8e-161">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="d0a8e-162">créez des sous-réseaux client DNS pour les réseaux d'Amsterdam et de Seattle.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-162">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="d0a8e-163">Créez des étendues de zone DNS pour adatum.biz pour Amsterdam et Seattle.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-163">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="d0a8e-164">Créez des enregistrements DNS dans chaque étendue de zone DNS.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-164">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="d0a8e-165">Amsterdam</span><span class="sxs-lookup"><span data-stu-id="d0a8e-165">Amsterdam</span></span>
    
   - <span data-ttu-id="d0a8e-166">Type A ;</span><span class="sxs-lookup"><span data-stu-id="d0a8e-166">Type A;</span></span>
    
   - <span data-ttu-id="d0a8e-167">Nom : hybridvoice dans l'étendue de zone DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d0a8e-167">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="d0a8e-168">Cible : 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="d0a8e-168">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="d0a8e-169">Créez des enregistrements supplémentaires pour les serveurs de médiation supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d0a8e-169">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="d0a8e-170">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="d0a8e-170">192.168.1.46</span></span>
    
   - <span data-ttu-id="d0a8e-171">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="d0a8e-171">192.168.1.47</span></span>
    
   - <span data-ttu-id="d0a8e-172">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="d0a8e-172">192.168.1.48</span></span>
    
     <span data-ttu-id="d0a8e-173">Seattle</span><span class="sxs-lookup"><span data-stu-id="d0a8e-173">Seattle</span></span>
    
   - <span data-ttu-id="d0a8e-174">Type A</span><span class="sxs-lookup"><span data-stu-id="d0a8e-174">Type A</span></span>
    
   - <span data-ttu-id="d0a8e-175">Nom : hybridvoice dans l'étendue de zone DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="d0a8e-175">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="d0a8e-176">Cible : 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="d0a8e-176">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="d0a8e-177">Créez des enregistrements supplémentaires pour les serveurs de médiation supplémentaires</span><span class="sxs-lookup"><span data-stu-id="d0a8e-177">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="d0a8e-178">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="d0a8e-178">10.10.1.9</span></span>
    
   - <span data-ttu-id="d0a8e-179">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="d0a8e-179">10.10.1.10</span></span>
    
4. <span data-ttu-id="d0a8e-180">Créez une stratégie DNS qui relie les sous-réseaux du client à l'étendue de zone appropriée pour assurer la résolution DNS souhaitée.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-180">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="d0a8e-181">À ce stade, les clients effectuant des requêtes DNS depuis le sous-réseau d'Amsterdam pour hybridvoice.adatum.biz renvoient les adresses 192.168.1.45, 192.168.1.46, 192.168.1.47 et 192.168.1.48, tandis que les clients effectuant des requêtes DNS depuis Seattle renvoient les adresses 10.10.1.8, 10.10.1.9 et 10.10.1.10.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-181">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="d0a8e-182">Si l’application CCE ne donne pas les paramètres mis à jour, vérifiez si l’application peut contacter le client par le biais de PowerShell distante.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-182">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="d0a8e-183">Vous pouvez utiliser Remote PowerShell pour vérifier l’état de l’appareil avec Get-CsHybridPSTNAppliance ou utiliser PowerShell sur l’hôte CCE pour vérifier l’état avec Get-CcApplianceStatus.</span><span class="sxs-lookup"><span data-stu-id="d0a8e-183">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="d0a8e-184">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d0a8e-184">See also</span></span>
<span data-ttu-id="d0a8e-185"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="d0a8e-185"><a name="Example"> </a></span></span>

[<span data-ttu-id="d0a8e-186">Planifier le contournement de média dans Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="d0a8e-186">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
