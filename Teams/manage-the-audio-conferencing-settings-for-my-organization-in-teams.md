---
title: Gérer les paramètres d'audioconférence de votre organisation dans Microsoft Teams.
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
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Cette section explique la procédure d’attribution d’une licence de conférence rendez-vous et d’un ID de conférence Microsoft Teams à un utilisateur, ainsi que les autres paramètres de conférence rendez-vous. '
ms.openlocfilehash: 593987c6de3f6245afcdd7221fa7130a511d9f77
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291010"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Gérer les paramètres d'audioconférence de votre organisation dans Microsoft Teams.

Il peut être plus simple pour vous d'afficher tous les paramètres de conférence rendez-vous à un seul endroit. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>Attribuer une licence d’audioconférence

> [!NOTE]
> Vous ne pouvez pas attribuer de licences par le biais de Teams. Vous devez utiliser le centre d’administration Microsoft 365. Reportez-vous à la rubrique [Attribuer des licences Skype Entreprise et Microsoft Teams](assign-teams-licenses.md) 
  
 **Pour attribuer une licence à un utilisateur**
  
1. Connectez-vous à Microsoft 365 à l’aide de votre compte professionnel ou scolaire.
    
2. Dans le volet de navigation de gauche du **Centre d’administration Microsoft 365**, accédez à **** > utilisateurs**actifs**, puis sélectionnez le ou les utilisateurs dans la liste des utilisateurs disponibles.
    
    > [!NOTE]
    > Si vous affectez des licences à 20 utilisateurs maximum simultanément, vous pouvez utiliser la liste déroulante **Sélectionner un affichage**, puis choisir l'une des options ou créer votre propre affichage. Cliquez ensuite sur **Modifier**, deux fois sur **Suivant**, puis sélectionnez la licence et cliquez sur **Envoyer**.  
  
3. Dans le volet Action sous **Licences de produits**, cliquez sur **Modifier**. 
    
4. Sur la page **licences de produits** , activez l' **audioconférence** , puis cliquez sur **Enregistrer**. Pour plus d’informations sur les licences, voir [licences de complément Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
> [!NOTE]
> Une fois que vous avez affecté la licence, Microsoft peut ne pas s'afficher initialement comme fournisseur de conférence rendez-vous dans la liste déroulante. Dans ce cas, déconnectez-vous du Centre d'administration Office 365 ou appuyez sur les touches Ctrl + F5 pour actualiser la fenêtre du navigateur. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Activer ou désactiver l'envoi de courriers électroniques aux utilisateurs d'audioconférence

![teams-logo-30x30. png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft teams**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont). 

3. Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Envoyer automatiquement un courrier électronique aux utilisateurs en cas de modification de leurs paramètres de numérotation**.

4. Cliquez sur **Enregistrer**.

    
**Utiliser Windows PowerShell**
  
Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="reset-the-meeting-conference-id"></a>Réinitialisation de l'ID de conférence

![teams-logo-30x30. png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft teams**

1. Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. Sous **audioconférence**, cliquez sur réinitialisation de l' **ID de conférence**.  

3. Dans la fenêtre de réinitialisation de l' **ID de conférence?** , cliquez sur **Réinitialiser**. Un ID de conférence sera créé automatiquement et un message électronique sera envoyé à l’utilisateur avec le nouvel ID de conférence, si l’envoi de courrier électronique à vos utilisateurs est activé. Il est activé par défaut.

Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Réinitialisation du code confidentiel d'un organisateur de conférence

Un ID de conférence unique est attribué à chaque réunion qu’un utilisateur planifie. Même si un ID de conférence est automatiquement créé et attribué à un utilisateur, il peut arriver que l’utilisateur ne l’utilise pas et que vous vouliez le définir sur un certain numéro ou que vos utilisateurs ne se souviens pas ou aient perdu leur ID de conférence. 

![teams-logo-30x30. png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft teams**

1. Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. Sous **audioconférence**, cliquez sur **Réinitialiser le code confidentiel**, puis cliquez sur **Réinitialiser**. 
  
Les utilisateurs recevront un message électronique contenant leur code confidentiel lorsqu’ils sont activés pour les conférences audio ou lorsque le code confidentiel est réinitialisé. En revanche, si vous avez désactivé l’envoi automatique de courriers électroniques, le message de réinitialisation du code confidentiel ne sera pas envoyé et vous devrez envoyer manuellement le code confidentiel à l’utilisateur. Le code confidentiel ne sera affiché qu'après avoir été réinitialisé. Après sa réinitialisation, le code confidentiel ne s’affichera plus sur les propriétés de l’utilisateur. au lieu de cela, * * * * * sera affiché. 
  
Voir [Réinitialiser le code confidentiel de l’audioconférence](reset-the-audio-conferencing-pin-in-teams.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Envoyer un courrier électronique à un utilisateur avec ses informations de conférence audio

![teams-logo-30x30. png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft teams**

1. Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. Sous **audioconférence**, cliquez sur **Envoyer les informations sur la Conférence par courrier électronique**. 

    > [!NOTE]
    > Dans ce cas, le code confidentiel de l’audioconférence n’est pas envoyé à l’utilisateur. 

Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="set-the-phone-numbers-included-on-invites"></a>Définir les numéros de téléphone inclus dans les invitations

![teams-logo-30x30. png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft teams**

1. Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. A côté de **Conférence Audio**, cliquez sur **Modifier**.
 
3. Dans le volet **audioconférence** , vous pouvez définir le **numéro payant** et, s’il est autorisé, le **numéro**gratuit.

4. Cliquez sur **Enregistrer**.
    
Reportez-vous [à la rubrique définition des numéros de téléphone inclus dans](set-the-phone-numbers-included-on-invites-in-teams.md)les invitations.
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>Sélectionnez Paramètres du pont de conférence audio

**Définir l’accès à la réunion lorsque les appelants rejoignent une réunion**

![teams-logo-30x30. png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft teams**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. Dans la partie supérieure de la page de **conférences ponts** , cliquez sur **paramètres du pont**. 

3. Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Meeting entry and exit notifications** (Notifications d’entrée et de sortie de réunion).

    Cette option est activée par défaut. Si vous désactivez cette option, les utilisateurs qui ont déjà rejoint la réunion par défaut ne sont pas avertis lorsqu’une personne entre ou quitte la réunion.

4. Sous **type d’annonce d’entrée/sortie**, **** sélectionnez tonalités ou **noms ou numéros de téléphone**. 

    Si vous choisissez des **noms ou des numéros de téléphone**, vous pouvez également choisir d’activer ou de désactiver **la demande aux appelants d’enregistrer leur nom avant de participer à la réunion**. 

5. Cliquez sur **Enregistrer**.

    
Voir [Modifier les paramètres d'un pont d'Audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. Dans la partie supérieure de la page de **conférences ponts** , cliquez sur **paramètres du pont**. 

3. Dans le volet **paramètres du pont** , entrez le nombre de chiffres souhaités pour le code confidentiel dans la liste longueur du **code confidentiel** , puis cliquez sur **Enregistrer**.

    Le code confidentiel doit comporter entre 4 et 12 chiffres. La valeur par défaut est 5.

    
Voir [Modifier les paramètres d'un pont d'Audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. Dans la partie supérieure de la page de **conférences ponts** , cliquez sur **paramètres du pont**. 

3. Dans le volet **paramètres du pont** , activez ou désactivez l' **envoi automatique de messages électroniques aux utilisateurs en cas de modification de leurs paramètres de conférence audio**.

4. Cliquez sur **Enregistrer**. 
 
    Vous pouvez également envoyer des messages électroniques à l’utilisateur avec les paramètres de l’audioconférence en accédant aux propriétés de l’audioconférence de l’utilisateur, puis en cliquant sur envoyer les informations sur la **Conférence par courrier électronique**.
    
    Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.

Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Afficher et définir les langues principales (par défaut) et secondaires (de remplacement) sur un pont de conférence audio

![teams-logo-30x30. png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft teams**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. Sélectionnez un numéro de téléphone dans la liste, puis cliquez sur **modifier**.

3. Choisissez les langues de votre choix dans **langue par défaut** et **autres langues (facultatif)**.

4. Cliquez sur **Enregistrer**.


Reportez-vous à la rubrique [Définir les langues du standard automatique pour les conférences Audio](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Afficher les numéros d’accès pour les conférences audio

![teams-logo-30x30. png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft teams**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. Sélectionnez un numéro de téléphone dans la liste, puis cliquez sur **modifier**. Depuis cette section, vous pouvez :
    
   - Affichez les numéros de téléphone définis par Office 365 pour être utilisés pour les conférences audio. 
    
   - Affichez l’emplacement, ainsi que la langue principale, qui sera utilisée par le standard automatique de conférence audio.

  
Voir [la liste des numéros de conférence audio](see-a-list-of-audio-conferencing-numbers-in-teams.md).
  

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
    
## <a name="related-topics"></a>Rubriques connexes

[Gestion des paramètres d'audioconférence d'un utilisateur](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


