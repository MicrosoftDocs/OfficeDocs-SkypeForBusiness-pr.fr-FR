---
title: Déployer plusieurs sites dans Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: En savoir plus sur le déploiement de plusieurs sites PSTN dans le nuage connecteur Edition.
ms.openlocfilehash: 194eaf0b68489b37a5ab1fc2d5d501177edd0b35
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32227900"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="27331-103">Déployer plusieurs sites dans Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="27331-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="27331-104">En savoir plus sur le déploiement de plusieurs sites PSTN dans le nuage connecteur Edition.</span><span class="sxs-lookup"><span data-stu-id="27331-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="27331-p101">Cette rubrique décrit comment déployer plusieurs sites Réseau Téléphonique Commuté (RTC). Les sites sont déployés un par un de la même manière que pour le déploiement d’un site unique. Cette rubrique décrit les facteurs à prendre en compte et les différences entre les sites lors du déploiement de plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="27331-p101">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites. Sites are deployed one at a time using the same steps as deploying a single site. This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="27331-108">Sites multiples de Réseau Téléphonique Commuté (RTC)</span><span class="sxs-lookup"><span data-stu-id="27331-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="27331-109">Voici un exemple de configuration pour déployer Skype pour édition dans le nuage connecteur pour différents sites PSTN.</span><span class="sxs-lookup"><span data-stu-id="27331-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="27331-110">Assurez-vous que les paramètres de configuration sont corrects avant de commencer un déploiement.</span><span class="sxs-lookup"><span data-stu-id="27331-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="27331-111">Site RTC 1</span><span class="sxs-lookup"><span data-stu-id="27331-111">PSTN Site 1</span></span>
  
```
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

<span data-ttu-id="27331-112">Site RTC 2</span><span class="sxs-lookup"><span data-stu-id="27331-112">PSTN Site 2</span></span>
  
```
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

<span data-ttu-id="27331-113">Pour chaque site PSTN que vous souhaitez ajouter, suivez les étapes de [déploiement d’un seul site dans le nuage connecteur](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="27331-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="27331-114">Le dossier partagé pour la préparation de la haute disponibilité est par site PSTN.</span><span class="sxs-lookup"><span data-stu-id="27331-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="27331-115">Le dossier partagé **doit** être différente pour les sites PSTN.</span><span class="sxs-lookup"><span data-stu-id="27331-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="27331-116">N’utilisez pas le même dossier partagé pour plusieurs sites.></span><span class="sxs-lookup"><span data-stu-id="27331-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="27331-117">Site unique à haute disponibilité comparé aux déploiements multi-sites</span><span class="sxs-lookup"><span data-stu-id="27331-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="27331-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="27331-118"></span></span>

<span data-ttu-id="27331-119">Le tableau suivant établit la liste des différences entre un site unique à haute disponibilité et un déploiement de plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="27331-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="27331-120">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="27331-120">**Category**</span></span>|<span data-ttu-id="27331-121">**Option**</span><span class="sxs-lookup"><span data-stu-id="27331-121">**Item**</span></span>|<span data-ttu-id="27331-122">**Site unique à haute disponibilité**</span><span class="sxs-lookup"><span data-stu-id="27331-122">**Single-Site with HA**</span></span>|<span data-ttu-id="27331-123">**Plusieurs sites**</span><span class="sxs-lookup"><span data-stu-id="27331-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="27331-124">Configuration</span><span class="sxs-lookup"><span data-stu-id="27331-124">Configure</span></span>  <br/> |<span data-ttu-id="27331-125">Nom de l’application hôte</span><span class="sxs-lookup"><span data-stu-id="27331-125">Appliance Host Name</span></span> <br/> |<span data-ttu-id="27331-126">**Différent** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="27331-126">**Different** across appliances</span></span> <br/> |<span data-ttu-id="27331-127">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="27331-127">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="27331-128">Installation</span><span class="sxs-lookup"><span data-stu-id="27331-128">Setup</span></span>  <br/> |<span data-ttu-id="27331-129">Répertoire partagé</span><span class="sxs-lookup"><span data-stu-id="27331-129">Shared folder</span></span>  <br/> |<span data-ttu-id="27331-130">Requiert le **même** dossier partagé sur appliances</span><span class="sxs-lookup"><span data-stu-id="27331-130">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="27331-131">Nécessite un répertoire partagé **différent** pour toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="27331-131">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="27331-132">Configuration</span><span class="sxs-lookup"><span data-stu-id="27331-132">Configure</span></span>  <br/> |<span data-ttu-id="27331-133">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="27331-133">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="27331-134">Nécessite le **même** domaine pour toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="27331-134">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="27331-135">Nécessite le **même** domaine pour tous les sites RTC</span><span class="sxs-lookup"><span data-stu-id="27331-135">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="27331-136">Configuration</span><span class="sxs-lookup"><span data-stu-id="27331-136">Configure</span></span>  <br/> |<span data-ttu-id="27331-137">Domaines SIP</span><span class="sxs-lookup"><span data-stu-id="27331-137">SIPDomains</span></span>  <br/> |<span data-ttu-id="27331-138">Ordre et les noms de domaine doivent être le **même** sur des appareils</span><span class="sxs-lookup"><span data-stu-id="27331-138">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="27331-139">Ordre et les noms de domaine doivent être le **même** entre les sites PSTN</span><span class="sxs-lookup"><span data-stu-id="27331-139">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="27331-140">Configuration</span><span class="sxs-lookup"><span data-stu-id="27331-140">Configure</span></span>  <br/> |<span data-ttu-id="27331-141">Nom du site</span><span class="sxs-lookup"><span data-stu-id="27331-141">Site name</span></span>  <br/> |<span data-ttu-id="27331-142">
            Le \*\*même\*\* nom de site pour toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="27331-142">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="27331-143">
            Nom de site \*\*différent\*\* pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="27331-143">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="27331-144">Configuration</span><span class="sxs-lookup"><span data-stu-id="27331-144">Configure</span></span>  <br/> |<span data-ttu-id="27331-145">Noms du serveur</span><span class="sxs-lookup"><span data-stu-id="27331-145">Server names</span></span>  <br/> |<span data-ttu-id="27331-146">**Différent** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="27331-146">**Different** across appliances</span></span> <br/> |<span data-ttu-id="27331-147">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="27331-147">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="27331-148">Configuration</span><span class="sxs-lookup"><span data-stu-id="27331-148">Configure</span></span>  <br/> |<span data-ttu-id="27331-149">FQDNs du pool interne</span><span class="sxs-lookup"><span data-stu-id="27331-149">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="27331-150">**Identique** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="27331-150">**Same** across appliances</span></span> <br/> |<span data-ttu-id="27331-151">
            Le \*\*même\*\* pour tous les sites RTC</span><span class="sxs-lookup"><span data-stu-id="27331-151">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="27331-152">Configuration</span><span class="sxs-lookup"><span data-stu-id="27331-152">Configure</span></span>  <br/> |<span data-ttu-id="27331-153">Adresses IP internes</span><span class="sxs-lookup"><span data-stu-id="27331-153">Internal IPs</span></span>  <br/> |<span data-ttu-id="27331-154">**Différent** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="27331-154">**Different** across appliances</span></span> <br/> |<span data-ttu-id="27331-155">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="27331-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="27331-156">Configuration</span><span class="sxs-lookup"><span data-stu-id="27331-156">Configure</span></span>  <br/> |<span data-ttu-id="27331-157">FQDN externe</span><span class="sxs-lookup"><span data-stu-id="27331-157">External FQDN</span></span>  <br/> |<span data-ttu-id="27331-158">**Identique** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="27331-158">**Same** across appliances</span></span> <br/> |<span data-ttu-id="27331-159">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="27331-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="27331-160">Configuration</span><span class="sxs-lookup"><span data-stu-id="27331-160">Configure</span></span>  <br/> |<span data-ttu-id="27331-161">Adresses IP externes</span><span class="sxs-lookup"><span data-stu-id="27331-161">External IPs</span></span>  <br/> |<span data-ttu-id="27331-162">**Différent** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="27331-162">**Different** across appliances</span></span> <br/> |<span data-ttu-id="27331-163">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="27331-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="27331-164">Configuration</span><span class="sxs-lookup"><span data-stu-id="27331-164">Configure</span></span>  <br/> |<span data-ttu-id="27331-165">Paramètres de la passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="27331-165">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="27331-166">**Identique** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="27331-166">**Same** across appliances</span></span> <br/> |<span data-ttu-id="27331-167">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="27331-167">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="27331-168">Configuration</span><span class="sxs-lookup"><span data-stu-id="27331-168">Configure</span></span>  <br/> |<span data-ttu-id="27331-169">Enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="27331-169">DNS record</span></span>  <br/> |<span data-ttu-id="27331-170">Ajouter des enregistrements avec le **même** FQDN de l’accès externe et des adresses IP **différentes**</span><span class="sxs-lookup"><span data-stu-id="27331-170">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="27331-171">Ajout d’enregistrements avec des FQDN d'accès externe **différents** et des adresses IP **différentes**</span><span class="sxs-lookup"><span data-stu-id="27331-171">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="27331-172">Installation</span><span class="sxs-lookup"><span data-stu-id="27331-172">Setup</span></span>  <br/> |<span data-ttu-id="27331-173">Client hybride</span><span class="sxs-lookup"><span data-stu-id="27331-173">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="27331-174">Site RTC hybride défini</span><span class="sxs-lookup"><span data-stu-id="27331-174">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="27331-175">Destination de secours des pairs définie</span><span class="sxs-lookup"><span data-stu-id="27331-175">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="27331-176">Site RTC hybride défini</span><span class="sxs-lookup"><span data-stu-id="27331-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="27331-177">Destination de secours des pairs définie</span><span class="sxs-lookup"><span data-stu-id="27331-177">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="27331-178">Installation</span><span class="sxs-lookup"><span data-stu-id="27331-178">Setup</span></span>  <br/> |<span data-ttu-id="27331-179">Passerelle</span><span class="sxs-lookup"><span data-stu-id="27331-179">Gateway</span></span>  <br/> |<span data-ttu-id="27331-180">Mappage dans ce site de passerelle MS **M : N**</span><span class="sxs-lookup"><span data-stu-id="27331-180">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="27331-181">La ou les passerelle(s) RTC de chaque site RTC devrai(en)t uniquement être connectée(s) au(x) serveur(s) de médiation dans le même site</span><span class="sxs-lookup"><span data-stu-id="27331-181">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="27331-182">Installation</span><span class="sxs-lookup"><span data-stu-id="27331-182">Setup</span></span>  <br/> |<span data-ttu-id="27331-183">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="27331-183">User</span></span>  <br/> |<span data-ttu-id="27331-184">Paramètres RTC utilisateur défini</span><span class="sxs-lookup"><span data-stu-id="27331-184">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="27331-185">Paramètres RTC utilisateur défini</span><span class="sxs-lookup"><span data-stu-id="27331-185">Set UserPSTNSettings</span></span>  <br/> |
   

