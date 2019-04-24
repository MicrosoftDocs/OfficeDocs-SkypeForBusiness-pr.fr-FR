---
title: Configurer le partage du bureau dans Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Configurer une stratégie de réunion pour permettre aux utilisateurs de partager leur bureau dans les conversations des équipes ou des réunions
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d0434804e7d0ec57ff4470fd8e9af23b73f8179f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198390"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>Configurer le partage du bureau dans Microsoft Teams
============================================

Le partage du bureau permet aux utilisateurs de présenter un écran ou une application pendant une réunion ou une conversation. Les administrateurs peuvent configurer Microsoft Teams pour permettre aux utilisateurs de partager un ensemble de l’écran, une application ou un fichier de partage d’écran. Vous pouvez permettre aux utilisateurs donner ou demander le contrôle, autoriser le partage de PowerPoint, ajouter un tableau blanc et les notes partagées. Vous pouvez également configurer si les utilisateurs anonymes ou externes peuvent demander le contrôle de l’écran partagé.

Pour configurer le partage d’écran, vous créez une nouvelle stratégie de réunions et puis attribuez-le aux utilisateurs que vous souhaitez gérer.

**Dans le centre d’administration Microsoft Teams**

1. Sélectionnez les **réunions** > **stratégies de la réunion**.

    ![Sélectionnez les stratégies de la réunion](media/configure-desktop-sharing-image1.png)

2. Dans la page **stratégies de la réunion** , sélectionnez **nouvelle stratégie**.

    ![Sélectionnez nouvelle stratégie](media/configure-desktop-sharing-image2.png)

3. Donnez à votre stratégie un titre unique et entrez une brève description.

4. Sous **partage de contenu**, choisissez un **mode de partage d’écran** de la liste déroulante :

   - **Écran entier** – permet aux utilisateurs de partager leur bureau.
   - **Application unique** – permet le partage d’écran utilisateurs limite à une seule application active.
   - **Désactivé** – comment désactiver le partage d’écran.

    ![Choisissez un mode de partage d’écran](media/configure-desktop-sharing-image3.png)

5. Activer ou désactiver les paramètres suivants :

    - **Autoriser un participant à faire ou demander le contrôle** – vous permet de membres de l’équipe faire ou demander le contrôle du bureau du présentateur ou d’application.
    - **Autoriser un participant externe à faire ou demander le contrôle** – permet aux invités et des utilisateurs externes (fédérés) ou demander le contrôle du bureau ou d’application du présentateur.
    - **Partage PowerPoint autoriser** - permet aux utilisateurs de créer des réunions qui autorisent les présentations PowerPoint à être téléchargé et partagés.
    - **Tableau blanc autoriser** – permet aux utilisateurs de partager un tableau blanc.
    - **Autoriser les notes partagées** – permet aux utilisateurs de prendre des notes partagées.

6. Cliquez sur **Enregistrer**.

## <a name="use-powershell-to-configure-shared-desktop"></a>Utilisation de PowerShell pour configurer le bureau partagé

Vous pouvez également utiliser l’applet de commande [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) pour contrôler le partage du bureau. Définir les paramètres suivants :

- Description
- ScreenSharingMode
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[En savoir plus sur l’utilisation de l’applet de commande csTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).

