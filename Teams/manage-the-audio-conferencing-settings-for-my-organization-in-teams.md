---
title: Gérer les paramètres d’audioconférence
ms.author: heidip
author: MicrosoftHeidi
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
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Consultez les étapes de Microsoft Teams pour attribuer une licence de conférence rendez-vous et un ID de conférence à un utilisateur et à de nombreux autres paramètres de conférence rendez-vous.
ms.openlocfilehash: 4bfb813b6e7b472ad7a9ab58e6403b92f60fd039
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271219"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Gérer les paramètres d'audioconférence de votre organisation dans Microsoft Teams.

Il peut être plus facile pour vous de voir tous les paramètres d’audioconférence pour Microsoft Teams au même endroit.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="assign-an-audio-conferencing-license"></a>Attribuer une licence d’audioconférence

> [!NOTE]
> Vous ne pouvez pas attribuer de licences à l’aide de Teams. Vous devez utiliser le Centre d'administration Microsoft 365. Voir [Attribuer des licences de module complémentaire Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="to-assign-a-license-for-a-user"></a>Pour affecter une licence à un utilisateur

1. Connectez-vous à Microsoft 365 avec votre compte professionnel ou scolaire.

2. Dans le volet de navigation gauche du **Centre d'administration Microsoft 365**, accédez à **Utilisateurs** > **actifs**, puis sélectionnez l’utilisateur ou les utilisateurs dans la liste des utilisateurs disponibles.

    > [!NOTE]
    > Si vous affectez des licences à 20 utilisateurs maximum en même temps, vous pouvez utiliser la liste déroulante **Sélectionnez une vue**, puis sélectionner l'une des options ou créer votre propre vue. Cliquez ensuite sur **Modifier**, deux fois sur **Suivant**, puis sélectionnez la licence et cliquez sur **Envoyer**.  
  
3. Dans le volet Action, sous **Licences de produit**, cliquez sur **Modifier**.

4. Dans la page **Licences de produit** , **activez l’audioconférence** , puis cliquez sur **Enregistrer**. Pour plus d’informations sur les licences, consultez [les licences des modules complémentaires Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

   > [!NOTE]
   > Après avoir attribué la licence, Microsoft peut ne pas apparaître initialement dans la liste en tant que fournisseur d’audioconférence. Dans ce cas, déconnectez-vous du Centre d’administration ou appuyez sur Ctrl+F5 pour actualiser la fenêtre du navigateur.
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Activer ou désactiver les e-mails envoyés aux utilisateurs de l’audioconférence

### <a name="enable-or-disable-using-the-microsoft-teams-admin-center"></a>Activer ou désactiver à l’aide du Centre d’administration Microsoft Teams

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).

2. En haut de la page **Ponts de conférence** , cliquez sur **Paramètres du pont**.

3. Dans le volet **Paramètres du pont** , activez ou désactivez **l’envoi automatique d’e-mails aux utilisateurs si leurs paramètres de connexion changent**.

4. Cliquez sur **Enregistrer**.

### <a name="enable-or-disable-using-windows-powershell"></a>Activer ou désactiver à l’aide de Windows PowerShell

Pour plus d’informations, consultez la [référence Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) .
  
## <a name="reset-the-meeting-conference-id"></a>Réinitialisation de l'ID de conférence

### <a name="reset-the-meeting-conference-id-using-the-microsoft-teams-admin-center"></a>Réinitialiser l’ID de conférence de réunion à l’aide du Centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. Sous **Audioconférence**, cliquez sur **Réinitialiser l’ID de conférence**.  

3. Dans la fenêtre **Réinitialiser l’ID de conférence?** , cliquez sur **Réinitialiser**. Un ID de conférence sera créé automatiquement et un message électronique sera envoyé à l’utilisateur avec le nouvel ID de conférence, si l’envoi de courrier électronique à vos utilisateurs est activé. Il est activé par défaut.

Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user-in-teams.md).

## <a name="reset-a-conference-organizers-pin"></a>Réinitialisation du code confidentiel d'un organisateur de conférence

Chaque réunion planifiée par un utilisateur se voit attribuer un ID de conférence unique. Bien qu’un ID de conférence soit automatiquement créé et affecté à un utilisateur, il peut arriver qu’un utilisateur ne souhaite pas utiliser celui-ci et que vous le définissiez sur un certain nombre, ou que vos utilisateurs ne se souviennent pas ou ont perdu leur ID de conférence.

### <a name="reset-a-conference-organizers-pin-using-the-microsoft-teams-admin-center"></a>Réinitialiser le code confidentiel d’un organisateur de conférence à l’aide du Centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. Sous **Audioconférence**, cliquez sur **Réinitialiser le code confidentiel**, puis sur **Réinitialiser**.
  
Les utilisateurs reçoivent un e-mail avec leur code confidentiel lorsqu’ils sont activés pour l’audioconférence ou lorsque le code confidentiel est réinitialisé. Toutefois, si vous avez désactivé l’envoi automatique d’e-mails, aucun e-mail de réinitialisation du code confidentiel n’est envoyé et vous devrez envoyer manuellement le code confidentiel à l’utilisateur. Le code confidentiel ne sera affiché qu'après avoir été réinitialisé. Une fois qu’il est affiché juste après la réinitialisation, le code confidentiel ne s’affiche plus sur les propriétés de l’utilisateur ; au lieu de cela, ***** s’affiche.
  
Voir [Réinitialiser le code confidentiel de l’audioconférence](reset-the-audio-conferencing-pin-in-teams.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Envoyer un e-mail avec des informations d’audioconférence à un utilisateur

### <a name="send-an-email-using-the-microsoft-teams-admin-center"></a>Envoyer un e-mail à l’aide du Centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. Sous **Audioconférence**, cliquez sur **Envoyer des informations de conférence par e-mail**.

    > [!NOTE]
    > Dans ce cas, le code confidentiel de l’audioconférence n’est pas envoyé à l’utilisateur.

Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="set-the-phone-numbers-included-on-invites"></a>Définir les numéros de téléphone inclus dans les invitations

### <a name="set-invite-phone-numbers-using-the-microsoft-teams-admin-center"></a>Définir des numéros de téléphone d’invitation à l’aide du Centre d’administration Microsoft Teams

Reportez-vous à [Définir les numéros de téléphone inclus dans les invitations dans Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

> [!NOTE]
> Vous pouvez également définir des numéros de téléphone en les ajoutant à *TeamsAudioconferencingpolicy et en affectant* la stratégie à vos utilisateurs. Les numéros de téléphone payants et gratuits ajoutés à la stratégie sont prioritaires sur les numéros de téléphone définis individuellement pour les utilisateurs via le volet des paramètres d’audioconférence. Si aucun numéro de téléphone n’est ajouté à *teamsaudioconferencingpolicy*, le numéro de téléphone défini individuellement pour les utilisateurs via le volet des paramètres d’audioconférence s’affiche dans les demandes de réunion Microsoft Teams. [Les paramètres de stratégie d’audioconférence pour les numéros payants et gratuits](audio-conferencing-toll-free-numbers-policy.md) contiennent plus d’informations.

## <a name="choose-audio-conferencing-bridge-settings"></a>Choisir les paramètres du pont d’audioconférence

### <a name="set-the-meeting-experience-when-callers-join-a-meeting-using-the-microsoft-teams-admin-center"></a>Définir l’expérience de réunion lorsque les appelants rejoignent une réunion à l’aide du Centre d’administration Microsoft Teams

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).

2. En haut de la page **Ponts de conférence** , cliquez sur **Paramètres du pont**.

3. Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Meeting entry and exit notifications** (Notifications d’entrée et de sortie de réunion).

    Cette option est activée par défaut. Si vous désactivez cette option, les utilisateurs qui ont déjà rejoint la réunion par défaut ne seront pas avertis lorsqu’une personne entre ou quitte la réunion.

4. Sous **Type d’annonce Entrée/sortie**, choisissez **Tons** ou **Noms ou numéros de téléphone**.

    Si vous choisissez **Noms ou numéros de téléphone**, vous pouvez également choisir d’activer ou de désactiver **demander aux appelants d’enregistrer leur nom avant de rejoindre la réunion**.
    > [!NOTE]
    > Par défaut, les participants externes ne peuvent pas voir les numéros de téléphone des participants connectés. Si vous voulez conserver la confidentialité de ces numéros de téléphone, sélectionnez **Tonalités** pour le **type d’annonce d’entrée/sortie** (cela permet d’éviter que les numéros soient lus par les équipes).
5. Cliquez sur **Enregistrer**.

Voir [Modifier les paramètres d'un pont d'Audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).
  
### <a name="set-the-pin-length-for-meetings"></a>Reportez-vous à la rubrique Modification des paramètres d'un pont de conférence rendez-vous Microsoft.

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).

2. En haut de la page **Ponts de conférence** , cliquez sur **Paramètres du pont**.

3. Dans le volet **Paramètres du pont** , entrez le nombre de chiffres souhaités pour le code confidentiel dans la liste de **longueurs de code confidentiel** , puis cliquez sur **Enregistrer**.

    Le code confidentiel doit comporter entre 4 et 12 chiffres. La valeur par défaut est 5.

Voir [Modifier les paramètres d'un pont d'Audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md).

### <a name="enable-or-disable-email-from-being-sent-to-audio-users"></a>Reportez-vous à la rubrique Modification des paramètres d'un pont de conférence rendez-vous Microsoft.

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).

2. En haut de la page **Ponts de conférence** , cliquez sur **Paramètres du pont**.

3. Dans le volet **Paramètres du pont** , activez ou désactivez **l’envoi automatique d’e-mails aux utilisateurs si leurs paramètres d’audioconférence changent**.

4. Cliquez sur **Enregistrer**.

    Vous pouvez également envoyer un e-mail à l’utilisateur avec les paramètres d’audioconférence, en accédant aux propriétés d’audioconférence de l’utilisateur et en cliquant sur **Envoyer des informations de conférence par e-mail**.

    Si vous procédez ainsi, le message envoyé ne contient pas le code confidentiel, mais uniquement l'ID de conférence et le numéro de téléphone de la conférence.

Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Afficher et définir les langues primaires (par défaut) et secondaires (alternatives) sur un pont d’audioconférence

### <a name="see-primary-and-secondary-languages-using-the-microsoft-teams-admin-center"></a>Voir les langues primaires et secondaires à l’aide du Centre d’administration Microsoft Teams

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).

2. Sélectionnez un numéro de téléphone dans la liste, puis cliquez sur **Modifier**.

3. Choisissez les langues souhaitées sous **Langue par défaut** et **Langues alternatives (facultatif).**

4. Cliquez sur **Enregistrer**.

Reportez-vous à la rubrique [Définir les langues du standard automatique pour les conférences Audio](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers-using-the-microsoft-teams-admin-center"></a>Voir les numéros d’accès à l’audioconférence à l’aide du Centre d’administration Microsoft Teams

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).

2. Sélectionnez un numéro de téléphone dans la liste, puis cliquez sur **Modifier**. Depuis cette section, vous pouvez :

   - Affichez les numéros de téléphone à utiliser pour l’audioconférence.

   - Affichez l’emplacement et la langue principale qui seront utilisés par le standard automatique de l’audioconférence.

Consultez [la liste des numéros d’audioconférence](see-a-list-of-audio-conferencing-numbers-in-teams.md).

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :

- [Pourquoi utiliser Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Rubriques connexes

[Gestion des paramètres d'audioconférence d'un utilisateur](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)
