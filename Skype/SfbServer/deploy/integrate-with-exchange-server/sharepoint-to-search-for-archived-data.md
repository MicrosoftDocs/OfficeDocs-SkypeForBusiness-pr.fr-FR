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
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a><span data-ttu-id="f4d2f-103">Configurer SharePoint Server pour rechercher des données Skype Entreprise archivées</span><span class="sxs-lookup"><span data-stu-id="f4d2f-103">Configure SharePoint Server to search for archived Skype for Business data</span></span>
 
<span data-ttu-id="f4d2f-104">**Résumé :** Configurer le serveur SharePoint pour rechercher des données archivées par 2016 d’Exchange Server ou Exchange Server 2013 et Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-104">**Summary:** Configure SharePoint Server to search for data archived by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f4d2f-105">Un des principaux avantages de stocker les transcriptions des conférences Web et messagerie instantanée dans Exchange Server 2016 ou 2013 d’Exchange Server au lieu de Skype pour Business Server 2015 est que le stockage de données dans le même emplacement permet aux administrateurs d’utiliser un seul outil pour recherche de données archivées de Exchange et/ou Skype archivé pour les données du serveur de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-105">One of the major advantages to storing instant messaging and Web conferencing transcripts in Exchange Server 2016 or Exchange Server 2013 instead of Skype for Business Server 2015 is that storing data in the same location allows administrators to use a single tool to search for archived Exchange data and/or archived Skype for Business Server data.</span></span> <span data-ttu-id="f4d2f-106">Parce que toutes les données sont stockées dans le même placent (Exchange) n’importe quel outil que vous pouvez rechercher des données archivées de Exchange peut également rechercher Skype archivé pour les données du serveur de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-106">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Skype for Business Server data.</span></span>
  
<span data-ttu-id="f4d2f-107">Un outil qui facilite la recherche de données archivées est Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-107">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="f4d2f-108">Si vous souhaitez utiliser SharePoint pour rechercher les Skype pour données Business Server, vous devez d’abord effectuer toutes les étapes impliquées dans la configuration de l’archivage Exchange dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-108">If you would like to use SharePoint to search for Skype for Business Server data, you must first complete all the steps involved in configuring Exchange archiving in Skype for Business Server.</span></span> <span data-ttu-id="f4d2f-109">Une fois Skype pour Business Server et Exchange Server ont été intégrés avec succès, vous devez ensuite installer Exchange [Web Services Managed API](https://go.microsoft.com/fwlink/p/?LinkId=258305) sur votre serveur SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-109">After Exchange Server and Skype for Business Server have been successfully integrated, you must then install the Exchange [Web Services Managed API](https://go.microsoft.com/fwlink/p/?LinkId=258305) on your SharePoint Server.</span></span> <span data-ttu-id="f4d2f-110">Vous pouvez enregistrer le fichier téléchargé (EWSManagedAPI.msi) dans n’importe quel dossier sur votre serveur SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-110">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>
  
<span data-ttu-id="f4d2f-111">Une fois le fichier téléchargé, procédez comme suit sur le serveur SharePoint :</span><span class="sxs-lookup"><span data-stu-id="f4d2f-111">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>
  
1. <span data-ttu-id="f4d2f-112">Ouvrez une fenêtre Commande en cliquant sur **Démarrer** > **Tous les programmes** > **Accessoires**, puis en cliquant avec le bouton droit sur **Invite de commandes** et enfin sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-112">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>
    
2. <span data-ttu-id="f4d2f-113">Dans la fenêtre de commande, utilisez la commande cd pour changer le répertoire en cours dans le dossier où le fichier EWSManagedAPI.msi a été enregistré.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-113">In the command window, use the cd command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="f4d2f-114">Par exemple, si vous avez enregistré le fichier à C:\Downloads tapez la commande suivante dans la fenêtre de commande et appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="f4d2f-114">For example, if you have saved the file to C:\Downloads type the following command in the command window and then press Enter:</span></span>
    
   ```
   cd C:\Downloads
   ```

3. <span data-ttu-id="f4d2f-115">Pour installer l’API, tapez la commande suivante, puis appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="f4d2f-115">To install the API, type the following command then press Enter:</span></span>
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. <span data-ttu-id="f4d2f-116">Une fois que l’API a été installé, réinitialisez IIS en tapant la commande suivante et en appuyant sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="f4d2f-116">After the API has been installed, reset IIS by typing the following command and pressing Enter:</span></span>
    
   ```
   iisreset
   ```

<span data-ttu-id="f4d2f-117">Après avoir installé les Services Web Exchange, vous devez alors configurer l’authentification de serveur à serveur entre SharePoint Server et Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-117">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server and Exchange Server.</span></span> <span data-ttu-id="f4d2f-118">Pour ce faire, ouvrir en premier le Shell de gestion SharePoint et exécutez l’ensemble des commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="f4d2f-118">To do this, first open the SharePoint Management Shell and run the following set of commands:</span></span>
  
```
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> <span data-ttu-id="f4d2f-119">Utilisez l’URI de votre service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-119">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="f4d2f-120">N’utilisez pas l’exemple d’URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-120">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span> 
  
<span data-ttu-id="f4d2f-121">Après avoir créé l’émetteur de jeton et configuré le service de jeton, exécuter ces commandes, en veillant à remplacer par l’URL de votre site SharePoint pour l’URL de l’exemplehttp://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="f4d2f-121">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

<span data-ttu-id="f4d2f-122">Pour configurer l’authentification de serveur à serveur pour Exchange Server, ouvrez Exchange Management Shell et exécutez une commande similaire à celle-ci (en supposant que Exchange a été installé sur le lecteur C: et qu’il utilise le chemin d’accès du dossier par défaut) :</span><span class="sxs-lookup"><span data-stu-id="f4d2f-122">To configure server-to-server authentication for Exchange Server, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

<span data-ttu-id="f4d2f-123">Après avoir configuré l’application partenaire il est recommandé d’arrêter et de redémarrer Internet Information Services (IIS) sur tous vos boîtes aux lettres et client accès aux serveurs Exchange.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-123">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="f4d2f-124">Vous pouvez redémarrer IIS à l’aide d’une commande semblable à la suivante, qui redémarre le service sur l’ordinateur atl-exchange-001 :</span><span class="sxs-lookup"><span data-stu-id="f4d2f-124">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```
iisreset atl-exchange-001
```

<span data-ttu-id="f4d2f-125">Cette commande peut être exécutée à partir d’Exchange Management Shell ou de toute autre fenêtre de commande.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-125">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>
  
<span data-ttu-id="f4d2f-126">Ensuite, exécutez une commande semblable à la suivante, qui accorde à l’utilisateur (dans cet exemple, kenmyer) le droit de faire la découverte sur Exchange :</span><span class="sxs-lookup"><span data-stu-id="f4d2f-126">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

<span data-ttu-id="f4d2f-127">Après que l’authentification du serveur-serveur a été établie entre Exchange et SharePoint, l’étape suivante est de créer un site d’e-Discovery dans SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-127">After server-to-server authentication has been established between Exchange and SharePoint, your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="f4d2f-128">Qui peut être effectuée en exécutant des commandes similaires aux suivants à partir du Shell de gestion SharePoint :</span><span class="sxs-lookup"><span data-stu-id="f4d2f-128">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> <span data-ttu-id="f4d2f-129">« eDiscovery » est l’abréviation de « découverte électronique » et désigne généralement la recherche, dans des archives électroniques, d’éléments susceptibles d’être « raisonnablement conçus pour conduire à une preuve admissible » devant une cour de justice.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-129">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span> 
  
<span data-ttu-id="f4d2f-130">Lorsque le nouveau site est prêt, l’étape suivante consiste à configurer Exchange Server pour agir ainsi source de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-130">When the new site is ready, the next step is to configure Exchange Server to act as a result source for SharePoint.</span></span> <span data-ttu-id="f4d2f-131">Vous pouvez faire qui en effectuant la procédure suivante à partir de la page Administration centrale de SharePoint :</span><span class="sxs-lookup"><span data-stu-id="f4d2f-131">You can do that by completing the following procedure from the SharePoint Central Administration page:</span></span>
  
1. <span data-ttu-id="f4d2f-132">Dans la page Administration centrale, cliquez sur **Gérer les applications de service** et sur **Application de service de recherche**.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-132">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>
    
2. <span data-ttu-id="f4d2f-133">Dans la page Application de service de recherche : Administration de la recherche, cliquez sur **Origines des résultats**, puis sur **Nouvelle origine des résultats**.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-133">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>
    
3. <span data-ttu-id="f4d2f-134">Dans le volet **Nouvelle origine des résultats**, attribuez un nom à la nouvelle origine des résultats (par exemple, **Microsoft Exchange**) dans la zone **Nom**.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-134">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="f4d2f-135">Sélectionnez **Exchange** comme source de résultats **protocole**et puis entrez l’URL source des services web pour votre serveur Exchange dans la zone **URL de la Source change** .</span><span class="sxs-lookup"><span data-stu-id="f4d2f-135">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="f4d2f-136">L’URL source doit ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="f4d2f-136">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. <span data-ttu-id="f4d2f-137">Vérifiez que l’option **Utiliser la découverte automatique** n’est pas sélectionnée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-137">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>
    
<span data-ttu-id="f4d2f-138">Enfin, créez un nouveau dossier d’e-Discovery et un nouveau eDiscovery en effectuant la procédure suivante à partir du site de découverte de SharePoint (par exemple, la valeurhttps://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="f4d2f-138">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>
  
1. <span data-ttu-id="f4d2f-139">Dans la page Contenu du site, cliquez sur **Créer un cas**.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-139">On the Site Contents page click **Create a new case**.</span></span>
    
2. <span data-ttu-id="f4d2f-p110">Dans la page Contenu du site : Nouveau site SharePoint, entrez l’alias de messagerie de l’utilisateur (par exemple, **kenmyer**) dans la zone **Titre**, puis ajoutez cette URL dans la zone **Adresse du site web**. Vous obtenez alors une URL similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="f4d2f-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. <span data-ttu-id="f4d2f-142">Cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-142">Click **Create**.</span></span>
    
4. <span data-ttu-id="f4d2f-143">Lorsque la page de l’ensemble eDiscovery apparaît, cliquez sur **nouvel élément** sous **Identité et préservation : Ensembles de découverte**.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-143">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>
    
5. <span data-ttu-id="f4d2f-144">Dans la page Nouveau : Ensemble de découverte, entrez l’alias de messagerie de l’utilisateur dans la zone **Nom de l’ensemble eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-144">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="f4d2f-145">Entrez \*\*eDiscovery Lync\* \*\* dans le **filtre** de la zone, puis cliquez sur **Ajouter &amp; gérer les Sources de**.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-145">Enter **eDiscovery Lync\*** in the **Filter** box and then click **Add &amp; Manage Sources**.</span></span>
    
6. <span data-ttu-id="f4d2f-146">Dans la zone Ajouter &amp; gérer les Sources de la page, entrez l’alias de messagerie de l’utilisateur dans la première zone de texte sous **boîtes aux lettres**.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-146">On the Add &amp; Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**.</span></span> <span data-ttu-id="f4d2f-147">Cliquez sur l’icône Vérifier la boîte aux lettres située en regard du manuel pour vérifier que SharePoint peut se connecter à la boîte aux lettres spécifiée.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-147">Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>
    
7. <span data-ttu-id="f4d2f-148">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-148">Click **OK**.</span></span>
    
8. <span data-ttu-id="f4d2f-149">Dans la page Ensemble eDiscovery, cliquez sur **Enregistrer** pour enregistrer le nouvel ensemble eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-149">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>
    
<span data-ttu-id="f4d2f-150">À ce stade, vous pouvez rechercher la boîte aux lettres spécifiée (kenmyer) et/ou activer Place conserve de la même façon que vous le feriez pour n’importe quel autre contenu ou résultat source de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f4d2f-150">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>
  

