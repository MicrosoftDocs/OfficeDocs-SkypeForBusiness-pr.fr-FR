---
title: Gestion des paramètres de conférence rendez-vous de mon organisation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. '
ms.openlocfilehash: c1b6b45d3516aa17dc50f62f62696339a2625799
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a>Gestion des paramètres de conférence rendez-vous de mon organisation

[] Il peut être préférable d'afficher tous les paramètres de conférence rendez-vous à un seul endroit. 
  
## <a name="assign-an-audio-conferencing-license"></a>Affecter une licence de conférence rendez-vous

> [!NOTE]
> Vous ne pouvez attribuer des licences à l’aide de la **Skype pour le centre d’administration Business**. Vous devez utiliser le centre d’administration Office 365. Reportez-vous à la section [Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
 Pour affecter une licence à un utilisateur
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Dans la navigation gauche du **Centre d’administration Office 365**, consultez la rubrique **utilisateurs** > **utilisateurs actifs**, puis sélectionnez les utilisateurs à partir de la liste des utilisateurs disponibles.
    
    > [!NOTE]
    > Si vous affectez des licences à 20 utilisateurs maximum simultanément, vous pouvez utiliser la liste déroulante **Sélectionner un affichage**, puis choisir l'une des options ou créer votre propre affichage. Cliquez ensuite sur **Modifier**, deux fois sur **Suivant**, puis sélectionnez la licence et cliquez sur **Envoyer**. Vous pouvez également affecter des licences à plusieurs utilisateurs à l'aide de Windows Powershell. Pour obtenir des informations et des exemples de scripts Powershell, reportez-vous à la rubrique [Attribuer des licences Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
3. Dans le volet Action sous **Licence affectée**, cliquez sur **Modifier**. 
    
4. Sur la page **Affecter une licence**, cochez **Conférence RTC Skype Entreprise**, puis cliquez sur **Enregistrer**. Pour plus d'informations sur les licences, reportez-vous à la rubrique [Licences de module complémentaire Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
> [!NOTE]
> Une fois que vous avez affecté la licence, Microsoft peut ne pas s'afficher initialement comme fournisseur de conférence rendez-vous dans la liste déroulante. Dans ce cas, déconnectez-vous du Centre d'administration Office 365 ou appuyez sur les touches Ctrl + F5 pour actualiser la fenêtre du navigateur. 
  
## <a name="assign-a-conference-id-for-a-user"></a>Affectation d'un ID de conférence à un utilisateur

Affectation d'un ID de conférence à un utilisateur 
  
ID statiques sont utilisés lorsque les personnes de votre organisation ne souhaitant mémoriser un nombre aléatoire ; Vous pouvez sélectionner un certain nombre ou choisir celui qui est facile à mémoriser. Lorsque des ID de conférence dynamiques sont utilisés, chaque réunion qu'un utilisateur planifie obtient un ID de conférence unique. Si vous souhaitez affecter les dynamique au lieu de l’ID de conférence statique, reportez-vous [à l’aide de l’audioconférence dynamique d’ID dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Contrairement à l'applet de commande Windows PowerShell, le Centre d'administration Skype Entreprise ne permet pas d'affecter un ID de conférence à un utilisateur.
  
Contrairement à l'applet de commande Windows PowerShell, le Centre d'administration Skype Entreprise ne permet pas d'affecter un ID de conférence à un utilisateur.
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> Pour définir l'ID de conférence d'un utilisateur, exécutez : 
  
Pour en savoir plus sur l'applet de commande, reportez-vous à la rubrique [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
  
> [!IMPORTANT]
>  Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. Les utilisateurs peuvent utiliser le Skype pour l’outil de Migration de réunion Business mise à jour de leurs réunions existantes. Pour savoir comment télécharger, installer et exécuter le Skype pour l’outil de mise à jour de réunion Professionnel, consultez : [Outil de mise à jour de réunion pour Skype pour les entreprises et Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype pour Business Online, l’outil de Migration de réunion (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)et [Skype pour Business Online, réunion L’outil de migration (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
Reportez-vous à la rubrique [Afficher, modifier et réinitialiser l'ID de conférence affecté à un utilisateur](see-change-and-reset-a-conference-id-assigned-to-a-user.md).
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a>Modifier le fournisseur de conférence audio de Microsoft, à un fournisseur tiers

1. Remplacement du fournisseur de conférence rendez-vous Microsoft par un fournisseur tiers
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **les utilisateurs**, puis sur et sélectionnez l’utilisateur que vous souhaitez modifier le fournisseur de conférence audio de.
    
4. Dans le volet Action, cliquez sur **Modifier**. 
    
5. Sur la page de **Propriétés** , sous **le nom du fournisseur**, sélectionnez le fournisseur de conférence audio pour l’utilisateur.
    
    > [!NOTE]
    > Vous ne pouvez sélectionner Microsoft comme le fournisseur de conférence audio, ou **None** si vous avez sélectionné plusieurs utilisateurs.
  
6. Si vous avez sélectionné plusieurs utilisateurs, vous ne pouvez sélectionner que Microsoft comme fournisseur de conférence rendez-vous, ou l'option **Aucun**. 
    
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Activer ou désactiver les courriers électroniques envoyés à des utilisateurs de conférence audio

Activation ou désactivation de l'envoi de messages électroniques aux utilisateurs d'appels entrants
  
 Le Centre d'administration Skype Entreprise ou Windows PowerShell permet d'activer ou de désactiver l'envoi de courrier électronique aux utilisateurs.
  
1. Utilisation du Centre d'administration Skype Entreprise
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans la page **paramètres du pont Microsoft** , activez ou désactivez **Envoyer automatiquement des e-mails aux utilisateurs si leurs paramètres de conférence audio changent**.
    
4. Cliquez sur **Enregistrer**.
    
    Cliquez sur **Enregistrer**.
    
    Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md).
    
 Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.
  
- Utilisation de Windows PowerShell 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    Vous pouvez également utiliser Windows PowerShell et exécuter :
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Modifier les informations de contact de l’expéditeur dans les messages électroniques envoyés aux utilisateurs

Modification des coordonnées de l'expéditeur dans les messages électroniques envoyés aux utilisateurs
  
- Entrez l’adresse e-mail dans le paramètre _SendEmailFromAddress_ .
    
- entrer le nom d'affichage associé à l'adresse électronique dans le paramètre  _SendEmailFromDisplayName_.
    
- Définissez le paramètre _SendEmailOverride_ sur _True_.
    
Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :
  
Si vous souhaitez modifier les informations de l'adresse électronique, vous devez vous assurer que les stratégies de courrier électronique entrant de votre entreprise autorisent les messages électroniques provenant de l'adresse électronique personnalisée.
  
Voir les [messages qui sont automatiquement envoyés aux utilisateurs lors de la modifient de leurs paramètres d’audioconférence](emails-sent-to-users-when-their-settings-change.md).
  
## <a name="reset-the-meeting-conference-id"></a>Réinitialisation de l'ID de conférence

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, allez dans le volet Actions, sous **ID de conférence**et **les conférences Audio**, cliquez sur **Réinitialiser**.
    
4. Dans le **Réinitialiser l’ID de conférence ?** la fenêtre, cliquez sur **Oui**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.
    
    > [!IMPORTANT]
    >  Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. Les utilisateurs peuvent utiliser le Skype pour l’outil de Migration de réunion Business mise à jour de leurs réunions existantes. Pour savoir comment télécharger, installer et exécuter le Skype pour l’outil de mise à jour de réunion Professionnel, consultez : [outil de mise à jour de réunion pour Skype pour les entreprises et Lync] ((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype pour Business Online, outil de Migration de réunion (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)et [Skype pour Business Online, Réunion de l’outil de Migration (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Réinitialisation du code confidentiel d'un organisateur de conférence

ID statiques sont utilisés lorsque les personnes de votre organisation ne souhaitant mémoriser un nombre aléatoire ; Vous pouvez sélectionner un certain nombre ou utiliser un qui soit facile à mémoriser. Lorsque des ID de conférence dynamiques sont utilisés, chaque réunion qu'un utilisateur planifie obtient un ID de conférence unique. Si vous souhaitez affecter les dynamique au lieu de la conférence static ID, [ID de dynamique à l’aide de l’audioconférence de votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Bien qu’un ID de conférence statique sera automatiquement créé et affecté à un utilisateur, il peut arriver lorsqu’un utilisateur ne souhaite pas utiliser cette et vous souhaitez la définir pour un certain nombre, ou vos utilisateurs ne vous souvenez plus ou ont perdu leur ID de conférence. Vous pouvez utiliser le Skype pour Business admin center et de Windows PowerShell pour afficher, de modifier et de réinitialiser leur ID de conférence.
  
1. Activation ou désactivation de l'envoi de messages électroniques aux utilisateurs d'appels entrants
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur que vous souhaitez réinitialiser le code PIN pour.
    
4. Dans le volet Actions, sous le **code confidentiel**, cliquez sur **Réinitialiser**.
    
Les utilisateurs recevront un message électronique avec leur code PIN lorsqu’ils sont activés pour l’audioconférence ou lorsque le code confidentiel est réinitialisé. Mais si vous avez désactivé automatiquement l’envoi d’e-mails, un e-mail de réinitialisation du code PIN ne seront pas envoyé et vous devrez envoyer manuellement le code PIN de l’utilisateur. Le code confidentiel ne sera affiché qu'après avoir été réinitialisé. Une fois qu’il est affiché juste après la réinitialisation, le code confidentiel ne s’affichera plus sur les propriétés de l’utilisateur ; au lieu de cela, *** s’affichera. 
  
Les utilisateurs recevront un courrier électronique avec leur code confidentiel lorsqu'ils seront activés pour la conférence rendez-vous ou lorsque le code confidentiel sera réinitialisé. Si vous avez désactivé l'envoi automatique de courriers électroniques, aucun message de réinitialisation du code confidentiel ne sera envoyé à l'utilisateur, ce qui vous obligera à réinitialiser manuellement le code confidentiel. Le code confidentiel ne sera affiché qu'après avoir été réinitialisé. Lorsqu'il s'affiche après la réinitialisation, le code confidentiel n'apparaît dans les propriétés de l'utilisateur que sous la forme *****.
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Envoyer un courriel avec les informations d’audioconférence à un utilisateur

1. Envoi d'un courrier électronique à un utilisateur avec ses informations de conférence rendez-vous
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur que vous souhaitez réinitialiser le code PIN pour.
    
4. Cliquez sur **Utilisateurs d'appels entrants**, sélectionnez l'utilisateur pour lequel vous souhaitez réinitialiser le code confidentiel.
    
    > [!NOTE]
    > Lorsque vous effectuez cette opération, la conférence audio code confidentiel n’est pas envoyé à l’utilisateur. 
  
Dans ce cas, le code confidentiel de conférence rendez-vous n'est pas envoyé à l'utilisateur.
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a>Définir le numéro de téléphone de conférence audio par défaut pour les organisateurs de la réunion

 Définition du numéro de téléphone de conférence rendez-vous par défaut pour les organisateurs de la réunion
  
1. Pour définir le numéro de téléphone de conférence rendez-vous par défaut pour les organisateurs de la réunion lorsque vous activez un utilisateur pour la conférence rendez-vous
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
4. Dans le volet Actions, dans les propriétés de l’utilisateur, cliquez sur **Modifier**.
    
5. Sur la page de **Propriétés** , sous **le nom du fournisseur**, utilisez la liste déroulante pour sélectionner le fournisseur de conférence audio.
    
  - Si vous sélectionnez Microsoft comme le fournisseur de conférence audio, vous pouvez choisir le numéro de téléphone de conférence audio par défaut dans la liste.  
    
  - Si vous sélectionnez Microsoft en tant que fournisseur de conférence rendez-vous, vous pouvez choisir le numéro de téléphone par défaut de la conférence rendez-vous dans la liste.
    
    Si vous sélectionnez un fournisseur de services d'audioconférence tiers, vous devrez entrer manuellement le numéro de téléphone payant et, si nécessaire, le numéro de téléphone gratuit. Ces numéros de téléphone constitueront le numéro de téléphone par défaut.
    
6. Le numéro de téléphone de conférence rendez-vous par défaut d'un utilisateur correspond au numéro indiqué sur l'invitation à la réunion lors de la planification d'une réunion. 
    
Voir [invite les inclure sur des numéros de téléphone](set-the-phone-numbers-included-on-invites.md).
  
 Reportez-vous à la rubrique **Définir les numéros de téléphone de conférence Audio pour les organisateurs comprises dans les invitations de réunion**.
  
1. Pour définir le numéro de téléphone de conférence rendez-vous par défaut pour les organisateurs de la réunion après avoir activé un utilisateur pour la conférence rendez-vous
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **les utilisateurs**, sélectionnez l’utilisateur que vous souhaitez et dans la page Action, cliquez sur **Modifier**.
    
4. Sur la page de **Propriétés** , sous **le nom du fournisseur**, utilisez la liste déroulante pour sélectionner le fournisseur de conférence audio.
    
  - Si l’utilisateur utilise Microsoft comme le fournisseur de conférence audio, vous pouvez choisir le numéro de téléphone de conférence audio par défaut dans la liste.  
    
  - Si l'utilisateur utilise Microsoft en tant que fournisseur de conférence rendez-vous, vous pouvez choisir le numéro de téléphone par défaut de la conférence rendez-vous dans la liste.
    
    Si l'utilisateur utilise un fournisseur de services d'audioconférence tiers, vous devrez entrer manuellement le numéro de téléphone payant et, si nécessaire, le numéro de téléphone gratuit.
    
5. Le numéro de téléphone de conférence rendez-vous par défaut d'un utilisateur correspond au numéro indiqué sur l'invitation à la réunion lors de la planification d'une réunion. 
    
Voir [invite les inclure sur des numéros de téléphone](set-the-phone-numbers-included-on-invites.md).
  
## <a name="setting-audio-conferencing-bridge-settings"></a>Définition des paramètres de pont de conférence audio

 Configuration des paramètres du pont de conférence rendez-vous
  
1. Définir les modalités d'accès aux réunions
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **paramètres de pont de Microsoft**.
    
4. **Expérience de jointure de la réunion**, cliquez sur les actions suivantes :
    
  - Sous **Expérience de participation à une réunion**, sélectionnez les actions suivantes :
    
    Cela peut être définie sur une base de réunion par réunion lorsqu’un utilisateur joint à une réunion en utilisant un Skype pour application métier ou Teams de Microsoft et de les modifient le paramètre **annonce lorsque des personnes intègrent ou quittent** dans le menu réunion de Skype ou Teams de Microsoft, **Options** de la de la réunion.
    
  - Ce paramètre peut être défini réunion par réunion lorsqu'un utilisateur participe à une réunion par le biais d'un client Skype Entreprise et qu'il modifie le paramètre **Annoncer l'arrivée ou le départ des personnes** dans le menu Options de la réunion Skype.
    
5. **Demander aux appelants d'enregistrer leur nom avant de participer à la réunion**: cette option est sélectionnée par défaut. Si vous la désélectionnez, les appelants ne seront pas invités à enregistrer leur nom avant de rejoindre à la réunion.
    
Une fois que vous avez effectué vos modifications, cliquez sur [Enregistrer](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.
  
1. Définition de la longueur du code confidentiel pour les réunions
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **paramètres de pont de Microsoft**.
    
4. Sous **sécurité**, entrez le nombre de chiffres que vous souhaitez pour le code confidentiel dans la liste **longueur du code confidentiel** , puis cliquez sur **Enregistrer**.
    
    Le code confidentiel doit comporter entre 4 et 12 chiffres. La valeur par défaut est 5.
    
Le code confidentiel doit comporter de 4 à 12 chiffres. La valeur par défaut est 5.
  
 Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.
  
1. Activation ou désactivation de l'envoi de messages électroniques aux utilisateurs d'appels entrants
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans la page **paramètres du pont Microsoft** , activez ou désactivez **Envoyer automatiquement des e-mails aux utilisateurs si leurs paramètres de conférence audio changent**.
    
4. Cliquez sur **Enregistrer**.
    
    Cliquez sur **Enregistrer**.
    
    Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.
    
    Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.
    
## <a name="see-and-set-the-primary-and-secondary-languages-on-an-audio-conferencing-bridge"></a>Afficher et définir les langues principales et secondaires sur un pont de conférence audio

1. Affichage et sélection de la langue principale et des langues secondaires associées à un point de conférence rendez-vous
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **l’audioconférence**, puis cliquez sur **pont de Microsoft**.
    
4. Dans le volet de navigation de gauche du **Centre d'administration Skype Entreprise**, sélectionnez **Conférences rendez-vous**, puis cliquez sur **Pont Microsoft**.
    
    Vous pouvez également définir les langues principales et secondaires qui sont pris en charge lorsque vous sélectionnez Microsoft comme le fournisseur de conférence audio. La commande que vous sélectionnez dans les listes correspond à l’ordre dans lequel les langues seront présentées aux appelants.
    
Vous pouvez également définir la langue principale et les langues secondaires prises en charge lorsque vous sélectionnez Microsoft comme fournisseur de conférences rendez-vous. L'ordre que vous sélectionnez dans les listes déroulantes correspondra à l'ordre dans lequel les langues sont proposées aux appelants.
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Consultez les numéros d’audioconférence

1. Affichage des numéros d'accès pour les conférences rendez-vous
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **pont de Microsoft**. Ici, vous pouvez :
    
  - Permet d’afficher les numéros de téléphone sont définis par Office 365 à utiliser pour les conférences Audio. 
    
  - Vous pouvez afficher les numéros de téléphone définis par Office 365 pour être utilisés avec la fonction de conférence rendez-vous.
    
  - Vous pouvez également afficher l'emplacement, la langue principale et les langues secondaires utilisés par le standard automatique de la fonction de conférence rendez-vous.
    
Vous pouvez sélectionner le numéro de téléphone de la conférence rendez-vous par défaut qui sera transmis aux utilisateurs lorsqu'ils seront activés pour la conférence rendez-vous. Toutefois, en cas de changement du numéro de téléphone par défaut du pont de la conférence rendez-vous, le numéro de téléphone affecté aux utilisateurs existants ne sera pas modifié.
  
Reportez-vous à la section [Afficher la liste des numéros d’audioconférence](see-a-list-of-audio-conferencing-numbers.md).
  
## <a name="see-a-list-of-users-that-are-enabled"></a>Affichage de la liste des utilisateurs activés

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence**> et ensuite **aux utilisateurs**.
    
Reportez-vous à la rubrique [Afficher la liste des utilisateurs activés pour les conférences Audio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

Il existe plusieurs paramètres que vous pouvez gérer au niveau de l’organisation à l’aide de Windows PowerShell. Cela rend facile à appliquer les paramètres à tous vos utilisateurs. 
    
Pour en savoir plus sur chaque applet de commande, reportez-vous à la rubrique [Applets de commande Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=627324).

Voici les paramètres au niveau de l’organisation : 
> 
- **Configuration de notifications d’entrée et de sortie** La valeur par défaut est _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- **Définition d’enregistrement de nom** La valeur par défaut est _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **Définition de la longueur du code confidentiel** La valeur par défaut est 5.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **Configuration à distance réunions uniquement à partir d’un téléphone** La valeur par défaut _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Définir s’il faut envoyer un e-mail aux utilisateurs** La valeur par défaut est _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Définir s’il faut envoyer un e-mail à partir d’un autre compte** La valeur par défaut est _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Définition de l’adresse de courrier électronique qui est envoyé aux utilisateurs** La valeur par défaut est _$null_. 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Définition du nom d’affichage de l’e-mail qui sera envoyé aux utilisateurs** La valeur par défaut est _$null_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a>Pour en savoir plus sur Windows PowerShell   
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages de vitesse, de simplicité et de productivité sur uniquement en utilisant le centre d’administration d’Office 365, par exemple lorsque vous devez apporter des modifications de paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
    
## <a name="related-topics"></a>Rubriques connexes

[Gérer les paramètres d'audioconférence d'un utilisateur](manage-the-audio-conferencing-settings-for-a-user.md)


