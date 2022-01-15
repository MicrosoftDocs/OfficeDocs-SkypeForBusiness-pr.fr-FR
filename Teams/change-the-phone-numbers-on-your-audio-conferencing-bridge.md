---
title: Modification des numéros de téléphone dans le pont d’audioconférence
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
description: Découvrez les étapes requises pour affecter un nouveau numéro de téléphone de service à votre pont de conférence afin de développer la couverture pour vos utilisateurs.
ms.openlocfilehash: f8cf35c15822569aa204446cd3c1c90995ffa563
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055464"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Modifier les numéros de téléphone de votre pont d’audioconférence

Lorsque vous achetez **des licences d’audioconférence,** Microsoft héberge votre pont de conférence audio pour votre organisation. Le pont de conférence audio fournit des numéros de téléphone à composer à partir de différents emplacements de sorte que les organisateurs et participants à la réunion peuvent les utiliser pour participer à des réunions Skype Entreprise ou Microsoft Teams à l’aide d’un téléphone.
  
Outre les numéros de téléphone déjà affectés à votre pont de conférence, vous pouvez obtenir des numéros de [service](./getting-service-phone-numbers.md) supplémentaires (numéros gratuits et gratuits utilisés pour l’audioconférence) à partir d’autres emplacements, puis les affecter au pont de conférence afin d’étendre la couverture pour vos utilisateurs.
  
> [!NOTE]
> Pour pouvoir affecter/désaffecter un numéro de téléphone pour un pont de conférence, le numéro de téléphone doit être un numéro *de « service*». Vous pouvez voir le type de numéro en naviguant jusqu’à la numéro Téléphone voix dans le Centre d’administration Microsoft Teams et en regardant dans la colonne  >   **Type de** nombre. Microsoft 365 ou Office 365 les crédits de communication doivent être d’abord réglés pour que les utilisateurs peuvent se rendre sur le pont sur un numéro gratuit.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Procédure d'affectation d'un nouveau numéro de téléphone de service à votre pont de conférence

> [!NOTE]
> Sauf si c’est ce qu’on appelle autrement, toutes ces étapes doivent être effectuées dans le Microsoft Teams d’administration.

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Étape 1 : affecter le nouveau numéro de téléphone à votre pont de conférence audio

1. Dans le volet de navigation gauche, allez sur **Numéros** Téléphone  >  **voix.**

2. Sélectionnez le numéro de téléphone dans la liste, puis cliquez sur **Modifier.**

3. Dans la page **Modifier,** sous **Affecté à,** développez la page de texte, puis sélectionnez **Appliquer le pont de**  >  **conférence.**

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Étape 2 : modifier le numéro de téléphone par défaut de votre pont de conférence (facultatif)

Le numéro de téléphone par défaut de votre pont de conférence définit l’ID d’appelant qui sera utilisé lorsqu’un participant ou l’organisateur d’un appel sortant sera passé à partir d’une réunion.

Seul un numéro de service gratuit peut être réglé comme numéro par défaut pour votre pont de conférence. **des numéros gratuits de service ne peuvent** pas être définir comme numéro par défaut de votre pont de conférence. Si vous attribuez un numéro de service gratuit et que vous souhaitez le définir comme nouveau numéro par défaut de votre pont de conférence audio, effectuez les étapes suivantes :

1. Dans le volet de navigation gauche, allez sur des **ponts de conférence**  >  **Réunions.**

2. Mettez en évidence le numéro de service gratuit que vous souhaitez configurer par défaut.

3. Sélectionnez **Définir par défaut**.

### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Étape 3 : modifier les numéros de téléphone par défaut inclus dans les invitations aux réunions des utilisateurs (facultatif)

Les numéros de téléphone par défaut d’un utilisateur sont inclus dans son invitation lorsqu’il planifiera une réunion. Pour plus d’informations, notamment sur la manière dont les numéros de téléphone par défaut sont attribués aux nouveaux [utilisateurs,](set-the-phone-numbers-included-on-invites-in-teams.md) voir Définir les numéros de téléphone inclus dans les invitations dans Microsoft Teams ou Définir les numéros de téléphone inclus dans les [invitations dans Skype Entreprise Online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)

1. Dans le volet de navigation  gauche, cliquez sur Le nom d’affichage de l’utilisateur souhaité dans la liste.

2. En plus de **l’audioconférence,** cliquez sur **Modifier.**

3. Sous **Numéro gratuit** ou Numéro **gratuit,** sélectionnez le numéro dans la dropdown et cliquez sur **Appliquer.**

Une fois les modifications appliquées, les nouveaux numéros de téléphone par défaut seront inclus dans les invitations aux réunions des organisateurs lors de leur prochaine planification.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Étape 4 : mettre à jour les invitations aux réunions existantes des utilisateurs à l’aide du service Meeting Migration Service (facultatif)

Pour les deux étapes suivantes, vous devrez commencer à Windows PowerShell.
  
Si vous avez mis à jour les numéros de téléphone par défaut inclus dans les invitations à des réunions pour certains ou l’ensemble de vos utilisateurs, vous pouvez éventuellement mettre à jour les invitations aux réunions envoyées aux utilisateurs de votre organisation avant la modification de leurs numéros de téléphone par défaut à l’aide du service Meeting Migration Service (DNS). Pour plus d'informations, reportez-vous à la rubrique [Configuration de Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Exécutez meeting Migration Service (MMS) pour les utilisateurs dont le numéro de téléphone par défaut a été modifié à l’étape 2. Pour cela, exécutez la commande suivante :

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- Vous pouvez également afficher le statut de migration des réunions. Toutes les réunions seront replanifiées lorsque plus aucune opération ne sera définie sur  *En attente*  ou *En cours*  .

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Procédure d'annulation d'affectation d'un numéro de téléphone de service dans votre pont de conférence

Lorsque vous annulez l'affectation d'un numéro de téléphone dans votre pont de conférence, les utilisateurs ne peuvent plus rejoindre aucune réunion à l'aide de ce numéro. Dans la mesure où le numéro de téléphone change, il est important de mettre à jour tous les utilisateurs qui pourraient avoir un numéro de téléphone comme numéro par défaut (le cas où ils en ont un) et de mettre à jour leurs invitations aux réunions existantes avant que le numéro ne soit non inscrit dans le pont de conférence audio.

Si le numéro de téléphone est supprimé sans mettre à jour les utilisateurs et leurs réunions, leurs invitations aux réunions existantes peuvent contenir un numéro de téléphone qui ne leur permet pas de rejoindre les réunions.

Dans le cas de ces trois premières étapes, vous devrez démarrer Windows PowerShell. Pour consulter l’aide à ce sujet, cliquez sur [Vous souhaitez savoir comment gérer avec Windows PowerShell ?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Étape 1 : mettre à jour les utilisateurs dont l’utilisation du numéro de téléphone comme numéro par défaut doit être non celle des numéros

Remplacez le numéro gratuit ou gratuit par défaut pour tous les utilisateurs dont l’utilisation du numéro de téléphone comme numéro par défaut doit être non prévue et lancez le processus de nouvelle planification de leurs réunions. Pour cela, exécutez la commande suivante :

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```

 > [!IMPORTANT]
 >Vous pouvez également modifier le nombre d’utilisateurs par défaut (gratuit ou gratuit) dans le Microsoft Teams d’administration. Toutefois, cela ne replanifiera pas leurs réunions de manière automatique.

 Pour plus d’informations, voir Définir les numéros de téléphone inclus dans les [invitations Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) ou définir les numéros de téléphone inclus dans les [invitations Skype Entreprise Online.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)

  > [!NOTE]
  > En fonction de la taille de votre organisation, cette opération peut prendre un certain temps.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Étape 2 : Affichage du statut de migration des réunions à l'aide de Windows PowerShell

Toutes les réunions seront reprogrammées dès qu’aucune opération n’est en attente ou en cours *d’état.* 

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Pour plus d'informations sur le service Meeting Migration Service (MMS), reportez-vous à la rubrique [Configuration de Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Étape 3 : désaffecter l’ancien numéro de téléphone du pont de conférence audio

Utiliser la cmdlet Unregister-CsOnlineDialInConferencingServiceNumber de conférence pour désinsinser un numéro gratuit ou gratuit d’un pont de conférence

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll number to be removed" -bridgeId "Conference Bridge ID"
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll free number to be removed" -bridgeId "Conference Bridge ID"
```

Remarque : pour trouver l’ID de pont de conférence, exécutez powerShell suivant : Get-CsOnlineDialInConferencingBridge.

   > [!IMPORTANT]
   > Une fois qu’un numéro de téléphone n’est plus signé dans un pont de conférence audio, il ne sera plus disponible pour les utilisateurs qui participent à des réunions nouvelles ou existantes.

### <a name="save-time-and-automate"></a>Gagner du temps et automatiser

Pour gagner du temps en automatisant ce processus, vous pouvez utiliser les [cmdlets Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) ou **Set-CsOnlineDialInConferencingUserDefaultNumber.**

- Utilisez l'applet de commande [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) pour modifier le numéro payant ou gratuit par défaut pour des utilisateurs spécifiques.

  - Pour modifier le numéro gratuit par défaut pour un utilisateur, exécutez ce qui suit :

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Utilisez l'applet de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** pour modifier le numéro gratuit ou payant par défaut des utilisateurs en fonction de leur numéro par défaut d'origine ou de leur emplacement.

    > [!NOTE]
    > Pour trouver le BridgeID, utilisez **Get-CsOnlineDialInConferencingBridge.**

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
    > L’emplacement utilisé ci-dessus doit correspondre aux informations de contact du ou des utilisateurs définies dans le Centre d'administration Microsoft 365.

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="the-unassign-button-isnt-available"></a>Le bouton Désaffecter n’est pas disponible

Vous voulez désaffecter un numéro, mais le bouton n’est pas disponible. Si vous pointez dessus, vous êtes redirigé pour contacter le support technique avec le message suivant : « Les numéros par défaut ou partagés ne peuvent pas être désaffectés du _pont. Pour désaffecter des numéros de téléphone toll dédiés, contactez le support technique._«

Pour obtenir des informations supplémentaires sur le ou les ponts, exécutez la powershell suivante :

```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

Le résultat, à côté d’autres informations telles que Identity, Name et Region, doit également contenir DefaultServiceNumber.

**Exemple**, pour désaffecter l’affectation, defaultServiceNumber « 8005551234 »

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>À propos de Windows PowerShell

Avec Windows PowerShell, vous pouvez gérer les utilisateurs et leurs autorisations. Windows PowerShell peut vous aider à gérer Microsoft 365 ou Office 365 et Skype Entreprise Online à l’aide d’un seul point d’administration qui peut simplifier votre travail quotidien, en particulier lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :

- [Présentation de Windows PowerShell et Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation de la Centre d'administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :

- [Meilleures méthodes pour gérer vos Microsoft 365 vos Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))

- [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Sujets associés

[Modifier les paramètres d’un pont d’audioconférence.](change-the-settings-for-an-audio-conferencing-bridge.md)
