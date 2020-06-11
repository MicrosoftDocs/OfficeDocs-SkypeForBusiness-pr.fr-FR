---
title: Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint Online & interactions OneDrive entreprise avec Teams. le stockage de fichiers en conversation privée & une interaction entre l’équipe, le canal standard & la bibliothèque de documents.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cdcf054cfcf6b9d4f030ff1cf47bb9959a4cbcf8
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44689820"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="d4bb3-103">Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d4bb3-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="d4bb3-104">Regardez la session suivante pour découvrir comment les équipes interagissent avec Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint et OneDrive entreprise : [notions de bases de Microsoft teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="d4bb3-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="d4bb3-105">Dans Microsoft Teams, chaque équipe dispose d’un site d’équipe dans SharePoint Online et chaque canal standard d’une équipe obtient un dossier au sein de la bibliothèque de documents du site d’équipe par défaut.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="d4bb3-106">Les fichiers partagés au sein d’une conversation sont automatiquement ajoutés à la bibliothèque de documents, et les autorisations et les options de sécurité des fichiers définies dans SharePoint sont automatiquement reflétées dans Teams.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="d4bb3-107">Pour constater l’incidence de la modification d’une adresse de site dans SharePoint, voir [modifier une adresse de site](https://docs.microsoft.com/sharepoint/change-site-address).</span><span class="sxs-lookup"><span data-stu-id="d4bb3-107">To see the impact of changing a site address in SharePoint, read [Change a site address](https://docs.microsoft.com/sharepoint/change-site-address).</span></span>

> [!NOTE]
> <span data-ttu-id="d4bb3-108">Cet article s’applique uniquement aux canaux standard.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-108">This article applies only to standard channels.</span></span> <span data-ttu-id="d4bb3-109">L’architecture des canaux privés est différente des canaux standard.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-109">The architecture for private channels is different from standard channels.</span></span> <span data-ttu-id="d4bb3-110">Chaque canal privé dispose de sa propre collection de sites SharePoint séparée du site d’équipe parent.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-110">Each private channel has its own SharePoint site collection that's separate from the parent team site.</span></span> <span data-ttu-id="d4bb3-111">Pour en savoir plus, voir [canaux privés dans Microsoft teams](private-channels.md).</span><span class="sxs-lookup"><span data-stu-id="d4bb3-111">To learn more, see [Private channels in Microsoft Teams](private-channels.md).</span></span>

<span data-ttu-id="d4bb3-112">Les fichiers de conversation privée sont stockés dans le dossier OneDrive entreprise de l’expéditeur, et les autorisations sont automatiquement accordées à tous les participants dans le cadre du processus de partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-112">Private chat files are stored in the sender's OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="d4bb3-113">Si les utilisateurs ne sont pas assignés et activés pour les licences SharePoint Online, ils n’ont pas de stockage OneDrive entreprise dans Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-113">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="d4bb3-114">Le partage de fichiers continue de fonctionner dans les canaux standard, mais les utilisateurs ne peuvent pas partager des fichiers dans les conversations sans espace de stockage OneDrive entreprise dans Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-114">File sharing will continue to work in standard channels, but users won't be able to share files in chats without OneDrive for Business storage in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="d4bb3-115">En stockant les fichiers dans la bibliothèque de documents SharePoint Online et dans OneDrive Entreprise, toutes les règles de conformité configurées au niveau du client seront appliquées.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-115">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="d4bb3-116">Pour le moment, l’intégration avec SharePoint local n’est pas prise en charge par Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-116">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="d4bb3-117">Voici un exemple de relations entre l’équipe, le canal standard et la bibliothèque de documents.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-117">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="d4bb3-118">Pour chaque équipe, un site SharePoint est créé et le dossier **documents partagés** est le dossier par défaut créé pour l’équipe.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-118">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="d4bb3-119">Chaque canal standard, y compris le canal **général** (canal par défaut de chaque équipe), possède un dossier dans **documents partagés**.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-119">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagramme de dossiers de documents partagés dans SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="d4bb3-121">Vous ne pouvez pas remplacer le site SharePoint par défaut ni la bibliothèque de documents par une autre pour le moment.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-121">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="d4bb3-122">Vous nous avez signalé que vous le souhaitiez, et nous y réfléchissons.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-122">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="d4bb3-123">Consultez la [Feuille de route de Teams](https://aka.ms/teamsroadmap) ou [Teams UserVoice](https://aka.ms/TeamsUserVoice) pour rester informé des fonctionnalités à venir.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-123">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="d4bb3-124">Pour ajouter un onglet à votre équipe qui est lié à une page de site SharePoint existante ou à votre bibliothèque de documents SharePoint existante :</span><span class="sxs-lookup"><span data-stu-id="d4bb3-124">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="d4bb3-125">Sélectionnez le signe plus à côté des onglets.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-125">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="d4bb3-126">Sélectionnez **SharePoint** pour une page de site SharePoint ou une **bibliothèque de documents** existante pour une bibliothèque de documents existante.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-126">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="d4bb3-127">Sélectionnez la page ou la bibliothèque de documents appropriée.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-127">Select the appropriate page or document library.</span></span>

<span data-ttu-id="d4bb3-128">Pour chaque utilisateur, le dossier OneDrive **Fichiers de conversation Microsoft Teams** est utilisé pour stocker tous les fichiers partagés dans les conversations avec d'autres utilisateurs (en tête-à-tête ou de groupe), avec les autorisations configurées pour limiter l'accès aux utilisateurs concernés uniquement.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-128">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagramme du dossier OneDrive intitulé fichiers Microsoft teams chat](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a><span data-ttu-id="d4bb3-130">Onglet fichiers de canal</span><span class="sxs-lookup"><span data-stu-id="d4bb3-130">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="d4bb3-131">L’onglet **fichiers** de teams ressemble étroitement à la vue documents SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-131">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="d4bb3-132">Dans l’onglet **fichiers** , les utilisateurs peuvent :</span><span class="sxs-lookup"><span data-stu-id="d4bb3-132">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="d4bb3-133">Voir d’autres options dans le menu **nouveau** fichier.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-133">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="d4bb3-134">Synchroniser des fichiers sur leur disque local.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-134">Sync files to their local drive.</span></span>
- <span data-ttu-id="d4bb3-135">Dans le **menu tous les documents** , passez du mode liste **au mode** **vignettes** . **List**</span><span class="sxs-lookup"><span data-stu-id="d4bb3-135">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="d4bb3-136">Identifiez les fichiers qui nécessitent d’être attentifs ou qui ont des logiciels malveillants.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-136">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="d4bb3-137">Déterminez immédiatement s’il s’agit d’un fichier en lecture seule ou extrait.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-137">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="d4bb3-138">Extraire et archiver des fichiers.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-138">Check out and check in files.</span></span>
- <span data-ttu-id="d4bb3-139">Épingler, détacher et changer l’ordre de tri des fichiers.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-139">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="d4bb3-140">Identifier les fichiers nécessitant des métadonnées</span><span class="sxs-lookup"><span data-stu-id="d4bb3-140">Identify which files need metadata</span></span>
- <span data-ttu-id="d4bb3-141">Choisissez parmi d’autres options de filtre.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-141">Choose from many more filter options.</span></span>
- <span data-ttu-id="d4bb3-142">Regroupez des fichiers en fonction d’en-têtes de colonne.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-142">Group files based on column headings.</span></span>
- <span data-ttu-id="d4bb3-143">Modifiez les paramètres de colonnes (déplacez-vous vers la gauche ou la droite, Masquer) et largeur de colonne.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-143">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="d4bb3-144">Paramètre de type de lien par défaut</span><span class="sxs-lookup"><span data-stu-id="d4bb3-144">Default link type setting</span></span>

<span data-ttu-id="d4bb3-145">SharePoint et OneDrive disposent d’un paramètre d’administrateur pour spécifier le type de lien par défaut pour les liens créés pour un fichier.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-145">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="d4bb3-146">Teams adopte cette même approche en réutilisant les paramètres définis par l’administrateur pour SharePoint et OneDrive.</span><span class="sxs-lookup"><span data-stu-id="d4bb3-146">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="d4bb3-147">Pour plus d’informations sur cette approche, voir [modifier le type de lien par défaut lorsque les utilisateurs reçoivent des liens pour le partage](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="d4bb3-147">More details about this approach are described in [Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="d4bb3-148">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="d4bb3-148">More information</span></span>

<span data-ttu-id="d4bb3-149">Pour plus d’informations sur le fonctionnement de SharePoint avec Teams, reportez-vous à la rubrique [SharePoint et équipes : meilleure combinaison](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="d4bb3-149">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="d4bb3-150">Pour en savoir plus sur l’interface utilisateur pour les invités dans Microsoft Teams, prenez connaissance de [l’interface utilisateur](guest-experience.md).</span><span class="sxs-lookup"><span data-stu-id="d4bb3-150">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>

