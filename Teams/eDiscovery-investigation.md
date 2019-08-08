---
title: Mener une recherche eDiscovery de contenu dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Découvrez les actions à entreprendre et le moment opportun pour mener une recherche eDiscovery, par exemple lorsque vous devez soumettre toutes les informations stockées électroniquement dans le cadre d'une procédure juridique.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6831ec2cef16e65e2fd8dd722d436c12b7548a5c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236358"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Mener une recherche eDiscovery de contenu dans Microsoft Teams
============================

Les grandes entreprises sont souvent exposées à des actions juridiques à forte pénalité qui demandent la soumission de toutes les informations stockées électroniquement (ESI).

Toutes les équipes 1:1 ou les discussions de groupe sont journalisées dans les boîtes aux lettres des utilisateurs correspondants, et tous les messages des canaux sont journalisés dans la boîte aux lettres du groupe représentant l’équipe. Les fichiers téléchargés sont décrits dans la fonctionnalité eDiscovery pour SharePoint Online et OneDrive entreprise.

1.  Pour effectuer une analyse eDiscovery avec le contenu Microsoft Teams, reportez-vous à l’étape 1 de [ce](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) lien.

2.  Les données de Microsoft teams s’affichent sous forme de messages instantanés ou de conversations dans la sortie d’exportation eDiscovery d’Excel et vous pouvez les monter. PST dans Outlook pour afficher ces messages après l’exportation.

    Lors du montage du. PST pour l’équipe, Notez que toutes les conversations sont conservées dans le dossier de discussion d’équipe sous historique des conversations. Le titre du message s’aligne sur l’équipe et le canal. À partir de la consultation de l’image ci-dessous, vous pouvez voir ce message de Bob qui a affiché le canal Project 7 de l’équipe des spécifications de fabrication.

    ![Capture d’écran d’un dossier de discussion d’équipe dans la boîte aux lettres d’un utilisateur dans Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  Pour afficher les conversations privées dans la boîte aux lettres d'un utilisateur, accédez au dossier Conversation de l'équipe sous l'historique des conversations.

## <a name="ediscovery-of-guest-to-guest-chats"></a>Découverte électronique des discussions entre invités

Sans boîte aux lettres, les discussions invitées invitées (1xNs dans lesquelles il n’y a pas d’utilisateurs privés) ne sont pas indexées et ne sont pas incluses dans eDiscovery. Pour faciliter l’eDiscovery pour les discussions invitées, une boîte aux lettres Cloud (ou une boîte aux lettres fantôme) est créée pour le stockage des données 1xN. Une fois que les données de chat de l’équipe sont stockées dans la boîte aux lettres dans le Cloud, celles-ci sont indexées pour la découverte électronique et la recherche de contenu de conformité.

L’illustration suivante décrit le fonctionnement de eDiscovery pour les discussions invitées dans lesquelles il n’y a pas de boîte aux lettres.

![invité-à-invité-discussions-avec non-boîte aux lettres](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
