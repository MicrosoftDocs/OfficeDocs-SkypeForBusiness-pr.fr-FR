---
title: "Conf. Micros. SharePoint Server 2013 pr rech. données Microsoft LS 2013 arch."
TOCtitle: "Conf. Micros. SharePoint Server 2013 pr rech. données Microsoft LS 2013 arch."
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49891246
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de Microsoft SharePoint Server 2013 pour la recherche des données Microsoft Lync Server 2013 archivées

 

_**Dernière rubrique modifiée :** 2016-12-08_

L’un des principaux avantages qu’offre le stockage des transcriptions de conférence web et de message instantané dans Microsoft Exchange Server 2013 au lieu de Microsoft Lync Server 2013 réside dans le fait que le stockage des données au même endroit permet aux administrateurs d’utiliser un seul outil pour rechercher des données Exchange archivées et/ou des données Lync Server archivées. Comme toutes les données sont stockées au même endroit (Exchange), les outils utilisés pour rechercher des données Exchange archivées peuvent également rechercher des données Lync Server archivées.

L’outil Microsoft SharePoint Server 2013 vous aide à rechercher facilement des données archivées. Si vous souhaitez utiliser SharePoint pour rechercher des données Lync Server, vous devez d’abord suivre toutes les étapes nécessaires à la configuration de l’archivage d’Exchange dans Lync Server. Une fois Exchange 2013 et Lync Server 2013 intégrés, vous devez ensuite installer la version 2.0 de l’API des services web d’Exchange sur votre serveur SharePoint. Vous pouvez télécharger le programme d’installation de cette API à partir du Centre de téléchargement Microsoft ([http://go.microsoft.com/fwlink/?linkid=258305\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=258305%26clcid=0x40c)). Le fichier téléchargé (EWSManagedAPI.msi) peut être enregistré dans n’importe quel dossier de votre serveur SharePoint.

Une fois le fichier téléchargé, procédez comme suit sur le serveur SharePoint :

1.  Ouvrez une fenêtre Commande en cliquant sur **Démarrer**, sur **Tous les programmes**, sur **Accessoires**, en cliquant avec le bouton droit sur **Invite de commandes**, puis en cliquant sur **Exécuter en tant qu’administrateur**.

2.  Dans la fenêtre Commande, utilisez la commande **cd** pour modifier le répertoire actuel et définir à la place le dossier dans lequel le fichier EWSManagedAPI.msi a été enregistré. Par exemple, si vous avez enregistré le fichier dans C:\\Downloads, tapez la commande suivante dans la fenêtre Commande, puis appuyez sur ENTRÉE :
    
        cd C:\Downloads

3.  Pour installer l’API, tapez la commande suivante, puis appuyez sur ENTRÉE :
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  Une fois l’API installée, réinitialisez les services Internet (IIS) en tapant la commande suivante et en appuyant sur ENTRÉE :
    
        iisreset

Une fois les services web d’Exchange installés, vous devez ensuite configurer l’authentification de serveur à serveur entre SharePoint Server 2013 et Exchange 2013. Pour ce faire, ouvrez d’abord SharePoint 2013 Management Shell, puis exécutez les commandes suivantes :

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

> [!NOTE]  
> Utilisez l’URI de votre service de découverte automatique. N’utilisez pas l’URI d’exemple https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.

Après avoir créé l’émetteur de jetons et configuré le service d’émission de jetons, exécutez ces commandes en prenant soin d’utiliser l’URL de votre site SharePoint à la place de l’URL d’exemple http://atl-sharepoint-001:

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

Pour configurer l’authentification de serveur à serveur pour Exchange 2013, ouvrez Exchange Management Shell et exécutez une commande similaire à celle-ci (en supposant qu’Exchange a été installé sur le lecteur C: et qu’il utilise le chemin d’accès par défaut au dossier) :

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

Après avoir configuré l’application partenaire, il est recommandé d’arrêter et de redémarrer les services Internet (IIS) sur tous vos serveurs de boîte aux lettres et d’accès au client d’Exchange. Vous pouvez redémarrer les services Internet (IIS) à l’aide d’une commande ressemblant à celle-ci, qui permet de redémarrer le service sur l’ordinateur atl-exchange-001 :

    iisreset atl-exchange-001

Cette commande peut être exécutée à partir de Exchange Management Shell ou de n’importe quelle autre fenêtre Commande.

Exécutez ensuite une commande similaire à la suivante, ce qui permettra à l’utilisateur spécifié (kenmyer dans cet exemple) d’effectuer une opération de découverte dans Exchange :

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

Une fois l’authentification de serveur à serveur établie entre Exchange et SharePoint, créez un site eDiscovery dans SharePoint. Pour ce faire, vous pouvez exécuter des commandes semblables à celles-ci dans SharePoint Management Shell :

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

> [!NOTE]  
> « eDiscovery » est l’abréviation de « découverte électronique » et désigne généralement la recherche, dans des archives électroniques, d’éléments susceptibles d’être « raisonnablement conçus pour conduire à une preuve admissible » devant une cour de justice.

Une fois le nouveau site prêt, vous devez configurer Exchange 2013 pour qu’il se comporte comme origine des résultats pour SharePoint. Vous pouvez pour cela suivre la procédure ci-dessous dans la page Administration centrale de SharePoint 2013 :

1.  Dans la page Administration centrale, cliquez sur **Gérer les applications de service** et sur **Application de service de recherche**.

2.  Dans la page Application de service de recherche : Administration de la recherche, cliquez sur **Origines des résultats**, puis sur **Nouvelle origine des résultats**.

3.  Dans le volet **Nouvelle origine des résultats**, attribuez un nom à la nouvelle origine des résultats (par exemple, **Microsoft Exchange**) dans la zone **Nom**. Sélectionnez **Exchange** comme **Protocole** de l’origine des résultats, puis entrez l’URL source des services web de votre serveur Exchange dans la zone **URL source d’Exchange**. L’URL source doit ressembler à ceci :
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  Vérifiez que **Utiliser la découverte automatique** n’est pas sélectionné, puis cliquez sur **OK**.

Enfin, créez un nouveau cas eDiscovery et un nouvel ensemble eDiscovery en procédant comme suit dans le site Discovery de SharePoint (par exemple, https://atl-sharepoint-001/sites/discovery):

1.  Dans la page Contenu du site, cliquez sur **Créer un cas**.

2.  Dans la page Contenu du site : Nouveau site SharePoint, entrez l’alias de messagerie de l’utilisateur (par exemple, **kenmyer**) dans la zone **Titre**, puis ajoutez cette URL dans la zone **Adresse du site web**. Vous obtenez alors une URL similaire à celle-ci :
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  Cliquez sur **Créer**.

4.  Lorsque la page de l’ensemble eDiscovery apparaît, cliquez sur **nouvel élément** sous **Identité et préservation : Ensembles de découverte**.

5.  Dans la page Nouveau : Ensemble de découverte, entrez l’alias de messagerie de l’utilisateur dans la zone **Nom de l’ensemble eDiscovery**. Entrez **eDiscovery Lync\*** dans la zone **Filtrer**, puis cliquez sur **Ajouter & Gérer les sources**.

6.  Dans la page Ajouter & Gérer les sources, entrez l’alias de messagerie de l’utilisateur dans la première zone de texte sous **Boîtes aux lettres**. Cliquez sur l’icône Vérifier la boîte aux lettres située en regard du manuel pour vérifier que SharePoint peut se connecter à la boîte aux lettres spécifiée.

7.  Cliquez sur **OK**.

8.  Dans la page Ensemble eDiscovery, cliquez sur **Enregistrer** pour enregistrer le nouvel ensemble eDiscovery.

À ce stade, vous pouvez rechercher la boîte aux lettres spécifiée (kenmyer) et/ou activer les archives permanentes tout comme vous le feriez pour n’importe quel autre contenu SharePoint ou origine des résultats.

