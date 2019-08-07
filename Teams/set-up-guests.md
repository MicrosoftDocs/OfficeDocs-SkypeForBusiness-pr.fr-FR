---
title: Activation ou désactivation de l’accès invité à Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Activer ou désactiver la fonctionnalité d’accès invité dans Microsoft Teams
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240e93d5f6329090940e6bf49cb2d6a4ee46ce2f
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2019
ms.locfileid: "35221450"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a>Activation ou désactivation de l’accès invité à Microsoft teams
===================================================

En tant qu'administrateur d'Office 365, vous devez activer la fonctionnalité Invité pour que vous ou les utilisateurs de votre organisation (notamment les propriétaires d'équipe) puissiez ajouter des invités.

Les paramètres d'invité sont définis dans Azure Active Directory. Il faut environ 2 à 24 heures pour que les modifications prennent effet dans votre organisation Office 365. Si un utilisateur voit le message « Contactez votre administrateur » lorsqu'il essaye d'ajouter un invité à son équipe, il est probable que la fonctionnalité d'invité ne soit pas activée ou que les paramètres ne sont pas encore actifs.

> [!IMPORTANT]
> Pour activer l’expérience complète de la fonctionnalité d’accès invité, il est important de comprendre la dépendance des autorisations principales entre Microsfot Teams, Azure Active Directory et Office 365. Pour plus d'informations, reportez-vous à la rubrique [Autoriser l’accès invité dans Microsoft Teams](Teams-dependencies.md).

## <a name="guest-access-vs-external-access-federation"></a>Accès invité et accès externe (fédération)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a>Configurer l’accès invité dans le centre d’administration de Microsoft Teams

1.  Se connecter au centre d’administration de Microsoft Teams.

2.  Sélectionnez **paramètres Org-wide** > **accès invité**.

3. Mettre le bouton bascule**Autoriser l’accès invité dans Microsoft Teams** sur **On**.

    ![Bouton Autoriser l’accès invité sur On ](media/set-up-guests-image1.png)

4.  Mettre les boutons bascules sous **Appel**, **Réunion**, et **Messagerie** sur **On** ou **Off**, en fonction de la fonctionnalité que vous voulez autoriser pour les utilisateurs invités.

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
    - **Utiliser mèmes dans conversations** : activez ce paramètre **** pour autoriser les invités à utiliser mèmes dans les conversations.
    - **Utiliser des Autocollants dans les conversations** : mettre ce paramètre sur **On** pour permettre aux invités d’utiliser des Autocollants dans les conversations. 


5.  Cliquez sur **Enregistrer**.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Utiliser PowerShell pour activer ou désactiver l’accès invité

1.  Télécharger le module PowerShell Skype Entreprise Online à partir de https://www.microsoft.com/en-us/download/details.aspx?id=39366
 
2.  Connecter une session PowerShell à un point de terminaison Skype Entreprise Online.

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  Vérifier votre configuration et si `AllowGuestUser` est `$False`, utilisez l’applet de commande [Ensemble CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) défini sur `$True`.

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
Vous pouvez désormais avoir des utilisateurs invités dans Teams pour votre organisation.

## <a name="more-information"></a>Plus d’informations

Regardez la vidéo suivante pour plus de détails à propos de l'accès invité.

|  |  |
|---------|---------|
| Ajout d'invités dans Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
