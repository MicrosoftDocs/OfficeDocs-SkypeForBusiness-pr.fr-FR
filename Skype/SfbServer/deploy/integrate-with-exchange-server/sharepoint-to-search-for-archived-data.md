---
title: Configurer SharePoint server pour rechercher des données Skype Entreprise archivées
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 'Résumé : Configurez SharePoint server pour rechercher des données archivées par Exchange Server et Skype Entreprise Server.'
ms.openlocfilehash: ab7fe3127f4837334142dd1f4138df81f7dadf21
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765852"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>Configurer SharePoint server pour rechercher des données Skype Entreprise archivées
 
**Résumé :** Configurez SharePoint Server pour rechercher des données archivées par Exchange Server 2016 ou Exchange Server 2013 et Skype Entreprise Server.
  
L’un des principaux avantages du stockage des transcriptions de messagerie instantanée et de conférence Web dans Exchange Server au lieu de Skype Entreprise Server est que le stockage de données au même emplacement permet aux administrateurs d’utiliser un seul outil pour rechercher des données Exchange archivées et/ou des données Skype Entreprise Server archivées. Étant donné que toutes les données sont stockées au même endroit (Exchange), tout outil qui peut rechercher des données Exchange archivées peut également rechercher des données Skype Entreprise Server archivées.
  
Un outil qui facilite la recherche de données archivées est Microsoft SharePoint Server 2013. Si vous souhaitez utiliser SharePoint pour rechercher des données Skype Entreprise Server, vous devez d’abord effectuer toutes les étapes nécessaires à la configuration de l’archivage Exchange dans Skype Entreprise Server. Une Exchange Server et Skype Entreprise Server correctement intégrées, vous devez installer l’API gérée des [services web](https://go.microsoft.com/fwlink/p/?LinkId=258305) Exchange sur votre serveur SharePoint. Le fichier téléchargé (EWSManagedAPI.msi) peut être enregistré dans n’importe quel dossier de SharePoint serveur.
  
Une fois le fichier téléchargé, procédez comme suit sur le serveur SharePoint :
  
1. Ouvrez une fenêtre Commande en cliquant sur **Démarrer**, sur **Tous les programmes**, sur **Accessoires**, en cliquant avec le bouton droit sur **Invite de commandes**, puis en cliquant sur **Exécuter en tant qu’administrateur**.
    
2. Dans la fenêtre Commande, utilisez la commande cd pour modifier le répertoire actuel et définir à la place le dossier dans lequel le fichier EWSManagedAPI.msi a été enregistré. Par exemple, si vous avez enregistré le fichier dans C:\Downloads, tapez la commande suivante dans la fenêtre de commande, puis appuyez sur Entrée :
    
   ```console
   cd C:\Downloads
   ```

3. Pour installer l’API, tapez la commande suivante, puis appuyez sur Entrée :
    
   ```console
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. Une fois l’API installée, réinitialisez IIS en tapant la commande suivante et en appuyant sur Entrée :
    
   ```console
   iisreset
   ```

Une Exchange services Web est installé, vous devez configurer l’authentification de serveur à serveur entre SharePoint Server et Exchange Server. Pour ce faire, ouvrez d’abord SharePoint Management Shell et exécutez l’ensemble de commandes suivant :
  
```powershell
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> Utilisez l’URI de votre service de découverte automatique. N’utilisez pas l’exemple d’URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 . 
  
Une fois que vous avez créé l’émetteur de jeton et configuré le service de jeton, exécutez ces commandes, en vous assurez de remplacer l’URL de votre site SharePoint par l’URL d’exemple `http://atl-sharepoint-001` :
  
```powershell
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

Pour configurer l’authentification de serveur à serveur pour Exchange Server, ouvrez l’Exchange Management Shell et exécutez une commande semblable à celle-ci (en supposant que Exchange a été installé sur le lecteur C: et qu’il utilise le chemin d’accès du dossier par défaut) :
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

Après avoir configuré l’application partenaire, il est recommandé d’arrêter et de redémarrer Internet Information Services (IIS) sur tous vos serveurs de boîtes aux lettres Exchange et d’accès au client. Vous pouvez redémarrer les services Internet (IIS) à l’aide d’une commande ressemblant à celle-ci, qui permet de redémarrer le service sur l’ordinateur atl-exchange-001 :
  
```powershell
iisreset atl-exchange-001
```

Cette commande peut être exécuté à partir de l’Exchange Management Shell ou de toute autre fenêtre de commande.
  
Ensuite, exécutez une commande semblable à la suivante, qui donne à l’utilisateur spécifié (dans cet exemple, kenmyer) le droit d’exécuter la découverte sur Exchange :
  
```powershell
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

Une fois l’authentification de serveur à serveur établie entre Exchange et SharePoint, l’étape suivante consiste à créer un site eDiscovery dans SharePoint. Pour ce faire, exécutez des commandes similaires à celles-ci à partir de SharePoint Management Shell :
  
```powershell
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> « eDiscovery » est l’abréviation de « découverte électronique » et désigne généralement la recherche, dans des archives électroniques, d’éléments susceptibles d’être « raisonnablement conçus pour conduire à une preuve admissible » devant une cour de justice. 
  
Lorsque le nouveau site est prêt, l’étape suivante consiste à configurer Exchange Server pour qu’il agisse en tant qu’origine des résultats pour SharePoint. Pour ce faire, vous pouvez effectuer la procédure suivante à partir de la page SharePoint Administration centrale :
  
1. Dans la page Administration centrale, cliquez sur **Gérer les applications de service** et sur **Application de service de recherche**.
    
2. Dans la page Application de service de recherche : Administration de la recherche, cliquez sur **Origines des résultats**, puis sur **Nouvelle origine des résultats**.
    
3. Dans le volet **Nouvelle origine des résultats**, attribuez un nom à la nouvelle origine des résultats (par exemple, **Microsoft Exchange**) dans la zone **Nom**. Sélectionnez **Exchange** comme protocole d’origine des **résultats,** puis entrez l’URL source des services web pour votre serveur Exchange dans la **zone EXCHANGE URL source.** L’URL source doit ressembler à ceci :
    
    `https://atl-exchange-001.litwareinc.com/ews/exchange.asmx`
    
4. Vérifiez que **Utiliser la découverte automatique** n’est pas sélectionné, puis cliquez sur **OK**.
    
Enfin, créez un nouveau cas eDiscovery et un nouvel ensemble eDiscovery en effectuant la procédure suivante à partir du site de découverte SharePoint (par exemple, `https://atl-sharepoint-001/sites/discovery` :
  
1. Dans la page Contenu du site, cliquez sur **Créer un cas**.
    
2. Dans la page Contenu du site : Nouveau site SharePoint, entrez l’alias de messagerie de l’utilisateur (par exemple, **kenmyer**) dans la zone **Titre**, puis ajoutez cette URL dans la zone **Adresse du site web**. Vous obtenez alors une URL similaire à celle-ci :
    
    `https://atl-sharepoint-001/sites/eDiscovery/kenmyer`
    
3. Cliquez sur **Créer**.
    
4. Lorsque la page de l’ensemble eDiscovery apparaît, cliquez sur **nouvel élément** sous **Identité et préservation : Ensembles de découverte**.
    
5. Dans la page Nouveau : Ensemble de découverte, entrez l’alias de messagerie de l’utilisateur dans la zone **Nom de l’ensemble eDiscovery**. Entrez **eDiscovery Lync \\** _ dans la zone _ *Filtre** , puis cliquez sur Ajouter gérer les **&amp; sources.**
    
6. Dans la page Ajouter des sources, entrez l’alias de messagerie de l’utilisateur dans la &amp; première boîte de texte sous Boîtes aux **lettres.** Cliquez sur l’icône Vérifier la boîte aux lettres située en regard du manuel pour vérifier que SharePoint peut se connecter à la boîte aux lettres spécifiée.
    
7. Cliquez sur **OK**.
    
8. Dans la page Ensemble eDiscovery, cliquez sur **Enregistrer** pour enregistrer le nouvel ensemble eDiscovery.
    
À ce stade, vous pouvez effectuer une recherche dans la boîte aux lettres spécifiée (kenmyer) et/ou activer les In-Place de la même manière que pour tout autre contenu SharePoint ou origine des résultats.
  

