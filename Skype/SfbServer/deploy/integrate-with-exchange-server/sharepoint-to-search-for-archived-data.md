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
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a><span data-ttu-id="12c9e-103">Configurer SharePoint Server pour rechercher des données Skype Entreprise archivées</span><span class="sxs-lookup"><span data-stu-id="12c9e-103">Configure SharePoint Server to search for archived Skype for Business data</span></span>
 
<span data-ttu-id="12c9e-104">**Résumé :** Configurer SharePoint Server pour rechercher des données archivées par Exchange Server 2016 ou Exchange Server 2013 et Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="12c9e-104">**Summary:** Configure SharePoint Server to search for data archived by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="12c9e-105">Un des principaux avantages pour le stockage des transcriptions de conférence Web et de messagerie instantanée dans Exchange Server au lieu de Skype pour Business Server est que le stockage des données dans le même emplacement permet aux administrateurs d’utiliser un seul outil pour rechercher des données Exchange archivées et/ou archivée Skype pour les données métiers.</span><span class="sxs-lookup"><span data-stu-id="12c9e-105">One of the major advantages to storing instant messaging and Web conferencing transcripts in Exchange Server instead of Skype for Business Server is that storing data in the same location allows administrators to use a single tool to search for archived Exchange data and/or archived Skype for Business Server data.</span></span> <span data-ttu-id="12c9e-106">Étant donné que toutes les données sont stockées dans la même (Exchange) n’importe quel outil que vous pouvez rechercher des données archivées Exchange peut également rechercher archivée Skype pour les données métiers.</span><span class="sxs-lookup"><span data-stu-id="12c9e-106">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Skype for Business Server data.</span></span>
  
<span data-ttu-id="12c9e-107">Un outil qui permet de rechercher des données archivées est Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="12c9e-107">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="12c9e-108">Si vous souhaitez utiliser SharePoint pour rechercher Skype pour les données métiers, vous devez tout d’abord effectuer toutes les étapes nécessaires à la configuration d’archivage Exchange dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="12c9e-108">If you would like to use SharePoint to search for Skype for Business Server data, you must first complete all the steps involved in configuring Exchange archiving in Skype for Business Server.</span></span> <span data-ttu-id="12c9e-109">Une fois Skype pour Business Server et Exchange Server ont été intégrées avec succès, vous devez installer puis [l’API managée des Services Web](https://go.microsoft.com/fwlink/p/?LinkId=258305) d' Exchange sur votre serveur SharePoint.</span><span class="sxs-lookup"><span data-stu-id="12c9e-109">After Exchange Server and Skype for Business Server have been successfully integrated, you must then install the Exchange [Web Services Managed API](https://go.microsoft.com/fwlink/p/?LinkId=258305) on your SharePoint Server.</span></span> <span data-ttu-id="12c9e-110">Vous pouvez enregistrer le fichier téléchargé (EWSManagedAPI.msi) dans n’importe quel dossier sur votre serveur SharePoint.</span><span class="sxs-lookup"><span data-stu-id="12c9e-110">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>
  
<span data-ttu-id="12c9e-111">Une fois le fichier téléchargé, procédez comme suit sur le serveur SharePoint :</span><span class="sxs-lookup"><span data-stu-id="12c9e-111">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>
  
1. <span data-ttu-id="12c9e-112">Ouvrez une fenêtre Commande en cliquant sur **Démarrer** > **Tous les programmes** > **Accessoires**, puis en cliquant avec le bouton droit sur **Invite de commandes** et enfin sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="12c9e-112">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>
    
2. <span data-ttu-id="12c9e-113">Dans la fenêtre Commande, utilisez la commande cd pour passer du répertoire actuel au dossier dans lequel le fichier EWSManagedAPI.msi a été enregistré.</span><span class="sxs-lookup"><span data-stu-id="12c9e-113">In the command window, use the cd command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="12c9e-114">Par exemple, si vous avez enregistré le fichier à C:\Downloads tapez la commande suivante dans la fenêtre de commandes et appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="12c9e-114">For example, if you have saved the file to C:\Downloads type the following command in the command window and then press Enter:</span></span>
    
   ```
   cd C:\Downloads
   ```

3. <span data-ttu-id="12c9e-115">Pour installer l’API, tapez la commande suivante, puis appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="12c9e-115">To install the API, type the following command then press Enter:</span></span>
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. <span data-ttu-id="12c9e-116">Une fois que l’API a été installé, réinitialisez IIS en tapant la commande suivante et appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="12c9e-116">After the API has been installed, reset IIS by typing the following command and pressing Enter:</span></span>
    
   ```
   iisreset
   ```

<span data-ttu-id="12c9e-117">Une fois que les Services Web Exchange a été installé, vous devez alors configurer l’authentification de serveur à serveur entre SharePoint Server et Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="12c9e-117">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server and Exchange Server.</span></span> <span data-ttu-id="12c9e-118">Pour ce faire, tout d’abord ouvrir SharePoint Management Shell et exécutez l’ensemble des commandes suivante :</span><span class="sxs-lookup"><span data-stu-id="12c9e-118">To do this, first open the SharePoint Management Shell and run the following set of commands:</span></span>
  
```
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> <span data-ttu-id="12c9e-119">Utilisez l’URI de votre service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="12c9e-119">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="12c9e-120">N’utilisez pas l’exemple d’URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span><span class="sxs-lookup"><span data-stu-id="12c9e-120">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span> 
  
<span data-ttu-id="12c9e-121">Après avoir créé l’émetteur de jeton et configuré le service d’émission de jeton, exécutez ces commandes en veillant à substituer l’URL de votre site SharePoint à l’URL de l’exemplehttp://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="12c9e-121">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

<span data-ttu-id="12c9e-122">Pour configurer l’authentification de serveur à serveur pour Exchange Server, ouvrez Exchange Management Shell et exécutez une commande similaire à celle-ci (en supposant que Exchange a été installé sur le lecteur c, et qu’elle utilise le chemin d’accès du dossier par défaut) :</span><span class="sxs-lookup"><span data-stu-id="12c9e-122">To configure server-to-server authentication for Exchange Server, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

<span data-ttu-id="12c9e-123">Après avoir configuré l’application partenaire, il est recommandé que vous arrêtez et redémarrez Internet Information Services (IIS) sur tous vos boîtes aux lettres et le client access serveurs Exchange.</span><span class="sxs-lookup"><span data-stu-id="12c9e-123">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="12c9e-124">Vous pouvez redémarrer IIS à l’aide d’une commande semblable à la suivante, qui redémarre le service sur l’ordinateur atl-exchange-001 :</span><span class="sxs-lookup"><span data-stu-id="12c9e-124">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```
iisreset atl-exchange-001
```

<span data-ttu-id="12c9e-125">Cette commande peut être exécutée à partir d’Exchange Management Shell ou à partir de n’importe quelle autre fenêtre commande.</span><span class="sxs-lookup"><span data-stu-id="12c9e-125">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>
  
<span data-ttu-id="12c9e-126">Ensuite, exécutez une commande semblable à la suivante, qui donne à l’utilisateur spécifié (dans cet exemple, kenmyer) d’effectuer une opération découverte sur Exchange :</span><span class="sxs-lookup"><span data-stu-id="12c9e-126">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

<span data-ttu-id="12c9e-127">Une fois que l’authentification de serveur à serveur a été établie entre Exchange et SharePoint, l’étape suivante consiste à créer un site d’eDiscovery dans SharePoint.</span><span class="sxs-lookup"><span data-stu-id="12c9e-127">After server-to-server authentication has been established between Exchange and SharePoint, your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="12c9e-128">Qui peuvent être effectuées par l’exécution des commandes semblables à celles-ci à partir de SharePoint Management Shell :</span><span class="sxs-lookup"><span data-stu-id="12c9e-128">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> <span data-ttu-id="12c9e-129">« eDiscovery » est l’abréviation de « découverte électronique » et désigne généralement la recherche, dans des archives électroniques, d’éléments susceptibles d’être « raisonnablement conçus pour conduire à une preuve admissible » devant une cour de justice.</span><span class="sxs-lookup"><span data-stu-id="12c9e-129">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span> 
  
<span data-ttu-id="12c9e-130">Lorsque le nouveau site est prêt, l’étape suivante consiste à configurer Exchange Server pour agir ainsi source pour SharePoint.</span><span class="sxs-lookup"><span data-stu-id="12c9e-130">When the new site is ready, the next step is to configure Exchange Server to act as a result source for SharePoint.</span></span> <span data-ttu-id="12c9e-131">Vous pouvez effectuer des opérations qui en effectuant la procédure suivante à partir de la page Administration centrale de SharePoint :</span><span class="sxs-lookup"><span data-stu-id="12c9e-131">You can do that by completing the following procedure from the SharePoint Central Administration page:</span></span>
  
1. <span data-ttu-id="12c9e-132">Dans la page Administration centrale, cliquez sur **Gérer les applications de service** et sur **Application de service de recherche**.</span><span class="sxs-lookup"><span data-stu-id="12c9e-132">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>
    
2. <span data-ttu-id="12c9e-133">Dans la page Application de service de recherche : Administration de la recherche, cliquez sur **Origines des résultats**, puis sur **Nouvelle origine des résultats**.</span><span class="sxs-lookup"><span data-stu-id="12c9e-133">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>
    
3. <span data-ttu-id="12c9e-134">Dans le volet **Nouvelle origine des résultats**, attribuez un nom à la nouvelle origine des résultats (par exemple, **Microsoft Exchange**) dans la zone **Nom**.</span><span class="sxs-lookup"><span data-stu-id="12c9e-134">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="12c9e-135">Sélectionnez l’origine des résultats **protocole** **Exchange** , puis entrez l’URL source des services web pour votre serveur Exchange dans la zone **URL Source d’Exchange** .</span><span class="sxs-lookup"><span data-stu-id="12c9e-135">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="12c9e-136">L’URL source doit ressembler à ceci :</span><span class="sxs-lookup"><span data-stu-id="12c9e-136">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. <span data-ttu-id="12c9e-137">Vérifiez que l’option **Utiliser la découverte automatique** n’est pas sélectionnée, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="12c9e-137">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>
    
<span data-ttu-id="12c9e-138">Enfin, créez un nouveau cas eDiscovery et un nouvel ensemble eDiscovery en procédant à partir du site de découverte de SharePoint (par exemple,https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="12c9e-138">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>
  
1. <span data-ttu-id="12c9e-139">Dans la page Contenu du site, cliquez sur **Créer un cas**.</span><span class="sxs-lookup"><span data-stu-id="12c9e-139">On the Site Contents page click **Create a new case**.</span></span>
    
2. <span data-ttu-id="12c9e-p110">Dans la page Contenu du site : Nouveau site SharePoint, entrez l’alias de messagerie de l’utilisateur (par exemple, **kenmyer**) dans la zone **Titre**, puis ajoutez cette URL dans la zone **Adresse du site web**. Vous obtenez alors une URL similaire à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="12c9e-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. <span data-ttu-id="12c9e-142">Cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="12c9e-142">Click **Create**.</span></span>
    
4. <span data-ttu-id="12c9e-143">Lorsque la page de l’ensemble eDiscovery apparaît, cliquez sur **nouvel élément** sous **Identité et préservation : Ensembles de découverte**.</span><span class="sxs-lookup"><span data-stu-id="12c9e-143">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>
    
5. <span data-ttu-id="12c9e-144">Dans la page Nouveau : Ensemble de découverte, entrez l’alias de messagerie de l’utilisateur dans la zone **Nom de l’ensemble eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="12c9e-144">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="12c9e-145">Entrez **eDiscovery Lync\\**\* dans le **filtre de** zone, puis cliquez sur **Ajouter &amp; gérer les Sources de**.</span><span class="sxs-lookup"><span data-stu-id="12c9e-145">Enter **eDiscovery Lync\\**\* in the **Filter** box and then click **Add &amp; Manage Sources**.</span></span>
    
6. <span data-ttu-id="12c9e-146">Dans la zone Ajouter &amp; gérer les Sources de page, entrez l’alias de messagerie de l’utilisateur dans la première zone de texte sous **boîtes aux lettres**.</span><span class="sxs-lookup"><span data-stu-id="12c9e-146">On the Add &amp; Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**.</span></span> <span data-ttu-id="12c9e-147">Cliquez sur l’icône Vérifier la boîte aux lettres située en regard du manuel pour vérifier que SharePoint peut se connecter à la boîte aux lettres spécifiée.</span><span class="sxs-lookup"><span data-stu-id="12c9e-147">Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>
    
7. <span data-ttu-id="12c9e-148">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="12c9e-148">Click **OK**.</span></span>
    
8. <span data-ttu-id="12c9e-149">Dans la page Ensemble eDiscovery, cliquez sur **Enregistrer** pour enregistrer le nouvel ensemble eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="12c9e-149">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>
    
<span data-ttu-id="12c9e-150">À ce stade, vous pouvez rechercher la boîte aux lettres spécifiée (kenmyer) et/ou activer archives permanentes de la même manière que vous le feriez pour n’importe quel autre SharePoint contenu ou origine des résultats.</span><span class="sxs-lookup"><span data-stu-id="12c9e-150">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>
  

