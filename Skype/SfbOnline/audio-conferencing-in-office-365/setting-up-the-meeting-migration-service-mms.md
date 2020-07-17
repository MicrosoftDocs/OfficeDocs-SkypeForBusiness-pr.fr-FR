---
title: Utiliser le service de migration de réunion (MMS)
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Le service de migration de réunion (MMS) est un service qui s’exécute en arrière-plan et qui met automatiquement à jour les réunions Skype entreprise et Microsoft teams pour les utilisateurs. MMS est conçu pour éviter aux utilisateurs d’exécuter l’outil de migration de réunion pour mettre à jour leurs réunions Skype entreprise et Microsoft Teams.
ms.openlocfilehash: da04e98269f20eca327b30c2bd40f3e5181523d0
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012180"
---
# <a name="using-the-meeting-migration-service-mms"></a>Utiliser le service de migration de réunion (MMS)

Le service de migration de réunion (MMS) est un service qui met à jour les réunions existantes d’un utilisateur dans les cas suivants :

- Lorsqu’un utilisateur effectue une migration de local vers le Cloud (que ce soit à Skype entreprise Online ou à TeamsOnly).
- Lorsqu’un administrateur modifie les paramètres de l’audioconférence de l’utilisateur 
- Lorsqu’un utilisateur en ligne est mis à niveau vers les équipes uniquement, ou lorsque le mode de l’utilisateur dans TeamsUpgradePolicy est défini sur SfBwithTeamsCollabAndMeetings
- Lorsque vous utilisez PowerShell 


Par défaut, l’application MMS est automatiquement déclenchée dans chacun de ces cas, même si les administrateurs peuvent la désactiver au niveau du client. De plus, les administrateurs peuvent utiliser une applet de passe PowerShell pour déclencher manuellement la migration de réunion pour un utilisateur donné.


**Limitations**: le service de migration de réunion ne peut pas être utilisé si l’une des conditions suivantes s’applique :

- La boîte aux lettres de l’utilisateur est hébergée dans Exchange sur site.
- L’utilisateur est en cours de migration du Cloud vers Skype entreprise Server en local.

Dans ces situations, les utilisateurs finaux peuvent utiliser l' [outil de migration de réunion](https://www.microsoft.com/download/details.aspx?id=51659) pour migrer leurs propres réunions à la place.

## <a name="how-mms-works"></a>Fonctionnement de MMS

Lorsque le MMS est déclenché pour un utilisateur donné, une demande de migration pour cet utilisateur est placée dans une file d’attente. Pour éviter toute condition de concurrence, la demande en file d’attente n’est pas transmise en attente tant que au moins 90 minutes n’ont pas été effectuées. Lorsque MMS traite la requête, il effectue les tâches suivantes :

1. Il recherche dans la boîte aux lettres de l’utilisateur toutes les réunions existantes organisées par cet utilisateur et programmées dans le futur.
2. D’après les informations figurant dans la boîte aux lettres de l’utilisateur, il met à jour ou planifie de nouvelles réunions dans teams ou Skype entreprise Online pour cet utilisateur, en fonction du scénario exact.
3. Dans le message électronique, il remplace le bloc de réunion en ligne dans les détails de la réunion.
4. Il envoie la version mise à jour de la réunion à tous les destinataires de la réunion de la part de l’organisateur de la réunion. Les invités à une réunion recevront une mise à jour de la réunion avec les coordonnées de réunion mises à jour dans leur courrier. 

    ![Le bloc de réunion mis à jour par MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

À partir du moment où le service MMS est déclenché, il faut généralement 2 heures avant la migration des réunions de l’utilisateur. Toutefois, si l’utilisateur a un grand nombre de réunions, cela peut prendre plus de temps. Si MMS rencontre une erreur lors de la migration d’une ou plusieurs réunions pour l’utilisateur, celui-ci réapparaîtra périodiquement à 9 reprises sur une durée de 24 heures.

**Remarques**:

- Lorsqu'une réunion est migrée, MMS remplace tous les éléments du bloc d'information de la réunion en ligne. Ainsi, si un utilisateur a modifié ce bloc, ses modifications sont écrasées. Le contenu indiqué dans les détails de la réunion et qui ne fait pas partie du bloc d'informations de la réunion en ligne n'est pas modifié. Cela signifie que tous les fichiers joints à l’invitation à la réunion seront toujours inclus. 
- Seules les réunions Skype entreprise ou Microsoft teams planifiées en cliquant sur le bouton **Ajouter une réunion Skype** dans Outlook sur le Web ou à l’aide du complément réunion Skype pour Outlook sont déplacées. Si un utilisateur copie et colle les informations relatives à la réunion en ligne Skype d’une réunion dans une nouvelle réunion, cette nouvelle réunion ne sera pas mise à jour dans la mesure où il n’y a aucune réunion dans le service d’origine.
- Le contenu de la réunion créé ou joint à la réunion (tableaux blancs, sondages, etc.) n’est pas conservé après l’exécution de MMS. Si les organisateurs de votre réunion ont joint du contenu aux réunions à l’avance, le contenu devra être recréé après exécution de MMS.
- Le lien vers les notes de réunion partagées dans l'élément du calendrier, ainsi que dans Skype, est également écrasé. Notez que les notes de réunion réelles stockées dans OneNote resteront là ; Il s’agit uniquement du lien vers les notes partagées qui sont écrasées.
- Les réunions comptant plus de 250 participants (organisateur inclus) ne feront pas l'objet d'une migration.
- Certains caractères UNICODE dans le corps de l’invitation peuvent être mis à jour de manière incorrecte dans l’un des caractères spéciaux suivants : ï, ¿, 1/2,.

## <a name="triggering-mms-for-a-user"></a>Déclenchement de MMS pour un utilisateur

Cette section décrit ce qui se produit lorsque MMS est déclenché dans les cas suivants :

- Lorsqu’un utilisateur effectue une migration de local vers le Cloud
- Lorsqu’un administrateur modifie les paramètres de l’audioconférence de l’utilisateur 
- Lorsque le mode de l’utilisateur dans TeamsUpgradePolicy est défini sur TeamsOnly ou SfBWithTeamsCollabAndMeetings (à l’aide de PowerShell ou du portail d’administration Teams)
- Lorsque vous utilisez l’applet de cmdlet PowerShell, démarrez-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Mise à jour des réunions lorsque vous déplacez un utilisateur sur site vers le Cloud

C’est le scénario le plus courant dans lequel MMS contribue à faciliter la transition de vos utilisateurs. Sans migration de réunion, les réunions existantes organisées par un utilisateur dans Skype entreprise Server locales ne fonctionneront plus une fois que l’utilisateur est déplacé en ligne. Par conséquent, lorsque vous utilisez les outils d’administration locaux ( `Move-CsUser` ou le panneau de configuration d’administration) pour déplacer un utilisateur vers le Cloud, les réunions existantes sont automatiquement déplacées vers le cloud comme suit :

- Si l' `MoveToTeams` option basculer `Move-CsUser` est spécifiée, les réunions sont déplacées directement vers équipes et l’utilisateur est en mode TeamsOnly. L’utilisation de ce commutateur nécessite Skype entreprise Server 2015 avec CU8 ou une version ultérieure. Ces utilisateurs peuvent tout de même participer à une réunion Skype entreprise à laquelle ils peuvent être invités, à l’aide du client Skype entreprise ou de l’application de réunion Skype.
- Dans le cas contraire, les réunions sont migrées dans Skype entreprise online.

Dans les deux cas, si une licence d’audioconférence a été affectée à l’utilisateur avant d’être déplacé vers le Cloud, les réunions seront créées avec des coordonnées de connexion. Si vous déplacez un utilisateur de local vers le Cloud et que vous prévoyez de l’utiliser pour l’audioconférence, nous vous conseillons d’affecter tout d’abord la conférence audio avant de déplacer l’utilisateur afin qu’une seule migration de réunion soit déclenchée.


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Mise à jour des réunions lorsque les paramètres de conférence audio d’un utilisateur sont modifiés

Dans les cas suivants, MMS met à jour les réunions Skype entreprise et Microsoft teams existantes pour ajouter, supprimer ou modifier des coordonnées de numérotation :

- Lorsque vous attribuez ou supprimez une licence de service de conférence rendez-vous Microsoft à un utilisateur, et qu’il n’est pas activé pour un fournisseur de services d’audioconférence tiers.
- Lorsque vous modifiez le fournisseur de services d’audioconférence d’un utilisateur de n’importe quel autre fournisseur en Microsoft, à condition que l’utilisateur dispose d’une licence Microsoft audio Conferencing. Pour plus d’informations, voir [affecter Microsoft en tant que fournisseur](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)de services d’audioconférence. Notez également que la prise en charge des fournisseurs de services d’audioconférence tiers [ACP] est planifiée pour la fin de vie du 1er avril 2019, comme [précédemment annoncé](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers).
- Lorsque vous activez ou désactivez les conférences audio pour un utilisateur.
- Lorsque vous modifiez ou réinitialisez l’ID de conférence d’un utilisateur configuré pour utiliser les réunions publiques.
- Lorsque vous déplacez l’utilisateur vers un nouveau pont de conférence audio.
- Lorsque le numéro de téléphone d’un pont de conférence audio n’est pas affecté. Il s’agit d’un scénario complexe qui nécessite des étapes supplémentaires. Pour plus d’informations, reportez-vous à [la rubrique Modification des numéros de téléphone de votre pont de conférence audio](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

Les modifications apportées aux paramètres de conférence audio d’un utilisateur ne déclenchent pas les MMS. Les deux modifications suivantes n'entraînent pas la mise à jour des réunions par MMS :

- la modification de l'adresse SIP de l'organisateur de la réunion (qu'il s'agisse de son nom d'utilisateur SIP ou son domaine SIP) ;
- Lorsque vous modifiez l’URL de la réunion de votre organisation à l’aide de la `Update-CsTenantMeetingUrl` commande.


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Mise à jour des réunions lors de l’attribution de TeamsUpgradePolicy

Par défaut, la migration de réunion est automatiquement déclenchée lorsque l’utilisateur dispose d’une instance de `TeamsUpgradePolicy` `mode=TeamsOnly` ou `mode= SfBWithTeamsCollabAndMeetings` . Si vous ne souhaitez pas migrer des réunions lorsque vous accordez l’un de ces modes, spécifiez `MigrateMeetingsToTeams $false` dans `Grant-CsTeamsUpgradePolicy` (si vous utilisez PowerShell) ou décochez la case migration des réunions lorsque vous définissez le mode de coexistence d’un utilisateur (si vous utilisez le portail d’administration Teams).

Notez également ce qui suit :

- La migration de réunion est appelée uniquement lorsque vous attribuez `TeamsUpgradePolicy` un utilisateur spécifique. Si vous accordez `TeamsUpgradePolicy` une autorisation par le biais de `mode=TeamsOnly` ou `mode=SfBWithTeamsCollabAndMeetings` sur un *client* , la migration de la réunion n’est pas appelée.
- Un utilisateur ne peut bénéficier du mode TeamsOnly que si l’utilisateur est connecté en ligne. Les utilisateurs hébergés sur site doivent être déplacés à l’aide `Move-CsUser` de la procédure décrite précédemment.
- L’attribution d’un mode autre que TeamsOnly ou SfBWithTeamsCollabAndMeetings ne permet pas de convertir des réunions d’équipes existantes en réunions Skype entreprise.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Déclenchez une migration de réunion manuellement via une cmdlet PowerShell

Outre la migration automatique de réunion, les administrateurs peuvent déclencher manuellement la migration de réunion pour un utilisateur en exécutant l’applet de cmdlet `Start-CsExMeetingMigration` . Cette applet de requête met en file d’attente une demande de migration pour l’utilisateur spécifié.  Outre le paramètre required `Identity` , il accepte deux paramètres facultatifs `SourceMeetingType` et `TargetMeetingType` vous permet de spécifier la migration des réunions :

**TargetMeetingType:**

- L’utilisation `TargetMeetingType Current` permet de spécifier que les réunions Skype entreprise restent des réunions Skype entreprise et des réunions en équipe. Néanmoins, les coordonnées de l’audioconférence peuvent être modifiées, et toutes les réunions Skype entreprise locales seront migrées vers Skype entreprise online. Il s’agit de la valeur par défaut de TargetMeetingType.
- L’utilisation `TargetMeetingType Teams` spécifie que toute réunion existante doit être déplacée vers Teams, que la réunion soit hébergée dans Skype entreprise Online ou en local, et indépendamment de la nécessité ou non des mises à jour de l’audioconférence. 

**SourceMeetingType:**
- Utilisation `SourceMeetingType SfB` indique que seules les réunions Skype entreprise (locales ou en ligne) doivent être mises à jour.
- L’utilisation `SourceMeetingType Teams` indique que seules les réunions d’équipes doivent être mises à jour.
- `SourceMeetingType All`Ce qui signifie que les réunions Skype entreprise et équipes doivent être mises à jour. Il s’agit de la valeur par défaut de SourceMeetingType.
    

L’exemple ci-dessous montre comment lancer la migration de réunion pour les utilisateurs de ashaw@contoso.com de sorte que toutes les réunions soient déplacées vers teams :

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>Gestion de MMS

À l’aide de Windows PowerShell, vous pouvez vérifier l’état de migrations en cours, déclencher manuellement la migration de réunion et désactiver entièrement la migration. 

### <a name="check-the-status-of-meeting-migrations"></a>Vérifier l’état des migrations de réunion

Vous pouvez utiliser l' `Get-CsMeetingMigrationStatus` applet de contrôle pour vérifier l’état des migrations de réunion. Vous trouverez ci-dessous plusieurs exemples.

- Pour obtenir une synthèse de l’état de toutes les migrations MMS, exécutez la commande suivante qui fournit une vue tabulaire de tous les États de migration :

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- Pour obtenir des informations complètes sur toutes les migrations au cours d’une période donnée, utilisez les `StartTime` `EndTime` paramètres et. Par exemple, la commande suivante renverra des informations complètes sur toutes les migrations effectuées du 1er octobre 2018 au 8 octobre 2018.

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- Pour vérifier l’état de la migration pour un utilisateur spécifique, utilisez le `Identity` paramètre. Ainsi, la commande suivante permet d'obtenir le statut de l'utilisateur ashaw@contoso.com :

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
Si vous voyez une migration en échec, prenez les mesures nécessaires pour résoudre ces problèmes le plus rapidement possible, car les utilisateurs ne seront pas en mesure de se connecter aux réunions organisées par ces utilisateurs tant que vous ne les aurez pas résolues. Si `Get-CsMeetingMigrationStatus` une migration a été effectuée en état d’échec, procédez comme suit :
 
1. Identifiez les utilisateurs concernés. Exécutez la commande suivante pour obtenir la liste des utilisateurs concernés, ainsi que l'erreur spécifique signalée :

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. Pour chaque utilisateur concerné, exécutez l’outil de migration de réunion pour migrer manuellement leurs réunions.

3. Si la migration ne fonctionne toujours pas avec l'outil de migration de réunions, vous disposez de deux options :

    - demander aux utilisateurs de créer de nouvelles réunions Skype ;
    - [contacter le support technique](https://go.microsoft.com/fwlink/p/?LinkID=518322).


### <a name="enabling-and-disabling-mms"></a>Activation et désactivation de MMS

La messagerie MMS est activée par défaut pour toutes les organisations, mais elle peut être désactivée comme suit :

- Désactiver entièrement pour le client. 
- Désactiver uniquement pour les modifications relatives aux conférences audio. Le cas échéant, MMS s’exécute quand un utilisateur est déplacé de local vers le Cloud ou lorsque vous accordez le mode TeamsOnly ou SfBWithTeamsCollabAndMeetings le mode `TeamsUpgradePolicy` .

Par exemple, vous souhaiterez peut-être migrer manuellement toutes les réunions ou désactiver temporairement MMS tout en apportant des modifications importantes aux paramètres de conférence audio de votre organisation.

Pour savoir si le MMS est activé pour votre organisation, exécutez la commande suivante. MMS est activé si le `MeetingMigrationEnabled` paramètre est `$true` .
```PowerShell
Get-CsTenantMigrationConfiguration
```
Pour activer ou désactiver entièrement MMS, utilisez la `Set-CsTenantMigrationConfiguration` commande. Par exemple, pour désactiver MMS, exécutez la commande suivante :

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
Si MMS est activé au sein de l’organisation et que vous voulez vérifier qu’il est activé pour les mises à jour de l’audioconférence, vérifiez la valeur du `AutomaticallyMigrateUserMeetings` paramètre dans le champ sortie de `Get-CsOnlineDialInConferencingTenantSettings` . Pour activer ou désactiver MMS pour les conférences audio, utilisez `Set-CsOnlineDialInConferencingTenantSettings` . Par exemple, pour désactiver MMS pour les conférences audio, exécutez la commande suivante :

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Sujets associés

[Essayez ou achetez une audioconférence dans Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Déplacer des utilisateurs entre l’environnement local et le cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
