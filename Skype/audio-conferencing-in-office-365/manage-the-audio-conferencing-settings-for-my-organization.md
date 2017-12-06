---
title: "Gérer les paramètres de conférence Audio pour mon organisation"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
description: "See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. "
---

# Gérer les paramètres de conférence Audio pour mon organisation

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](bc9bd328-c5b2-44e5-af15-e02bf00e1c81.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/bc9bd328-c5b2-44e5-af15-e02bf00e1c81). 
  
Il peut être plus facile de voir tous les paramètres de conférence audio pour Skype entreprise et Teams Microsoft en un seul endroit.
  
## Attribuer une licence de conférence Audio

> [!NOTE]
> Vous ne pouvez pas attribuer des licences à l'aide de la **Centre d'administration Skype Entreprise**. Vous devez utiliser le centre d'administration Office 365. Voir [Attribuez Skype pour les entreprises et Microsoft Teams des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
 **Pour attribuer une licence pour un utilisateur**
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Dans la navigation à gauche du **Centre d'administration Office 365**, accédez à **utilisateurs** > **utilisateurs actifs**, puis sélectionnez l'ou les utilisateurs dans la liste des utilisateurs disponibles.
    
    > [!NOTE]
    > Si vous attribuez des licences aux jusqu'à 20 utilisateurs en même temps, vous pouvez utiliser la **Sélectionner un affichage de** liste déroulante Choisir une des options ou créer votre propre affichage. Puis cliquez sur **Modifier**, **suivant** à deux reprises puis sélectionnez la licence, puis cliquez sur **Envoyer**. Vous pouvez également attribuer des licences à plusieurs utilisateurs à l'aide de Windows Powershell. Pour obtenir des instructions et exemples de scripts PowerShell, voir [Attribuez Skype pour les entreprises et Microsoft Teams des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
3. Dans le volet Action, sous **Licences de produit**, cliquez sur **Modifier**. 
    
4. Dans la page **Licences de produits**, activer les **Services de conférence Audio**, puis sur **Enregistrer**. Pour plus d'informations sur les licences, voir [Skype pour les entreprises et Microsoft Teams module complémentaire licences](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
> [!NOTE]
> Après avoir affecté la licence, Microsoft peut-être ne pas apparaître initialement dans la liste comme un fournisseur de services d'audioconférence. Dans ce cas, vous déconnectez le centre d'administration Office 365 ou appuyez sur CTRL + F5 pour actualiser la fenêtre du navigateur. 
  
## Affectation d'un ID de conférence à un utilisateur

Un ID de conférence est automatiquement affecté à un utilisateur lorsqu'ils sont configurés pour les conférences audio à l'aide de Microsoft comme fournisseur de services d'audioconférence. L'ID de conférence affectée peut être statique ou dynamique et est envoyé dans l'invitation à la réunion lors de la planification de la réunion.
  
ID statique est utilisés lorsque les personnes de votre organisation ne voulez pas n'oubliez pas d'un nombre aléatoire ; Vous pouvez sélectionner un certain nombre ou choisir celui qui est facile à mémoriser. Lors de l'ID de conférence dynamique sont utilisés, chaque réunion qui une planification de l'utilisateur doivent obtenir affectées un ID de conférence unique. Si vous voulez affecter les dynamique plutôt que de conférence statique ID, [Utilisation d'identificateurs dynamiques audioconférence dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Contrairement à l'applet de commande Windows PowerShell, le Centre d'administration Skype Entreprise ne permet pas d'affecter un ID de conférence à un utilisateur.
  
Pour définir l'ID de conférence d'un utilisateur, exécutez :
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> Un ID de conférence doit contenir 7 chiffres, et vous ne pouvez pas le modifier dans le Skype centre d'administration entreprise ou à l'aide de Windows PowerShell. 
  
Voir [Set-csonlinedialinconferencinguser n'affiche](https://go.microsoft.com/fwlink/?LinkId=617688 ) pour en savoir plus sur l'applet de commande.
  
> [!IMPORTANT]
>  Après la création d'un nouvel ID de conférence, l'ID de conférence ancien ne peuvent pas utilisé par les appelants. Vous recommandons d'informer les utilisateurs à reprogrammer son existant invitations pour vous assurer que la nouvelle conférence QU'ID est ajouté aux invitations aux réunions. Les utilisateurs peuvent utiliser l'outil de Migration de réunion Skype Entreprise pour mettre à jour leurs réunions existantes. Pour savoir comment télécharger, installer et exécuter la Skype pour les entreprises Meeting Update Tool, voir :> [Skype Entreprise (Lync) Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)> [Outil de migration de réunions Skype Entreprise Online (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)> [Skype entreprise Online, outil de Migration de réunion (32 bits)](https://go.microsoft.com/fwlink/?LinkID=626046)
  
Voir [Afficher, modifier et réinitialiser l'ID de conférence affecté à un utilisateur](see-change-and-reset-a-conference-id-assigned-to-a-user.md).
  
## Remplacer le fournisseur de services d'audioconférence de Microsoft par un fournisseur tiers

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Centre d'administration Skype Entreprise**, dans le volet de navigation gauche, accédez à la **conférence Audio** > **utilisateurs**, puis sur et sélectionnez l'utilisateur que vous souhaitez remplacer le fournisseur de services d'audioconférence pour.
    
4. Dans le volet Action, cliquez sur **Modifier**.
    
5. Dans la page de **Propriétés**, sous **nom du fournisseur**, sélectionnez le fournisseur de services d'audioconférence pour l'utilisateur.
    
    > [!NOTE]
    > Vous ne pouvez sélectionner Microsoft comme fournisseur de services d'audioconférence ou **Aucun** si vous avez sélectionné plusieurs utilisateurs.
  
6. Cliquez sur **Enregistrer**.
    
Voir [Changer le fournisseur de services de conférence rendez-vous des utilisateurs](https://support.office.com/article/9b74f053-4d23-485f-9232-3d30370a8c6e).
  
## Activer ou désactiver les messages électroniques envoyés aux utilisateurs de services d'audioconférence

Vous pouvez utiliser la Skype centre d'administration Business ou Windows PowerShell pour activer ou désactiver les messages envoyés aux utilisateurs.
  
 **À l'aide de la Skype centre d'administration Business**
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au **Centre d'administration Office 365** > **Skype Entreprise** dans le volet de navigation gauche, cliquez sur **conférence Audio**.
    
3. Dans la page **paramètres du pont Microsoft**, activez ou désactivez **Envoyer automatiquement les messages électroniques pour les utilisateurs si leurs paramètres de services d'audioconférence sont modifiés**.
    
4. Cliquez sur **Enregistrer**.
    
    Vous pouvez également envoyer des messages électroniques à l'utilisateur avec les paramètres de services d'audioconférence en accédant à propriétés de services d'audioconférence de l'utilisateur en cliquant sur **Envoyer les informations de conférence par courrier électronique**. Le numéro de téléphone de conférence audio par défaut et les ID de conférence est inclus dans l'invitation à la réunion mais pas le code confidentiel.
    
    Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-audio-conferencing-information.md).
    
 **Utilisation de Windows PowerShell**
  
- Vous pouvez également utiliser Windows PowerShell et exécuter :
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    Vous pouvez utiliser le [Jeu de CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) pour gérer d'autres paramètres pour votre organisation, notamment la messagerie électronique.
    
## Modifier les informations de contact de l'expéditeur dans les messages électroniques envoyés aux utilisateurs

Vous pouvez apporter des modifications à la messagerie électronique qui est envoyé automatiquement à vos utilisateurs, y compris l'adresse de messagerie réelle et le nom d'affichage des informations de contact de l'expéditeur. Par défaut, l'expéditeur des messages électroniques d'Office 365, mais vous pouvez modifier l'adresse de messagerie et nom complet à l'aide de Windows PowerShell et l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Pour apporter des modifications à l'adresse de messagerie qui envoie le message électronique aux utilisateurs, vous devez :
  
- entrer l'adresse électronique dans le paramètre À _SendEmailFromAddress_;
    
- entrer le nom d'affichage associé à l'adresse électronique dans le paramètre  _SendEmailFromDisplayName_.
    
- définir le paramètre  _SendEmailOverride_ sur _True_;
    
Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Si vous souhaitez modifier les informations de l'adresse électronique, vous devez vous assurer que les stratégies de courrier électronique entrant de votre entreprise autorisent les messages électroniques provenant de l'adresse électronique personnalisée.
  
Vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) pour gérer d'autres paramètres pour votre organisation, notamment la messagerie.
  
Voir les [Messages électroniques qui sont envoyés automatiquement aux utilisateurs lorsque leurs paramètres de conférence Audio modifier](emails-that-are-automatically-sent-to-users-when-their-audio-conferencing-settin.md).
  
## Réinitialisation de l'ID de conférence

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Centre d'administration Skype Entreprise**, dans le volet de navigation gauche, accédez à la **conférence Audio**, puis dans le volet Action sous **ID de conférence**, cliquez sur **Réinitialiser**.
    
4. Dans le **Réinitialiser l'ID de conférence ?** fenêtre, cliquez sur **Oui**. Un ID de conférence est automatiquement créé et un message électronique envoyé à l'utilisateur avec le nouvel ID de conférence si l'envoi de messages électroniques à vos utilisateurs est activée. Il est activé par défaut.
    
    > [!IMPORTANT]
    >  Après la création d'un nouvel ID de conférence, l'ID de conférence ancien ne peuvent pas utilisé par les appelants. Vous recommandons d'informer les utilisateurs à reprogrammer son existant invitations pour vous assurer que la nouvelle conférence QU'ID est ajouté aux invitations aux réunions. Les utilisateurs peuvent utiliser l'outil de Migration de réunion Skype Entreprise pour mettre à jour leurs réunions existantes. Pour savoir comment télécharger, installer et exécuter la Skype pour les entreprises Meeting Update Tool, voir :> [Skype Entreprise (Lync) Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)> [Outil de migration de réunions Skype Entreprise Online (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)> [Skype entreprise Online, outil de Migration de réunion (32 bits)](https://go.microsoft.com/fwlink/?LinkID=626046)
  
Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user.md).
  
## Réinitialisation du code confidentiel d'un organisateur de conférence

ID statique est utilisés lorsque les personnes de votre organisation ne voulez pas n'oubliez pas d'un nombre aléatoire ; Vous pouvez sélectionner un certain nombre ou utilisez celui qui est facile à mémoriser. Lors de l'ID de conférence dynamique sont utilisés, chaque réunion qui une planification de l'utilisateur doivent obtenir affectées un ID de conférence unique. Si vous voulez affecter les dynamique plutôt que de conférence statique ID, [Utilisation d'identificateurs dynamiques audioconférence dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Bien qu'un ID de conférence statique est automatiquement créé et affecté à un utilisateur, il peut arriver quand un utilisateur ne souhaite pas utiliser celle-ci et que vous souhaitez définir à un certain nombre, ou vos utilisateurs ne vous souvenez pas ou ont perdu leur ID de conférence. Vous pouvez utiliser la Skype centre d'administration Business et Windows PowerShell pour afficher, modifier et réinitialiser leur ID de conférence.
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au **Centre d'administration Office 365** > **Skype Entreprise** dans le volet de navigation gauche, cliquez sur **conférence Audio**.
    
3. Cliquez sur **utilisateurs** et sélectionnez l'utilisateur que vous voulez réinitialiser le code confidentiel pour.
    
4. Dans le volet Action, sous **code confidentiel**, cliquez sur **Réinitialiser**.
    
Les utilisateurs recevront un message électronique avec son code confidentiel quand elles sont activées pour les services d'audioconférence ou lorsque le code confidentiel est remis. Mais si vous avez désactivé automatiquement l'envoi d'e-mails, un message de réinitialisation du code confidentiel ne seront pas envoyé et vous devrez envoyer manuellement le code confidentiel à l'utilisateur. Le code confidentiel apparaîtra uniquement une fois une fois qu'il a été réinitialisé. Une fois qu'il est affiché juste après la réinitialisation, le code confidentiel ne s'affichera plus dans les propriétés utilisateur ; en revanche, *** seront affichés.
  
Reportez-vous à la rubrique [Réinitialiser le code confidentiel conférence Audio pour un utilisateur](reset-the-audio-conferencing-pin-for-a-user.md).
  
## Envoyer un message électronique avec les informations de conférence Audio à un utilisateur

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au **Centre d'administration Office 365** > **Skype Entreprise** dans le volet de navigation gauche, cliquez sur **conférence Audio**.
    
3. Cliquez sur **utilisateurs** et sélectionnez l'utilisateur que vous voulez réinitialiser le code confidentiel pour.
    
4. Dans le volet Action, cliquez sur **Envoyer les informations sur la conférence par courrier électronique**.
    
    > [!NOTE]
    > Lorsque vous effectuez cette opération, les services d'audioconférence code confidentiel n'est pas envoyé à l'utilisateur. 
  
Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-audio-conferencing-information.md).
  
## Définir le numéro de téléphone de conférence audio par défaut pour les organisateurs de réunion

 **Pour définir le numéro de téléphone de conférence audio par défaut pour les organisateurs de réunion lorsque vous activez un utilisateur pour les services d'audioconférence**
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans le volet de navigation gauche, accédez à la **conférence Audio** > **utilisateurs**. Sélectionnez l'utilisateur que vous souhaitez activer pour les conférences Audio.
    
4. Dans le volet Action, dans les propriétés de l'utilisateur, cliquez sur **Modifier**.
    
5. Dans la page de **Propriétés**, sous **nom du fournisseur**, utilisez la liste déroulante pour sélectionner le fournisseur de services d'audioconférence.
    
  - Si vous sélectionnez Microsoft comme fournisseur de services d'audioconférence, vous pouvez choisir le numéro de téléphone de conférence audio par défaut dans la liste.
    
  - Si vous sélectionnez un fournisseur tiers comme fournisseur de services d'audioconférence, vous devrez entrer manuellement le numéro payant et, si nécessaire, le numéro de téléphone gratuit. Ces numéros de téléphone sera le numéro de téléphone par défaut.
    
    Le numéro de téléphone de conférence audio par défaut d'un utilisateur est le nombre qui apparaît dans l'invitation à la réunion lorsqu'ils planifient une réunion.
    
6. Cliquez sur **Enregistrer**.
    
Voir [Définir les numéros de téléphone de conférence Audio pour les organisateurs comprises dans les invitations de réunion](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
 **Pour définir le numéro de téléphone de conférence audio par défaut pour les organisateurs de réunion après avoir activé un utilisateur pour les services d'audioconférence**
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Centre d'administration Skype Entreprise**, dans le volet de navigation gauche, accédez à la **conférence Audio** > **utilisateurs**, sélectionnez l'utilisateur souhaité, puis dans la page Action, cliquez sur **Modifier**.
    
4. Dans la page de **Propriétés**, sous **nom du fournisseur**, utilisez la liste déroulante pour sélectionner le fournisseur de services d'audioconférence.
    
  - Si l'utilisateur utilise Microsoft comme fournisseur de services d'audioconférence, vous pouvez choisir le numéro de téléphone de conférence audio par défaut dans la liste.
    
  - Si l'utilisateur utilise un fournisseur tiers comme fournisseur de services d'audioconférence, vous devrez entrer manuellement le numéro payant et, si nécessaire, le numéro de téléphone gratuit.
    
    Le numéro de téléphone de conférence audio par défaut d'un utilisateur est le nombre qui apparaît dans l'invitation à la réunion lorsqu'ils planifient une réunion.
    
5. Cliquez sur **Enregistrer**.
    
Voir [Définir les numéros de téléphone de conférence Audio pour les organisateurs comprises dans les invitations de réunion](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
## Définir des paramètres de pont de conférence audio

 **Définir l'expérience de réunion lorsque les appelants participer à une réunion**
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Centre d'administration Skype Entreprise**, dans le volet de navigation gauche, accédez à la **conférence Audio** > **paramètres du pont Microsoft**.
    
4. Sous **expérience de participer à une réunion**, sélectionnez les actions suivantes :
    
  - **Activer l'accès à la réunion et quitter notifications pour être activée** Cette option est sélectionnée par défaut. Si vous désactivez cette case à cocher, les utilisateurs qui ont déjà rejoint la réunion par défaut ne serez pas avertis lorsque quelqu'un entre ou quitte la réunion.
    
    Cela peut être définie sur une base de réunion par réunion lorsqu'un utilisateur joint à une réunion en utilisant un Skype entreprise ou Microsoft Teams application et ils modifient le paramètre de **case à cocher annoncer personnes intègrent ou quittent** dans le menu réunion Skype ou Microsoft Teams **Options** de la la réunion.
    
  - **Demander aux appelants d'enregistrer leur nom avant de rejoindre la réunion** Cette option est sélectionnée par défaut. Si vous désactivez cette case à cocher, les appelants ne vous êtes invités à enregistrer leur nom avant de participer à une réunion.
    
5. Une fois que vous avez effectué vos modifications, cliquez sur **Enregistrer**.
    
Voir [Modifier les paramètres d'un pont de conférence Audio](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Définir la longueur du code confidentiel pour les réunions**
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Centre d'administration Skype Entreprise**, dans le volet de navigation gauche, accédez à la **conférence Audio** > **paramètres du pont Microsoft**.
    
4. Sous **sécurité**, entrez le nombre de chiffres que vous voulez pour le code confidentiel dans la liste **longueur du code confidentiel**, puis cliquez sur **Enregistrer**.
    
    Le code confidentiel doit être comprise entre 4 à 12 chiffres. La valeur par défaut est 5.
    
Voir [Modifier les paramètres d'un pont de conférence Audio](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Activer ou désactiver la messagerie à partir d'envoyé aux utilisateurs audio**
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au **Centre d'administration Office 365** > **Skype Entreprise** dans le volet de navigation gauche, cliquez sur **conférence Audio**.
    
3. Dans la page **paramètres du pont Microsoft**, activez ou désactivez **Envoyer automatiquement les messages électroniques pour les utilisateurs si leurs paramètres de services d'audioconférence sont modifiés**.
    
4. Cliquez sur **Enregistrer**.
    
    Vous pouvez également envoyer courrier électronique à l'utilisateur avec les paramètres de conférence audio, en accédant à propriétés de services d'audioconférence de l'utilisateur en cliquant sur **Envoyer les informations de conférence par courrier électronique**.
    
    Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.
    
    Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-audio-conferencing-information.md).
    
## Voir et définir les langues principales et secondaires sur un pont de conférence audio

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Centre d'administration Skype Entreprise**, dans le volet de navigation gauche, accédez à la **conférence Audio**, puis cliquez sur **pont Microsoft**.
    
4. Sélectionnez un numéro de téléphone dans la liste et cliquez sur **définir les langues** dans le volet Action, puis dans la page **définir les langues**, cliquez sur utiliser la liste **langue principale** pour afficher la liste complète des langues prises en charge.
    
    Vous pouvez également définir les langues principales et secondaires sont pris en charge lorsque vous sélectionnez Microsoft comme fournisseur de services d'audioconférence. La commande que vous sélectionnez dans les listes correspond à l'ordre dans lequel les langues seront affichera aux appelants.
    
Consultez [Définir les langues du standard automatique pour les conférences Audio](set-auto-attendant-languages-for-audio-conferencing.md).
  
## Afficher les numéros de connexion services d'audioconférence

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Centre d'administration Skype Entreprise**, dans le volet de navigation gauche, accédez à la **conférence Audio** > **pont Microsoft**. Ici, vous pouvez :
    
  - Afficher les numéros de téléphone définis par Office 365 pour être utilisés pour les conférences Audio.
    
  - Afficher l'emplacement et les langues principales et secondaires, qui seront utilisés par le standard automatique de conférence Audio.
    
  - Sélectionnez le numéro de téléphone par défaut qui sera attribué aux utilisateurs lorsqu'ils sont activés pour les conférences Audio. Toutefois, si le numéro de téléphone par défaut de la passerelle de services d'audioconférence modifie, le numéro de téléphone par défaut pour les utilisateurs existants ne modifie.
    
Vous pouvez accéder à la **conférence Audio** > **utilisateurs** et sélectionnez le nombre de propriétés de l'utilisateur à modifier la valeur par défaut pour un utilisateur en choisissant un nouveau numéro dans la liste de nombres disponibles dans votre organisation.
  
Consultez [Afficher la liste des numéros de conférence Audio](see-a-list-of-audio-conferencing-numbers.md).
  
## Affichage de la liste des utilisateurs activés

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Centre d'administration Skype Entreprise**, dans le volet de navigation gauche, accédez à la **conférence Audio** >, puis sur **les utilisateurs**.
    
Consultez [Afficher la liste des utilisateurs activés pour les conférences Audio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).
  
## Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Il existe plusieurs paramètres que vous pouvez gérer au niveau de l'organisation à l'aide de Windows PowerShell. Cela facilite appliquer les paramètres pour l'ensemble de vos utilisateurs. Voici les paramètres de niveau de l'organisation :
    
    Pour obtenir plus d'aide sur chaque applet de commande, voir [Skype pour les applets de commande entreprise Online](https://go.microsoft.com/fwlink/?LinkId=627324).
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

    La valeur par défaut est  _$true_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

    La valeur par défaut est  _$true_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

    La valeur par défaut est 5.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

    La valeur par défaut est  _$false_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    La valeur par défaut est  _$true_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

    La valeur par défaut est  _$false_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

    La valeur par défaut est  _$null_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

    La valeur par défaut est  _$null_.
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Pourquoi vous devez utiliser Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages dans vitesse, simplicité et la productivité sur qu'à l'aide du centre d'administration Office 365, tels que lorsque vous devez apporter des modifications de paramètres pour de nombreux utilisateurs en même temps. En savoir plus sur les avantages suivants dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  
## Voir aussi
<a name="MT_Footer"> </a>

#### 

[Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)

