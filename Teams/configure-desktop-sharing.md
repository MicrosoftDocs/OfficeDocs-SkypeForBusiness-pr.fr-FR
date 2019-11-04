---
title: Configurer le partage du bureau dans Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Configurer une stratégie de réunion pour permettre aux utilisateurs de partager leur bureau dans des conversations ou des réunions teams
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 99c6e2a5adb9d0f9a4b4e3f6f17b7484bda96a74
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37516885"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>Configurer le partage du bureau dans Microsoft Teams
============================================

Le partage de bureau permet aux utilisateurs de présenter un écran ou une application pendant une réunion ou une conversation. Les administrateurs peuvent configurer le partage d’écran dans Microsoft teams pour permettre aux utilisateurs de partager tout l’écran, une application ou un fichier. Vous pouvez permettre aux utilisateurs de donner ou de demander le contrôle, d’autoriser le partage PowerPoint, d’ajouter un tableau blanc et de permettre des notes partagées. Vous pouvez également configurer la possibilité pour les utilisateurs anonymes ou externes d’exiger le contrôle de l’écran partagé.

Pour configurer le partage d’écran, vous devez créer une nouvelle stratégie de réunion, puis l’affecter aux utilisateurs que vous voulez gérer.

**Dans le centre d’administration Microsoft teams**

1. Sélectionnez **** > **stratégies de réunion**pour les réunions.

    ![Capture d’écran montrant les stratégies de réunion sélectionnées](media/configure-desktop-sharing-image1.png)

2. Dans la page stratégies de la **réunion** , sélectionnez **nouvelle stratégie**.

    ![Capture d’écran montrant le message stratégies de réunion](media/configure-desktop-sharing-image2.png)

3. Donnez un titre unique à votre politique et entrez une brève description.

4. Sous **partage de contenu**, choisissez un **mode de partage d’écran** dans la liste déroulante :

   - **Tout l’écran** : permet aux utilisateurs de partager leur bureau entier.
   - **Application unique** -permet aux utilisateurs de limiter le partage d’écran à une seule application active.
   - **Désactivé** -désactive le partage d’écran.

    ![Capture d’écran montrant les options du mode de partage](media/configure-desktop-sharing-image3.png)

5. Activer ou désactiver les paramètres suivants :

    - **Permettre à un participant de donner ou demander le contrôle** – permet aux membres de l’équipe de donner ou demander le contrôle de l’application ou du Bureau du présentateur.
    - **Autoriser un participant externe à céder ou demander le contrôle** – permet aux invités et aux utilisateurs externes d’octroyer le contrôle du bureau ou de l’application du présentateur.
    - **Autoriser le partage PowerPoint** -permet aux utilisateurs de créer des réunions permettant de télécharger et de partager des présentations PowerPoint.
    - **Autoriser le tableau blanc** : permet aux utilisateurs de partager un tableau blanc.
    - **Autoriser les notes partagées** : permet aux utilisateurs de prendre des notes partagées.

6. Cliquez sur **Enregistrer**.

## <a name="use-powershell-to-configure-shared-desktop"></a>Utiliser PowerShell pour configurer le bureau partagé

Vous pouvez également utiliser l’applet de commande [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) pour contrôler le partage de bureau. Définissez les paramètres suivants :

- Description
- ScreenSharingMode
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[En savoir plus sur l’utilisation de l’applet de passe csTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).

