---
title: Configurer la base de données de localisation dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Configurer, peupler et publier la base de données de localisation E9-1-1 dans Skype entreprise Server Voice.
ms.openlocfilehash: 4b8848637130886250d08847c45df3c2dc080f5b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768107"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a><span data-ttu-id="38a84-103">Configurer la base de données de localisation dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="38a84-103">Configure the location database in Skype for Business Server</span></span>
 
<span data-ttu-id="38a84-104">Configurer, peupler et publier la base de données de localisation E9-1-1 dans Skype entreprise Server Voice.</span><span class="sxs-lookup"><span data-stu-id="38a84-104">Configure, populate, and publish the E9-1-1 location database in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="38a84-105">Pour permettre aux clients de détecter automatiquement leur emplacement au sein d’un réseau, vous devez d’abord configurer la base de données d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="38a84-105">To enable clients to automatically detect their location within a network, you first need to configure the location database.</span></span> 
  
<span data-ttu-id="38a84-106">Pour configurer la base de données d’emplacements, effectuez les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="38a84-106">To configure the location database, perform the following tasks:</span></span>
  
- <span data-ttu-id="38a84-107">Remplissez la base de données avec une correspondance des éléments réseau avec les emplacements.</span><span class="sxs-lookup"><span data-stu-id="38a84-107">Populate the database with a mapping of network elements to locations.</span></span> <span data-ttu-id="38a84-108">Si vous utilisez une passerelle ELIN, vous devez inclure la ELIN dans le \<champ CompanyName\> (région d’urgence).</span><span class="sxs-lookup"><span data-stu-id="38a84-108">If you use an Emergency Location Identification Number (ELIN) gateway, you need to include the ELIN in the \<CompanyName\> field.</span></span>
    
    <span data-ttu-id="38a84-109">Si vous ne remplissez pas la base de données d’emplacements et que **Lieu obligatoire** dans la stratégie d’emplacement est défini sur **Oui** ou sur **Clause d’exclusion de responsabilité**, le client invitera l’utilisateur à entrer manuellement un emplacement.</span><span class="sxs-lookup"><span data-stu-id="38a84-109">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>
    
- <span data-ttu-id="38a84-110">Validez les adresses par rapport à la base de données MSAG gérée par le fournisseur de service E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="38a84-110">Validate the addresses against the master street address guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span>
    
- <span data-ttu-id="38a84-111">Publiez la base de données mise à jour.</span><span class="sxs-lookup"><span data-stu-id="38a84-111">Publish the updated database.</span></span>
    
## <a name="populate-the-location-database"></a><span data-ttu-id="38a84-112">Remplissage de la base de données d’emplacements</span><span class="sxs-lookup"><span data-stu-id="38a84-112">Populate the location database</span></span>

<span data-ttu-id="38a84-113">Pour localiser automatiquement des clients sur un réseau, vous devez tout d’abord remplir la base de données d’emplacements avec un schéma de collage réseau, qui mappe les éléments du réseau à des adresses civiles (c’est à dire, les rues).</span><span class="sxs-lookup"><span data-stu-id="38a84-113">To automatically locate clients within a network, you first need to populate the location database with a network wiremap, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="38a84-114">Vous pouvez utiliser des sous-réseaux, des points d’accès sans fil, des commutateurs et des ports pour définir le schéma de collage.</span><span class="sxs-lookup"><span data-stu-id="38a84-114">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>
  
<span data-ttu-id="38a84-115">Vous pouvez ajouter des adresses à la base de données d’emplacements individuellement ou par lot en utilisant un fichier CSV contenant les formats de colonne décrits dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="38a84-115">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>
  
<span data-ttu-id="38a84-p103">Si vous utilisez une passerelle ELIN, incluez-la dans le champ **CompanyName** pour chaque emplacement. Vous pouvez inclure plusieurs passerelles ELIN pour chaque emplacement, en les séparant par des points-virgules.</span><span class="sxs-lookup"><span data-stu-id="38a84-p103">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location. You can include multiple ELINs for each location, each separated by a semicolon.</span></span>
  
|<span data-ttu-id="38a84-118">**Élément réseau**</span><span class="sxs-lookup"><span data-stu-id="38a84-118">**Network Element**</span></span>|<span data-ttu-id="38a84-119">**Colonnes requises**</span><span class="sxs-lookup"><span data-stu-id="38a84-119">**Required Columns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="38a84-120">**Point d’accès sans fil**</span><span class="sxs-lookup"><span data-stu-id="38a84-120">**Wireless access point**</span></span> <br/> |<span data-ttu-id="38a84-121">\<BSSID\>,\<description\>,\<emplacement\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<\>,... prédirectionnel</span><span class="sxs-lookup"><span data-stu-id="38a84-121">\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="38a84-122">... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<CodePostal\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="38a84-122">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="38a84-123">**Subnet**</span><span class="sxs-lookup"><span data-stu-id="38a84-123">**Subnet**</span></span> <br/> |<span data-ttu-id="38a84-124">\<Sous\>-\<réseau\>,\<description\>,\<emplacement\>,\<nom_société\>,\<HouseNumber\>,\<HouseNumberSuffix,\>,... prédirectionnel</span><span class="sxs-lookup"><span data-stu-id="38a84-124">\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="38a84-125">... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<CodePostal\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="38a84-125">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="38a84-126">**Port**</span><span class="sxs-lookup"><span data-stu-id="38a84-126">**Port**</span></span> <br/> |<span data-ttu-id="38a84-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<description\>,\<emplacement\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,...</span><span class="sxs-lookup"><span data-stu-id="38a84-127">\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…</span></span>  <br/> <span data-ttu-id="38a84-128">... \<Prédirectionnelle\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<ville\>,\<état\>,\<CodePostal\>,\<pays\></span><span class="sxs-lookup"><span data-stu-id="38a84-128">…\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
|<span data-ttu-id="38a84-129">**Commutateur**</span><span class="sxs-lookup"><span data-stu-id="38a84-129">**Switch**</span></span> <br/> |<span data-ttu-id="38a84-130">\<ChassisID\>,\<description\>,\<emplacement\>,\<nom_société\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<\>,... prédirectionnel</span><span class="sxs-lookup"><span data-stu-id="38a84-130">\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…</span></span>  <br/> <span data-ttu-id="38a84-131">... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<CodePostal\>,\<Country\></span><span class="sxs-lookup"><span data-stu-id="38a84-131">…\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\></span></span>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="38a84-132">Pour ajouter des éléments réseau à la base de données d’emplacements</span><span class="sxs-lookup"><span data-stu-id="38a84-132">To add network elements to the location database</span></span>

1. <span data-ttu-id="38a84-133">Exécutez l’applet de commande ci-dessous pour ajouter un emplacement de sous-réseau à la base de données d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="38a84-133">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="38a84-p104">Pour les passerelles ELIN, insérez l’ELIN dans le champ CompanyName. Vous pouvez inclure plusieurs ELIN. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="38a84-p104">For ELIN gateways, put the ELIN in the CompanyName field. You can include more than one ELIN. For example:</span></span>
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    <span data-ttu-id="38a84-137">Vous pouvez également exécuter les applets de commande et utiliser le fichier « subnets.csv » pour pour mettre à jour par lot les emplacements de sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="38a84-137">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. <span data-ttu-id="38a84-138">Exécutez l’applet de commande ci-dessous pour ajouter des emplacements sans fil à la base de données d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="38a84-138">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="38a84-139">Vous pouvez également exécuter les applets de commande ci-dessous et utiliser le fichier « waps.csv » pour mettre à jour par lot les emplacements sans-fil.</span><span class="sxs-lookup"><span data-stu-id="38a84-139">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. <span data-ttu-id="38a84-140">Exécutez l’applet de commande ci-dessous pour ajouter des emplacements de commutateur à la base de données d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="38a84-140">Run the following cmdlet to add switch locations to the location database.</span></span>
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   <span data-ttu-id="38a84-141">Vous pouvez également exécuter les applets de commande ci-dessous et utiliser le fichier « switches.csv » pour mettre à jour par lot les emplacements de commutateur.</span><span class="sxs-lookup"><span data-stu-id="38a84-141">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. <span data-ttu-id="38a84-142">Exécutez l’applet de commande ci-dessous pour ajouter des emplacements de port à la base de données d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="38a84-142">Run the following cmdlet to add port locations to the location database</span></span>
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   <span data-ttu-id="38a84-p105">La valeur par défaut de PortIDSubType est LocallyAssigned. Vous pouvez également la définir sur InterfaceAlias ou InterfaceName</span><span class="sxs-lookup"><span data-stu-id="38a84-p105">The default for PortIDSubType is LocallyAssigned. You can also set it to InterfaceAlias or InterfaceName</span></span>
    
   <span data-ttu-id="38a84-145">Vous pouvez également exécuter les applets de commande ci-dessous et utiliser le fichier « ports.csv » pour mettre à jour par lot les emplacements de port.</span><span class="sxs-lookup"><span data-stu-id="38a84-145">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a><span data-ttu-id="38a84-146">Validation des adresses</span><span class="sxs-lookup"><span data-stu-id="38a84-146">Validate addresses</span></span>

### <a name="to-validate-addresses-located-in-the-location-database"></a><span data-ttu-id="38a84-147">Pour valider des adresses situées dans la base de données des emplacements</span><span class="sxs-lookup"><span data-stu-id="38a84-147">To validate addresses located in the location database</span></span>

1.  <span data-ttu-id="38a84-148">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="38a84-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="38a84-149">Exécutez les applets de commande ci-dessous pour configurer la connexion du fournisseur de service d’urgence.</span><span class="sxs-lookup"><span data-stu-id="38a84-149">Run the following cmdlets to configure the emergency service provider connection.</span></span>
    
   ```powershell
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. <span data-ttu-id="38a84-150">Exécutez l’applet de commande ci-dessous pour valider les adresses de la base de données des emplacements.</span><span class="sxs-lookup"><span data-stu-id="38a84-150">Run the following cmdlet to validate the addresses in the location database.</span></span>
    
   ```powershell
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   <span data-ttu-id="38a84-151">Vous pouvez également utiliser l’applet de commande **Test-CsLisCivicAddress** pour valider des adresses individuelles.</span><span class="sxs-lookup"><span data-stu-id="38a84-151">You can also use the **Test-CsLisCivicAddress** cmdlet to validate individual addresses.</span></span>
    
## <a name="publish-the-location-database"></a><span data-ttu-id="38a84-152">Publication de la base de données d’emplacements</span><span class="sxs-lookup"><span data-stu-id="38a84-152">Publish the location database</span></span>

<span data-ttu-id="38a84-153">Le client ne pourra accéder aux nouveaux emplacements ajoutés à la base de données d’emplacements qu’une fois qu’ils seront publiés.</span><span class="sxs-lookup"><span data-stu-id="38a84-153">The new locations that you added to the location database will not be made available to the client until they have been published.</span></span>
  
<span data-ttu-id="38a84-154">Si vous utilisez des passerelles ELIN, vous devez également charger les numéros d’identification de l’emplacement en cas d’urgence dans la base de données ALI (Automatic Location Identification) de votre opérateur de réseau téléphonique commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="38a84-154">If you use Emergency Location Identification Number (ELIN) gateways, you also need to upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span> <span data-ttu-id="38a84-155">Celui-ci peut exiger l’utilisation d’un format spécifique pour les enregistrements ELIN.</span><span class="sxs-lookup"><span data-stu-id="38a84-155">Your PSTN carrier may require you to use a specific format for the ELIN records.</span></span> <span data-ttu-id="38a84-156">Pour plus d’informations, contactez l’opérateur RTC.</span><span class="sxs-lookup"><span data-stu-id="38a84-156">Contact your PSTN carrier for details.</span></span> <span data-ttu-id="38a84-157">Vous pouvez exporter les enregistrements de la base de données de service d’information d’emplacement et les mettre en forme selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="38a84-157">You can export the records from the Location Information service database and format them as required.</span></span>
  
### <a name="to-publish-the-location-database"></a><span data-ttu-id="38a84-158">Pour publier la base de données d’emplacements</span><span class="sxs-lookup"><span data-stu-id="38a84-158">To publish the location database</span></span>

-  <span data-ttu-id="38a84-159">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="38a84-159">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
- <span data-ttu-id="38a84-160">Exécutez l’applet de commande ci-dessous pour publier la base de données d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="38a84-160">Run the following cmdlet to publish the location database.</span></span>
    
  ```powershell
  Publish-CsLisConfiguration
  ```


