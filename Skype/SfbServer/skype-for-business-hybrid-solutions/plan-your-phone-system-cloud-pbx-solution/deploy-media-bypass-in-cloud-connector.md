---
title: Déploiement de la déviation du trafic multimédia dans Cloud Connector Edition
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
description: Lisez cette rubrique pour en savoir plus sur les étapes de déploiement de la déviation du trafic multimédia avec la version 2,0 et les versions ultérieures de Cloud Connector.
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359310"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="623e6-103">Déploiement de la déviation du trafic multimédia dans Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="623e6-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="623e6-104">La version Cloud Connector sera déconnectée le 31 juillet 2021 avec Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="623e6-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="623e6-105">Une fois que votre organisation a effectué la mise à niveau vers Teams, Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="623e6-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="623e6-106">Lisez cette rubrique pour en savoir plus sur les étapes de déploiement de la déviation du trafic multimédia avec la version 2,0 et les versions ultérieures de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="623e6-106">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="623e6-107">La déviation du trafic multimédia permet à un client d’envoyer directement des médias au tronçon suivant du réseau téléphonique commuté (RTC), à savoir un contrôleur de frontière de session ou un contrôleur SBC (session Border Controller) et d’éliminer le composant Cloud Connector Edition du chemin de média.</span><span class="sxs-lookup"><span data-stu-id="623e6-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="623e6-108">Voir aussi [plan for Media Bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="623e6-108">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="623e6-109">Activer le contournement de média</span><span class="sxs-lookup"><span data-stu-id="623e6-109">Enable media bypass</span></span>

<span data-ttu-id="623e6-110">Pour activer la déviation du trafic multimédia, vous devez configurer le nom DNS du service Web de déviation du trafic multimédia et activer la déviation du trafic multimédia dans la configuration du client.</span><span class="sxs-lookup"><span data-stu-id="623e6-110">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="623e6-111">Le service Web de déviation du trafic multimédia se déploie automatiquement sur chaque serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="623e6-111">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="623e6-112">Un administrateur client doit choisir un nom pour un service voix hybride (site), et ce nom doit provenir d’un domaine SIP enregistré pour la voix hybride.</span><span class="sxs-lookup"><span data-stu-id="623e6-112">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="623e6-113">Le nom du service doit être le même pour toutes les appliances Cloud Connector et tous les sites PSTN, quel que soit l’emplacement du client.</span><span class="sxs-lookup"><span data-stu-id="623e6-113">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="623e6-114">Le service Web ne doit être disponible qu’en interne sur le réseau.</span><span class="sxs-lookup"><span data-stu-id="623e6-114">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="623e6-115">Un administrateur client doit configurer un enregistrement DNS A dans le service Active Directory de production interne.</span><span class="sxs-lookup"><span data-stu-id="623e6-115">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="623e6-116">Si vous disposez d’un environnement multisite complexe, consultez l’exemple de l’exemple [ci-dessous : enregistrements DNS du site Web de déviation du trafic multimédia dans des environnements multisites complexes](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="623e6-116">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="623e6-117">L’enregistrement DNS ne doit être résolu que pour les clients du réseau interne ; il ne doit pas être résolu pour les clients du réseau externe.</span><span class="sxs-lookup"><span data-stu-id="623e6-117">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="623e6-118">Après avoir configuré le DNS, connectez-vous à Skype entreprise Online à l’aide de PowerShell à distance avec les informations d’identification de l’administrateur Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="623e6-118">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="623e6-119">Pour plus d’informations, reportez-vous à [configurer votre ordinateur pour Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span><span class="sxs-lookup"><span data-stu-id="623e6-119">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="623e6-120">Dans la session PowerShell, entrez les commandes suivantes pour activer la déviation du trafic multimédia :</span><span class="sxs-lookup"><span data-stu-id="623e6-120">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="623e6-121">L’activation de la déviation du trafic multimédia est un processus en deux étapes.</span><span class="sxs-lookup"><span data-stu-id="623e6-121">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="623e6-122">La cmdlet New-CsNetworkMedia n’enregistre pas immédiatement la nouvelle configuration ; Il crée uniquement les paramètres en mémoire.</span><span class="sxs-lookup"><span data-stu-id="623e6-122">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="623e6-123">L’objet créé par cette applet de commande doit être enregistré dans une variable, puis affecté à la propriété MediaBypassSettings de la configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="623e6-123">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="623e6-124">Pour plus d’informations, reportez-vous aux [enregistrements DNS du site Web de contournement de média dans les environnements multisites complexes](deploy-media-bypass-in-cloud-connector.md#Example).</span><span class="sxs-lookup"><span data-stu-id="623e6-124">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="623e6-125">La réplication entre les composants locaux et en ligne peut prendre jusqu’à 24 heures, c’est pourquoi Microsoft vous recommande d’exécuter les commandes nécessaires avant d’activer les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="623e6-125">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="623e6-126">Vérifier les paramètres de contournement de média</span><span class="sxs-lookup"><span data-stu-id="623e6-126">Confirm media bypass settings</span></span>

<span data-ttu-id="623e6-127">Vous pouvez vérifier les paramètres de déviation du trafic multimédia comme suit.</span><span class="sxs-lookup"><span data-stu-id="623e6-127">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="623e6-128">Pour vérifier la réplication en ligne de votre pool de locataires, exécutez la commande suivante dans PowerShell à distance :</span><span class="sxs-lookup"><span data-stu-id="623e6-128">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="623e6-129">Pour vérifier la réplication locale, connectez-vous aux serveurs de médiation Cloud Connector, exécutez la commande suivante dans PowerShell, puis confirmez que enabled = true et AlwaysBypass = true.</span><span class="sxs-lookup"><span data-stu-id="623e6-129">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="623e6-130">Pour vérifier les paramètres du client, déconnectez-vous du client Skype entreprise, reconnectez-vous, puis confirmez que le client a reçu l’URL de service comme suit :</span><span class="sxs-lookup"><span data-stu-id="623e6-130">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="623e6-131">Ouvrir%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span><span class="sxs-lookup"><span data-stu-id="623e6-131">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="623e6-132">Recherchez hybridconfigserviceinternalurl et confirmez que l’URL correspond à celle que vous avez définie.</span><span class="sxs-lookup"><span data-stu-id="623e6-132">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="623e6-133">Modifier les paramètres de contournement de média</span><span class="sxs-lookup"><span data-stu-id="623e6-133">Change media bypass parameters</span></span>

<span data-ttu-id="623e6-134">Les administrateurs clients peuvent modifier le nom DNS du service Web en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="623e6-134">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="623e6-135">Les clients doivent se déconnecter et se connecter pour obtenir le nouveau nom de service et reconnaître la modification.</span><span class="sxs-lookup"><span data-stu-id="623e6-135">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="623e6-136">Désactiver temporairement la déviation du trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="623e6-136">Temporarily disable media bypass</span></span>

<span data-ttu-id="623e6-137">Ce scénario peut être utile pour le dépannage ou la maintenance.</span><span class="sxs-lookup"><span data-stu-id="623e6-137">This scenario might be useful for troubleshooting or maintenance.</span></span> <span data-ttu-id="623e6-138">Pour désactiver le service, exécutez les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="623e6-138">To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="623e6-139">Après avoir effectué la modification, la réplication des modifications sur tous les connecteurs Cloud peut prendre du temps.</span><span class="sxs-lookup"><span data-stu-id="623e6-139">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="623e6-140">Pour vérifier l’état de la réplication, exécutez l’applet de commande suivante dans PowerShell sur les serveurs de médiation Cloud Connector :</span><span class="sxs-lookup"><span data-stu-id="623e6-140">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="623e6-141">Une fois les modifications répliquées, le service Web sur le serveur de médiation commence à rejeter les demandes des clients pour le service de déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="623e6-141">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="623e6-142">Désactiver définitivement la déviation du trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="623e6-142">Disable media bypass permanently</span></span>

<span data-ttu-id="623e6-143">Pour désactiver la déviation du trafic multimédia de façon permanente, un administrateur client doit exécuter les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="623e6-143">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="623e6-144">Un administrateur doit également supprimer les adresses Web pour la déviation du trafic multimédia des serveurs DNS internes.</span><span class="sxs-lookup"><span data-stu-id="623e6-144">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="623e6-145">Après avoir effectué la modification, la réplication des modifications sur tous les appareils Cloud Connector peut prendre du temps.</span><span class="sxs-lookup"><span data-stu-id="623e6-145">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="623e6-146">Exemple : enregistrements DNS du site Web de contournement de média dans des environnements multisites complexes</span><span class="sxs-lookup"><span data-stu-id="623e6-146">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="623e6-147"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="623e6-147"><a name="Example"> </a></span></span>

<span data-ttu-id="623e6-148">Les clients recevront l’adresse Web du service Web de déviation du trafic multimédia à partir d’un serveur DNS interne.</span><span class="sxs-lookup"><span data-stu-id="623e6-148">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="623e6-149">Le nom du service Web est le même pour tous les appareils Cloud Connector et les sites RTC de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="623e6-149">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="623e6-150">Dans un environnement multisite complexe, nous vous recommandons d’utiliser la stratégie DNS Windows 2016 pour la gestion du trafic basé sur l’emplacement géographique, afin que les clients puissent être redirigés vers le service Web qui est local pour leur réseau.</span><span class="sxs-lookup"><span data-stu-id="623e6-150">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="623e6-151">Pour plus d’informations sur les stratégies DNS Windows 2016, reportez-vous à la rubrique [use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span><span class="sxs-lookup"><span data-stu-id="623e6-151">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="623e6-152">Voici un exemple de configuration pour une société avec plusieurs sites utilisant la stratégie DNS Windows 2016 pour la gestion du trafic basée sur l’emplacement géographique.</span><span class="sxs-lookup"><span data-stu-id="623e6-152">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="623e6-153">Le nom du service de contournement est « hybridvoice.adatum.biz ».</span><span class="sxs-lookup"><span data-stu-id="623e6-153">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="623e6-154">Le site à Amsterdam est doté de quatre Appliances Cloud Connector déployées avec les adresses IP de serveur de médiation suivantes :</span><span class="sxs-lookup"><span data-stu-id="623e6-154">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="623e6-155">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="623e6-155">192.168.1.45</span></span>
    
- <span data-ttu-id="623e6-156">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="623e6-156">192.168.1.46</span></span>
    
- <span data-ttu-id="623e6-157">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="623e6-157">192.168.1.47</span></span>
    
- <span data-ttu-id="623e6-158">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="623e6-158">192.168.1.48</span></span>
    
<span data-ttu-id="623e6-159">Le site à Seattle dispose de trois appliances Cloud Connector déployées avec les adresses IP de serveur de médiation suivantes :</span><span class="sxs-lookup"><span data-stu-id="623e6-159">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="623e6-160">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="623e6-160">10.10.1.8</span></span>
    
- <span data-ttu-id="623e6-161">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="623e6-161">10.10.1.9</span></span>
    
- <span data-ttu-id="623e6-162">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="623e6-162">10.10.1.10</span></span>
    
<span data-ttu-id="623e6-163">À l’aide de la gestion du trafic basé sur l’emplacement géographique, les serveurs DNS sont configurés comme suit :</span><span class="sxs-lookup"><span data-stu-id="623e6-163">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="623e6-164">Créez des sous-réseaux de client DNS pour les sous-réseaux d’Amsterdam et de Seattle.</span><span class="sxs-lookup"><span data-stu-id="623e6-164">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="623e6-165">Créez des étendues de zone DNS pour adatum.biz pour Amsterdam et Seattle.</span><span class="sxs-lookup"><span data-stu-id="623e6-165">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="623e6-166">Créez des enregistrements DNS dans chaque étendue de zone DNS.</span><span class="sxs-lookup"><span data-stu-id="623e6-166">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="623e6-167">Amsterdam</span><span class="sxs-lookup"><span data-stu-id="623e6-167">Amsterdam</span></span>
    
   - <span data-ttu-id="623e6-168">Type A ;</span><span class="sxs-lookup"><span data-stu-id="623e6-168">Type A;</span></span>
    
   - <span data-ttu-id="623e6-169">Nom : hybridvoice dans la zone DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="623e6-169">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="623e6-170">Cible : 192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="623e6-170">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="623e6-171">Créer des enregistrements supplémentaires pour les serveurs de médiation supplémentaires</span><span class="sxs-lookup"><span data-stu-id="623e6-171">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="623e6-172">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="623e6-172">192.168.1.46</span></span>
    
   - <span data-ttu-id="623e6-173">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="623e6-173">192.168.1.47</span></span>
    
   - <span data-ttu-id="623e6-174">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="623e6-174">192.168.1.48</span></span>
    
     <span data-ttu-id="623e6-175">Seattle</span><span class="sxs-lookup"><span data-stu-id="623e6-175">Seattle</span></span>
    
   - <span data-ttu-id="623e6-176">Tapez un</span><span class="sxs-lookup"><span data-stu-id="623e6-176">Type A</span></span>
    
   - <span data-ttu-id="623e6-177">Nom : hybridvoice dans la zone DNS adatum.biz</span><span class="sxs-lookup"><span data-stu-id="623e6-177">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="623e6-178">Cible : 10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="623e6-178">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="623e6-179">Créer des enregistrements supplémentaires pour les serveurs de médiation supplémentaires</span><span class="sxs-lookup"><span data-stu-id="623e6-179">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="623e6-180">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="623e6-180">10.10.1.9</span></span>
    
   - <span data-ttu-id="623e6-181">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="623e6-181">10.10.1.10</span></span>
    
4. <span data-ttu-id="623e6-182">Créez la stratégie DNS qui connecte les sous-réseaux client aux étendues de zone appropriées afin de garantir la résolution DNS souhaitée.</span><span class="sxs-lookup"><span data-stu-id="623e6-182">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="623e6-183">À ce stade, les clients qui effectuent des requêtes DNS à partir du sous-réseau d’Amsterdam pour hybridvoice.adatum.biz renverront les adresses 192.168.1.45, 192.168.1.46, 192.168.1.47 et 192.168.1.48, tandis que les clients faisant le même formulaire de requête Seattle renverront 10.10.1.8, 10.10.1.9 et 10.10.1.10.</span><span class="sxs-lookup"><span data-stu-id="623e6-183">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="623e6-184">Si l’appliance CCE ne semble pas recevoir les paramètres mis à jour, vérifiez si l’appliance peut contacter le client via PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="623e6-184">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="623e6-185">Vous pouvez utiliser PowerShell à distance pour vérifier l’état du matériel avec Get-CsHybridPSTNAppliance ou utiliser PowerShell sur l’hôte CCE pour vérifier l’état avec Get-CcApplianceStatus.</span><span class="sxs-lookup"><span data-stu-id="623e6-185">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="623e6-186">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="623e6-186">See also</span></span>
<span data-ttu-id="623e6-187"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="623e6-187"><a name="Example"> </a></span></span>

[<span data-ttu-id="623e6-188">Planifier le contournement de média dans Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="623e6-188">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
