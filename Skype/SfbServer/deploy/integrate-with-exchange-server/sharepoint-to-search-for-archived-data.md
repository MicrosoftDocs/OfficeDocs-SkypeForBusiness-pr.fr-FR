---
title: Configurer SharePoint Server pour rechercher des données Skype Entreprise archivées
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 'Résumé: configurez SharePoint Server pour rechercher des données archivées par Exchange Server et Skype entreprise Server.'
ms.openlocfilehash: ef8fde621eddfb83972f6cdd540336c9380c7cd7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244140"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>Configurer SharePoint Server pour rechercher des données Skype Entreprise archivées
 
**Résumé:** Configurer SharePoint Server pour rechercher des données archivées par Exchange Server 2016 ou Exchange Server 2013 et Skype entreprise Server.
  
L’un des principaux avantages du stockage de messages instantanés et de transcriptions de conférences Web dans Exchange Server au lieu de Skype entreprise Server est le stockage de données dans le même emplacement, permettant aux administrateurs d’utiliser un seul outil pour rechercher des données Exchange archivées et/ou archivage de données Skype entreprise Server. Dans la mesure où toutes les données sont stockées au même emplacement (Exchange), tous les outils qui peuvent rechercher des données Exchange archivées peuvent également rechercher des données archivées Skype entreprise Server.
  
L’un des outils qui simplifient la recherche de données archivées est Microsoft SharePoint Server 2013. Si vous voulez utiliser SharePoint pour rechercher des données de Skype entreprise Server, vous devez d’abord effectuer toutes les étapes de configuration de l’archivage Exchange dans Skype entreprise Server. Après l’intégration réussie d’Exchange Server et de Skype entreprise Server, vous devez installer l' [API gérée de services Web](https://go.microsoft.com/fwlink/p/?LinkId=258305) Exchange sur votre serveur SharePoint. Vous pouvez enregistrer le fichier téléchargé (EWSManagedAPI.msi) dans n’importe quel dossier sur votre serveur SharePoint.
  
Une fois le fichier téléchargé, procédez comme suit sur le serveur SharePoint :
  
1. Ouvrez une fenêtre Commande en cliquant sur **Démarrer** > **Tous les programmes** > **Accessoires**, puis en cliquant avec le bouton droit sur **Invite de commandes** et enfin sur **Exécuter en tant qu’administrateur**.
    
2. Dans la fenêtre Commande, utilisez la commande cd pour passer du répertoire actuel au dossier dans lequel le fichier EWSManagedAPI.msi a été enregistré. Par exemple, si vous avez enregistré le fichier sur C:\Downloads tapez la commande suivante dans la fenêtre de commande, puis appuyez sur entrée:
    
   ```
   cd C:\Downloads
   ```

3. Pour installer l’API, tapez la commande suivante, puis appuyez sur entrée:
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. Une fois l’API installée, réinitialisez IIS en entrant la commande suivante et en appuyant sur entrée:
    
   ```
   iisreset
   ```

Une fois les services Web Exchange installés, vous devez configurer l’authentification de serveur à serveur entre SharePoint Server et Exchange Server. Pour ce faire, ouvrez d’abord SharePoint Management Shell et exécutez les commandes suivantes:
  
```
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> Utilisez l’URI de votre service de découverte automatique. Ne l’utilisez pas https://autodiscover.litwareinc.com/autodiscover/metadata/json/1. 
  
Une fois que vous avez créé l’émetteur du jeton et configuré le service de jeton, exécutez les commandes suivantes en vous assurant de remplacer l’URL de votre site SharePoint par l’exemple d’URL.http://atl-sharepoint-001:
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Pour configurer l’authentification de serveur à serveur pour Exchange Server, ouvrez Exchange Management Shell et exécutez une commande semblable à celle-ci (en partant du principe que Exchange a été installé sur le lecteur C, et qu’il utilise le chemin de dossier par défaut):
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

Après la configuration de l’application partenaire, il est recommandé d’arrêter et de redémarrer Internet Information Services (IIS) sur l’ensemble de votre boîte aux lettres Exchange et des serveurs d’accès client. Vous pouvez redémarrer IIS à l’aide d’une commande semblable à la suivante, qui redémarre le service sur l’ordinateur atl-exchange-001 :
  
```
iisreset atl-exchange-001
```

Vous pouvez exécuter cette commande à partir d’Exchange Management Shell ou à partir d’une autre fenêtre de commandes.
  
Ensuite, exécutez une commande similaire à ce qui suit, qui donne à l’utilisateur spécifié (dans cet exemple, kenmyer) la droite de la découverte sur Exchange:
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

Après avoir établi l’authentification de serveur à serveur entre Exchange et SharePoint, l’étape suivante consiste à créer un site eDiscovery dans SharePoint. Pour cela, il est possible d’exécuter des commandes similaires à celles-ci dans SharePoint Management Shell:
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> « eDiscovery » est l’abréviation de « découverte électronique » et désigne généralement la recherche, dans des archives électroniques, d’éléments susceptibles d’être « raisonnablement conçus pour conduire à une preuve admissible » devant une cour de justice. 
  
Lorsque le nouveau site est prêt, l’étape suivante consiste à configurer Exchange Server pour qu’il serve de source de résultat pour SharePoint. Pour ce faire, vous pouvez procéder de la manière suivante à partir de la page Administration centrale de SharePoint:
  
1. Dans la page Administration centrale, cliquez sur **Gérer les applications de service** et sur **Application de service de recherche**.
    
2. Dans la page Application de service de recherche : Administration de la recherche, cliquez sur **Origines des résultats**, puis sur **Nouvelle origine des résultats**.
    
3. Dans le volet **Nouvelle origine des résultats**, attribuez un nom à la nouvelle origine des résultats (par exemple, **Microsoft Exchange**) dans la zone **Nom**. Sélectionnez **Exchange** comme source de résultat ****, puis entrez l’URL de la source de services Web pour votre serveur Exchange dans la zone **URL source d’Exchange** . L’URL source doit ressembler à ceci :
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. Vérifiez que l’option **Utiliser la découverte automatique** n’est pas sélectionnée, puis cliquez sur **OK**.
    
Enfin, créez un nouveau cas de découverte électronique et un nouvel ensemble de découverte électronique en effectuant les étapes suivantes sur le site de découverte SharePoint (par exemple,https://atl-sharepoint-001/sites/discovery):
  
1. Dans la page Contenu du site, cliquez sur **Créer un cas**.
    
2. Dans la page Contenu du site : Nouveau site SharePoint, entrez l’alias de messagerie de l’utilisateur (par exemple, **kenmyer**) dans la zone **Titre**, puis ajoutez cette URL dans la zone **Adresse du site web**. Vous obtenez alors une URL similaire à celle-ci :
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. Cliquez sur **Créer**.
    
4. Lorsque la page de l’ensemble eDiscovery apparaît, cliquez sur **nouvel élément** sous **Identité et préservation : Ensembles de découverte**.
    
5. Dans la page Nouveau : Ensemble de découverte, entrez l’alias de messagerie de l’utilisateur dans la zone **Nom de l’ensemble eDiscovery**. Entrez **découverte électronique\\Lync*** dans la zone **filtre** , puis cliquez sur ** &amp; ajouter gérer les sources**.
    
6. Dans la page &amp; ajouter des sources de gestion, entrez l’adresse de messagerie de l’utilisateur dans le premier élément de zone de **boîte aux lettres**. Cliquez sur l’icône Vérifier la boîte aux lettres située en regard du manuel pour vérifier que SharePoint peut se connecter à la boîte aux lettres spécifiée.
    
7. Cliquez sur **OK**.
    
8. Dans la page Ensemble eDiscovery, cliquez sur **Enregistrer** pour enregistrer le nouvel ensemble eDiscovery.
    
À ce stade, vous pouvez effectuer une recherche dans la boîte aux lettres spécifiée (kenmyer) et/ou activer les conservations sur place de la même manière que pour n’importe quelle autre source de contenu ou résultat SharePoint.
  

