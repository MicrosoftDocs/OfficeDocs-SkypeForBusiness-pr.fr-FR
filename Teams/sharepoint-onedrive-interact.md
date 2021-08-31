---
title: Interaction entre SharePoint et les OneDrive interactions entre Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: snigdhav
search.appverid: MET150
description: SharePoint & OneDrive interaction avec les Teams ; stockage de fichiers de conversation privée & interaction entre l’équipe, le canal standard et & bibliothèque de documents.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2163201f4b9b1090c62fbe42f5236665b09164f6
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729543"
---
# <a name="how-sharepoint-and-onedrive-interact-with-microsoft-teams"></a>Interaction entre SharePoint et les OneDrive interactions entre Microsoft Teams

> [!Tip]
> Regardez la session suivante pour découvrir comment Teams interagit avec les groupes Azure Active Directory, Microsoft 365, Exchange, SharePoint et OneDrive : bases de [Microsoft Teams](https://aka.ms/teams-foundations)

Chaque équipe dans Microsoft Teams a un site d’équipe dans SharePoint, et chaque canal standard d’une équipe reçoit un dossier dans la bibliothèque de documents du site d’équipe par défaut. Chaque [canal privé possède](private-channels.md) son propre canal et SharePoint site. Pour en savoir plus sur ces sites d’équipe et de canal, voir [Teams sites connectés et les sites de canaux.](/sharepoint/teams-connected-sites)

Les fichiers partagés dans une conversation sont automatiquement ajoutés à la bibliothèque de documents, et les autorisations et options de sécurité des fichiers définies dans SharePoint sont automatiquement reflétées dans Teams. Pour voir l’impact de la modification d’une adresse de site dans SharePoint, [lisez Modifier une adresse de site.](/sharepoint/change-site-address)

Les fichiers de conversation privée sont stockés dans le dossier OneDrive de l’expéditeur et les autorisations sont automatiquement accordées à tous les participants dans le cadre du processus de partage de fichiers.

Si des licences ne leur sont pas SharePoint, ils n’ont pas d’espace OneDrive stockage dans Microsoft 365. Le partage de fichiers fonctionne dans les canaux standard, mais les utilisateurs ne peuvent pas partager de fichiers dans les conversations sans stockage OneDrive dans Microsoft 365.

En stockant les fichiers dans SharePoint bibliothèque de documents et OneDrive fichiers, toutes les règles de conformité configurées au niveau de l’organisation sont suivies. 

> [!NOTE]
> L’intégration avec SharePoint Server n’est pas prise en charge pour Teams.

Voici un exemple de relations entre une équipe, un canal standard et une bibliothèque de documents.

Pour chaque équipe, un site SharePoint est créé et le dossier **Documents** partagés est le dossier par défaut créé pour l’équipe. Chaque canal standard, y compris le **canal Général** (canal par défaut pour chaque équipe) dispose d’un dossier dans **Documents partagés.**

![Diagramme des dossiers Documents partagés dans SharePoint.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

Les paramètres SharePoint de site et de bibliothèque de documents par défaut ne peuvent pas être remplacés par un autre site ou bibliothèque de documents.

Pour chaque utilisateur, le dossier OneDrive **Fichiers de conversation Microsoft Teams** est utilisé pour stocker tous les fichiers partagés dans les conversations avec d'autres utilisateurs (en tête-à-tête ou de groupe), avec les autorisations configurées pour limiter l'accès aux utilisateurs concernés uniquement.

![Diagramme du dossier OneDrive nommé Microsoft Teams Fichiers de conversation.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

Notez que pour les équipes publiques, SharePoint site d’équipe est mis en service avec l’accès « Tout le monde sauf les utilisateurs externes ». L’équipe publique ne s’affiche pas dans Teams pour les personnes qui ne sont pas membres de cette équipe. Toutefois, ils peuvent accéder au contenu du site d SharePoint d’équipe à l’aide de l’URL SharePoint site d’équipe. 

## <a name="channel-files-tab"></a>Onglet Fichiers de canal

**L’onglet** Fichiers Teams l’affichage SharePoint documents. Sous **l’onglet Fichiers,** les utilisateurs peuvent :

- D’autres options sont disponibles **dans le** menu Nouveau fichier.
- Synchronisez des fichiers sur leur disque local.
- Dans le menu **Tous les documents,** passez de l’affichage de liste à l’affichage **de liste** compacté **à l’affichage vignettes.** 
- Identifiez les fichiers qui ont besoin d’être identifiés ou qui contiennent des programmes malveillants.
- Voir immédiatement si un fichier est en lecture seule ou extrait.
- Consultez et archivez des fichiers.
- Épingler, désépiner et modifier l’ordre de tri des fichiers.
- Identifier les fichiers qui ont besoin de métadonnées
- Choisissez parmi un grand nombre d’autres options de filtre.
- Grouper des fichiers sur la base d’en-tête de colonnes.
- Modifiez les paramètres des colonnes (déplacer vers la gauche ou la droite, masquer) et la largeur de colonne.

## <a name="default-link-type-setting"></a>Paramètre du type de lien par défaut

Type de lien de partage affiché par défaut lorsqu’un utilisateur a partagé un fichier est SharePoint centre d’administration. Voir [Modifier le type de lien par défaut lorsque les utilisateurs obtiennent des liens de partage pour](/sharepoint/change-default-sharing-link) plus d’informations.

## <a name="related-topics"></a>Sujets associés

[Gérer Teams sites connectés et des sites de canaux](/SharePoint/teams-connected-sites)

[SharePoint et Teams la collaboration .](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)

[À quoi ressemble l’expérience des invités](guest-experience.md)
