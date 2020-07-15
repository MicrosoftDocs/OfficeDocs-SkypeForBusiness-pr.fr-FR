---
title: Partager des fichiers dans Microsoft teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: haagaraw
audience: admin
search.appverid: MET150
description: En savoir plus sur l’interface de partage de fichiers dans Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 98935f7d8629e22b733b12f3f046ccb7af36b396
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138354"
---
# <a name="sharing-files-in-microsoft-teams"></a>Partager des fichiers dans Microsoft teams

Dans Microsoft Teams, les utilisateurs peuvent partager du contenu avec d’autres utilisateurs d’équipes au sein de leur organisation et en dehors. Le partage dans teams repose sur les paramètres configurés dans SharePoint et OneDrive, de sorte que ce que vous configurez pour SharePoint et OneDrive contrôle le partage dans teams également.

## <a name="overview"></a>Vue d’ensemble

Les utilisateurs peuvent partager des fichiers à partir de OneDrive, des équipes et des sites auxquels ils ont accès et de leur ordinateur. Pour partager un fichier, les utilisateurs peuvent procéder comme suit :

- Dans un canal, cliquez sur **joindre** (l’icône trombone), **sur récent**, **Parcourir les équipes et les canaux**, **OneDrive**ou **Télécharger à partir de mon ordinateur**, puis choisissez le fichier à partager. <br> 
    ![Capture d’écran montrant le partage d’un fichier à partir d’un canal](media/share-files-channel.png)
- Dans une discussion, cliquez sur **joindre** (l’icône de trombone), sur Sélectionner ou sur **OneDrive** ou **Télécharger à partir de mon ordinateur**, puis choisissez le fichier à partager. <br>
    ![Capture d’écran montrant le partage d’un fichier à partir d’une conversation](media/share-files-chat.png)
- Copiez et collez le lien de partage dans la zone de rédaction.<br>
    ![Capture d’écran montrant un aperçu de fichier dans la zone de rédaction](media/share-files-link.png)

### <a name="what-you-need-to-know-about-the-file-sharing-experience"></a>Ce que vous devez savoir sur l’interface de partage de fichiers

### <a name="permissions-of-shared-files-and-sharing-links"></a>Autorisations de partage de fichiers et de liens de partage

Lorsque les utilisateurs partagent un fichier en naviguant dans OneDrive ou équipes et canaux, tous les destinataires ont accès à l' [autorisation par défaut définie au niveau de l’organisation](https://docs.microsoft.com/sharepoint/change-default-sharing-link).

Lorsqu’un utilisateur copie et colle un lien de partage, les autorisations définies sur ce lien de partage sont honorées et l’URL SharePoint est raccourcie vers le nom du fichier. En d’autres termes, teams utilise uniquement le nom de fichier pour créer un lien vers un fichier.

Lorsque les utilisateurs partagent un fichier à partir de teams, ils peuvent définir qui peut accéder au fichier de la même manière que sur Microsoft 365. Ils peuvent donner accès à tout le monde, à des personnes de votre organisation, à des personnes disposant d’un accès existant ou à des personnes spécifiques (qui peuvent inclure les personnes dans une discussion 1:1, une discussion de groupe ou un canal).  Lorsqu’un fichier est partagé, l’aperçu du fichier est disponible dans le message, ainsi que toutes les actions de fichier, par exemple, **ouvrir en ligne**, **Télécharger**et **copier le lien**. Par défaut, le fichier s’ouvre dans Teams. Il est possible que le lien de partage ne soit pas converti en aperçu de fichier au moment où l’utilisateur envoie le message. L’aperçu du fichier sera généré par le système, mais dans ce scénario, le lien de partage ne sera pas raccourci au seul nom de fichier.

Lorsqu’un utilisateur partage un fichier dans une conversation ou un canal, il est averti que certains ou tous les destinataires ne sont pas autorisés à afficher le fichier. Ils peuvent modifier les autorisations du fichier avant de le partager en cliquant sur la flèche en regard de l’aperçu du fichier qui apparaît désormais dans le message.

![Capture d’écran de la notification si les destinataires ne disposent pas des autorisations](media/share-files-permissions.png)

### <a name="copy-a-sharing-link-in-teams"></a>Copier un lien de partage dans teams

Les utilisateurs peuvent copier un lien de partage SharePoint et modifier les autorisations de partage de la même manière que sur Microsoft 365. Ils peuvent donner accès à tout le monde, à des personnes de votre organisation, à des personnes disposant d’un accès existant ou à des personnes spécifiques. L’autorisation par défaut du lien est identique à celle définie par défaut au niveau de l’organisation, sauf si les autorisations de niveau de site SharePoint le remplacent.

## <a name="configure-sharing-in-onedrive-and-sharepoint"></a>Configurer le partage dans OneDrive et SharePoint

Pour plus d’informations sur le partage de fichiers dans OneDrive et SharePoint, notamment sur la configuration du partage et la façon d’activer ou de désactiver le partage, voir :

- [Présentation du partage externe](https://docs.microsoft.com/sharepoint/external-sharing-overview) -décrit ce qui se produit lorsque les utilisateurs partagent le partage, en fonction de ce qui est partagé et avec qui.

- [Gérer les paramètres de partage](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off) : décrit la façon dont les administrateurs généraux et SharePoint peuvent modifier leurs paramètres de partage de niveau Organisation pour SharePoint et OneDrive.

- [Activer ou désactiver le partage externe pour un site](https://docs.microsoft.com/sharepoint/change-external-sharing-site) : décrit la manière dont les administrateurs généraux et SharePoint peuvent activer ou désactiver le partage externe pour un site.

- [Changer le type de lien par défaut d’un site](https://docs.microsoft.com/sharepoint/change-default-sharing-link) -décrit comment définir le type de lien par défaut afin d’en limiter l’efficacité.

## <a name="more-information"></a>Plus d’informations

- [Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams](sharepoint-onedrive-interact.md)

- [SharePoint et équipes : utilisation conjointe](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

- [Partager des fichiers et des dossiers OneDrive](https://support.office.com/article/Share-OneDrive-files-and-folders-9fcc2f7d-de0c-4cec-93b0-a82024800c07#OS_Type=OneDrive_-_Business)

- [Partager des fichiers ou des dossiers SharePoint](https://support.office.com/article/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c)
