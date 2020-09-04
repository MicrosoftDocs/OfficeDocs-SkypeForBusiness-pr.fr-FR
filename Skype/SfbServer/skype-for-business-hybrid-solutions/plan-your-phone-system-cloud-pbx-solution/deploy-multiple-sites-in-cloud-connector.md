---
title: Déployer plusieurs sites dans Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Découvrez comment déployer plusieurs sites RTC dans la version Cloud Connector.
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358920"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="bf3ef-103">Déployer plusieurs sites dans Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="bf3ef-103">Deploy multiple sites in Cloud Connector</span></span>

> [!Important] 
> <span data-ttu-id="bf3ef-104">La version Cloud Connector sera déconnectée le 31 juillet 2021 avec Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="bf3ef-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="bf3ef-105">Une fois que votre organisation a effectué la mise à niveau vers Teams, Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="bf3ef-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="bf3ef-106">Découvrez comment déployer plusieurs sites RTC dans la version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="bf3ef-106">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="bf3ef-107">Cette section décrit comment déployer plusieurs sites RTC (réseau téléphonique commuté).</span><span class="sxs-lookup"><span data-stu-id="bf3ef-107">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="bf3ef-108">Les sites sont déployés l’un après l’autre en suivant les mêmes étapes que pour le déploiement d’un site unique.</span><span class="sxs-lookup"><span data-stu-id="bf3ef-108">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="bf3ef-109">Cette rubrique décrit les éléments à prendre en compte et les différences entre les sites dans un déploiement sur plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="bf3ef-109">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="bf3ef-110">Plusieurs sites RTC (réseau téléphonique commuté)</span><span class="sxs-lookup"><span data-stu-id="bf3ef-110">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="bf3ef-111">Voici un exemple de configuration pour déployer Skype entreprise, version Cloud Connector pour différents sites RTC.</span><span class="sxs-lookup"><span data-stu-id="bf3ef-111">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="bf3ef-112">Assurez-vous que vos paramètres de configuration sont corrects avant de démarrer un déploiement.</span><span class="sxs-lookup"><span data-stu-id="bf3ef-112">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="bf3ef-113">Site RTC 1</span><span class="sxs-lookup"><span data-stu-id="bf3ef-113">PSTN Site 1</span></span>
  
```console
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

<span data-ttu-id="bf3ef-114">Site PSTN 2</span><span class="sxs-lookup"><span data-stu-id="bf3ef-114">PSTN Site 2</span></span>
  
```console
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

<span data-ttu-id="bf3ef-115">Pour chaque site RTC que vous souhaitez ajouter, suivez les étapes de la procédure de [déploiement d’un seul site dans Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="bf3ef-115">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bf3ef-116">Le dossier partagé pour la préparation de la haute disponibilité (HA) est par site RTC.</span><span class="sxs-lookup"><span data-stu-id="bf3ef-116">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="bf3ef-117">Le dossier partagé **doit** être différent entre les sites RTC.</span><span class="sxs-lookup"><span data-stu-id="bf3ef-117">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="bf3ef-118">N’utilisez pas le même dossier partagé pour plusieurs sites. ></span><span class="sxs-lookup"><span data-stu-id="bf3ef-118">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="bf3ef-119">Site unique avec haute disponibilité (HA) comparé aux déploiements multisites</span><span class="sxs-lookup"><span data-stu-id="bf3ef-119">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="bf3ef-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="bf3ef-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="bf3ef-121">Le tableau suivant répertorie les différences entre un site unique avec prise en charge de la haute disponibilité et un déploiement sur plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="bf3ef-121">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="bf3ef-122">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="bf3ef-122">**Category**</span></span>|<span data-ttu-id="bf3ef-123">**Élément**</span><span class="sxs-lookup"><span data-stu-id="bf3ef-123">**Item**</span></span>|<span data-ttu-id="bf3ef-124">**Site unique avec haute disponibilité**</span><span class="sxs-lookup"><span data-stu-id="bf3ef-124">**Single-Site with HA**</span></span>|<span data-ttu-id="bf3ef-125">**Multisite**</span><span class="sxs-lookup"><span data-stu-id="bf3ef-125">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bf3ef-126">Configurer</span><span class="sxs-lookup"><span data-stu-id="bf3ef-126">Configure</span></span>  <br/> |<span data-ttu-id="bf3ef-127">Nom d’hôte de l’appliance</span><span class="sxs-lookup"><span data-stu-id="bf3ef-127">Appliance Host Name</span></span> <br/> |<span data-ttu-id="bf3ef-128">**Différentes** sur plusieurs appliances</span><span class="sxs-lookup"><span data-stu-id="bf3ef-128">**Different** across appliances</span></span> <br/> |<span data-ttu-id="bf3ef-129">**Différents** sur les sites RTC</span><span class="sxs-lookup"><span data-stu-id="bf3ef-129">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bf3ef-130">Configuration</span><span class="sxs-lookup"><span data-stu-id="bf3ef-130">Setup</span></span>  <br/> |<span data-ttu-id="bf3ef-131">Dossier partagé</span><span class="sxs-lookup"><span data-stu-id="bf3ef-131">Shared folder</span></span>  <br/> |<span data-ttu-id="bf3ef-132">Nécessite le **même** dossier partagé entre plusieurs appliances</span><span class="sxs-lookup"><span data-stu-id="bf3ef-132">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="bf3ef-133">Nécessite un dossier partagé **différent** sur plusieurs appliances</span><span class="sxs-lookup"><span data-stu-id="bf3ef-133">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="bf3ef-134">Configurer</span><span class="sxs-lookup"><span data-stu-id="bf3ef-134">Configure</span></span>  <br/> |<span data-ttu-id="bf3ef-135">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="bf3ef-135">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="bf3ef-136">Nécessite le **même** domaine pour toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="bf3ef-136">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="bf3ef-137">Nécessite le **même** domaine pour tous les sites RTC</span><span class="sxs-lookup"><span data-stu-id="bf3ef-137">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bf3ef-138">Configurer</span><span class="sxs-lookup"><span data-stu-id="bf3ef-138">Configure</span></span>  <br/> |<span data-ttu-id="bf3ef-139">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="bf3ef-139">SIPDomains</span></span>  <br/> |<span data-ttu-id="bf3ef-140">Les noms de domaine et l’ordre doivent être les **mêmes** pour toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="bf3ef-140">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="bf3ef-141">Les noms de domaine et l’ordre doivent être les **mêmes** pour tous les sites RTC</span><span class="sxs-lookup"><span data-stu-id="bf3ef-141">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bf3ef-142">Configurer</span><span class="sxs-lookup"><span data-stu-id="bf3ef-142">Configure</span></span>  <br/> |<span data-ttu-id="bf3ef-143">Nom du site</span><span class="sxs-lookup"><span data-stu-id="bf3ef-143">Site name</span></span>  <br/> |<span data-ttu-id="bf3ef-144">**Mêmes** Nom du site entre les appliances</span><span class="sxs-lookup"><span data-stu-id="bf3ef-144">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="bf3ef-145">**Différent** Nom du site sur les sites RTC</span><span class="sxs-lookup"><span data-stu-id="bf3ef-145">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bf3ef-146">Configurer</span><span class="sxs-lookup"><span data-stu-id="bf3ef-146">Configure</span></span>  <br/> |<span data-ttu-id="bf3ef-147">Noms des serveurs</span><span class="sxs-lookup"><span data-stu-id="bf3ef-147">Server names</span></span>  <br/> |<span data-ttu-id="bf3ef-148">**Différentes** sur plusieurs appliances</span><span class="sxs-lookup"><span data-stu-id="bf3ef-148">**Different** across appliances</span></span> <br/> |<span data-ttu-id="bf3ef-149">**Différents** sur les sites RTC</span><span class="sxs-lookup"><span data-stu-id="bf3ef-149">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bf3ef-150">Configurer</span><span class="sxs-lookup"><span data-stu-id="bf3ef-150">Configure</span></span>  <br/> |<span data-ttu-id="bf3ef-151">Noms de domaine complets du pool interne</span><span class="sxs-lookup"><span data-stu-id="bf3ef-151">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="bf3ef-152">**Identique** pour toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="bf3ef-152">**Same** across appliances</span></span> <br/> |<span data-ttu-id="bf3ef-153">**Identique** sur tous les sites PSTN</span><span class="sxs-lookup"><span data-stu-id="bf3ef-153">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bf3ef-154">Configurer</span><span class="sxs-lookup"><span data-stu-id="bf3ef-154">Configure</span></span>  <br/> |<span data-ttu-id="bf3ef-155">Adresses IP internes</span><span class="sxs-lookup"><span data-stu-id="bf3ef-155">Internal IPs</span></span>  <br/> |<span data-ttu-id="bf3ef-156">**Différentes** sur plusieurs appliances</span><span class="sxs-lookup"><span data-stu-id="bf3ef-156">**Different** across appliances</span></span> <br/> |<span data-ttu-id="bf3ef-157">**Différents** sur les sites RTC</span><span class="sxs-lookup"><span data-stu-id="bf3ef-157">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bf3ef-158">Configurer</span><span class="sxs-lookup"><span data-stu-id="bf3ef-158">Configure</span></span>  <br/> |<span data-ttu-id="bf3ef-159">Nom de domaine complet externe</span><span class="sxs-lookup"><span data-stu-id="bf3ef-159">External FQDN</span></span>  <br/> |<span data-ttu-id="bf3ef-160">**Identique** pour toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="bf3ef-160">**Same** across appliances</span></span> <br/> |<span data-ttu-id="bf3ef-161">**Différents** sur les sites RTC</span><span class="sxs-lookup"><span data-stu-id="bf3ef-161">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bf3ef-162">Configurer</span><span class="sxs-lookup"><span data-stu-id="bf3ef-162">Configure</span></span>  <br/> |<span data-ttu-id="bf3ef-163">Adresses IP externes</span><span class="sxs-lookup"><span data-stu-id="bf3ef-163">External IPs</span></span>  <br/> |<span data-ttu-id="bf3ef-164">**Différentes** sur plusieurs appliances</span><span class="sxs-lookup"><span data-stu-id="bf3ef-164">**Different** across appliances</span></span> <br/> |<span data-ttu-id="bf3ef-165">**Différents** sur les sites RTC</span><span class="sxs-lookup"><span data-stu-id="bf3ef-165">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bf3ef-166">Configurer</span><span class="sxs-lookup"><span data-stu-id="bf3ef-166">Configure</span></span>  <br/> |<span data-ttu-id="bf3ef-167">Paramètres RTC GW</span><span class="sxs-lookup"><span data-stu-id="bf3ef-167">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="bf3ef-168">**Identique** pour toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="bf3ef-168">**Same** across appliances</span></span> <br/> |<span data-ttu-id="bf3ef-169">**Différents** sur les sites RTC</span><span class="sxs-lookup"><span data-stu-id="bf3ef-169">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="bf3ef-170">Configurer</span><span class="sxs-lookup"><span data-stu-id="bf3ef-170">Configure</span></span>  <br/> |<span data-ttu-id="bf3ef-171">Enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="bf3ef-171">DNS record</span></span>  <br/> |<span data-ttu-id="bf3ef-172">Ajouter des enregistrements avec les **mêmes** noms de domaine complets d’accès externe et **différentes** adresses IP</span><span class="sxs-lookup"><span data-stu-id="bf3ef-172">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="bf3ef-173">Ajouter des enregistrements avec des noms de domaine complets d’accès externe **différents** et des adresses IP **différentes**</span><span class="sxs-lookup"><span data-stu-id="bf3ef-173">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="bf3ef-174">Configuration</span><span class="sxs-lookup"><span data-stu-id="bf3ef-174">Setup</span></span>  <br/> |<span data-ttu-id="bf3ef-175">Client hybride</span><span class="sxs-lookup"><span data-stu-id="bf3ef-175">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="bf3ef-176">Définir défini</span><span class="sxs-lookup"><span data-stu-id="bf3ef-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="bf3ef-177">Définir PeerDestination pour le secours</span><span class="sxs-lookup"><span data-stu-id="bf3ef-177">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="bf3ef-178">Définir défini</span><span class="sxs-lookup"><span data-stu-id="bf3ef-178">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="bf3ef-179">Définir PeerDestination pour le secours</span><span class="sxs-lookup"><span data-stu-id="bf3ef-179">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="bf3ef-180">Configuration</span><span class="sxs-lookup"><span data-stu-id="bf3ef-180">Setup</span></span>  <br/> |<span data-ttu-id="bf3ef-181">Passerelle</span><span class="sxs-lookup"><span data-stu-id="bf3ef-181">Gateway</span></span>  <br/> |<span data-ttu-id="bf3ef-182">Mappage MS GW **M :N** dans ce site</span><span class="sxs-lookup"><span data-stu-id="bf3ef-182">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="bf3ef-183">La ou les passerelles PSTN de chaque site PSTN doivent se connecter uniquement au (x) serveur (s) de médiation dans le même site</span><span class="sxs-lookup"><span data-stu-id="bf3ef-183">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="bf3ef-184">Configuration</span><span class="sxs-lookup"><span data-stu-id="bf3ef-184">Setup</span></span>  <br/> |<span data-ttu-id="bf3ef-185">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="bf3ef-185">User</span></span>  <br/> |<span data-ttu-id="bf3ef-186">Définir défini</span><span class="sxs-lookup"><span data-stu-id="bf3ef-186">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="bf3ef-187">Définir défini</span><span class="sxs-lookup"><span data-stu-id="bf3ef-187">Set UserPSTNSettings</span></span>  <br/> |
   

