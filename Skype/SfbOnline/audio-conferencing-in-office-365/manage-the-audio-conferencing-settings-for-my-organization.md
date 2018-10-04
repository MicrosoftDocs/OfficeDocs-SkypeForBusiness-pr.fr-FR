---
title: Gérer les paramètres d'Audioconférence de mon organisation dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Voir Skype pour obtenir la procédure Business Online pour affecter un ID de conférence et de licence de conférence rendez-vous à un utilisateur et de nombreux autres paramètres de conférence rendez-vous. '
ms.openlocfilehash: ed5d2cb2115c47ba84dd91ebc45561aa93e4c023
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375330"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Gérer les paramètres d'Audioconférence de mon organisation dans Skype Entreprise Online

> [!NOTE]
> Si vous souhaitez gérer ces paramètres dans Teams, voir [Gérer les paramètres d'Audioconférence de mon organisation dans Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).

Il peut être plus facile à voir tous les paramètres de conférence audio pour Skype pour les entreprises à un seul endroit.


## <a name="assign-an-audio-conferencing-license"></a>Affecter une licence de conférence rendez-vous

> [!NOTE]
> You can't assign licenses using the **Skype for Business admin center**. You must use the Office 365 admin center. See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

 Pour affecter une licence à un utilisateur

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Dans la navigation de gauche du **Centre d’administration Office 365**, accédez aux **utilisateurs** > **utilisateurs actifs**, puis sélectionnez les utilisateurs dans la liste des utilisateurs disponibles.

    > [!NOTE]
    > If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

3. Dans le volet Action, sous **Licences de produit**, cliquez sur **Modifier**.

4. On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> Une fois que vous avez affecté la licence, Microsoft peut ne pas s'afficher initialement comme fournisseur de conférence rendez-vous dans la liste déroulante. Dans ce cas, déconnectez-vous du Centre d'administration Office 365 ou appuyez sur les touches Ctrl + F5 pour actualiser la fenêtre du navigateur.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Activer ou désactiver les courriers électroniques envoyés à des utilisateurs de conférence audio

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Allez dans le **Centre d'administration Office 365** > **Skype Entreprise** et dans le volet de navigation de gauche, cliquez sur **Audioconférence**.

3. Dans la page des **paramètres de pont Microsoft**, activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres d’audioconférence ont été modifiés**.

4. Cliquez sur **Enregistrer**.

    Vous pouvez également envoyer des messages électroniques à l’utilisateur avec les paramètres d'audioconférence en accédant aux propriétés d'audioconférence de l’utilisateur et en cliquant sur **Envoyer les informations de conférence par courrier électronique**. L'ID de conférence et le numéro de téléphone d'audioconférence par défaut seront inclus dans l’invitation à la réunion, mais pas le code confidentiel.

    Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Utilisation de Windows PowerShell**

- Vous pouvez aussi utiliser Windows PowerShell et exécuter :

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    Vous pouvez également utiliser Windows PowerShell et exécuter :[](https://go.microsoft.com/fwlink/?LinkId=627285)

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Modifier les informations de contact de l’expéditeur dans les messages électroniques envoyés aux utilisateurs

Modification des coordonnées de l'expéditeur dans les messages électroniques envoyés aux utilisateurs[](https://go.microsoft.com/fwlink/?LinkId=627285)

- Entrez l’adresse de messagerie dans le paramètre _SendEmailFromAddress_ .

- entrer le nom d'affichage associé à l'adresse électronique dans le paramètre  _SendEmailFromDisplayName_.

- Définissez le paramètre _SendEmailOverride_ à _True_.

Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :

```
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :

Si vous souhaitez modifier les informations de l'adresse électronique, vous devez vous assurer que les stratégies de courrier électronique entrant de votre entreprise autorisent les messages électroniques provenant de l'adresse électronique personnalisée.

Voir [les messages électroniques qui sont automatiquement envoyées aux utilisateurs lorsque modifient leurs paramètres de conférence Audio](emails-sent-to-users-when-their-settings-change.md).

## <a name="reset-the-meeting-conference-id"></a>Réinitialisation de l'ID de conférence

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Allez dans le **Centre d'administration Office 365** > **Skype Entreprise**.

3. Dans le **Centre d’administration Skype Entreprise**, dans le volet de navigation de gauche, allez à **Audioconférence**, et dans le volet Actions, sous d'**ID de conférence**, cliquez sur **Réinitialiser**.

4. In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.

    > [!IMPORTANT]
    >  After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).

Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user.md).

## <a name="reset-a-conference-organizers-pin"></a>Réinitialisation du code confidentiel d'un organisateur de conférence

Each meeting that a user schedules will get assigned a unique conference ID. Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.


1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.**** > ********

3. Cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur que vous souhaitez réinitialiser le code confidentiel pour.

4. Dans le volet Actions, sous **code confidentiel**, cliquez sur **Réinitialiser**.

Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, ***** will be shown.

Consultez la rubrique [Réinitialiser le code confidentiel de conférence Audio](reset-the-audio-conferencing-pin.md).

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Envoyer un message électronique avec des informations de conférence Audio à un utilisateur

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.**** > ********

3. Cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur que vous souhaitez réinitialiser le code confidentiel pour.

4. Cliquez sur **Utilisateurs d'appels entrants**, sélectionnez l'utilisateur pour lequel vous souhaitez réinitialiser le code confidentiel.

    > [!NOTE]
    > Lorsque vous faites cela, la conférence audio code confidentiel n’est pas envoyé à l’utilisateur.

Dans ce cas, le code confidentiel de conférence rendez-vous n'est pas envoyé à l'utilisateur.

## <a name="setting-the-phone-numbers-included-on-invites"></a>Configuration du téléphone numéros inclus sur invite

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.**** > ****

3. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.

4. Dans le volet Action, vous pouvez définir le **Numéro payant** et, si permis, le **Numéro gratuit**.

5. Cliquez sur **Enregistrer**.

Voir [l’invite inclus sur les numéros de téléphone](set-the-phone-numbers-included-on-invites.md).


## <a name="choosing-audio-conferencing-bridge-settings"></a>Choix des paramètres de pont d'audioconférence

Configuration des paramètres du pont de conférence rendez-vous


1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.**** > ****

3. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **paramètres de pont de Microsoft**.

4. Sous **l’expérience de participation aux réunions**, sélectionnez les actions suivantes :

   - Sous **Expérience de participation à une réunion**, sélectionnez les actions suivantes :

     Cela peut être définie sur une base de réunion par réunion lorsqu’un utilisateur joint à une réunion en utilisant un Skype pour l’application de gestion et ils modifient le paramètre **annoncer lorsque les utilisateurs entrent ou quittent** dans le menu **Options** de la réunion de Skype de la réunion.

   - **Demander aux appelants d'enregistrer leur nom avant de se joindre à la réunion**. C'est le choix par défaut. Si vous effacer cette case à cocher, les appelants ne se verront pas demander d'enregistrer leur nom avant de se joindre à une réunion.

5. Après avoir fait vos modifications, cliquez sur **Enregistrer**.
    
Voir [Modifier les paramètres d'un pont d'Audioconférence](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 **Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.**** > ****

3. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **paramètres de pont de Microsoft**.

4. Sous **sécurité**, entrez le nombre de chiffres pour le code confidentiel dans la liste **longueur du code confidentiel** , puis cliquez sur **Enregistrer**.

    The PIN must be between 4 and 12 digits. The default is 5.
    
Le code confidentiel doit comporter de 4 à 12 chiffres. La valeur par défaut est 5.
  
 **Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.**** > ********

3. Dans la page des **paramètres de pont Microsoft**, activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres d’audioconférence ont été modifiés**.

4. Cliquez sur **Enregistrer**.

    Cliquez sur **Enregistrer**.

    Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.

    Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Afficher et définir principal (par défaut) et secondaires (autres) langues sur un pont de conférence audio


1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.**** > ****

3. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio**, puis cliquez sur **Microsoft bridge**.

4. Dans le volet de navigation de gauche du **Centre d'administration Skype Entreprise**, sélectionnez **Conférences rendez-vous**, puis cliquez sur **Pont Microsoft**.

    You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.

Vous pouvez également définir la langue principale et les langues secondaires prises en charge lorsque vous sélectionnez Microsoft comme fournisseur de conférences rendez-vous. L'ordre que vous sélectionnez dans les listes déroulantes correspondra à l'ordre dans lequel les langues sont proposées aux appelants.

## <a name="see-audio-conferencing-dial-in-numbers"></a>Voir les numéros de services d’audioconférence rendez-vous

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:

   - Afficher les numéros de téléphone qui sont définis par Office 365 à utiliser pour une audioconférence.

   - Vous pouvez afficher les numéros de téléphone définis par Office 365 pour être utilisés avec la fonction de conférence rendez-vous.

   - Vous pouvez également afficher l'emplacement, la langue principale et les langues secondaires utilisés par le standard automatique de la fonction de conférence rendez-vous.

Vous pouvez sélectionner le numéro de téléphone de la conférence rendez-vous par défaut qui sera transmis aux utilisateurs lorsqu'ils seront activés pour la conférence rendez-vous. Toutefois, en cas de changement du numéro de téléphone par défaut du pont de la conférence rendez-vous, le numéro de téléphone affecté aux utilisateurs existants ne sera pas modifié.**** > ****

Consultez la rubrique [Afficher la liste des numéros de conférence Audio](see-a-list-of-audio-conferencing-numbers.md).

## <a name="see-a-list-of-users-that-are-enabled"></a>Affichage de la liste des utilisateurs activés

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.**** > ****

3. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio**> puis **utilisateurs**et.

Reportez-vous à la rubrique [Afficher la liste des utilisateurs activés pour les conférences Audio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.

Pour en savoir plus sur chaque applet de commande, reportez-vous à la rubrique [Applets de commande Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=627324).

Voici les paramètres au niveau de l’organisation :

- **Configuration des notifications d’entrée/de sortie** La valeur par défaut est _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **Définition de l’enregistrement des noms** La valeur par défaut est _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **Définition de la longueur du code confidentiel** La valeur par défaut est 5.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **Définition seulement des réunions téléphoniques à partir d’un téléphone** La valeur par défaut _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Définition de savoir s’il faut envoyer un message électronique aux utilisateurs** La valeur par défaut est _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Définition de savoir s’il faut envoyer un message électronique à partir d’un compte différent** La valeur par défaut est _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Définition de l’adresse de messagerie De qui est envoyée aux utilisateurs** La valeur par défaut est _$null_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Définition du nom d'affichage du message électronique qui est envoyé aux utilisateurs** La valeur par défaut est _$null_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a>Pour en savoir plus sur Windows PowerShell
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :

  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)

- Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:

  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)

    Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).

## <a name="related-topics"></a>Rubriques connexes

[Gérer les paramètres d'audioconférence d'un utilisateur](manage-the-audio-conferencing-settings-for-a-user.md)


