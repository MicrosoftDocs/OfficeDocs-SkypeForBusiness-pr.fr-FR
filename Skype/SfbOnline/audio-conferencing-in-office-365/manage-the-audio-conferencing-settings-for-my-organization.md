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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Voir les étapes de Skype Entreprise Online pour affecter une licence de conférence téléphonique et un ID de conférence à un utilisateur et de nombreux autres paramètres de conférence téléphonique. '
ms.openlocfilehash: 7f4387e7d818730de3b2b0336453a3f6ec9b39e7
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780490"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Gérer les paramètres d'Audioconférence de mon organisation dans Skype Entreprise Online

> [!NOTE]
> Si vous souhaitez gérer ces paramètres dans Teams, voir [Gérer les paramètres d'Audioconférence de mon organisation dans Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).

Il pourra être plus facile pour vous de voir tous les paramètres d’audioconférence de Skype Entreprise à un seul endroit.


## <a name="assign-an-audio-conferencing-license"></a>Affecter une licence de conférence rendez-vous

> [!NOTE]
> Vous ne pouvez pas affecter de licences avec le **centre d’administration Skype Entreprise**. Vous devez utiliser le centre d’administration Office 365. Consultez [Attribuer des licences Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

 **Pour affecter une licence à un utilisateur**

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Dans le volet de navigation de gauche du **Centre d'administration Office 365**, allez à **Utilisateurs** > **Utilisateurs actifs**, puis sélectionnez le ou les utilisateurs dans la liste des utilisateurs disponibles.

    > [!NOTE]
    > Si vous affectez des licences à 20 utilisateurs maximum simultanément, vous pouvez utiliser la liste déroulante **Sélectionner un affichage**, puis choisir l'une des options ou créer votre propre affichage. Cliquez ensuite sur **Modifier**, deux fois sur **Suivant**, puis sélectionnez la licence et cliquez sur **Envoyer**. Vous pouvez également affecter des licences à plusieurs utilisateurs à l'aide de Windows Powershell. Pour des instructions et des exemples de scripts Powershell, reportez-vous à la rubrique [Affecter des licences Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

3. Dans le volet Action, sous **Licences de produit**, cliquez sur **Modifier**.

4. Dans la page **Licences de produits**, activez l’**Audioconférence**, puis cliquez sur **Enregistrer**. Pour plus d'informations sur les licences, reportez-vous à la rubrique [Licences de module complémentaire Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> Une fois que vous avez affecté la licence, Microsoft peut ne pas s'afficher initialement comme fournisseur de conférence rendez-vous dans la liste déroulante. Dans ce cas, déconnectez-vous du Centre d'administration Office 365 ou appuyez sur les touches Ctrl + F5 pour actualiser la fenêtre du navigateur.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Activer ou désactiver les courriers électroniques envoyés aux utilisateurs d’audioconférence

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Utilisation du centre d’administration de Skype Entreprise**

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Allez dans le **Centre d'administration Office 365** > **Skype Entreprise** et dans le volet de navigation de gauche, cliquez sur **Audioconférence**.

3. Dans la page des **paramètres de pont Microsoft**, activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres d’audioconférence ont été modifiés**.

4. Cliquez sur **Enregistrer**.

    Vous pouvez également envoyer des messages électroniques à l’utilisateur avec les paramètres d'audioconférence en accédant aux propriétés d'audioconférence de l’utilisateur et en cliquant sur **Envoyer les informations de conférence par courrier électronique**. L'ID de conférence et le numéro de téléphone d'audioconférence par défaut seront inclus dans l’invitation à la réunion, mais pas le code confidentiel.

    Dans ce cas, le code confidentiel de conférence rendez-vous n'est pas envoyé à l'utilisateur.[ ](send-an-email-to-a-user-with-their-dial-in-information.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**

- Utilisation de Windows PowerShell

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    Vous pouvez également utiliser Windows PowerShell et exécuter :[](https://go.microsoft.com/fwlink/?LinkId=627285)

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Modifier les informations de contact de l’expéditeur dans les messages électroniques envoyés aux utilisateurs

Modification des coordonnées de l'expéditeur dans les messages électroniques envoyés aux utilisateurs[](https://go.microsoft.com/fwlink/?LinkId=627285)

- Entrez l’adresse de messagerie dans le paramètre _SendEmailFromAddress_.

- entrer le nom d'affichage associé à l'adresse électronique dans le paramètre  _SendEmailFromDisplayName_.

- Définissez le paramètre _SendEmailOverride_ à _True_.

Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :

```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :

|||UNTRANSLATED_CONTENT_START|||You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.|||UNTRANSLATED_CONTENT_END|||

Voir [Messages électroniques envoyés automatiquement aux utilisateurs lorsque leurs paramètres d’Audioconférence sont modifiés](emails-sent-to-users-when-their-settings-change.md).

## <a name="reset-the-meeting-conference-id"></a>Réinitialisation de l'ID de conférence

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.** ** > ** **.

3. Dans le **Centre d’administration Skype Entreprise**, dans le volet de navigation de gauche, allez à **Audioconférence**, et dans le volet Actions, sous d'**ID de conférence**, cliquez sur **Réinitialiser**.

4. Dans la fenêtre **Réinitialiser l’ID de conférence ?**, cliquez sur **Oui**. Un ID de conférence sera créé automatiquement et un message électronique sera envoyé à l’utilisateur avec le nouvel ID de conférence, si l’envoi de courrier électronique à vos utilisateurs est activé. Il est activé par défaut.

    > [!IMPORTANT]
    >  Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. Les utilisateurs peuvent utiliser l’Outil de migration de réunions de Skype Entreprise pour mettre à jour leurs réunions existantes. Pour savoir comment télécharger, installer et exécuter l’Outil de migration de réunions de Skype Entreprise, voir : [Outil de migration de réunions de Skype Entreprise et Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype Entreprise Online, Outil de migration de réunions (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)et [Skype Entreprise Online, Outil de migration de réunions (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).

Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user.md).

## <a name="reset-a-conference-organizers-pin"></a>Réinitialisation du code confidentiel d'un organisateur de conférence

Chaque réunion qu’un utilisateur planifie se verra affecter un ID de conférence unique. Bien qu’un ID de conférence soit automatiquement créé et affecté à un utilisateur, il peut y avoir des cas où un utilisateur ne souhaite pas l’utiliser, où vous voudrez le définir manuellement, ou des cas dans lesquels vos utilisateurs auront oublié ou égaré leur ID de conférence. Vous pouvez utiliser le centre d’administration Skype Entreprise et Windows PowerShell pour afficher, modifier et réinitialiser leurs ID de conférence.


1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.**** > ********

3. Cliquez sur **Utilisateurs**, puis sélectionnez l’utilisateur dont vous voulez réinitialiser le code confidentiel.

4. Dans le volet Actions, sous **Code confidentiel**, cliquez sur **Réinitialiser**.

Les utilisateurs recevront un courrier électronique avec leur code confidentiel lorsqu'ils seront autorisés pour l'audioconférence ou lorsque le code confidentiel sera réinitialisé. Mais si vous avez désactivé l’envoi automatique de courriers électroniques, aucun message de réinitialisation du code confidentiel ne sera envoyé, et vous devrez envoyer manuellement le code confidentiel à l’utilisateur. Le code confidentiel ne sera affiché qu'après avoir été réinitialisé. Une fois qu’il aura été affiché juste après avoir été réinitialisé, le code confidentiel ne sera plus affiché dans les propriétés de l’utilisateur ; à la place, ***** sera affiché.

Voir [Réinitialiser le code confidentiel de l'Audioconférence](reset-the-audio-conferencing-pin.md).

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Envoyer un message électronique d’informations d’Audioconférence à un utilisateur

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.**** > ********

3. Cliquez sur **Utilisateurs**, puis sélectionnez l’utilisateur dont vous voulez réinitialiser le code confidentiel.

4. Cliquez sur **Utilisateurs d'appels entrants**, sélectionnez l'utilisateur pour lequel vous souhaitez réinitialiser le code confidentiel.

    > [!NOTE]
    > Quand vous faites cela, le code confidentiel de l’audioconférence n'est pas envoyé à l’utilisateur.

Dans ce cas, le code confidentiel de conférence rendez-vous n'est pas envoyé à l'utilisateur.[ ](send-an-email-to-a-user-with-their-dial-in-information.md)

## <a name="setting-the-phone-numbers-included-on-invites"></a>Définir les numéros de téléphone inclus dans les invitations

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office ** 365 à l'aide de votre compte professionnel ou scolaire. ** > ** **

3. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.

4. Dans le volet Action, vous pouvez définir le **Numéro payant** et, si permis, le **Numéro gratuit**.

5. Cliquez sur **Enregistrer**.

Voir [Définir les numéros de téléphone inclus dans les invitations](set-the-phone-numbers-included-on-invites.md).


## <a name="choosing-audio-conferencing-bridge-settings"></a>Choix des paramètres de pont d'audioconférence

**Configuration des paramètres du pont de conférence rendez-vous**


1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.** ** > ****.

3. Dans le **Centre d’administration Skype Entreprise**, dans le volet de navigation de gauche, allez à **Audioconférence** > **Paramètres de pont Microsoft**.

4. Sous **Expérience de participation à une réunion**, sélectionnez les actions suivantes :

  - Sous **Expérience de participation à une réunion**, sélectionnez les actions suivantes :

    Celui-ci peut être défini réunion par réunion lorsqu’un utilisateur participe à une réunion en utilisant une application Skype Entreprise et qu’il modifie le paramètre **Annoncer l’arrivée ou le départ des personnes** dans le menu **Options** Skype Meeting de la réunion.

  - **Demander aux appelants d'enregistrer leur nom avant de se joindre à la réunion**. C'est le choix par défaut. Si vous effacer cette case à cocher, les appelants ne se verront pas demander d'enregistrer leur nom avant de se joindre à une réunion.

5. Après avoir fait vos modifications, cliquez sur **Enregistrer**.
    
Voir [Modifier les paramètres d'un pont d'Audioconférence](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 **Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.** ** > **  **.

3. Dans le **Centre d’administration Skype Entreprise**, dans le volet de navigation de gauche, allez à **Audioconférence** > **Paramètres de pont Microsoft**.

4. Sous **Sécurité**, entrez le nombre de chiffres que vous souhaitez pour le code confidentiel dans la liste **Longueur du code confidentiel**, puis cliquez sur **Enregistrer**.

    Le code confidentiel doit comporter entre 4 et 12 chiffres. La valeur par défaut est 5.
    
|||UNTRANSLATED_CONTENT_START|||See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).|||UNTRANSLATED_CONTENT_END|||
  
 **Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.**** > ********

3. Dans la page des **paramètres de pont Microsoft**, activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres d’audioconférence ont été modifiés**.

4. Cliquez sur **Enregistrer**.

    Cliquez sur **Enregistrer**.

    Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.

    Dans ce cas, le code confidentiel de conférence rendez-vous n'est pas envoyé à l'utilisateur.[ ](send-an-email-to-a-user-with-their-dial-in-information.md)

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Afficher et définir la langue principale (par défaut) et les langues secondaires (autre) pour un pont d’audioconférence


1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.** ** > ** **

3. Dans le volet de navigation de gauche du **Centre d’administration Skype Entreprise**, sélectionnez **Audioconférence**, puis cliquez sur **Pont Microsoft**.

4. Dans le volet de navigation de gauche du **Centre d'administration Skype Entreprise**, sélectionnez **Conférences rendez-vous**, puis cliquez sur **Pont Microsoft**.

    Vous pouvez également définir les langues principale et secondaire qui sont supportées lorsque vous sélectionnez Microsoft comme fournisseur d’audioconférence. L’ordre que vous sélectionnez dans les listes sera l’ordre dans lequel les langues seront présentées aux appelants.

Définir les langues du standard automatique pour l’Audioconférence dans Skype Entreprise Online[ ](set-auto-attendant-languages-for-audio-conferencing.md)

## <a name="see-audio-conferencing-dial-in-numbers"></a>Voir les numéros d’appel d’audioconférence

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.** **  >  ** **

3. Dans le **Centre d'administration Skype Entreprise**, dans le volet de navigation de gauche, allez à **Audioconférence** > **Pont Microsoft**. Depuis cette section, vous pouvez :

  - Affichez les numéros de téléphone qui sont définis par Office 365 pour l’utilisation en Audioconférence.

  - Vous pouvez afficher les numéros de téléphone définis par Office 365 pour être utilisés avec la fonction de conférence rendez-vous.

  - Vous pouvez également afficher l'emplacement, la langue principale et les langues secondaires utilisés par le standard automatique de la fonction de conférence rendez-vous.

Vous pouvez sélectionner le numéro de téléphone de la conférence rendez-vous par défaut qui sera transmis aux utilisateurs lorsqu'ils seront activés pour la conférence rendez-vous. Toutefois, en cas de changement du numéro de téléphone par défaut du pont de la conférence rendez-vous, le numéro de téléphone affecté aux utilisateurs existants ne sera pas modifié.**** > ****

Voir [Afficher la liste des numéros d’Audioconférence](see-a-list-of-audio-conferencing-numbers.md).

## <a name="see-a-list-of-users-that-are-enabled"></a>Affichage de la liste des utilisateurs activés

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.** ** > ** **

3. Dans la **centre d’administration Skype Entreprise**, dans la navigation de gauche, allez à **Audioconférence**>, puis **Utilisateurs**.

Reportez-vous à la rubrique [Afficher la liste des utilisateurs activés pour les conférences Audio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

Il existe plusieurs paramètres que vous pouvez gérer au niveau de l’organisation à l’aide de Windows PowerShell. Cela facilite l’application de paramètres à tous vos utilisateurs.

Pour en savoir plus sur chaque applet de commande, reportez-vous à la rubrique [Applets de commande Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=627324).

Voici les paramètres de niveau organisation :

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

 ## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :

  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365](https://go.microsoft.com/fwlink/?LinkId=525142)

- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à la seule utilisation du centre d’administration Office 365, par exemple lorsque vous faites des modifications de paramètres pour beaucoup d’utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :

  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)

    Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).

## <a name="related-topics"></a>Rubriques connexes

[Gérer les paramètres d'audioconférence d'un utilisateur](manage-the-audio-conferencing-settings-for-a-user.md)


