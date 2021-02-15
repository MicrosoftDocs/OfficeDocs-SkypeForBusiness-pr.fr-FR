---
title: Utiliser la recherche de contenu dans Microsoft Teams
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Découvrez comment utiliser la recherche de contenu dans le Centre de conformité Microsoft 365 pour rechercher du contenu Microsoft Teams stocké dans Exchange Online, SharePoint Online, OneDrive Entreprise et OneNote.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f91e630b6f0666def3e64e40e68a6a3f18097152
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980438"
---
<a name="use-content-search-in-microsoft-teams"></a><span data-ttu-id="81fa4-103">Utiliser la recherche de contenu dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="81fa4-103">Use Content search in Microsoft Teams</span></span>
=====================================

> [!NOTE]
> <span data-ttu-id="81fa4-104">La recherche de contenu dans les messages et les fichiers dans les [canaux](private-channels.md) privés fonctionne différemment que dans les canaux standard.</span><span class="sxs-lookup"><span data-stu-id="81fa4-104">Content search of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="81fa4-105">Pour en savoir plus, consultez [la recherche de contenu dans les canaux privés.](#content-search-of-private-channels)</span><span class="sxs-lookup"><span data-stu-id="81fa4-105">To learn more, see [Content search of private channels](#content-search-of-private-channels).</span></span>

<span data-ttu-id="81fa4-106">La recherche de contenu permet d’interroger les informations de Microsoft Teams couvrant Exchange, SharePoint Online et OneDrive Entreprise.</span><span class="sxs-lookup"><span data-stu-id="81fa4-106">Content search provides a way to query Microsoft Teams information spanning Exchange, SharePoint Online, and OneDrive for Business.</span></span>

<span data-ttu-id="81fa4-107">Pour en savoir plus, consultez [la recherche de contenu dans Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/content-search)</span><span class="sxs-lookup"><span data-stu-id="81fa4-107">To learn more, see [Content search in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/content-search).</span></span>

<span data-ttu-id="81fa4-108">Par exemple,  en utilisant la recherche de contenu par rapport à votre boîte aux lettres Spécifications de fabrication et à votre site SharePoint Caractéristiques de fabrication, vous pouvez effectuer une recherche sur les conversations de canal standard de Teams à partir d’Exchange, les téléchargements et modifications des fichiers à partir de SharePoint Online et les modifications apportées à OneNote.</span><span class="sxs-lookup"><span data-stu-id="81fa4-108">For example, using **Content search** against your Manufacturing Specs mailbox and Manufacturing Specs SharePoint site, you can search against Teams standard channel conversations from Exchange, file uploads and modifications from SharePoint Online, and OneNote changes.</span></span>

<span data-ttu-id="81fa4-109">Vous pouvez également ajouter des critères de requête à **la** recherche de contenu pour affiner les résultats renvoyés.</span><span class="sxs-lookup"><span data-stu-id="81fa4-109">You can also add query criteria to the **Content Search** to narrow the results returned.</span></span> <span data-ttu-id="81fa4-110">Dans l’exemple ci-dessus, vous pouvez rechercher le contenu dans lequel les mots clés «**Nouvelles spécifications d’usine »** ont été utilisés.</span><span class="sxs-lookup"><span data-stu-id="81fa4-110">In the above example, you can look for content where the keywords "**New Factory Specs"** were used.</span></span>

> [!TIP]
> <span data-ttu-id="81fa4-111">Après avoir ajouté des conditions de recherche, vous pouvez exporter un rapport ou le contenu réel vers votre ordinateur pour analyse.</span><span class="sxs-lookup"><span data-stu-id="81fa4-111">After adding search conditions, you can export a report or the actual content to your computer for analysis.</span></span>

## <a name="content-search-of-private-channels"></a><span data-ttu-id="81fa4-112">Recherche de contenu dans les canaux privés</span><span class="sxs-lookup"><span data-stu-id="81fa4-112">Content search of private channels</span></span>

<span data-ttu-id="81fa4-113">Les enregistrements pour les messages envoyés dans un canal privé sont distribués dans la boîte aux lettres de tous les membres du canal privé, plutôt que dans une boîte aux lettres de groupe.</span><span class="sxs-lookup"><span data-stu-id="81fa4-113">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="81fa4-114">Les titres des enregistrements sont mis en forme de façon à indiquer le canal privé à partir duquel ils ont été envoyés.</span><span class="sxs-lookup"><span data-stu-id="81fa4-114">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="81fa4-115">Chaque canal privé possède sa propre collection de sites SharePoint distincte du site d’équipe parent, les fichiers dans un canal privé sont gérés indépendamment de l’équipe parente.</span><span class="sxs-lookup"><span data-stu-id="81fa4-115">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="81fa4-116">Teams ne prend pas en charge la recherche de contenu sur un seul canal. Il faut donc effectuer une recherche dans toute l’équipe.</span><span class="sxs-lookup"><span data-stu-id="81fa4-116">Teams doesn't support content search of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="81fa4-117">Pour effectuer une recherche de contenu dans un canal privé, recherchez dans l’équipe, la collection de sites associée au canal privé (pour inclure les fichiers) et les boîtes aux lettres des membres du canal privé (pour inclure les messages).</span><span class="sxs-lookup"><span data-stu-id="81fa4-117">To perform a content search of a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="81fa4-118">Pour identifier les fichiers et messages d’un canal privé à inclure dans votre recherche de contenu, utilisez les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="81fa4-118">Use the following steps to identify files and messages in a private channel to include in  your content search.</span></span>

### <a name="include-private-channel-files-in-a-content-search"></a><span data-ttu-id="81fa4-119">Inclure les fichiers de canal privé dans une recherche de contenu</span><span class="sxs-lookup"><span data-stu-id="81fa4-119">Include private channel files in a content search</span></span>

<span data-ttu-id="81fa4-120">Avant d’effectuer ces étapes, installez [SharePoint Online Management Shell et connectez-vous à SharePoint Online.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="81fa4-120">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="81fa4-121">Exécutez la suivante pour obtenir la liste de toutes les collections de sites SharePoint associées à des canaux privés de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="81fa4-121">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```
2. <span data-ttu-id="81fa4-122">Exécutez le script PowerShell suivant pour obtenir la liste de toutes les URL de collection de sites SharePoint associées aux canaux privés de l’équipe et à l’ID du groupe parent.</span><span class="sxs-lookup"><span data-stu-id="81fa4-122">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```
3. <span data-ttu-id="81fa4-123">Pour chaque ID d’équipe ou de groupe, exécutez le script PowerShell suivant pour identifier tous les sites de canaux privés pertinents.</span><span class="sxs-lookup"><span data-stu-id="81fa4-123">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-a-content-search"></a><span data-ttu-id="81fa4-124">Inclure les messages de canal privé dans une recherche de contenu</span><span class="sxs-lookup"><span data-stu-id="81fa4-124">Include private channel messages in a content search</span></span>

<span data-ttu-id="81fa4-125">Avant d’effectuer ces étapes, assurez-vous que vous avez installé la dernière version du [module Teams PowerShell.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="81fa4-125">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="81fa4-126">Exécutez la liste suivante pour obtenir la liste des canaux privés de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="81fa4-126">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```
2. <span data-ttu-id="81fa4-127">Exécutez l’information suivante pour obtenir la liste des membres d’un canal privé.</span><span class="sxs-lookup"><span data-stu-id="81fa4-127">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```
3. <span data-ttu-id="81fa4-128">Incluez les boîtes aux lettres de tous les membres de chaque canal privé de l’équipe dans votre requête de recherche de contenu.</span><span class="sxs-lookup"><span data-stu-id="81fa4-128">Include the mailboxes of all members from each private channel in the team as part of your content search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="81fa4-129">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="81fa4-129">Related topics</span></span>

- [<span data-ttu-id="81fa4-130">Cas de découverte électronique dans le Centre de conformité Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="81fa4-130">eDiscovery cases in the Microsoft 365 Compliance Center</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ediscovery-cases) 