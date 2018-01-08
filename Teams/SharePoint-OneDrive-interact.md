---
title: "Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Découvrez l'interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams, comme le stockage de fichiers de conversation privée, et la relation entre l'équipe, le canal et la bibliothèque de documents."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: b7d9ffad23c8f26d7d95c3f31df4ff0307517179
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/20/2017
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams
=============================================================================

Dans Microsoft Teams, chaque équipe dispose d'un site dans SharePoint Online, et chaque canal d'une équipe reçoit un dossier dans la bibliothèque de documents par défaut du site de l'équipe. Les fichiers partagés dans une conversation sont automatiquement ajoutés à la bibliothèque de documents, et les autorisations et options de sécurité de fichier définies dans SharePoint sont automatiquement appliquées à Teams.

Les fichiers de conversation privée sont stockés dans le dossier OneDrive Entreprise de l'**envoyeur** et les autorisations sont automatiquement accordées à tous les participants dans le cadre du processus de partage de fichiers.

Si SharePoint Online n’est pas activé dans votre client, les utilisateurs de Microsoft Teams ne peuvent pas partager des fichiers avec les équipes. Les utilisateurs des services de conversation privée ne peuvent pas non plus partager de fichiers, car OneDrive Entreprise (qui est lié à la licence SharePoint) est requis.

En stockant les fichiers dans la bibliothèque de documents SharePoint Online et dans OneDrive Entreprise, toutes les règles de conformité configurées au niveau du client seront appliquées.

Voici un exemple de relations entre une équipe, un canal et une bibliothèque de documents.

Pour chaque équipe, un site SharePoint et le dossier par défaut *Documents partagés* sont créés. Chaque canal, y compris le canal **Général** par défaut de l'équipe, dispose d'un dossier sous le dossier *Documents partagés*.

![Diagramme des dossiers de documents partagés dans SharePoint Online pour une équipe et ses canaux dans Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

Pour chaque utilisateur, le dossier OneDrive *Fichiers de conversation Microsoft Teams* est utilisé pour stocker tous les fichiers partagés dans les conversations avec d'autres utilisateurs (en tête-à-tête ou de groupe), avec les autorisations configurées pour limiter l'accès aux utilisateurs concernés uniquement.

![Diagramme du dossier OneDrive nommé Fichiers de conversation Microsoft Teams pour les conversations de chaque utilisateur.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
