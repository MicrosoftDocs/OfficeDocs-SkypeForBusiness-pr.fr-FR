---
title: Déploiement de la gestion de Skype Room Systems v2 avec OMS
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: d86ff657-ee92-4b06-aee3-d4c43090bdcb
description: Cet article explique comment déployer la gestion des systèmes de salle Skype v2 périphériques d’une manière intégrée, de bout en bout à l’aide de Microsoft Operations Management Suite.
ms.openlocfilehash: 0d0490d92a5513dad38a9ff6348a957204274878
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-management-with-oms"></a><span data-ttu-id="66dfc-103">Déploiement de la gestion de Skype Room Systems v2 avec OMS</span><span class="sxs-lookup"><span data-stu-id="66dfc-103">Deploy Skype Room Systems v2 management with OMS</span></span>
 
<span data-ttu-id="66dfc-104">Cet article explique comment déployer la gestion des systèmes de salle Skype v2 périphériques d’une manière intégrée, de bout en bout à l’aide de Microsoft Operations Management Suite.</span><span class="sxs-lookup"><span data-stu-id="66dfc-104">This article discusses how to deploy management of Skype Room Systems v2 devices in an integrated, end-to-end manner using Microsoft Operations Management Suite.</span></span> 
  
<span data-ttu-id="66dfc-p101">Vous pouvez configurer Microsoft Operations Management Suite (OMS) pour fournir des données télémétriques de base qui facilitent la gestion des dispositifs de salle de réunion Skype. Une fois que votre solution de gestion acquiert sa maturité, vous pouvez acheter des capacités de données et de gestion supplémentaires pour créer des vues plus précises des performances des appareils.</span><span class="sxs-lookup"><span data-stu-id="66dfc-p101">You can configure Microsoft Operations Management Suite (OMS) to provide basic telemetry that will help you manage Skype meeting room devices. As your management solution matures, you can purchase additional data and management capabilities to create a more detailed view of device performance.</span></span>
  
<span data-ttu-id="66dfc-107">À haut niveau, vous devez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="66dfc-107">At a high level, you need to perform the following tasks:</span></span>
  
1. [<span data-ttu-id="66dfc-108">Configurer les appareils pour la gestion OMS </span><span class="sxs-lookup"><span data-stu-id="66dfc-108">Configure devices for OMS Management </span></span>](with-oms.md#config_devices)
    
2. [<span data-ttu-id="66dfc-109">Mapper les champs personnalisés</span><span class="sxs-lookup"><span data-stu-id="66dfc-109">Map custom fields</span></span>](with-oms.md#Custom_fields)
    
3. [<span data-ttu-id="66dfc-110">Définir les vues SRS v2 dans OMS</span><span class="sxs-lookup"><span data-stu-id="66dfc-110">Define the SRS v2 views in OMS</span></span>](with-oms.md#Views)
    
## <a name="find-and-record-device-locations-capabilities-and-configurations"></a><span data-ttu-id="66dfc-111">Rechercher et enregistrer l’emplacement des appareils, les fonctionnalités et les configurations</span><span class="sxs-lookup"><span data-stu-id="66dfc-111">Find and record device locations, capabilities, and configurations</span></span>
<span data-ttu-id="66dfc-112"><a name="find_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="66dfc-112"></span></span>

<span data-ttu-id="66dfc-p102">La première étape consiste à créer une base de données complète regroupant tout l’équipement du système, détaillant les fonctionnalités, la configuration et l’emplacement. Une feuille de calcul peut s’avérer adaptée pour cette tâche dans les petites et moyennes entreprises. Si vous travaillez dans une grande entreprise, vous devriez envisager de recourir à des outils et des services tiers de gestion des ressources. L’important, c’est que vous enregistriez l’emplacement et tous les détails appropriés sur chaque appareil.</span><span class="sxs-lookup"><span data-stu-id="66dfc-p102">The first step is to create a detailed database of all of the equipment in the system, the details of its capabilities and configuration, and its location. A spreadsheet may be adequate for this task in small to medium organizations. If you work at a larger organization, you may need to consider asset management tools and third-party services. What is important is that you record the location and all the relevant details of every device.</span></span>
  
<span data-ttu-id="66dfc-117">Une fois cette tâche effectuée, vous pouvez utiliser ces informations pour déléguer des techniciens et gérer les correctifs et les mises à niveau.</span><span class="sxs-lookup"><span data-stu-id="66dfc-117">Once that work is done, you can use this information to dispatch technicians and manage device patches and upgrades.</span></span>
  
## <a name="configure-devices-for-oms-management"></a><span data-ttu-id="66dfc-118">Configurer les appareils pour la gestion OMS </span><span class="sxs-lookup"><span data-stu-id="66dfc-118">Configure devices for OMS Management</span></span>
<span data-ttu-id="66dfc-119"><a name="config_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="66dfc-119"></span></span>

<span data-ttu-id="66dfc-120">Pour chaque périphérique SRS, suivez les instructions dans les [ordinateurs Windows de se connecter au service journal Analytique dans Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents).</span><span class="sxs-lookup"><span data-stu-id="66dfc-120">For each SRS device, follow the instructions found in [Connect Windows computers to the Log Analytics service in Azure](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents).</span></span>
  
## <a name="configure-oms-to-collect-device-event-logs"></a><span data-ttu-id="66dfc-121">Configurer OMS pour collecter le journal des événements des appareils</span><span class="sxs-lookup"><span data-stu-id="66dfc-121">Configure OMS to collect device event logs</span></span>
<span data-ttu-id="66dfc-122"><a name="config_devices"> </a></span><span class="sxs-lookup"><span data-stu-id="66dfc-122"></span></span>

<span data-ttu-id="66dfc-123">Vous devez configurer spécifiquement OMS pour collecter des journaux des événements à partir de périphériques SRS à l’aide de la procédure à [des sources de données de journal des événements Windows dans le journal Analytique](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events).</span><span class="sxs-lookup"><span data-stu-id="66dfc-123">You will need to specifically configure OMS to collect event logs from SRS devices using the steps at [Windows event log data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events).</span></span> <span data-ttu-id="66dfc-124">Le journal des événements pour sélectionner SRS est « Système de salle Skype » et vous devez vérifier les cases d’option pour tous les types : erreur, avertissement et informations.</span><span class="sxs-lookup"><span data-stu-id="66dfc-124">The SRS event log to select is "Skype Room System" and you should check the option boxes for all types: Error, Warning and Information.</span></span>
  
## <a name="map-custom-fields"></a><span data-ttu-id="66dfc-125">Mapper les champs personnalisés</span><span class="sxs-lookup"><span data-stu-id="66dfc-125">Map custom fields</span></span>
<span data-ttu-id="66dfc-126"><a name="Custom_fields"> </a></span><span class="sxs-lookup"><span data-stu-id="66dfc-126"></span></span>

<span data-ttu-id="66dfc-127">Avant de pouvoir utiliser les mosaïques créés dans les [vues de définir le v2 SRS de l’OMS](with-oms.md#Views) , vous devrez créer des champs personnalisés pour votre affichage.</span><span class="sxs-lookup"><span data-stu-id="66dfc-127">Before the tiles created in the [Define the SRS v2 views in OMS](with-oms.md#Views) can be used, you'll need to create custom fields for your view.</span></span> <span data-ttu-id="66dfc-128">Pour plus d’informations sur la création de champs personnalisés, reportez-vous à la section [champs personnalisés dans le journal Analytique](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields) .</span><span class="sxs-lookup"><span data-stu-id="66dfc-128">see [Custom fields in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-custom-fields) for details on creating custom fields.</span></span>
  
<span data-ttu-id="66dfc-129">Utiliser les mappages ci-dessous, OMS ajoute automatiquement le _CF lors de la définition du nouveau champ.</span><span class="sxs-lookup"><span data-stu-id="66dfc-129">Use the mappings shown below, OMS will automatically add the _CF when defining the new field.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="66dfc-130">N’oubliez pas que tous les champs JSON et OMS sont sensibles à la casse.</span><span class="sxs-lookup"><span data-stu-id="66dfc-130">Remember that all JSON and OMS fields are case sensitive.</span></span> 
  
<span data-ttu-id="66dfc-131">**Mappage des champs personnalisés**</span><span class="sxs-lookup"><span data-stu-id="66dfc-131">**Custom fields mapping**</span></span>

|<span data-ttu-id="66dfc-132">**Champ JSON**</span><span class="sxs-lookup"><span data-stu-id="66dfc-132">**JSON field**</span></span>|<span data-ttu-id="66dfc-133">**Champ personnalisé d’OMS**</span><span class="sxs-lookup"><span data-stu-id="66dfc-133">**OMS custom field**</span></span>|
|:-----|:-----|
|<span data-ttu-id="66dfc-134">Description</span><span class="sxs-lookup"><span data-stu-id="66dfc-134">Description</span></span>  <br/> |<span data-ttu-id="66dfc-135">SRSEventDescription_CF</span><span class="sxs-lookup"><span data-stu-id="66dfc-135">SRSEventDescription_CF</span></span>  <br/> |
|<span data-ttu-id="66dfc-136">ResourceState</span><span class="sxs-lookup"><span data-stu-id="66dfc-136">ResourceState</span></span>  <br/> |<span data-ttu-id="66dfc-137">SRSResourceState_CF</span><span class="sxs-lookup"><span data-stu-id="66dfc-137">SRSResourceState_CF</span></span>  <br/> |
|<span data-ttu-id="66dfc-138">OperationName</span><span class="sxs-lookup"><span data-stu-id="66dfc-138">OperationName</span></span>  <br/> |<span data-ttu-id="66dfc-139">SRSOperationName_CF</span><span class="sxs-lookup"><span data-stu-id="66dfc-139">SRSOperationName_CF</span></span>  <br/> |
|<span data-ttu-id="66dfc-140">OperationResult</span><span class="sxs-lookup"><span data-stu-id="66dfc-140">OperationResult</span></span>  <br/> |<span data-ttu-id="66dfc-141">SRSOperationResult_CF</span><span class="sxs-lookup"><span data-stu-id="66dfc-141">SRSOperationResult_CF</span></span>  <br/> |
|<span data-ttu-id="66dfc-142">OS</span><span class="sxs-lookup"><span data-stu-id="66dfc-142">OS</span></span>  <br/> |<span data-ttu-id="66dfc-143">SRSOSVersion_CF</span><span class="sxs-lookup"><span data-stu-id="66dfc-143">SRSOSVersion_CF</span></span>  <br/> |
|<span data-ttu-id="66dfc-144">OSVersion</span><span class="sxs-lookup"><span data-stu-id="66dfc-144">OSVersion</span></span>  <br/> |<span data-ttu-id="66dfc-145">SRSOSLongVersion_CF</span><span class="sxs-lookup"><span data-stu-id="66dfc-145">SRSOSLongVersion_CF</span></span>  <br/> |
|<span data-ttu-id="66dfc-146">Alias</span><span class="sxs-lookup"><span data-stu-id="66dfc-146">Alias</span></span>  <br/> |<span data-ttu-id="66dfc-147">SRSAlias_CF</span><span class="sxs-lookup"><span data-stu-id="66dfc-147">SRSAlias_CF</span></span>  <br/> |
|<span data-ttu-id="66dfc-148">DisplayName</span><span class="sxs-lookup"><span data-stu-id="66dfc-148">DisplayName</span></span>  <br/> |<span data-ttu-id="66dfc-149">SRSDisplayName_CF</span><span class="sxs-lookup"><span data-stu-id="66dfc-149">SRSDisplayName_CF</span></span>  <br/> |
|<span data-ttu-id="66dfc-150">AppVersion</span><span class="sxs-lookup"><span data-stu-id="66dfc-150">AppVersion</span></span>  <br/> |<span data-ttu-id="66dfc-151">SRSAppVersion_CF</span><span class="sxs-lookup"><span data-stu-id="66dfc-151">SRSAppVersion_CF</span></span>  <br/> |
|<span data-ttu-id="66dfc-152">IPv4Address</span><span class="sxs-lookup"><span data-stu-id="66dfc-152">IPv4Address</span></span>  <br/> |<span data-ttu-id="66dfc-153">SRSIPv4Address_CF</span><span class="sxs-lookup"><span data-stu-id="66dfc-153">SRSIPv4Address_CF</span></span>  <br/> |
|<span data-ttu-id="66dfc-154">IPv6Address</span><span class="sxs-lookup"><span data-stu-id="66dfc-154">IPv6Address</span></span>  <br/> |<span data-ttu-id="66dfc-155">SRSIPv6Address_CF</span><span class="sxs-lookup"><span data-stu-id="66dfc-155">SRSIPv6Address_CF</span></span>  <br/> |
   
## <a name="define-the-srs-v2-views-in-oms"></a><span data-ttu-id="66dfc-156">Définir les vues SRS v2 dans OMS</span><span class="sxs-lookup"><span data-stu-id="66dfc-156">Define the SRS v2 views in OMS</span></span>
<span data-ttu-id="66dfc-157"><a name="Views"> </a></span><span class="sxs-lookup"><span data-stu-id="66dfc-157"></span></span>

<span data-ttu-id="66dfc-158">Une fois que les données sont collectées et mappage des champs personnalisés, vous pouvez utiliser le Concepteur de vues OMS pour développer un tableau de bord contenant des mosaïques pour surveiller les événements de v2 SRS.</span><span class="sxs-lookup"><span data-stu-id="66dfc-158">Once data is collected and custom fields are mapped, you can use OMS View Designer to develop a Dashboard containing Tiles to monitor SRS v2 events.</span></span> <span data-ttu-id="66dfc-159">Concepteur de vues permet de créer des mosaïques suivantes, consultez [Concepteur de vue utilisé pour créer des vues personnalisées dans le journal Analytique](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer) si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="66dfc-159">Use View Designer to create the following tiles, refer to [Use View Designer to create custom views in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-view-designer) as necessary.</span></span>
  
### <a name="create-a-tile-that-shows-healthy-devices"></a><span data-ttu-id="66dfc-160">Créer une mosaïque qui indique les appareils sains</span><span class="sxs-lookup"><span data-stu-id="66dfc-160">Create a tile that shows healthy devices</span></span>

1. <span data-ttu-id="66dfc-161">Définissez le cas : </span><span class="sxs-lookup"><span data-stu-id="66dfc-161">Define the case:</span></span> 
    
    <span data-ttu-id="66dfc-162">Cette mosaïque affiche tous les appareils ayant envoyé un message de pulsations au cours des 10 dernières minutes.</span><span class="sxs-lookup"><span data-stu-id="66dfc-162">This tile displays all devices that have sent a heartbeat message in the last 10 minutes.</span></span>
    
2. <span data-ttu-id="66dfc-163">Assigner une mosaïque de groupe </span><span class="sxs-lookup"><span data-stu-id="66dfc-163">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="66dfc-164">Case à cocher nouveau groupe</span><span class="sxs-lookup"><span data-stu-id="66dfc-164">Check the new group box</span></span>
    
4. <span data-ttu-id="66dfc-165">Ajouter le texte de légende de la mosaïque</span><span class="sxs-lookup"><span data-stu-id="66dfc-165">Add the Tile legend text</span></span>
    
   ```
   All healthy devices (Heartbeat sent in last 10 minutes)
   ```

5. <span data-ttu-id="66dfc-166">Entrer la requête de mosaïque</span><span class="sxs-lookup"><span data-stu-id="66dfc-166">Enter the tile query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" TimeGenerated >NOW-10MINUTES|measure count() by SRSDisplayName_CF 
   ```

6. <span data-ttu-id="66dfc-167">Entrer la requête de liste</span><span class="sxs-lookup"><span data-stu-id="66dfc-167">Enter the list query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by SRSDisplayName_CF |Where LastHB>NOW-10MINUTES
   ```

7. <span data-ttu-id="66dfc-168">Définir le nom des titres de colonne</span><span class="sxs-lookup"><span data-stu-id="66dfc-168">Define column titles name</span></span>
    
   ```
   Display Name
   ```

8. <span data-ttu-id="66dfc-169">Définir la valeur des titres de colonne</span><span class="sxs-lookup"><span data-stu-id="66dfc-169">Define Column titles value</span></span>
    
   ```
   Last HB
   ```

9. <span data-ttu-id="66dfc-170">Entrer la requête de navigation</span><span class="sxs-lookup"><span data-stu-id="66dfc-170">Enter Navigation query</span></span>
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat"|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="create-the-tile-that-shows-devices-with-connectivity-issues"></a><span data-ttu-id="66dfc-171">Créer la mosaïque qui montre les appareils présentant des problèmes de connectivité</span><span class="sxs-lookup"><span data-stu-id="66dfc-171">Create the tile that shows devices with connectivity issues</span></span>

1. <span data-ttu-id="66dfc-172">Définissez le cas : </span><span class="sxs-lookup"><span data-stu-id="66dfc-172">Define the case:</span></span> 
    
    <span data-ttu-id="66dfc-p106">Cette mosaïque affiche tous les appareils qui ont envoyé un message de pulsations au cours des 10 dernières minutes. Ces appareils ont pu rencontrer des problèmes de connectivité avec le réseau, Exchange ou Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="66dfc-p106">This tile displays all devices that have not sent a heartbeat message in the last 10 minutes. These devices may be experiencing issues with network connectivity, Exchange connectivity, or Skype for Business connectivity.</span></span>
    
2. <span data-ttu-id="66dfc-175">Assigner une mosaïque de groupe </span><span class="sxs-lookup"><span data-stu-id="66dfc-175">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="66dfc-176">Ne cochez pas la nouvelle zone de groupe.</span><span class="sxs-lookup"><span data-stu-id="66dfc-176">Do not check the new group box.</span></span> <span data-ttu-id="66dfc-177">Vous l’avez déjà fait lors de la création de la mosaïque 1. Vous n’avez donc pas à le refaire.</span><span class="sxs-lookup"><span data-stu-id="66dfc-177">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="66dfc-178">Ajouter le texte de légende de la mosaïque</span><span class="sxs-lookup"><span data-stu-id="66dfc-178">Add the Tile legend text</span></span>
    
   ```
   Devices no longer sending Heartbeat messages
   ```

5. <span data-ttu-id="66dfc-179">Entrer la requête de mosaïque</span><span class="sxs-lookup"><span data-stu-id="66dfc-179">Enter the tile query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

6. <span data-ttu-id="66dfc-180">Entrer la requête de liste</span><span class="sxs-lookup"><span data-stu-id="66dfc-180">Enter the list query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |measure max(TimeGenerated) as LastHB by Computer|Where LastHB<NOW-10MINUTES
   ```

7. <span data-ttu-id="66dfc-181">Définir le nom des titres de colonne</span><span class="sxs-lookup"><span data-stu-id="66dfc-181">Define column titles name</span></span>
    
   ```
   Device Name
   ```

8. <span data-ttu-id="66dfc-182">Définir la valeur des titres de colonne </span><span class="sxs-lookup"><span data-stu-id="66dfc-182">Define Column titles Value</span></span> 
    
   ```
   Last HB
   ```

9. <span data-ttu-id="66dfc-183">Entrer la requête de navigation</span><span class="sxs-lookup"><span data-stu-id="66dfc-183">Enter Navigation query</span></span>
    
   ```
   {selected item} EventLog:"Skype Room System" SRSOperationName_CF:"Heartbeat" |Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-a-hardware-error"></a><span data-ttu-id="66dfc-184">Liste des appareils présentant une erreur matérielle </span><span class="sxs-lookup"><span data-stu-id="66dfc-184">List devices with a hardware error</span></span>

1. <span data-ttu-id="66dfc-185">Définissez le cas : </span><span class="sxs-lookup"><span data-stu-id="66dfc-185">Define the case:</span></span> 
    
   <span data-ttu-id="66dfc-186">Cette mosaïque affiche tous les périphériques qui a envoyé un message indiquant un un ou plusieurs problèmes de composant matériel dans les dix dernières minutes.</span><span class="sxs-lookup"><span data-stu-id="66dfc-186">This tile displays all devices that sent a message indicating a one or more hardware component issues in the last 10 minutes.</span></span> 
    
2. <span data-ttu-id="66dfc-187">Assigner une mosaïque de groupe </span><span class="sxs-lookup"><span data-stu-id="66dfc-187">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="66dfc-188">Ne cochez pas la nouvelle zone de groupe.</span><span class="sxs-lookup"><span data-stu-id="66dfc-188">Do not check the new group box.</span></span> <span data-ttu-id="66dfc-189">Vous l’avez déjà fait lors de la création de la mosaïque 1. Vous n’avez donc pas à le refaire.</span><span class="sxs-lookup"><span data-stu-id="66dfc-189">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="66dfc-190">Légende de la mosaïque : </span><span class="sxs-lookup"><span data-stu-id="66dfc-190">Tile legend:</span></span> 
    
   ```
   Devices with a Hardware Error
   ```

5. <span data-ttu-id="66dfc-191">Requête de mosaïque</span><span class="sxs-lookup"><span data-stu-id="66dfc-191">Tile Query</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure count() by SRSDisplayName_CF
   ```

6. <span data-ttu-id="66dfc-192">Requête de liste :</span><span class="sxs-lookup"><span data-stu-id="66dfc-192">List query:</span></span>
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:3001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by SRSDisplayName_CF
   ```

7. <span data-ttu-id="66dfc-193">Nom des titres de colonne : </span><span class="sxs-lookup"><span data-stu-id="66dfc-193">Column titles Name:</span></span> 
    
   ```
   Display Name
   ```

8. <span data-ttu-id="66dfc-194">Valeur des titres de colonne : </span><span class="sxs-lookup"><span data-stu-id="66dfc-194">Column titles Value:</span></span> 
    
   ```
   Last Error
   ```

9. <span data-ttu-id="66dfc-195">Requête de navigation : </span><span class="sxs-lookup"><span data-stu-id="66dfc-195">Navigation query:</span></span> 
    
   ```
   {selected item}  EventLevelName:Error EventID:3001|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-with-an-app-error"></a><span data-ttu-id="66dfc-196">Liste des appareils présentant une erreur d’application  </span><span class="sxs-lookup"><span data-stu-id="66dfc-196">List devices with an App error</span></span>

1. <span data-ttu-id="66dfc-197">Définissez le cas :</span><span class="sxs-lookup"><span data-stu-id="66dfc-197">Define the case:</span></span> 
    
   <span data-ttu-id="66dfc-198">Cette mosaïque affiche tous les appareils SRS qui signalent la survenue d’une ou de plusieurs erreurs au niveau des composants de l’application au cours des 10 dernières minutes.</span><span class="sxs-lookup"><span data-stu-id="66dfc-198">This tile displays all SRS devices that report 1 or more app component errors within the last 10 minutes</span></span>
    
2. <span data-ttu-id="66dfc-199">Assigner une mosaïque de groupe </span><span class="sxs-lookup"><span data-stu-id="66dfc-199">Assign Group Title</span></span> 
    
   ```
   SRS v2
   ```

3. <span data-ttu-id="66dfc-200">Ne cochez pas la nouvelle zone de groupe.</span><span class="sxs-lookup"><span data-stu-id="66dfc-200">Do not check the new group box.</span></span> <span data-ttu-id="66dfc-201">Vous l’avez déjà fait lors de la création de la mosaïque 1. Vous n’avez donc pas à le refaire.</span><span class="sxs-lookup"><span data-stu-id="66dfc-201">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="66dfc-202">Légende de la mosaïque : </span><span class="sxs-lookup"><span data-stu-id="66dfc-202">Tile legend:</span></span> 
   ``` 
    Device with App Errors (in prior 10 minutes)
   ``` 
5. <span data-ttu-id="66dfc-203">Requête de mosaïque : </span><span class="sxs-lookup"><span data-stu-id="66dfc-203">Tile Query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure count() by Computer
   ```

6. <span data-ttu-id="66dfc-204">Requête de liste : </span><span class="sxs-lookup"><span data-stu-id="66dfc-204">List query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventLevelName:Error EventID:2001 TimeGenerated>NOW-10MINUTES|measure max(TimeGenerated) by Computer
   ```

7. <span data-ttu-id="66dfc-205">Nom des titres de colonne : </span><span class="sxs-lookup"><span data-stu-id="66dfc-205">Column titles Name:</span></span> 
    
   ```
   Device Name
   ```

8. <span data-ttu-id="66dfc-206">Valeur des titres de colonne : </span><span class="sxs-lookup"><span data-stu-id="66dfc-206">Column titles Value:</span></span> 
    
   ```
   Last Error
   ```

9. <span data-ttu-id="66dfc-207">Requête de navigation :</span><span class="sxs-lookup"><span data-stu-id="66dfc-207">Navigation query:</span></span>
    
   ```
   {selected item} EventLevelName:Error|Dedup SRSDisplayName_CF|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

### <a name="list-devices-requiring-a-restart"></a><span data-ttu-id="66dfc-208">Liste des appareils nécessitant un redémarrage</span><span class="sxs-lookup"><span data-stu-id="66dfc-208">List devices requiring a restart</span></span>

1. <span data-ttu-id="66dfc-209">Définissez le cas :</span><span class="sxs-lookup"><span data-stu-id="66dfc-209">Define the case:</span></span> 
    
   <span data-ttu-id="66dfc-210">Cette mosaïque affiche tous les appareils SRS qui ont été redémarrés au cours des 24 dernières heures et le nombre de redémarrages.</span><span class="sxs-lookup"><span data-stu-id="66dfc-210">This tile displays all SRS devices that have been restarted in the past 24 hours and number of restarts</span></span>
    
2. <span data-ttu-id="66dfc-211">Assigner une mosaïque de groupe </span><span class="sxs-lookup"><span data-stu-id="66dfc-211">Assign Group Title</span></span> 
    
  ```
  SRS v2
  ```

3. <span data-ttu-id="66dfc-212">Ne cochez pas la nouvelle zone de groupe.</span><span class="sxs-lookup"><span data-stu-id="66dfc-212">Do not check the new group box.</span></span> <span data-ttu-id="66dfc-213">Vous l’avez déjà fait lors de la création de la mosaïque 1. Vous n’avez donc pas à le refaire.</span><span class="sxs-lookup"><span data-stu-id="66dfc-213">You already did this when creating tile 1, and don't need to do it again.</span></span>
    
4. <span data-ttu-id="66dfc-214">Légende de la mosaïque : </span><span class="sxs-lookup"><span data-stu-id="66dfc-214">Tile legend:</span></span> 
    
   ```
   Devices with App restarted (past 24 hours)
   ```

5. <span data-ttu-id="66dfc-215">Requête de mosaïque : </span><span class="sxs-lookup"><span data-stu-id="66dfc-215">Tile Query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count() by Computer
   ```

6. <span data-ttu-id="66dfc-216">Requête de liste : </span><span class="sxs-lookup"><span data-stu-id="66dfc-216">List query:</span></span> 
    
   ```
   Type:Event EventLog:"Skype Room System" EventID:4000 TimeGenerated>NOW-24HOURS|measure count(EventID) by SRSDisplayName_CF
   ```

7. <span data-ttu-id="66dfc-217">Nom des titres de colonne : </span><span class="sxs-lookup"><span data-stu-id="66dfc-217">Column titles Name:</span></span> 
    
   ```
   Display Name
   ```

8. <span data-ttu-id="66dfc-218">Valeur des titres de colonne : </span><span class="sxs-lookup"><span data-stu-id="66dfc-218">Column titles Value:</span></span> 
    
   ```
   Number of restarts
   ```

9. <span data-ttu-id="66dfc-219">Requête de navigation : </span><span class="sxs-lookup"><span data-stu-id="66dfc-219">Navigation query:</span></span> 
    
   ```
   {selected item} EventID:4000 TimeGenerated >NOW-24HOURS|Select TimeGenerated, Computer, SRSOperationName_CF, SRSOperationResult_CF,SRSEventDescription_CF, SRSAppVersion_CF, SRSDisplayName_CF, SRSAlias_CF, SRSOSVersion_CF, SRSOSLongVersion_CF, SRSIPv4Address_CF, SRSIPv6Address_CF
   ```

<span data-ttu-id="66dfc-p111">La création de vues est terminée. Les alertes disponibles sont toutes reflétées dans une ou plusieurs de ces mosaïques.</span><span class="sxs-lookup"><span data-stu-id="66dfc-p111">That completes view creation. The alerts currently available are all reflected in one or more of these tiles.</span></span>
## <a name="see-also"></a><span data-ttu-id="66dfc-222">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="66dfc-222">See also</span></span>
<span data-ttu-id="66dfc-223"><a name="Views"> </a></span><span class="sxs-lookup"><span data-stu-id="66dfc-223"></span></span>

#### 

[<span data-ttu-id="66dfc-224">Planification de la gestion de v2 Skype salle systèmes avec OMS</span><span class="sxs-lookup"><span data-stu-id="66dfc-224">Plan Skype Room Systems v2 management with OMS</span></span>](../../plan-your-deployment/clients-and-devices/oms-management.md)
  
[<span data-ttu-id="66dfc-225">Gérer les périphériques de v2 Skype salle systèmes avec OMS</span><span class="sxs-lookup"><span data-stu-id="66dfc-225">Manage Skype Room Systems v2 devices with OMS</span></span>](../../manage/skype-room-systems-v2/oms.md)

