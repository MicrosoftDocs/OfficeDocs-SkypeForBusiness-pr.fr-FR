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
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Consultez Skype Entreprise la procédure en ligne pour affecter une licence de conférence rendez-vous et un ID de conférence à un utilisateur et de nombreux autres paramètres de conférence rendez-vous. '
ms.openlocfilehash: 68deefd4092d05081ffe8a7aac9a1dc92ea36940
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726463"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Gérer les paramètres d'Audioconférence de mon organisation dans Skype Entreprise Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Si vous souhaitez gérer ces paramètres dans Teams, voir [Gérer les paramètres d'Audioconférence de mon organisation dans Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).

Il peut être plus facile de voir tous les paramètres d’audioconférence Skype Entreprise un seul endroit.


## <a name="assign-an-audio-conferencing-license"></a>Affecter une licence d’audioconférence

> [!NOTE]
> Vous ne pouvez pas attribuer de licences à l’aide du **Skype Entreprise d’administration.** Vous devez utiliser l’Centre d’administration Microsoft 365. Consultez [Attribuer des licences Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

 **Pour attribuer une licence à un utilisateur**

1. Connectez-vous avec votre compte scolaire ou scolaire.

2. Dans le panneau de navigation gauche du Centre d’administration, sélectionnez Utilisateurs actifs, puis sélectionnez le ou les utilisateurs dans la liste  >  des utilisateurs disponibles.

    > [!NOTE]
    > Si vous affectez des licences à 20 utilisateurs maximum simultanément, vous pouvez utiliser la liste déroulante **Sélectionner un affichage**, puis choisir l'une des options ou créer votre propre affichage. Cliquez ensuite sur **Modifier**, deux fois sur **Suivant**, puis sélectionnez la licence et cliquez sur **Envoyer**. Vous pouvez également affecter des licences à plusieurs utilisateurs à l'aide de Windows Powershell. Pour obtenir des instructions et des exemples de scripts PowerShell, voir [Attribuer Skype Entreprise licences.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)

3. Dans le volet Action, sous **Licences de produit**, cliquez sur **Modifier**.

4. Sur la page **Licences de produits,** activer **l’audioconférence,** puis cliquer sur **Enregistrer.** Pour plus d'informations sur les licences, reportez-vous à la rubrique [Licences de module complémentaire Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> Une fois que vous avez attribué la licence, Microsoft peut ne pas apparaître initialement dans la liste en tant que fournisseur de services d’audioconférence. Dans ce cas, déconnectez-vous du Centre d’administration ou appuyez sur Ctrl+F5 pour actualiser la fenêtre du navigateur.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Activer ou désactiver les messages électroniques envoyés aux utilisateurs de l’audioconférence

![Icône représentant le logo Skype Entreprise’affichage.](../images/sfb-logo-30x30.png) **Utilisation du Skype Entreprise d’administration**

1. Connectez-vous avec votre compte scolaire ou scolaire.

2. Dans le panneau de navigation de gauche du > **Skype Entreprise,** cliquez sur **Audioconférence.**

3. Dans la page des **paramètres de pont Microsoft**, activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres d’audioconférence ont été modifiés**.

4. Cliquez sur **Enregistrer**.

    Vous pouvez également envoyer des messages électroniques à l’utilisateur avec les paramètres d'audioconférence en accédant aux propriétés d'audioconférence de l’utilisateur et en cliquant sur **Envoyer les informations de conférence par courrier électronique**. L'ID de conférence et le numéro de téléphone d'audioconférence par défaut seront inclus dans l’invitation à la réunion, mais pas le code confidentiel.

    Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**

- Utilisation de Windows PowerShell

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    Vous pouvez également utiliser Windows PowerShell et exécuter :[](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Modifier les informations de contact de l’expéditeur dans les messages électroniques envoyés aux utilisateurs

Vous pouvez apporter des modifications aux courriers électroniques envoyés automatiquement à vos utilisateurs, y compris l’adresse de messagerie réelle et le nom d’affichage des informations de contact de l’expéditeur. Par défaut, l’expéditeur des courriers électroniques est Microsoft 365 ou Office 365, mais vous pouvez modifier l’adresse de messagerie et le nom d’affichage à l’aide de Windows PowerShell et de la cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Pour apporter des modifications à l’adresse de messagerie qui envoie le courrier électronique aux utilisateurs, vous devez :

- Entrez l’adresse de courrier dans le _paramètre SendEmailFromAddress._

- entrer le nom d'affichage associé à l'adresse électronique dans le paramètre  _SendEmailFromDisplayName_.

- Définissez le paramètre _SendEmailOverride_ à _True_.

Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :

Vous pouvez utiliser l’cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) pour gérer d’autres paramètres de votre organisation, y compris le courrier électronique.

Consultez les messages électroniques envoyés automatiquement aux utilisateurs en cas de modification de [leurs paramètres d’audioconférence.](emails-sent-to-users-when-their-settings-change.md)

## <a name="reset-the-meeting-conference-id"></a>Réinitialisation de l'ID de conférence

1. Connectez-vous avec votre compte scolaire ou scolaire.

2. Dans le centre d’administration, > **Skype Entreprise.**

3. Dans le **Centre d’administration Skype Entreprise**, dans le volet de navigation de gauche, allez à **Audioconférence**, et dans le volet Actions, sous d'**ID de conférence**, cliquez sur **Réinitialiser**.

4. Dans la fenêtre **Réinitialiser l’ID de conférence** ? cliquez sur **Oui.** Un ID de conférence sera créé automatiquement et un message électronique sera envoyé à l’utilisateur avec le nouvel ID de conférence, si l’envoi de courrier électronique à vos utilisateurs est activé. Il est activé par défaut.

    > [!IMPORTANT]
    >  Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. Les utilisateurs peuvent utiliser l’outil Skype Entreprise migration de réunions pour mettre à jour leurs réunions existantes. Pour découvrir comment télécharger, installer et exécuter l’outil de mise à jour de réunion Skype Entreprise, voir : Outil de mise à jour des réunions pour Skype Entreprise et [Lync,](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)Skype Entreprise Online, Outil de migration de réunions [(64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)et Skype Entreprise Online, outil de migration de réunion [(32 bits).](https://www.microsoft.com/download/details.aspx?id=54079)

Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user.md).

## <a name="reset-a-conference-organizers-pin"></a>Réinitialisation du code confidentiel d'un organisateur de conférence

Chaque réunion qu’un utilisateur planifiera se voit attribuer un ID de conférence unique. Bien qu’un ID de conférence soit automatiquement créé et attribué à un utilisateur, il arrive qu’un utilisateur ne souhaite pas l’utiliser et que vous le définissez sur un nombre donné, ou que vos utilisateurs ne se souvenent pas ou ont perdu leur ID de conférence. Vous pouvez utiliser le centre d’administration Skype Entreprise et Windows PowerShell pour afficher, modifier et réinitialiser leurs ID de conférence.


1. Connectez-vous avec votre compte scolaire ou scolaire.

2. Dans le panneau de navigation de gauche du > **Skype Entreprise,** cliquez sur **Audioconférence.**

3. Cliquez **sur** Utilisateurs, puis sélectionnez l’utilisateur pour qui vous voulez réinitialiser le code confidentiel.

4. Dans le volet Action, sous Code **confidentiel,** cliquez sur **Réinitialiser.**

Les utilisateurs reçoivent un courrier électronique avec leur code confidentiel lorsqu’ils sont activés pour l’audioconférence ou lorsque le code confidentiel est réinitialisé. Toutefois, si vous avez désactivé l’envoi automatique de courriers électroniques, le message de réinitialisation du code confidentiel ne sera pas envoyé et vous de aurez à envoyer manuellement le code confidentiel à l’utilisateur. Le code confidentiel ne sera affiché qu'après avoir été réinitialisé. Une fois qu’il s’affiche juste après la réinitialisation, le code confidentiel n’est plus affiché dans les propriétés de l’utilisateur. ***** s’affiche à la place.

Consultez [réinitialiser le code confidentiel de l’audioconférence.](reset-the-audio-conferencing-pin.md)

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Envoyer un courrier électronique avec des informations d’audioconférence à un utilisateur

1. Connectez-vous avec votre compte scolaire ou scolaire.

2. Dans le panneau de navigation de gauche du > **Skype Entreprise,** cliquez sur **Audioconférence.**

3. Cliquez **sur** Utilisateurs, puis sélectionnez l’utilisateur pour qui vous voulez réinitialiser le code confidentiel.

4. Cliquez sur **Utilisateurs d'appels entrants**, sélectionnez l'utilisateur pour lequel vous souhaitez réinitialiser le code confidentiel.

    > [!NOTE]
    > Ainsi, le code confidentiel de l’audioconférence n’est pas envoyé à l’utilisateur.

Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="setting-the-phone-numbers-included-on-invites"></a>Définition des numéros de téléphone inclus dans les invitations

1. Connectez-vous avec votre compte scolaire ou scolaire.

2. Dans le centre d’administration, > **Skype Entreprise.**

3. Dans le groupe de navigation de gauche, allez à Utilisateurs de **l’audioconférence.**  >   Sélectionnez l’utilisateur que vous voulez activer pour l’audioconférence.

4. Dans le volet Action, vous pouvez définir le **Numéro payant** et, si permis, le **Numéro gratuit**.

5. Cliquez sur **Enregistrer**.

Consultez [Définir les numéros de téléphone inclus dans les invitations.](set-the-phone-numbers-included-on-invites.md)


## <a name="choosing-audio-conferencing-bridge-settings"></a>Choix des paramètres de pont d'audioconférence

**Définir l’expérience de réunion lorsque les appelants participent à une réunion**


1. Connectez-vous avec votre compte scolaire ou scolaire.

2. Dans le centre d’administration, > **Skype Entreprise.**

3. Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, allez aux paramètres du pont Microsoft d’audioconférence.   >  

4. Sous **Expérience de rejoindre une réunion,** sélectionnez les actions suivantes :

   - Sous **Expérience de participation à une réunion**, sélectionnez les actions suivantes :

     Ce paramètre peut être réglé réunion par réunion lorsqu’un utilisateur participe à une réunion  à l’aide d’une application Skype Entreprise et qu’il modifie le paramètre Annoncer l’entrée ou le départ des personnes dans le menu **Options** Réunion Skype de la réunion.

   - **Demander aux appelants d'enregistrer leur nom avant de se joindre à la réunion**. C'est le choix par défaut. Si vous effacer cette case à cocher, les appelants ne se verront pas demander d'enregistrer leur nom avant de se joindre à une réunion.

5. Après avoir fait vos modifications, cliquez sur **Enregistrer**.
    
Voir [Modifier les paramètres d'un pont d'Audioconférence](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 **Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**

1. Connectez-vous avec votre compte scolaire ou scolaire.

2. Dans le centre d’administration, > **Skype Entreprise.**

3. Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, allez aux paramètres du pont Microsoft d’audioconférence.   >  

4. Sous **Sécurité,** entrez le nombre de chiffres  que vous souhaitez pour le code confidentiel dans la liste de longueur du code confidentiel, puis cliquez sur **Enregistrer.**

    Le code confidentiel doit comporter entre 4 et 12 chiffres. La valeur par défaut est 5.
    
Voir [Modifier les paramètres d'un pont d'Audioconférence](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 **Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**

1. Connectez-vous avec votre compte scolaire ou scolaire.

2. Dans le panneau de navigation de gauche du > **Skype Entreprise,** cliquez sur **Audioconférence.**

3. Dans la page des **paramètres de pont Microsoft**, activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres d’audioconférence ont été modifiés**.

4. Cliquez sur **Enregistrer**.

    Cliquez sur **Enregistrer**.

    Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.

    Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Consulter et définir la langue principale (par défaut) et les langues secondaires (secondaires) d’un pont d’audioconférence


1. Connectez-vous avec votre compte scolaire ou scolaire.

2. Dans le centre d’administration, > **Skype Entreprise.**

3. Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, cliquez sur **Audioconférence,** puis sur **Pont Microsoft.**

4. Dans le volet de navigation de gauche du **Centre d'administration Skype Entreprise**, sélectionnez **Conférences rendez-vous**, puis cliquez sur **Pont Microsoft**.

    Vous pouvez également définir la langue principale et les langues secondaires qui sont pris en charge lorsque vous sélectionnez Microsoft comme fournisseur de services d’audioconférence. L’ordre que vous sélectionnez dans les listes sera l’ordre dans lequel les langues seront présentées aux appelants.

Reportez-vous à la rubrique [Définir les langues du standard automatique pour les conférences Audio](set-auto-attendant-languages-for-audio-conferencing.md).

## <a name="see-audio-conferencing-dial-in-numbers"></a>Consulter les numéros d’accès pour les conférences audio

1. Connectez-vous avec votre compte scolaire ou scolaire.

2. Dans le centre d’administration, > **Skype Entreprise.**
 
3. Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, allez au pont Microsoft de l’audioconférence.   >   Depuis cette section, vous pouvez :

   - Affichez les numéros de téléphone Microsoft 365 ou Office 365 à utiliser pour l’audioconférence.

   - Vous pouvez afficher les numéros de téléphone définis par Office 365 pour être utilisés avec la fonction de conférence rendez-vous.

   - Vous pouvez également afficher l'emplacement, la langue principale et les langues secondaires utilisés par le standard automatique de la fonction de conférence rendez-vous.

Vous pouvez sélectionner le numéro de téléphone de la conférence rendez-vous par défaut qui sera transmis aux utilisateurs lorsqu'ils seront activés pour la conférence rendez-vous. Toutefois, en cas de changement du numéro de téléphone par défaut du pont de la conférence rendez-vous, le numéro de téléphone affecté aux utilisateurs existants ne sera pas modifié. > 

Consultez [la liste des numéros d’audioconférence.](see-a-list-of-audio-conferencing-numbers.md)

## <a name="see-a-list-of-users-that-are-enabled"></a>Affichage de la liste des utilisateurs activés

1. Connectez-vous avec votre compte scolaire ou scolaire.

2. Dans le centre d’administration, > **Skype Entreprise.**

3. Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, allez à Conférence **audio** et> puis **Utilisateurs.**

Reportez-vous à la rubrique [Afficher la liste des utilisateurs activés pour les conférences Audio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

Il existe plusieurs paramètres que vous pouvez gérer au niveau de l’organisation à l’aide Windows PowerShell. Cela facilite l’application des paramètres à tous vos utilisateurs.

Pour en savoir plus sur chaque applet de commande, reportez-vous à la rubrique [Applets de commande Skype Entreprise Online](/previous-versions//mt228132(v=technet.10)).

Voici les paramètres au niveau de l’organisation :

- **Configuration des notifications d’entrée/de sortie** La valeur par défaut est _$true_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **Définition de l’enregistrement des noms** La valeur par défaut est _$true_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **Définition de la longueur du code confidentiel** La valeur par défaut est 5.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **Définition seulement des réunions téléphoniques à partir d’un téléphone** La valeur par défaut _$false_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Définition de savoir s’il faut envoyer un message électronique aux utilisateurs** La valeur par défaut est _$true_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Définition de savoir s’il faut envoyer un message électronique à partir d’un compte différent** La valeur par défaut est _$false_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Définition de l’adresse de messagerie De qui est envoyée aux utilisateurs** La valeur par défaut est _$null_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Définition du nom d'affichage du message électronique qui est envoyé aux utilisateurs** La valeur par défaut est _$null_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a>Vous voulez en savoir plus sur Windows PowerShell
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer vos tâches Microsoft 365 Office 365 d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Raisons pour lesquelles vous devez Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))

- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du centre d’administration uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :

  - [Présentation de Windows PowerShell et Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

    Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).

## <a name="related-topics"></a>Sujets associés

[Gestion des paramètres d'audioconférence d'un utilisateur](manage-the-audio-conferencing-settings-for-a-user.md)
