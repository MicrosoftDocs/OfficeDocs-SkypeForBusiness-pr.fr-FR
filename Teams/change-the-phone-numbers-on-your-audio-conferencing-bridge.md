---
title: Modifier les numéros de téléphone de votre pont d’audioconférence
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: When you buy Audio Conferencing licenses, Microsoft is hosting your audio conferencing bridge for your organization. The audio conferencing bridge gives out dial-in phone numbers from different locations so meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.
ms.openlocfilehash: bc26fc64f4b95c1a469908251781c4951c7d0a84
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211799"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Modifier les numéros de téléphone de votre pont d’audioconférence

Lorsque vous achetez des licences de **Services d’audioconférence** , Microsoft héberge votre pont de conférence audio pour votre organisation. Le pont de conférence audio permet aux numéros de téléphone à partir de différents emplacements afin que les organisateurs de réunions et les participants peuvent utiliser les joindre Skype pour les réunions Microsoft Teams ou de l’entreprise à l’aide d’un téléphone.
  
Outre les numéros de téléphone déjà affectés à votre pont de conférence, vous pouvez [obtenir les numéros de service supplémentaires](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) (payants et gratuits utilisés pour la conférence audio) à partir d’autres emplacements, puis attribuer à la conférence un pont afin de pouvoir Développez la couverture pour vos utilisateurs.
  
> [!NOTE]
> Pour pouvoir affecter/annuler l’affectation d’un numéro de téléphone pour un pont de conférence, le numéro de téléphone doit être un nombre de «*service*». Vous pouvez voir le type de numéro en accédant à **voix** > hérité portail et en recherche dans la colonne **Type de numéro de** **numéros de téléphone** . Les crédits de communication Office 365 doivent être configurés en premier pour permettre aux utilisateurs de se connecter au pont via un numéro gratuit.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Procédure d'affectation d'un nouveau numéro de téléphone de service à votre pont de conférence

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Étape 1 : attribuer le numéro de téléphone à votre pont de conférence audio

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel.

2. Accédez au **Centre d’administration Office 365** > **Admin centres** > **& équipes Skype** > **portail hérité** > **vocale** > **numéros de téléphone**.

3. Sélectionnez le numéro de téléphone dans la liste, puis dans le volet Actions, cliquez sur **affecter**.

4. Sur la page **Affecter**, cliquez sur **Enregistrer**.

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Étape 2 : modifier le numéro de téléphone par défaut de votre pont de conférence (facultatif)

Le numéro de téléphone par défaut de votre pont de conférence définit l’ID d’appelant qui sera utilisé lorsqu’un appel sortant est placé par l’organisateur à partir d’une réunion ou d’un participant.

Uniquement un numéro de service peut être défini en tant que le numéro par défaut pour votre pont de conférence ; **numéros gratuits service ne peut pas être définis en tant que le numéro par défaut de votre pont de conférence**. Si vous affectez un numéro de service et que vous souhaitez définir en tant que le nouveau numéro par défaut pour votre pont de conférence audio, procédez comme suit :

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel.

2. Accédez au **Centre d’administration Office 365** > **Admin centres** > **& équipes Skype** > **réunions** > **Ponts de conférence**.

3. Mettez en surbrillance le numéro de service que vous souhaitez configurer en tant que la valeur par défaut.

4. Sélectionnez **Définir par défaut**.
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Étape 3 : modifier les numéros de téléphone par défaut qui sont inclus dans la réunion invite d’utilisateurs (facultatifs)

Les numéros de téléphone par défaut d’un utilisateur sont ceux qui est inclus dans leur réunion invite lorsqu’ils planifient une réunion. Pour plus d’informations, notamment le mode d’attribution des numéros de téléphone par défaut pour les nouveaux utilisateurs, voir [définir le téléphone numéros inclus sur invite dans les équipes Microsoft](set-the-phone-numbers-included-on-invites-in-teams.md) ou [le téléphone numéros inclus sur invite dans Skype pour Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Accéder au **Centre d’administration Office 365** > **Admin centres** > **& équipes Skype** > **portail hérité** > **audioconférence** > **les utilisateurs**, puis sélectionnez les utilisateurs dans la liste.

3. Cliquez sur **Modifier** dans le volet Action.

4. Sous **numéro de téléphone payant par défaut** ou **par défaut numéro gratuit**, sélectionnez le numéro dans la liste, cliquez sur **Enregistrer**.

Une fois que les modifications ont été enregistrées, l’autre numéro de téléphone par défaut numéros doivent être incluses dans la réunion invite des organisateurs la prochaine fois qu’il planifie une nouvelle réunion.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Étape 4 : mise à jour existant meeting invite d’utilisateurs à l’aide du Service de Migration de réunion (facultatif)

Pour les deux étapes suivantes, vous devrez démarrer de Windows PowerShell.
  
Si la mise à jour de téléphone par défaut invite les numéros qui sont inclus dans la réunion pour tout ou partie de vos utilisateurs, vous pouvez éventuellement mettre à jour des invitations de réunion qui ont déjà été envoyées aux utilisateurs de votre organisation avant que leurs numéros de téléphone par défaut ont été modifiées à l’aide de la Service de Migration de réunion. Pour plus d'informations, reportez-vous à la rubrique [Configuration de Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Exécutez le Service de Migration de réunion (MMS) pour les utilisateurs qui avaient leurs numéros de téléphone par défaut modifié à l’étape 2. Pour cela, exécutez la commande suivante :

```
    Start-CsExMeetingMigration user@contoso.com
```

- Vous pouvez également afficher le statut de migration des réunions. Toutes les réunions seront replanifiées lorsque plus aucune opération ne sera définie sur  *En attente*  ou *En cours*  .

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Procédure d'annulation d'affectation d'un numéro de téléphone de service dans votre pont de conférence


Lorsque vous annulez l'affectation d'un numéro de téléphone dans votre pont de conférence, les utilisateurs ne peuvent plus rejoindre aucune réunion à l'aide de ce numéro. Étant donné que le numéro de téléphone est modifié, il est important pour mettre à jour tous les utilisateurs qui peuvent avoir un numéro de téléphone comme leur numéro par défaut (le cas échéant) et mettre à jour les invitations aux réunions avant le numéro de téléphone non attribué dans le pont de conférence audio existant.

Si le numéro de téléphone est supprimé sans mettre à jour les utilisateurs et leurs réunions, les invitations aux réunions existante peut contenir un numéro de téléphone qui ne fonctionne pas pour participer à des réunions.

Dans le cas de ces trois premières étapes, vous devrez démarrer Windows PowerShell. Pour consulter l’aide à ce sujet, cliquez sur [Vous souhaitez savoir comment gérer avec Windows PowerShell ?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Étape 1 : les utilisateurs de mise à jour qui ont le numéro de téléphone à non affectés en tant qu’un de leurs numéros par défaut

Remplacez le numéro payant par défaut ou un numéro gratuit pour tous les utilisateurs qui ont le numéro non attribué par défaut et démarrer le processus de replanification des réunions. Pour cela, exécutez la commande suivante :

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >Vous pouvez également modifier le numéro payant par défaut ou le numéro gratuit d’utilisateurs dans le Skype entreprise centre d’administration. Toutefois, cela ne replanifiera pas leurs réunions de manière automatique. 
 
 Pour plus d’informations, voir [définir le téléphone numéros inclus sur invite dans les équipes Microsoft](set-the-phone-numbers-included-on-invites-in-teams.md) ou [le téléphone numéros inclus sur invite dans Skype pour Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).

  > [!NOTE]
  > En fonction de la taille de votre organisation, cette opération peut prendre un certain temps.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Étape 2 : Affichage du statut de migration des réunions à l'aide de Windows PowerShell

Toutes les réunions seront replanifiées alors qu’aucune opération à l’état *en attente* ou *En cours* .

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Pour plus d'informations sur le service Meeting Migration Service (MMS), reportez-vous à la rubrique [Configuration de Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Étape 3 : annuler l’affectation de l’ancien numéro de téléphone à partir du pont d’audioconférence

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Accéder au **Centre d’administration Office 365** > **Admin centres** > **& équipes Skype** > **portail hérité** > **vocale** > **numéros de téléphone**.

3. Sélectionnez le numéro de téléphone dans la liste, puis dans le volet Actions, cliquez sur **Supprimer l’attribution**.

4. Dans la fenêtre de confirmation, cliquez sur **Oui**.

   > [!IMPORTANT]
   > Une fois un numéro de téléphone non attribué à partir d’un pont de conférence audio, le numéro de téléphone ne sera plus disponible pour les utilisateurs à participer à des réunions de nouveau ou existantes.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Vérifier que Windows PowerShell est prêt

 Ces étapes Vérifiez que vous exécutez Windows PowerShell version 3.0 ou ultérieure.

1. Depuis le **Menu Démarrer** > **Windows PowerShell**.

2. Dans la fenêtre **Windows PowerShell** pour vérifier la version, tapez _Get-Host_.

3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.

4. Vous devez également installer le module Windows PowerShell pour Skype pour Business en ligne qui vous permet de créer une session Windows PowerShell à distance qui se connecte à Skype pour Business Online. Ce module est pris en charge uniquement sur les ordinateurs 64 bits et peut être téléchargé depuis le Center Download Microsoft sur [Le Module Windows PowerShell pour Skype pour Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
Redémarrez votre ordinateur si vous y êtes invité.

Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).

### <a name="to-start-windows-powershell"></a>Lancer Windows PowerShell

 **Démarrez une session Windows PowerShell**

1. From the **Start Menu** > **Windows PowerShell**.

2. Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :

>
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.
Si vous souhaitez plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [Connecting to Skype pour Business Online à l’aide de Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).

### <a name="save-time-and-automate"></a>Gagner du temps et automatiser

Pour gagner du temps en l’automatisation de ce processus, vous pouvez utiliser la [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) ou les applets de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** .

- Utilisez l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) pour modifier le numéro payant ou gratuit par défaut pour des utilisateurs spécifiques.

  - Pour modifier le numéro gratuit par défaut pour un utilisateur, exécutez ce qui suit :

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Utilisez l'applet de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** pour modifier le numéro gratuit ou payant par défaut des utilisateurs en fonction de leur numéro par défaut d'origine ou de leur emplacement.

    > [!NOTE]
    > Pour rechercher la BridgeID, utilisez la **Get-CsOnlineDialInConferencingBridge**.

  - Pour définir le numéro gratuit par défaut pour tous les utilisateurs qui n'en ont pas sur 8005551234, exécutez ce qui suit :

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Pour remplacer le numéro gratuit par défaut 8005551234 pour tous les utilisateurs qui l'utilisent par 8005551239 et replanifier leurs réunions de manière automatique, exécutez ce qui suit :

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - Pour définir le numéro gratuit par défaut de tous les utilisateurs situés aux États-Unis sur 8005551234 et replanifier leurs réunions de manière automatique, exécutez ce qui suit :

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > L'emplacement utilisé ci-dessus doit correspondre aux coordonnées des utilisateurs qui sont définies dans le Centre d'administration Office 365.

## <a name="troubleshooting"></a>Résolution des problèmes

**Annuler l’affectation bouton est grisé**

Vous souhaitez annuler l’affectation d’un nombre, mais le bouton est grisé et si tout en hoovering dessus, vous êtes redirigé pour contacter le Support avec le message suivant _« par défaut ou numéros partagé can´t être non affectés à partir de la passerelle. Pour annuler l’affectation de numéros payants dédié, contactez le support technique._».

Pour obtenir plus d’informations sur la bridge(s), exécutez la Powershell suivante :
```
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

Le résultat, côté d’autres informations comme identité, le nom et la région, doit également contenir le DefaultServiceNumber.

**Exemple**, pour annuler l’affectation, la DefaultServiceNumber « 8005551234 »
```
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName “Conference Bridge” -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>À propos de Windows PowerShell

Avec Windows PowerShell, vous pouvez gérer les utilisateurs et leurs autorisations. Windows PowerShell peut vous aider à gérer Office 365 et Skype pour Business Online à l’aide d’un point unique d’administration qui peut simplifier votre travail quotidien, en particulier lorsque vous avez plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :

  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Voir aussi
[Modifier les paramètres d’un pont d’audioconférence.](change-the-settings-for-an-audio-conferencing-bridge.md)
