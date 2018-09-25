---
title: Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/31/2018
ms.topic: article
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: Découvrez l'interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams, comme le stockage de fichiers de conversation privée, et la relation entre l'équipe, le canal et la bibliothèque de documents.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 869adf9401e3704cc78de5f646b0b9e676e8efe9
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016524"
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams
=============================================================================

> [!Tip]
> Regarder la session suivante pour savoir comment les équipes interagit avec Azure Active Directory (DAS), groupes d’Office 365, Exchange, SharePoint et OneDrive for Business : [Notions de base sur les équipes de Microsoft](https://aka.ms/teams-foundations)

Dans Microsoft Teams, chaque équipe dispose d'un site dans SharePoint Online, et chaque canal d'une équipe reçoit un dossier dans la bibliothèque de documents par défaut du site de l'équipe. Les fichiers partagés dans une conversation sont automatiquement ajoutés à la bibliothèque de documents, et les autorisations et options de sécurité de fichier définies dans SharePoint sont automatiquement appliquées à Teams.

Les fichiers de conversation privée sont stockés dans le dossier OneDrive Entreprise de l'envoyeur et les autorisations sont automatiquement accordées à tous les participants dans le cadre du processus de partage de fichiers.

Si les utilisateurs ne sont pas affectés et activés avec SharePoint Online licences, ils n’ont OneDrive pour le stockage d’entreprise dans Office 365. Partage de fichiers continueront de fonctionner dans des canaux, mais les utilisateurs ne pourront pas partager des fichiers dans les salles de conversation sans OneDrive pour le stockage d’entreprise dans Office 365.

En stockant les fichiers dans la bibliothèque de documents SharePoint Online et dans OneDrive Entreprise, toutes les règles de conformité configurées au niveau du client seront appliquées. 

> [!NOTE]
> Intégration Sharepoint sur site n’est pas pris en charge pour Microsoft Teams à ce stade.

Voici un exemple de relations entre une équipe, un canal et une bibliothèque de documents.

Pour chaque équipe, un site SharePoint et le dossier par défaut **Documents partagés** sont créés. Chaque canal, y compris le canal **Général** par défaut de l'équipe, dispose d'un dossier dans le dossier **Documents partagés**.

![Diagramme des dossiers de documents partagés dans SharePoint Online pour une équipe et ses canaux dans Microsoft Teams.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> Vous ne pouvez pas remplacer le site SharePoint par défaut ni la bibliothèque de documents par une autre pour le moment. Vous nous avez signalé que vous le souhaitiez, et nous y réfléchissons. Consultez la [Feuille de route de Teams](https://aka.ms/teamsroadmap) ou [Teams UserVoice](https://aka.ms/TeamsUserVoice) pour rester informé des fonctionnalités à venir.

> [!TIP]
> Pour ajouter un onglet à votre équipe que des liens vers un SharePoint existant à SharePoint existante bibliothèque de documents ou de site :
> 1. Sélectionnez le signe plus en regard des onglets.
> 2. Sélectionnez le **site Web**.
> 3. Tapez un nom et entrez l’URL de votre bibliothèque de documents ou de site SharePoint.

Pour chaque utilisateur, le dossier OneDrive **Fichiers de conversation Microsoft Teams** est utilisé pour stocker tous les fichiers partagés dans les conversations avec d'autres utilisateurs (en tête-à-tête ou de groupe), avec les autorisations configurées pour limiter l'accès aux utilisateurs concernés uniquement.

![Diagramme du dossier OneDrive nommé Fichiers de conversation Microsoft Teams pour les conversations de chaque utilisateur.](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)
