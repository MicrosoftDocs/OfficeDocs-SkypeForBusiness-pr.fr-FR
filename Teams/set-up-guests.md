---
title: Activation ou désactivation de l’accès invité à Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Découvrez comment activer ou désactiver la fonctionnalité d’accès invité dans Microsoft teams en tant qu’administrateur 365 Office.
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 297a101389de2e1609697ffa2c30a2a8b7a84080
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2020
ms.locfileid: "45042776"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Activation ou désactivation de l’accès invité à Microsoft teams
===================================================

Par défaut, l’accès invité est désactivé. En tant qu’administrateur Microsoft 365 ou Office 365, vous devez activer l’accès invité pour les équipes pour que l’administrateur ou les propriétaires d’équipes puissent ajouter des invités. Pour activer l’accès invité, utilisez la [liste de contrôle d’accès invité](guest-access-checklist.md). 

Après avoir activé l’accès invité, il est possible que les modifications soient prises en compte. Si un utilisateur voit le message « contactez votre administrateur » lorsqu’il essaye d’ajouter un invité à son équipe, il est probable que l’accès invité n’ait pas été activé ou que les paramètres ne soient pas encore effectifs.

> [!IMPORTANT]
> L’activation de l’accès invité dépend des paramètres d’Azure Active Directory, de Microsoft 365 ou d’Office 365, SharePoint Online et Teams. Pour plus d’informations, voir [autoriser l’accès invité dans Microsoft teams](Teams-dependencies.md).



## <a name="configure-guest-access-in-the-teams-admin-center"></a>Configurer l’accès invité dans le centre d’administration teams

1. Se connecter au centre d’administration de Microsoft Teams.

2. Sélectionnez **paramètres Org-wide** > **accès invité**.

3. Définissez **autoriser l’accès invité dans Microsoft teams** **sur activé**.

    ![Bouton Autoriser l’accès invité sur On ](media/set-up-guests-image1.png)

4. Sous **appel**, **réunion**et **messagerie**, sélectionnez **activé** ou **désactivé** pour chaque fonctionnalité, en fonction de ce que vous voulez autoriser pour les utilisateurs invités.

      - **Passer des appels privés** : mettre ce paramètre sur **On** pour permettre aux invités d’effectuer des appels privés.
      - **Autoriser IP vidéo** : mettre ce paramètre sur**On** pour permettre aux invités d’utiliser la vidéo dans leurs appels et réunions.
      - **Mode de partage d’écran** : ce paramètre détermine la disponibilité de l’écran de partage pour les utilisateurs invités. 
          - Mettre ce paramètre sur **Désactivé** pour supprimer la possibilité pour les invités de partager leurs écrans dans Teams. 
          - Activez ce paramètre sur **Application unique** pour autoriser le partage d’applications individuelles. 
          - Activez ce paramètre sur **Écran entier** pour autoriser le partage d’écran entier.
      - **Autoriser Conférence maintenant** : mettre ce paramètre sur **On** pour permettre aux invités d’utiliser la fonctionnalité Conférence maintenant dans Microsoft Teams.
      - **Modifier les messages envoyés** : mettre ce paramètre sur**On** pour permettre aux invités de modifier les messages électroniques qu’ils ont envoyés précédemment.
      - **Invités peuvent supprimer les messages envoyés** : mettre ce paramètre sur**On** pour permettre aux invités de supprimer les messages électroniques qu’ils ont envoyés précédemment.
      - **Conversation** : mettre ce paramètre sur**On** pour donner aux invités la possibilité d’utiliser la conversation dans Teams.
      - **Utiliser Giphys dans les conversations** : mettre ce paramètre sur **On** pour permettre aux invités d’utiliser des Giphys dans les conversations. Giphy est une base de données en ligne et moteur de recherche qui permet aux utilisateurs de rechercher et partager des fichiers GIF animés. Chaque Giphy est affecté à une évaluation du contenu.
      - **Évaluation du contenu Giphy** : sélectionner une note dans la liste déroulante :
          - **Autoriser tout le contenu** : les invités pourront insérer tous les Giphys dans des conversations, quelle que soit l’évaluation du contenu.
          - **Modéré** : les invités pourront insérer Giphys dans les conversations, mais seront relativement limités pour le contenu adulte.
          - **Strict** : les invités seront en mesure d’insérer des Giphys dans les discussions, mais ils ne seront pas autorisés à insérer des contenus adultes.
      - **Utiliser mèmes dans conversations** : activez ce paramètre pour autoriser les **invités à utiliser** mèmes dans les conversations.
      - **Utiliser des Autocollants dans les conversations** : mettre ce paramètre sur **On** pour permettre aux invités d’utiliser des Autocollants dans les conversations. 

5. Cliquez sur **Enregistrer**.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Utiliser PowerShell pour activer ou désactiver l’accès invité

Lire [Utiliser PowerShell pour activer ou désactiver l’accès invité](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)


## <a name="video-adding-guests-in-teams"></a>Vidéo : ajout d’invités dans teams

|  |  |
|---------|---------|
| Ajout d'invités dans Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 


## <a name="external-access-federation-vs-guest-access"></a>Accès externe (fédération) et accès invité

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]