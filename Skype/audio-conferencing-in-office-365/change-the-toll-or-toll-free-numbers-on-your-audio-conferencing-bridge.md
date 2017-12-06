---
title: "Modifier le numéro payant ou numéros gratuits sur le pont de conférence Audio"
ms.author: tonysmit
author: tonysmit
ms.date: 11/29/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.lync.lac.PSTNConferencingRemovePhoneNumberFromBridge
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
description: "Lorsque vous achetez des licences de Services d'audioconférence, Microsoft héberge votre pont de conférence audio pour votre organisation. Le pont de conférence audio vous propose des numéros de téléphone à partir d'emplacements différents afin que les participants et organisateurs de la réunion peuvent les utiliser pour participer à Skype entreprise ou Microsoft Teams réunions à l'aide d'un téléphone."
---

# Modifier le numéro payant ou numéros gratuits sur le pont de conférence Audio

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](6403f6d1-c05a-44ab-a6e0-558000e246f4.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/6403f6d1-c05a-44ab-a6e0-558000e246f4). 
  
Lorsque vous achetez des licences de **Services d'audioconférence**, Microsoft héberge votre  *pont de conférence audio*  pour votre organisation. Le pont de conférence audio vous propose des numéros de téléphone à partir d'emplacements différents afin que les participants et organisateurs de la réunion peuvent les utiliser pour participer à Skype entreprise ou Microsoft Teams réunions à l'aide d'un téléphone.
  
Outre les numéros de téléphone déjà affectés à votre pont de conférence, vous pouvez [Obtention des numéros de téléphone des services Skype Entreprise](../what-is-phone-system-in-office-365/getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) (numéro payant et numéros gratuits utilisés pour les conférences audio) à partir d'autres emplacements et puis attribuer à la conférence par-delà afin de pouvoir Développez couverture pour vos utilisateurs.
  
> [!NOTE]
> Pour pouvoir attribuer/retirer un numéro de téléphone d'un pont de conférence, le numéro de téléphone doit être un nombre « *service*  ». Vous pouvez voir le type de numéro en accédant à **voix** > **numéros de téléphone** et de recherche dans la colonne **Type nombre**. > Office 365 Communications crédits doit être définies en premier afin que les utilisateurs à composer le numéro de la passerelle sur un numéro gratuit. Voir [Modifier le numéro payant ou numéros gratuits sur le pont de conférence Audio](6403f6d1-c05a-44ab-a6e0-558000e246f4.md). 
  
## Procédure d'affectation d'un nouveau numéro de téléphone de service à votre pont de conférence

### Étape 1 : assigner le nouveau numéro de téléphone à votre pont de conférence audio

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel.
    
2. Accédez au **Centre d'administration Office 365** > **Centre d'administration** > **Skype entreprise** > **vocale** > **numéros de téléphone**.
    
3. Sélectionnez le numéro de téléphone dans la liste, puis dans le volet Action, cliquez sur **attribuer**.
    
4. Sur la page **Affecter**, cliquez sur **Enregistrer**.
    
    Uniquement un numéro payant service peut être défini comme étant le nombre par défaut pour votre pont de conférence ; **numéros gratuits service ne peuvent pas être définies comme étant le nombre par défaut de votre pont de conférence**. Si vous affectez un numéro payant service et que vous voulez définir comme le nouveau numéro par défaut pour votre pont de conférence audio, sélectionnez **utiliser ce numéro par défaut**.
    
    > [!NOTE]
    > Une fois le nouveau numéro de téléphone a été affecté, même si le nombre est devenu le nouveau numéro par défaut, le numéro par défaut pour les utilisateurs existants ne modifier. Pour définir le numéro payant par défaut ou un numéro gratuit qui est ajouté à l'invite de réunion d'un organisateur, voir [Définir les numéros de téléphone de conférence Audio pour les organisateurs comprises dans les invitations de réunion](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md). 
  
### Étape 2 : Modification des numéros de téléphone par défaut inclus dans les invitations aux réunions (facultatif)

Les numéros de téléphone par défaut pour l'utilisateur sont ceux qui est inclus dans leur réunion invite lorsqu'ils planifient une réunion. Pour plus d'informations, voir [Définir les numéros de téléphone de conférence Audio pour les organisateurs comprises dans les invitations de réunion](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au **Centre d'administration Office 365** > **Centre d'administration** > **Skype entreprise** > **audioconférence** > **utilisateurs** et sélectionnez les utilisateurs dans la liste.
    
3. Cliquez sur **Modifier** dans le volet Action.
    
4. Sous **numéro payant par défaut** ou **par défaut numéro gratuit**, sélectionnez le nombre dans la liste, puis cliquez sur **Enregistrer**.
    
Une fois que les modifications ont été enregistrées, l'autre numéro de téléphone par défaut nombres seront incluses dans la réunion invite des organisateurs de la prochaine fois qu'ils planifient une nouvelle réunion.
  
### Étape 3 : Mise à jour des invitations aux réunions des utilisateurs à l'aide du service Meeting Migration Service (MMS) (facultatif)

Pour les deux étapes suivantes, vous devrez démarrer de Windows PowerShell. Pour savoir comment effectuer cette opération, cliquez [Comment utiliser Windows PowerShell pour gérer cette fonction ?](6403f6d1-c05a-44ab-a6e0-558000e246f4.md#bk_PowerShell).
  
À l'aide du Service de Migration de réunion, vous pouvez éventuellement mettre à jour les invitations aux réunions qui ont déjà été envoyées aux utilisateurs de votre organisation avant que leurs numéros de téléphone par défaut ont été modifiés. Pour plus d'informations, voir le [Configuration de Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).
  
- Exécuter le Service de Migration de réunion (MMS) pour les utilisateurs qui disposaient leurs numéros de téléphone par défaut modifiée à l'étape 2. Pour ce faire, exécutez la commande suivante :
    
```
	Start-CsExMeetingMigration user@contoso.com

```

- Vous pouvez également afficher le statut de migration des réunions. Toutes les réunions seront replanifiées lorsque plus aucune opération ne sera définie sur  *En attente*  ou *En cours*  .
    
```
	Get-CsMeetingMigrationStatus -SummaryOnly
```

## Procédure d'annulation d'affectation d'un numéro de téléphone de service dans votre pont de conférence
<a name="bk_StartPowerShell"> </a>

Lorsque vous retirer un numéro de téléphone à partir d'un pont de conférence, les utilisateurs ne pourront pas participer à des réunions à l'aide de ce numéro de téléphone plus. Étant donné que le numéro de téléphone est modifié, il est important pour mettre à jour tous les utilisateurs qui peuvent avoir un numéro de téléphone en tant que son numéro par défaut (le cas échéant) et mettre à jour son invitations aux réunions avant le numéro de téléphone est non attribué du pont de conférence audio existant.
  
Si le numéro de téléphone est supprimé sans ces mises à jour, leurs invitations risquent de contenir un numéro qui ne leur permettra plus de rejoindre les réunions..
  
Pour les trois premières étapes, vous devrez démarrer de Windows PowerShell. Pour savoir comment effectuer cette opération, cliquez [Comment utiliser Windows PowerShell pour gérer cette fonction ?](6403f6d1-c05a-44ab-a6e0-558000e246f4.md#bk_PowerShell).
  
### Étape 1 : Mise à jour des utilisateurs dont l'affectation de numéro de téléphone comme numéro par défaut doit être annulée

Remplacez le numéro payant ou gratuit par défaut de tous les utilisateurs dont l'affectation de numéro de téléphone comme numéro par défaut doit être annulée et lancez le processus de nouvelle planification de leurs réunions. Pour cela, exécutez la commande suivante :
  
```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```

> [!NOTE]
> En fonction de la taille de votre organisation, cette opération peut prendre un certain temps. 
  
 **Vous pouvez également modifier le numéro payant par défaut ou le numéro gratuit d'utilisateurs dans le Skype centre d'administration entreprise. Toutefois, cela ne reprogrammer automatiquement leurs réunions**. Pour plus d'informations, voir[Définir les numéros de téléphone de conférence Audio pour les organisateurs comprises dans les invitations de réunion](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
### Étape 2 : Affichage du statut de migration des réunions à l'aide de Windows PowerShell

Toutes les réunions seront replanifiées une fois qu'aucune opération dans l'état  *en attente*  ou *En cours*  .
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Pour plus d'informations sur le service Meeting Migration Service (MMS), reportez-vous à la rubrique [Configuration de Meeting Migration Service (MMS)](setting-up-the-meeting-migration-service-mms.md).
  
### Étape 3 : retirer l'ancien numéro de téléphone à partir de la passerelle de services d'audioconférence

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au **Centre d'administration Office 365** > **Centre d'administration** > **Skype entreprise** > **vocale** > **numéros de téléphone**.
    
3. Sélectionnez le numéro de téléphone dans la liste, puis dans le volet Action, cliquez sur **Supprimer l'attribution**.
    
4. Dans la fenêtre de confirmation, cliquez sur **Oui**.
    
> [!IMPORTANT]
> Une fois un numéro de téléphone non attribué à partir d'un pont de conférence audio, le numéro de téléphone ne seront plus disponible aux utilisateurs de participer à des réunions nouvelles ou existantes. 
  
## Comment utiliser Windows PowerShell pour gérer cette fonction ?
<a name="bk_PowerShell"> </a>

### Vérifier que Windows PowerShell est prêt

 **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
  
1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
    
2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
    
3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.
    
4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
  
### Lancer Windows PowerShell

 **Démarrez une session Windows PowerShell**
  
1. Dans le **menu Démarrer**, recherchez **Windows PowerShell**.
    
2. Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :
    
    > [!NOTE]
    > Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

Pour plus d'informations sur le démarrage de Windows PowerShell, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou[Connexion à Skype Entreprise Online à l'aide de Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
  
### Gagner du temps ou automatiser

Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser le [Jeu-csonlinedialinconferencinguser n'affiche](http://go.microsoft.com/fwlink/?LinkId=617688) ou les applets de commande **Set-CsOnlineDialInConferencingUserDefaultNumber**.
  
- Utilisez l'applet de commande [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688) pour modifier le numéro payant ou gratuit par défaut pour des utilisateurs spécifiques.
    
  - Pour modifier le numéro gratuit par défaut pour un utilisateur, exécutez ce qui suit :
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Utilisez l'applet de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** pour modifier le numéro gratuit ou payant par défaut des utilisateurs en fonction de leur numéro par défaut d'origine ou de leur emplacement.
    
    > [!NOTE]
    > Remarque : Pour rechercher le BridgeID, utilisez l'applet de commande **Get-CsOnlineDialInConferencingBridge**.
  
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
  
### En savoir plus

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

