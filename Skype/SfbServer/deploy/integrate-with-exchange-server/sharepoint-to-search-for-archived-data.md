---
title: Configurer SharePoint Server pour rechercher des données Skype Entreprise archivées
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 'Résumé : Configurer SharePoint Server pour rechercher des données archivées par Exchange Server et Skype pour Business Server.'
ms.openlocfilehash: b9e08c5681b35b71ac7543115ee008a97e207bb7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884977"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>Configurer SharePoint Server pour rechercher des données Skype Entreprise archivées
 
**Résumé :** Configurer SharePoint Server pour rechercher des données archivées par Exchange Server 2016 ou Exchange Server 2013 et Skype pour Business Server.
  
Un des principaux avantages pour le stockage des transcriptions de conférence Web et de messagerie instantanée dans Exchange Server au lieu de Skype pour Business Server est que le stockage des données dans le même emplacement permet aux administrateurs d’utiliser un seul outil pour rechercher des données Exchange archivées et/ou archivée Skype pour les données métiers. Étant donné que toutes les données sont stockées dans la même (Exchange) n’importe quel outil que vous pouvez rechercher des données archivées Exchange peut également rechercher archivée Skype pour les données métiers.
  
Un outil qui permet de rechercher des données archivées est Microsoft SharePoint Server 2013. Si vous souhaitez utiliser SharePoint pour rechercher Skype pour les données métiers, vous devez tout d’abord effectuer toutes les étapes nécessaires à la configuration d’archivage Exchange dans Skype pour Business Server. Une fois Skype pour Business Server et Exchange Server ont été intégrées avec succès, vous devez installer puis [l’API managée des Services Web](https://go.microsoft.com/fwlink/p/?LinkId=258305) d' Exchange sur votre serveur SharePoint. Vous pouvez enregistrer le fichier téléchargé (EWSManagedAPI.msi) dans n’importe quel dossier sur votre serveur SharePoint.
  
Une fois le fichier téléchargé, procédez comme suit sur le serveur SharePoint :
  
1. Ouvrez une fenêtre Commande en cliquant sur **Démarrer** > **Tous les programmes** > **Accessoires**, puis en cliquant avec le bouton droit sur **Invite de commandes** et enfin sur **Exécuter en tant qu’administrateur**.
    
2. Dans la fenêtre Commande, utilisez la commande cd pour passer du répertoire actuel au dossier dans lequel le fichier EWSManagedAPI.msi a été enregistré. Par exemple, si vous avez enregistré le fichier à C:\Downloads tapez la commande suivante dans la fenêtre de commandes et appuyez sur ENTRÉE :
    
   ```
   cd C:\Downloads
   ```

3. Pour installer l’API, tapez la commande suivante, puis appuyez sur ENTRÉE :
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. Une fois que l’API a été installé, réinitialisez IIS en tapant la commande suivante et appuyez sur ENTRÉE :
    
   ```
   iisreset
   ```

Une fois que les Services Web Exchange a été installé, vous devez alors configurer l’authentification de serveur à serveur entre SharePoint Server et Exchange Server. Pour ce faire, tout d’abord ouvrir SharePoint Management Shell et exécutez l’ensemble des commandes suivante :
  
```
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> Utilisez l’URI de votre service de découverte automatique. N’utilisez pas l’exemple d’URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1. 
  
Après avoir créé l’émetteur de jeton et configuré le service d’émission de jeton, exécutez ces commandes en veillant à substituer l’URL de votre site SharePoint à l’URL de l’exemplehttp://atl-sharepoint-001:
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Pour configurer l’authentification de serveur à serveur pour Exchange Server, ouvrez Exchange Management Shell et exécutez une commande similaire à celle-ci (en supposant que Exchange a été installé sur le lecteur c, et qu’elle utilise le chemin d’accès du dossier par défaut) :
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

Après avoir configuré l’application partenaire, il est recommandé que vous arrêtez et redémarrez Internet Information Services (IIS) sur tous vos boîtes aux lettres et le client access serveurs Exchange. Vous pouvez redémarrer IIS à l’aide d’une commande semblable à la suivante, qui redémarre le service sur l’ordinateur atl-exchange-001 :
  
```
iisreset atl-exchange-001
```

Cette commande peut être exécutée à partir d’Exchange Management Shell ou à partir de n’importe quelle autre fenêtre commande.
  
Ensuite, exécutez une commande semblable à la suivante, qui donne à l’utilisateur spécifié (dans cet exemple, kenmyer) d’effectuer une opération découverte sur Exchange :
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

Une fois que l’authentification de serveur à serveur a été établie entre Exchange et SharePoint, l’étape suivante consiste à créer un site d’eDiscovery dans SharePoint. Qui peuvent être effectuées par l’exécution des commandes semblables à celles-ci à partir de SharePoint Management Shell :
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> « eDiscovery » est l’abréviation de « découverte électronique » et désigne généralement la recherche, dans des archives électroniques, d’éléments susceptibles d’être « raisonnablement conçus pour conduire à une preuve admissible » devant une cour de justice. 
  
Lorsque le nouveau site est prêt, l’étape suivante consiste à configurer Exchange Server pour agir ainsi source pour SharePoint. Vous pouvez effectuer des opérations qui en effectuant la procédure suivante à partir de la page Administration centrale de SharePoint :
  
1. Dans la page Administration centrale, cliquez sur **Gérer les applications de service** et sur **Application de service de recherche**.
    
2. Dans la page Application de service de recherche : Administration de la recherche, cliquez sur **Origines des résultats**, puis sur **Nouvelle origine des résultats**.
    
3. Dans le volet **Nouvelle origine des résultats**, attribuez un nom à la nouvelle origine des résultats (par exemple, **Microsoft Exchange**) dans la zone **Nom**. Sélectionnez l’origine des résultats **protocole** **Exchange** , puis entrez l’URL source des services web pour votre serveur Exchange dans la zone **URL Source d’Exchange** . L’URL source doit ressembler à ceci :
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. Vérifiez que l’option **Utiliser la découverte automatique** n’est pas sélectionnée, puis cliquez sur **OK**.
    
Enfin, créez un nouveau cas eDiscovery et un nouvel ensemble eDiscovery en procédant à partir du site de découverte de SharePoint (par exemple,https://atl-sharepoint-001/sites/discovery):
  
1. Dans la page Contenu du site, cliquez sur **Créer un cas**.
    
2. Dans la page Contenu du site : Nouveau site SharePoint, entrez l’alias de messagerie de l’utilisateur (par exemple, **kenmyer**) dans la zone **Titre**, puis ajoutez cette URL dans la zone **Adresse du site web**. Vous obtenez alors une URL similaire à celle-ci :
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. Cliquez sur **Créer**.
    
4. Lorsque la page de l’ensemble eDiscovery apparaît, cliquez sur **nouvel élément** sous **Identité et préservation : Ensembles de découverte**.
    
5. Dans la page Nouveau : Ensemble de découverte, entrez l’alias de messagerie de l’utilisateur dans la zone **Nom de l’ensemble eDiscovery**. Entrez **eDiscovery Lync\\*** dans le **filtre de** zone, puis cliquez sur **Ajouter &amp; gérer les Sources de**.
    
6. Dans la zone Ajouter &amp; gérer les Sources de page, entrez l’alias de messagerie de l’utilisateur dans la première zone de texte sous **boîtes aux lettres**. Cliquez sur l’icône Vérifier la boîte aux lettres située en regard du manuel pour vérifier que SharePoint peut se connecter à la boîte aux lettres spécifiée.
    
7. Cliquez sur **OK**.
    
8. Dans la page Ensemble eDiscovery, cliquez sur **Enregistrer** pour enregistrer le nouvel ensemble eDiscovery.
    
À ce stade, vous pouvez rechercher la boîte aux lettres spécifiée (kenmyer) et/ou activer archives permanentes de la même manière que vous le feriez pour n’importe quel autre SharePoint contenu ou origine des résultats.
  

