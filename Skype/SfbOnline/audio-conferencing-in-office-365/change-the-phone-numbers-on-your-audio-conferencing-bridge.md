---
title: "Modifier les numéros de téléphone sur le pont de conférence de données Audio"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Lorsque vous achetez des licences de conférence Audio, Microsoft héberge votre pont de conférence audio pour votre organisation. Le pont de conférence audio fournit les numéros de téléphone à partir d’emplacements différents afin que les participants et les organisateurs de la réunion peuvent les utiliser pour joindre Skype pour les réunions commerciales ou Teams de Microsoft, à l’aide d’un téléphone."
ms.openlocfilehash: 21603ebc5ea710598a1af70a66fe4388e206cea9
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Modifier les numéros de téléphone sur le pont de conférence de données Audio

Lorsque vous achetez des licences de **Conférence Audio** , Microsoft héberge votre *pont de conférence audio* pour votre organisation. Le pont de conférence audio fournit les numéros de téléphone à partir d’emplacements différents afin que les participants et les organisateurs de la réunion peuvent les utiliser pour joindre Skype pour les réunions commerciales ou Teams de Microsoft, à l’aide d’un téléphone.
  
Outre les numéros de téléphone déjà affectées à votre pont de conférence, vous pouvez [obtenir les numéros de service supplémentaires](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md) (numéro payant et numéros verts utilisés pour la conférence audio) à partir d’autres emplacements et le puis attribuer à la conférence de pont afin de pouvoir Développez la couverture pour vos utilisateurs.
  
> [!NOTE]
> Pour être en mesure d’attribuer/supprimer l’attribution d’un numéro de téléphone d’un pont de conférence, le numéro de téléphone doit être un nombre «*service*». Vous pouvez voir le type de numéro en naviguant à **voix** > de**numéros de téléphone** et de recherche dans la colonne de **Type Number** . Crédits de Communications Office 365 doit être définies en premier dans l’ordre pour les utilisateurs de se connecter à la passerelle sur un numéro d’appel gratuit. 
  
## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Procédure d'affectation d'un nouveau numéro de téléphone de service à votre pont de conférence

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Étape 1 : attribuez le nouveau numéro de téléphone pour le pont de conférence audio

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel.
    
2. Accédez au **Centre d’administration Office 365** > **Admin centres** > **Skype pour entreprise** > **voix** > **les numéros de téléphone**.
    
3. Sélectionnez le numéro de téléphone dans la liste, puis dans le volet Actions, cliquez sur **attribuer**.
    
4. Sur la page **Affecter**, cliquez sur **Enregistrer**.
    
    Uniquement un numéro de service peut être défini comme le nombre par défaut pour le pont de conférence ; **numéros gratuits de service ne peut pas être définies comme le nombre par défaut de votre pont de conférence**. Si vous affectez un numéro de service et que vous souhaitez définir comme le nouveau numéro par défaut pour le pont de conférence audio, sélectionnez **utiliser ce numéro par défaut**.
    
    > [!NOTE]
    > Après avoir affecté un nouveau numéro de téléphone, même si le numéro est devenu le nouveau numéro par défaut, le numéro par défaut pour les utilisateurs existants ne changera pas. Pour définir le numéro par défaut ou un numéro gratuit qui est ajouté à l’invite de réunion d’un organisateur, consultez [définir l’invite les inclure sur des numéros de téléphone](set-the-phone-numbers-included-on-invites.md). 
  
### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Étape 2 : Modification des numéros de téléphone par défaut inclus dans les invitations aux réunions (facultatif)

Les numéros de téléphone par défaut pour les utilisateurs sont inclus dans leur invitation lorsqu'ils planifient une réunion. Pour plus d’informations, consultez [définir l’invite les inclure sur des numéros de téléphone](set-the-phone-numbers-included-on-invites.md).
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au **Centre d’administration Office 365** > **Admin centres** > **Skype pour entreprise** > **audioconférence** > **utilisateurs** et sélectionnez les utilisateurs dans la liste.
    
3. Cliquez sur **Modifier** dans le volet Action.
    
4. Sous **numéro d’appel payant par défaut** ou **par défaut le numéro gratuit**, sélectionnez le numéro de la liste et cliquez sur **Enregistrer**.
    
Une fois que les modifications ont été enregistrées, l’autre numéro de téléphone par défaut numéros seront incluses dans la réunion invite agendas la prochaine fois qu’il planifie une nouvelle réunion.
  
### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Étape 3 : Mise à jour des invitations aux réunions des utilisateurs à l'aide du service Meeting Migration Service (MMS) (facultatif)

Pour les deux étapes suivantes, vous devez démarrer Windows PowerShell.
  
À l’aide du Service de Migration de réunion, vous pouvez éventuellement mettre à jour des invitations de réunion qui ont déjà été envoyées à des utilisateurs de votre organisation avant que leurs numéros de téléphone par défaut ont été modifiés. Pour plus d'informations, reportez-vous à la rubrique [Configuration de Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).
  
- Exécuter le Service de Migration de réunion (MMS) pour les utilisateurs qui disposaient de leurs numéros de téléphone par défaut modifié à l’étape 2. Pour cela, exécutez la commande suivante :
    
```
    Start-CsExMeetingMigration user@contoso.com

```

- Vous pouvez également afficher le statut de migration des réunions. Toutes les réunions seront replanifiées lorsque plus aucune opération ne sera définie sur  *En attente*  ou *En cours*  .
    
```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Procédure d'annulation d'affectation d'un numéro de téléphone de service dans votre pont de conférence


Lorsque vous annulez l'affectation d'un numéro de téléphone dans votre pont de conférence, les utilisateurs ne peuvent plus rejoindre aucune réunion à l'aide de ce numéro. Parce que le numéro de téléphone est modifié, il est important pour tous les utilisateurs susceptibles d’avoir un numéro de téléphone en tant que leur nombre par défaut (le cas échéant) de mettre à jour et mettre à jour les invitations aux réunions avant le numéro de téléphone n’est pas assigné dans le pont de conférence audio existant. 
  
Si le numéro de téléphone est supprimé sans ces mises à jour, leurs invitations risquent de contenir un numéro qui ne leur permettra plus de rejoindre les réunions..
  
Dans le cas de ces trois premières étapes, vous devrez démarrer Windows PowerShell. Pour savoir comment procéder, cliquez sur [pour connaître la façon de gérer avec Windows PowerShell ?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)
  
### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Étape 1 : Mise à jour des utilisateurs dont l'affectation de numéro de téléphone comme numéro par défaut doit être annulée

Remplacez le numéro payant ou gratuit par défaut de tous les utilisateurs dont l'affectation de numéro de téléphone comme numéro par défaut doit être annulée et lancez le processus de nouvelle planification de leurs réunions. Pour cela, exécutez la commande suivante :
  
```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >Vous pouvez également modifier le numéro payant de par défaut ou le numéro d’appel gratuit d’utilisateurs dans le Skype pour le centre d’administration de Business. Toutefois, cela ne replanifie automatiquement leurs réunions. 
 
 Pour plus d’informations, consultez [définir invite les inclure sur des numéros de téléphone](set-the-phone-numbers-included-on-invites.md).

  > [!NOTE]
  > En fonction de la taille de votre organisation, cette opération peut prendre un certain temps. 
  
### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Étape 2 : Affichage du statut de migration des réunions à l'aide de Windows PowerShell

Toutes les réunions seront replanifiées une fois qu’il n’existe aucune opération dans l’état *en attente* ou *En cours* .
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Pour plus d'informations sur le service Meeting Migration Service (MMS), reportez-vous à la rubrique [Configuration de Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Étape 3 : supprimer l’attribution de l’ancien numéro de téléphone du pont de conférence audio

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au **Centre d’administration Office 365** > **Admin centres** > **Skype pour entreprise** > **voix** > **les numéros de téléphone**.
    
3. Sélectionnez le numéro de téléphone dans la liste, puis dans le volet Actions, cliquez sur **Supprimer l’attribution**.
    
4. Dans la fenêtre de confirmation, cliquez sur **Oui**.
    
  > [!IMPORTANT]
  > Une fois un numéro de téléphone est assigné à partir d’un pont de conférence audio, le numéro de téléphone ne sera plus disponible pour les utilisateurs de participer à des conférences de nouveau ou existants. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Vérifier que Windows PowerShell est prêt

 **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
  
1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
    
2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
    
3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.
    
4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
  
### <a name="to-start-windows-powershell"></a>Lancer Windows PowerShell

 **Démarrez une session Windows PowerShell**
  
1. From the **Start Menu** > **Windows PowerShell**.
    
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

Si vous souhaitez plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [connexion à Skype pour entreprise en ligne à l’aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
### <a name="save-time-or-automate"></a>Gagner du temps ou automatiser

Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser le [Jeu-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) ou les applets de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** .
  
- Utilisez l'applet de commande [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) pour modifier le numéro payant ou gratuit par défaut pour des utilisateurs spécifiques.
    
  - Pour modifier le numéro gratuit par défaut pour un utilisateur, exécutez ce qui suit :
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Utilisez l'applet de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** pour modifier le numéro gratuit ou payant par défaut des utilisateurs en fonction de leur numéro par défaut d'origine ou de leur emplacement.
    
    > [!NOTE]
    > Pour rechercher la BridgeID, utilisez le **Get-CsOnlineDialInConferencingBridge**.
  
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
  
## <a name="about-windows-powershell"></a>À propos de Windows PowerShell

Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Rubriques connexes
[Modifier les paramètres pour un pont d'audioconférence](change-the-settings-for-an-audio-conferencing-bridge.md)
  