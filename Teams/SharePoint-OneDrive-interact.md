---
title: Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: Découvrez l'interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams, comme le stockage de fichiers de conversation privée, et la relation entre l'équipe, le canal et la bibliothèque de documents.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f790a01050811ee46526fe37a4d6c14f107491b5
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2019
ms.locfileid: "33827739"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams

> [!Tip]
> Regarder la session suivante pour savoir comment les équipes interagit avec Azure Active Directory (DAS), groupes d’Office 365, Exchange, SharePoint et OneDrive for Business : [Notions de base sur les équipes de Microsoft](https://aka.ms/teams-foundations)

Dans Microsoft Teams, chaque équipe dispose d'un site dans SharePoint Online, et chaque canal d'une équipe reçoit un dossier dans la bibliothèque de documents par défaut du site de l'équipe. Les fichiers partagés dans une conversation sont automatiquement ajoutés à la bibliothèque de documents, et les autorisations et options de sécurité de fichier définies dans SharePoint sont automatiquement appliquées à Teams.

Les fichiers de conversation privée sont stockés dans le dossier OneDrive Entreprise de l'envoyeur et les autorisations sont automatiquement accordées à tous les participants dans le cadre du processus de partage de fichiers.

Si les utilisateurs ne sont pas affectés et activés avec SharePoint Online licences, ils n’ont OneDrive pour le stockage d’entreprise dans Office 365. Partage de fichiers continueront de fonctionner dans des canaux, mais les utilisateurs ne pourront pas partager des fichiers dans les salles de conversation sans OneDrive pour le stockage d’entreprise dans Office 365.

En stockant les fichiers dans la bibliothèque de documents SharePoint Online et dans OneDrive Entreprise, toutes les règles de conformité configurées au niveau du client seront appliquées. 

> [!NOTE]
> Intégration SharePoint sur site n’est pas pris en charge pour Microsoft Teams à ce stade.

Voici un exemple de relations entre une équipe, un canal et une bibliothèque de documents.

Pour chaque équipe, un site SharePoint et le dossier par défaut **Documents partagés** sont créés. Chaque canal, y compris le canal **Général** par défaut de l'équipe, dispose d'un dossier dans le dossier **Documents partagés**.

![Diagramme des dossiers de documents partagés dans SharePoint Online pour une équipe et ses canaux dans Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> Vous ne pouvez pas remplacer le site SharePoint par défaut ni la bibliothèque de documents par une autre pour le moment. Vous nous avez signalé que vous le souhaitiez, et nous y réfléchissons. Consultez la [Feuille de route de Teams](https://aka.ms/teamsroadmap) ou [Teams UserVoice](https://aka.ms/TeamsUserVoice) pour rester informé des fonctionnalités à venir.

> [!TIP]
> Pour ajouter un onglet à votre équipe qui lie à une page de site SharePoint existante ou à votre bibliothèque de documents SharePoint existante :
> 1. Sélectionnez le signe plus en regard des onglets.
> 2. Sélectionnez la **Bibliothèque de documents** pour une bibliothèque de documents existante ou **SharePoint** pour une page de site SharePoint existante.
> 3. Sélectionnez la bibliothèque de documents ou page appropriée.

Pour chaque utilisateur, le dossier OneDrive **Fichiers de conversation Microsoft Teams** est utilisé pour stocker tous les fichiers partagés dans les conversations avec d'autres utilisateurs (en tête-à-tête ou de groupe), avec les autorisations configurées pour limiter l'accès aux utilisateurs concernés uniquement.

![Diagramme du dossier OneDrive nommé Fichiers de conversation Microsoft Teams pour les conversations de chaque utilisateur.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a>Onglet fichiers de canal

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

L’onglet **fichiers** dans les équipes ressemble à l’affichage de documents SharePoint. Sous l’onglet **fichiers** , les utilisateurs peuvent :

- Afficher d’autres options dans le menu fichier de **Nouveau** .
- Synchronisation de fichiers sur leur lecteur local.
- Dans le menu de **Tous les Documents** , passer d’affichage de **liste** à **liste Compact** à la vue **mosaïques** .
- Identifier les fichiers qui nécessitent une attention ou qu’un programme malveillant.
- Voir immédiatement si un fichier est en lecture seule ou checked out.
- Extraire et archiver des fichiers.
- Épingler et désépingler modifier l’ordre de tri des fichiers.
- Identifier les fichiers qui nécessitent des métadonnées
- Choisissez à partir de nombreuses autres options de filtre.
- Fichiers de groupe basées sur les en-têtes de colonne.
- Modifier les paramètres de colonne (déplacer vers la gauche ou droite, masquer) et la largeur de colonne.

## <a name="default-link-type-setting"></a>Type de lien par défaut

SharePoint et OneDrive ont un paramètre d’administration pour spécifier le type de lien par défaut pour les liens qui sont créées pour un fichier. Les équipes adopte cette même approche en réutilisant les paramètres que l’administrateur définit pour SharePoint et OneDrive. Plus d’informations sur cette approche sont décrits dans [Modifier le type de liaison par défaut lorsque les utilisateurs obtiennent des liens pour le partage](https://docs.microsoft.com/sharepoint/change-default-sharing-link). 

## <a name="more-information"></a>Plus d’informations

Pour plus d’informations sur le fonctionne de SharePoint avec des équipes, voir [SharePoint et les équipes : une association efficace](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).

Pour en savoir plus sur l’expérience invité dans les équipes, lire les [Nouveautés de l’expérience de l’invité](guest-experience.md).

