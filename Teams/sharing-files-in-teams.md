---
title: Partage de fichiers et de dossiers dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
description: Découvrez l’expérience de partage de fichiers et de dossiers dans Microsoft Teams.
ms.openlocfilehash: 53997f4493a0217e980427ab0d1f85d64095b9c9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117022"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="ae26c-103">Partage de fichiers dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ae26c-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="ae26c-104">Dans Microsoft Teams, les utilisateurs peuvent partager du contenu avec d’autres utilisateurs Teams à l’intérieur et à l’extérieur de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="ae26c-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="ae26c-105">Le partage dans Microsoft Teams dépend des paramètres configurés dans SharePoint et OneDrive, de sorte que ce que vous configurez pour SharePoint et OneDrive affectera le partage dans Teams également.</span><span class="sxs-lookup"><span data-stu-id="ae26c-105">Sharing files and folders in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will affect sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="ae26c-106">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="ae26c-106">Overview</span></span>

<span data-ttu-id="ae26c-107">Les utilisateurs peuvent partager des fichiers à partir de OneDrive, d’équipes et de sites auxquels ils ont accès, et à partir de leur ordinateur.</span><span class="sxs-lookup"><span data-stu-id="ae26c-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="ae26c-108">Pour partager un fichier, les utilisateurs peuvent suivre la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="ae26c-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="ae26c-p103">Dans un canal, cliquez sur **Joindre** (l’icône du trombone), sélectionnez **Récent**, **Parcourir les canaux et les équipes**, **OneDrive**, ou **Charger à partir de mon ordinateur**, puis choisir le fichier que vous voulez partager.</span><span class="sxs-lookup"><span data-stu-id="ae26c-p103">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share. </span></span><br> 
    <span data-ttu-id="ae26c-110">![Capture d’écran affichant le partage d’un fichier à partir d’un canal](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="ae26c-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="ae26c-p104">Dans une conversation, cliquez sur **Joindre** l’(icône du trombone), Sélectionnez  ou **OneDrive** ou **Charger à partir de mon ordinateur**, puis choisissez le fichier que vous voulez partager.</span><span class="sxs-lookup"><span data-stu-id="ae26c-p104">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share. </span></span><br>
    <span data-ttu-id="ae26c-112">![Capture d’écran affichant le partage d’un fichier à partir d’une conversation](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="ae26c-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="ae26c-113">Copiez et collez le lien de partage dans la zone de rédaction.</span><span class="sxs-lookup"><span data-stu-id="ae26c-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="ae26c-114">![Capture d’écran affichant l’aperçu d’un fichier dans la zone de rédaction](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="ae26c-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="ae26c-115">Autorisations relatives aux fichiers partagés et aux liens de partage</span><span class="sxs-lookup"><span data-stu-id="ae26c-115">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="ae26c-116">Lorsque des utilisateurs partagent un fichier à partir de Teams, ils peuvent définir qui peut accéder au fichier tout comme ils le font dans Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae26c-116">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="ae26c-117">Ils peuvent octroyer un accès à toute personne, à des personnes au sein de votre organisation, à des personnes ayant déjà un accès ou à des personnes spécifiques (ce qui peut inclure les personnes dans une discussion entre deux personnes, dans une conversation de groupe ou dans un canal).</span><span class="sxs-lookup"><span data-stu-id="ae26c-117">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="ae26c-118">Lorsqu’un fichier est partagé, l’aperçu de fichier est disponible dans le message, avec toutes les actions de fichier telles que **Ouvrir en ligne**, **Télécharger** et **Copier le lien**.</span><span class="sxs-lookup"><span data-stu-id="ae26c-118">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="ae26c-119">Le fichier s’ouvre dans Teams par défaut.</span><span class="sxs-lookup"><span data-stu-id="ae26c-119">By default, the file opens in Teams.</span></span>

<span data-ttu-id="ae26c-120">Lorsque des utilisateurs partagent un fichier dans une conversation ou un canal, ils sont avertis si tout ou partie des destinataires n’a pas l’autorisation d’afficher le fichier.</span><span class="sxs-lookup"><span data-stu-id="ae26c-120">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="ae26c-121">Ils peuvent modifier les autorisations sur le fichier avant de le partager en cliquant sur la flèche près de l’aperçu de fichier qui apparaît désormais dans le message.</span><span class="sxs-lookup"><span data-stu-id="ae26c-121">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![Capture d’écran d’une notification si des destinataires ne disposent pas des autorisations](media/share-files-permissions.png)

## <a name="related-topics"></a><span data-ttu-id="ae26c-123">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="ae26c-123">Related topics</span></span>

[<span data-ttu-id="ae26c-124">Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ae26c-124">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

[<span data-ttu-id="ae26c-125">Modifier le type de lien par défaut d’un site</span><span class="sxs-lookup"><span data-stu-id="ae26c-125">Change the default link type for a site</span></span>](/sharepoint/change-default-sharing-link)

[<span data-ttu-id="ae26c-126">Collaborer avec des invités au sein d’une équipe</span><span class="sxs-lookup"><span data-stu-id="ae26c-126">Collaborate with guests in a team</span></span>](/microsoft-365/solutions/collaborate-as-team)