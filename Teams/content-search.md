---
title: Utiliser la recherche de contenu dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Apprenez-en davantage sur l’utilisation de la recherche de contenu dans Microsoft teams pour interroger les informations de Microsoft teams à partir d’Exchange, SharePoint Online, OneDrive entreprise et OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 93f566590baedc77a4d15eca96569cc85ce54f0b
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776449"
---
<a name="use-content-search-in-microsoft-teams"></a><span data-ttu-id="b1437-103">Utiliser la recherche de contenu dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b1437-103">Use Content Search in Microsoft Teams</span></span>
=====================================

> [!NOTE]
> <span data-ttu-id="b1437-104">La recherche de contenu dans les messages et les fichiers de [canaux privés](private-channels.md) ne fonctionne pas de la même manière que dans les canaux standard.</span><span class="sxs-lookup"><span data-stu-id="b1437-104">Content search of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="b1437-105">Pour en savoir plus, voir [recherche de contenu de canaux privés](#content-search-of-private-channels).</span><span class="sxs-lookup"><span data-stu-id="b1437-105">To learn more, see [Content search of private channels](#content-search-of-private-channels).</span></span>

<span data-ttu-id="b1437-106">La recherche de contenu fournit un moyen de rechercher des informations sur Microsoft teams dans Exchange, SharePoint Online et OneDrive entreprise.</span><span class="sxs-lookup"><span data-stu-id="b1437-106">Content Search provides a way to query Microsoft Teams information spanning Exchange, SharePoint Online, and OneDrive for Business.</span></span>

<span data-ttu-id="b1437-107">Pour en savoir plus, voir [recherche de contenu dans Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).</span><span class="sxs-lookup"><span data-stu-id="b1437-107">To learn more, read [Content Search in Office 365](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).</span></span>

<span data-ttu-id="b1437-108">Par exemple, l’utilisation de la **recherche de contenu** par rapport aux spécifications de fabrication dans le site SharePoint, vous pouvez effectuer des recherches sur des conversations par canal standard d’Exchange, des téléchargements de fichiers et des modifications de SharePoint Online, et des modifications de OneNote.</span><span class="sxs-lookup"><span data-stu-id="b1437-108">For example, using **Content Search** against your Manufacturing Specs mailbox and Manufacturing Specs SharePoint site, you can search against Teams standard channel conversations from Exchange, file uploads and modifications from SharePoint Online, and OneNote changes.</span></span>

<span data-ttu-id="b1437-109">Vous pouvez également ajouter des critères de requête à la **recherche de contenu** pour affiner les résultats renvoyés.</span><span class="sxs-lookup"><span data-stu-id="b1437-109">You can also add query criteria to the **Content Search** to narrow the results returned.</span></span> <span data-ttu-id="b1437-110">Dans l’exemple ci-dessus, vous pouvez chercher le contenu dans lequel les mots clés «**New Factory specs »** étaient utilisés.</span><span class="sxs-lookup"><span data-stu-id="b1437-110">In the above example, you can look for content where the keywords "**New Factory Specs"** were used.</span></span>

> [!TIP]
> <span data-ttu-id="b1437-111">Après avoir ajouté des conditions de recherche, vous pouvez exporter un rapport ou les données vers votre ordinateur pour analyse.</span><span class="sxs-lookup"><span data-stu-id="b1437-111">After adding search conditions, you can export a report or the data to your computer for analysis.</span></span>

## <a name="content-search-of-private-channels"></a><span data-ttu-id="b1437-112">Recherche de contenu de canaux privés</span><span class="sxs-lookup"><span data-stu-id="b1437-112">Content search of private channels</span></span>

<span data-ttu-id="b1437-113">Les enregistrements pour les messages envoyés dans un canal privé sont distribués dans la boîte aux lettres de tous les membres du canal privé, plutôt que dans une boîte aux lettres de groupe.</span><span class="sxs-lookup"><span data-stu-id="b1437-113">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="b1437-114">Les titres des enregistrements sont mis en forme de façon à indiquer le canal privé à partir duquel ils ont été envoyés.</span><span class="sxs-lookup"><span data-stu-id="b1437-114">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="b1437-115">Étant donné que chaque canal privé dispose de sa propre collection de sites SharePoint séparée du site d’équipe parent, les fichiers d’un canal privé sont gérés indépendamment de l’équipe parente.</span><span class="sxs-lookup"><span data-stu-id="b1437-115">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="b1437-116">Microsoft Teams ne prend pas en charge la recherche de contenu d’un seul canal ; de sorte que l’ensemble de l’équipe doit être recherché.</span><span class="sxs-lookup"><span data-stu-id="b1437-116">Teams doesn't support content search of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="b1437-117">Pour effectuer une recherche de contenu d’un canal privé, effectuez une recherche dans l’équipe, la collection de sites associée au canal privé (pour inclure les fichiers) et les boîtes aux lettres des membres du canal privé (pour inclure des messages).</span><span class="sxs-lookup"><span data-stu-id="b1437-117">To perform a content search of a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="b1437-118">Procédez comme suit pour identifier les fichiers et les messages dans un canal privé à inclure dans la recherche de contenu.</span><span class="sxs-lookup"><span data-stu-id="b1437-118">Use the following steps to identify files and messages in a private channel to include in  your content search.</span></span>

### <a name="include-private-channel-files-in-a-content-search"></a><span data-ttu-id="b1437-119">Inclure des fichiers de canal privé dans une recherche de contenu</span><span class="sxs-lookup"><span data-stu-id="b1437-119">Include private channel files in a content search</span></span>

<span data-ttu-id="b1437-120">Avant d’effectuer cette procédure, installez [SharePoint Online Management Shell et connectez-vous à SharePoint](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)online.</span><span class="sxs-lookup"><span data-stu-id="b1437-120">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="b1437-121">Exécutez la commande suivante pour obtenir la liste de toutes les collections de sites SharePoint associées à des canaux privés au sein de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="b1437-121">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="b1437-122">Exécutez le script PowerShell suivant pour obtenir la liste de toutes les URL de collection de sites SharePoint associées aux canaux privés de l’équipe et de l’ID du groupe d’équipe parent.</span><span class="sxs-lookup"><span data-stu-id="b1437-122">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="b1437-123">Pour chaque ID d’équipe ou de groupe, exécutez le script PowerShell suivant pour identifier tous les sites de canaux privés pertinents.</span><span class="sxs-lookup"><span data-stu-id="b1437-123">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a><span data-ttu-id="b1437-124">Inclure des messages de canal privé dans une recherche de contenu</span><span class="sxs-lookup"><span data-stu-id="b1437-124">Include private channel messages in a content search</span></span>

<span data-ttu-id="b1437-125">Avant d’effectuer cette procédure, vérifiez que vous avez installé la [dernière version du module teams PowerShell](teams-powershell-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="b1437-125">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="b1437-126">Exécutez la commande suivante pour obtenir la liste des canaux privés de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="b1437-126">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="b1437-127">Exécutez la commande suivante pour obtenir la liste des membres du canal privé.</span><span class="sxs-lookup"><span data-stu-id="b1437-127">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="b1437-128">Incluez les boîtes aux lettres de tous les membres de chaque canal privé de l’équipe dans le cadre de votre requête de recherche de contenu.</span><span class="sxs-lookup"><span data-stu-id="b1437-128">Include the mailboxes of all members from each private channel in the team as part of your content search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b1437-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b1437-129">Related topics</span></span>

- [<span data-ttu-id="b1437-130">cas de découverte électronique dans le centre de conformité Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b1437-130">eDiscovery cases in the Microsoft 365 Compliance Center</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 