---
title: Interaction entre SharePoint et les OneDrive interactions entre Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint & OneDrive interaction avec les Teams ; stockage de fichiers de conversation privée & interaction entre l’équipe, le canal standard et & bibliothèque de documents.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 21abc840ddc740d7d842767c6c864d8ff5b598dd
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855953"
---
# <a name="how-sharepoint-and-onedrive-interact-with-microsoft-teams"></a><span data-ttu-id="d3388-103">Interaction entre SharePoint et les OneDrive interactions entre Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3388-103">How SharePoint and OneDrive interact with Microsoft Teams</span></span>

> [!Tip]
> <span data-ttu-id="d3388-104">Regardez la session suivante pour découvrir comment Teams interagit avec les groupes Azure Active Directory, Microsoft 365, Exchange, SharePoint et OneDrive : bases de [Microsoft Teams](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="d3388-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Microsoft 365 Groups, Exchange, SharePoint and OneDrive: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="d3388-105">Chaque équipe dans Microsoft Teams a un site d’équipe dans SharePoint, et chaque canal standard d’une équipe reçoit un dossier dans la bibliothèque de documents du site d’équipe par défaut.</span><span class="sxs-lookup"><span data-stu-id="d3388-105">Each team in Microsoft Teams has a team site in SharePoint, and each standard channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="d3388-106">Chaque [canal privé possède](private-channels.md) son propre canal et SharePoint site.</span><span class="sxs-lookup"><span data-stu-id="d3388-106">Each [private channel](private-channels.md) gets its own, separate SharePoint site.</span></span>

<span data-ttu-id="d3388-107">Les fichiers partagés dans une conversation sont automatiquement ajoutés à la bibliothèque de documents, et les autorisations et options de sécurité des fichiers définies dans SharePoint sont automatiquement reflétées dans Teams.</span><span class="sxs-lookup"><span data-stu-id="d3388-107">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span> <span data-ttu-id="d3388-108">Pour voir l’impact de la modification d’une adresse de site dans SharePoint, [lisez Modifier une adresse de site.](/sharepoint/change-site-address)</span><span class="sxs-lookup"><span data-stu-id="d3388-108">To see the impact of changing a site address in SharePoint, read [Change a site address](/sharepoint/change-site-address).</span></span>

<span data-ttu-id="d3388-109">Les fichiers de conversation privée sont stockés dans le dossier OneDrive de l’expéditeur et les autorisations sont automatiquement accordées à tous les participants dans le cadre du processus de partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="d3388-109">Private chat files are stored in the sender's OneDrive folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="d3388-110">Si des licences ne leur sont pas SharePoint, ils n’ont pas d’espace OneDrive stockage dans Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d3388-110">If users aren't assigned SharePoint licenses, they don't have OneDrive storage in Microsoft 365.</span></span> <span data-ttu-id="d3388-111">Le partage de fichiers fonctionne dans les canaux standard, mais les utilisateurs ne peuvent pas partager de fichiers dans les conversations sans stockage OneDrive dans Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d3388-111">File sharing works in standard channels, but users won't be able to share files in chats without OneDrive storage in Microsoft 365.</span></span>

<span data-ttu-id="d3388-112">En stockant les fichiers dans SharePoint bibliothèque de documents et OneDrive fichiers, toutes les règles de conformité configurées au niveau de l’organisation sont suivies.</span><span class="sxs-lookup"><span data-stu-id="d3388-112">By storing the files in the SharePoint document library and OneDrive, all compliance rules configured at the organization level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="d3388-113">L’intégration avec SharePoint Server n’est pas prise en charge pour Teams.</span><span class="sxs-lookup"><span data-stu-id="d3388-113">Integration with SharePoint Server is not supported for Teams.</span></span>

<span data-ttu-id="d3388-114">Voici un exemple de relations entre une équipe, un canal standard et une bibliothèque de documents.</span><span class="sxs-lookup"><span data-stu-id="d3388-114">The following is the example of relationships between team, standard channel, and document library.</span></span>

<span data-ttu-id="d3388-115">Pour chaque équipe, un site SharePoint est créé et le dossier **Documents** partagés est le dossier par défaut créé pour l’équipe.</span><span class="sxs-lookup"><span data-stu-id="d3388-115">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="d3388-116">Chaque canal standard, y compris le **canal Général** (canal par défaut pour chaque équipe) dispose d’un dossier dans **Documents partagés.**</span><span class="sxs-lookup"><span data-stu-id="d3388-116">Each standard channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![Diagramme des dossiers Documents partagés dans SharePoint.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

<span data-ttu-id="d3388-118">Les paramètres SharePoint de site et de bibliothèque de documents par défaut ne peuvent pas être remplacés par un autre site ou bibliothèque de documents.</span><span class="sxs-lookup"><span data-stu-id="d3388-118">The default SharePoint site and document library can't be replaced with a different one.</span></span>

<span data-ttu-id="d3388-119">Pour chaque utilisateur, le dossier OneDrive **Fichiers de conversation Microsoft Teams** est utilisé pour stocker tous les fichiers partagés dans les conversations avec d'autres utilisateurs (en tête-à-tête ou de groupe), avec les autorisations configurées pour limiter l'accès aux utilisateurs concernés uniquement.</span><span class="sxs-lookup"><span data-stu-id="d3388-119">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagramme du dossier OneDrive nommé Microsoft Teams Fichiers de conversation](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<span data-ttu-id="d3388-121">Notez que pour les équipes publiques, SharePoint site d’équipe est mis en service avec l’accès « Tout le monde sauf les utilisateurs externes ».</span><span class="sxs-lookup"><span data-stu-id="d3388-121">Note that for public teams, the SharePoint team site is provisioned with "Everyone except external users" access.</span></span> <span data-ttu-id="d3388-122">L’équipe publique ne s’affiche pas dans Teams pour les personnes qui ne sont pas membres de cette équipe.</span><span class="sxs-lookup"><span data-stu-id="d3388-122">The public team isn't displayed in Teams for people who aren't members of that team.</span></span> <span data-ttu-id="d3388-123">Toutefois, ils peuvent accéder au contenu du site d SharePoint d’équipe à l’aide de l’URL SharePoint site d’équipe.</span><span class="sxs-lookup"><span data-stu-id="d3388-123">However, they can access content on the SharePoint team site using the URL of the SharePoint team site.</span></span> 

## <a name="channel-files-tab"></a><span data-ttu-id="d3388-124">Onglet Fichiers de canal</span><span class="sxs-lookup"><span data-stu-id="d3388-124">Channel Files tab</span></span>

<span data-ttu-id="d3388-125">**L’onglet** Fichiers Teams l’affichage SharePoint documents.</span><span class="sxs-lookup"><span data-stu-id="d3388-125">The **Files** tab in Teams closely resembles the SharePoint documents view.</span></span> <span data-ttu-id="d3388-126">Sous **l’onglet Fichiers,** les utilisateurs peuvent :</span><span class="sxs-lookup"><span data-stu-id="d3388-126">On the **Files** tab, users can:</span></span>

- <span data-ttu-id="d3388-127">D’autres options sont disponibles **dans le** menu Nouveau fichier.</span><span class="sxs-lookup"><span data-stu-id="d3388-127">See additional options in the **New** file menu.</span></span>
- <span data-ttu-id="d3388-128">Synchronisez des fichiers sur leur disque local.</span><span class="sxs-lookup"><span data-stu-id="d3388-128">Sync files to their local drive.</span></span>
- <span data-ttu-id="d3388-129">Dans le menu **Tous les documents,** passez de l’affichage de liste à l’affichage **de liste** compacté **à l’affichage vignettes.** </span><span class="sxs-lookup"><span data-stu-id="d3388-129">On the **All Documents** menu, switch from **List** view to **Compact list** to **Tiles** view.</span></span>
- <span data-ttu-id="d3388-130">Identifiez les fichiers qui ont besoin d’être identifiés ou qui contiennent des programmes malveillants.</span><span class="sxs-lookup"><span data-stu-id="d3388-130">Identify files that need attention or have malware.</span></span>
- <span data-ttu-id="d3388-131">Voir immédiatement si un fichier est en lecture seule ou extrait.</span><span class="sxs-lookup"><span data-stu-id="d3388-131">Immediately see whether a file is read-only or checked out.</span></span>
- <span data-ttu-id="d3388-132">Consultez et archivez des fichiers.</span><span class="sxs-lookup"><span data-stu-id="d3388-132">Check out and check in files.</span></span>
- <span data-ttu-id="d3388-133">Épingler, désépiner et modifier l’ordre de tri des fichiers.</span><span class="sxs-lookup"><span data-stu-id="d3388-133">Pin, unpin, and change the sort order of files.</span></span>
- <span data-ttu-id="d3388-134">Identifier les fichiers qui ont besoin de métadonnées</span><span class="sxs-lookup"><span data-stu-id="d3388-134">Identify which files need metadata</span></span>
- <span data-ttu-id="d3388-135">Choisissez parmi un grand nombre d’autres options de filtre.</span><span class="sxs-lookup"><span data-stu-id="d3388-135">Choose from many more filter options.</span></span>
- <span data-ttu-id="d3388-136">Grouper des fichiers sur la base d’en-tête de colonnes.</span><span class="sxs-lookup"><span data-stu-id="d3388-136">Group files based on column headings.</span></span>
- <span data-ttu-id="d3388-137">Modifiez les paramètres des colonnes (déplacer vers la gauche ou la droite, masquer) et la largeur de colonne.</span><span class="sxs-lookup"><span data-stu-id="d3388-137">Modify column settings (move left or right, hide) and column width.</span></span>

## <a name="default-link-type-setting"></a><span data-ttu-id="d3388-138">Paramètre du type de lien par défaut</span><span class="sxs-lookup"><span data-stu-id="d3388-138">Default link type setting</span></span>

<span data-ttu-id="d3388-139">Type de lien de partage affiché par défaut lorsqu’un utilisateur a partagé un fichier est SharePoint centre d’administration.</span><span class="sxs-lookup"><span data-stu-id="d3388-139">The type of sharing link shown by default when a user shared a file is set in the SharePoint admin center.</span></span> <span data-ttu-id="d3388-140">Voir [Modifier le type de lien par défaut lorsque les utilisateurs obtiennent des liens de partage pour](/sharepoint/change-default-sharing-link) plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="d3388-140">See [Change the default link type when users get links for sharing](/sharepoint/change-default-sharing-link) for information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d3388-141">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="d3388-141">Related topics</span></span>

<span data-ttu-id="d3388-142">[SharePoint et Teams la collaboration .](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)</span><span class="sxs-lookup"><span data-stu-id="d3388-142">[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

[<span data-ttu-id="d3388-143">À quoi ressemble l’expérience des invités</span><span class="sxs-lookup"><span data-stu-id="d3388-143">What the guest experience is like</span></span>](guest-experience.md)