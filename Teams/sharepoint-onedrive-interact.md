---
title: Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: Interaction de SharePoint Online & OneDrive Entreprise avec Teams stockage de fichiers de conversation privée & interaction entre l'équipe, le canal standard et & bibliothèque de documents.
localization_priority: Normal
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d063cae8b87ffcacd63676da17fc000384c432c
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948622"
---
# <a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams

> [!Tip]
> Visionnez la session suivante pour découvrir comment Microsoft Teams interagit avec Azure Active Directory (AAD), les groupes Microsoft 365, Exchange, SharePoint and OneDrive Entreprise : [Fondements de Microsoft Teams](https://aka.ms/teams-foundations)

Chaque équipe dans Microsoft Teams a un site d'équipe dans SharePoint Online, et chaque canal standard d'une équipe reçoit un dossier dans la bibliothèque de documents du site d'équipe par défaut. Les fichiers partagés dans une conversation sont automatiquement ajoutés à la bibliothèque de documents, et les autorisations et options de sécurité des fichiers définies dans SharePoint sont automatiquement reflétées dans Teams. Pour voir l'impact de la modification d'une adresse de site dans SharePoint, lisez [Modifier une adresse de site.](/sharepoint/change-site-address)

> [!NOTE]
> Cet article s'applique uniquement aux canaux standard. L'architecture des canaux privés est différente des canaux standard. Chaque canal privé possède sa propre collection de sites SharePoint distincte du site d'équipe parent. Pour en savoir plus, [consultez canaux privés dans Microsoft Teams.](private-channels.md)

Les fichiers de conversation privée sont stockés dans le dossier OneDrive Entreprise de l'expéditeur et les autorisations sont automatiquement accordées à tous les participants dans le cadre du processus de partage de fichiers.

Si des licences SharePoint Online ne sont pas affectées et activées pour les utilisateurs, ceux-ci ne disposent pas d'un stockage OneDrive Entreprise dans Microsoft 365 ou Office 365. Le partage de fichiers continuera à fonctionner dans les canaux standard, mais les utilisateurs ne pourront pas partager de fichiers dans les conversations sans stockage OneDrive Entreprise dans Microsoft 365 ou Office 365.

En stockant les fichiers dans la bibliothèque de documents SharePoint Online et dans OneDrive Entreprise, toutes les règles de conformité configurées au niveau du client seront appliquées. 

> [!NOTE]
> L'intégration à SharePoint en local n'est pas prise en charge pour Microsoft Teams pour le moment.

Voici un exemple de relations entre une équipe, un canal standard et une bibliothèque de documents.

Pour chaque équipe, un site SharePoint est créé et le dossier **Documents** partagés est le dossier par défaut créé pour l'équipe. Chaque canal standard, y compris le **canal Général** (canal par défaut pour chaque équipe) dispose d'un dossier dans **Documents partagés.**

![Diagramme des dossiers Documents partagés dans SharePoint Online.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> Vous ne pouvez pas remplacer le site SharePoint par défaut ni la bibliothèque de documents par une autre pour le moment. Vous nous avez signalé que vous le souhaitiez, et nous y réfléchissons. Consultez la [Feuille de route de Teams](https://aka.ms/teamsroadmap) ou [Teams UserVoice](https://aka.ms/TeamsUserVoice) pour rester informé des fonctionnalités à venir.

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

> [!TIP]
> Pour ajouter un onglet à votre équipe qui pointe vers une page de site SharePoint existante ou vers votre bibliothèque de documents SharePoint existante :
> 1. Sélectionnez le signe plus en côté des onglets.
> 2. Sélectionnez **SharePoint pour** une page de site SharePoint existante ou **une** bibliothèque de documents pour une bibliothèque de documents existante.
> 3. Sélectionnez la page ou la bibliothèque de documents appropriée.

Pour chaque utilisateur, le dossier OneDrive **Fichiers de conversation Microsoft Teams** est utilisé pour stocker tous les fichiers partagés dans les conversations avec d'autres utilisateurs (en tête-à-tête ou de groupe), avec les autorisations configurées pour limiter l'accès aux utilisateurs concernés uniquement.

![Diagramme du dossier OneDrive nommé Fichiers de conversation Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

Notez que pour les équipes publiques, le site d'équipe SharePoint est mis en service avec l'accès « Tout le monde sauf les utilisateurs externes ». L'équipe publique ne s'affiche pas dans Teams pour les personnes qui ne sont pas membres de cette équipe. Toutefois, ils peuvent accéder au contenu sur le site d'équipe SharePoint à l'aide de l'URL du site d'équipe SharePoint. 

## <a name="channel-files-tab"></a>Onglet Fichiers de canal

> [!INCLUDE [new feature coming soon](includes/new-feature-coming-soon-section.md)]

**L'onglet** Fichiers dans Teams ressemble beaucoup à l'affichage Documents SharePoint. Sous **l'onglet Fichiers,** les utilisateurs peuvent :

- D'autres options sont disponibles **dans le** menu Nouveau fichier.
- Synchronisez des fichiers sur leur disque local.
- Dans le menu **Tous les documents,** passez de l'affichage de liste à l'affichage **de liste** compacté **à l'affichage vignettes.** 
- Identifiez les fichiers qui ont besoin d'être identifiés ou qui contiennent des programmes malveillants.
- Voir immédiatement si un fichier est en lecture seule ou extrait.
- Consultez et archivez des fichiers.
- Épingler, désépiner et modifier l'ordre de tri des fichiers.
- Identifier les fichiers qui ont besoin de métadonnées
- Choisissez parmi un grand nombre d'autres options de filtre.
- Grouper des fichiers sur la base d'en-tête de colonnes.
- Modifiez les paramètres des colonnes (déplacer vers la gauche ou la droite, masquer) et la largeur de colonne.

## <a name="default-link-type-setting"></a>Paramètre du type de lien par défaut

SharePoint et OneDrive ont un paramètre d'administration qui spécifie le type de lien par défaut pour les liens créés pour un fichier. Teams adopte la même approche en utilsant les paramètres que l'administrateur définit pour SharePoint et OneDrive. Des informations plus détaillées sur cette approche sont décrites dans Modifier le type de lien par défaut lorsque les utilisateurs [obtiennent des liens pour le partage.](/sharepoint/change-default-sharing-link) 

## <a name="more-information"></a>Plus d’informations

Pour plus d'informations sur le fonctionnement de SharePoint avec Teams, voir [SharePoint et Teams : meilleur ensemble.](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

Pour en savoir plus sur l'expérience des invités dans Teams, lisez ce à quoi [ressemble l'expérience des invités.](guest-experience.md)