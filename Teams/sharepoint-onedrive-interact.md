---
title: Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: Interaction de SharePoint Online & OneDrive Entreprise avec Teams ; stockage de fichiers de conversation privée & interaction entre l’équipe, le canal standard et & de documents.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b69b156e5cea0ff63925e91f5e3c077c794b3425
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117032"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="7aefb-103">Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7aefb-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="7aefb-104">Visionnez la session suivante pour découvrir comment Microsoft Teams interagit avec Azure Active Directory (AAD), les groupes Microsoft 365, Exchange, SharePoint and OneDrive Entreprise : [Fondements de Microsoft Teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="7aefb-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="7aefb-105">Chaque équipe dans Microsoft Teams a un site d’équipe dans SharePoint Online, et chaque canal standard d’une équipe reçoit un dossier dans la bibliothèque de documents du site d’équipe par défaut.</span><span class="sxs-lookup"><span data-stu-id="7aefb-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="7aefb-106">Les fichiers partagés dans une conversation sont automatiquement ajoutés à la bibliothèque de documents, et les autorisations et options de sécurité des fichiers définies dans SharePoint sont automatiquement reflétées dans Teams.</span><span class="sxs-lookup"><span data-stu-id="7aefb-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="7aefb-107">Pour voir l’impact de la modification d’une adresse de site dans SharePoint, lisez [Modifier une adresse de site.](/sharepoint/change-site-address)</span><span class="sxs-lookup"><span data-stu-id="7aefb-107">To see the impact of changing a site address in SharePoint, read [Change a site address](/sharepoint/change-site-address).</span></span>

> [!NOTE]
> <span data-ttu-id="7aefb-108">Cet article s’applique uniquement aux canaux standard.</span><span class="sxs-lookup"><span data-stu-id="7aefb-108">This article applies only to standard channels.</span></span> <span data-ttu-id="7aefb-109">L’architecture des canaux privés est différente des canaux standard.</span><span class="sxs-lookup"><span data-stu-id="7aefb-109">The architecture for private channels is different from standard channels.</span></span> <span data-ttu-id="7aefb-110">Chaque canal privé possède sa propre collection de sites SharePoint distincte du site d’équipe parent.</span><span class="sxs-lookup"><span data-stu-id="7aefb-110">Each private channel has its own SharePoint site collection that's separate from the parent team site.</span></span> <span data-ttu-id="7aefb-111">Pour en savoir plus, [consultez canaux privés dans Microsoft Teams.](private-channels.md)</span><span class="sxs-lookup"><span data-stu-id="7aefb-111">To learn more, see [Private channels in Microsoft Teams](private-channels.md).</span></span>

<span data-ttu-id="7aefb-112">Les fichiers de conversation privée sont stockés dans le dossier OneDrive Entreprise de l’expéditeur et les autorisations sont automatiquement accordées à tous les participants dans le cadre du processus de partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="7aefb-112">Private chat files are stored in the sender's OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="7aefb-113">Si des licences SharePoint Online ne sont pas affectées et activées pour les utilisateurs, ceux-ci ne disposent pas d'un stockage OneDrive Entreprise dans Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="7aefb-113">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="7aefb-114">Le partage de fichiers continuera à fonctionner dans les canaux standard, mais les utilisateurs ne pourront pas partager de fichiers dans les conversations sans stockage OneDrive Entreprise dans Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="7aefb-114">File sharing will continue to work in standard channels, but users won't be able to share files in chats without OneDrive for Business storage in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="7aefb-115">En stockant les fichiers dans la bibliothèque de documents SharePoint Online et dans OneDrive Entreprise, toutes les règles de conformité configurées au niveau du client seront appliquées.</span><span class="sxs-lookup"><span data-stu-id="7aefb-115">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="7aefb-116">L’intégration à SharePoint en local n’est pas prise en charge pour Microsoft Teams pour le moment.</span><span class="sxs-lookup"><span data-stu-id="7aefb-116">Integration with SharePoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="7aefb-117">Voici un exemple de relations entre une équipe, un canal standard et une bibliothèque de documents.</span><span class="sxs-lookup"><span data-stu-id="7aefb-117">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="7aefb-118">Pour chaque équipe, un site SharePoint est créé et le dossier **Documents** partagés est le dossier par défaut créé pour l’équipe.</span><span class="sxs-lookup"><span data-stu-id="7aefb-118">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="7aefb-119">Chaque canal standard, y compris le **canal Général** (canal par défaut pour chaque équipe) dispose d’un dossier dans **Documents partagés.**</span><span class="sxs-lookup"><span data-stu-id="7aefb-119">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagramme des dossiers Documents partagés dans SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="7aefb-121">Vous ne pouvez pas remplacer le site SharePoint par défaut ni la bibliothèque de documents par une autre pour le moment.</span><span class="sxs-lookup"><span data-stu-id="7aefb-121">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="7aefb-122">Vous nous avez signalé que vous le souhaitiez, et nous y réfléchissons.</span><span class="sxs-lookup"><span data-stu-id="7aefb-122">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="7aefb-123">Consultez la [Feuille de route de Teams](https://aka.ms/teamsroadmap) ou [Teams UserVoice](https://aka.ms/TeamsUserVoice) pour rester informé des fonctionnalités à venir.</span><span class="sxs-lookup"><span data-stu-id="7aefb-123">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="7aefb-124">Pour ajouter un onglet à votre équipe qui pointe vers une page de site SharePoint existante ou vers votre bibliothèque de documents SharePoint existante :</span><span class="sxs-lookup"><span data-stu-id="7aefb-124">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="7aefb-125">Sélectionnez le signe plus en côté des onglets.</span><span class="sxs-lookup"><span data-stu-id="7aefb-125">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="7aefb-126">Sélectionnez **SharePoint pour** une page de site SharePoint existante ou **une** bibliothèque de documents pour une bibliothèque de documents existante.</span><span class="sxs-lookup"><span data-stu-id="7aefb-126">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="7aefb-127">Sélectionnez la page ou la bibliothèque de documents appropriée.</span><span class="sxs-lookup"><span data-stu-id="7aefb-127">Select the appropriate page or document library.</span></span>

<span data-ttu-id="7aefb-128">Pour chaque utilisateur, le dossier OneDrive **Fichiers de conversation Microsoft Teams** est utilisé pour stocker tous les fichiers partagés dans les conversations avec d'autres utilisateurs (en tête-à-tête ou de groupe), avec les autorisations configurées pour limiter l'accès aux utilisateurs concernés uniquement.</span><span class="sxs-lookup"><span data-stu-id="7aefb-128">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagramme du dossier OneDrive nommé Fichiers de conversation Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="7aefb-130">Notez que pour les équipes publiques, le site d’équipe SharePoint est mis en service avec l’accès « Tout le monde sauf les utilisateurs externes ».</span><span class="sxs-lookup"><span data-stu-id="7aefb-130">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="7aefb-131">L’équipe publique ne s’affiche pas dans Teams pour les personnes qui ne sont pas membres de cette équipe.</span><span class="sxs-lookup"><span data-stu-id="7aefb-131">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="7aefb-132">Toutefois, ils peuvent accéder au contenu sur le site d’équipe SharePoint à l’aide de l’URL du site d’équipe SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7aefb-132">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="7aefb-133">Onglet Fichiers de canal</span><span class="sxs-lookup"><span data-stu-id="7aefb-133">Channel Files tab</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

<span data-ttu-id="7aefb-134">**L’onglet** Fichiers dans Teams ressemble beaucoup à l’affichage Documents SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7aefb-134">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="7aefb-135">Sous **l’onglet Fichiers,** les utilisateurs peuvent :</span><span class="sxs-lookup"><span data-stu-id="7aefb-135">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="7aefb-136">D’autres options sont disponibles **dans le** menu Nouveau fichier.</span><span class="sxs-lookup"><span data-stu-id="7aefb-136">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="7aefb-137">Synchronisez des fichiers sur leur disque local.</span><span class="sxs-lookup"><span data-stu-id="7aefb-137">Sync files to their local drive.</span></span>
- <span data-ttu-id="7aefb-138">Dans le menu **Tous les documents,** passez de l’affichage de liste à l’affichage **de liste** compacté **à l’affichage vignettes.** </span><span class="sxs-lookup"><span data-stu-id="7aefb-138">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="7aefb-139">Identifiez les fichiers qui ont besoin d’être attentifs ou qui contiennent des programmes malveillants.</span><span class="sxs-lookup"><span data-stu-id="7aefb-139">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="7aefb-140">Découvrez immédiatement si un fichier est en lecture seule ou extrait.</span><span class="sxs-lookup"><span data-stu-id="7aefb-140">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="7aefb-141">Consultez et archivez des fichiers.</span><span class="sxs-lookup"><span data-stu-id="7aefb-141">Check out and check in files.</span></span>
- <span data-ttu-id="7aefb-142">Épingler, désépiner et modifier l’ordre de tri des fichiers.</span><span class="sxs-lookup"><span data-stu-id="7aefb-142">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="7aefb-143">Identifier les fichiers qui ont besoin de métadonnées</span><span class="sxs-lookup"><span data-stu-id="7aefb-143">Identify which files need metadata</span></span>
- <span data-ttu-id="7aefb-144">Choisissez parmi un grand nombre d’autres options de filtre.</span><span class="sxs-lookup"><span data-stu-id="7aefb-144">Choose from many more filter options.</span></span>
- <span data-ttu-id="7aefb-145">Grouper des fichiers sur la base d’en-tête de colonnes.</span><span class="sxs-lookup"><span data-stu-id="7aefb-145">Group files based on column headings.</span></span>
- <span data-ttu-id="7aefb-146">Modifiez les paramètres des colonnes (déplacer vers la gauche ou la droite, masquer) et la largeur de colonne.</span><span class="sxs-lookup"><span data-stu-id="7aefb-146">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="7aefb-147">Paramètre du type de lien par défaut</span><span class="sxs-lookup"><span data-stu-id="7aefb-147">Default link type setting</span></span>

<span data-ttu-id="7aefb-148">SharePoint et OneDrive ont un paramètre d’administration qui spécifie le type de lien par défaut pour les liens créés pour un fichier.</span><span class="sxs-lookup"><span data-stu-id="7aefb-148">SharePoint and OneDrive have an admin setting for specifying the default link type for links that are created for a file.</span></span> <span data-ttu-id="7aefb-149">Teams adopte la même approche en utilsant les paramètres que l’administrateur définit pour SharePoint et OneDrive.</span><span class="sxs-lookup"><span data-stu-id="7aefb-149">Teams is adopting that same approach by reusing the settings that the admin sets for SharePoint and OneDrive.</span></span> <span data-ttu-id="7aefb-150">Des informations plus détaillées sur cette approche sont décrites dans La modification du type de lien par défaut lorsque les utilisateurs [obtiennent des liens à partager.](/sharepoint/change-default-sharing-link)</span><span class="sxs-lookup"><span data-stu-id="7aefb-150">More details about this approach are described in [Change the default link type when users get links for sharing](/sharepoint/change-default-sharing-link).</span></span> 

## <a name="more-information"></a><span data-ttu-id="7aefb-151">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="7aefb-151">More information</span></span>

<span data-ttu-id="7aefb-152">Pour plus d’informations sur le fonctionnement de SharePoint avec Teams, voir [SharePoint et Teams : meilleur ensemble.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)</span><span class="sxs-lookup"><span data-stu-id="7aefb-152">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

<span data-ttu-id="7aefb-153">Pour en savoir plus sur l’expérience des invités dans Teams, lisez ce à quoi [ressemble l’expérience des invités.](guest-experience.md)</span><span class="sxs-lookup"><span data-stu-id="7aefb-153">To learn more about the guest experience in Teams, read [What the guest experience is like](guest-experience.md).</span></span>