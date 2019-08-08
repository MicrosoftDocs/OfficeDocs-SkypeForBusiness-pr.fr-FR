---
title: Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: Découvrez l'interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams, comme le stockage de fichiers de conversation privée, et la relation entre l'équipe, le canal et la bibliothèque de documents.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d28a4a968fc9e478c3a13fb38acd1019221b5dcb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232277"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams

> [!Tip]
> Regardez la session suivante pour découvrir comment les équipes interagissent avec Azure Active Directory (AAD), les groupes Office 365, Exchange, SharePoint et OneDrive entreprise: [notions de bases de Microsoft teams](https://aka.ms/teams-foundations)

Dans Microsoft Teams, chaque équipe dispose d'un site dans SharePoint Online, et chaque canal d'une équipe reçoit un dossier dans la bibliothèque de documents par défaut du site de l'équipe. Les fichiers partagés dans une conversation sont automatiquement ajoutés à la bibliothèque de documents, et les autorisations et options de sécurité de fichier définies dans SharePoint sont automatiquement appliquées à Teams.

Les fichiers de conversation privée sont stockés dans le dossier OneDrive Entreprise de l'envoyeur et les autorisations sont automatiquement accordées à tous les participants dans le cadre du processus de partage de fichiers.

Si les utilisateurs ne sont pas assignés et activés pour les licences SharePoint Online, ils n’ont pas de stockage OneDrive entreprise dans Office 365. Le partage de fichiers continuera à fonctionner dans les canaux, mais les utilisateurs ne seront pas en mesure de partager des fichiers dans les conversations sans espace de stockage OneDrive entreprise dans Office 365.

En stockant les fichiers dans la bibliothèque de documents SharePoint Online et dans OneDrive Entreprise, toutes les règles de conformité configurées au niveau du client seront appliquées. 

> [!NOTE]
> Pour le moment, l’intégration avec SharePoint local n’est pas prise en charge par Microsoft Teams.

Voici un exemple de relations entre une équipe, un canal et une bibliothèque de documents.

Pour chaque équipe, un site SharePoint et le dossier par défaut **Documents partagés** sont créés. Chaque canal, y compris le canal **Général** par défaut de l'équipe, dispose d'un dossier dans le dossier **Documents partagés**.

![Diagramme de dossiers de documents partagés dans SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> Vous ne pouvez pas remplacer le site SharePoint par défaut ni la bibliothèque de documents par une autre pour le moment. Vous nous avez signalé que vous le souhaitiez, et nous y réfléchissons. Consultez la [Feuille de route de Teams](https://aka.ms/teamsroadmap) ou [Teams UserVoice](https://aka.ms/TeamsUserVoice) pour rester informé des fonctionnalités à venir.

> [!TIP]
> Pour ajouter un onglet à votre équipe qui est lié à une page de site SharePoint existante ou à votre bibliothèque de documents SharePoint existante:
> 1. Sélectionnez le signe plus à côté des onglets.
> 2. Sélectionnez **SharePoint** pour une page de site SharePoint ou une **bibliothèque de documents** existante pour une bibliothèque de documents existante.
> 3. Sélectionnez la page ou la bibliothèque de documents appropriée.

Pour chaque utilisateur, le dossier OneDrive **Fichiers de conversation Microsoft Teams** est utilisé pour stocker tous les fichiers partagés dans les conversations avec d'autres utilisateurs (en tête-à-tête ou de groupe), avec les autorisations configurées pour limiter l'accès aux utilisateurs concernés uniquement.

![Diagramme du dossier OneDrive intitulé fichiers Microsoft teams chat](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

## <a name="channel-files-tab"></a>Onglet fichiers de canal

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

L’onglet **fichiers** de teams ressemble étroitement à la vue documents SharePoint. Dans l’onglet **fichiers** , les utilisateurs peuvent:

- Voir d’autres options dans le menu **nouveau** fichier.
- Synchroniser des fichiers sur leur disque local.
- Dans le menu **tous les documents** , passez du mode **** **liste** au mode **vignettes** .
- Identifiez les fichiers qui nécessitent d’être attentifs ou qui ont des logiciels malveillants.
- Déterminez immédiatement s’il s’agit d’un fichier en lecture seule ou extrait.
- Extraire et archiver des fichiers.
- Épingler, détacher et changer l’ordre de tri des fichiers.
- Identifier les fichiers nécessitant des métadonnées
- Choisissez parmi d’autres options de filtre.
- Regroupez des fichiers en fonction d’en-têtes de colonne.
- Modifiez les paramètres de colonnes (déplacez-vous vers la gauche ou la droite, Masquer) et largeur de colonne.

## <a name="default-link-type-setting"></a>Paramètre de type de lien par défaut

SharePoint et OneDrive disposent d’un paramètre d’administrateur pour spécifier le type de lien par défaut pour les liens créés pour un fichier. Teams adopte cette même approche en réutilisant les paramètres définis par l’administrateur pour SharePoint et OneDrive. Pour plus d’informations sur cette approche, voir [modifier le type de lien par défaut lorsque les utilisateurs reçoivent des liens pour le partage](https://docs.microsoft.com/sharepoint/change-default-sharing-link). 

## <a name="more-information"></a>Plus d’informations

Pour plus d’informations sur le fonctionnement de SharePoint avec Teams, reportez-vous à la rubrique [SharePoint et équipes: meilleure combinaison](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).

Pour en savoir plus sur l’interface utilisateur pour les invités dans Microsoft Teams, prenez connaissance de [l’interface utilisateur](guest-experience.md).

