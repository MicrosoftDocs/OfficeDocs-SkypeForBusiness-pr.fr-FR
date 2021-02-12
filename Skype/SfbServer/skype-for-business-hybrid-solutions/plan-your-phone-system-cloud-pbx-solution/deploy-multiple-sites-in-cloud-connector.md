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
description: Découvrez le déploiement de plusieurs sites PSTN dans Cloud Connector Edition.
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358920"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="f63ad-103">Déployer plusieurs sites dans Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="f63ad-103">Deploy multiple sites in Cloud Connector</span></span>

> [!Important] 
> <span data-ttu-id="f63ad-104">Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="f63ad-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="f63ad-105">Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams à l’aide du [routage direct.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="f63ad-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="f63ad-106">Découvrez le déploiement de plusieurs sites PSTN dans Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="f63ad-106">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="f63ad-107">Cette section décrit comment déployer plusieurs sites de réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="f63ad-107">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="f63ad-108">Les sites sont déployés un par un en utilisant les mêmes étapes que le déploiement d’un seul site.</span><span class="sxs-lookup"><span data-stu-id="f63ad-108">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="f63ad-109">Cette rubrique décrit les considérations et les différences entre les sites dans un déploiement sur plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="f63ad-109">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="f63ad-110">Plusieurs sites de réseau téléphonique commuté (PSTN)</span><span class="sxs-lookup"><span data-stu-id="f63ad-110">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="f63ad-111">Voici un exemple de configuration pour déployer Skype Entreprise, version Cloud Connector pour différents sites PSTN.</span><span class="sxs-lookup"><span data-stu-id="f63ad-111">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="f63ad-112">Assurez-vous que vos paramètres de configuration sont corrects avant de commencer un déploiement.</span><span class="sxs-lookup"><span data-stu-id="f63ad-112">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="f63ad-113">Site PSTN 1</span><span class="sxs-lookup"><span data-stu-id="f63ad-113">PSTN Site 1</span></span>
  
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

<span data-ttu-id="f63ad-114">Site PSTN 2</span><span class="sxs-lookup"><span data-stu-id="f63ad-114">PSTN Site 2</span></span>
  
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

<span data-ttu-id="f63ad-115">Pour chaque site PSTN que vous souhaitez ajouter, suivez les étapes de la procédure de déploiement d’un [site unique dans Cloud Connector.](deploy-a-single-site-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="f63ad-115">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f63ad-116">Le dossier partagé pour la préparation de la haute disponibilité (HA) est par site PSTN.</span><span class="sxs-lookup"><span data-stu-id="f63ad-116">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="f63ad-117">Le dossier partagé **doit être** différent entre les sites PSTN.</span><span class="sxs-lookup"><span data-stu-id="f63ad-117">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="f63ad-118">N’utilisez pas le même dossier partagé pour plusieurs sites.></span><span class="sxs-lookup"><span data-stu-id="f63ad-118">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="f63ad-119">Site unique avec haute disponibilité (HA) par rapport aux déploiements multisesses</span><span class="sxs-lookup"><span data-stu-id="f63ad-119">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="f63ad-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="f63ad-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="f63ad-121">Le tableau suivant répertorie les différences entre un site unique avec prise en charge de la ha et un déploiement sur plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="f63ad-121">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="f63ad-122">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="f63ad-122">**Category**</span></span>|<span data-ttu-id="f63ad-123">**Élément**</span><span class="sxs-lookup"><span data-stu-id="f63ad-123">**Item**</span></span>|<span data-ttu-id="f63ad-124">**Site unique avec ha**</span><span class="sxs-lookup"><span data-stu-id="f63ad-124">**Single-Site with HA**</span></span>|<span data-ttu-id="f63ad-125">**Multisesse**</span><span class="sxs-lookup"><span data-stu-id="f63ad-125">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f63ad-126">Configurer</span><span class="sxs-lookup"><span data-stu-id="f63ad-126">Configure</span></span>  <br/> |<span data-ttu-id="f63ad-127">Nom d’hôte de l’appliance</span><span class="sxs-lookup"><span data-stu-id="f63ad-127">Appliance Host Name</span></span> <br/> |<span data-ttu-id="f63ad-128">**Différents d’une** appliances à l’autre</span><span class="sxs-lookup"><span data-stu-id="f63ad-128">**Different** across appliances</span></span> <br/> |<span data-ttu-id="f63ad-129">**Différents sites** PSTN</span><span class="sxs-lookup"><span data-stu-id="f63ad-129">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f63ad-130">Configuration</span><span class="sxs-lookup"><span data-stu-id="f63ad-130">Setup</span></span>  <br/> |<span data-ttu-id="f63ad-131">Dossier partagé</span><span class="sxs-lookup"><span data-stu-id="f63ad-131">Shared folder</span></span>  <br/> |<span data-ttu-id="f63ad-132">Nécessite le **même dossier** partagé entre les appliances</span><span class="sxs-lookup"><span data-stu-id="f63ad-132">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="f63ad-133">Nécessite un **dossier partagé différent pour** toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="f63ad-133">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="f63ad-134">Configurer</span><span class="sxs-lookup"><span data-stu-id="f63ad-134">Configure</span></span>  <br/> |<span data-ttu-id="f63ad-135">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="f63ad-135">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="f63ad-136">Nécessite le **même domaine pour** toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="f63ad-136">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="f63ad-137">Nécessite le **même domaine** sur les sites PSTN</span><span class="sxs-lookup"><span data-stu-id="f63ad-137">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f63ad-138">Configurer</span><span class="sxs-lookup"><span data-stu-id="f63ad-138">Configure</span></span>  <br/> |<span data-ttu-id="f63ad-139">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="f63ad-139">SIPDomains</span></span>  <br/> |<span data-ttu-id="f63ad-140">Les noms de domaine et l’ordre doivent être **les mêmes pour toutes les** appliances</span><span class="sxs-lookup"><span data-stu-id="f63ad-140">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="f63ad-141">Les noms de domaine et l’ordre doivent être **les mêmes** sur les sites PSTN</span><span class="sxs-lookup"><span data-stu-id="f63ad-141">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f63ad-142">Configurer</span><span class="sxs-lookup"><span data-stu-id="f63ad-142">Configure</span></span>  <br/> |<span data-ttu-id="f63ad-143">Nom du site</span><span class="sxs-lookup"><span data-stu-id="f63ad-143">Site name</span></span>  <br/> |<span data-ttu-id="f63ad-144">**Identique** Nom du site sur les appliances</span><span class="sxs-lookup"><span data-stu-id="f63ad-144">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="f63ad-145">**Différent** Nom du site sur les sites PSTN</span><span class="sxs-lookup"><span data-stu-id="f63ad-145">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f63ad-146">Configurer</span><span class="sxs-lookup"><span data-stu-id="f63ad-146">Configure</span></span>  <br/> |<span data-ttu-id="f63ad-147">Noms de serveur</span><span class="sxs-lookup"><span data-stu-id="f63ad-147">Server names</span></span>  <br/> |<span data-ttu-id="f63ad-148">**Différents d’une** appliances à l’autre</span><span class="sxs-lookup"><span data-stu-id="f63ad-148">**Different** across appliances</span></span> <br/> |<span data-ttu-id="f63ad-149">**Différents sites** PSTN</span><span class="sxs-lookup"><span data-stu-id="f63ad-149">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f63ad-150">Configurer</span><span class="sxs-lookup"><span data-stu-id="f63ad-150">Configure</span></span>  <br/> |<span data-ttu-id="f63ad-151">FQDN du pool interne</span><span class="sxs-lookup"><span data-stu-id="f63ad-151">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="f63ad-152">**Identique pour** toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="f63ad-152">**Same** across appliances</span></span> <br/> |<span data-ttu-id="f63ad-153">**Identique sur** les sites PSTN</span><span class="sxs-lookup"><span data-stu-id="f63ad-153">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f63ad-154">Configurer</span><span class="sxs-lookup"><span data-stu-id="f63ad-154">Configure</span></span>  <br/> |<span data-ttu-id="f63ad-155">IPs internes</span><span class="sxs-lookup"><span data-stu-id="f63ad-155">Internal IPs</span></span>  <br/> |<span data-ttu-id="f63ad-156">**Différents d’une** appliances à l’autre</span><span class="sxs-lookup"><span data-stu-id="f63ad-156">**Different** across appliances</span></span> <br/> |<span data-ttu-id="f63ad-157">**Différents sites** PSTN</span><span class="sxs-lookup"><span data-stu-id="f63ad-157">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f63ad-158">Configurer</span><span class="sxs-lookup"><span data-stu-id="f63ad-158">Configure</span></span>  <br/> |<span data-ttu-id="f63ad-159">FQDN externe</span><span class="sxs-lookup"><span data-stu-id="f63ad-159">External FQDN</span></span>  <br/> |<span data-ttu-id="f63ad-160">**Identique pour** toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="f63ad-160">**Same** across appliances</span></span> <br/> |<span data-ttu-id="f63ad-161">**Différents sites** PSTN</span><span class="sxs-lookup"><span data-stu-id="f63ad-161">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f63ad-162">Configurer</span><span class="sxs-lookup"><span data-stu-id="f63ad-162">Configure</span></span>  <br/> |<span data-ttu-id="f63ad-163">Fournisseurs d’IP externes</span><span class="sxs-lookup"><span data-stu-id="f63ad-163">External IPs</span></span>  <br/> |<span data-ttu-id="f63ad-164">**Différents d’une** appliances à l’autre</span><span class="sxs-lookup"><span data-stu-id="f63ad-164">**Different** across appliances</span></span> <br/> |<span data-ttu-id="f63ad-165">**Différents sites** PSTN</span><span class="sxs-lookup"><span data-stu-id="f63ad-165">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f63ad-166">Configurer</span><span class="sxs-lookup"><span data-stu-id="f63ad-166">Configure</span></span>  <br/> |<span data-ttu-id="f63ad-167">Paramètres PSTN GW</span><span class="sxs-lookup"><span data-stu-id="f63ad-167">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="f63ad-168">**Identique pour** toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="f63ad-168">**Same** across appliances</span></span> <br/> |<span data-ttu-id="f63ad-169">**Différents sites** PSTN</span><span class="sxs-lookup"><span data-stu-id="f63ad-169">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f63ad-170">Configurer</span><span class="sxs-lookup"><span data-stu-id="f63ad-170">Configure</span></span>  <br/> |<span data-ttu-id="f63ad-171">Enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="f63ad-171">DNS record</span></span>  <br/> |<span data-ttu-id="f63ad-172">Ajouter des enregistrements avec les **mêmes FQDN** d’accès externe et différentes **adresses** IP</span><span class="sxs-lookup"><span data-stu-id="f63ad-172">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="f63ad-173">Ajouter des enregistrements avec **différents** FQDN d’accès externe et **différentes adresses** IP</span><span class="sxs-lookup"><span data-stu-id="f63ad-173">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="f63ad-174">Configuration</span><span class="sxs-lookup"><span data-stu-id="f63ad-174">Setup</span></span>  <br/> |<span data-ttu-id="f63ad-175">Client hybride</span><span class="sxs-lookup"><span data-stu-id="f63ad-175">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="f63ad-176">Définir HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="f63ad-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="f63ad-177">Définir PeerDestination pour le retour</span><span class="sxs-lookup"><span data-stu-id="f63ad-177">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="f63ad-178">Définir HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="f63ad-178">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="f63ad-179">Définir PeerDestination pour le retour</span><span class="sxs-lookup"><span data-stu-id="f63ad-179">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="f63ad-180">Configuration</span><span class="sxs-lookup"><span data-stu-id="f63ad-180">Setup</span></span>  <br/> |<span data-ttu-id="f63ad-181">Passerelle</span><span class="sxs-lookup"><span data-stu-id="f63ad-181">Gateway</span></span>  <br/> |<span data-ttu-id="f63ad-182">Mappage **M:N MS** GW dans ce site</span><span class="sxs-lookup"><span data-stu-id="f63ad-182">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="f63ad-183">Les passerelles PSTN de chaque site PSTN doivent uniquement se connecter au(s) serveur(s) de médiation du même site</span><span class="sxs-lookup"><span data-stu-id="f63ad-183">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="f63ad-184">Configuration</span><span class="sxs-lookup"><span data-stu-id="f63ad-184">Setup</span></span>  <br/> |<span data-ttu-id="f63ad-185">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="f63ad-185">User</span></span>  <br/> |<span data-ttu-id="f63ad-186">Définir UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="f63ad-186">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="f63ad-187">Définir UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="f63ad-187">Set UserPSTNSettings</span></span>  <br/> |
   

