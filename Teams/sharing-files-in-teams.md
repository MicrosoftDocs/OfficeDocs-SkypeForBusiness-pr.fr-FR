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
# <a name="sharing-files-in-microsoft-teams"></a>Partage de fichiers dans Microsoft Teams

Dans Microsoft Teams, les utilisateurs peuvent partager du contenu avec d’autres utilisateurs Teams à l’intérieur et à l’extérieur de leur organisation. Le partage dans Microsoft Teams dépend des paramètres configurés dans SharePoint et OneDrive, de sorte que ce que vous configurez pour SharePoint et OneDrive contrôle le partage dans Teams également.

## <a name="overview"></a>Vue d’ensemble

Les utilisateurs peuvent partager des fichiers à partir de OneDrive, d’équipes et de sites auxquels ils ont accès, et à partir de leur ordinateur. Pour partager un fichier, les utilisateurs peuvent suivre la procédure suivante :

- Dans un canal, cliquez sur **Joindre** (l’icône du trombone), sélectionnez **Récent**, **Parcourir les canaux et les équipes**, **OneDrive**, ou **Charger à partir de mon ordinateur**, puis choisir le fichier que vous voulez partager. <br> 
    ![Capture d’écran affichant le partage d’un fichier à partir d’un canal](media/share-files-channel.png)
- Dans une conversation, cliquez sur **Joindre** l’(icône du trombone), Sélectionnez  ou **OneDrive** ou **Charger à partir de mon ordinateur**, puis choisissez le fichier que vous voulez partager. <br>
    ![Capture d’écran affichant le partage d’un fichier à partir d’une conversation](media/share-files-chat.png)
- Copiez et collez le lien de partage dans la zone de rédaction.<br>
    ![Capture d’écran affichant l’aperçu d’un fichier dans la zone de rédaction](media/share-files-link.png)

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a>Ce que vous devez savoir sur l’expérience du partage de fichier

### <a name="permissions-of-shared-files-and-sharing-links"></a>Autorisations relatives aux fichiers partagés et aux liens de partage

Lorsque des utilisateurs partagent un fichier en y accédant dans OneDrive ou des équipes et des canaux, tous les destinataires se voient accorder un accès avec l’[autorisation par défaut qui est définie au niveau de l’organisation](https://docs.microsoft.com/sharepoint/change-default-sharing-link).

Lorsqu’un utilisateur copie et colle un lien de partage, les autorisations définies sur ce lien de partage sont reconnues et l’URL SharePoint URL est réduite au nom du fichier. Entre d’autres termes, Teams n’utilise que le nom du fichier à lier à un fichier.

Lorsque des utilisateurs partagent un fichier à partir de Teams, ils peuvent définir qui peut accéder au fichier tout comme ils le font dans Microsoft 365. Ils peuvent octroyer un accès à toute personne, à des personnes au sein de votre organisation, à des personnes ayant déjà un accès ou à des personnes spécifiques (ce qui peut inclure les personnes dans une discussion entre deux personnes, dans une conversation de groupe ou dans un canal).  Lorsqu’un fichier est partagé, l’aperçu de fichier est disponible dans le message, avec toutes les actions de fichier telles que **Ouvrir en ligne**, **Télécharger** et **Copier le lien**. Le fichier s’ouvre dans Teams par défaut. Le lien de partage peut parfois ne pas être converti en aperçu de fichier au moment où l’utilisateur envoie le message. L’aperçu de fichier est généré par le système mais, dans ce cas, le lien de partage n’est pas réduit au nom de fichier uniquement.

Lorsque des utilisateurs partagent un fichier dans une conversation ou un canal, ils sont avertis si tout ou partie des destinataires n’a pas l’autorisation d’afficher le fichier. Ils peuvent modifier les autorisations sur le fichier avant de le partager en cliquant sur la flèche près de l’aperçu de fichier qui apparaît désormais dans le message.

![Capture d’écran d’une notification si des destinataires ne disposent pas des autorisations](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a>Copier un lien de partage dans Teams

Les utilisateurs peuvent copier un lien de partage SharePoint et modifier les autorisations de partage tout comme ils le font dans Microsoft 365. Ils peuvent octroyer un accès à toute personne, à des personnes au sein de votre organisation, à des personnes ayant déjà un accès ou à des personnes spécifiques. L’autorisation par défaut du lien est identique à l’autorisation par défaut défini au niveau de l’organisation, sauf si les autorisations SharePoint au niveau du site la remplacent.

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a>Configurer le partage dans OneDrive et SharePoint

Pour en savoir plus sur le partage de fichiers dans OneDrive et SharePoint, notamment comment configurer le partage et comment activer ou désactiver le partage, voir :

- [Vue d’ensemble du partage externe](https://docs.microsoft.com/sharepoint/external-sharing-overview) : décrit ce qui se passe quand des utilisateurs partagent du contenu, en fonction de ce qu’ils partagent et avec qui.

- [Gérer les paramètres de partage](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) : explique comment des administrateurs généraux et SharePoint peuvent modifier les paramètres de partage pour SharePoint et OneDrive au niveau de leur organisation.

- [Activer ou désactiver le partage externe pour un site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) : décrit comment les administrateurs SharePoint et général peuvent activer ou désactiver le partage externe pour un site.

- [Modifier le type de lien par défaut pour un site](https://docs.microsoft.com/sharepoint/change-default-sharing-link) : explique comment définir le type de lien par défaut pour le rendre plus restrictif.

## <a name="more-information"></a>Plus d’informations

- [Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams](sharepoint-onedrive-interact.md)

- [SharePoint et Teams : ensemble, c’est mieux](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [Partager des fichiers et des dossiers OneDrive](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [Partager des fichiers ou dossiers SharePoint](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
