---
title: Configurer le partage du bureau dans Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: Découvrez comment configurer une stratégie de réunion permettant aux utilisateurs de partager leurs bureaux dans des conversations ou réunions Teams.
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d75e540de7e40206f0b1dd15e26adc62d6f6baa7
ms.sourcegitcommit: d27b97f012d0cb3f1690d3673d50bbaa0caae16f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47652470"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>Configurer le partage du bureau dans Microsoft Teams
============================================

Le partage de bureau permet aux utilisateurs d'afficher un écran ou une application pendant une réunion ou une conversation. Les administrateurs peuvent configurer le partage d’écran dans Microsoft Teams pour autoriser les utilisateurs à partager l'ensemble d'un écran, d'une application ou d'un fichier. Vous pouvez permettre aux utilisateurs d’attribuer ou de demander le contrôle, d'autoriser le partage PowerPoint, d'ajouter un tableau blanc et d'autoriser les notes partagées. Vous pouvez également préciser si les utilisateurs anonymes ou externes peuvent demander le contrôle de l’écran partagé. Les participants externes aux réunions teams peuvent être classés comme suit :

- Utilisateur anonyme
- Utilisateurs invités
- Utilisateur B2B
- Utilisateur fédéré

Pour configurer le partage d’écran, vous créez une stratégie de réunion, puis vous l’attribuez aux utilisateurs que vous souhaitez gérer.

**Dans le [Centre d’administration Microsoft Teams](https://admin.teams.microsoft.com/)**

1. Sélectionnez **Réunions** > **Stratégies de réunion**.

    ![Stratégies de réunion sélectionnées](media/configure-desktop-sharing-image1.png)

2. Dans la page stratégies de la **réunion** , sélectionnez **Ajouter**.

    ![Le message stratégies de réunion](media/addMeeting.png)

3. Donnez un titre unique à votre stratégie, puis entrez une brève description.

4. Sous le **Partage de contenu**, choisissez un **Mode de partage d’écran** dans la liste déroulante :

   - **Écran complet** : permet au utilisateurs de partager la totalité de leur bureau.
   - **Application Unique** : permet aux utilisateurs de limiter le partage d’écran à une seule application active.
   - **Désactivé** : désactive le partage d’écran.

    ![Options du mode de partage](media/configure-desktop-sharing-image3.png)

  > [!Note]
  > Vous n’avez pas besoin d’activer la stratégie d’appel pour que les utilisateurs puissent utiliser le partage d’écran à partir de la discussion. Toutefois, leur son est désactivé tant qu’il n’est pas activé. Par ailleurs, l’utilisateur qui partage l’écran peut cliquer sur **Ajouter du son** pour activer l’audio. Si la stratégie d’appel est désactivée, les utilisateurs ne seront pas en mesure d’ajouter de l’audio au partage d’écran à partir d’une session de conversation.

5. Activer ou désactiver les paramètres suivants :

    - **Autoriser un participant à donner ou demander le contrôle** : permet aux membres de l’équipe de donner ou de demander le contrôle du bureau ou de l'application du présentateur.
    - **Autoriser un participant externe à attribuer ou demander le contrôle** – il s’agit d’une stratégie par utilisateur. La présence d’une organisation pour un utilisateur ne contrôle pas ce qu’il est possible de faire, quels que soient les participants externes qu’il a définis. Ce paramètre détermine si les participants externes peuvent recevoir le contrôle ou demander le contrôle de l’écran du partage, en fonction de ce que le partage a défini dans les stratégies de la réunion de leur organisation.
    - **Autoriser le partage de PowerPoint** : permet aux utilisateurs de créer des réunions autorisant le téléchargement et le partage de présentations PowerPoint.
    - **Autoriser le tableau blanc** : permet aux utilisateurs de partager un tableau blanc.
    - **Autoriser les notes partagées** : permet aux utilisateurs de prendre des notes partagées.

6. Cliquez sur **Enregistrer**.

## <a name="use-powershell-to-configure-shared-desktop"></a>Utiliser PowerShell pour configurer le bureau partagé

Vous pouvez également utiliser l’applet de commande [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) pour contrôler le partage de Bureau. Définissez les paramètres suivants :

- Description
- ScreenSharingMode
- AllowPrivateCalling
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[En savoir plus sur l’utilisation de l'applet de commande csTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).
