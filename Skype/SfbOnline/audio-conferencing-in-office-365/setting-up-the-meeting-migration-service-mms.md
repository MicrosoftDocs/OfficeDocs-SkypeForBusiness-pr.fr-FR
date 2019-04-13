---
title: Utilisation du Service de Migration de réunion (MMS)
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
description: Réunion Migration MMS (Service) est un service qui s’exécute en arrière-plan et met à jour automatiquement Skype pour les réunions d’entreprise et Teams Microsoft pour les utilisateurs. MMS est conçu pour éliminer le besoin pour les utilisateurs d’exécuter l’outil de Migration de réunion pour mettre à jour leur Skype pour les réunions d’entreprise et Teams Microsoft.
ms.openlocfilehash: 90953f1352f54a8411513a78ccfda8bfb5356883
ms.sourcegitcommit: 004d9475aa704779f8f70adeaf2db9b36c6828cc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/12/2019
ms.locfileid: "31836855"
---
# <a name="using-the-meeting-migration-service-mms"></a>Utilisation du Service de Migration de réunion (MMS)

Le Service de Migration de réunion (MMS) est un service qui met à jour des réunions existantes d’un utilisateur dans les scénarios suivants :

- Lorsqu’un utilisateur est migré local vers le nuage (s’il faut Skype pour Business Online ou TeamsOnly).
- Lorsqu’un administrateur modifie les paramètres de conférence audio de l’utilisateur 
- Lorsqu’un utilisateur en ligne est mise à niveau pour les équipes uniquement, ou lorsque le mode d’un utilisateur dans TeamsUpgradePolicy est défini sur SfBwithTeamsCollabAndMeetings (appuyez sur clients uniquement)
- Lorsque vous utilisez PowerShell 


Par défaut, MMS est automatiquement déclenché dans chacun de ces cas, bien que les administrateurs peuvent désactiver au niveau du client. En outre, les administrateurs peuvent utiliser une applet de commande PowerShell pour déclencher manuellement la migration de réunion pour un utilisateur donné.

> [!NOTE]
> La possibilité de convertir Skype pour les réunions d’entreprise à des réunions d’équipes et la possibilité de mettre à jour des réunions d’équipes existantes pour modifier les paramètres de conférence audio est actuellement limitée aux clients TAP uniquement. Microsoft prévoit doter cette fonctionnalité à tous les clients dans mai 2019.

**Limitations**: la réunion service de migration ne peut pas être utilisé si une des conditions suivantes est remplie :

- Boîte aux lettres de l’utilisateur est hébergé dans Exchange sur site.
- L’utilisateur est en cours de migration du nuage à Skype pour Business Server local.

Dans ce cas, les utilisateurs finaux peuvent utiliser l' [Outil de Migration de réunion](https://www.microsoft.com/en-us/download/details.aspx?id=51659) à migrer leurs propres réunions à la place.

## <a name="how-mms-works"></a>Fonctionnement du MMS

Lorsque MMS est déclenchée pour un utilisateur donné, une demande de migration de cet utilisateur est placée dans une file d’attente. Pour éviter les conflits d’accès, la demande en file d’attente est traitée pas délibérément jusqu'à ce qu’au moins 90 minutes écoulée. Une fois MMS traite la demande, elle effectue les tâches suivantes :

1. Il recherche les boîtes aux lettres de l’utilisateur pour toutes les réunions organisées par cet utilisateur et planifiée à l’avenir.
2. Selon les informations de boîte aux lettres de l’utilisateur, il met à jour ou planifie les nouvelles réunions dans les équipes ou Skype pour Business en ligne de cet utilisateur, en fonction du scénario exact.
3. Dans le message électronique, il remplace le bloc de réunion en ligne dans les détails de la réunion.
4. Il envoie la version mise à jour de cette réunion à tous les destinataires de réunion au nom de l’organisateur de la réunion. Réunion invités recevront une mise à jour de réunion à la réunion mise à jour des coordonnées dans leur messagerie électronique. 

    ![Le bloc de réunion mis à jour par MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

Depuis le moment où que MMS est déclenchée, il faut généralement environ 2 heures jusqu'à la migrent des réunions de l’utilisateur. Toutefois, si l’utilisateur a un grand nombre de réunions, il pourrait être plus longue. Si MMS rencontre une erreur de migration d’une ou plusieurs réunions pour l’utilisateur, il va réessayer périodiquement jusqu'à 9 fois sur la durée de 24 heures.

**Notes**:

- Lorsqu'une réunion est migrée, MMS remplace tous les éléments du bloc d'information de la réunion en ligne. Ainsi, si un utilisateur a modifié ce bloc, ses modifications sont écrasées. Le contenu indiqué dans les détails de la réunion et qui ne fait pas partie du bloc d'informations de la réunion en ligne n'est pas modifié.
- Uniquement la Skype pour les réunions Microsoft Teams ou de l’entreprise qui ont été planifiées en cliquant sur le bouton **Skype ajouter une réunion** dans Outlook sur le Web ou à l’aide du complément de réunion Skype pour Outlook sont migrées. Si un utilisateur copie et colle les informations de réunion en ligne Skype à partir d’une réunion à une nouvelle réunion, cette nouvelle réunion ne sont pas mis à jour car il n’existe aucune réunion dans le service d’origine.
- Le contenu qui a été créé ou attaché à la réunion (tableaux blancs, sondages et ainsi de suite) de la réunion ne seront pas conservée après l’exécution de MMS. Si votre organisateurs de réunion ont joint contenu aux réunions à l’avance, le contenu vous devrez être recréés après l’exécution de MMS.
- Le lien vers les notes de réunion partagées dans l'élément du calendrier, ainsi que dans Skype, est également écrasé. Notez que les notes de réunion réel stockés dans OneNote sont toujours être Il est uniquement le lien vers les notes partagées qui est remplacé.
- Les réunions comptant plus de 250 participants (organisateur inclus) ne feront pas l'objet d'une migration.
- Certains caractères UNICODE dans le corps de l’invitation peuvent être correctement mis à jour à un des caractères spéciaux suivants : ï, ¿, ½,.

## <a name="triggering-mms-for-a-user"></a>Déclenchement MMS pour un utilisateur

Cette section décrit ce qui se produit lors du déclenchement MMS dans chacun des cas suivants :

- Lorsqu’un utilisateur est migré local vers le nuage
- Lorsqu’un administrateur modifie les paramètres de conférence audio de l’utilisateur 
- Lorsque le mode de l’utilisateur dans TeamsUpgradePolicy est défini sur TeamsOnly ou SfBWithTeamsCollabAndMeetings (appuyez sur clients uniquement)
- Lorsque vous utilisez PowerShell 

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Mise à jour de réunions lorsque vous déplacez un utilisateur local vers le nuage

Il s’agit du scénario le plus courant où MMS permet de créer une transition simplifiée pour vos utilisateurs. Sans migration de réunions, existantes réunions organisées par un utilisateur dans Skype pour Business Server locaux ne fonctionnent plus une fois que l’utilisateur est déplacé en ligne. Par conséquent, lorsque vous utilisez les outils d’administration locale (soit `Move-CsUser` ou le panneau de configuration d’administration) pour déplacer un utilisateur vers le nuage, réunions existantes sont automatiquement déplacées vers le nuage comme suit :

- Si le `MoveToTeams` basculer dans `Move-CsUser` est spécifié, les réunions sont migrées directement aux équipes. L’utilisation de ce commutateur nécessite Skype pour Business Server avec CU8 ou version ultérieure.
- Dans le cas contraire les réunions sont migrées vers Skype pour Business Online.

Dans les deux cas, si l’utilisateur a été attribué une licence de conférence Audio avant d’être déplacés vers le nuage, les réunions seront créées avec les coordonnées du rendez-vous. Si vous déplacez un utilisateur sur site vers le nuage et que vous avez l’intention de cet utilisateur à utiliser l’audioconférence, nous vous recommandons de tout d’abord affecter la conférence audio avant de déplacer l’utilisateur afin que la migration de réunion uniquement 1 est déclenchée.

> [!NOTE]
> La possibilité de migration des réunions directement aux équipes via le commutateur MoveToTeams est actuellement uniquement disponible en TAP. Si vous n’êtes pas un client TAP et le commutateur MoveToTeams est spécifié, l’utilisateur sera déplacé vers le mode TeamsOnly, mais les réunions seront déplacées vers Skype pour Business Online. Même si l’utilisateur est en mode TeamsOnly, ils peuvent tout de même rejoindre tout Skype pour une réunion d’affaires.

### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Mise à jour des réunions lors de la modifient des paramètres de conférence audio d’un utilisateur

Dans les cas suivants, MMS mettra à jour Skype existant pour les réunions d’entreprise et Teams Microsoft pour ajouter, supprimer ou modifier les coordonnées du rendez-vous :

- Lorsque vous affectez ou supprimez une licence de service de conférence Audio Microsoft à un utilisateur et que l’utilisateur n’est pas activé pour un fournisseur de services d’audioconférence tiers.
- Lorsque vous changez le fournisseur de services d’audioconférence d’un utilisateur à partir de n’importe quel autre fournisseur fournis par Microsoft, l’utilisateur est attribué une licence Microsoft Services d’audioconférence. Pour plus d’informations, voir [Attribuer de Microsoft en tant que le fournisseur de services d’audioconférence](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider). Notez également que la prise en charge pour les fournisseurs de services d’audioconférence tiers [ACP] est prévue pour fin de vie 2019, avril 1, comme [annoncé](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers).
- Lorsque vous activez ou désactivez les services d’audioconférence pour un utilisateur.
- Lorsque vous modifiez ou réinitialisez l’ID de conférence pour un utilisateur configuré pour utiliser des réunions publiques.
- Lorsque vous déplacez l’utilisateur vers un nouveau pont de conférence audio.
- Lorsqu’un numéro de téléphone à partir d’un pont de conférence audio est assigné. Il s’agit d’un scénario complexe qui requiert des étapes supplémentaires. Pour plus d’informations, voir [Modifier les numéros de téléphone sur le pont de conférence audio](https://docs.microsoft.com/en-us/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

Toutes les modifications aux paramètres de conférence audio d’un utilisateur déclenchent MMS. Les deux modifications suivantes n'entraînent pas la mise à jour des réunions par MMS :

- la modification de l'adresse SIP de l'organisateur de la réunion (qu'il s'agisse de son nom d'utilisateur SIP ou son domaine SIP) ;
- Lorsque vous modifiez votre organisation de réunions à l’aide de l’URL du `Update-CsTenantMeetingUrl` commande.


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Mise à jour des réunions lors de l’affectation TeamsUpgradePolicy

> [!NOTE]
> Cette section décrit la fonctionnalité qui n’est actuellement disponible pour les clients TAP. Microsoft prévoit doter cette fonctionnalité à tous les clients dans mai 2019.

Par défaut, migration de la réunion sera automatiquement déclenchée lorsqu’un utilisateur est accordé à une instance de `TeamsUpgradePolicy` avec `mode=TeamsOnly` ou `mode= SfBWithTeamsCollabAndMeetings`. Si vous ne souhaitez pas migrer des réunions lors de l’octroi d’un de ces modes, puis spécifiez `MigrateMeetingsToTeams $false` dans `Grant-CsTeamsUpgradePolicy`.

Notez également les éléments suivants :

- Migration de la réunion est appelée uniquement lorsque vous accordez `TeamsUpgradePolicy` pour un utilisateur spécifique. Si vous accordez `TeamsUpgradePolicy` avec `mode=TeamsOnly` ou `mode=SfBWithTeamsCollabAndMeetings` sur un client à l’échelle, migration de la réunion n’est pas appelée.
- Un utilisateur ne peut être accordé TeamsOnly mode si l’utilisateur est hébergé en ligne. Les utilisateurs qui sont hébergés sur un système local doivent être déplacées à l’aide de `Move-CsUser` comme décrit précédemment.
- Octroi d’un mode autre que TeamsOnly ou SfBWithTeamsCollabAndMeetings ne convertit pas les réunions équipes existantes Skype pour les réunions d’entreprise.

### <a name="trigger-meeting-migration-manually-via-powershell"></a>Migration de réunion déclencheur manuellement via PowerShell

En plus des migrations automatiques de réunion, administrateurs peuvent déclencher manuellement migration de réunion pour un utilisateur en exécutant l’applet de commande `Start-CsExMeetingMigration`. Cette applet de commande en file d’attente une demande de migration pour l’utilisateur spécifié. La nouvelle `TargetMeetingType` paramètre (qui est actuellement limitée aux participants à la technologie du programme d’Adoption) vous permet de spécifier comment migrer les réunions : 

- À l’aide de `TargetMeetingType Current` Spécifie que Skype pour les réunions Business restent Skype pour les réunions d’entreprise et réunions d’équipes restent réunions d’équipes. Coordonnées de services d’audioconférence toutefois peuvent être modifié et n’importe quel Skype sur site pour les réunions Business serait migré vers Skype pour Business Online.
- À l’aide de `TargetMeetingType Teams` Spécifie que des réunions existantes doivent être migrées vers des équipes, indépendamment de si la réunion est hébergée dans Skype pour des activités en ligne ou sur site et que les mises à jour des services d’audioconférence sont requis. 

L’exemple ci-dessous montre comment lancer la migration de réunion pour utilisateur ashaw@contoso.com afin que toutes les réunions sont migrées vers les équipes :

```
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```

> [!NOTE]
> L’applet de commande Start-CsExMeetingMigration est disponible pour tous les clients, mais la nouvelle TargetMeetingTypeParameter fonctionne actuellement uniquement pour les clients TAP. 


## <a name="managing-mms"></a>Gestion de MMS

À l’aide de Windows PowerShell, vous pouvez vérifier l’état de migration en cours, manuellement déclencher la migration de la réunion et désactiver migration entièrement. 

### <a name="check-the-status-of-meeting-migrations"></a>Vérifier l’état des migrations de réunion

Vous utilisez la `Get-CsMeetingMigrationStatus` applet de commande pour vérifier l’état des migrations de la réunion. Vous trouverez ci-dessous plusieurs exemples.

- Pour obtenir un état récapitulatif de toutes les migrations MMS, exécutez la commande suivante, qui fournit une vue tabulaire de tous les États de migration :

    ```
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- Pour obtenir tous les détails de toutes les migrations au sein d’une période spécifique, utilisez la `StartTime` et `EndTime` paramètres. Par exemple, la commande suivante renvoie tous les détails sur toutes les migrations qui s’est produite à partir du 1 octobre 2018 à 8 octobre 2018.

    ```
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- Pour vérifier l’état de la migration pour un utilisateur spécifique, utilisez la `Identity` paramètre. Ainsi, la commande suivante permet d'obtenir le statut de l'utilisateur ashaw@contoso.com :

    ```
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
Si vous voyez les migrations qui ont échoué, prendre des mesures pour résoudre ces problèmes dès que possible, dans la mesure où les personnes ne pourront pas rendez-vous pour les réunions organisées par les utilisateurs avant de les résoudre. Si `Get-CsMeetingMigrationStatus` montre les migrations dans un état d’échec, effectuez ces étapes :
 
1. Identifiez les utilisateurs concernés. Exécutez la commande suivante pour obtenir la liste des utilisateurs concernés, ainsi que l'erreur spécifique signalée :

    ```
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table Identity, LastMessage
    ```
2. Pour chaque utilisateur concerné, exécutez l’outil de Migration de réunion pour migrer manuellement leurs réunions.

3. Si la migration ne fonctionne toujours pas avec l'outil de migration de réunions, vous disposez de deux options :

    - demander aux utilisateurs de créer de nouvelles réunions Skype ;
    - [contacter le support technique](https://go.microsoft.com/fwlink/p/?LinkID=518322).


### <a name="enabling-and-disabling-mms"></a>Activation et désactivation de MMS

MMS est activée par défaut pour toutes les organisations, mais elle peut être désactivée comme suit :

- Désactiver entièrement pour le client. 
- Désactiver uniquement pour les modifications relatives aux services d’audioconférence. Dans ce cas, MMS exécuteront toujours lorsqu’un utilisateur est migré local vers le nuage, ou lorsque vous accordez mode TeamsOnly ou SfBWithTeamsCollabAndMeetings dans `TeamsUpgradePolicy`.

Par exemple, vous souhaiterez peut-être migrer toutes les réunions manuellement ou de désactiver temporairement MMS lors de modifications substantielles aux paramètres de conférence audio pour votre organisation

Pour voir si MMS est activé pour votre organisation, exécutez la commande suivante. MMS est activé si la `MeetingMigrationEnabled` paramètre est `$true`.
```
Get-CsTenantMigrationConfiguration
```
Pour activer ou désactiver entièrement les MMS, utilisez la `Set-CsTenantMigrationConfiguration` commande. Par exemple, pour désactiver MMS, exécutez la commande suivante :

```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
Si MMS est activé dans l’organisation et que vous souhaitez vérifier si elle est activée pour les mises à jour de la conférence audio, vérifiez la valeur de la `AutomaticallyMigrateUserMeetings` paramètre dans la sortie de `Get-CsOnlineDialInConferencingTenantSettings`. Pour activer ou désactiver MMS pour l’audioconférence, utilisez `Set-CsOnlineDialInConferencingTenantSettings`. Par exemple, pour désactiver MMS pour les conférences audio, exécutez la commande suivante :

```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l’audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Déplacer des utilisateurs entre local et le nuage](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
