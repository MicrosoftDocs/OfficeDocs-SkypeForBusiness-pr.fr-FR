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
description: Meeting Migration Service (MMS) est un service Skype Entreprise qui s'exécute en arrière-plan et met automatiquement à jour les réunions Skype Entreprise et Microsoft Teams pour les utilisateurs. MMS est conçu pour que les utilisateurs n'aient plus besoin d'exécuter l'outil de migration des réunions pour mettre à jour leurs réunions Skype Entreprise et Microsoft Teams.
ms.openlocfilehash: 013e68ada16f15b3a410823680ec062b9fb7fa3a
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780500"
---
# <a name="setting-up-the-meeting-migration-service-mms"></a>Configuration de Meeting Migration Service (MMS)

Meeting Migration Service (MMS) est un service Skype Entreprise qui s'exécute en arrière-plan et met automatiquement à jour les réunions Skype Entreprise et Microsoft Teams pour les utilisateurs. MMS est conçu pour que les utilisateurs n'aient plus besoin d'exécuter l'outil de migration des réunions pour mettre à jour leurs réunions Skype Entreprise et Microsoft Teams.  Cet outil ne migre pas les réunions Skype Entreprise vers les réunions Microsoft Teams.  
  
 **Configuration requise**
  
Pour que MMS fonctionne, les boîtes aux lettres des organisateurs de réunion doivent être sur Exchange Online.
  
 **Principaux scénarios**
  
MMS met à jour les réunions Skype pour un utilisateur dans les deux principaux scénarios suivants :
  
- Lorsque l'utilisateur migre localement de Skype Entreprise Server vers Skype Entreprise Online.

    
- Lorsqu'un administrateur apporte une modification aux paramètres d'audioconférence de l'utilisateur qui nécessiterait la mise à jour des informations d'audioconférence dans les réunions de cet utilisateur.
    
 **Scénarios courants pour lesquels vous ne pouvez pas utiliser MMS**
  
Voici quelques scénarios courants qui peuvent s'appliquer. Tous ces scénarios prennent en charge la migration. Toutefois, MMS ne fonctionne pas pour ces scénarios ; vous devez utiliser [l'outil de migration de réunion](https://go.microsoft.com/fwlink/p/?linkid=626047).
  
- Les boîtes aux lettres de l'utilisateur se trouvent sur une version locale d'Exchange Server
    
- Utilisation d'un fournisseur d'audioconférence tiers
    
- Migration des utilisateurs de Skype Entreprise Online vers Skype Server local
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a>Mise à jour des réunions lorsqu'un utilisateur local est migré vers Skype Entreprise Online

C'est le scénario le plus courant dans lequel MMS peut aider à créer une transition plus fluide pour vos utilisateurs. Lorsqu'un utilisateur migre d'un Skype Entreprise Server local vers Skype Entreprise Online, MMS détectera le nouvel utilisateur et analysera le calendrier de cet utilisateur pour les réunions Skype Entreprise et Microsoft Teams. Toute réunion future sera mise à jour avec les nouvelles informations pour cet utilisateur.
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a>Si vous utilisez actuellement Skype Server 2015 pour l'audioconférence

Nous vous recommandons de suivre les meilleures pratiques ci-dessous pour la meilleure expérience avec MMS dans ce scénario :
  
- Puisque, pour que MMS fonctionne, la boîte aux lettres de l'utilisateur doit être sur Exchange Online, si vous effectuez une migration depuis Exchange Server sur site, déplacez d'abord la boîte aux lettres de l'utilisateur vers Exchange Online.
    
- Attribuez la licence d' **audioconférence** à l'utilisateur avant d'exécuter le `Move-CSUser` cmdlet pour effectuer une migration de l'utilisateur. En effet, MMS met également à jour les réunions lorsque les paramètres d'audioconférence sont modifiés pour un utilisateur. Si vous n'attribuez pas la licence en premier, MMS mettra à jour toutes les réunions à nouveau lorsque vous attribuerez la licence.
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a>Si vous utilisez actuellement un fournisseur de services d'audioconférence tiers (ACP)

Avec un ACP tiers, le fait que MMS s'exécute ou pas dépend des paramètres d'audioconférence de votre organisation. Vous pouvez choisir de remplacer automatiquement les numéros d'appel à partir de votre ACP, lorsque vous attribuez une licence d' **audioconférence** à un utilisateur. Toutefois, vous devrez peut-être empêcher que cela se produise et conserver les numéros, d'appel depuis votre ACP. Pour voir les paramètres de votre organisation, exécutez la commande Windows PowerShell suivante et vérifiez la valeur du paramètre `AutomaticallyReplaceAcpProvider`. Si vous avez besoin d'aide pour utiliser PowerShell, consultez la section [Utilisation de PowerShell pour gérer votre entreprise dans Skype Entreprise](setting-up-the-meeting-migration-service-mms.md#WPSInfo) à la fin de cet article.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- Si la valeur de ce paramètre est $true, alors MMS s'exécutera quand un utilisateur se verra attribuer une licence d' **audioconférence** et mettra à jour leurs réunions. Les numéros d'appel de votre ACP sont conservés jusqu'à l'attribution de la licence d' **audioconférence**.
    
- Si la valeur de ce paramètre est $false, alors MMS ne mettra pas à jour les réunions, même si un utilisateur se voit attribuer une licence **d'audioconférence** . Les numéros d'appel de votre ACP sont conservés, jusqu'à ce que l'utilisateur soit manuellement configuré pour l'audioconférence dans le centre d'administration Skype Entreprise ou en utilisant Windows PowerShell.
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Mise à jour des réunions lorsque les paramètres d'audioconférence d'un utilisateur changent

MMS mettra à jour les réunions existantes de Skype Entreprise et Microsoft Teams dans les cas suivants :

  
- Lorsque vous attribuez ou supprimez une licence d' **audioconférence** .
    
- Lorsque vous activez ou désactivez les services d’audioconférence.
    
- Lorsque vous modifiez ou réinitialisez l'ID de conférence pour un utilisateur configuré pour les réunions publiques.

    
- Lorsque vous déplacez l'utilisateur vers un nouveau pont d'audioconférence.
    
- Lorsqu'un numéro de cellulaire n'est pas attribué depuis un pont d'audioconférence. Il s'agit d'un scénario complexe qui nécessite des étapes supplémentaires. Pour en savoir plus, consultez la section [Modifiez les numéros payants ou les numéros gratuits sur votre pont d'audioconférence](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).
    
> [!IMPORTANT]
> MMS ne met à jour les réunions que lorsque vous utilisez le pont Microsoft. Si vous utilisez un fournisseur d'audioconférence tiers, les utilisateurs devront mettre à jour leurs réunions manuellement. Dans ce cas, vous pouvez utiliser l' [outil de migration des réunions](https://go.microsoft.com/fwlink/p/?linkid=626047). 
  
Seules certaines modifications des paramètres d'audioconférence d'un utilisateur déclenchent MMS. Plus précisément, les deux changements suivants n'entraîneront pas une mise à jour des réunions par MMS :
  
- la modification de l'adresse SIP de l'organisateur de la réunion (qu'il s'agisse de son nom d'utilisateur SIP ou son domaine SIP) ;
    
- la modification de l'URL de réunion de votre entreprise à l'aide de la commande [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).
    
## <a name="what-happens-when-mms-updates-meetings"></a>Que se passe-t-il lorsque MMS met à jour des réunions ?

Lorsque MMS détecte que la réunion d'un utilisateur doit être mise à jour, il effectue les opérations suivantes :
  
1. Identifier toutes les réunions Skype Entreprise et Microsoft Teams planifiées par l'utilisateur
    
  - Toutes les réunions Skype Entreprise ou Microsoft Teams qui ont eu lieu avant l'exécution de MMS sont ignorées

    
  - Seules les réunions où l'utilisateur est l'organisateur sont mises à jour

    
2. Il remplace le bloc d'informations de la réunion en ligne dans les détails de la réunion.
    
3. Il envoie des mises à jour à tous les destinataires de la réunion de la part de l'organisateur.
    
 **Combien de temps faut-il pour que MMS fonctionne ?**
  
Le temps nécessaire au MMS pour migrer des réunions varie en fonction du nombre d'utilisateurs impliqués et du nombre total de réunions Skype Entreprise ou Microsoft Teams que chaque utilisateur a dans son calendrier. Au minimum, il faudra 10 minutes pour que l'exécution ait lieu. Bien que des migrations importantes puissent prendre jusqu'à 12 heures, la plupart sont effectuées en moins d'une heure.
  
 **Limites et problèmes potentiels**
  
- Seules les réunions Skype Entreprise ou Microsoft Teams qui ont été planifiées en cliquant sur le bouton **Ajouter une réunion Skype** dans Outlook sur le Web ou en utilisant le module d'extension Skype Meeting pour Outlook sont migrées. En d'autres termes, si un utilisateur copie et colle les informations relatives à une réunion en ligne Skype dans une nouvelle réunion, cette nouvelle réunion n'est pas mise à jour.
    
- Lorsqu'une réunion est migrée, MMS remplace tous les éléments du bloc d'information de la réunion en ligne. Ainsi, si un utilisateur a modifié ce bloc, ses modifications sont écrasées. Le contenu indiqué dans les détails de la réunion et qui ne fait pas partie du bloc d'informations de la réunion en ligne n'est pas modifié.
    
     ![Le bloc de réunion mis à jour par MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- Le contenu relatif à la réunion qui a été créé ou joint à la réunion (tableaux blancs, sondages, etc.) n'est pas conservé après l'exécution de MMS Si les organisateurs de votre réunion ont joint du contenu aux réunions à l'avance, ce contenu doit être recréé après l'exécution de MMS.
    
- Le lien vers les notes de réunion partagées dans l'élément du calendrier, ainsi que dans Skype, est également écrasé. Le contenu des notes de réunion enregistrées dans OneNote n'est pas supprimé : seul le lien vers les notes partagées est écrasé.
    
- Les réunions comptant plus de 250 participants (organisateur inclus) ne feront pas l'objet d'une migration.
    
- Certains caractères Unicode dans le corps de l'invitation peuvent être mis à jour de manière incorrecte et remplacés par l'un des caractères spéciaux suivants : ï, ¿, ½, �.
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a>Que voient les utilisateurs lorsque MMS met à jour leurs réunions ?

Tout comme l'outil de migration de réunion, MMS envoie des mises à jour de réunion à la place des utilisateurs. Vos utilisateurs ne verront ainsi qu'un nouveau cycle de notifications d'approbation pour leurs réunions. Cela peut être déroutant pour les utilisateurs. Nous vous recommandons donc d'avertir vos utilisateurs à l'avance, non seulement lorsque vous migrez de vos locaux vers Skype Entreprise Online, mais aussi lorsque vous effectuez des changements d'audioconférence qui déclencheront MMS.
  
## <a name="managing-mms"></a>Gestion du MMS

Vous devez utiliser Windows PowerShell pour gérer MMS et vérifier le statut des migrations en cours. Les informations de cette section supposent que vous maîtrisez suffisamment PowerSHell pour gérer votre organisation Skype Entreprise. Si vous êtes nouveau dans PowerShell, consultez la section [Utilisation de PowerShell pour gérer votre organisation Skype Entreprise](setting-up-the-meeting-migration-service-mms.md#WPSInfo) à la fin de cet article.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a>Comment puis-je vérifier le statut des migrations de réunion ?

Utilisez l'applet de commande  `Get-CsMeetingMigrationStatus` pour vérifier le statut des migrations de réunion. Vous trouverez ci-dessous plusieurs exemples.
  
Pour obtenir un statut récapitulatif pour toutes les migrations MMS, exécutez la commande suivante :
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Cela vous permettra de bénéficier de la vue tabulaire suivante de tous les états de migration :
  
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

MMS est activé par défaut pour toutes les organisations, mais peut être désactivé au besoin. Par exemple, si vous souhaitez effectuer une migration, manuellement, de toutes les réunions ou si vous utilisez un fournisseur d'audioconférence tiers, il se peut que vous n'ayez pas besoin de MMS en cours d'exécution. Vous pouvez également choisir de désactiver MMS temporairement. Par exemple, vous pouvez apporter des modifications importantes aux paramètres d'audioconférence de votre organisation et vous ne voulez pas que MMS s'exécute tant que tous les changements ne sont pas terminés.
  
Pour voir si MMS est activé pour votre entreprise, exécutez la commande suivante et vérifier la valeur du paramètre  `MeetingMigrationEnabled`. Si le paramètre a pour valeur $true, MMS est activé.
  
```
Get-CsTenantMigrationConfiguration
```

Pour désactiver MMS, exécutez la commande suivante :
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

Pour activer MMS, exécutez la commande suivante :
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a>Activation et désactivation MMS uniquement pour les modifications de services d’audioconférence
<a name="Troubleshooting"> </a>

Vous pouvez également désactiver MMS uniquement pour les modifications de services d’audioconférence. Il continuera à s'exécuter lorsqu'un utilisateur est migré deSkype Entreprise local vers Skype Entreprise Online. Pour vérifier l'état actuel du MMS pour les mises à jour des audioconférences, exécutez la commande suivante et vérifiez la valeur du  `AutomaticallyMigrateUserMeetings` paramètre. Si ce paramètre est défini sur $true, MMS est configuré pour mettre à jour les réunions d'utilisateurs lorsque les paramètres d'audioconférence sont modifiés.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

Pour désactiver MMS pour les audioconférences, exécutez la commande suivante :
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

Pour activer MMS pour les audioconférences, exécutez la commande suivante :
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a>Comment puis-je exécuter manuellement une migration de réunion pour un utilisateur ?
<a name="Troubleshooting"> </a>

En plus des migrations automatiques de réunion, vous pouvez également exécuter manuellement la migration de réunion pour un utilisateur, en exécutant le cmdlet **Start-CsExMeetingMigration**. Ce cmdlet ajoute l'utilisateur dans la file d'attente de migration de réunion. Meeting Migration Service lira la demande de l'utilisateur et effectuera une migration de leurs réunions. Vous pouvez vérifier le statut de la migration des réunions par cmdlet **Get-CsMeetingMigrationStatus**.
  
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
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```
Pour plus d'informations sur le démarrage de Windows PowerShell, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou[Connexion à Skype Entreprise Online à l'aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Pourquoi vous devez utiliser Office 365 PowerShell
](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
