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
ms.openlocfilehash: 04e9599e0790c3d3468273ba27ea26f28ed3d766
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a><span data-ttu-id="898b8-102">Configuration de Microsoft SharePoint Server 2013 pour rechercher des données archivées Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="898b8-102">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="898b8-103">_**Dernière modification de la rubrique :** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="898b8-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="898b8-104">L’un des principaux avantages du stockage des transcriptions de messagerie instantanée et de conférence Web dans Microsoft Exchange Server 2013 au lieu de Microsoft Lync Server 2013 est le fait que le stockage de données dans le même emplacement permet aux administrateurs d’utiliser un seul outil pour rechercher des données Exchange archivées et/ou des données Lync Server archivées.</span><span class="sxs-lookup"><span data-stu-id="898b8-104">One of the major advantages to storing instant messaging and Web conferencing transcripts in Microsoft Exchange Server 2013 instead of Microsoft Lync Server 2013 is the fact that storing data in the same location enables administrators to use a single tool to search for archived Exchange data and/or archived Lync Server data.</span></span> <span data-ttu-id="898b8-105">Étant donné que toutes les données sont stockées au même endroit (Exchange), tous les outils pouvant Rechercher des données Exchange archivées peuvent également rechercher des données Lync Server archivées.</span><span class="sxs-lookup"><span data-stu-id="898b8-105">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Lync Server data.</span></span>

<span data-ttu-id="898b8-106">Microsoft SharePoint Server 2013 est un outil qui facilite la recherche des données archivées.</span><span class="sxs-lookup"><span data-stu-id="898b8-106">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="898b8-107">Si vous souhaitez utiliser SharePoint pour rechercher des données Lync Server, vous devez d’abord effectuer toutes les étapes nécessaires à la configuration de l’archivage Exchange dans Lync Server.</span><span class="sxs-lookup"><span data-stu-id="898b8-107">If you would like to use SharePoint to search for Lync Server data, you must first complete all the steps involved in configuring Exchange archiving in Lync Server.</span></span> <span data-ttu-id="898b8-108">Une fois les services Exchange 2013 et Lync Server 2013 correctement intégrés, vous devez installer la version 2,0 de l’API managée des services Web Exchange sur votre serveur SharePoint Server ; le programme d’installation de cette API peut être téléchargé à partir du centre de[https://go.microsoft.com/fwlink/p/?LinkId=258305](https://go.microsoft.com/fwlink/p/?linkid=258305)téléchargement Microsoft ().</span><span class="sxs-lookup"><span data-stu-id="898b8-108">After Exchange 2013 and Lync Server 2013 have been successfully integrated you must then install the Exchange Web Services Managed API Version 2.0 on your SharePoint Server; the setup program for that API can be downloaded from the Microsoft Downloads Center ([https://go.microsoft.com/fwlink/p/?LinkId=258305](https://go.microsoft.com/fwlink/p/?linkid=258305)).</span></span> <span data-ttu-id="898b8-109">Le fichier téléchargé (le fichier ewsmanagedapi. msi) peut être enregistré dans n’importe quel dossier sur votre serveur SharePoint.</span><span class="sxs-lookup"><span data-stu-id="898b8-109">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>

<span data-ttu-id="898b8-110">Une fois le fichier téléchargé, procédez comme suit sur le serveur SharePoint :</span><span class="sxs-lookup"><span data-stu-id="898b8-110">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>

1.  <span data-ttu-id="898b8-111">Ouvrez une fenêtre Commande en cliquant sur **Démarrer**, sur **Tous les programmes**, sur **Accessoires**, en cliquant avec le bouton droit sur **Invite de commandes**, puis en cliquant sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="898b8-111">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>

2.  <span data-ttu-id="898b8-112">Dans la fenêtre Commande, utilisez la commande **cd** pour modifier le répertoire actuel et définir à la place le dossier dans lequel le fichier EWSManagedAPI.msi a été enregistré.</span><span class="sxs-lookup"><span data-stu-id="898b8-112">In the command window, use the **cd** command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="898b8-113">Par exemple, si vous avez enregistré le fichier dans C :\\downloads, tapez la commande suivante dans la fenêtre de commande, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="898b8-113">For example, if you have saved the file to C:\\Downloads type the following command in the command window and then press ENTER:</span></span>
    
        cd C:\Downloads

3.  <span data-ttu-id="898b8-114">Pour installer l’API, tapez la commande suivante, puis appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="898b8-114">To install the API, type the following command then press ENTER:</span></span>
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  <span data-ttu-id="898b8-115">Une fois l’API installée, réinitialisez les services Internet (IIS) en tapant la commande suivante et en appuyant sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="898b8-115">After the API has been installed, reset IIS by typing the following command and pressing ENTER:</span></span>
    
        iisreset

<span data-ttu-id="898b8-116">Une fois les services Web Exchange installés, vous devez configurer l’authentification de serveur à serveur entre SharePoint Server 2013 et Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="898b8-116">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="898b8-117">Pour ce faire, ouvrez d’abord SharePoint 2013 Management Shell et exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="898b8-117">To do this, first open the SharePoint 2013 Management Shell and run the following set of command:</span></span>

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> <span data-ttu-id="898b8-118">Utilisez l’URI de votre service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="898b8-118">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="898b8-119">N’utilisez pas l’exemple d' https://autodiscover.litwareinc.com/autodiscover/metadata/json/1URI.</span><span class="sxs-lookup"><span data-stu-id="898b8-119">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span>



</div>

<span data-ttu-id="898b8-120">Une fois que vous avez créé l’émetteur de jeton et configuré le service de jeton, exécutez ces commandes, en vous assurant de remplacer l’URL de votre site SharePoint par l’exemple d’URL.http://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="898b8-120">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

<span data-ttu-id="898b8-121">Pour configurer l’authentification de serveur à serveur pour Exchange 2013, ouvrez l’environnement de commande Exchange Management Shell et exécutez une commande semblable à celle-ci (en supposant qu’Exchange a été installé sur le lecteur C : et qu’il utilise le chemin d’accès du dossier par défaut) :</span><span class="sxs-lookup"><span data-stu-id="898b8-121">To configure server-to-server authentication for Exchange 2013, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

<span data-ttu-id="898b8-122">Après avoir configuré l’application partenaire, il est recommandé d’arrêter et de redémarrer les services Internet (IIS) sur tous vos serveurs de boîtes aux lettres et d’accès au client Exchange.</span><span class="sxs-lookup"><span data-stu-id="898b8-122">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="898b8-123">Vous pouvez redémarrer les services Internet (IIS) à l’aide d’une commande ressemblant à celle-ci, qui permet de redémarrer le service sur l’ordinateur atl-exchange-001 :</span><span class="sxs-lookup"><span data-stu-id="898b8-123">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="898b8-124">Cette commande peut être exécutée dans l’environnement de commande Exchange Management Shell ou dans une autre fenêtre de commande.</span><span class="sxs-lookup"><span data-stu-id="898b8-124">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>

<span data-ttu-id="898b8-125">Ensuite, exécutez une commande semblable à la suivante, qui donne à l’utilisateur spécifié (dans cet exemple, kenmyer) le droit de procéder à la découverte sur Exchange :</span><span class="sxs-lookup"><span data-stu-id="898b8-125">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

<span data-ttu-id="898b8-126">Une fois l’authentification de serveur à serveur établie entre Exchange et SharePoint, l’étape suivante consiste à créer un site eDiscovery dans SharePoint.</span><span class="sxs-lookup"><span data-stu-id="898b8-126">After server-to-server authentication has been established between Exchange and SharePoint your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="898b8-127">Cela peut être réalisé en exécutant des commandes similaires à celles-ci à partir de SharePoint Management Shell :</span><span class="sxs-lookup"><span data-stu-id="898b8-127">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> <span data-ttu-id="898b8-128">« eDiscovery » est l’abréviation de « découverte électronique » et désigne généralement la recherche, dans des archives électroniques, d’éléments susceptibles d’être « raisonnablement conçus pour conduire à une preuve admissible » devant une cour de justice.</span><span class="sxs-lookup"><span data-stu-id="898b8-128">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span>



</div>

<span data-ttu-id="898b8-129">Lorsque le nouveau site est prêt, l’étape suivante consiste à configurer Exchange 2013 comme origine des résultats pour SharePoint.</span><span class="sxs-lookup"><span data-stu-id="898b8-129">When the new site is ready, the next step is to configure Exchange 2013 to act as a result source for SharePoint.</span></span> <span data-ttu-id="898b8-130">Pour ce faire, procédez comme suit à partir de la page Administration centrale de SharePoint 2013 :</span><span class="sxs-lookup"><span data-stu-id="898b8-130">You can do that by completing the following procedure from the SharePoint 2013 Central Administration page:</span></span>

1.  <span data-ttu-id="898b8-131">Dans la page Administration centrale, cliquez sur **Gérer les applications de service** et sur **Application de service de recherche**.</span><span class="sxs-lookup"><span data-stu-id="898b8-131">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>

2.  <span data-ttu-id="898b8-132">Dans la page Application de service de recherche : Administration de la recherche, cliquez sur **Origines des résultats**, puis sur **Nouvelle origine des résultats**.</span><span class="sxs-lookup"><span data-stu-id="898b8-132">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>

3.  <span data-ttu-id="898b8-133">Dans le volet **Nouvelle origine des résultats**, attribuez un nom à la nouvelle origine des résultats (par exemple, **Microsoft Exchange**) dans la zone **Nom**.</span><span class="sxs-lookup"><span data-stu-id="898b8-133">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="898b8-134">Sélectionnez **Exchange** comme **protocole**d’origine des résultats, puis entrez l’URL de la source des services Web pour votre serveur Exchange dans la zone **URL source Exchange** .</span><span class="sxs-lookup"><span data-stu-id="898b8-134">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="898b8-135">L’URL source doit ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="898b8-135">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  <span data-ttu-id="898b8-136">Vérifiez que **Utiliser la découverte automatique** n’est pas sélectionné, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="898b8-136">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>

<span data-ttu-id="898b8-137">Enfin, créez un nouveau cas eDiscovery et un nouvel ensemble eDiscovery en effectuant la procédure suivante à partir du site de découverte SharePoint (par exemple,https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="898b8-137">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>

1.  <span data-ttu-id="898b8-138">Dans la page Contenu du site, cliquez sur **Créer un cas**.</span><span class="sxs-lookup"><span data-stu-id="898b8-138">On the Site Contents page click **Create a new case**.</span></span>

2.  <span data-ttu-id="898b8-p110">Dans la page Contenu du site : Nouveau site SharePoint, entrez l’alias de messagerie de l’utilisateur (par exemple, **kenmyer**) dans la zone **Titre**, puis ajoutez cette URL dans la zone **Adresse du site web**. Vous obtenez alors une URL similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="898b8-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  <span data-ttu-id="898b8-141">Cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="898b8-141">Click **Create**.</span></span>

4.  <span data-ttu-id="898b8-142">Lorsque la page de l’ensemble eDiscovery apparaît, cliquez sur **nouvel élément** sous **Identité et préservation : Ensembles de découverte**.</span><span class="sxs-lookup"><span data-stu-id="898b8-142">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>

5.  <span data-ttu-id="898b8-143">Dans la page Nouveau : Ensemble de découverte, entrez l’alias de messagerie de l’utilisateur dans la zone **Nom de l’ensemble eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="898b8-143">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="898b8-144">Entrez **Lync\* eDiscovery** dans la zone **filtre** , puis cliquez sur **Ajouter & gérer les sources**.</span><span class="sxs-lookup"><span data-stu-id="898b8-144">Enter **eDiscovery Lync\*** in the **Filter** box and then click **Add & Manage Sources**.</span></span>

6.  <span data-ttu-id="898b8-p112">Dans la page Ajouter & Gérer les sources, entrez l’alias de messagerie de l’utilisateur dans la première zone de texte sous **Boîtes aux lettres**. Cliquez sur l’icône Vérifier la boîte aux lettres située en regard du manuel pour vérifier que SharePoint peut se connecter à la boîte aux lettres spécifiée.</span><span class="sxs-lookup"><span data-stu-id="898b8-p112">On the Add & Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**. Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>

7.  <span data-ttu-id="898b8-147">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="898b8-147">Click **OK**.</span></span>

8.  <span data-ttu-id="898b8-148">Dans la page Ensemble eDiscovery, cliquez sur **Enregistrer** pour enregistrer le nouvel ensemble eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="898b8-148">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>

<span data-ttu-id="898b8-149">À ce stade, vous pouvez rechercher dans la boîte aux lettres spécifiée (kenmyer) et/ou activer les conservations inaltérables de la même façon que vous le feriez pour n’importe quel autre contenu SharePoint ou origine des résultats.</span><span class="sxs-lookup"><span data-stu-id="898b8-149">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

