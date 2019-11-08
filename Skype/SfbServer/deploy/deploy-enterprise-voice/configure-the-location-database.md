---
title: Configurer la base de données de localisation dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Configurer, peupler et publier la base de données de localisation E9-1-1 dans Skype entreprise Server Voice.
ms.openlocfilehash: 5aad449d8d286fb4bd71373be33baea9cbb2c8f3
ms.sourcegitcommit: 5e6eb8286bd5eb318a901e42235e91a58946c3a9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2019
ms.locfileid: "38038703"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>Configurer la base de données de localisation dans Skype entreprise Server
 
Configurer, peupler et publier la base de données de localisation E9-1-1 dans Skype entreprise Server Voice. 
  
Pour permettre aux clients de détecter automatiquement leur emplacement au sein d’un réseau, vous devez d’abord configurer la base de données d’emplacements. 
  
Pour configurer la base de données d’emplacements, effectuez les tâches suivantes :
  
- Remplissez la base de données avec une correspondance des éléments réseau avec les emplacements. Si vous utilisez une passerelle ELIN, vous devez inclure la ELIN dans le \<champ CompanyName\> (région d’urgence).
    
    Si vous ne remplissez pas la base de données d’emplacements et que **Lieu obligatoire** dans la stratégie d’emplacement est défini sur **Oui** ou sur **Clause d’exclusion de responsabilité**, le client invitera l’utilisateur à entrer manuellement un emplacement.
    
- Validez les adresses par rapport à la base de données MSAG gérée par le fournisseur de service E9-1-1.
    
- Publiez la base de données mise à jour.
    
## <a name="populate-the-location-database"></a>Remplissage de la base de données d’emplacements

Pour localiser automatiquement des clients sur un réseau, vous devez tout d’abord remplir la base de données d’emplacements avec un schéma de collage réseau, qui mappe les éléments du réseau à des adresses civiles (c’est à dire, les rues). Vous pouvez utiliser des sous-réseaux, des points d’accès sans fil, des commutateurs et des ports pour définir le schéma de collage.
  
Vous pouvez ajouter des adresses à la base de données d’emplacements individuellement ou par lot en utilisant un fichier CSV contenant les formats de colonne décrits dans le tableau suivant.
  
Si vous utilisez une passerelle ELIN, incluez-la dans le champ **CompanyName** pour chaque emplacement. Vous pouvez inclure plusieurs passerelles ELIN pour chaque emplacement, en les séparant par des points-virgules.
  
|**Élément réseau**|**Colonnes requises**|
|:-----|:-----|
|**Point d’accès sans fil** <br/> |\<BSSID\>,\<description\>,\<emplacement\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<\>,... prédirectionnel  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<CodePostal\>,\<Country\>  <br/> |
|**Subnet** <br/> |\<Sous\>-\<réseau\>,\<description\>,\<emplacement\>,\<nom_société\>,\<HouseNumber\>,\<HouseNumberSuffix,\>,... prédirectionnel  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<CodePostal\>,\<Country\>  <br/> |
|**Port** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<description\>,\<emplacement\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,...  <br/> ... \<Prédirectionnelle\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<ville\>,\<état\>,\<CodePostal\>,\<pays\>  <br/> |
|**Commutateur** <br/> |\<ChassisID\>,\<description\>,\<emplacement\>,\<nom_société\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<\>,... prédirectionnel  <br/> ... \<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<CodePostal\>,\<Country\>  <br/> |
   
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
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
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

1.  Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
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
  
Si vous utilisez des passerelles ELIN, vous devez également charger les numéros d’identification de l’emplacement en cas d’urgence dans la base de données ALI (Automatic Location Identification) de votre opérateur de réseau téléphonique commuté (RTC). Celui-ci peut exiger l’utilisation d’un format spécifique pour les enregistrements ELIN. Pour plus d’informations, contactez l’opérateur RTC. Vous pouvez exporter les enregistrements de la base de données de service d’information d’emplacement et les mettre en forme selon les besoins.
  
### <a name="to-publish-the-location-database"></a>Pour publier la base de données d’emplacements

-  Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
- Exécutez l’applet de commande ci-dessous pour publier la base de données d’emplacements.
    
  ```
  Publish-CsLisConfiguration
  ```


