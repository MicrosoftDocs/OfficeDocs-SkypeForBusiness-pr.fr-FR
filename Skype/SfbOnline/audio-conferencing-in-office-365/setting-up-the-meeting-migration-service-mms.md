---
title: Configuration de Meeting Migration Service (MMS)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users. MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.
ms.openlocfilehash: 045896fe8b612e01a22360e0c12f15ebe2719c76
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374639"
---
# <a name="setting-up-the-meeting-migration-service-mms"></a>Configuration de Meeting Migration Service (MMS)

Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users. MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.  This tool does not migrate Skype for Business meetings into Microsoft Teams meetings.  
  
 **Configuration requise**
  
Pour que MMS fonctionne, les boîtes aux lettres des organisateurs de réunion doivent être sur Exchange Online.
  
 **Principaux scénarios**
  
MMS met à jour les réunions Skype d'un utilisateur pour les deux situations suivants :
  
- Lorsque l’utilisateur est migré locale Skype pour Business Server Skype pour Business Online.
    
- Lorsque un administrateur effectue une modification aux paramètres de conférence audio de l’utilisateur qui nécessitent la mise à jour les informations de services d’audioconférence dans les réunions de cet utilisateur.
    
  **Scénarios courants pour lesquels vous ne pouvez pas utiliser MMS**
  
Voici quelques scénarios courants qui peuvent s'appliquer. Tous ces scénarios prennent en charge la migration. Toutefois, MMS ne fonctionne pas pour ces scénarios ; vous devez utiliser [l'outil de migration de réunion](https://go.microsoft.com/fwlink/p/?linkid=626047).
  
- L'emplacement des boîtes aux lettres de l'utilisateur se trouve sur une version locale de Exchange Server
    
- À l’aide d’un fournisseur de services d’audioconférence tiers
    
- Migration d’utilisateurs de Skype pour Business en ligne pour le serveur local Skype
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a>Mise à jour des réunions lorsqu'un utilisateur sur site est migré vers Skype Entreprise Online

This is the most common scenario where MMS can help create a smoother transition for your users. When a user is migrated from an on-premises Skype for Business Server to Skype for Business Online, MMS will detect the new user and will scan that user's calendar for Skype for Business and Microsoft Teams meetings. Any future meetings will be updated with the new information for that user.
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a>Si vous utilisez actuellement Skype Server 2015 pour l’audioconférence

Nous vous recommandons de suivre les meilleures pratiques suivantes afin d'exploiter pleinement MMS pour ce scénario :
  
- Puisque, pour que MMS fonctionne, la boîte aux lettres de l'utilisateur doit être sur Exchange Online, si vous effectuez une migration depuis Exchange Server sur site, déplacez d'abord la boîte aux lettres de l'utilisateur vers Exchange Online.
    
- Assign the **Audio Conferencing** license to the user before you run the `Move-CSUser` cmdlet to migrate the user. This is because MMS also updates meetings when audio conferencing settings are changed for a user. If you don't assign the license first, MMS will update all meetings again when you assign the license.
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a>Si vous utilisez actuellement un fournisseur de services d'audioconférence (ACP) tiers

With a third-party ACP, whether or not MMS runs depends on your organization's audio conferencing settings. You can choose to automatically replace the dial-in numbers from your ACP when you assign a user a **Audio Conferencing** license. On the other hand, you may need to prevent that from happening and retain the dial-in numbers from your ACP. To see your organization's setting, run the following Windows PowerShell command and check the value of the parameter `AutomaticallyReplaceAcpProvider`. If you need help with PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- If the value of this parameter is $true, then MMS will run when a user is assigned a **Audio Conferencing** license and update their meetings. The dial-in numbers from your ACP are retained until the **Audio Conferencing** license is assigned.
    
- If the value of this parameter is $false, then MMS won't update the meetings even if a user is assigned a **Audio Conferencing** licence. The dial-in numbers from your ACP are retained until the user is manually provisioned for audio conferencing in Skype for Business admin center or using Windows PowerShell.
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Mise à jour des réunions lors de la modifient des paramètres de conférence audio d’un utilisateur

MMS met à jour un Skype existant pour les réunions d’entreprise et Teams Microsoft dans les cas suivants :
  
- Lorsque vous affectez ou supprimez des licences **d’Audioconférence** .
    
- Lorsque vous activez ou désactivez les services d’audioconférence.
    
- Lorsque vous modifiez ou réinitialisez l’ID de conférence pour un utilisateur configuré pour utiliser des réunions publiques.
    
- Lorsque vous déplacez l’utilisateur vers un nouveau pont de conférence audio.
    
- When a phone number is unassigned from a audio conferencing bridge. This is a complex scenario which requires additional steps. For more information, see [Change the toll or toll free numbers on your Audio Conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).
    
> [!IMPORTANT]
> MMS only updates meetings when you're using the Microsoft bridge. If you are using a third-party audio conferencing provider, the users will need to update their meetings manually. In this case, you can use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047). 
  
Not all changes to a user's audio conferencing settings trigger MMS. Specifically, the following two changes won't result in MMS updating meetings:
  
- la modification de l'adresse SIP de l'organisateur de la réunion (qu'il s'agisse de son nom d'utilisateur SIP ou son domaine SIP) ;
    
- la modification de l'URL de réunion de votre entreprise à l'aide de la commande [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).
    
## <a name="what-happens-when-mms-updates-meetings"></a>Que se passe-t-il lorsque MMS met à jour des réunions ?

Lorsque MMS détecte que les réunions d'un utilisateur doivent être mises à jour, le service effectue les actions suivantes :
  
1. Identifier les Skype pour les réunions d’entreprise et Teams Microsoft l’utilisateur a été planifiée à l’avenir
    
   - N’importe quel Skype pour les réunions Microsoft Teams ou de l’entreprise qui se sont produites avant lors de l’exécution MMS sont ignorés.
    
   - Il met à jour uniquement les réunions dont l'utilisateur est l'organisateur.
    
2. Il remplace le bloc d'informations de la réunion en ligne dans les détails de la réunion.
    
3. Il envoie des mises à jour à tous les destinataires de la réunion de la part de l'organisateur.
    
   **Combien de temps dure l'exécution de MMS ?**
  
The amount of time it take for MMS to migrate meetings varies depending on how many users are impacted, and the total number of Skype for Business or Microsoft Teams meetings each user has on their calendar. At a minimum, it will take 10 minutes to run. While some large migrations can take up to 12 hours, most migrations should complete within 1 hour.
  
 **Limites et problèmes potentiels**
  
- Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated. In other words, if a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated.
    
- Lorsqu'une réunion est migrée, MMS remplace tous les éléments du bloc d'information de la réunion en ligne. Ainsi, si un utilisateur a modifié ce bloc, ses modifications sont écrasées. Le contenu indiqué dans les détails de la réunion et qui ne fait pas partie du bloc d'informations de la réunion en ligne n'est pas modifié.
    
     ![Le bloc de réunion mis à jour par MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- Le contenu relatif à la réunion qui a été créé ou joint à la réunion (tableaux blancs, sondages, etc.) n'est pas conservé après l'exécution de MMS Si les organisateurs de votre réunion ont joint du contenu aux réunions à l'avance, ce contenu doit être recréé après l'exécution de MMS.
    
- Le lien vers les notes de réunion partagées dans l'élément du calendrier, ainsi que dans Skype, est également écrasé. Le contenu des notes de réunion enregistrées dans OneNote n'est pas supprimé : seul le lien vers les notes partagées est écrasé.
    
- Les réunions comptant plus de 250 participants (organisateur inclus) ne feront pas l'objet d'une migration.
    
- Certains caractères Unicode dans le corps de l'invitation peuvent être mis à jour de manière incorrecte et remplacés par l'un des caractères spéciaux suivants : ï, ¿, ½, �.
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a>Que voient les utilisateurs lorsque MMS met à jour leurs réunions ?

Just like the Meeting Migration Tool, MMS sends meeting updates on behalf of users. Therefore, the only thing your users will see is another round of meeting acceptance notifications for their meetings. This might be confusing for users, so we recommend that you notify your users in advance not only when you migrate them from on-premises to Skype for Business Online, but also when you make audio conferencing changes that will trigger MMS.
  
## <a name="managing-mms"></a>Gestion de MMS

You need to use Windows PowerShell to manage MMS and check the status of ongoing migrations. The information in this section assumes that you're familiar with using PowerShell to manage your Skype for Business organization. If you are new to PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a>Comment puis-je vérifier le statut des migrations de réunion ?

Utilisez l'applet de commande  `Get-CsMeetingMigrationStatus` pour vérifier le statut des migrations de réunion. Vous trouverez ci-dessous plusieurs exemples.
  
Pour obtenir un statut récapitulatif pour toutes les migrations MMS, exécutez la commande suivante :
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Cela vous permettra de bénéficier de la vue tabulaire suivante des états de toutes les migrations :
  
État UserCount---------------<br/> En attente 21<br/>En cours 6<br/> Échec 2 <br/> Succès 131
> [!IMPORTANT]
> Si certaines des migrations ont le statut Échoué, agissez de façon à résoudre ces problèmes le plus tôt possible. Il est impossible de participer aux réunions organisées par ces utilisateurs tant que ces problèmes ne sont pas résolus. Consultez la section [Que faire en cas d'erreur ?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) pour en savoir plus.
  
Pour obtenir les détails complets de toutes les migrations d'une période précise, vous pouvez utiliser les paramètres  `StartTime` et `EndTime`. Par exemple, la commande suivante permet d'obtenir les détails complets de toutes les migrations qui ont eu lieu du 1er au 8 octobre 2016.
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

Vous pouvez également vérifier le statut de migration d'un utilisateur particulier, en utilisant le paramètre  `UserId`. Ainsi, la commande suivante permet d'obtenir le statut de l'utilisateur ashaw@contoso.com :
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a>Que faire en cas d'erreur ?
<a name="Troubleshooting"> </a>

Lorsque vous exécutez l'applet de commande  `Get-CsMeetingMigrationStatus` pour obtenir une vue récapitulative et remarquez que le statut Échouéconcernent une ou plusieurs migrations, procédez comme suit :
  
1. Identifiez les utilisateurs concernés. Exécutez la commande suivante pour obtenir la liste des utilisateurs concernés, ainsi que l'erreur spécifique signalée :
    
   ```
   Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
   ```

2. Pour chaque utilisateur, exécutez l'[outil de migration de réunion](https://go.microsoft.com/fwlink/p/?linkid=626047) afin de migrer manuellement leurs réunions.
    
3. Si la migration ne fonctionne toujours pas avec l'outil de migration de réunions, vous disposez de deux options :
    
   - demander aux utilisateurs de créer de nouvelles réunions Skype ;
    
   - [contacter le support technique](https://go.microsoft.com/fwlink/p/?LinkID=518322).
    
### <a name="enabling-and-disabling-mms"></a>Activation et désactivation de MMS
<a name="Troubleshooting"> </a>

MMS is enabled by default for all organizations, but it can be disabled as needed. For example, if you want to manually migrate all meetings or if you use a third-party audio conferencing provider, you may not need MMS running. You may also choose to temporarily disable MMS. For example, you may be doing substantial changes to the audio conferencing settings for your organization and you don't want MMS to run until all changes are completed.
  
Pour voir si MMS est activé pour votre entreprise, exécutez la commande suivante et vérifier la valeur du paramètre  `MeetingMigrationEnabled`. Si le paramètre a pour valeur $true, MMS est activé.
  
```
Get-CsTenantMigrationConfiguration
```

Pour désactiver MMS, exécutez la commande suivante :
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

Pour activer ce paramètre, exécutez la commande suivante :
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a>Activation et désactivation MMS uniquement pour les modifications de services d’audioconférence
<a name="Troubleshooting"> </a>

You can also disable MMS only for audio conferencing changes. It will still run when a user is migrated from Skype for Business on-premises to Skype for Business Online. To check the current MMS status for audio conferencing updates, run the following command and check the value for the  `AutomaticallyMigrateUserMeetings` parameter. If this parameter is set to$true, MMS is set to update user meetings when audio conferencing settings are changed.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

Pour désactiver MMS pour les conférences audio, exécutez la commande suivante :
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

Pour activer MMS pour les conférences audio, exécutez la commande suivante :
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a>Comment puis-je exécuter manuellement une migration de réunion pour un utilisateur ?
<a name="Troubleshooting"> </a>

In addition to the automatic meeting migrations, you can also run the meeting migration manually for a user by running the cmdlet **Start-CsExMeetingMigration**. This cmdlet adds the user in meeting migration queue. Meeting Migration Service will read the user request and migrate their meetings. You can check the status of meeting migration by cmdlet **Get-CsMeetingMigrationStatus**.
  
Voici un exemple qui déclenche la migration de réunion pour l'utilisateur ashaw@contoso.com :
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a>Utilisation de PowerShell pour gérer votre entreprise dans Skype Entreprise
<a name="WPSInfo"> </a>

 **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
  
1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
    
2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
    
3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.
    
4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
  
 **Démarrez une session Windows PowerShell**
  
1. Depuis le **Menu Démarrer** > **Windows PowerShell**.
    
2. Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :
    
    > [!NOTE]
    > Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.
  
> 
>   ```
>   Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
>   $credential = Get-Credential
>   $session = New-CsOnlineSession -Credential $credential
>   Import-PSSession $session
>   ```
> Pour plus d'informations sur le démarrage de Windows PowerShell, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou[Connexion à Skype Entreprise Online à l'aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
