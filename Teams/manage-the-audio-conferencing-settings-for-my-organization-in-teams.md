---
title: Gérer les paramètres d'audioconférence de mon organisation dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Cette section explique la procédure d’attribution d’une licence de conférence rendez-vous et d’un ID de conférence Microsoft Teams à un utilisateur, ainsi que les autres paramètres de conférence rendez-vous. '
ms.openlocfilehash: 40a6dd3e545e913a134ae7bac80b5ec3085dc96a
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015332"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a>Gérer les paramètres d'audioconférence de mon organisation dans Microsoft Teams

Il peut être plus simple pour vous d'afficher tous les paramètres de conférence rendez-vous à un seul endroit. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>Attribuer une licence d’audioconférence

> [!NOTE]
> Vous ne pouvez pas affecter des licences à l’aide des équipes. Vous devez utiliser le centre d’administration Office 365. Voir [Assigner de Skype pour les professionnels et les équipes Microsoft de licences](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses). 
  
 **Pour attribuer une licence à un utilisateur**
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Dans le volet de navigation de gauche du **centre d’administration Office 365**, accédez à **Utilisateurs** > **Utilisateurs actifs**, puis sélectionnez le ou les utilisateurs dans la liste des utilisateurs disponibles.
    
    > [!NOTE]
    > Si vous affectez des licences à 20 utilisateurs maximum simultanément, vous pouvez utiliser la liste déroulante **Sélectionner un affichage**, puis choisir l'une des options ou créer votre propre affichage. Cliquez ensuite sur **Modifier**, deux fois sur **Suivant**, puis sélectionnez la licence et cliquez sur **Envoyer**.  
  
3. Dans le volet Action sous **Licences de produits**, cliquez sur **Modifier**. 
    
4. Sur la page **Affecter une licence**, cochez **Conférence RTC Skype Entreprise**, puis cliquez sur **Enregistrer**. Pour plus d'informations sur les licences, reportez-vous à la rubrique [Licences de module complémentaire Skype Entreprise](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
    
> [!NOTE]
> Une fois que vous avez affecté la licence, Microsoft peut ne pas s'afficher initialement comme fournisseur de conférence rendez-vous dans la liste déroulante. Dans ce cas, déconnectez-vous du Centre d'administration Office 365 ou appuyez sur les touches Ctrl + F5 pour actualiser la fenêtre du navigateur. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Activer ou désactiver l'envoi de courriers électroniques aux utilisateurs d'audioconférence

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Utiliser le Centre d’Administration de Microsoft Teams et de Skype Entreprise :**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont). 

3. Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Envoyer automatiquement un courrier électronique aux utilisateurs en cas de modification de leurs paramètres de numérotation**.

4. Cliquez sur **Enregistrer**.

    
**Utiliser Windows PowerShell**
  
Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Modifier les coordonnées de l'expéditeur dans les courriers électroniques envoyés aux utilisateurs

Vous pouvez modifier le message électronique qui est envoyé automatiquement à vos utilisateurs, y compris l’adresse de messagerie réelle et le nom complet d’informations de contact de l’expéditeur. Par défaut, l’expéditeur des e-mails est Office 365, mais vous pouvez modifier l’adresse de messagerie et affiche le nom de l’aide de Windows PowerShell. Voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.
  
## <a name="reset-the-meeting-conference-id"></a>Réinitialiser l’ID de conférence

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Sous **Audioconférence**, cliquez sur **Réinitialiser l’ID de conférence**.  

4. Dans le **Réinitialiser l’ID de conférence ?** fenêtre, cliquez sur **Réinitialiser**. Un ID de conférence sera créé automatiquement et un message électronique sera envoyé à l’utilisateur avec le nouvel ID de conférence, si l’envoi de courrier électronique à vos utilisateurs est activé. Il est activé par défaut.

Reportez-vous à la section [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Réinitialiser le code confidentiel d’un organisateur de conférence

Chaque réunion planifie un utilisateur sera se voit attribuer un ID de conférence unique. Bien qu’un ID de conférence est automatiquement créé et affecté à un utilisateur, il peut arriver lorsqu’un utilisateur ne souhaite pas utiliser cette et vous voulez lui attribuer un certain nombre, ou vos utilisateurs ne vous souvenez pas ou ont perdu leur ID de conférence. 

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Sous **Audioconférence**, cliquez sur **Réinitialiser le code confidentiel**, puis cliquez sur **Réinitialiser**. 
  
    
Les utilisateurs recevront un message électronique avec leur code confidentiel lorsqu’ils sont activés pour les services d’audioconférence ou lorsque le code confidentiel est réinitialisé. Mais si vous avez désactivé automatiquement l’envoi d’e-mails, un message électronique de réinitialisation du code confidentiel ne seront pas envoyé et vous devez envoyer manuellement le code confidentiel à l’utilisateur. Le code confidentiel ne sera affiché qu'après avoir été réinitialisé. Une fois qu’il est affiché juste après la réinitialisation, le code confidentiel ne s’affichera plus sur les propriétés de l’utilisateur ; au lieu de cela, *** s’affichera. 
  
Reportez-vous à la section [Réinitialiser le code confidentiel d'audioconférence](reset-the-audio-conferencing-pin-in-teams.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Envoyer à un utilisateur un courrier électronique qui contient les informations d’audioconférence

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Sous **Audioconférence**, cliquez sur **Envoyer les informations de la conférence dans un courrier électronique**. 

    > [!NOTE]
    > Dans ce cas, le code confidentiel d’audioconférence n'est pas envoyé à l'utilisateur. 

  
Reportez-vous à la section [Envoyer à un utilisateur un courrier électronique qui contient ses informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="setting-the-phone-numbers-included-on-invites"></a>Définir les numéros de téléphone inclus dans les invitations

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs** et sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En regard de l’option **Audioconférence**, cliquez sur **Modifier**.
 
3. Dans le volet **Audioconférence**, vous pouvez définir le **numéro payant** et, si cela est autorisé, le **numéro gratuit**.

4. Cliquez sur **Enregistrer**.
    
Reportez-vous à la section [Définir les numéros de téléphone inclus dans les invitations](set-the-phone-numbers-included-on-invites-in-teams.md)
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a>Choix des paramètres de pont d'audioconférence

**Définissez l’expérience de réunion lorsque les appelants rejoignent une réunion**


1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont). 

3. Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Meeting entry and exit notifications** (Notifications d’entrée et de sortie de réunion).

    Il est activé par défaut. Si vous désactivez cette option, les utilisateurs qui ont déjà joint la réunion par défaut ne sera pas avertis lorsque quelqu'un rejoint ou quitte la réunion.

4. Sous **Type d’annonces entrée-sortie**, sélectionnez **Tones** (Tonalités) ou **Names or phone numbers** (Noms ou numéros de téléphone). 

    Si vous sélectionnez l'option **Names or phone numbers** (Noms ou numéros de téléphone), vous pouvez également activer ou désactiver l’option **Demander aux appelants d'enregistrer leur nom avant de rejoindre la réunion**. 

5. Cliquez sur **Enregistrer**.

    
Reportez-vous à la section [Modifier les paramètres d’un pont d’audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Modifier la longueur du code confidentiel pour les réunions**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont). 

3. Dans le volet **Bridge settings** (Paramètres du pont), entrez le nombre de chiffres que vous voulez pour le code confidentiel dans la liste **Longueur du code confidentiel**, puis cliquez sur **Enregistrer**.

    Le code confidentiel doit comporter entre 4 et 12 chiffres. La valeur par défaut est 5.

    
Reportez-vous à la section [Modifier les paramètres d’un pont d’audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Activer ou désactiver l’envoi de courriers électroniques aux utilisateurs d’audioconférence**


1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont). 

3. Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Automatically send emails to users if their audio conferencing settings change** (Envoyer automatiquement un courrier électronique aux utilisateurs en cas de modification de leurs paramètres d’audioconférence).

4. Cliquez sur **Enregistrer**. 
 
    Vous pouvez aussi envoyer à l’utilisateur un courrier électronique avec les paramètres d’audioconférence, en accédant aux propriétés d’audioconférence de l’utilisateur puis en cliquant sur **Envoyer les informations de la conférence dans un courrier électronique**.
    
    Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.

Reportez-vous à la section [Envoyer à un utilisateur un courrier électronique qui contient ses informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Afficher et définir la langue principale (par défaut) et les langues secondaires sur un pont d’audioconférence

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. Sélectionnez un numéro de téléphone dans la liste et cliquez sur **Modifier**.

3. Sélectionnez les langues souhaitées sous **Langue par défaut** et **Alternate languages (optional)** (Autres langues (facultatif)).

4. Cliquez sur **Enregistrer**.


Vous pouvez également définir la langue principale et les langues secondaires prises en charge lorsque vous sélectionnez Microsoft comme fournisseur de conférences rendez-vous. L'ordre que vous sélectionnez dans les listes déroulantes correspondra à l'ordre dans lequel les langues sont proposées aux appelants.
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Voir les numéros de services d’audioconférence rendez-vous


1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. Sélectionnez un numéro de téléphone dans la liste, cliquez sur **Modifier**. Depuis cette section, vous pouvez :
    
  - Afficher les numéros de téléphone qui sont définis par Office 365 à utiliser pour une audioconférence. 
    
  - Afficher l’emplacement et la langue principale, qui sera utilisée par le standard automatique de conférence Audio.

  
Consultez la rubrique [Afficher la liste des numéros de conférence Audio](see-a-list-of-audio-conferencing-numbers-in-teams.md).
  

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
    
## <a name="related-topics"></a>Rubriques connexes

[Gérer les paramètres d'audioconférence d'un utilisateur](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


