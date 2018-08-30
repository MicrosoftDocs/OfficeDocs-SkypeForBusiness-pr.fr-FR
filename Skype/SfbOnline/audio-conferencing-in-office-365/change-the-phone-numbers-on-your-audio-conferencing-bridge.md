---
title: Modifier les numéros de téléphone de votre pont d’audioconférence
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Modifier les numéros de téléphone de votre pont d’audioconférence Le pont d’audioconférence vous fournit des numéros de téléphone à composer à partir de différents endroits afin que les organisateurs et participants aux réunions puissent les utiliser pour rejoindre les réunions Skype Entreprise et Microsoft Teams à l’aide d’un téléphone.
ms.openlocfilehash: c567c1394c60b0be04cae90865cea14b856f1cd5
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255710"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Modifier les numéros de téléphone de votre pont d’audioconférence

Lorsque vous achetez des licences **Audioconférence**, Microsoft héberge le *pont d’audioconférence*  pour votre organisation. Le pont d’audioconférence vous fournit des numéros de téléphone à composer à partir de différents endroits afin que les organisateurs et participants aux réunions puissent les utiliser pour rejoindre les réunions Skype Entreprise et Microsoft Teams à l’aide d’un téléphone.

Outre les numéros de téléphone déjà affectés à votre pont de conférence, vous pouvez [obtenir des numéros de service supplémentaires](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md) (numéros gratuits et payants utilisés pour les audioconférences) d’autres endroits, puis les affecter au pont de conférence afin d’étendre la couverture pour vos utilisateurs.

> [!NOTE]
> Pour pouvoir affecter/annuler l’affectation d’un numéro de téléphone pour un pont de conférence, le numéro de téléphone doit être un numéro de « *service* ». Vous pouvez voir le type de numéro en accédant à **Voix** > **Numéros de téléphone** et en consultant la colonne **Type de numéro**. Les crédits de communication Office 365 doivent être configurés en premier pour permettre aux utilisateurs de se connecter au pont via un numéro gratuit.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Procédure d’affectation d’un nouveau numéro de téléphone de service à votre pont de conférence

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Étape 1 : Affectation d’un nouveau numéro de téléphone de service à votre pont d’audioconférence

1. Connectez-vous à Office 365 à l’aide de votre compte professionnel.

2. Accédez au **Centre d’administration Office 365** > **Centres d’administration** > **Skype Entreprise** > **Voix** > **Numéros de téléphone**.

3. Sélectionnez le numéro de téléphone dans la liste et cliquez sur **Affecter** dans le volet Action.

4. Sur la page **Affecter**, cliquez sur **Enregistrer**.

    Seul un numéro de service payant peut être défini comme numéro par défaut pour votre pont de conférence. **Vous ne pouvez pas définir un numéro de service gratuit comme numéro par défaut pour votre pont de conférence**. Si vous attribuez un numéro de service payant et que vous souhaitez le définir comme nouveau numéro par défaut de votre pont d’audioconférence, sélectionnez **Utiliser ce numéro par défaut**.

    > [!NOTE]
    > Après avoir affecté un nouveau numéro de téléphone, même si le numéro est devenu le nouveau numéro par défaut, le numéro par défaut pour les utilisateurs existants ne changera pas. Pour définir le numéro gratuit ou payant par défaut qui est ajouté aux invitations aux réunions d’un organisateur, consultez la rubrique [Définir les numéros inclus dans les invitations](set-the-phone-numbers-included-on-invites.md).



### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Étape 2 : Modification des numéros de téléphone par défaut inclus dans les invitations aux réunions des utilisateurs (facultatif)

Les numéros de téléphone par défaut pour les utilisateurs sont inclus dans leurs invitations lorsqu'ils planifient une réunion. Pour plus d’informations, voir [Définir les numéros de téléphone inclus dans les invitations](set-the-phone-numbers-included-on-invites.md).

1. Connectez-vous à Office 365 à l’aide de votre compte professionnel ou scolaire.

2. Accédez au **Centre d’administration Office 365** > **Centres d’administration** > **Skype Entreprise** > **Audioconférence** > **Utilisateurs** et sélectionnez les utilisateurs dans la liste.

3. Cliquez sur **Modifier** dans le volet Action.

4. Sous **Numéro payant par défaut** ou **Numéro gratuit par défaut**, sélectionnez le numéro dans la liste et cliquez sur **Enregistrer**.

Une fois les modifications enregistrées, les nouveaux numéros de téléphone par défaut seront inclus dans les invitations des organisateurs lorsqu’ils planifieront leur prochaine réunion.

### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Étape 3 : Mise à jour des invitations aux réunions des utilisateurs à l’aide du service Meeting Migration Service (facultatif)

Pour les deux étapes suivantes, vous devrez démarrer Windows PowerShell.

Grâce au service Meeting Migration Service (MMS), vous pouvez éventuellement mettre à jour les invitations aux réunions envoyées aux utilisateurs de votre organisation avant la modification de leur numéros de téléphone par défaut. Pour plus d'informations, reportez-vous à la rubrique [Configuration de Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).

- Exécutez le service Meeting Migration Service (MMS) pour les utilisateurs dont le numéro de téléphone par défaut a été modifié à l'étape 2. Pour cela, exécutez la commande suivante :

```
    Start-CsExMeetingMigration user@contoso.com
```

- Vous pouvez également afficher le statut de migration des réunions. Toutes les réunions seront replanifiées lorsque plus aucune opération ne sera dans les états *En attente* ou *En cours*.

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Procédure d’annulation d’affectation d’un numéro de téléphone de service d’un pont de conférence


Lorsque vous annulez l’affectation d’un numéro de téléphone d’un pont de conférence, les utilisateurs ne peuvent plus rejoindre aucune réunion à l’aide de ce numéro. En raison de la modification du numéro de téléphone, il est important de mettre à jour tous les utilisateurs pouvant disposer d’un numéro de téléphone par défaut (le cas échéant), ainsi que leurs invitations aux réunions existantes avant d’annuler l’affectation du numéro du pont d’audioconférence.

Si le numéro de téléphone est supprimé sans ces mises à jour, leurs invitations risquent de contenir un numéro qui ne leur permettra plus de rejoindre les réunions..

Dans le cas de ces trois premières étapes, vous devrez démarrer Windows PowerShell. Pour consulter l’aide à ce sujet, cliquez sur [Vous souhaitez savoir comment gérer avec Windows PowerShell ?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Étape 1 : Mise à jour des utilisateurs dont l’affectation du numéro de téléphone comme numéro par défaut doit être annulée

Remplacez le numéro payant ou gratuit par défaut de tous les utilisateurs dont l'affectation de numéro de téléphone comme numéro par défaut doit être annulée et lancez le processus de nouvelle planification de leurs réunions. Pour cela, exécutez la commande suivante :

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT]
 >Vous pouvez également modifier le numéro de téléphone payant ou gratuit par défaut des utilisateurs dans le Centre d’administration Skype Entreprise. Toutefois, cela ne replanifiera pas leurs réunions de manière automatique.

 Pour plus d’informations, voir [Définir les numéros de téléphone inclus dans les invitations](set-the-phone-numbers-included-on-invites.md).

  > [!NOTE]
  > En fonction de la taille de votre organisation, cette opération peut prendre un certain temps.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Étape 2 : Affichage du statut de migration des réunions à l’aide de Windows PowerShell

Toutes les réunions seront replanifiées lorsque plus aucune opération ne sera dans les états *En attente* ou *En cours*.

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Pour plus d’informations sur le service Meeting Migration Service, reportez-vous à la rubrique [Configuration de Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).

### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Étape 3 : Annulation de l’affectation de l’ancien numéro de téléphone dans le pont d’audioconférence

1. Connectez-vous à Office 365 à l’aide de votre compte professionnel ou scolaire.

2. Accédez au **Centre d’administration Office 365** > **Centres d’administration** > **Skype Entreprise** > **Voix** > **Numéros de téléphone**.

3. Sélectionnez le numéro de téléphone dans la liste et cliquez sur **Annuler l’affectation** dans le volet Action.

4. Dans la fenêtre de confirmation, cliquez sur **Oui**.

  > [!IMPORTANT]
  > Une fois l’affectation d’un numéro de téléphone annulée pour un pont d’audioconférence, le numéro de téléphone ne sera plus disponible et les utilisateurs ne pourront plus rejoindre les nouvelles réunions ou celles existantes.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vous souhaitez savoir comment gérer avec Windows PowerShell ?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Pour vérifier que Windows PowerShell est prêt à fonctionner

 Ces étapes permettent de vérifier que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell.

1. Depuis le **Menu Démarrer** > **Windows PowerShell**.

2. Dans la fenêtre **Windows PowerShell** pour vérifier la version, tapez _Get-Host_.

3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.

4. Vous devez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
Redémarrez votre ordinateur si vous y êtes invité.

Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).

### <a name="to-start-windows-powershell"></a>Lancer Windows PowerShell

 **Démarrez une session Windows PowerShell**

1. Depuis le **Menu Démarrer** > **Windows PowerShell**.

2. Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :

    > [!NOTE]
    > Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.

>
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

Pour plus d’informations sur le démarrage de Windows PowerShell, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou[Connexion à Skype Entreprise Online à l'aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).

### <a name="save-time-and-automate"></a>Gagner du temps et automatiser

Pour gagner du temps en automatisant ce processus, vous pouvez utiliser les applets de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) ou **Set-CsOnlineDialInConferencingUserDefaultNumber**.

- Utilisez l’applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) pour modifier le numéro payant ou gratuit par défaut pour des utilisateurs spécifiques.

  - Pour modifier le numéro gratuit par défaut pour un utilisateur, exécutez ce qui suit :

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Utilisez l’applet de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** pour modifier le numéro gratuit ou payant par défaut des utilisateurs en fonction de leur numéro par défaut d’origine ou de leur emplacement.

    > [!NOTE]
    > Pour trouver le BridgeID, utilisez **Get-CsOnlineDialInConferencingBridge**.

  - Pour définir le numéro gratuit par défaut pour tous les utilisateurs qui n’en ont pas sur 8005551234, exécutez la commande :

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
    > L’emplacement utilisé ci-dessus doit correspondre aux coordonnées des utilisateurs qui sont définies dans le Centre d’administration Office 365.

## <a name="about-windows-powershell"></a>À propos de Windows PowerShell

Avec Windows PowerShell, vous pouvez gérer les utilisateurs et leurs autorisations. Windows PowerShell peut vous aider à gérer Office 365 et Skype Entreprise Online à l’aide d’un point d’administration unique qui peut simplifier votre travail au quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Pourquoi utiliser Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :

  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Rubriques connexes
[Modifier les paramètres pour un pont d’audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md)
