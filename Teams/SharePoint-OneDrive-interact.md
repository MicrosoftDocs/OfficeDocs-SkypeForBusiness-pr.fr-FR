---
title: Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: Découvrez l'interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams, comme le stockage de fichiers de conversation privée, et la relation entre l'équipe, le canal et la bibliothèque de documents.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f790a01050811ee46526fe37a4d6c14f107491b5
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2019
ms.locfileid: "33827739"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="0889b-103">Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0889b-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="0889b-104">Regarder la session suivante pour savoir comment les équipes interagit avec Azure Active Directory (DAS), groupes d’Office 365, Exchange, SharePoint et OneDrive for Business : [Notions de base sur les équipes de Microsoft](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="0889b-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="0889b-p101">Dans Microsoft Teams, chaque équipe dispose d'un site dans SharePoint Online, et chaque canal d'une équipe reçoit un dossier dans la bibliothèque de documents par défaut du site de l'équipe. Les fichiers partagés dans une conversation sont automatiquement ajoutés à la bibliothèque de documents, et les autorisations et options de sécurité de fichier définies dans SharePoint sont automatiquement appliquées à Teams.</span><span class="sxs-lookup"><span data-stu-id="0889b-p101">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="0889b-107">Les fichiers de conversation privée sont stockés dans le dossier OneDrive Entreprise de l'envoyeur et les autorisations sont automatiquement accordées à tous les participants dans le cadre du processus de partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="0889b-107">Private chat files are stored in the sender’s OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="0889b-108">Si les utilisateurs ne sont pas affectés et activés avec SharePoint Online licences, ils n’ont OneDrive pour le stockage d’entreprise dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="0889b-108">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="0889b-109">Partage de fichiers continueront de fonctionner dans des canaux, mais les utilisateurs ne pourront pas partager des fichiers dans les salles de conversation sans OneDrive pour le stockage d’entreprise dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="0889b-109">File sharing will continue to work in channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="0889b-110">En stockant les fichiers dans la bibliothèque de documents SharePoint Online et dans OneDrive Entreprise, toutes les règles de conformité configurées au niveau du client seront appliquées.</span><span class="sxs-lookup"><span data-stu-id="0889b-110">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="0889b-111">Intégration SharePoint sur site n’est pas pris en charge pour Microsoft Teams à ce stade.</span><span class="sxs-lookup"><span data-stu-id="0889b-111">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="0889b-112">Voici un exemple de relations entre une équipe, un canal et une bibliothèque de documents.</span><span class="sxs-lookup"><span data-stu-id="0889b-112">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="0889b-p103">Pour chaque équipe, un site SharePoint et le dossier par défaut **Documents partagés** sont créés. Chaque canal, y compris le canal **Général** par défaut de l'équipe, dispose d'un dossier dans le dossier **Documents partagés**.</span><span class="sxs-lookup"><span data-stu-id="0889b-p103">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team. Each channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagramme des dossiers de documents partagés dans SharePoint Online pour une équipe et ses canaux dans Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="0889b-116">Vous ne pouvez pas remplacer le site SharePoint par défaut ni la bibliothèque de documents par une autre pour le moment.</span><span class="sxs-lookup"><span data-stu-id="0889b-116">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="0889b-117">Vous nous avez signalé que vous le souhaitiez, et nous y réfléchissons.</span><span class="sxs-lookup"><span data-stu-id="0889b-117">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="0889b-118">Consultez la [Feuille de route de Teams](https://aka.ms/teamsroadmap) ou [Teams UserVoice](https://aka.ms/TeamsUserVoice) pour rester informé des fonctionnalités à venir.</span><span class="sxs-lookup"><span data-stu-id="0889b-118">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="0889b-119">Pour ajouter un onglet à votre équipe qui lie à une page de site SharePoint existante ou à votre bibliothèque de documents SharePoint existante :</span><span class="sxs-lookup"><span data-stu-id="0889b-119">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="0889b-120">Sélectionnez le signe plus en regard des onglets.</span><span class="sxs-lookup"><span data-stu-id="0889b-120">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="0889b-121">Sélectionnez la **Bibliothèque de documents** pour une bibliothèque de documents existante ou **SharePoint** pour une page de site SharePoint existante.</span><span class="sxs-lookup"><span data-stu-id="0889b-121">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="0889b-122">Sélectionnez la bibliothèque de documents ou page appropriée.</span><span class="sxs-lookup"><span data-stu-id="0889b-122">Select the appropriate page or document library.</span></span>

<span data-ttu-id="0889b-123">Pour chaque utilisateur, le dossier OneDrive **Fichiers de conversation Microsoft Teams** est utilisé pour stocker tous les fichiers partagés dans les conversations avec d'autres utilisateurs (en tête-à-tête ou de groupe), avec les autorisations configurées pour limiter l'accès aux utilisateurs concernés uniquement.</span><span class="sxs-lookup"><span data-stu-id="0889b-123">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagramme du dossier OneDrive nommé Fichiers de conversation Microsoft Teams pour les conversations de chaque utilisateur.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a><span data-ttu-id="0889b-125">Onglet fichiers de canal</span><span class="sxs-lookup"><span data-stu-id="0889b-125">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="0889b-126">L’onglet **fichiers** dans les équipes ressemble à l’affichage de documents SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0889b-126">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="0889b-127">Sous l’onglet **fichiers** , les utilisateurs peuvent :</span><span class="sxs-lookup"><span data-stu-id="0889b-127">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="0889b-128">Afficher d’autres options dans le menu fichier de **Nouveau** .</span><span class="sxs-lookup"><span data-stu-id="0889b-128">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="0889b-129">Synchronisation de fichiers sur leur lecteur local.</span><span class="sxs-lookup"><span data-stu-id="0889b-129">Sync files to their local drive.</span></span>
- <span data-ttu-id="0889b-130">Dans le menu de **Tous les Documents** , passer d’affichage de **liste** à **liste Compact** à la vue **mosaïques** .</span><span class="sxs-lookup"><span data-stu-id="0889b-130">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="0889b-131">Identifier les fichiers qui nécessitent une attention ou qu’un programme malveillant.</span><span class="sxs-lookup"><span data-stu-id="0889b-131">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="0889b-132">Voir immédiatement si un fichier est en lecture seule ou checked out.</span><span class="sxs-lookup"><span data-stu-id="0889b-132">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="0889b-133">Extraire et archiver des fichiers.</span><span class="sxs-lookup"><span data-stu-id="0889b-133">Check out and check in files.</span></span>
- <span data-ttu-id="0889b-134">Épingler et désépingler modifier l’ordre de tri des fichiers.</span><span class="sxs-lookup"><span data-stu-id="0889b-134">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="0889b-135">Identifier les fichiers qui nécessitent des métadonnées</span><span class="sxs-lookup"><span data-stu-id="0889b-135">Identify which files need metadata</span></span>
- <span data-ttu-id="0889b-136">Choisissez à partir de nombreuses autres options de filtre.</span><span class="sxs-lookup"><span data-stu-id="0889b-136">Choose from many more filter options.</span></span>
- <span data-ttu-id="0889b-137">Fichiers de groupe basées sur les en-têtes de colonne.</span><span class="sxs-lookup"><span data-stu-id="0889b-137">Group files based on column headings.</span></span>
- <span data-ttu-id="0889b-138">Modifier les paramètres de colonne (déplacer vers la gauche ou droite, masquer) et la largeur de colonne.</span><span class="sxs-lookup"><span data-stu-id="0889b-138">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="0889b-139">Type de lien par défaut</span><span class="sxs-lookup"><span data-stu-id="0889b-139">Default link type setting</span></span>

<span data-ttu-id="0889b-140">SharePoint et OneDrive ont un paramètre d’administration pour spécifier le type de lien par défaut pour les liens qui sont créées pour un fichier.</span><span class="sxs-lookup"><span data-stu-id="0889b-140">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="0889b-141">Les équipes adopte cette même approche en réutilisant les paramètres que l’administrateur définit pour SharePoint et OneDrive.</span><span class="sxs-lookup"><span data-stu-id="0889b-141">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="0889b-142">Plus d’informations sur cette approche sont décrits dans [Modifier le type de liaison par défaut lorsque les utilisateurs obtiennent des liens pour le partage](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="0889b-142">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="0889b-143">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="0889b-143">More information</span></span>

<span data-ttu-id="0889b-144">Pour plus d’informations sur le fonctionne de SharePoint avec des équipes, voir [SharePoint et les équipes : une association efficace](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="0889b-144">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="0889b-145">Pour en savoir plus sur l’expérience invité dans les équipes, lire les [Nouveautés de l’expérience de l’invité](guest-experience.md).</span><span class="sxs-lookup"><span data-stu-id="0889b-145">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>

