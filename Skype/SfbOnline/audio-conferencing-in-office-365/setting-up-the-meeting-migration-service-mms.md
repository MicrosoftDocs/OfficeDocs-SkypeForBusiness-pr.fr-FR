---
title: Configuration de Meeting Migration Service (MMS)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
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
description: "Service de Migration (MMS) de réunion est un Skype pour service d’entreprise qui s’exécute en arrière-plan et met automatiquement à jour Skype pour les réunions d’entreprise et Teams de Microsoft pour les utilisateurs. MMS est conçu pour éliminer le besoin pour les utilisateurs d’exécuter l’outil de Migration de réunion mise à jour de leur Skype pour les réunions d’entreprise et Teams de Microsoft."
ms.openlocfilehash: 0d33efb2f60a06853ba26cd6e525f624114c95a5
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="setting-up-the-meeting-migration-service-mms"></a>Configuration de Meeting Migration Service (MMS)

Service de Migration (MMS) de réunion est un Skype pour service d’entreprise qui s’exécute en arrière-plan et met automatiquement à jour Skype pour les réunions d’entreprise et Teams de Microsoft pour les utilisateurs. MMS est conçu pour éliminer le besoin pour les utilisateurs d’exécuter l’outil de Migration de réunion mise à jour de leur Skype pour les réunions d’entreprise et Teams de Microsoft.
  
 **Configuration requise**
  
Pour que MMS fonctionne, les boîtes aux lettres des organisateurs de réunion doivent être sur Exchange Online.
  
 **Principaux scénarios**
  
MMS met à jour les réunions Skype d'un utilisateur pour les deux situations suivants :
  
- Lorsque l’utilisateur migré à partir de locaux Skype pour Business Server Skype pour l’activité en ligne.
    
- Lorsqu’un administrateur modifie des paramètres de conférence audio de l’utilisateur qui nécessitent les informations d’audioconférence au cours des réunions de cet utilisateur de mise à jour.
    
 **Scénarios courants pour lesquels vous ne pouvez pas utiliser MMS**
  
Voici quelques scénarios courants qui peuvent s'appliquer. Tous ces scénarios prennent en charge la migration. Toutefois, MMS ne fonctionne pas pour ces scénarios ; vous devez utiliser [l'outil de migration de réunion](https://go.microsoft.com/fwlink/p/?linkid=626047).
  
- L'emplacement des boîtes aux lettres de l'utilisateur se trouve sur une version locale de Exchange Server
    
- À l’aide d’un fournisseur de conférence audio de tiers
    
- Migration d’utilisateurs de Skype pour entreprise en ligne au serveur de Skype sur site
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a>Mise à jour des réunions lorsqu'un utilisateur sur site est migré vers Skype Entreprise Online

Il s'agit du scénario de simplification de la transition de vos utilisateurs avec MMS le plus courant. Lorsqu’un utilisateur est migré à partir d’un local Skype pour Business Server vers Skype pour Business Online, MMS détecte le nouvel utilisateur et il analyse le calendrier de l’utilisateur Skype pour les réunions d’entreprise et Teams de Microsoft. Toutes les réunions futures seront mis à jour avec les nouvelles informations de cet utilisateur.
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a>Si vous utilisez actuellement Skype serveur 2015 pour la conférence audio

Nous vous recommandons de suivre les meilleures pratiques suivantes afin d'exploiter pleinement MMS pour ce scénario :
  
- Puisque, pour que MMS fonctionne, la boîte aux lettres de l'utilisateur doit être sur Exchange Online, si vous effectuez une migration depuis Exchange Server sur site, déplacez d'abord la boîte aux lettres de l'utilisateur vers Exchange Online.
    
- Attribuer la licence **Audioconférence** à l’utilisateur avant d’exécuter le `Move-CSUser` applet de commande pour la migration de l’utilisateur. C’est pourquoi MMS met également à jour réunions lorsque les paramètres de conférence audio sont modifiés pour un utilisateur. Si vous n'attribuez pas d'abord la licence, MMS effectue une nouvelle mise à jour de toutes les réunions lorsque de l'attribution.
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a>Si vous utilisez actuellement un fournisseur de services d'audioconférence (ACP) tiers

Avec un tiers ACP, ou non MMS s’exécute dépend des paramètres de conférence audio de votre organisation. Vous pouvez choisir de remplacer automatiquement les numéros d’accès à distance à partir de votre ACP lorsque vous affectez un utilisateur, une licence **d’Audioconférence** . Toutefois, vous pouvez également choisir d'éviter un tel remplacement et de conserver les numéros de rendez-vous de votre ACP. Pour voir la définition de votre organisation, exécutez la commande Windows PowerShell suivante et vérifiez la valeur du paramètre `AutomaticallyReplaceAcpProvider`. Si vous avez besoin d'aide pour utiliser PowerShell, consultez la section [Utilisation de PowerShell pour gérer votre entreprise dans Skype Entreprise](setting-up-the-meeting-migration-service-mms.md#WPSInfo) à la fin de cet article.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- Si la valeur de ce paramètre est $true, MMS s’exécuter lorsqu’un utilisateur reçoit une licence **d’Audioconférence** et mise à jour de leurs réunions. Les numéros d’accès à distance à partir de votre ACP sont conservés jusqu'à ce que la licence **d’Audioconférence** est attribuée.
    
- Si la valeur de ce paramètre est $false, puis MMS ne mettre à jour les réunions même si un utilisateur possède une licence **d’Audioconférence** . Les numéros d’accès à distance à partir de votre ACP sont conservés jusqu'à ce que l’utilisateur est configuré manuellement pour la conférence audio dans Skype pour le centre d’administration commerciale ou à l’aide de Windows PowerShell.
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Mise à jour de réunions lors de la modifient des paramètres de conférence audio d’un utilisateur

MMS met à jour un Skype existant pour les réunions d’entreprise et Teams de Microsoft dans les cas suivants :
  
- Lorsque vous affectez ou supprimez des licences **d’Audioconférence** .
    
- Lorsque vous activez ou désactivez la fonction d’audioconférence.
    
- Lorsque vous modifiez ou réinitialisez l’ID de conférence pour un utilisateur configuré pour utiliser des réunions publiques.
    
- Lorsque vous déplacez l’utilisateur à un nouveau pont de conférence audio.
    
- Lorsqu’un numéro de téléphone est assigné à partir d’un pont de conférence audio. Il s'agit d'un scénario complexe qui nécessite des étapes supplémentaires. Pour plus d’informations, voir [Modifier le numéro ou les numéros gratuits sur le pont de conférence de données Audio](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).
    
> [!IMPORTANT]
> MMS effectue uniquement la mise à jour des réunions lorsque vous utilisez le pont Microsoft. Si vous utilisez un fournisseur de conférence audio de tiers, les utilisateurs doivent mettre à jour leurs réunions manuellement. Dans ce cas, vous pouvez utiliser l'[outil de migration de réunion](https://go.microsoft.com/fwlink/p/?linkid=626047). 
  
Toutes les modifications aux paramètres de conférence audio de l’utilisateur déclenchent MMS. Les deux modifications suivantes n'entraînent pas la mise à jour des réunions par MMS :
  
- la modification de l'adresse SIP de l'organisateur de la réunion (qu'il s'agisse de son nom d'utilisateur SIP ou son domaine SIP) ;
    
- la modification de l'URL de réunion de votre entreprise à l'aide de la commande [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).
    
## <a name="what-happens-when-mms-updates-meetings"></a>Que se passe-t-il lorsque MMS met à jour des réunions ?

Lorsque MMS détecte que les réunions d'un utilisateur doivent être mises à jour, le service effectue les actions suivantes :
  
1. Identifier tous les Skype pour les réunions d’entreprise et Teams de Microsoft l’utilisateur a été planifié à l’avenir
    
  - Tout Skype pour les réunions d’entreprise ou Teams de Microsoft qui s’est produite avant lors de l’exécution de MMS sont ignorés.
    
  - Il met à jour uniquement les réunions dont l'utilisateur est l'organisateur.
    
2. Il remplace le bloc d'informations de la réunion en ligne dans les détails de la réunion.
    
3. Il envoie des mises à jour à tous les destinataires de la réunion de la part de l'organisateur.
    
 **Combien de temps dure l'exécution de MMS ?**
  
La quantité de temps pour les services MMS migrer des réunions dépend de combien d’utilisateurs est concernés et le nombre total de Skype pour les réunions d’entreprise ou Teams de Microsoft que chaque utilisateur dispose sur leur calendrier. La migration dure au minimum 10 minutes. Bien que des migrations importantes puissent prendre jusqu'à 12 heures, la plupart sont effectuées en moins d'une heure.
  
 **Limites et problèmes potentiels**
  
- Uniquement le Skype pour les réunions d’entreprise ou Teams de Microsoft qui ont été planifiées en cliquant sur le bouton **Ajouter de Skype réunion** dans Outlook sur le Web ou en utilisant le complément de réunion de Skype pour Outlook sont migrées. En d'autres termes, si un utilisateur copie et colle les informations relatives à une réunion en ligne Skype dans une nouvelle réunion, cette nouvelle réunion n'est pas mise à jour.
    
- Lorsqu'une réunion est migrée, MMS remplace tous les éléments du bloc d'information de la réunion en ligne. Ainsi, si un utilisateur a modifié ce bloc, ses modifications sont écrasées. Le contenu indiqué dans les détails de la réunion et qui ne fait pas partie du bloc d'informations de la réunion en ligne n'est pas modifié.
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- Le contenu relatif à la réunion qui a été créé ou joint à la réunion (tableaux blancs, sondages, etc.) n'est pas conservé après l'exécution de MMS Si les organisateurs de votre réunion ont joint du contenu aux réunions à l'avance, ce contenu doit être recréé après l'exécution de MMS.
    
- Le lien vers les notes de réunion partagées dans l'élément du calendrier, ainsi que dans Skype, est également écrasé. Le contenu des notes de réunion enregistrées dans OneNote n'est pas supprimé : seul le lien vers les notes partagées est écrasé.
    
- Les réunions comptant plus de 250 participants (organisateur inclus) ne feront pas l'objet d'une migration.
    
- Certains caractères Unicode dans le corps de l'invitation peuvent être mis à jour de manière incorrecte et remplacés par l'un des caractères spéciaux suivants : ï, ¿, ½, �.
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a>Que voient les utilisateurs lorsque MMS met à jour leurs réunions ?

Tout comme l'outil de migration de réunion, MMS envoie des mises à jour de réunion à la place des utilisateurs. Vos utilisateurs ne verront ainsi qu'un nouveau cycle de notifications d'approbation pour leurs réunions. Cela peut être source de confusion pour les utilisateurs, nous vous recommandons d’avertir vos utilisateurs à l’avance non seulement lorsque vous les migrez depuis des locaux à Skype pour professionnels en ligne, mais également lorsque vous apportez des modifications de conférence audio qui déclenchera MMS.
  
## <a name="managing-mms"></a>Gestion de MMS

Vous devez utiliser Windows PowerShell pour gérer MMS et vérifier le statut des migrations en cours. Cette section suppose que vous maîtrisez suffisamment PowerSHell pour gérer votre entreprise dans Skype Entreprise. Si vous débutez sur PowerShell, consultez la section [Utilisation de PowerShell pour gérer votre entreprise dans Skype Entreprise](setting-up-the-meeting-migration-service-mms.md#WPSInfo) à la fin de cet article.
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a>Comment puis-je vérifier le statut des migrations de réunion ?

Utilisez l'applet de commande  `Get-CsMeetingMigrationStatus` pour vérifier le statut des migrations de réunion. Vous trouverez ci-dessous plusieurs exemples.
  
Pour obtenir un statut récapitulatif pour toutes les migrations MMS, exécutez la commande suivante :
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Cela vous permettra de bénéficier de la vue tabulaire suivante des états de toutes les migrations :
  
État UserCount---<br/> 21 en attente<br/>InProgress 6<br/> 2 a échoué <br/> 131 a réussi
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

MMS est activé par défaut pour toutes les organisations, mais peut être désactivé au besoin. Par exemple, si vous souhaitez faire migrer manuellement toutes les réunions ou si vous utilisez un fournisseur de conférence audio de tierce partie, vous peut-être pas MMS en cours d’exécution. Vous pouvez également choisir de désactiver MMS temporairement. Par exemple, vous pouvez le faire des modifications substantielles aux paramètres de conférence audio pour votre organisation que vous ne MMS à s’exécuter jusqu'à ce que toutes les modifications sont terminées.
  
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

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a>Activation et désactivation des services MMS uniquement pour les modifications d’audioconférence
<a name="Troubleshooting"> </a>

Vous pouvez également désactiver MMS uniquement pour les modifications de conférence audio. Il s’exécute lorsqu’un utilisateur migré à partir de Skype pour professionnels sur site à Skype pour l’activité en ligne. Pour vérifier l’état MMS en cours des mises à jour de la conférence audio, exécutez la commande suivante et vérifiez la valeur de la `AutomaticallyMigrateUserMeetings` paramètre. Si ce paramètre a la valeur true de $, MMS est définie pour mettre à jour des réunions de l’utilisateur lors de la modification des paramètres de conférence audio.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

Pour désactiver les services MMS pour la conférence audio, exécutez la commande suivante :
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

Pour activer les services MMS pour les conférences audio, exécutez la commande suivante :
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a>Comment puis-je exécuter manuellement une migration de réunion pour un utilisateur ?
<a name="Troubleshooting"> </a>

Outre les migrations automatiques de réunion, vous pouvez également exécuter la migration de la réunion manuellement pour un utilisateur en exécutant l’applet de commande **Start-CsExMeetingMigration**. Cette applet de commande ajoute l’utilisateur dans la file d’attente de la migration de la réunion. Service de Migration de réunion pour lire la demande de l’utilisateur et migrer leurs réunions. Vous pouvez vérifier l’état de la migration de la conférence à l’applet de commande **Get-CsMeetingMigrationStatus**.
  
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
Pour plus d'informations sur le démarrage de Windows PowerShell, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou[Connexion à Skype Entreprise Online à l'aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Rubriques connexes

[Configurer la conférence Audio pour Skype entreprise et Teams Microsoft](set-up-audio-conferencing.md)
