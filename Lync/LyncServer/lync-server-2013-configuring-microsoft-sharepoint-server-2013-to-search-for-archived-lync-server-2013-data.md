---
title: 'Lync Server 2013 : configuration de Microsoft SharePoint Server 2013 pour rechercher des données archivées Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SharePoint Server 2013 to search for archived Lync Server 2013 data
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49733566
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8debab39073bf31f509ec504f944c8e4c7a9dfc3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a>Configuration de Microsoft SharePoint Server 2013 pour rechercher des données archivées Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-04_

L’un des principaux avantages du stockage des transcriptions de messagerie instantanée et de conférence Web dans Microsoft Exchange Server 2013 au lieu de Microsoft Lync Server 2013 est le fait que le stockage de données dans le même emplacement permet aux administrateurs d’utiliser un seul outil pour rechercher des données Exchange archivées et/ou des données Lync Server archivées. Étant donné que toutes les données sont stockées au même endroit (Exchange), tous les outils pouvant Rechercher des données Exchange archivées peuvent également rechercher des données Lync Server archivées.

Microsoft SharePoint Server 2013 est un outil qui facilite la recherche des données archivées. Si vous souhaitez utiliser SharePoint pour rechercher des données Lync Server, vous devez d’abord effectuer toutes les étapes nécessaires à la configuration de l’archivage Exchange dans Lync Server. Une fois les services Exchange 2013 et Lync Server 2013 correctement intégrés, vous devez installer la version 2,0 de l’API managée des services Web Exchange sur votre serveur SharePoint Server ; le programme d’installation de cette API peut être téléchargé à partir du centre de[http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305)téléchargement Microsoft (). Le fichier téléchargé (le fichier ewsmanagedapi. msi) peut être enregistré dans n’importe quel dossier sur votre serveur SharePoint.

Une fois le fichier téléchargé, procédez comme suit sur le serveur SharePoint :

1.  Ouvrez une fenêtre Commande en cliquant sur **Démarrer**, sur **Tous les programmes**, sur **Accessoires**, en cliquant avec le bouton droit sur **Invite de commandes**, puis en cliquant sur **Exécuter en tant qu’administrateur**.

2.  Dans la fenêtre Commande, utilisez la commande **cd** pour modifier le répertoire actuel et définir à la place le dossier dans lequel le fichier EWSManagedAPI.msi a été enregistré. Par exemple, si vous avez enregistré le fichier dans C :\\downloads, tapez la commande suivante dans la fenêtre de commande, puis appuyez sur entrée :
    
        cd C:\Downloads

3.  Pour installer l’API, tapez la commande suivante, puis appuyez sur ENTRÉE :
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  Une fois l’API installée, réinitialisez les services Internet (IIS) en tapant la commande suivante et en appuyant sur ENTRÉE :
    
        iisreset

Une fois les services Web Exchange installés, vous devez configurer l’authentification de serveur à serveur entre SharePoint Server 2013 et Exchange 2013. Pour ce faire, ouvrez d’abord SharePoint 2013 Management Shell et exécutez la commande suivante :

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> Utilisez l’URI de votre service de découverte automatique. N’utilisez pas l’exemple d' https://autodiscover.litwareinc.com/autodiscover/metadata/json/1URI.



</div>

Une fois que vous avez créé l’émetteur de jeton et configuré le service de jeton, exécutez ces commandes, en vous assurant de remplacer l’URL de votre site SharePoint par l’exemple d’URL.http://atl-sharepoint-001:

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

Pour configurer l’authentification de serveur à serveur pour Exchange 2013, ouvrez l’environnement de commande Exchange Management Shell et exécutez une commande semblable à celle-ci (en supposant qu’Exchange a été installé sur le lecteur C : et qu’il utilise le chemin d’accès du dossier par défaut) :

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

Après avoir configuré l’application partenaire, il est recommandé d’arrêter et de redémarrer les services Internet (IIS) sur tous vos serveurs de boîtes aux lettres et d’accès au client Exchange. Vous pouvez redémarrer les services Internet (IIS) à l’aide d’une commande ressemblant à celle-ci, qui permet de redémarrer le service sur l’ordinateur atl-exchange-001 :

    iisreset atl-exchange-001

Cette commande peut être exécutée dans l’environnement de commande Exchange Management Shell ou dans une autre fenêtre de commande.

Ensuite, exécutez une commande semblable à la suivante, qui donne à l’utilisateur spécifié (dans cet exemple, kenmyer) le droit de procéder à la découverte sur Exchange :

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

Une fois l’authentification de serveur à serveur établie entre Exchange et SharePoint, l’étape suivante consiste à créer un site eDiscovery dans SharePoint. Cela peut être réalisé en exécutant des commandes similaires à celles-ci à partir de SharePoint Management Shell :

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> « eDiscovery » est l’abréviation de « découverte électronique » et désigne généralement la recherche, dans des archives électroniques, d’éléments susceptibles d’être « raisonnablement conçus pour conduire à une preuve admissible » devant une cour de justice.



</div>

Lorsque le nouveau site est prêt, l’étape suivante consiste à configurer Exchange 2013 comme origine des résultats pour SharePoint. Pour ce faire, procédez comme suit à partir de la page Administration centrale de SharePoint 2013 :

1.  Dans la page Administration centrale, cliquez sur **Gérer les applications de service** et sur **Application de service de recherche**.

2.  Dans la page Application de service de recherche : Administration de la recherche, cliquez sur **Origines des résultats**, puis sur **Nouvelle origine des résultats**.

3.  Dans le volet **Nouvelle origine des résultats**, attribuez un nom à la nouvelle origine des résultats (par exemple, **Microsoft Exchange**) dans la zone **Nom**. Sélectionnez **Exchange** comme **protocole**d’origine des résultats, puis entrez l’URL de la source des services Web pour votre serveur Exchange dans la zone **URL source Exchange** . L’URL source doit ressembler à ceci :
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  Vérifiez que **Utiliser la découverte automatique** n’est pas sélectionné, puis cliquez sur **OK**.

Enfin, créez un nouveau cas eDiscovery et un nouvel ensemble eDiscovery en effectuant la procédure suivante à partir du site de découverte SharePoint (par exemple,https://atl-sharepoint-001/sites/discovery):

1.  Dans la page Contenu du site, cliquez sur **Créer un cas**.

2.  Dans la page Contenu du site : Nouveau site SharePoint, entrez l’alias de messagerie de l’utilisateur (par exemple, **kenmyer**) dans la zone **Titre**, puis ajoutez cette URL dans la zone **Adresse du site web**. Vous obtenez alors une URL similaire à celle-ci :
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  Cliquez sur **Créer**.

4.  Lorsque la page de l’ensemble eDiscovery apparaît, cliquez sur **nouvel élément** sous **Identité et préservation : Ensembles de découverte**.

5.  Dans la page Nouveau : Ensemble de découverte, entrez l’alias de messagerie de l’utilisateur dans la zone **Nom de l’ensemble eDiscovery**. Entrez **Lync\* eDiscovery** dans la zone **filtre** , puis cliquez sur **Ajouter & gérer les sources**.

6.  Dans la page Ajouter & Gérer les sources, entrez l’alias de messagerie de l’utilisateur dans la première zone de texte sous **Boîtes aux lettres**. Cliquez sur l’icône Vérifier la boîte aux lettres située en regard du manuel pour vérifier que SharePoint peut se connecter à la boîte aux lettres spécifiée.

7.  Cliquez sur **OK**.

8.  Dans la page Ensemble eDiscovery, cliquez sur **Enregistrer** pour enregistrer le nouvel ensemble eDiscovery.

À ce stade, vous pouvez rechercher dans la boîte aux lettres spécifiée (kenmyer) et/ou activer les conservations inaltérables de la même façon que vous le feriez pour n’importe quel autre contenu SharePoint ou origine des résultats.

</div>

<span> </span>

</div>

</div>

</div>

