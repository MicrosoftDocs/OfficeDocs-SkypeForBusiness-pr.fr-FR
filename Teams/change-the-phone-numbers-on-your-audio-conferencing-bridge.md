---
title: Modification des numéros de téléphone sur l’audio Conferencing Bridge
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
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Découvrez les étapes nécessaires à l’affectation d’un nouveau numéro de téléphone de service à votre pont de conférence pour développer la couverture de vos utilisateurs.
ms.openlocfilehash: e0786ad2c35ebe7d9663a71b594f7f5facd73b08
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691380"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>Modifier les numéros de téléphone de votre pont d’audioconférence

Lorsque vous achetez des licences de **conférence audio** , Microsoft héberge votre pont de conférence audio pour votre organisation. Le pont de conférence rend les numéros de téléphone d’accès à partir de différents emplacements de sorte que les organisateurs de la réunion et les participants puissent les utiliser pour participer à des réunions Skype entreprise ou Microsoft teams à l’aide d’un téléphone.
  
Outre les numéros de téléphone déjà attribués à votre pont de conférence, vous pouvez [obtenir des numéros de service supplémentaires](/microsoftteams/getting-service-phone-numbers) (numéro payant et numéro gratuit utilisés pour les conférences audio) à partir d’autres emplacements, puis les affecter à la Conférence de conférence pour développer la couverture de vos utilisateurs.
  
> [!NOTE]
> Pour être en mesure d’affecter/retirer un numéro de téléphone à un pont de conférence, le numéro de téléphone doit être un numéro de*service*. Vous pouvez voir le type de numéro qu’il contient en accédant **aux**  >  **numéros de téléphone** dans le portail hérité et en regardant dans la colonne **type de nombre** . Les crédits de communications Microsoft 365 ou Office 365 doivent d’abord être configurés pour permettre aux utilisateurs de se connecter au pont sur un numéro gratuit.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>Procédure d'affectation d'un nouveau numéro de téléphone de service à votre pont de conférence

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>Étape 1 : affectation d’un nouveau numéro de téléphone à votre pont de conférence audio

1. Connectez-vous à Microsoft 365 ou Office 365 à l’aide de votre compte professionnelle.

2. Accédez aux centres d’administration du **Centre d’administration Microsoft 365**  >  **Admin centers**  >  **équipes &** aux  >  numéros de téléphone vocaux du**portail hérité**de Skype  >  **Voice**  >  **Phone numbers**.

3. Sélectionnez le numéro de téléphone dans la liste, puis, dans le volet action, cliquez sur **affecter**.

4. Sur la page **Affecter**, cliquez sur **Enregistrer**.

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>Étape 2 : modifier le numéro de téléphone par défaut de votre pont de conférence (facultatif)

Le numéro de téléphone par défaut de votre pont de conférence définit l’IDENTIFIant de l’appelant qui sera utilisé lors de la placement d’un appel sortant par un participant ou par l’organisateur à partir d’une réunion.

Seul le numéro payant du service peut être défini comme numéro par défaut de votre pont de conférence. **les numéros gratuits du service ne peuvent pas être définis comme numéro par défaut de votre pont de conférence**. Si vous affectez un numéro payant de service et que vous voulez le configurer comme nouveau numéro par défaut de votre pont de conférence audio, procédez comme suit :

1. Connectez-vous à Microsoft 365 ou Office 365 à l’aide de votre compte professionnelle.

2. Accédez aux centres d’administration du **Centre d’administration Microsoft 365**  >  **Admin centers**  >  **équipes & équipes**de  >  **Meetings**  >  **conférences**Skype.

3. Mettez en surbrillance le numéro payant du service à configurer par défaut.

4. Sélectionnez **Définir par défaut**.
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>Étape 3 : modifier les numéros de téléphone par défaut inclus dans les invitations aux réunions (facultatif)

Le numéro de téléphone par défaut d’un utilisateur est celui qui est inclus dans les invitations à la réunion lors de la planification d’une réunion. Pour plus d’informations sur l’affectation des numéros de téléphone par défaut pour les nouveaux utilisateurs, reportez-vous à [la rubrique définition des numéros de téléphone inclus dans les invitations de Microsoft teams](set-the-phone-numbers-included-on-invites-in-teams.md) ou [définition des numéros de téléphone des invitations dans Skype entreprise Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).
  
1. Connectez-vous à l’aide de votre compte professionnel ou scolaire.

2. Accédez aux centres d’administration du **Centre d’administration 365 Microsoft**  >  **Admin centers**  >  **teams &**  >  **Legacy portal**  >  **Audio conferencing**  >  **les utilisateurs**de l’audioconférence Skype hérités, puis sélectionnez les utilisateurs dans la liste.

3. Cliquez sur **Modifier** dans le volet Action.

4. Sous **numéro payant par défaut** ou **numéro gratuit par défaut**, sélectionnez le numéro dans la liste et cliquez sur **Enregistrer**.

Une fois les changements enregistrés, les nouveaux numéros de téléphone par défaut seront inclus dans les invitations aux réunions des organisateurs lors de leur prochaine planification.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>Étape 4 : mettre à jour les invitations aux réunions existantes à l’aide du service de migration des réunions (facultatif)

Pour les deux étapes suivantes, vous devrez démarrer Windows PowerShell.
  
Si vous avez mis à jour les numéros de téléphone par défaut inclus dans les invitations aux réunions pour tout ou partie de vos utilisateurs, vous pouvez également mettre à jour les invitations aux réunions déjà envoyées aux utilisateurs de votre organisation avant de modifier leurs numéros de téléphone par défaut à l’aide du service de migration des réunions. Pour plus d'informations, reportez-vous à la rubrique [Configuration de Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Exécutez le service de migration de réunion (MMS) pour les utilisateurs qui ont modifié leurs numéros de téléphone par défaut à l’étape 2. Pour cela, exécutez la commande suivante :

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- Vous pouvez également afficher le statut de migration des réunions. Toutes les réunions seront replanifiées lorsque plus aucune opération ne sera définie sur  *En attente*  ou *En cours*  .

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>Procédure d'annulation d'affectation d'un numéro de téléphone de service dans votre pont de conférence


Lorsque vous annulez l'affectation d'un numéro de téléphone dans votre pont de conférence, les utilisateurs ne peuvent plus rejoindre aucune réunion à l'aide de ce numéro. Le numéro de téléphone étant modifié, il est important de mettre à jour tous les utilisateurs qui pourraient avoir un numéro de téléphone comme numéro par défaut (le cas échéant) et mettre à jour les invitations à la réunion avant que le numéro de téléphone ne soit non affecté par le pont de conférence audio.

Si le numéro de téléphone est supprimé sans la mise à jour des utilisateurs et de leurs réunions, les invitations de réunion existantes peuvent contenir un numéro de téléphone qui ne fonctionne pas pour joindre leurs réunions.

Dans le cas de ces trois premières étapes, vous devrez démarrer Windows PowerShell. Pour consulter l’aide à ce sujet, cliquez sur [Vous souhaitez savoir comment gérer avec Windows PowerShell ?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>Étape 1 : mettre à jour les utilisateurs dont le numéro de téléphone ne doit pas être attribué en tant qu’un de leurs numéros par défaut

Remplacez le numéro gratuit par défaut pour tous les utilisateurs dont le numéro doit être non affecté par défaut et commencez le processus de replanification de leurs réunions. Pour cela, exécutez la commande suivante :

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >Vous pouvez également modifier le nombre d’utilisateurs payant ou gratuit par défaut dans le centre d’administration Skype entreprise. Toutefois, cela ne replanifiera pas leurs réunions de manière automatique. 
 
 Pour plus d’informations, reportez-vous à [la rubrique définition des numéros de téléphone inclus dans les invitations de Microsoft teams](set-the-phone-numbers-included-on-invites-in-teams.md) ou [définition des numéros de téléphone des invitations dans Skype entreprise Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).

  > [!NOTE]
  > En fonction de la taille de votre organisation, cette opération peut prendre un certain temps.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>Étape 2 : Affichage du statut de migration des réunions à l'aide de Windows PowerShell

Toutes les réunions seront replanifiées lorsque aucune opération n’est en *attente* ou en *cours* .

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

Pour plus d'informations sur le service Meeting Migration Service (MMS), reportez-vous à la rubrique [Configuration de Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>Étape 3 : annulation de l’affectation de l’ancien numéro de téléphone du pont de conférence audio

1. Connectez-vous à l’aide de votre compte professionnel ou scolaire.

2. Accédez aux centres d’administration du **Centre d’administration 365 Microsoft**  >  **Admin centers**  >  **teams &** les  >  numéros de téléphone vocaux du**portail hérité**de Skype  >  **Voice**  >  **Phone numbers**.

3. Si le numéro de téléphone est un numéro gratuit, sélectionnez le numéro de téléphone dans la liste, puis, dans le volet action, cliquez sur **Annuler l’affectation**. Si le numéro de téléphone est un numéro payant, contactez le [support technique Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) pour obtenir le numéro de téléphone non affecté.

4. Si le numéro de téléphone est un numéro gratuit, cliquez sur **Oui** dans la fenêtre de confirmation.

   > [!IMPORTANT]
   > Après l’affectation d’un numéro de téléphone à un pont de conférence audio, le numéro de téléphone ne sera plus disponible pour les utilisateurs qui peuvent rejoindre une réunion nouvelle ou existante.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Vérifier que Windows PowerShell est prêt

 Ces étapes vérifient que vous exécutez la version 3,0 ou une version ultérieure de Windows PowerShell.

1. Depuis le **Menu Démarrer** > **Windows PowerShell**.

2. Dans la fenêtre **Windows PowerShell** pour vérifier la version, tapez _Get-Host_.

3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4,0, voir [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .
Redémarrez votre ordinateur lorsque vous y êtes invité.

4. Vous devez également installer le module Windows PowerShell pour Skype entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype entreprise online. Ce module est uniquement pris en charge sur les ordinateurs 64 bits et peut être téléchargé à partir du centre de téléchargement Microsoft dans le [module Windows PowerShell pour Skype entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
Redémarrez votre ordinateur si vous y êtes invité.

Pour en savoir plus, voir [se connecter à tous les services Microsoft 365 ou Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).

### <a name="to-start-windows-powershell"></a>Lancer Windows PowerShell

 **Démarrez une session Windows PowerShell**

1. From the **Start Menu** > **Windows PowerShell**.

2. Dans la fenêtre **Windows PowerShell** , connectez-vous à Microsoft 365 ou Office 365 en exécutant :

>
  ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.
Pour plus d’informations sur le démarrage de Windows PowerShell, voir [connexion à tous les services Microsoft 365 ou Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [connexion à Skype entreprise Online à l’aide de Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).

### <a name="save-time-and-automate"></a>Gagnez du temps et automatisez

Pour gagner du temps en automatisant ce processus, vous pouvez utiliser les applets [de connexion Set-csonlinedialinconferencinguser n’affiche](https://go.microsoft.com/fwlink/?LinkId=617688) ou **Set-CsOnlineDialInConferencingUserDefaultNumber** .

- Utilisez l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) pour modifier le numéro payant ou gratuit par défaut pour des utilisateurs spécifiques.

  - Pour modifier le numéro gratuit par défaut pour un utilisateur, exécutez ce qui suit :

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- Utilisez l'applet de commande **Set-CsOnlineDialInConferencingUserDefaultNumber** pour modifier le numéro gratuit ou payant par défaut des utilisateurs en fonction de leur numéro par défaut d'origine ou de leur emplacement.

    > [!NOTE]
    > Pour rechercher le BridgeID, utilisez **Get-CsOnlineDialInConferencingBridge**.

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
    > L’emplacement utilisé ci-dessus doit correspondre aux coordonnées des utilisateurs qui sont définies dans le centre d’administration 365 Microsoft.

## <a name="troubleshooting"></a>Résolution des problèmes

**Le bouton Annuler l’affectation n’est pas disponible**

Vous voulez annuler l’affectation d’un numéro, mais le bouton n’est pas disponible et, si vous pointez dessus, vous êtes redirigé vers contacter le support technique avec le message suivant : _«les numéros par défaut ou les numéros partagés peuvent ́t pas être attribués à partir du pont. Pour retirer des numéros payants, veuillez contacter le service clientèle._

Pour obtenir des informations supplémentaires sur le ou les ponts, exécutez la commande PowerShell suivante :
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

Le résultat, à l’instar des informations telles que l’identité, le nom et la région, doit également contenir le DefaultServiceNumber.

**Par exemple**, pour annuler l’affectation, le DefaultServiceNumber « 8005551234 »
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>À propos de Windows PowerShell

Avec Windows PowerShell, vous pouvez gérer les utilisateurs et leurs autorisations. Windows PowerShell peut vous aider à gérer Microsoft 365 ou Office 365 et Skype entreprise Online à l’aide d’un point d’administration unique qui peut vous simplifier le travail quotidien, en particulier lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois. Découvrez ces avantages dans les rubriques suivantes :

  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Rubriques connexes
[Modifier les paramètres d’un pont d’audioconférence.](change-the-settings-for-an-audio-conferencing-bridge.md)
