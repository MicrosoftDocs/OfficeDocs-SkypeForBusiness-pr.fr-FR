---
title: "Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams | Support Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Découvrez l'interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams, comme le stockage de fichiers de conversation privée, et la relation entre l'équipe, le canal et la bibliothèque de documents."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 01149aa436862de8e6537c658524be9f4db13124
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2017
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="c7245-103">Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c7245-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>
=============================================================================

<span data-ttu-id="c7245-p101">Dans Microsoft Teams, chaque équipe dispose d'un site dans SharePoint Online, et chaque canal d'une équipe reçoit un dossier dans la bibliothèque de documents par défaut du site de l'équipe. Les fichiers partagés dans une conversation sont automatiquement ajoutés à la bibliothèque de documents, et les autorisations et options de sécurité de fichier définies dans SharePoint sont automatiquement appliquées à Teams.</span><span class="sxs-lookup"><span data-stu-id="c7245-p101">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="c7245-106">Les fichiers de conversation privée sont stockés dans le dossier OneDrive Entreprise de l'**envoyeur** et les autorisations sont automatiquement accordées à tous les participants dans le cadre du processus de partage de fichiers.</span><span class="sxs-lookup"><span data-stu-id="c7245-106">Private chat files are stored in the **sender’s** OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="c7245-p102">Si SharePoint Online n’est pas activé dans votre client, les utilisateurs de Microsoft Teams ne seront pas toujours en mesure de partager des fichiers avec les équipes. Les utilisateurs des services de conversation privée ne peuvent pas partager de fichiers, car OneDrive Entreprise (qui est lié à la licence SharePoint) est requis.</span><span class="sxs-lookup"><span data-stu-id="c7245-p102">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams’ users cannot always share files in teams. Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="c7245-109">En stockant les fichiers dans la bibliothèque de documents SharePoint Online et dans OneDrive Entreprise, toutes les règles de conformité configurées au niveau du client seront appliquées.</span><span class="sxs-lookup"><span data-stu-id="c7245-109">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span>

<span data-ttu-id="c7245-110">Voici un exemple de relations entre une équipe, un canal et une bibliothèque de documents.</span><span class="sxs-lookup"><span data-stu-id="c7245-110">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="c7245-p103">Pour chaque équipe, un site SharePoint et le dossier par défaut *Documents partagés* sont créés. Chaque canal, y compris le canal **Général** par défaut de l'équipe, dispose d'un dossier sous le dossier *Documents partagés*.</span><span class="sxs-lookup"><span data-stu-id="c7245-p103">For every team, a SharePoint site is created, and the *Shared Documents* folder is the default folder created for the team. Each channel, including the **General** channel, the default channel for each team, has a folder under the *Shared Documents* folder.</span></span>

![Diagramme des dossiers de documents partagés dans SharePoint Online pour une équipe et ses canaux dans Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

<span data-ttu-id="c7245-114">Pour chaque utilisateur, le dossier OneDrive *Fichiers de conversation Microsoft Teams* est utilisé pour stocker tous les fichiers partagés dans les conversations avec d'autres utilisateurs (en tête-à-tête ou de groupe), avec les autorisations configurées pour limiter l'accès aux utilisateurs concernés uniquement.</span><span class="sxs-lookup"><span data-stu-id="c7245-114">For every user, the OneDrive folder *Microsoft Teams Chat Files* is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![Diagramme du dossier OneDrive nommé Fichiers de conversation Microsoft Teams pour les conversations de chaque utilisateur.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
