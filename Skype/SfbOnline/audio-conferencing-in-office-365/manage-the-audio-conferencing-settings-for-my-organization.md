---
title: Gérer les paramètres de conférence Audio de mon organisation dans Skype pour les professionnels en ligne
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
description: 'Voir Skype pour obtenir la procédure Business Online pour affecter un ID de conférence et de licence de conférence rendez-vous à un utilisateur et de nombreux autres paramètres de conférence rendez-vous. '
ms.openlocfilehash: fe5de9aa17a242337776c04178fe36bab24ca8f9
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490809"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Gérer les paramètres de conférence Audio de mon organisation dans Skype pour les professionnels en ligne

> [!NOTE]
> Si vous souhaitez gérer ces paramètres dans les équipes, voir [Gérer les paramètres de conférence Audio de mon organisation dans les équipes Microsoft](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).

Il peut être plus facile à voir tous les paramètres de conférence audio pour Skype pour les entreprises à un seul endroit. 

  
## <a name="assign-an-audio-conferencing-license"></a>Affecter une licence de conférence rendez-vous

> [!NOTE]
> Vous ne pouvez attribuer des licences à l’aide de la **Skype entreprise centre d’administration**. Vous devez utiliser le centre d’administration Office 365. Consultez [Attribuer des licences Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
 Pour affecter une licence à un utilisateur
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Dans la navigation de gauche du **Centre d’administration Office 365**, accédez aux **utilisateurs** > **utilisateurs actifs**, puis sélectionnez les utilisateurs dans la liste des utilisateurs disponibles.
    
    > [!NOTE]
    > Si vous affectez des licences à 20 utilisateurs maximum simultanément, vous pouvez utiliser la liste déroulante **Sélectionner un affichage**, puis choisir l'une des options ou créer votre propre affichage. Cliquez ensuite sur **Modifier**, deux fois sur **Suivant**, puis sélectionnez la licence et cliquez sur **Envoyer**. Vous pouvez également affecter des licences à plusieurs utilisateurs à l'aide de Windows Powershell. Pour obtenir des instructions et des exemples de scripts PowerShell, voir [Attribuer de Skype pour les licences de l’entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
3. Dans le volet Action, sous **Licences de produit**, cliquez sur **Modifier**. 
    
4. Dans la page **Licences de produits** , activer la **Conférence Audio** , puis sur **Enregistrer**. Pour plus d'informations sur les licences, reportez-vous à la rubrique [Licences de module complémentaire Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
> [!NOTE]
> Une fois que vous avez affecté la licence, Microsoft peut ne pas s'afficher initialement comme fournisseur de conférence rendez-vous dans la liste déroulante. Dans ce cas, déconnectez-vous du Centre d'administration Office 365 ou appuyez sur les touches Ctrl + F5 pour actualiser la fenêtre du navigateur. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Activer ou désactiver les courriers électroniques envoyés à des utilisateurs de conférence audio

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**
  
1. Activation ou désactivation de l'envoi de messages électroniques aux utilisateurs d'appels entrants
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans la page **paramètres du pont Microsoft** , activez ou désactivez l' **Envoyer automatiquement des messages électroniques aux utilisateurs si modifient leurs paramètres de conférence audio**.
    
4. Cliquez sur **Enregistrer**.
    
    Cliquez sur **Enregistrer**.
    
    Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.
  
- Utilisation de Windows PowerShell 
    
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    Vous pouvez également utiliser Windows PowerShell et exécuter :
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Modifier les informations de contact de l’expéditeur dans les messages électroniques envoyés aux utilisateurs

Modification des coordonnées de l'expéditeur dans les messages électroniques envoyés aux utilisateurs
  
- Entrez l’adresse de messagerie dans le paramètre _SendEmailFromAddress_ .
    
- entrer le nom d'affichage associé à l'adresse électronique dans le paramètre  _SendEmailFromDisplayName_.
    
- Définissez le paramètre _SendEmailOverride_ sur _True_.
    
Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, notamment l'adresse électronique d'envoi du courrier électronique ou le nom d'affichage associé à l'adresse électronique en exécutant :
  
Si vous souhaitez modifier les informations de l'adresse électronique, vous devez vous assurer que les stratégies de courrier électronique entrant de votre entreprise autorisent les messages électroniques provenant de l'adresse électronique personnalisée.
  
Voir [les messages électroniques qui sont automatiquement envoyées aux utilisateurs lorsque modifient leurs paramètres de conférence Audio](emails-sent-to-users-when-their-settings-change.md).
  
## <a name="reset-the-meeting-conference-id"></a>Réinitialisation de l'ID de conférence

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio**, dans le volet Actions, sous **ID de conférence**, cliquez sur **Réinitialiser**.
    
4. Dans le **Réinitialiser l’ID de conférence ?** fenêtre, cliquez sur **Oui**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.
    
    > [!IMPORTANT]
    >  Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. Les utilisateurs peuvent utiliser le Skype pour l’outil de Migration de réunion Business pour mettre à jour leurs réunions existantes. Pour savoir comment télécharger, installer et exécuter la Skype pour l’outil de mise à jour de réunion Business, voir : [Outil de mise à jour de réunion pour Skype pour les entreprises et Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype pour Business Online, outil de Migration de réunion (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)et [Skype pour Business Online réunion Outil de migration (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Réinitialisation du code confidentiel d'un organisateur de conférence

Chaque réunion planifie un utilisateur sera se voit attribuer un ID de conférence unique. Bien qu’un ID de conférence est automatiquement créé et affecté à un utilisateur, il peut arriver lorsqu’un utilisateur ne souhaite pas utiliser cette et vous voulez lui attribuer un certain nombre, ou vos utilisateurs ne vous souvenez pas ou ont perdu leur ID de conférence. Vous pouvez utiliser la Skype entreprise centre d’administration et de Windows PowerShell pour afficher, modifier et de réinitialiser leur ID de conférence.


1. Activation ou désactivation de l'envoi de messages électroniques aux utilisateurs d'appels entrants
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur que vous souhaitez réinitialiser le code confidentiel pour.
    
4. Dans le volet Actions, sous **code confidentiel**, cliquez sur **Réinitialiser**.
    
Les utilisateurs recevront un message électronique avec leur code confidentiel lorsqu’ils sont activés pour les services d’audioconférence ou lorsque le code confidentiel est réinitialisé. Mais si vous avez désactivé automatiquement l’envoi d’e-mails, un message électronique de réinitialisation du code confidentiel ne seront pas envoyé et vous devez envoyer manuellement le code confidentiel à l’utilisateur. Le code confidentiel ne sera affiché qu'après avoir été réinitialisé. Une fois qu’il est affiché juste après la réinitialisation, le code confidentiel ne s’affichera plus sur les propriétés de l’utilisateur ; au lieu de cela, *** s’affichera. 
  
Consultez la rubrique [Réinitialiser le code confidentiel de conférence Audio](reset-the-audio-conferencing-pin.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Envoyer un message électronique avec des informations de conférence Audio à un utilisateur

1. Envoi d'un courrier électronique à un utilisateur avec ses informations de conférence rendez-vous
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur que vous souhaitez réinitialiser le code confidentiel pour.
    
4. Cliquez sur **Utilisateurs d'appels entrants**, sélectionnez l'utilisateur pour lequel vous souhaitez réinitialiser le code confidentiel.
    
    > [!NOTE]
    > Lorsque vous faites cela, la conférence audio code confidentiel n’est pas envoyé à l’utilisateur. 
  
Dans ce cas, le code confidentiel de conférence rendez-vous n'est pas envoyé à l'utilisateur.
  
## <a name="setting-the-phone-numbers-included-on-invites"></a>Configuration du téléphone numéros inclus sur invite
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
4. Dans le volet Actions, vous pouvez définir le **numéro de téléphone payant** et, si Oui, le **numéro d’appel gratuit**.

5. Cliquez sur **Enregistrer**.
    
Voir [l’invite inclus sur les numéros de téléphone](set-the-phone-numbers-included-on-invites.md).
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a>Choix des paramètres de pont de conférence audio

Configuration des paramètres du pont de conférence rendez-vous

   
1. Définir les modalités d'accès aux réunions
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **paramètres de pont de Microsoft**.
    
4. Sous **l’expérience de participation aux réunions**, sélectionnez les actions suivantes :
    
  - Sous **Expérience de participation à une réunion**, sélectionnez les actions suivantes :
    
    Cela peut être définie sur une base de réunion par réunion lorsqu’un utilisateur joint à une réunion en utilisant un Skype pour l’application de gestion et ils modifient le paramètre **annoncer lorsque les utilisateurs entrent ou quittent** dans le menu **Options** de la réunion de Skype de la réunion.
    
  - Ce paramètre peut être défini réunion par réunion lorsqu'un utilisateur participe à une réunion par le biais d'un client Skype Entreprise et qu'il modifie le paramètre **Annoncer l'arrivée ou le départ des personnes** dans le menu Options de la réunion Skype.
    
5. **Demander aux appelants d'enregistrer leur nom avant de participer à la réunion**: cette option est sélectionnée par défaut. Si vous la désélectionnez, les appelants ne seront pas invités à enregistrer leur nom avant de rejoindre à la réunion.
    
Une fois que vous avez effectué vos modifications, cliquez sur [Enregistrer](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.
  
1. Définition de la longueur du code confidentiel pour les réunions
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **paramètres de pont de Microsoft**.
    
4. Sous **sécurité**, entrez le nombre de chiffres pour le code confidentiel dans la liste **longueur du code confidentiel** , puis cliquez sur **Enregistrer**.
    
    Le code confidentiel doit comporter entre 4 et 12 chiffres. La valeur par défaut est 5.
    
Le code confidentiel doit comporter de 4 à 12 chiffres. La valeur par défaut est 5.
  
 Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.
  
1. Activation ou désactivation de l'envoi de messages électroniques aux utilisateurs d'appels entrants
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans la page **paramètres du pont Microsoft** , activez ou désactivez l' **Envoyer automatiquement des messages électroniques aux utilisateurs si modifient leurs paramètres de conférence audio**.
    
4. Cliquez sur **Enregistrer**.
    
    Cliquez sur **Enregistrer**.
    
    Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.
    
    Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md).
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Afficher et définir principal (par défaut) et secondaires (autres) langues sur un pont de conférence audio


1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio**, puis cliquez sur **Microsoft bridge**.
    
4. Dans le volet de navigation de gauche du **Centre d'administration Skype Entreprise**, sélectionnez **Conférences rendez-vous**, puis cliquez sur **Pont Microsoft**.
    
    Vous pouvez également définir les langues principales et secondaires qui sont prises en charge lorsque vous sélectionnez Microsoft en tant que le fournisseur de services d’audioconférence. L’ordre que vous sélectionnez dans les listes correspond à l’ordre dans lequel les langues seront présentées aux appelants.
    
Vous pouvez également définir la langue principale et les langues secondaires prises en charge lorsque vous sélectionnez Microsoft comme fournisseur de conférences rendez-vous. L'ordre que vous sélectionnez dans les listes déroulantes correspondra à l'ordre dans lequel les langues sont proposées aux appelants.
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Voir les numéros de services d’audioconférence rendez-vous

1. Affichage des numéros d'accès pour les conférences rendez-vous
    
2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.
    
3. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **Microsoft bridge**. Ici, vous pouvez :
    
  - Afficher les numéros de téléphone qui sont définis par Office 365 à utiliser pour une audioconférence. 
    
  - Vous pouvez afficher les numéros de téléphone définis par Office 365 pour être utilisés avec la fonction de conférence rendez-vous.
    
  - Vous pouvez également afficher l'emplacement, la langue principale et les langues secondaires utilisés par le standard automatique de la fonction de conférence rendez-vous.
    
Vous pouvez sélectionner le numéro de téléphone de la conférence rendez-vous par défaut qui sera transmis aux utilisateurs lorsqu'ils seront activés pour la conférence rendez-vous. Toutefois, en cas de changement du numéro de téléphone par défaut du pont de la conférence rendez-vous, le numéro de téléphone affecté aux utilisateurs existants ne sera pas modifié.
  
Consultez la rubrique [Afficher la liste des numéros de conférence Audio](see-a-list-of-audio-conferencing-numbers.md).
  
## <a name="see-a-list-of-users-that-are-enabled"></a>Affichage de la liste des utilisateurs activés

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio**> puis **utilisateurs**et.
    
Reportez-vous à la rubrique [Afficher la liste des utilisateurs activés pour les conférences Audio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

Il existe plusieurs paramètres que vous pouvez gérer au niveau de l’organisation à l’aide de Windows PowerShell. Cela facilite appliquer les paramètres à tous vos utilisateurs. 
    
Pour en savoir plus sur chaque applet de commande, reportez-vous à la rubrique [Applets de commande Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=627324).

Voici les paramètres au niveau de l’organisation : 
 
- **Configuration de notifications d’entrée/sortie** La valeur par défaut est _$true_.
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

- **Définition de rendez-vous réunions uniquement à partir d’un téléphone** La valeur par défaut _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Définition s’il faut envoyer un message électronique aux utilisateurs** La valeur par défaut est _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Définition s’il faut envoyer un message électronique à partir d’un autre compte** La valeur par défaut est _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Définition de l’adresse de messagerie qui est envoyé aux utilisateurs** La valeur par défaut est _$null_. 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Définition du nom complet pour le message électronique qui est envoyé aux utilisateurs** La valeur par défaut est _$null_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a>Pour en savoir plus sur Windows PowerShell   
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Office 365, tels que lorsque vous modifiez les paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
    
## <a name="related-topics"></a>Rubriques connexes

[Gérer les paramètres d'audioconférence d'un utilisateur](manage-the-audio-conferencing-settings-for-a-user.md)


