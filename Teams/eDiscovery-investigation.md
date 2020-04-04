---
title: Conduire une étude eDiscovery du contenu
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
description: Découvrez ce que vous pouvez faire lorsque vous devez effectuer une découverte électronique, comme lorsque vous avez besoin de transmettre toutes les informations stockées électroniquement à des fins juridiques.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 955fbf6ba937ca0fc11270cb58c12a0349d46330
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136684"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a><span data-ttu-id="3354a-103">Mener une recherche eDiscovery de contenu dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3354a-103">Conduct an eDiscovery investigation of content in Microsoft Teams</span></span>

<span data-ttu-id="3354a-104">Les grandes entreprises sont souvent exposées à des actions juridiques à forte pénalité qui demandent la soumission de toutes les informations stockées électroniquement (ESI).</span><span class="sxs-lookup"><span data-stu-id="3354a-104">Large Enterprises are often exposed to high penalty legal proceedings that demand submission of all Electronically Stored Information (ESI).</span></span>

<span data-ttu-id="3354a-105">Toutes les équipes 1:1 ou les discussions de groupe sont journalisées dans les boîtes aux lettres des utilisateurs correspondants, et tous les messages des canaux standard sont journalisés dans la boîte aux lettres du groupe représentant l’équipe.</span><span class="sxs-lookup"><span data-stu-id="3354a-105">All Teams 1:1 or group chats are journaled through to the respective users' mailboxes, and all standard channel messages are journaled through to the group mailbox representing the team.</span></span> <span data-ttu-id="3354a-106">Les fichiers téléchargés dans les canaux standard sont décrits sous la fonctionnalité eDiscovery pour SharePoint Online et OneDrive entreprise.</span><span class="sxs-lookup"><span data-stu-id="3354a-106">Files uploaded in standard channels are covered under the eDiscovery functionality for SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="3354a-107">la découverte électronique des messages et fichiers dans des [canaux privés](private-channels.md) ne fonctionne pas de la même manière que dans les canaux standard.</span><span class="sxs-lookup"><span data-stu-id="3354a-107">eDiscovery of messages and files in [private channels](private-channels.md) work differently than in standard channels.</span></span> <span data-ttu-id="3354a-108">Pour en savoir plus, voir [découverte électronique des canaux privés](#ediscovery-of-private-channels).</span><span class="sxs-lookup"><span data-stu-id="3354a-108">To learn more, see [eDiscovery of private channels](#ediscovery-of-private-channels).</span></span>

> [!NOTE]
> <span data-ttu-id="3354a-109">Pour le moment, nous ne prenons pas en charge la découverte électronique des messages de chat dans les scénarios où les utilisateurs invités sont les seuls participants à une conversation 1:1 ou 1 : N.</span><span class="sxs-lookup"><span data-stu-id="3354a-109">At this time, we don't support eDiscovery of chat messages in scenarios where guest users are the only participants in a 1:1 or 1:N chat.</span></span> <span data-ttu-id="3354a-110">Ces types de discussions sont également appelés discussions *invitées invitées* , car elles n’incluent pas les utilisateurs privés.</span><span class="sxs-lookup"><span data-stu-id="3354a-110">These types of chats are also called *guest-to-guest* chats because they don't include home tenant users.</span></span>

1. <span data-ttu-id="3354a-111">Pour effectuer une analyse eDiscovery avec le contenu Microsoft Teams, reportez-vous à l’étape 1 de [ce](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) lien.</span><span class="sxs-lookup"><span data-stu-id="3354a-111">To conduct an eDiscovery investigation with Microsoft Teams content, review step 1 in [this](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) link.</span></span>

2. <span data-ttu-id="3354a-112">Les données de Microsoft teams s’affichent sous forme de messages instantanés ou de conversations dans la sortie d’exportation eDiscovery d’Excel, et vous pouvez ouvrir le fichier. PST dans Outlook pour afficher ces messages après l’exportation.</span><span class="sxs-lookup"><span data-stu-id="3354a-112">Microsoft Teams data will appear as IM or Conversations in the Excel eDiscovery export output, and you can open the PST in Outlook to view those messages post export.</span></span>

    <span data-ttu-id="3354a-113">Lorsque vous affichez le fichier PST de l’équipe, les conversations sont conservées dans le dossier de discussion d’équipe sous historique des conversations.</span><span class="sxs-lookup"><span data-stu-id="3354a-113">When viewing the PST for the Team, note that all conversations are kept in the Team Chat folder under Conversation History.</span></span> <span data-ttu-id="3354a-114">Le titre du message s’aligne sur l’équipe et le canal.</span><span class="sxs-lookup"><span data-stu-id="3354a-114">The title of the message aligns to Team and Channel.</span></span> <span data-ttu-id="3354a-115">À partir de la consultation de l’image ci-dessous, vous pouvez voir ce message de Bob qui a affiché le canal Project 7 standard de l’équipe des spécifications de fabrication.</span><span class="sxs-lookup"><span data-stu-id="3354a-115">From reviewing the image below, you can see this message from Bob who messaged the Project 7 standard channel of the Manufacturing Specs team.</span></span>

    ![Capture d’écran d’un dossier de discussion d’équipe dans la boîte aux lettres d’un utilisateur dans Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3. <span data-ttu-id="3354a-117">Pour afficher des discussions privées dans la boîte aux lettres d’un utilisateur, celles-ci se trouvent également dans le dossier de discussion d’équipe sous historique des conversations.</span><span class="sxs-lookup"><span data-stu-id="3354a-117">To see private chats in a user's mailbox, they are also located in the Team Chat folder under Conversation History.</span></span>

## <a name="ediscovery-of-private-channels"></a><span data-ttu-id="3354a-118">Découverte électronique des canaux privés</span><span class="sxs-lookup"><span data-stu-id="3354a-118">eDiscovery of private channels</span></span>

<span data-ttu-id="3354a-119">Les enregistrements pour les messages envoyés dans un canal privé sont distribués dans la boîte aux lettres de tous les membres du canal privé, plutôt que dans une boîte aux lettres de groupe.</span><span class="sxs-lookup"><span data-stu-id="3354a-119">Records for messages sent in a private channel are delivered to the mailbox of all private channel members, rather than to a group mailbox.</span></span> <span data-ttu-id="3354a-120">Les titres des enregistrements sont mis en forme de façon à indiquer le canal privé à partir duquel ils ont été envoyés.</span><span class="sxs-lookup"><span data-stu-id="3354a-120">The titles of the records are formatted to indicate which private channel they were sent from.</span></span>

<span data-ttu-id="3354a-121">Étant donné que chaque canal privé dispose de sa propre collection de sites SharePoint séparée du site d’équipe parent, les fichiers d’un canal privé sont gérés indépendamment de l’équipe parente.</span><span class="sxs-lookup"><span data-stu-id="3354a-121">Because each private channel has its own SharePoint site collection that's separate from the parent team site, files in a private channel are managed independently of the parent team.</span></span>

<span data-ttu-id="3354a-122">Microsoft Teams ne prend pas en charge la découverte électronique d’un seul canal, de sorte que l’ensemble de l’équipe doit être recherché.</span><span class="sxs-lookup"><span data-stu-id="3354a-122">Teams doesn't support eDiscovery of a single channel, so the whole team must be searched.</span></span> <span data-ttu-id="3354a-123">Pour effectuer une recherche eDiscovery du contenu d’un canal privé, effectuez une recherche sur l’équipe, la collection de sites associée au canal privé (pour inclure les fichiers) et les boîtes aux lettres des membres du canal privé (pour inclure des messages).</span><span class="sxs-lookup"><span data-stu-id="3354a-123">To perform an eDiscovery search of content in a private channel, search across the team, the site collection associated with the private channel (to include files), and mailboxes of private channel members (to include messages).</span></span>

<span data-ttu-id="3354a-124">Procédez comme suit pour identifier les fichiers et les messages d’un canal privé à inclure dans votre recherche eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="3354a-124">Use the following steps to identify files and messages in a private channel to include in  your eDiscovery search.</span></span>

### <a name="include-private-channel-files-in-an-ediscovery-search"></a><span data-ttu-id="3354a-125">Inclusion de fichiers de canal privé dans une recherche eDiscovery</span><span class="sxs-lookup"><span data-stu-id="3354a-125">Include private channel files in an eDiscovery search</span></span>

<span data-ttu-id="3354a-126">Avant d’effectuer cette procédure, installez [SharePoint Online Management Shell et connectez-vous à SharePoint](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)online.</span><span class="sxs-lookup"><span data-stu-id="3354a-126">Before you perform these steps, install the [SharePoint Online Management Shell and connect to  SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

1. <span data-ttu-id="3354a-127">Exécutez la commande suivante pour obtenir la liste de toutes les collections de sites SharePoint associées à des canaux privés au sein de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="3354a-127">Run the following to get a list of all SharePoint site collections associated with private channels in the team.</span></span>

    ```PowerShell
    Get-SPOSite
    ```

2. <span data-ttu-id="3354a-128">Exécutez le script PowerShell suivant pour obtenir la liste de toutes les URL de collection de sites SharePoint associées aux canaux privés de l’équipe et de l’ID du groupe d’équipe parent.</span><span class="sxs-lookup"><span data-stu-id="3354a-128">Run the following PowerShell script to get a list of all SharePoint site collection URLs associated with private channels in the team and the parent team group ID.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```

3. <span data-ttu-id="3354a-129">Pour chaque ID d’équipe ou de groupe, exécutez le script PowerShell suivant pour identifier tous les sites de canaux privés pertinents, où $groupID est l’ID de groupe de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="3354a-129">For each team or group ID, run the following PowerShell script to identify all relevant private channel sites, where $groupID is the group ID of the team.</span></span>

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a><span data-ttu-id="3354a-130">Inclure des messages de canal privé dans une recherche eDiscovery</span><span class="sxs-lookup"><span data-stu-id="3354a-130">Include private channel messages in an eDiscovery search</span></span>

<span data-ttu-id="3354a-131">Avant d’effectuer cette procédure, vérifiez que vous avez installé la [dernière version du module teams PowerShell](teams-powershell-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="3354a-131">Before you perform these steps, make sure you have the [latest version of the Teams PowerShell module](teams-powershell-overview.md) installed.</span></span>

1. <span data-ttu-id="3354a-132">Exécutez la commande suivante pour obtenir la liste des canaux privés de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="3354a-132">Run the following to get a list of private channels in the team.</span></span>

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. <span data-ttu-id="3354a-133">Exécutez la commande suivante pour obtenir la liste des membres du canal privé.</span><span class="sxs-lookup"><span data-stu-id="3354a-133">Run the following to get a list of private channel members.</span></span>

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. <span data-ttu-id="3354a-134">Incluez les boîtes aux lettres de tous les membres de chaque canal privé de l’équipe dans le cadre de votre requête de recherche eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="3354a-134">Include the mailboxes of all members from each private channel in the team as part of your eDiscovery search query.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3354a-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3354a-135">Related topics</span></span>

- [<span data-ttu-id="3354a-136">Aperçu de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="3354a-136">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
