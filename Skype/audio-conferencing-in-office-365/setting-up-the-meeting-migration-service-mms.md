---
title: "Configuration de Meeting Migration Service (MMS)"
ms.author: tonysmit
author: tonysmit
ms.date: 9/25/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
description: "Service de Migration (MMS) de la réunion est un Skype pour le service Business qui s'exécute en arrière-plan et met automatiquement à jour Skype pour les réunions d'entreprise et Teams de Microsoft pour les utilisateurs. MMS est conçu pour éliminer le besoin pour les utilisateurs d'exécuter l'outil de Migration de réunion pour mettre à jour leur Skype pour les réunions d'entreprise et Teams de Microsoft."
---

# Configuration de Meeting Migration Service (MMS)

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Service de Migration (MMS) de la réunion est un Skype pour le service Business qui s'exécute en arrière-plan et met automatiquement à jour Skype pour les réunions d'entreprise et Teams de Microsoft pour les utilisateurs. MMS est conçu pour éliminer le besoin pour les utilisateurs d'exécuter l'outil de Migration de réunion pour mettre à jour leur Skype pour les réunions d'entreprise et Teams de Microsoft.
  
 **Configuration requise**
  
Pour que MMS fonctionne, les boîtes aux lettres des organisateurs de réunion doivent être sur Exchange Online.
  
 **Principaux scénarios**
  
MMS met à jour les réunions Skype d'un utilisateur pour les deux situations suivants : 
  
- Lorsque l'utilisateur migré à partir de locaux Skype entreprise Server pour Skype entreprise Online.
    
- Lorsqu'un administrateur apporte une modification à des paramètres de conférence audio de l'utilisateur qui requièrent mise à jour les informations de services d'audioconférence dans les réunions de cet utilisateur.
    
 **Scénarios courants pour lesquels vous ne pouvez pas utiliser MMS**
  
Voici quelques scénarios courants qui peuvent s'appliquer. Tous ces scénarios prennent en charge la migration. Toutefois, MMS ne fonctionne pas pour ces scénarios ; vous devez utiliser [l'outil de migration de réunion](https://go.microsoft.com/fwlink/p/?linkid=626047).
  
- L'emplacement des boîtes aux lettres de l'utilisateur se trouve sur une version locale de Exchange Server
    
- Utilisation d'un fournisseur de services d'audioconférence tiers
    
- Migration des utilisateurs de Skype entreprise Online au serveur de Skype en local
    
## Mise à jour des réunions lorsqu'un utilisateur sur site est migré vers Skype Entreprise Online

Il s'agit du scénario le plus courant où MMS peut vous aider à créer une transition plus fluide pour vos utilisateurs. Lorsqu'un utilisateur est migré à partir d'un Skype en local pour Business Server pour Skype entreprise Online, MMS détecte le nouvel utilisateur et analysera calendrier de cet utilisateur de Skype pour les réunions d'entreprise et Teams de Microsoft. Toutes les réunions futures seront mise à jour avec les nouvelles informations pour cet utilisateur.
  
### Si vous utilisez actuellement Skype Server 2015 pour les conférences audio

Nous vous recommandons de suivre les meilleures pratiques suivantes afin d'exploiter pleinement MMS pour ce scénario :
  
- Puisque, pour que MMS fonctionne, la boîte aux lettres de l'utilisateur doit être sur Exchange Online, si vous effectuez une migration depuis Exchange Server sur site, déplacez d'abord la boîte aux lettres de l'utilisateur vers Exchange Online.
    
- Attribuer la licence de **Conférence Audio** à l'utilisateur avant d'exécuter l'applet de commande `Move-CSUser` pour déplacer l'utilisateur. C'est parce que MMS met également à jour réunions lorsque les paramètres de conférence audio sont modifiées pour un utilisateur. Si vous n'affectez la licence tout d'abord, MMS met à jour toutes les réunions à nouveau lorsque vous affectez la licence.
    
### Si vous utilisez actuellement un fournisseur de services d'audioconférence (ACP) tiers

Avec un fournisseur tiers, ou non MMS s'exécute dépend de paramètres de conférence audio de votre organisation. Vous pouvez choisir de remplacer automatiquement les numéros de connexion à partir de votre fournisseur lorsque vous attribuez une licence de **Conférence Audio** à un utilisateur. En revanche, vous devrez peut-être empêcher que cela se produise, mais de conserver les numéros de connexion à partir de votre fournisseur. Pour afficher le paramètre de votre organisation, exécutez la commande Windows PowerShell suivante et vérifiez la valeur du paramètre `AutomaticallyReplaceAcpProvider`. Si vous avez besoin d'aide de PowerShell, consultez la section [Utilisation de PowerShell pour gérer votre entreprise dans Skype Entreprise](031f09c0-9d2a-487a-b6db-b5d4bed6d16a.md#WPSInfo) à la fin de cet article.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- Si la valeur de ce paramètre est $true, MMS exécuter lorsqu'un utilisateur reçoit une licence de **Conférence Audio** et mettre à jour des réunions. Les numéros de connexion à partir de votre ACP sont conservés jusqu'à ce que la licence de **Conférence Audio** est affectée.
    
- Si la valeur de ce paramètre est $false, puis MMS ne mettez à jour les réunions même si un utilisateur reçoit une licence de **Conférence Audio**. Les numéros de connexion à partir de votre ACP sont conservés jusqu'à ce que l'utilisateur est configuré manuellement pour les conférences audio dans Skype pour le centre d'administration entreprise ou à l'aide de Windows PowerShell.
    
## Mettre à jour des réunions quand modifient les paramètres de conférence audio d'un utilisateur

MMS met à jour un Skype existant pour les réunions d'entreprise et Teams Microsoft dans les cas suivants :
  
- Lorsque vous affectez ou supprimez la licence de **Conférence Audio**.
    
- Lorsque vous activez ou désactivez les services d'audioconférence.
    
- Lorsque vous modifiez ou réinitialisez l'ID de conférence pour un utilisateur configuré pour utiliser les réunions publiques.
    
- Lorsque vous déplacez l'utilisateur vers un nouveau pont de conférence audio.
    
- Quand un numéro de téléphone est assigné à partir d'un pont de conférence audio. Il s'agit d'un scénario complexe qui nécessite des étapes supplémentaires. Pour plus d'informations, voir [Modifier le numéro payant ou numéros gratuits sur le pont de conférence Audio](change-the-toll-or-toll-free-numbers-on-your-audio-conferencing-bridge.md).
    
> [!IMPORTANT]
> MMS met à jour uniquement les réunions lorsque vous utilisez le pont Microsoft. Si vous utilisez un fournisseur de services d'audioconférence tiers, les utilisateurs doivent mettre à jour des réunions manuellement. Dans ce cas, vous pouvez utiliser l' [Outil de Migration de réunion](https://go.microsoft.com/fwlink/p/?linkid=626047). 
  
Pas toutes les modifications apportées aux paramètres de conférence audio d'un utilisateur déclenchent MMS. Plus précisément, les deux modifications suivantes ne provoquer MMS mise à jour des réunions :
  
- la modification de l'adresse SIP de l'organisateur de la réunion (qu'il s'agisse de son nom d'utilisateur SIP ou son domaine SIP) ;
    
- la modification de l'URL de réunion de votre entreprise à l'aide de la commande [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).
    
## Que se passe-t-il lorsque MMS met à jour des réunions ?

Lorsque MMS détecte que les réunions d'un utilisateur doivent être mises à jour, le service effectue les actions suivantes :
  
1. Identifier tous les Skype pour les réunions d'entreprise et Microsoft Teams l'utilisateur a planifié à l'avenir
    
  - N'importe quel Skype pour les réunions d'entreprise ou Microsoft Teams qui se sont produites avant lors de l'exécution MMS sont ignorés
    
  - Il met à jour uniquement les réunions dont l'utilisateur est l'organisateur.
    
2. Il remplace le bloc d'informations de la réunion en ligne dans les détails de la réunion.
    
3. Il envoie des mises à jour à tous les destinataires de la réunion de la part de l'organisateur.
    
 **Combien de temps dure l'exécution de MMS ?**
  
L'intervalle de temps faut-il pour MMS migrer des réunions varie selon le nombre d'utilisateurs est affecté et le nombre total de Skype entreprise ou Microsoft Teams réunions que chaque utilisateur possède à son calendrier. Au minimum, vous devrez patienter 10 minutes pour s'exécuter. Pendant que certains migrations volumineuses peuvent prendre jusqu'à 12 heures, la plupart des migrations doit se terminer dans l'heure.
  
 **Limites et problèmes potentiels**
  
- Uniquement la Skype pour les réunions d'entreprise ou Microsoft Teams qui ont été planifiée en cliquant sur le bouton **Ajouter Skype meeting** dans Outlook sur le Web ou à l'aide du complément réunion Skype pour Outlook sont migrés. En d'autres termes, si un utilisateur copie et colle les informations de réunion en ligne Skype à partir d'une réunion à une nouvelle réunion, cette nouvelle réunion ne sont pas actualisée.
    
- Lorsqu'une réunion est migrée, MMS remplace tous les éléments du bloc d'information de la réunion en ligne. Ainsi, si un utilisateur a modifié ce bloc, ses modifications sont écrasées. Le contenu indiqué dans les détails de la réunion et qui ne fait pas partie du bloc d'informations de la réunion en ligne n'est pas modifié. 
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- Le contenu relatif à la réunion qui a été créé ou joint à la réunion (tableaux blancs, sondages, etc.) n'est pas conservé après l'exécution de MMS Si les organisateurs de votre réunion ont joint du contenu aux réunions à l'avance, ce contenu doit être recréé après l'exécution de MMS.
    
- Le lien vers les notes de réunion partagées dans l'élément du calendrier, ainsi que dans Skype, est également écrasé. Le contenu des notes de réunion enregistrées dans OneNote n'est pas supprimé : seul le lien vers les notes partagées est écrasé.
    
- Les réunions comptant plus de 250 participants (organisateur inclus) ne feront pas l'objet d'une migration. 
    
- Certains caractères Unicode dans le corps de l'invitation peuvent être mis à jour de manière incorrecte et remplacés par l'un des caractères spéciaux suivants : ï, ¿, ½, �.
    
### Que voient les utilisateurs lorsque MMS met à jour leurs réunions ?

Comme l'outil de Migration de réunion, MMS envoie des mises à jour de réunion au nom d'utilisateurs. Par conséquent, la seule chose que vos utilisateurs verront est une autre série de notifications d'acceptation pour des réunions de la réunion. Cela peut prêter à confusion pour les utilisateurs, nous vous recommandons d'informer vos utilisateurs à l'avance pas uniquement lorsque vous migrez les locaux pour Skype entreprise Online, mais également lorsque vous apportez des modifications de services d'audioconférence qui se déclenche MMS.
  
## Gestion de MMS

Vous devez utiliser Windows PowerShell pour gérer MMS et vérifier le statut des migrations en cours. Cette section suppose que vous maîtrisez suffisamment PowerSHell pour gérer votre entreprise dans Skype Entreprise. Si vous débutez sur PowerShell, consultez la section [Utilisation de PowerShell pour gérer votre entreprise dans Skype Entreprise](031f09c0-9d2a-487a-b6db-b5d4bed6d16a.md#WPSInfo) à la fin de cet article.
  
### Comment puis-je vérifier le statut des migrations de réunion ?

Utilisez l'applet de commande  `Get-CsMeetingMigrationStatus` pour vérifier le statut des migrations de réunion. Vous trouverez ci-dessous plusieurs exemples.
  
Pour obtenir un statut récapitulatif pour toutes les migrations MMS, exécutez la commande suivante :
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

Cela vous permettra de bénéficier de la vue tabulaire suivante des états de toutes les migrations :
  
État Nombre d'utilisateurs----- ---------EnAttente 21EnCours 6Échoué 2Réussie 131
> [!IMPORTANT]
> Si certaines des migrations ont le statut Échoué, agissez de façon à résoudre ces problèmes le plus tôt possible. Il est impossible de participer aux réunions organisées par ces utilisateurs tant que ces problèmes ne sont pas résolus. Consultez la section [Que faire en cas d'erreur ?](031f09c0-9d2a-487a-b6db-b5d4bed6d16a.md#Troubleshooting) pour en savoir plus.
  
Pour obtenir les détails complets de toutes les migrations d'une période précise, vous pouvez utiliser les paramètres  `StartTime` et `EndTime`. Par exemple, la commande suivante permet d'obtenir les détails complets de toutes les migrations qui ont eu lieu du 1er au 8 octobre 2016.
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

Vous pouvez également vérifier le statut de migration d'un utilisateur particulier, en utilisant le paramètre  `UserId`. Ainsi, la commande suivante permet d'obtenir le statut de l'utilisateur ashaw@contoso.com :
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### Que faire en cas d'erreur ?
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
    
### Activation et désactivation de MMS
<a name="Troubleshooting"> </a>

MMS est activée par défaut pour toutes les organisations, mais elle peut être désactivée selon vos besoins. Par exemple, si vous voulez migrer manuellement toutes les réunions ou si vous utilisez un fournisseur de services d'audioconférence tiers, vous devrez pas MMS en cours d'exécution. Vous pouvez également choisir de désactiver temporairement MMS. Par exemple, vous pouvez le faire des modifications substantielles aux paramètres de services d'audioconférence pour votre organisation et vous ne voulez pas MMS exécute jusqu'à ce que toutes les modifications sont terminées.
  
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

### Activation et désactivation des MMS uniquement pour les modifications de services d'audioconférence
<a name="Troubleshooting"> </a>

Vous pouvez également désactiver MMS uniquement pour les modifications de services d'audioconférence. Il s'exécute lorsqu'un utilisateur est migré à partir de Skype pour entreprise local vers Skype entreprise Online. Pour vérifier l'état actuel MMS les mises à jour de services d'audioconférence, exécutez la commande suivante et vérifiez la valeur du paramètre  `AutomaticallyMigrateUserMeetings` . Si ce paramètre est défini sur$true, MMS est défini pour mettre à jour des réunions utilisateur lors de la modification des paramètres de conférence audio.
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

Pour désactiver MMS pour les services d'audioconférence, exécutez la commande suivante :
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

Pour activer MMS pour les services d'audioconférence, exécutez la commande suivante :
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### Comment puis-je exécuter manuellement une migration de réunion pour un utilisateur ?
<a name="Troubleshooting"> </a>

Outre les migrations automatiques de réunion, vous pouvez également exécuter la migration de réunion manuellement pour un utilisateur en exécutant l' applet de commande **Start-CsExMeetingMigration**. Cette applet de commande ajoute l'utilisateur dans la file d'attente de migration de réunion. Service de Migration de réunion pour lire la demande utilisateur et migrer des réunions. Vous pouvez vérifier l'état de la migration de la conférence à l' applet de commande **Get-CsMeetingMigrationStatus**.
  
Voici un exemple qui déclenche la migration de réunion pour l'utilisateur ashaw@contoso.com :
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## Utilisation de PowerShell pour gérer votre entreprise dans Skype Entreprise
<a name="WPSInfo"> </a>

 **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
  
1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
    
2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
    
3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.
    
4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
  
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
  

