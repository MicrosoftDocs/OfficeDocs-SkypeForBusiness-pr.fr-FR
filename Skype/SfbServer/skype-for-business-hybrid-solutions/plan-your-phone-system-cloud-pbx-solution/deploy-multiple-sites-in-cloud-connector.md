---
title: Déployer plusieurs sites dans Cloud Connector
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
ms.openlocfilehash: b6d4c489136f038a5d4dbe7188958ef60e4a5aed
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295712"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="9357b-103">Déployer plusieurs sites dans Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="9357b-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="9357b-104">En savoir plus sur le déploiement de plusieurs sites PSTN dans le nuage connecteur Edition.</span><span class="sxs-lookup"><span data-stu-id="9357b-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="9357b-p101">Cette rubrique décrit comment déployer plusieurs sites Réseau Téléphonique Commuté (RTC). Les sites sont déployés un par un de la même manière que pour le déploiement d’un site unique. Cette rubrique décrit les facteurs à prendre en compte et les différences entre les sites lors du déploiement de plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="9357b-p101">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites. Sites are deployed one at a time using the same steps as deploying a single site. This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="9357b-108">Sites multiples de Réseau Téléphonique Commuté (RTC)</span><span class="sxs-lookup"><span data-stu-id="9357b-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="9357b-109">Voici un exemple de configuration pour déployer Skype pour édition dans le nuage connecteur pour différents sites PSTN.</span><span class="sxs-lookup"><span data-stu-id="9357b-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="9357b-110">Assurez-vous que les paramètres de configuration sont corrects avant de commencer un déploiement.</span><span class="sxs-lookup"><span data-stu-id="9357b-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="9357b-111">Site RTC 1</span><span class="sxs-lookup"><span data-stu-id="9357b-111">PSTN Site 1</span></span>
  
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

<span data-ttu-id="9357b-112">Site RTC 2</span><span class="sxs-lookup"><span data-stu-id="9357b-112">PSTN Site 2</span></span>
  
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

<span data-ttu-id="9357b-113">Pour chaque site PSTN que vous souhaitez ajouter, suivez les étapes de [déploiement d’un seul site dans le nuage connecteur](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="9357b-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9357b-114">Le dossier partagé pour la préparation de la haute disponibilité est par site PSTN.</span><span class="sxs-lookup"><span data-stu-id="9357b-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="9357b-115">Le dossier partagé **doit** être différente pour les sites PSTN.</span><span class="sxs-lookup"><span data-stu-id="9357b-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="9357b-116">N’utilisez pas le même dossier partagé pour plusieurs sites. ></span><span class="sxs-lookup"><span data-stu-id="9357b-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="9357b-117">Site unique à haute disponibilité comparé aux déploiements multi-sites</span><span class="sxs-lookup"><span data-stu-id="9357b-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="9357b-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="9357b-118"></span></span>

<span data-ttu-id="9357b-119">Le tableau suivant établit la liste des différences entre un site unique à haute disponibilité et un déploiement de plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="9357b-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="9357b-120">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="9357b-120">**Category**</span></span>|<span data-ttu-id="9357b-121">**Option**</span><span class="sxs-lookup"><span data-stu-id="9357b-121">**Item**</span></span>|<span data-ttu-id="9357b-122">**Site unique à haute disponibilité**</span><span class="sxs-lookup"><span data-stu-id="9357b-122">**Single-Site with HA**</span></span>|<span data-ttu-id="9357b-123">**Plusieurs sites**</span><span class="sxs-lookup"><span data-stu-id="9357b-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9357b-124">Installation</span><span class="sxs-lookup"><span data-stu-id="9357b-124">Setup</span></span>  <br/> |<span data-ttu-id="9357b-125">Répertoire partagé</span><span class="sxs-lookup"><span data-stu-id="9357b-125">Shared folder</span></span>  <br/> |<span data-ttu-id="9357b-126">Requiert le **même** dossier partagé sur appliances</span><span class="sxs-lookup"><span data-stu-id="9357b-126">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="9357b-127">Nécessite un répertoire partagé **différent** pour toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="9357b-127">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="9357b-128">Configuration</span><span class="sxs-lookup"><span data-stu-id="9357b-128">Configure</span></span>  <br/> |<span data-ttu-id="9357b-129">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="9357b-129">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="9357b-130">Nécessite le **même** domaine pour toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="9357b-130">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="9357b-131">Nécessite le **même** domaine pour tous les sites RTC</span><span class="sxs-lookup"><span data-stu-id="9357b-131">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="9357b-132">Configuration</span><span class="sxs-lookup"><span data-stu-id="9357b-132">Configure</span></span>  <br/> |<span data-ttu-id="9357b-133">Domaines SIP</span><span class="sxs-lookup"><span data-stu-id="9357b-133">SIPDomains</span></span>  <br/> |<span data-ttu-id="9357b-134">Ordre et les noms de domaine doivent être le **même** sur des appareils</span><span class="sxs-lookup"><span data-stu-id="9357b-134">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="9357b-135">Ordre et les noms de domaine doivent être le **même** entre les sites PSTN</span><span class="sxs-lookup"><span data-stu-id="9357b-135">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="9357b-136">Configuration</span><span class="sxs-lookup"><span data-stu-id="9357b-136">Configure</span></span>  <br/> |<span data-ttu-id="9357b-137">Nom du site</span><span class="sxs-lookup"><span data-stu-id="9357b-137">Site name</span></span>  <br/> |<span data-ttu-id="9357b-138">
            Le \*\*même\*\* nom de site pour toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="9357b-138">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="9357b-139">
            Nom de site \*\*différent\*\* pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="9357b-139">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="9357b-140">Configuration</span><span class="sxs-lookup"><span data-stu-id="9357b-140">Configure</span></span>  <br/> |<span data-ttu-id="9357b-141">Noms du serveur</span><span class="sxs-lookup"><span data-stu-id="9357b-141">Server names</span></span>  <br/> |<span data-ttu-id="9357b-142">**Différent** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="9357b-142">**Different** across appliances</span></span> <br/> |<span data-ttu-id="9357b-143">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="9357b-143">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="9357b-144">Configuration</span><span class="sxs-lookup"><span data-stu-id="9357b-144">Configure</span></span>  <br/> |<span data-ttu-id="9357b-145">FQDNs du pool interne</span><span class="sxs-lookup"><span data-stu-id="9357b-145">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="9357b-146">**Identique** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="9357b-146">**Same** across appliances</span></span> <br/> |<span data-ttu-id="9357b-147">
            Le \*\*même\*\* pour tous les sites RTC</span><span class="sxs-lookup"><span data-stu-id="9357b-147">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="9357b-148">Configuration</span><span class="sxs-lookup"><span data-stu-id="9357b-148">Configure</span></span>  <br/> |<span data-ttu-id="9357b-149">Adresses IP internes</span><span class="sxs-lookup"><span data-stu-id="9357b-149">Internal IPs</span></span>  <br/> |<span data-ttu-id="9357b-150">**Différent** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="9357b-150">**Different** across appliances</span></span> <br/> |<span data-ttu-id="9357b-151">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="9357b-151">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="9357b-152">Configuration</span><span class="sxs-lookup"><span data-stu-id="9357b-152">Configure</span></span>  <br/> |<span data-ttu-id="9357b-153">FQDN externe</span><span class="sxs-lookup"><span data-stu-id="9357b-153">External FQDN</span></span>  <br/> |<span data-ttu-id="9357b-154">**Identique** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="9357b-154">**Same** across appliances</span></span> <br/> |<span data-ttu-id="9357b-155">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="9357b-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="9357b-156">Configuration</span><span class="sxs-lookup"><span data-stu-id="9357b-156">Configure</span></span>  <br/> |<span data-ttu-id="9357b-157">Adresses IP externes</span><span class="sxs-lookup"><span data-stu-id="9357b-157">External IPs</span></span>  <br/> |<span data-ttu-id="9357b-158">**Différent** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="9357b-158">**Different** across appliances</span></span> <br/> |<span data-ttu-id="9357b-159">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="9357b-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="9357b-160">Configuration</span><span class="sxs-lookup"><span data-stu-id="9357b-160">Configure</span></span>  <br/> |<span data-ttu-id="9357b-161">Paramètres de la passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="9357b-161">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="9357b-162">**Identique** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="9357b-162">**Same** across appliances</span></span> <br/> |<span data-ttu-id="9357b-163">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="9357b-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="9357b-164">Configuration</span><span class="sxs-lookup"><span data-stu-id="9357b-164">Configure</span></span>  <br/> |<span data-ttu-id="9357b-165">Enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="9357b-165">DNS record</span></span>  <br/> |<span data-ttu-id="9357b-166">Ajouter des enregistrements avec le **même** FQDN de l’accès externe et des adresses IP **différentes**</span><span class="sxs-lookup"><span data-stu-id="9357b-166">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="9357b-167">Ajout d’enregistrements avec des FQDN d'accès externe **différents** et des adresses IP **différentes**</span><span class="sxs-lookup"><span data-stu-id="9357b-167">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="9357b-168">Installation</span><span class="sxs-lookup"><span data-stu-id="9357b-168">Setup</span></span>  <br/> |<span data-ttu-id="9357b-169">Client hybride</span><span class="sxs-lookup"><span data-stu-id="9357b-169">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="9357b-170">Site RTC hybride défini</span><span class="sxs-lookup"><span data-stu-id="9357b-170">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="9357b-171">Destination de secours des pairs définie</span><span class="sxs-lookup"><span data-stu-id="9357b-171">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="9357b-172">Site RTC hybride défini</span><span class="sxs-lookup"><span data-stu-id="9357b-172">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="9357b-173">Destination de secours des pairs définie</span><span class="sxs-lookup"><span data-stu-id="9357b-173">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="9357b-174">Installation</span><span class="sxs-lookup"><span data-stu-id="9357b-174">Setup</span></span>  <br/> |<span data-ttu-id="9357b-175">Passerelle</span><span class="sxs-lookup"><span data-stu-id="9357b-175">Gateway</span></span>  <br/> |<span data-ttu-id="9357b-176">Mappage dans ce site de passerelle MS **M : N**</span><span class="sxs-lookup"><span data-stu-id="9357b-176">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="9357b-177">La ou les passerelle(s) RTC de chaque site RTC devrai(en)t uniquement être connectée(s) au(x) serveur(s) de médiation dans le même site</span><span class="sxs-lookup"><span data-stu-id="9357b-177">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="9357b-178">Installation</span><span class="sxs-lookup"><span data-stu-id="9357b-178">Setup</span></span>  <br/> |<span data-ttu-id="9357b-179">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="9357b-179">User</span></span>  <br/> |<span data-ttu-id="9357b-180">Paramètres RTC utilisateur défini</span><span class="sxs-lookup"><span data-stu-id="9357b-180">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="9357b-181">Paramètres RTC utilisateur défini</span><span class="sxs-lookup"><span data-stu-id="9357b-181">Set UserPSTNSettings</span></span>  <br/> |
   

