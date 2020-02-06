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
description: Apprenez-en davantage sur le déploiement de plusieurs sites RTC dans la version Cloud Connector.
ms.openlocfilehash: 98890bb3ffe53497c5e915acba5c073c4316f3b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799694"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="a5ba3-103">Déployer plusieurs sites dans Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="a5ba3-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="a5ba3-104">Apprenez-en davantage sur le déploiement de plusieurs sites RTC dans la version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a5ba3-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="a5ba3-p101">Cette rubrique décrit comment déployer plusieurs sites Réseau Téléphonique Commuté (RTC). Les sites sont déployés un par un de la même manière que pour le déploiement d’un site unique. Cette rubrique décrit les facteurs à prendre en compte et les différences entre les sites lors du déploiement de plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="a5ba3-p101">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites. Sites are deployed one at a time using the same steps as deploying a single site. This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="a5ba3-108">Sites multiples de Réseau Téléphonique Commuté (RTC)</span><span class="sxs-lookup"><span data-stu-id="a5ba3-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="a5ba3-109">Le code suivant montre un exemple de configuration pour le déploiement de Skype entreprise version Cloud Connector pour différents sites PSTN.</span><span class="sxs-lookup"><span data-stu-id="a5ba3-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="a5ba3-110">Assurez-vous que les paramètres de configuration sont corrects avant de commencer un déploiement.</span><span class="sxs-lookup"><span data-stu-id="a5ba3-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="a5ba3-111">Site RTC 1</span><span class="sxs-lookup"><span data-stu-id="a5ba3-111">PSTN Site 1</span></span>
  
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

<span data-ttu-id="a5ba3-112">Site RTC 2</span><span class="sxs-lookup"><span data-stu-id="a5ba3-112">PSTN Site 2</span></span>
  
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

<span data-ttu-id="a5ba3-113">Pour chaque site PSTN que vous voulez ajouter, suivez les étapes décrites dans [la procédure de déploiement d’un seul site dans le Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="a5ba3-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a5ba3-114">Le dossier partagé pour préparer la haute disponibilité est disponible par site PSTN.</span><span class="sxs-lookup"><span data-stu-id="a5ba3-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="a5ba3-115">Le dossier partagé **doit** être différent entre les sites PSTN.</span><span class="sxs-lookup"><span data-stu-id="a5ba3-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="a5ba3-116">N’utilisez pas le même dossier partagé pour plusieurs sites. ></span><span class="sxs-lookup"><span data-stu-id="a5ba3-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="a5ba3-117">Site unique à haute disponibilité comparé aux déploiements multi-sites</span><span class="sxs-lookup"><span data-stu-id="a5ba3-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="a5ba3-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="a5ba3-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="a5ba3-119">Le tableau suivant établit la liste des différences entre un site unique à haute disponibilité et un déploiement de plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="a5ba3-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="a5ba3-120">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="a5ba3-120">**Category**</span></span>|<span data-ttu-id="a5ba3-121">**Option**</span><span class="sxs-lookup"><span data-stu-id="a5ba3-121">**Item**</span></span>|<span data-ttu-id="a5ba3-122">**Site unique à haute disponibilité**</span><span class="sxs-lookup"><span data-stu-id="a5ba3-122">**Single-Site with HA**</span></span>|<span data-ttu-id="a5ba3-123">**Plusieurs sites**</span><span class="sxs-lookup"><span data-stu-id="a5ba3-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a5ba3-124">Configuration</span><span class="sxs-lookup"><span data-stu-id="a5ba3-124">Configure</span></span>  <br/> |<span data-ttu-id="a5ba3-125">Nom d’hôte de l’appareil</span><span class="sxs-lookup"><span data-stu-id="a5ba3-125">Appliance Host Name</span></span> <br/> |<span data-ttu-id="a5ba3-126">**Différent** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="a5ba3-126">**Different** across appliances</span></span> <br/> |<span data-ttu-id="a5ba3-127">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="a5ba3-127">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="a5ba3-128">Installation</span><span class="sxs-lookup"><span data-stu-id="a5ba3-128">Setup</span></span>  <br/> |<span data-ttu-id="a5ba3-129">Répertoire partagé</span><span class="sxs-lookup"><span data-stu-id="a5ba3-129">Shared folder</span></span>  <br/> |<span data-ttu-id="a5ba3-130">Nécessite le **même** dossier partagé sur plusieurs appareils</span><span class="sxs-lookup"><span data-stu-id="a5ba3-130">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="a5ba3-131">Nécessite un répertoire partagé **différent** pour toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="a5ba3-131">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="a5ba3-132">Configuration</span><span class="sxs-lookup"><span data-stu-id="a5ba3-132">Configure</span></span>  <br/> |<span data-ttu-id="a5ba3-133">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="a5ba3-133">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="a5ba3-134">Nécessite le **même** domaine pour toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="a5ba3-134">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="a5ba3-135">Nécessite le **même** domaine pour tous les sites RTC</span><span class="sxs-lookup"><span data-stu-id="a5ba3-135">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="a5ba3-136">Configuration</span><span class="sxs-lookup"><span data-stu-id="a5ba3-136">Configure</span></span>  <br/> |<span data-ttu-id="a5ba3-137">Domaines SIP</span><span class="sxs-lookup"><span data-stu-id="a5ba3-137">SIPDomains</span></span>  <br/> |<span data-ttu-id="a5ba3-138">Les noms de domaine et la commande doivent être **identiques** sur les appareils</span><span class="sxs-lookup"><span data-stu-id="a5ba3-138">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="a5ba3-139">Les noms de domaine et la commande doivent être **identiques** sur les sites RTC</span><span class="sxs-lookup"><span data-stu-id="a5ba3-139">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="a5ba3-140">Configuration</span><span class="sxs-lookup"><span data-stu-id="a5ba3-140">Configure</span></span>  <br/> |<span data-ttu-id="a5ba3-141">Nom du site</span><span class="sxs-lookup"><span data-stu-id="a5ba3-141">Site name</span></span>  <br/> |<span data-ttu-id="a5ba3-142">
            Le \*\*même\*\* nom de site pour toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="a5ba3-142">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="a5ba3-143">
            Nom de site \*\*différent\*\* pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="a5ba3-143">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="a5ba3-144">Configuration</span><span class="sxs-lookup"><span data-stu-id="a5ba3-144">Configure</span></span>  <br/> |<span data-ttu-id="a5ba3-145">Noms du serveur</span><span class="sxs-lookup"><span data-stu-id="a5ba3-145">Server names</span></span>  <br/> |<span data-ttu-id="a5ba3-146">**Différent** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="a5ba3-146">**Different** across appliances</span></span> <br/> |<span data-ttu-id="a5ba3-147">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="a5ba3-147">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="a5ba3-148">Configuration</span><span class="sxs-lookup"><span data-stu-id="a5ba3-148">Configure</span></span>  <br/> |<span data-ttu-id="a5ba3-149">FQDNs du pool interne</span><span class="sxs-lookup"><span data-stu-id="a5ba3-149">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="a5ba3-150">**Identique** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="a5ba3-150">**Same** across appliances</span></span> <br/> |<span data-ttu-id="a5ba3-151">
            Le \*\*même\*\* pour tous les sites RTC</span><span class="sxs-lookup"><span data-stu-id="a5ba3-151">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="a5ba3-152">Configuration</span><span class="sxs-lookup"><span data-stu-id="a5ba3-152">Configure</span></span>  <br/> |<span data-ttu-id="a5ba3-153">Adresses IP internes</span><span class="sxs-lookup"><span data-stu-id="a5ba3-153">Internal IPs</span></span>  <br/> |<span data-ttu-id="a5ba3-154">**Différent** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="a5ba3-154">**Different** across appliances</span></span> <br/> |<span data-ttu-id="a5ba3-155">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="a5ba3-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="a5ba3-156">Configuration</span><span class="sxs-lookup"><span data-stu-id="a5ba3-156">Configure</span></span>  <br/> |<span data-ttu-id="a5ba3-157">FQDN externe</span><span class="sxs-lookup"><span data-stu-id="a5ba3-157">External FQDN</span></span>  <br/> |<span data-ttu-id="a5ba3-158">**Identique** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="a5ba3-158">**Same** across appliances</span></span> <br/> |<span data-ttu-id="a5ba3-159">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="a5ba3-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="a5ba3-160">Configuration</span><span class="sxs-lookup"><span data-stu-id="a5ba3-160">Configure</span></span>  <br/> |<span data-ttu-id="a5ba3-161">Adresses IP externes</span><span class="sxs-lookup"><span data-stu-id="a5ba3-161">External IPs</span></span>  <br/> |<span data-ttu-id="a5ba3-162">**Différent** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="a5ba3-162">**Different** across appliances</span></span> <br/> |<span data-ttu-id="a5ba3-163">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="a5ba3-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="a5ba3-164">Configuration</span><span class="sxs-lookup"><span data-stu-id="a5ba3-164">Configure</span></span>  <br/> |<span data-ttu-id="a5ba3-165">Paramètres de la passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="a5ba3-165">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="a5ba3-166">**Identique** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="a5ba3-166">**Same** across appliances</span></span> <br/> |<span data-ttu-id="a5ba3-167">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="a5ba3-167">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="a5ba3-168">Configuration</span><span class="sxs-lookup"><span data-stu-id="a5ba3-168">Configure</span></span>  <br/> |<span data-ttu-id="a5ba3-169">Enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="a5ba3-169">DNS record</span></span>  <br/> |<span data-ttu-id="a5ba3-170">Ajouter des enregistrements avec les **mêmes** noms de domaine complets d’accès externe et **différentes** adresses IP</span><span class="sxs-lookup"><span data-stu-id="a5ba3-170">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="a5ba3-171">Ajout d’enregistrements avec des FQDN d'accès externe **différents** et des adresses IP **différentes**</span><span class="sxs-lookup"><span data-stu-id="a5ba3-171">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="a5ba3-172">Installation</span><span class="sxs-lookup"><span data-stu-id="a5ba3-172">Setup</span></span>  <br/> |<span data-ttu-id="a5ba3-173">Client hybride</span><span class="sxs-lookup"><span data-stu-id="a5ba3-173">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="a5ba3-174">Site RTC hybride défini</span><span class="sxs-lookup"><span data-stu-id="a5ba3-174">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="a5ba3-175">Destination de secours des pairs définie</span><span class="sxs-lookup"><span data-stu-id="a5ba3-175">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="a5ba3-176">Site RTC hybride défini</span><span class="sxs-lookup"><span data-stu-id="a5ba3-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="a5ba3-177">Destination de secours des pairs définie</span><span class="sxs-lookup"><span data-stu-id="a5ba3-177">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="a5ba3-178">Installation</span><span class="sxs-lookup"><span data-stu-id="a5ba3-178">Setup</span></span>  <br/> |<span data-ttu-id="a5ba3-179">Passerelle</span><span class="sxs-lookup"><span data-stu-id="a5ba3-179">Gateway</span></span>  <br/> |<span data-ttu-id="a5ba3-180">Mappage dans ce site de passerelle MS **M : N**</span><span class="sxs-lookup"><span data-stu-id="a5ba3-180">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="a5ba3-181">La ou les passerelle(s) RTC de chaque site RTC devrai(en)t uniquement être connectée(s) au(x) serveur(s) de médiation dans le même site</span><span class="sxs-lookup"><span data-stu-id="a5ba3-181">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="a5ba3-182">Installation</span><span class="sxs-lookup"><span data-stu-id="a5ba3-182">Setup</span></span>  <br/> |<span data-ttu-id="a5ba3-183">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="a5ba3-183">User</span></span>  <br/> |<span data-ttu-id="a5ba3-184">Paramètres RTC utilisateur défini</span><span class="sxs-lookup"><span data-stu-id="a5ba3-184">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="a5ba3-185">Paramètres RTC utilisateur défini</span><span class="sxs-lookup"><span data-stu-id="a5ba3-185">Set UserPSTNSettings</span></span>  <br/> |
   

