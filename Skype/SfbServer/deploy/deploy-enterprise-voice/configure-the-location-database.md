---
title: Configurer la base de données d’emplacements dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
description: Configurez, remplissez et publiez la base de données d’emplacements E9-1-1 dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 8cd4f10a383d279421af6f9152a31f637ee47474
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851608"
---
# <a name="configure-the-location-database-in-skype-for-business-server"></a>Configurer la base de données d’emplacements dans Skype Entreprise Server
 
Configurez, remplissez et publiez la base de données d’emplacements E9-1-1 dans Skype Entreprise Server Voix Entreprise. 
  
Pour permettre aux clients de détecter automatiquement leur emplacement au sein d’un réseau, vous devez d’abord configurer la base de données d’emplacements. 
  
Pour configurer la base de données d’emplacements, effectuez les tâches suivantes :
  
- Remplir la base de données avec une correspondance des éléments réseau avec les emplacements. Si vous utilisez une passerelle ELIN (Emergency Location Identification Number), vous devez inclure le numéro ELIN dans le \<CompanyName\> champ.
    
    Si vous ne renseignez pas la base de données d’emplacements et que **Lieu obligatoire** dans la stratégie d’emplacement est défini sur **Oui** ou sur **Clause d’exclusion de responsabilité**, le client invitera l’utilisateur à entrer un emplacement manuellement.
    
- Valider les adresses par rapport à la base de données MSAG gérée par le fournisseur de service E9-1-1.
    
- Publier la base de données mise à jour.
    
## <a name="populate-the-location-database"></a>Remplir la base de données d’emplacements

Pour localiser automatiquement des clients au sein d’un réseau, vous devez tout d’abord renseigner la base de données d’emplacements avec un schéma de collage réseau, qui mappe les éléments du réseau à des adresses civiles (c’est à dire, les rues). Vous pouvez utiliser des sous-réseaux, des points d’accès sans fil, des commutateurs et des ports pour définir le schéma de collage.
  
Vous pouvez ajouter des adresses à la base de données d’emplacements individuellement ou par lot en utilisant un fichier CSV contenant les formats de colonne décrits dans le tableau suivant.
  
Si vous utilisez une passerelle ELIN, incluez-la dans le champ **CompanyName** pour chaque emplacement. Vous pouvez inclure plusieurs ELIN pour chaque emplacement, séparées par un point-virgule.
  
|**Élément réseau**|**Colonnes requises**|
|:-----|:-----|
|**Point d’accès sans fil** <br/> |\<BSSID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Subnet** <br/> |\<Subnet\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Port** <br/> |\<ChassisID\>,\<PortIDSubType\>,\<PortID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,…  <br/> …\<PreDirectional\>,\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
|**Commutateur** <br/> |\<ChassisID\>,\<Description\>,\<Location\>,\<CompanyName\>,\<HouseNumber\>,\<HouseNumberSuffix\>,\<PreDirectional\>,…  <br/> …\<StreetName\>,\<StreetSuffix\>,\<PostDirectional\>,\<City\>,\<State\>,\<PostalCode\>,\<Country\>  <br/> |
   
### <a name="to-add-network-elements-to-the-location-database"></a>Pour ajouter des éléments réseau à la base de données d’emplacements

1. Exécutez la cmdlet suivante pour ajouter un emplacement de sous-réseau à la base de données d’emplacements.
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Pour les passerelles ELIN, placez l’ELIN dans le champ CompanyName. Vous pouvez inclure plusieurs ELIN. Par exemple :
    
   ```powershell
   Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

    Vous pouvez également exécuter les cmdlets et utiliser un fichier nommé « subnets.csv » pour pour mettre à jour par lot les emplacements de sous-réseau.
    
   ```powershell
   $g = Import-Csv subnets.csv
   $g | Set-CsLisSubnet
   ```

2. Exécutez la cmdlet suivante pour ajouter des emplacements sans fil à la base de données d’emplacements.
    
   ```powershell
   Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   Vous pouvez également exécuter les cmdlets suivantes et utiliser un fichier nommé « waps.csv » pour mettre à jour par lot les emplacements sans-fil.
    
   ```powershell
   $g = Import-Csv waps.csv
   $g | Set-CsLisWirelessAccessPoint
   ```

3. Exécutez la cmdlet suivante pour ajouter des emplacements de commutateur à la base de données d’emplacements.
    
   ```powershell
   Set-CsLisSwitch -ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
   ```

   Vous pouvez également exécuter les cmdlets suivantes et utiliser un fichier nommé « switches.csv » pour mettre à jour par lot les emplacements de commutateur.
    
   ```powershell
   $g = Import-Csv switches.csv
   $g | Set-CsLisSwitch
   ```

4. Exécutez la cmdlet suivante pour ajouter des emplacements de port à la base de données d’emplacements.
    
   ```powershell
   Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
   ```

   La valeur par défaut de PortIDSubType est LocallyAssigned. Vous pouvez également la définir sur InterfaceAlias ou InterfaceName
    
   Vous pouvez également exécuter les cmdlets suivantes et utiliser un fichier nommé « ports.csv » pour mettre à jour par lot les emplacements de port.
    
   ```powershell
   $g = Import-Csv ports.csv
   $g | Set-CsLisPort
   ```

## <a name="validate-addresses"></a>Valider les adresses

### <a name="to-validate-addresses-located-in-the-location-database"></a>Pour valider des adresses situées dans la base de données des emplacements

1.  Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
2. Exécutez les applets de commande suivantes pour configurer la connexion du fournisseur de service d’urgence.
    
   ```powershell
   $pwd = Read-Host -AsSecureString <password>
   Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd
   ```

3. Exécutez l’applet de commande suivante pour valider les adresses de la base de données des emplacements.
    
   ```powershell
   Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
   ```

   Vous pouvez également utiliser l’applet de commande **Test-CsLisCivicAddress** pour valider des adresses individuelles.
    
## <a name="publish-the-location-database"></a>Publier la base de données d’emplacements

Les nouveaux emplacements que vous avez ajoutés à la base de données d’emplacements ne seront pas mis à la disposition du client tant qu’ils n’auront pas été publiés.
  
Si vous utilisez des passerelles ELIN (Emergency Location Identification Number), vous devez également charger les numéros d’identification d’emplacement d’urgence vers la base de données ALI (Automatic Location Identification) de votre opérateur de réseau téléphonique commuté (PSTN). Votre opérateur PSTN peut vous obliger à utiliser un format spécifique pour les enregistrements ELIN. Pour plus d’informations, contactez votre opérateur PSTN. Vous pouvez exporter les enregistrements à partir de la base de données du service Informations sur l’emplacement et les mettre en forme selon les besoins.
  
### <a name="to-publish-the-location-database"></a>Pour publier la base de données d’emplacements

-  Démarrez l’Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**
    
- Exécutez l’cmdlet suivante pour publier la base de données d’emplacements.
    
  ```powershell
  Publish-CsLisConfiguration
  ```


