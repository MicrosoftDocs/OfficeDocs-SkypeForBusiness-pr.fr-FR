---
title: Gérer les paramètres d’audioconférence
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
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Consultez les étapes de Microsoft Teams pour affecter une licence de conférence rendez-vous et un ID de conférence à un utilisateur et de nombreux autres paramètres de conférence rendez-vous. '
ms.openlocfilehash: 96a8995b995340642c6b58be9d5062eacd3cd29c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101090"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Gérer les paramètres d'audioconférence de votre organisation dans Microsoft Teams.

Il peut être plus facile de voir tous les paramètres d’audioconférence de Microsoft Teams au même endroit. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>Affecter une licence d’audioconférence

> [!NOTE]
> Vous ne pouvez pas attribuer de licences à l’aide de Teams. Vous devez utiliser le Centre d’administration Microsoft 365. Voir [Attribuer des licences de modules add-on Microsoft Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 
  
 **Pour attribuer une licence à un utilisateur**
  
1. Connectez-vous à Microsoft 365 à l’aide de votre compte scolaire ou scolaire.
    
2. Dans le panneau de navigation gauche du Centre d’administration **Microsoft 365,** sélectionnez Utilisateurs actifs, puis sélectionnez le ou les utilisateurs dans la liste des  >  utilisateurs disponibles.
    
    > [!NOTE]
    > Si vous affectez des licences à 20 utilisateurs maximum simultanément, vous pouvez utiliser la liste déroulante **Sélectionner un affichage**, puis choisir l'une des options ou créer votre propre affichage. Cliquez ensuite sur **Modifier**, deux fois sur **Suivant**, puis sélectionnez la licence et cliquez sur **Envoyer**.  
  
3. Dans le volet Action, sous **Licences de produit**, cliquez sur **Modifier**. 
    
4. Dans la page **Licences de produits,** activer **l’audioconférence,** puis cliquer sur **Enregistrer.** Pour plus d’informations sur les licences, voir [Licences de modules logiciels de la suite Microsoft Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
    
   > [!NOTE]
   > Une fois que vous avez attribué la licence, Microsoft peut ne pas apparaître initialement dans la liste en tant que fournisseur de services d’audioconférence. Dans ce cas, déconnectez-vous du Centre d’administration ou appuyez sur Ctrl+F5 pour actualiser la fenêtre du navigateur. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Activer ou désactiver les messages électroniques envoyés aux utilisateurs de l’audioconférence

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. En haut de la page Ponts **de** conférence, cliquez sur **Paramètres du pont.** 

3. Dans le **volet Paramètres du** pont, activez ou désactivez automatiquement l’envoi de courriers électroniques aux utilisateurs en cas de modification de **leurs paramètres de connexion.**

4. Cliquez sur **Enregistrer**.

    
**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**
  
Pour plus [d’informations,](/powershell/module/teams/?view=teams-ps) consultez la référence Microsoft Teams PowerShell.
  
## <a name="reset-the-meeting-conference-id"></a>Réinitialisation de l'ID de conférence

![Icône montrant le logo Teams à ](media/teams-logo-30x30.png) **l’aide du Centre d’administration Microsoft Teams**

1. Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. Sous **Audioconférence,** cliquez sur **Réinitialiser l’ID de conférence.**  

3. Dans la fenêtre **Réinitialiser l’ID de conférence** ? , cliquez sur **Réinitialiser.** Un ID de conférence sera créé automatiquement et un message électronique sera envoyé à l’utilisateur avec le nouvel ID de conférence, si l’envoi de courrier électronique à vos utilisateurs est activé. Il est activé par défaut.

Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Réinitialisation du code confidentiel d'un organisateur de conférence

Chaque réunion qu’un utilisateur planifiera se voit attribuer un ID de conférence unique. Bien qu’un ID de conférence soit automatiquement créé et attribué à un utilisateur, il arrive qu’un utilisateur ne souhaite pas l’utiliser et que vous le définissez sur un nombre donné, ou que vos utilisateurs ne se souvenent pas ou ont perdu leur ID de conférence. 

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. Sous **Audioconférence,** cliquez sur **Réinitialiser** le code confidentiel, puis sur **Réinitialiser.** 
  
Les utilisateurs reçoivent un courrier électronique avec leur code confidentiel lorsqu’ils sont activés pour l’audioconférence ou lorsque le code confidentiel est réinitialisé. Toutefois, si vous avez désactivé l’envoi automatique de courriers électroniques, le message de réinitialisation du code confidentiel ne sera pas envoyé et vous de aurez à envoyer manuellement le code confidentiel à l’utilisateur. Le code confidentiel ne sera affiché qu'après avoir été réinitialisé. Une fois qu’il s’affiche juste après la réinitialisation, le code confidentiel n’est plus affiché dans les propriétés de l’utilisateur. ***** s’affiche à la place. 
  
Consultez [réinitialiser le code confidentiel de l’audioconférence.](reset-the-audio-conferencing-pin-in-teams.md)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Envoyer un courrier électronique avec des informations d’audioconférence à un utilisateur

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. Sous **Audioconférence,** cliquez sur Envoyer les informations sur **la conférence par courrier électronique.** 

    > [!NOTE]
    > Ainsi, le code confidentiel de l’audioconférence n’est pas envoyé à l’utilisateur. 

Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="set-the-phone-numbers-included-on-invites"></a>Définir les numéros de téléphone inclus dans les invitations

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. A côté de **Conférence Audio**, cliquez sur **Modifier**.
 
3. Dans le **volet Audioconférence,** vous  pouvez définir le numéro gratuit et, si cette est autorisée, **le numéro gratuit.**

4. Cliquez sur **Enregistrer**.
    
Consultez [Définir les numéros de téléphone inclus dans les invitations.](set-the-phone-numbers-included-on-invites-in-teams.md)
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>Choisir les paramètres du pont de conférence audio

**Définir l’expérience de réunion lorsque les appelants participent à une réunion**

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. En haut de la page Ponts **de** conférence, cliquez sur **Paramètres du pont.** 

3. Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Meeting entry and exit notifications** (Notifications d’entrée et de sortie de réunion).

    Cette option est activée par défaut. Si vous désactivez cette option, les utilisateurs qui ont déjà rejoint la réunion par défaut ne seront pas informés de l’arrivée ou du départ d’une personne.

4. Sous Type **d’annonce d’entrée/sortie,** sélectionnez **Sonnerie** **ou Noms ou des numéros de téléphone.** 

    Si vous choisissez Noms ou **numéros de téléphone,** vous pouvez également choisir d’activer ou de désactiver l’enregistrement du nom des appelants avant **de rejoindre la réunion.** 
    > [!NOTE]
    > Par défaut, les participants externes ne peuvent pas voir les numéros de téléphone des participants appelés. Si vous voulez conserver la confidentialité de ces numéros de téléphone, sélectionnez **Tonalités** pour le **type d’annonce d’entrée/sortie** (cela permet d’éviter que les numéros soient lus par les équipes).


5. Cliquez sur **Enregistrer**.

    
Voir [Modifier les paramètres d'un pont d'Audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. En haut de la page Ponts **de** conférence, cliquez sur **Paramètres du pont.** 

3. Dans le **volet Paramètres du** pont, entrez le nombre de  chiffres que vous souhaitez pour le code confidentiel dans la liste de longueur du code confidentiel, puis cliquez sur **Enregistrer.**

    Le code confidentiel doit comporter entre 4 et 12 chiffres. La valeur par défaut est 5.

    
Voir [Modifier les paramètres d'un pont d'Audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Reportez-vous à la rubrique **Modification des paramètres d'un pont de conférence rendez-vous Microsoft**.**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. En haut de la page Ponts **de** conférence, cliquez sur **Paramètres du pont.** 

3. Dans le **volet Paramètres** du pont, activez ou désactivez automatiquement l’envoi de courriers électroniques aux utilisateurs en cas de modification de **leurs paramètres d’audioconférence.**

4. Cliquez sur **Enregistrer**. 
 
    Vous pouvez également envoyer un courrier électronique à l’utilisateur avec les paramètres d’audioconférence en cliquant sur Envoyer les informations sur la conférence par courrier **électronique.**
    
    Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.

Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Consulter et définir la langue principale (par défaut) et les langues secondaires (secondaires) d’un pont d’audioconférence

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. Sélectionnez un numéro de téléphone dans la liste, puis cliquez **sur Modifier.**

3. Sélectionnez les langues de votre choix sous **Langue par** défaut et **Autres langues (facultatif).**

4. Cliquez sur **Enregistrer**.


Reportez-vous à la rubrique [Définir les langues du standard automatique pour les conférences Audio](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Consulter les numéros d’accès pour les conférences audio

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft teams**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. Sélectionnez un numéro de téléphone dans la liste, puis cliquez **sur Modifier.** Depuis cette section, vous pouvez :
    
   - Affichez les numéros de téléphone à utiliser pour l’audioconférence. 
    
   - Affichez l’emplacement et la langue principale qui seront utilisés par le attendant automatique de l’audioconférence.

  
Consultez [la liste des numéros d’audioconférence.](see-a-list-of-audio-conferencing-numbers-in-teams.md)
  

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 avec un seul point d’administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Pourquoi utiliser Microsoft 365 ou PowerShell Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](/powershell/module/teams/?view=teams-ps).
  
    
## <a name="related-topics"></a>Rubriques connexes

[Gestion des paramètres d'audioconférence d'un utilisateur](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)