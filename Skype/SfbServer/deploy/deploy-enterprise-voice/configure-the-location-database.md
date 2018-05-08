---
title: Configuration de la base de données d’emplacements dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Configurer, remplir et publier la base de données emplacement E9-1-1 dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 0a08d248c5eb7ec406a86f8357c565507bb10ed6
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="configure-the-location-database-in-skype-for-business-server-2015"></a>Configuration de la base de données d’emplacements dans Skype Entreprise Server 2015
 
Configurer, remplir et publier la base de données emplacement E9-1-1 dans Skype pour Business Server Enterprise Voice. 
  
Pour permettre aux clients de détecter automatiquement leur emplacement au sein d’un réseau, vous devez d’abord configurer la base de données d’emplacements. 
  
Pour configurer la base de données d’emplacement, effectuez les tâches suivantes :
  
- Remplissez la base de données avec une correspondance des éléments réseau avec les emplacements. Si vous utilisez une passerelle d’urgence ELIN Location Identification Number (), vous devez inclure le ELIN dans les \<CompanyName\> champ.
    
    Si vous ne remplissez pas la base de données d’emplacements et que **Lieu obligatoire** dans la stratégie d’emplacement est défini sur **Oui** ou sur **Clause d’exclusion de responsabilité**, le client invitera l’utilisateur à entrer manuellement un emplacement.
    
- Valider les adresses par rapport au guide rue maître (MSAG) qui est gérée par le fournisseur de services E9-1-1.
    
- Publiez la base de données mise à jour.
    
## <a name="populate-the-location-database"></a>Remplissage de la base de données d’emplacements

Pour rechercher automatiquement les clients au sein d’un réseau, vous devez tout d’abord remplir la base de données d’emplacement avec un schéma de câblage réseau, qui mappe des éléments réseau à civiles (autrement dit, rue) adresses. Vous pouvez utiliser des sous-réseaux, des points d’accès sans fil, des commutateurs et des ports pour définir le schéma de collage.
  
Vous pouvez ajouter des adresses à la base de données d’emplacements individuellement ou par lot en utilisant un fichier CSV contenant les formats de colonne décrits dans le tableau suivant.
  
Si vous utilisez une passerelle ELIN, incluez-la dans le champ **CompanyName** pour chaque emplacement. Vous pouvez inclure plusieurs passerelles ELIN pour chaque emplacement, en les séparant par des points-virgules.
  
|**Élément réseau**|**Colonnes requises**|
|:-----|:-----|
|**Point d’accès sans fil** <br/> |\<BSSID\>,\<Description\>,\<emplacement\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Ville\>,\<état\>,\<PostalCode\>,\<pays\>  <br/> |
|**Sous-réseau** <br/> |\<Sous-réseau\>,\<Description\>,\<emplacement\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Ville\>,\<état\>,\<PostalCode\>,\<pays\>  <br/> |
|**Port** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<emplacement\>,\<CompanyName\>,\<HouseNumber\>,\< HouseNumberSuffix\>,...  <br/> ... \<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Ville\>,\<état\>,\<PostalCode\>,\< Pays\>  <br/> |
|**Commutateur** <br/> |\<ChassisID\>,\<Description\>,\<emplacement\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,...  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<Ville\>,\<état\>,\<PostalCode\>,\<pays\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>Pour ajouter des éléments réseau à la base de données d’emplacements

1. Exécutez l’applet de commande ci-dessous pour ajouter un emplacement de sous-réseau à la base de données d’emplacements.
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Pour les passerelles ELIN, insérez l’ELIN dans le champ CompanyName. Vous pouvez inclure plusieurs ELIN. Par exemple :
    
   ```
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Vous pouvez également exécuter les applets de commande et utiliser le fichier « subnets.csv » pour pour mettre à jour par lot les emplacements de sous-réseau.
    
   ```
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet

   ```

2. Exécutez l’applet de commande ci-dessous pour ajouter des emplacements sans fil à la base de données d’emplacements.
    
   ```
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   Vous pouvez également exécuter les applets de commande ci-dessous et utiliser le fichier « waps.csv » pour mettre à jour par lot les emplacements sans-fil.
    
   ```
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. Exécutez l’applet de commande ci-dessous pour ajouter des emplacements de commutateur à la base de données d’emplacements.
    
   ```
   Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   Vous pouvez également exécuter les applets de commande ci-dessous et utiliser le fichier « switches.csv » pour mettre à jour par lot les emplacements de commutateur.
    
   ```
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. Exécutez l’applet de commande ci-dessous pour ajouter des emplacements de port à la base de données d’emplacements.
    
   ```
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   La valeur par défaut de PortIDSubType est LocallyAssigned. Vous pouvez également la définir sur InterfaceAlias ou InterfaceName
    
   Vous pouvez également exécuter les applets de commande ci-dessous et utiliser le fichier « ports.csv » pour mettre à jour par lot les emplacements de port.
    
   ```
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>Validation des adresses

### <a name="to-validate-addresses-located-in-the-location-database"></a>Pour valider des adresses situées dans la base de données des emplacements

1.  Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Exécutez les applets de commande ci-dessous pour configurer la connexion du fournisseur de service d’urgence.
    
   ```
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

   ```

3. Exécutez l’applet de commande ci-dessous pour valider les adresses de la base de données des emplacements.
    
   ```
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   Vous pouvez également utiliser l’applet de commande **Test-CsLisCivicAddress** pour valider des adresses individuelles.
    
## <a name="publish-the-location-database"></a>Publication de la base de données d’emplacements

Le client ne pourra accéder aux nouveaux emplacements ajoutés à la base de données d’emplacements qu’une fois qu’ils seront publiés.
  
Si vous utilisez des passerelles ELIN, vous devez également charger les numéros d’identification de l’emplacement en cas d’urgence dans la base de données ALI (Automatic Location Identification) de votre opérateur de réseau téléphonique commuté (RTC). Celui-ci peut exiger l’utilisation d’un format spécifique pour les enregistrements ELIN. Pour plus d’informations, contactez l’opérateur RTC. Vous pouvez exporter les enregistrements à partir de la base de données du service informations d’emplacement et les mettre en forme selon les besoins.
  
### <a name="to-publish-the-location-database"></a>Pour publier la base de données d’emplacements

-  Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
- Exécutez l’applet de commande ci-dessous pour publier la base de données d’emplacements.
    
  ```
  Publish-CsLisConfiguration

  ```


