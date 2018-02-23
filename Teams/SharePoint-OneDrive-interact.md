---
title: "Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: snigdhav
description: "Découvrez l'interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams, comme le stockage de fichiers de conversation privée, et la relation entre l'équipe, le canal et la bibliothèque de documents."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0207cb87d6d340e4904e1ff8526165bf43a3f99e
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2018
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="efd50-103">Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="efd50-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>
=============================================================================

<span data-ttu-id="efd50-p101">Dans Microsoft Teams, chaque équipe dispose d'un site dans SharePoint Online, et chaque canal d'une équipe reçoit un dossier dans la bibliothèque de documents par défaut du site de l'équipe. Les fichiers partagés dans une conversation sont automatiquement ajoutés à la bibliothèque de documents, et les autorisations et options de sécurité de fichier définies dans SharePoint sont automatiquement appliquées à Teams.</span><span class="sxs-lookup"><span data-stu-id="efd50-p101">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="efd50-106">Les fichiers de conversation privée sont stockés dans le dossier OneDrive Entreprise de l'**envoyeur** et les autorisations sont automatiquement accordées à tous les participants dans le cadre du processus de partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="efd50-106">Private chat files are stored in the **sender’s** OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="efd50-p102">Si SharePoint Online n’est pas activé dans votre client, les utilisateurs de Microsoft Teams ne peuvent pas partager des fichiers avec les équipes. Les utilisateurs des services de conversation privée ne peuvent pas non plus partager de fichiers, car OneDrive Entreprise (qui est lié à la licence SharePoint) est requis.</span><span class="sxs-lookup"><span data-stu-id="efd50-p102">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams’ users can't share files in teams. Users in private chat also can't share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="efd50-109">En stockant les fichiers dans la bibliothèque de documents SharePoint Online et dans OneDrive Entreprise, toutes les règles de conformité configurées au niveau du client seront appliquées.</span><span class="sxs-lookup"><span data-stu-id="efd50-109">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span>

<span data-ttu-id="efd50-110">Voici un exemple de relations entre une équipe, un canal et une bibliothèque de documents.</span><span class="sxs-lookup"><span data-stu-id="efd50-110">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="efd50-p103">Pour chaque équipe, un site SharePoint et le dossier par défaut *Documents partagés* sont créés. Chaque canal, y compris le canal **Général** par défaut de l'équipe, dispose d'un dossier sous le dossier *Documents partagés*.</span><span class="sxs-lookup"><span data-stu-id="efd50-p103">For every team, a SharePoint site is created, and the *Shared Documents* folder is the default folder created for the team. Each channel, including the **General** channel, the default channel for each team, has a folder under the *Shared Documents* folder.</span></span>

![Diagramme des dossiers de documents partagés dans SharePoint Online pour une équipe et ses canaux dans Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

<span data-ttu-id="efd50-114">Pour chaque utilisateur, le dossier OneDrive *Fichiers de conversation Microsoft Teams* est utilisé pour stocker tous les fichiers partagés dans les conversations avec d'autres utilisateurs (en tête-à-tête ou de groupe), avec les autorisations configurées pour limiter l'accès aux utilisateurs concernés uniquement.</span><span class="sxs-lookup"><span data-stu-id="efd50-114">For every user, the OneDrive folder *Microsoft Teams Chat Files* is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagramme du dossier OneDrive nommé Fichiers de conversation Microsoft Teams pour les conversations de chaque utilisateur.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
