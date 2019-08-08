---
title: Partager des fichiers dans Microsoft teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
search.appverid: MET150
description: Microsoft teams utilise les paramètres de OneDrive et SharePoint pour contrôler le partage.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d9f2060c7b87d58820cf0d90dd8e4dc556297f1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243158"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="4fdc3-103">Partager des fichiers dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="4fdc3-103">Sharing files in Microsoft Teams</span></span>

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-article.md)]

<span data-ttu-id="4fdc3-104">Les fonctionnalités de partage de fichiers dans teams permettent aux utilisateurs de partager du contenu avec d’autres utilisateurs d’équipes au sein de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-104">The file sharing features in Teams let users share content with other Teams users in their organization.</span></span> <span data-ttu-id="4fdc3-105">Le partage dans teams repose sur les paramètres configurés dans SharePoint et OneDrive, de sorte que ce que vous configurez pour SharePoint et OneDrive contrôle le partage dans teams également.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>
<span data-ttu-id="4fdc3-106">![Diagramme indiquant le fonctionnement du partage de fichiers entre teams et OneDrive entreprise et SharePoint](media/sharing-files-in-teams-image1.png)</span><span class="sxs-lookup"><span data-stu-id="4fdc3-106">![Diagram indicating how file sharing works between Teams and OneDrive for Business and SharePoint](media/sharing-files-in-teams-image1.png)</span></span>

<span data-ttu-id="4fdc3-107">Le partage d’équipes permet aux utilisateurs d’effectuer les opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="4fdc3-107">Teams sharing lets users do the following:</span></span>

- <span data-ttu-id="4fdc3-108">Partager des fichiers à partir de OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-108">Share files from OneDrive.</span></span>

- <span data-ttu-id="4fdc3-109">Définir des autorisations pour les fichiers que vous voulez partager avec d’autres utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-109">Set permissions for files they want to share with others.</span></span>

- <span data-ttu-id="4fdc3-110">Partager des fichiers au sein d’une équipe.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-110">Share files across Teams.</span></span>

- <span data-ttu-id="4fdc3-111">Partager des fichiers à partir de la liste des fichiers récemment consultés (en règle générale, il s’agit des fichiers les plus intéressants pour le partage).</span><span class="sxs-lookup"><span data-stu-id="4fdc3-111">Share files from their list of recently accessed files (typically, these are the files users are most interested in sharing).</span></span>

- <span data-ttu-id="4fdc3-112">Restez dans teams lorsqu’ils cliquent sur un nom de fichier pour ouvrir un fichier.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-112">Stay within Teams when they click a file name to open a file.</span></span>

<span data-ttu-id="4fdc3-113">Teams réduit la durée des URL SharePoint et des URL du navigateur pointant vers un fichier.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-113">Teams shortens long SharePoint URLS and browser URLS that point to a file.</span></span> <span data-ttu-id="4fdc3-114">Teams utilise uniquement le nom du fichier pour créer un lien vers un fichier.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-114">Teams uses just the file name to link to a file.</span></span> <span data-ttu-id="4fdc3-115">Par ailleurs, l’option **obtenir un lien** a été remplacée par copier le **lien** pour éliminer toute confusion éventuelle pour permettre à d’autres utilisateurs d’accéder à un fichier.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-115">Additionally, the **Get link** option has been changed to **Copy link** to eliminate any confusion that users might have about giving others access to a file.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="4fdc3-116">Configurer le partage dans OneDrive et SharePoint</span><span class="sxs-lookup"><span data-stu-id="4fdc3-116">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="4fdc3-117">Pour plus d’informations sur le partage de fichiers dans OneDrive et SharePoint, notamment sur la configuration du partage et la façon d’activer ou de désactiver le partage, voir:</span><span class="sxs-lookup"><span data-stu-id="4fdc3-117">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="4fdc3-118">[Présentation du partage externe](https://docs.microsoft.com/sharepoint/external-sharing-overview) -décrit ce qui se produit lorsque les utilisateurs partagent le partage, en fonction de ce qui est partagé et avec qui.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-118">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="4fdc3-119">[Activer ou désactiver le partage externe](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) -décrit la façon dont les administrateurs généraux et SharePoint peuvent modifier les paramètres de partage de niveau de l’organisation de SharePoint et OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-119">[Turn external sharing on or off](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="4fdc3-120">[Changer le partage externe pour un site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) -décrit la façon dont les administrateurs généraux et SharePoint peuvent activer ou désactiver le partage externe pour un site.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-120">[Change external sharing for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="4fdc3-121">[Changer le type de lien par défaut lorsque les utilisateurs obtiennent des liens pour le partage](https://docs.microsoft.com/sharepoint/change-default-sharing-link) : décrit la définition du type de lien par défaut afin qu’il soit plus restrictif.</span><span class="sxs-lookup"><span data-stu-id="4fdc3-121">[Change the default link type when users get links for sharing](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it is more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="4fdc3-122">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="4fdc3-122">More information</span></span>

- [<span data-ttu-id="4fdc3-123">Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4fdc3-123">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- <span data-ttu-id="4fdc3-124">[SharePoint et équipes: une meilleure collaboration](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span><span class="sxs-lookup"><span data-stu-id="4fdc3-124">[SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>

- [<span data-ttu-id="4fdc3-125">Partager des fichiers et des dossiers OneDrive</span><span class="sxs-lookup"><span data-stu-id="4fdc3-125">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="4fdc3-126">Partager des fichiers ou des dossiers SharePoint</span><span class="sxs-lookup"><span data-stu-id="4fdc3-126">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)

