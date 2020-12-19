---
title: Partage de fichiers dans Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: Découvrez l’expérience de partage de fichiers dans Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138354"
---
# <a name="sharing-files-in-microsoft-teams"></a><span data-ttu-id="040a5-103">Partage de fichiers dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="040a5-103">Sharing files in Microsoft Teams</span></span>

<span data-ttu-id="040a5-104">Dans Microsoft Teams, les utilisateurs peuvent partager du contenu avec d’autres utilisateurs Teams à l’intérieur et à l’extérieur de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="040a5-104">In Microsoft Teams, users can share content with other Teams users within and outside their organization.</span></span> <span data-ttu-id="040a5-105">Le partage dans Microsoft Teams dépend des paramètres configurés dans SharePoint et OneDrive, de sorte que ce que vous configurez pour SharePoint et OneDrive contrôle le partage dans Teams également.</span><span class="sxs-lookup"><span data-stu-id="040a5-105">Sharing in Teams is based on the settings configured in SharePoint and OneDrive, so whatever you set up for SharePoint and OneDrive will control sharing in Teams as well.</span></span>

## <a name="overview"></a><span data-ttu-id="040a5-106">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="040a5-106">Overview</span></span>

<span data-ttu-id="040a5-107">Les utilisateurs peuvent partager des fichiers à partir de OneDrive, d’équipes et de sites auxquels ils ont accès, et à partir de leur ordinateur.</span><span class="sxs-lookup"><span data-stu-id="040a5-107">Users can share files from OneDrive, from teams and sites they have access to, and from their computer.</span></span> <span data-ttu-id="040a5-108">Pour partager un fichier, les utilisateurs peuvent suivre la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="040a5-108">To share a file, users can do the following:</span></span>

- <span data-ttu-id="040a5-109">Dans un canal, cliquez sur **Joindre** (l’icône du trombone), sélectionnez **Récent**, **Parcourir les canaux et les équipes**, **OneDrive**, ou **Charger à partir de mon ordinateur**, puis choisir le fichier que vous voulez partager.</span><span class="sxs-lookup"><span data-stu-id="040a5-109">In a channel, click **Attach** (the paperclip icon), select **Recent**, **Browse Teams and Channels**, **OneDrive**, or **Upload from my computer**, and then choose the file they want to share.</span></span> <br> 
    <span data-ttu-id="040a5-110">![Capture d’écran affichant le partage d’un fichier à partir d’un canal](media/share-files-channel.png)</span><span class="sxs-lookup"><span data-stu-id="040a5-110">![Screenshot showing sharing a file from a channel](media/share-files-channel.png)</span></span>
- <span data-ttu-id="040a5-111">Dans une conversation, cliquez sur **Joindre** l’(icône du trombone), Sélectionnez  ou **OneDrive** ou **Charger à partir de mon ordinateur**, puis choisissez le fichier que vous voulez partager.</span><span class="sxs-lookup"><span data-stu-id="040a5-111">In a chat, click **Attach** (the paperclip icon), select  or **OneDrive** or **Upload from my computer**, and then choose the file they want to share.</span></span> <br>
    <span data-ttu-id="040a5-112">![Capture d’écran affichant le partage d’un fichier à partir d’une conversation](media/share-files-chat.png)</span><span class="sxs-lookup"><span data-stu-id="040a5-112">![Screenshot showing sharing a file from a chat](media/share-files-chat.png)</span></span>
- <span data-ttu-id="040a5-113">Copiez et collez le lien de partage dans la zone de rédaction.</span><span class="sxs-lookup"><span data-stu-id="040a5-113">Copy and paste the sharing link in the compose box.</span></span><br>
    <span data-ttu-id="040a5-114">![Capture d’écran affichant l’aperçu d’un fichier dans la zone de rédaction](media/share-files-link.png)</span><span class="sxs-lookup"><span data-stu-id="040a5-114">![Screenshot showing file preview in the compose box](media/share-files-link.png)</span></span>

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a><span data-ttu-id="040a5-115">Ce que vous devez savoir sur l’expérience du partage de fichier</span><span class="sxs-lookup"><span data-stu-id="040a5-115">What you need to know about the file sharing experience</span></span>

### <a name="permissions-of-shared-files-and-sharing-links"></a><span data-ttu-id="040a5-116">Autorisations relatives aux fichiers partagés et aux liens de partage</span><span class="sxs-lookup"><span data-stu-id="040a5-116">Permissions of shared files and sharing links</span></span>

<span data-ttu-id="040a5-117">Lorsque des utilisateurs partagent un fichier en y accédant dans OneDrive ou des équipes et des canaux, tous les destinataires se voient accorder un accès avec l’[autorisation par défaut qui est définie au niveau de l’organisation](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span><span class="sxs-lookup"><span data-stu-id="040a5-117">When users share a file by browsing to it in OneDrive or teams and channels, all recipients are granted access along with the [default permission that's set at the organization level](https://docs.microsoft.com/sharepoint/change-default-sharing-link).</span></span>

<span data-ttu-id="040a5-118">Lorsqu’un utilisateur copie et colle un lien de partage, les autorisations définies sur ce lien de partage sont reconnues et l’URL SharePoint URL est réduite au nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="040a5-118">When a user copies and pastes a sharing link, the permissions set on that sharing link are honored and the SharePoint URL is shortened to the file name.</span></span> <span data-ttu-id="040a5-119">Entre d’autres termes, Teams n’utilise que le nom du fichier à lier à un fichier.</span><span class="sxs-lookup"><span data-stu-id="040a5-119">In other words, Teams uses just the file name to link to a file.</span></span>

<span data-ttu-id="040a5-120">Lorsque des utilisateurs partagent un fichier à partir de Teams, ils peuvent définir qui peut accéder au fichier tout comme ils le font dans Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="040a5-120">When users share a file from within Teams, they can set who can access the file just like they do across Microsoft 365.</span></span> <span data-ttu-id="040a5-121">Ils peuvent octroyer un accès à toute personne, à des personnes au sein de votre organisation, à des personnes ayant déjà un accès ou à des personnes spécifiques (ce qui peut inclure les personnes dans une discussion entre deux personnes, dans une conversation de groupe ou dans un canal).</span><span class="sxs-lookup"><span data-stu-id="040a5-121">They can give access to anyone, people in your organization, people with existing access, or specific people (which can include the people in a 1:1 chat, group chat, or channel).</span></span>  <span data-ttu-id="040a5-122">Lorsqu’un fichier est partagé, l’aperçu de fichier est disponible dans le message, avec toutes les actions de fichier telles que **Ouvrir en ligne**, **Télécharger** et **Copier le lien**.</span><span class="sxs-lookup"><span data-stu-id="040a5-122">When a file is shared, the file preview is available in the message, along with all file actions such as **Open online**, **Download**, and **Copy link**.</span></span> <span data-ttu-id="040a5-123">Le fichier s’ouvre dans Teams par défaut.</span><span class="sxs-lookup"><span data-stu-id="040a5-123">By default, the file opens in Teams.</span></span> <span data-ttu-id="040a5-124">Le lien de partage peut parfois ne pas être converti en aperçu de fichier au moment où l’utilisateur envoie le message.</span><span class="sxs-lookup"><span data-stu-id="040a5-124">Sometimes, the sharing link may not have converted to a file preview by the time a user sends the message.</span></span> <span data-ttu-id="040a5-125">L’aperçu de fichier est généré par le système mais, dans ce cas, le lien de partage n’est pas réduit au nom de fichier uniquement.</span><span class="sxs-lookup"><span data-stu-id="040a5-125">The file preview will be generated by the system, but in this scenario, the sharing link won't be shortened to the only the file name.</span></span>

<span data-ttu-id="040a5-126">Lorsque des utilisateurs partagent un fichier dans une conversation ou un canal, ils sont avertis si tout ou partie des destinataires n’a pas l’autorisation d’afficher le fichier.</span><span class="sxs-lookup"><span data-stu-id="040a5-126">When users share a file in a chat or channel, they're notified whether some or all recipients don't have permission to view the file.</span></span> <span data-ttu-id="040a5-127">Ils peuvent modifier les autorisations sur le fichier avant de le partager en cliquant sur la flèche près de l’aperçu de fichier qui apparaît désormais dans le message.</span><span class="sxs-lookup"><span data-stu-id="040a5-127">They can change the permissions on the file before they share it by clicking the arrow next to the file preview that now appears in the message.</span></span>

![Capture d’écran d’une notification si des destinataires ne disposent pas des autorisations](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a><span data-ttu-id="040a5-129">Copier un lien de partage dans Teams</span><span class="sxs-lookup"><span data-stu-id="040a5-129">Copy a sharing link in Teams</span></span>

<span data-ttu-id="040a5-130">Les utilisateurs peuvent copier un lien de partage SharePoint et modifier les autorisations de partage tout comme ils le font dans Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="040a5-130">Users can copy a SharePoint sharing link and change sharing permissions just like they do across Microsoft 365.</span></span> <span data-ttu-id="040a5-131">Ils peuvent octroyer un accès à toute personne, à des personnes au sein de votre organisation, à des personnes ayant déjà un accès ou à des personnes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="040a5-131">They can give access to anyone, people in your organization, people with existing access, or specific people.</span></span> <span data-ttu-id="040a5-132">L’autorisation par défaut du lien est identique à l’autorisation par défaut défini au niveau de l’organisation, sauf si les autorisations SharePoint au niveau du site la remplacent.</span><span class="sxs-lookup"><span data-stu-id="040a5-132">The default permission of the link is the same as the default permission set at the organization level unless SharePoint site level permissions override it.</span></span>

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a><span data-ttu-id="040a5-133">Configurer le partage dans OneDrive et SharePoint</span><span class="sxs-lookup"><span data-stu-id="040a5-133">Configure sharing in OneDrive and SharePoint</span></span>

<span data-ttu-id="040a5-134">Pour en savoir plus sur le partage de fichiers dans OneDrive et SharePoint, notamment comment configurer le partage et comment activer ou désactiver le partage, voir :</span><span class="sxs-lookup"><span data-stu-id="040a5-134">For more information about sharing files in OneDrive and SharePoint, including how to configure sharing and how to turn sharing on and off, see:</span></span>

- <span data-ttu-id="040a5-135">[Vue d’ensemble du partage externe](https://docs.microsoft.com/sharepoint/external-sharing-overview) : décrit ce qui se passe quand des utilisateurs partagent du contenu, en fonction de ce qu’ils partagent et avec qui.</span><span class="sxs-lookup"><span data-stu-id="040a5-135">[External sharing overview](https://docs.microsoft.com/sharepoint/external-sharing-overview) - describes what happens when users share, depending on what they're sharing and with whom.</span></span>

- <span data-ttu-id="040a5-136">[Gérer les paramètres de partage](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) : explique comment des administrateurs généraux et SharePoint peuvent modifier les paramètres de partage pour SharePoint et OneDrive au niveau de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="040a5-136">[Manage sharing settings](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) - describes how global and SharePoint admins can change their organization-level sharing settings for SharePoint and OneDrive.</span></span>

- <span data-ttu-id="040a5-137">[Activer ou désactiver le partage externe pour un site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) : décrit comment les administrateurs SharePoint et général peuvent activer ou désactiver le partage externe pour un site.</span><span class="sxs-lookup"><span data-stu-id="040a5-137">[Turn external sharing on or off for a site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) – describes how global and SharePoint admins can turn external sharing on or off for a site.</span></span>

- <span data-ttu-id="040a5-138">[Modifier le type de lien par défaut pour un site](https://docs.microsoft.com/sharepoint/change-default-sharing-link) : explique comment définir le type de lien par défaut pour le rendre plus restrictif.</span><span class="sxs-lookup"><span data-stu-id="040a5-138">[Change the default link type for a site](https://docs.microsoft.com/sharepoint/change-default-sharing-link) - describes how to set the default link type so that it's more restrictive.</span></span>

## <a name="more-information"></a><span data-ttu-id="040a5-139">Plus d’informations</span><span class="sxs-lookup"><span data-stu-id="040a5-139">More information</span></span>

- [<span data-ttu-id="040a5-140">Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="040a5-140">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>](sharepoint-onedrive-interact.md)

- [<span data-ttu-id="040a5-141">SharePoint et Teams : ensemble, c’est mieux</span><span class="sxs-lookup"><span data-stu-id="040a5-141">SharePoint and Teams: better together</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [<span data-ttu-id="040a5-142">Partager des fichiers et des dossiers OneDrive</span><span class="sxs-lookup"><span data-stu-id="040a5-142">Share OneDrive files and folders</span></span>](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [<span data-ttu-id="040a5-143">Partager des fichiers ou dossiers SharePoint</span><span class="sxs-lookup"><span data-stu-id="040a5-143">Share SharePoint files or folders</span></span>](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
