---
title: Activer ou désactiver l'accès invité de Microsoft Teams
author: LaithAlShamri
ms.author: lolaj
manager: serdars
ms.date: 10/11/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Activer ou désactiver la fonctionnalité d’accès invité dans Microsoft Teams
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ab67b3fa9ad58c1aa3e8fdd254e3b3515743b4c
ms.sourcegitcommit: 9dd5d8fe6888f0c7d2df1e40fdd8b4c80512f8f9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/11/2018
ms.locfileid: "25498120"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a>Activer ou désactiver l'accès invité de Microsoft Teams
======================================

En tant qu'administrateur d'Office 365, vous devez activer la fonctionnalité Invité pour que vous ou les utilisateurs de votre organisation (notamment les propriétaires d'équipe) puissiez ajouter des invités. 

Les paramètres d'invité sont définis dans Azure Active Directory. Il faut environ 2 à 24 heures pour que les modifications prennent effet dans votre organisation Office 365. Si un utilisateur voit le message « Contactez votre administrateur » lorsqu'il essaye d'ajouter un invité à son équipe, il est probable que la fonctionnalité d'invité ne soit pas activée ou que les paramètres ne sont pas encore actifs.


> [!IMPORTANT]
> Pour activer l’expérience complète de la fonctionnalité d’accès invité, il est important de comprendre la dépendance des autorisations principales entre Microsfot Teams, Azure Active Directory et Office 365. Pour plus d'informations, reportez-vous à la rubrique [Autoriser l’accès invité dans Microsoft Teams](Teams-dependencies.md).

## <a name="configure-guest-access-in-the-teams--skype-for-business-admin-center"></a>Configurer l’accès invité dans les équipes & Skype entreprise centre d’administration

1.  Connectez-vous au portail les équipes & Skype entreprise centre d’administration.

2.  Sélectionnez les **paramètres à l’échelle de la société** > **accès invité**.

3. La valeur du bouton bascule **Autoriser l’accès invité dans les équipes Microsoft** **sur**.

    ![Autoriser le commutateur d’accès invité activé ](media/set-up-guests-image1.png)

4.  Définir la bascule pour **appel**, la **réunion**et **messagerie** **sur** ou **désactiver**, en fonction de l’accès que vous souhaitez autoriser.

5.  Cliquez sur **Enregistrer**.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Utilisation de PowerShell pour activer ou désactiver les accès invité

1.  Télécharger le Skype pour le module Business Online PowerShell à partir dehttps://www.microsoft.com/en-us/download/details.aspx?id=39366
 
2.  Se connecter à une session PowerShell à la Skype pour le point de terminaison Business en ligne.

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  Vérifiez votre configuration et si `AllowGuestUser` est `$False`, utilisez l’applet de commande [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) pour le définir sur `$True`.

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
    AllowTBotProactiveMessaging      : False
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
Vous pouvez maintenant avoir des utilisateurs invités dans les équipes de votre organisation.

## <a name="more-information"></a>Informations complémentaires

Regardez la vidéo suivante pour plus d’informations sur l’accès invité.

|  |  |
|---------|---------|
| Ajout d'invités dans Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
