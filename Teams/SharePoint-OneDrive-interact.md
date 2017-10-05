---
title: "Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams | Support Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Découvrez l'interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams, comme le stockage de fichiers de conversation privée, et la relation entre l'équipe, le canal et la bibliothèque de documents."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: cf971714c1ad3b797c181f982ea8688bf8c73977
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2017
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams
=============================================================================

Dans Microsoft Teams, chaque équipe dispose d'un site dans SharePoint Online, et chaque canal d'une équipe reçoit un dossier dans la bibliothèque de documents par défaut du site de l'équipe. Les fichiers partagés dans une conversation sont automatiquement ajoutés à la bibliothèque de documents, et les autorisations et options de sécurité de fichier définies dans SharePoint sont automatiquement appliquées à Teams.

Les fichiers de conversation privée sont stockés dans le dossier OneDrive Entreprise de l'**envoyeur** et les autorisations sont automatiquement accordées à tous les participants dans le cadre du processus de partage de fichiers.

Si SharePoint Online n’est pas activé dans votre client, les utilisateurs de Microsoft Teams ne seront pas toujours en mesure de partager des fichiers avec les équipes. Les utilisateurs des services de conversation privée ne peuvent pas partager de fichiers, car OneDrive Entreprise (qui est lié à la licence SharePoint) est requis.

En stockant les fichiers dans la bibliothèque de documents SharePoint Online et dans OneDrive Entreprise, toutes les règles de conformité configurées au niveau du client seront appliquées.

Voici un exemple de relations entre une équipe, un canal et une bibliothèque de documents.

Pour chaque équipe, un site SharePoint et le dossier par défaut *Documents partagés* sont créés. Chaque canal, y compris le canal **Général** par défaut de l'équipe, dispose d'un dossier sous le dossier *Documents partagés*.

![](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

Pour chaque utilisateur, le dossier OneDrive *Fichiers de conversation Microsoft Teams* est utilisé pour stocker tous les fichiers partagés dans les conversations avec d'autres utilisateurs (en tête-à-tête ou de groupe), avec les autorisations configurées pour limiter l'accès aux utilisateurs concernés uniquement.

![](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
