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
ms.openlocfilehash: 1276d436a05e5151bdc90c19bbf41b8e90d913bf
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887633"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="eca92-103">Déployer plusieurs sites dans Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="eca92-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="eca92-104">Apprenez-en davantage sur le déploiement de plusieurs sites RTC dans la version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="eca92-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="eca92-p101">Cette rubrique décrit comment déployer plusieurs sites Réseau Téléphonique Commuté (RTC). Les sites sont déployés un par un de la même manière que pour le déploiement d’un site unique. Cette rubrique décrit les facteurs à prendre en compte et les différences entre les sites lors du déploiement de plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="eca92-p101">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites. Sites are deployed one at a time using the same steps as deploying a single site. This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="eca92-108">Sites multiples de Réseau Téléphonique Commuté (RTC)</span><span class="sxs-lookup"><span data-stu-id="eca92-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="eca92-109">Le code suivant montre un exemple de configuration pour le déploiement de Skype entreprise version Cloud Connector pour différents sites PSTN.</span><span class="sxs-lookup"><span data-stu-id="eca92-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="eca92-110">Assurez-vous que les paramètres de configuration sont corrects avant de commencer un déploiement.</span><span class="sxs-lookup"><span data-stu-id="eca92-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="eca92-111">Site RTC 1</span><span class="sxs-lookup"><span data-stu-id="eca92-111">PSTN Site 1</span></span>
  
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

<span data-ttu-id="eca92-112">Site RTC 2</span><span class="sxs-lookup"><span data-stu-id="eca92-112">PSTN Site 2</span></span>
  
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

<span data-ttu-id="eca92-113">Pour chaque site PSTN que vous voulez ajouter, suivez les étapes décrites dans [la procédure de déploiement d’un seul site dans le Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="eca92-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="eca92-114">Le dossier partagé pour préparer la haute disponibilité est disponible par site PSTN.</span><span class="sxs-lookup"><span data-stu-id="eca92-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="eca92-115">Le dossier partagé **doit** être différent entre les sites PSTN.</span><span class="sxs-lookup"><span data-stu-id="eca92-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="eca92-116">N’utilisez pas le même dossier partagé pour plusieurs sites. ></span><span class="sxs-lookup"><span data-stu-id="eca92-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="eca92-117">Site unique à haute disponibilité comparé aux déploiements multi-sites</span><span class="sxs-lookup"><span data-stu-id="eca92-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="eca92-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="eca92-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="eca92-119">Le tableau suivant établit la liste des différences entre un site unique à haute disponibilité et un déploiement de plusieurs sites.</span><span class="sxs-lookup"><span data-stu-id="eca92-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="eca92-120">**Catégorie**</span><span class="sxs-lookup"><span data-stu-id="eca92-120">**Category**</span></span>|<span data-ttu-id="eca92-121">**Option**</span><span class="sxs-lookup"><span data-stu-id="eca92-121">**Item**</span></span>|<span data-ttu-id="eca92-122">**Site unique à haute disponibilité**</span><span class="sxs-lookup"><span data-stu-id="eca92-122">**Single-Site with HA**</span></span>|<span data-ttu-id="eca92-123">**Plusieurs sites**</span><span class="sxs-lookup"><span data-stu-id="eca92-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eca92-124">Configuration</span><span class="sxs-lookup"><span data-stu-id="eca92-124">Configure</span></span>  <br/> |<span data-ttu-id="eca92-125">Nom d’hôte de l’appareil</span><span class="sxs-lookup"><span data-stu-id="eca92-125">Appliance Host Name</span></span> <br/> |<span data-ttu-id="eca92-126">**Différent** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="eca92-126">**Different** across appliances</span></span> <br/> |<span data-ttu-id="eca92-127">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="eca92-127">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="eca92-128">Installation</span><span class="sxs-lookup"><span data-stu-id="eca92-128">Setup</span></span>  <br/> |<span data-ttu-id="eca92-129">Répertoire partagé</span><span class="sxs-lookup"><span data-stu-id="eca92-129">Shared folder</span></span>  <br/> |<span data-ttu-id="eca92-130">Nécessite le **même** dossier partagé sur plusieurs appareils</span><span class="sxs-lookup"><span data-stu-id="eca92-130">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="eca92-131">Nécessite un répertoire partagé **différent** pour toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="eca92-131">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="eca92-132">Configuration</span><span class="sxs-lookup"><span data-stu-id="eca92-132">Configure</span></span>  <br/> |<span data-ttu-id="eca92-133">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="eca92-133">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="eca92-134">Nécessite le **même** domaine pour toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="eca92-134">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="eca92-135">Nécessite le **même** domaine pour tous les sites RTC</span><span class="sxs-lookup"><span data-stu-id="eca92-135">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="eca92-136">Configuration</span><span class="sxs-lookup"><span data-stu-id="eca92-136">Configure</span></span>  <br/> |<span data-ttu-id="eca92-137">Domaines SIP</span><span class="sxs-lookup"><span data-stu-id="eca92-137">SIPDomains</span></span>  <br/> |<span data-ttu-id="eca92-138">Les noms de domaine et la commande doivent être **identiques** sur les appareils</span><span class="sxs-lookup"><span data-stu-id="eca92-138">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="eca92-139">Les noms de domaine et la commande doivent être **identiques** sur les sites RTC</span><span class="sxs-lookup"><span data-stu-id="eca92-139">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="eca92-140">Configuration</span><span class="sxs-lookup"><span data-stu-id="eca92-140">Configure</span></span>  <br/> |<span data-ttu-id="eca92-141">Nom du site</span><span class="sxs-lookup"><span data-stu-id="eca92-141">Site name</span></span>  <br/> |<span data-ttu-id="eca92-142">
            Le \*\*même\*\* nom de site pour toutes les appliances</span><span class="sxs-lookup"><span data-stu-id="eca92-142">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="eca92-143">
            Nom de site \*\*différent\*\* pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="eca92-143">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="eca92-144">Configuration</span><span class="sxs-lookup"><span data-stu-id="eca92-144">Configure</span></span>  <br/> |<span data-ttu-id="eca92-145">Noms du serveur</span><span class="sxs-lookup"><span data-stu-id="eca92-145">Server names</span></span>  <br/> |<span data-ttu-id="eca92-146">**Différent** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="eca92-146">**Different** across appliances</span></span> <br/> |<span data-ttu-id="eca92-147">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="eca92-147">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="eca92-148">Configuration</span><span class="sxs-lookup"><span data-stu-id="eca92-148">Configure</span></span>  <br/> |<span data-ttu-id="eca92-149">FQDNs du pool interne</span><span class="sxs-lookup"><span data-stu-id="eca92-149">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="eca92-150">**Identique** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="eca92-150">**Same** across appliances</span></span> <br/> |<span data-ttu-id="eca92-151">
            Le \*\*même\*\* pour tous les sites RTC</span><span class="sxs-lookup"><span data-stu-id="eca92-151">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="eca92-152">Configuration</span><span class="sxs-lookup"><span data-stu-id="eca92-152">Configure</span></span>  <br/> |<span data-ttu-id="eca92-153">Adresses IP internes</span><span class="sxs-lookup"><span data-stu-id="eca92-153">Internal IPs</span></span>  <br/> |<span data-ttu-id="eca92-154">**Différent** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="eca92-154">**Different** across appliances</span></span> <br/> |<span data-ttu-id="eca92-155">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="eca92-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="eca92-156">Configuration</span><span class="sxs-lookup"><span data-stu-id="eca92-156">Configure</span></span>  <br/> |<span data-ttu-id="eca92-157">FQDN externe</span><span class="sxs-lookup"><span data-stu-id="eca92-157">External FQDN</span></span>  <br/> |<span data-ttu-id="eca92-158">**Identique** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="eca92-158">**Same** across appliances</span></span> <br/> |<span data-ttu-id="eca92-159">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="eca92-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="eca92-160">Configuration</span><span class="sxs-lookup"><span data-stu-id="eca92-160">Configure</span></span>  <br/> |<span data-ttu-id="eca92-161">Adresses IP externes</span><span class="sxs-lookup"><span data-stu-id="eca92-161">External IPs</span></span>  <br/> |<span data-ttu-id="eca92-162">**Différent** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="eca92-162">**Different** across appliances</span></span> <br/> |<span data-ttu-id="eca92-163">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="eca92-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="eca92-164">Configuration</span><span class="sxs-lookup"><span data-stu-id="eca92-164">Configure</span></span>  <br/> |<span data-ttu-id="eca92-165">Paramètres de la passerelle RTC</span><span class="sxs-lookup"><span data-stu-id="eca92-165">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="eca92-166">**Identique** pour chaque appliance</span><span class="sxs-lookup"><span data-stu-id="eca92-166">**Same** across appliances</span></span> <br/> |<span data-ttu-id="eca92-167">**Différent** pour chaque site RTC</span><span class="sxs-lookup"><span data-stu-id="eca92-167">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="eca92-168">Configuration</span><span class="sxs-lookup"><span data-stu-id="eca92-168">Configure</span></span>  <br/> |<span data-ttu-id="eca92-169">Enregistrement DNS</span><span class="sxs-lookup"><span data-stu-id="eca92-169">DNS record</span></span>  <br/> |<span data-ttu-id="eca92-170">Ajouter des enregistrements avec les **mêmes** noms de domaine complets d’accès externe et **différentes** adresses IP</span><span class="sxs-lookup"><span data-stu-id="eca92-170">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="eca92-171">Ajout d’enregistrements avec des FQDN d'accès externe **différents** et des adresses IP **différentes**</span><span class="sxs-lookup"><span data-stu-id="eca92-171">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="eca92-172">Installation</span><span class="sxs-lookup"><span data-stu-id="eca92-172">Setup</span></span>  <br/> |<span data-ttu-id="eca92-173">Client hybride</span><span class="sxs-lookup"><span data-stu-id="eca92-173">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="eca92-174">Site RTC hybride défini</span><span class="sxs-lookup"><span data-stu-id="eca92-174">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="eca92-175">Destination de secours des pairs définie</span><span class="sxs-lookup"><span data-stu-id="eca92-175">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="eca92-176">Site RTC hybride défini</span><span class="sxs-lookup"><span data-stu-id="eca92-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="eca92-177">Destination de secours des pairs définie</span><span class="sxs-lookup"><span data-stu-id="eca92-177">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="eca92-178">Installation</span><span class="sxs-lookup"><span data-stu-id="eca92-178">Setup</span></span>  <br/> |<span data-ttu-id="eca92-179">Passerelle</span><span class="sxs-lookup"><span data-stu-id="eca92-179">Gateway</span></span>  <br/> |<span data-ttu-id="eca92-180">Mappage dans ce site de passerelle MS **M : N**</span><span class="sxs-lookup"><span data-stu-id="eca92-180">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="eca92-181">La ou les passerelle(s) RTC de chaque site RTC devrai(en)t uniquement être connectée(s) au(x) serveur(s) de médiation dans le même site</span><span class="sxs-lookup"><span data-stu-id="eca92-181">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="eca92-182">Installation</span><span class="sxs-lookup"><span data-stu-id="eca92-182">Setup</span></span>  <br/> |<span data-ttu-id="eca92-183">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="eca92-183">User</span></span>  <br/> |<span data-ttu-id="eca92-184">Paramètres RTC utilisateur défini</span><span class="sxs-lookup"><span data-stu-id="eca92-184">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="eca92-185">Paramètres RTC utilisateur défini</span><span class="sxs-lookup"><span data-stu-id="eca92-185">Set UserPSTNSettings</span></span>  <br/> |
   

