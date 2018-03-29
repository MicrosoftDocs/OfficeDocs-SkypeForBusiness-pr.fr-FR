---
title: Configurer SharePoint Server pour rechercher des données Skype Entreprise archivées
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 'Résumé : Configuration de SharePoint Server pour rechercher des données archivées par 2016 d’Exchange Server ou Exchange Server 2013 et Skype pour Business Server 2015.'
ms.openlocfilehash: 161e4dd530490d22d14f5392539e2cc3d788d6bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>Configurer SharePoint Server pour rechercher des données Skype Entreprise archivées
 
**Résumé :** Configurer le serveur SharePoint pour rechercher des données archivées par 2016 d’Exchange Server ou Exchange Server 2013 et Skype pour Business Server 2015.
  
Un des principaux avantages de stocker les transcriptions des conférences Web et messagerie instantanée dans Exchange Server 2016 ou 2013 d’Exchange Server au lieu de Skype pour Business Server 2015 est que le stockage de données dans le même emplacement permet aux administrateurs d’utiliser un seul outil pour recherche de données archivées de Exchange et/ou Skype archivé pour les données du serveur de l’entreprise. Parce que toutes les données sont stockées dans le même placent (Exchange) n’importe quel outil que vous pouvez rechercher des données archivées de Exchange peut également rechercher Skype archivé pour les données du serveur de l’entreprise.
  
Un outil qui facilite la recherche de données archivées est Microsoft SharePoint Server 2013. Si vous souhaitez utiliser SharePoint pour rechercher les Skype pour données Business Server, vous devez d’abord effectuer toutes les étapes impliquées dans la configuration de l’archivage Exchange dans Skype pour Business Server. Une fois Skype pour Business Server et Exchange Server ont été intégrés avec succès, vous devez ensuite installer Exchange [Web Services Managed API](https://go.microsoft.com/fwlink/p/?LinkId=258305) sur votre serveur SharePoint. Vous pouvez enregistrer le fichier téléchargé (EWSManagedAPI.msi) dans n’importe quel dossier sur votre serveur SharePoint.
  
Une fois le fichier téléchargé, procédez comme suit sur le serveur SharePoint :
  
1. Ouvrez une fenêtre Commande en cliquant sur **Démarrer** > **Tous les programmes** > **Accessoires**, puis en cliquant avec le bouton droit sur **Invite de commandes** et enfin sur **Exécuter en tant qu’administrateur**.
    
2. Dans la fenêtre de commande, utilisez la commande cd pour changer le répertoire en cours dans le dossier où le fichier EWSManagedAPI.msi a été enregistré. Par exemple, si vous avez enregistré le fichier à C:\Downloads tapez la commande suivante dans la fenêtre de commande et appuyez sur ENTRÉE :
    
   ```
   cd C:\Downloads
   ```

3. Pour installer l’API, tapez la commande suivante, puis appuyez sur ENTRÉE :
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. Une fois que l’API a été installé, réinitialisez IIS en tapant la commande suivante et en appuyant sur ENTRÉE :
    
   ```
   iisreset
   ```

Après avoir installé les Services Web Exchange, vous devez alors configurer l’authentification de serveur à serveur entre SharePoint Server et Exchange Server. Pour ce faire, ouvrir en premier le Shell de gestion SharePoint et exécutez l’ensemble des commandes suivantes :
  
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
  
Après avoir créé l’émetteur de jeton et configuré le service de jeton, exécuter ces commandes, en veillant à remplacer par l’URL de votre site SharePoint pour l’URL de l’exemplehttp://atl-sharepoint-001:
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Pour configurer l’authentification de serveur à serveur pour Exchange Server, ouvrez Exchange Management Shell et exécutez une commande similaire à celle-ci (en supposant que Exchange a été installé sur le lecteur C: et qu’il utilise le chemin d’accès du dossier par défaut) :
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

Après avoir configuré l’application partenaire il est recommandé d’arrêter et de redémarrer Internet Information Services (IIS) sur tous vos boîtes aux lettres et client accès aux serveurs Exchange. Vous pouvez redémarrer IIS à l’aide d’une commande semblable à la suivante, qui redémarre le service sur l’ordinateur atl-exchange-001 :
  
```
iisreset atl-exchange-001
```

Cette commande peut être exécutée à partir d’Exchange Management Shell ou de toute autre fenêtre de commande.
  
Ensuite, exécutez une commande semblable à la suivante, qui accorde à l’utilisateur (dans cet exemple, kenmyer) le droit de faire la découverte sur Exchange :
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

Après que l’authentification du serveur-serveur a été établie entre Exchange et SharePoint, l’étape suivante est de créer un site d’e-Discovery dans SharePoint. Qui peut être effectuée en exécutant des commandes similaires aux suivants à partir du Shell de gestion SharePoint :
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> « eDiscovery » est l’abréviation de « découverte électronique » et désigne généralement la recherche, dans des archives électroniques, d’éléments susceptibles d’être « raisonnablement conçus pour conduire à une preuve admissible » devant une cour de justice. 
  
Lorsque le nouveau site est prêt, l’étape suivante consiste à configurer Exchange Server pour agir ainsi source de SharePoint. Vous pouvez faire qui en effectuant la procédure suivante à partir de la page Administration centrale de SharePoint :
  
1. Dans la page Administration centrale, cliquez sur **Gérer les applications de service** et sur **Application de service de recherche**.
    
2. Dans la page Application de service de recherche : Administration de la recherche, cliquez sur **Origines des résultats**, puis sur **Nouvelle origine des résultats**.
    
3. Dans le volet **Nouvelle origine des résultats**, attribuez un nom à la nouvelle origine des résultats (par exemple, **Microsoft Exchange**) dans la zone **Nom**. Sélectionnez **Exchange** comme source de résultats **protocole**et puis entrez l’URL source des services web pour votre serveur Exchange dans la zone **URL de la Source change** . L’URL source doit ressembler à ceci :
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. Vérifiez que l’option **Utiliser la découverte automatique** n’est pas sélectionnée, puis cliquez sur **OK**.
    
Enfin, créez un nouveau dossier d’e-Discovery et un nouveau eDiscovery en effectuant la procédure suivante à partir du site de découverte de SharePoint (par exemple, la valeurhttps://atl-sharepoint-001/sites/discovery):
  
1. Dans la page Contenu du site, cliquez sur **Créer un cas**.
    
2. Dans la page Contenu du site : Nouveau site SharePoint, entrez l’alias de messagerie de l’utilisateur (par exemple, **kenmyer**) dans la zone **Titre**, puis ajoutez cette URL dans la zone **Adresse du site web**. Vous obtenez alors une URL similaire à celle-ci :
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. Cliquez sur **Créer**.
    
4. Lorsque la page de l’ensemble eDiscovery apparaît, cliquez sur **nouvel élément** sous **Identité et préservation : Ensembles de découverte**.
    
5. Dans la page Nouveau : Ensemble de découverte, entrez l’alias de messagerie de l’utilisateur dans la zone **Nom de l’ensemble eDiscovery**. Entrez **eDiscovery Lync\* ** dans le **filtre** de la zone, puis cliquez sur **Ajouter &amp; gérer les Sources de**.
    
6. Dans la zone Ajouter &amp; gérer les Sources de la page, entrez l’alias de messagerie de l’utilisateur dans la première zone de texte sous **boîtes aux lettres**. Cliquez sur l’icône Vérifier la boîte aux lettres située en regard du manuel pour vérifier que SharePoint peut se connecter à la boîte aux lettres spécifiée.
    
7. Cliquez sur **OK**.
    
8. Dans la page Ensemble eDiscovery, cliquez sur **Enregistrer** pour enregistrer le nouvel ensemble eDiscovery.
    
À ce stade, vous pouvez rechercher la boîte aux lettres spécifiée (kenmyer) et/ou activer Place conserve de la même façon que vous le feriez pour n’importe quel autre contenu ou résultat source de SharePoint.
  

