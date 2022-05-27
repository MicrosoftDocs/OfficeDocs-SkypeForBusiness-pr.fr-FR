---
title: Modifier les numéros de téléphone sur Audioconférence pont
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Découvrez les étapes nécessaires pour affecter un nouveau numéro de téléphone de service à votre pont de conférence afin d’étendre la couverture de vos utilisateurs.
ms.openlocfilehash: 0433577334dca5f84854ba1cdc14b81e4ec37e63
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674776"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Modifier les numéros de téléphone de votre pont d’audioconférence

Lorsque vous achetez des licences **Audioconférence**, Microsoft héberge votre pont d’audioconférence pour votre organisation. Le pont d’audioconférence fournit des numéros de téléphone rendez-vous à partir de différents emplacements afin que les organisateurs de réunion et les participants puissent les utiliser pour participer à Skype Entreprise ou Microsoft Teams réunions à l’aide d’un téléphone.

En plus des numéros de téléphone déjà affectés à votre pont de conférence, vous pouvez obtenir des [numéros de service supplémentaires](./getting-service-phone-numbers.md) (numéros gratuits et gratuits utilisés pour l’audioconférence) à partir d’autres emplacements, puis les affecter au pont de conférence afin de pouvoir étendre la couverture de vos utilisateurs.

> [!NOTE]
> Pour pouvoir attribuer/annuler l’affectation d’un numéro de téléphone pour un pont de conférence, le numéro de téléphone doit être un numéro de « *service* ». Vous pouvez voir le type de nombre en accédant à **Voix** >  **Téléphone numéros** dans le centre d’administration Microsoft Teams et en recherchant dans la colonne **Type de** nombre. Microsoft 365 ou Office 365 crédits de communication doivent être configurés en premier pour que les utilisateurs puissent se connecter au pont sur un numéro gratuit.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Procédure d'affectation d'un nouveau numéro de téléphone de service à votre pont de conférence

> [!NOTE]
> Sauf indication contraire, toutes ces étapes doivent être effectuées dans le centre d’administration Microsoft Teams.

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Étape 1 : Affecter le nouveau numéro de téléphone à votre pont d’audioconférence

1. Dans le volet de navigation gauche, accédez à **Voix** >  **Téléphone nombres**.

2. Sélectionnez le numéro de téléphone dans la liste, puis cliquez sur **Modifier**.

3. Dans la page **Modifier** , sous **Affecté à**, développez la liste déroulante, puis sélectionnez **Pont de conférence** > **Appliquer**.

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Étape 2 : modifier le numéro de téléphone par défaut de votre pont de conférence (facultatif)

Le numéro de téléphone par défaut de votre pont de conférence définit l’ID de l’appelant qui sera utilisé lorsqu’un appel sortant est placé par un participant ou l’organisateur à partir d’une réunion.

Seul un numéro payant de service peut être défini comme numéro par défaut pour votre pont de conférence ; Les **numéros gratuits de service ne peuvent pas être définis comme numéro par défaut de votre pont de conférence**. Si vous attribuez un numéro payant de service et que vous souhaitez le définir comme nouveau numéro par défaut pour votre pont d’audioconférence, procédez comme suit :

1. Dans le volet de navigation gauche, accédez aux **ponts de conférence** **Réunions** > .

2. Mettez en surbrillance le numéro payant de service que vous souhaitez configurer comme numéro par défaut.

3. Sélectionnez **Définir par défaut**.

### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Étape 3 : modifier les numéros de téléphone par défaut inclus dans les invitations aux réunions des utilisateurs (facultatif)

Reportez-vous à [Définir les numéros de téléphone inclus dans les invitations dans Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

> [!NOTE]
> Vous pouvez également définir des numéros de téléphone en les ajoutant à *TeamsAudioconferencingpolicy et en affectant* la stratégie à vos utilisateurs. Les numéros de téléphone payants et gratuits ajoutés à la stratégie sont prioritaires sur les numéros de téléphone définis individuellement pour les utilisateurs via le volet des paramètres d’audioconférence. Si aucun numéro de téléphone n’est ajouté à *Teamsaudioconferencingpolicy*, le numéro de téléphone défini individuellement pour les utilisateurs via le volet des paramètres d’audioconférence s’affiche dans Microsoft Teams demandes de réunion. [Audioconférence paramètres de stratégie pour les numéros payants et gratuits](audio-conferencing-toll-free-numbers-policy.md) contient plus d’informations.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Étape 4 : Mettre à jour les invitations aux réunions existantes des utilisateurs à l’aide du service de migration de réunion (facultatif)

Pour les deux étapes suivantes, vous devez commencer Windows PowerShell.

Si vous avez mis à jour les numéros de téléphone par défaut inclus dans les invitations à la réunion pour certains ou tous vos utilisateurs, vous pouvez éventuellement mettre à jour les invitations aux réunions qui ont déjà été envoyées aux utilisateurs de votre organisation avant que leurs numéros de téléphone par défaut aient été modifiés à l’aide du service de migration de réunion. Pour plus d'informations, reportez-vous à la rubrique [Configuration de Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

- Exécutez le service de migration de réunion (MMS) pour les utilisateurs dont les numéros de téléphone par défaut ont été modifiés à l’étape 2. Pour cela, exécutez la commande suivante :

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- Vous pouvez également afficher le statut de migration des réunions. Toutes les réunions seront replanifiées lorsque plus aucune opération ne sera définie sur  *En attente*  ou *En cours*  .

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Procédure d'annulation d'affectation d'un numéro de téléphone de service dans votre pont de conférence

Lorsque vous annulez l'affectation d'un numéro de téléphone dans votre pont de conférence, les utilisateurs ne peuvent plus rejoindre aucune réunion à l'aide de ce numéro. Étant donné que le numéro de téléphone change, il est important de mettre à jour tous les utilisateurs qui pourraient avoir un numéro de téléphone comme numéro par défaut (le cas échéant) et de mettre à jour leurs invitations à la réunion existantes avant que le numéro de téléphone ne soit non attribué à partir du pont d’audioconférence.

Si le numéro de téléphone est supprimé sans mettre à jour les utilisateurs et leurs réunions, leurs invitations aux réunions existantes peuvent contenir un numéro de téléphone qui ne fonctionnera pas pour participer à leurs réunions.

Dans le cas de ces trois premières étapes, vous devrez démarrer Windows PowerShell. Pour consulter l’aide à ce sujet, cliquez sur [Vous souhaitez savoir comment gérer avec Windows PowerShell ?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Étape 1 : Mettre à jour les utilisateurs dont le numéro de téléphone doit être non attribué comme un de leurs numéros par défaut

Remplacez le numéro payant ou gratuit par défaut pour tous les utilisateurs dont le numéro doit être non attribué comme numéro par défaut et démarrez le processus de replanification de leurs réunions. Pour cela, exécutez la commande suivante :

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```

 > [!IMPORTANT]
 >Vous pouvez également modifier le nombre d’utilisateurs payants ou gratuits par défaut dans le centre d’administration Microsoft Teams. Toutefois, cela ne replanifiera pas leurs réunions de manière automatique.

 Pour plus d’informations, consultez [Définir les numéros de téléphone inclus dans les invitations dans Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) ou [Définir les numéros de téléphone inclus dans les invitations dans Skype Entreprise Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).

  > [!NOTE]
  > En fonction de la taille de votre organisation, cette opération peut prendre un certain temps.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Étape 2 : Affichage du statut de migration des réunions à l'aide de Windows PowerShell

Toutes les réunions seront replanifiées une fois qu’aucune opération n’est en *attente* ou *en cours* .

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Pour plus d'informations sur le service Meeting Migration Service (MMS), reportez-vous à la rubrique [Configuration de Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Étape 3 : Annuler l’affectation de l’ancien numéro de téléphone à partir du pont d’audioconférence

Utilisez l’applet de commande Unregister-CsOnlineDialInConferencingServiceNumber pour annuler l’inscription d’un numéro gratuit ou payant à partir d’un pont de conférence

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll number to be removed" -bridgeId "Conference Bridge ID"
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll free number to be removed" -bridgeId "Conference Bridge ID"
```

Remarque : pour trouver l’ID de pont de conférence, exécutez la commande PowerShell suivante : Get-CsOnlineDialInConferencingBridge.

   > [!IMPORTANT]
   > Une fois qu’un numéro de téléphone n’est plus attribué à partir d’un pont d’audioconférence, le numéro de téléphone ne sera plus disponible pour les utilisateurs qui pourront participer à des réunions nouvelles ou existantes.

### <a name="save-time-and-automate"></a>Gagner du temps et automatiser

Pour gagner du temps en automatisant ce processus, vous pouvez utiliser les applets de commande [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) ou **Set-CsOnlineDialInConferencingUserDefaultNumber** .

- Utilisez l'applet de commande [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) pour modifier le numéro payant ou gratuit par défaut pour des utilisateurs spécifiques.

  - Pour modifier le numéro gratuit par défaut pour un utilisateur, exécutez ce qui suit :

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Utilisez l'applet de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** pour modifier le numéro gratuit ou payant par défaut des utilisateurs en fonction de leur numéro par défaut d'origine ou de leur emplacement.

    > [!NOTE]
    > Pour trouver bridgeID, utilisez **Get-CsOnlineDialInConferencingBridge**.

  - Pour définir le numéro gratuit par défaut pour tous les utilisateurs qui n'en ont pas sur 8005551234, exécutez ce qui suit :

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Pour remplacer le numéro gratuit par défaut 8005551234 pour tous les utilisateurs qui l'utilisent par 8005551239 et replanifier leurs réunions de manière automatique, exécutez ce qui suit :

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - Pour définir le numéro gratuit par défaut de tous les utilisateurs situés aux États-Unis sur 8005551234 et replanifier leurs réunions de manière automatique, exécutez ce qui suit :

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > L’emplacement utilisé ci-dessus doit correspondre aux informations de contact des utilisateurs définies dans le Centre d'administration Microsoft 365.

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="the-unassign-button-isnt-available"></a>Le bouton Annuler l’affectation n’est pas disponible

Vous souhaitez annuler l’affectation d’un numéro, mais le bouton n’est pas disponible et, si vous pointez dessus, vous êtes redirigé vers le support technique avec le message suivant : « Les numéros par défaut ou partagés ne peuvent pas être désaffectés à partir du pont. Pour annuler l’affectation de numéros de péage dédiés, contactez le support technique. »

Pour obtenir plus d’informations sur le ou les ponts, exécutez powershell suivant :

```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

Le résultat, mis à part d’autres informations telles que l’identité, le nom et la région, doit également contenir defaultServiceNumber.

**Par exemple**, pour annuler l’affectation, defaultServiceNumber « 8005551234 »

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234
```

## <a name="about-windows-powershell"></a>À propos de Windows PowerShell

Avec Windows PowerShell, vous pouvez gérer les utilisateurs et leurs autorisations. Windows PowerShell pouvez vous aider à gérer Microsoft 365 ou Office 365 et Skype Entreprise Online à l’aide d’un seul point d’administration qui peut simplifier votre travail quotidien, en particulier lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :

- [Présentation de Windows PowerShell et Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

Windows PowerShell présente de nombreux avantages en termes de vitesse, de simplicité et de productivité, par rapport à l’utilisation des Centre d'administration Microsoft 365, par exemple lorsque vous apportez des modifications de paramètres à de nombreux utilisateurs à la fois. Découvrez ces avantages dans les rubriques suivantes :

- [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))

- [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Voir aussi

[Modifier les paramètres d’un pont d’audioconférence.](change-the-settings-for-an-audio-conferencing-bridge.md)
