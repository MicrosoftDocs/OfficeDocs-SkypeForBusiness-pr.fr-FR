---
title: Utilisation du service Meeting Migration Service (MMS)
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Meeting Migration Service (MMS) est un service qui s’exécute en arrière-plan et met automatiquement à jour Skype Entreprise et Microsoft Teams réunions pour les utilisateurs. MmS est conçu pour éliminer la nécessité pour les utilisateurs d’exécuter l’outil de migration de réunion pour mettre à jour Skype Entreprise et Microsoft Teams réunions.
ms.openlocfilehash: 3fefc7aa45df3323f8c96801bde1cb301ff40572
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613263"
---
# <a name="using-the-meeting-migration-service-mms"></a>Utilisation du service Meeting Migration Service (MMS)

Meeting Migration Service (MMS) est un service qui met à jour les réunions existantes d’un utilisateur dans les scénarios suivants :

- Lorsqu’un utilisateur est migré de l’offre en local vers le cloud (que ce soit Skype Entreprise Online ou TeamsOnly).
- Lorsqu’un administrateur modifie les paramètres d’audioconférence de l’utilisateur 
- Lorsqu’un utilisateur en ligne est mis à niveau vers Teams uniquement, ou quand le mode d’un utilisateur dans TeamsUpgradePolicy est définie sur SfBwithTeamsCollabAndMeetings
- Lorsque vous utilisez PowerShell 


Par défaut, MMS est déclenché automatiquement dans chacun de ces cas, bien que les administrateurs peuvent le désactiver au niveau du client. De plus, les administrateurs peuvent utiliser une cmdlet PowerShell pour déclencher manuellement la migration de réunion pour un utilisateur donné.


**Limitations**: Le service de migration de réunion ne peut pas être utilisé si l’une des raisons suivantes s’applique :

- La boîte aux lettres de l’utilisateur est hébergée Exchange local.
- L’utilisateur est en cours de migration du cloud vers Skype Entreprise Server site.


## <a name="how-mms-works"></a>Fonctionnement de MMS

Lorsque MMS est déclenché pour un utilisateur donné, une demande de migration pour cet utilisateur est placée dans une file d’attente. Pour éviter toute condition de course, la demande en file d’attente est délibérément non traitée avant au moins 90 minutes. Une fois que MMS traite la demande, il effectue les tâches suivantes :

1. Il recherche dans la boîte aux lettres de cet utilisateur toutes les réunions existantes organisées par cet utilisateur et organisées ultérieurement.
2. En fonction des informations trouvées dans la boîte aux lettres de l’utilisateur, il met à jour ou planifier de nouvelles réunions dans Teams ou Skype Entreprise Online pour cet utilisateur, selon le scénario exact.
3. Dans le message électronique, il remplace le bloc de réunion en ligne dans les détails de la réunion.
4. Elle envoie la version mise à jour de cette réunion à tous les destinataires de la réunion de la part de l’organisateur de la réunion. Les invités à la réunion recevront une mise à jour de la réunion avec les coordonnées de réunion mises à jour dans leur courrier électronique. 

    ![Le bloc de réunion mis à jour par MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

À partir du moment où MMS est déclenché, la migration des réunions de l’utilisateur prend généralement 2 heures. Toutefois, si l’utilisateur a un grand nombre de réunions, cela peut prendre plus de temps. Si MMS rencontre une erreur lors de la migration d’une ou plusieurs réunions de l’utilisateur, il réessaye régulièrement jusqu’à 9 fois sur une période de 24 heures.

**Remarques**:

- Lorsqu'une réunion est migrée, MMS remplace tous les éléments du bloc d'information de la réunion en ligne. Ainsi, si un utilisateur a modifié ce bloc, ses modifications sont écrasées. Le contenu indiqué dans les détails de la réunion et qui ne fait pas partie du bloc d'informations de la réunion en ligne n'est pas modifié. Cela signifie que tous les fichiers joints à l’invitation à la réunion seront toujours inclus. 
- Seules les réunions Skype Entreprise ou Microsoft Teams qui ont été programmées en cliquant sur le bouton Ajouter une réunion **Skype** dans Outlook sur le web ou à l’aide du Réunion Skype pour Outlook sont migrées. Si un utilisateur copie et copie les informations de la réunion en ligne Skype d’une réunion vers une nouvelle réunion, cette nouvelle réunion n’est pas mise à jour car aucune réunion n’Skype été mise à jour dans le service d’origine.
- Le contenu de la réunion qui a été créé ou joint à la réunion (tableaux blancs, sondages, etc.) n’est pas conservé après l’affichage de MMS. Si les organisateurs de votre réunion ont joint du contenu aux réunions à l’avance, ce contenu devra être recréé après l’incrément de MMS.
- Le lien vers les notes de réunion partagées dans l'élément du calendrier, ainsi que dans Skype, est également écrasé. Notez que les notes de réunion enregistrées dans OneNote sont toujours là ; il s’agit uniquement du lien vers les notes partagées écrasée.
- Les réunions comptant plus de 250 participants (organisateur inclus) ne feront pas l'objet d'une migration.
- Certains caractères UNICODE dans le corps de l’invitation peuvent être mis à jour de façon incorrecte avec l’un des caractères spéciaux suivants : ï, ¿, 1/2, .

## <a name="triggering-mms-for-a-user"></a>Déclenchement de MMS pour un utilisateur

Cette section décrit ce qui se produit lorsque MMS est déclenché dans chacun des cas suivants :

- Lorsqu’un utilisateur est migré de l’offre en local vers le cloud
- Lorsqu’un administrateur modifie les paramètres d’audioconférence de l’utilisateur 
- Lorsque le mode de l’utilisateur dans TeamsUpgradePolicy est définie sur TeamsOnly ou SfBWithTeamsCollabAndMeetings (à l’aide de Powershell ou du portail d’administration Teams)
- Lorsque vous utilisez l’cmdlet PowerShell, Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Mise à jour des réunions lorsque vous déplacez un utilisateur local vers le cloud

Il s’agit du scénario le plus courant dans lequel MMS facilite la transition de vos utilisateurs. Sans la migration de réunion, les réunions existantes organisées par un utilisateur dans Skype Entreprise Server sur site ne fonctionneraient plus une fois l’utilisateur déplacé en ligne. Par conséquent, lorsque vous utilisez les outils d’administration locaux (soit ou le Panneau de contrôle de l’administrateur) pour déplacer un utilisateur vers le cloud, les réunions existantes sont automatiquement déplacées vers le cloud comme suit `Move-CsUser` :

- Si le commutateur est spécifié, les réunions sont migrées directement vers Teams et l’utilisateur est `MoveToTeams` `Move-CsUser` en mode TeamsOnly. L’utilisation de ce commutateur Skype Entreprise Server 2015 avec CU8 ou une date ultérieure. Ces utilisateurs peuvent toujours participer à Skype Entreprise réunion à qui ils peuvent être invités, à l’aide du client Skype Entreprise ou de l’Réunion Skype client.
- Sinon, les réunions sont migrées vers Skype Entreprise Online.

Dans les deux cas, si l’utilisateur a reçu une licence d’audioconférence avant d’être déplacé vers le cloud, les réunions sont créées avec des coordonnées d’accès. Si vous déplacez un utilisateur du cloud en local et que vous souhaitez qu’il utilise l’audioconférence, nous vous recommandons d’attribuer d’abord l’audioconférence avant de déplacer l’utilisateur afin que seule une migration de réunion soit déclenchée.


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Mise à jour des réunions en cas de modification des paramètres d’audioconférence d’un utilisateur

Dans les cas suivants, MMS met à jour les réunions Skype Entreprise et Microsoft Teams pour ajouter, supprimer ou modifier les coordonnées de connexion :

- Lorsque vous affectez ou supprimez une licence de service d’audioconférence Microsoft à un utilisateur et que cet utilisateur n’est pas activé pour un fournisseur de services d’audioconférence tiers.
- Lorsque vous modifiez le fournisseur de services d’audioconférence d’un utilisateur de n’importe quel autre fournisseur par Microsoft, à condition qu’une licence Microsoft Audioconférence lui soit attribuée. Pour plus d’informations, voir Affecter Microsoft comme fournisseur de services [d’audioconférence.](./assign-microsoft-as-the-audio-conferencing-provider.md) Notez également que le support pour les fournisseurs de services d’audioconférence tiers est prévu pour le 1er avril 2019, comme annoncé [précédemment.](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md)
- Lorsque vous activez ou désactivez l’audioconférence pour un utilisateur.
- Lorsque vous modifiez ou réinitialisez l’ID de conférence d’un utilisateur configuré pour utiliser les réunions publiques.
- Lorsque vous déplacez l’utilisateur vers un nouveau pont de conférence audio.
- Lorsqu’un numéro de téléphone d’un pont d’audioconférence n’est pas engagé. Il s’agit d’un scénario complexe qui nécessite des étapes supplémentaires. Pour plus d’informations, [voir Modifier les numéros de téléphone sur votre pont de conférence audio.](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)

Toutes les modifications apportées aux paramètres d’audioconférence d’un utilisateur ne déclenchent pas MMS. Les deux modifications suivantes n'entraînent pas la mise à jour des réunions par MMS :

- la modification de l'adresse SIP de l'organisateur de la réunion (qu'il s'agisse de son nom d'utilisateur SIP ou son domaine SIP) ;
- Lorsque vous modifiez l’URL de réunion de votre organisation à l’aide de la `Update-CsTenantMeetingUrl` commande.


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Mise à jour des réunions lors de l’attribution de TeamsUpgradePolicy

Par défaut, la migration de réunion est déclenchée automatiquement lorsqu’un utilisateur se voie accorder une instance avec `TeamsUpgradePolicy` `mode=TeamsOnly` `mode= SfBWithTeamsCollabAndMeetings` ou. Si vous ne souhaitez pas migrer les réunions lors de l’octroi de l’un de ces modes, spécifiez-le (si vous utilisez PowerShell) ou décochez la case pour migrer les réunions lors de la configuration du mode de coexistence d’un utilisateur (si vous utilisez le portail `MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy` d’administration Teams).

Notez également ce qui suit :

- La migration de réunions est uniquement évoquée lorsque vous accordez `TeamsUpgradePolicy` l’accès à un utilisateur spécifique. Si vous accordez avec ou au niveau du client, la migration de réunion `TeamsUpgradePolicy` `mode=TeamsOnly` `mode=SfBWithTeamsCollabAndMeetings` n’est pas évoquée. 
- Un utilisateur ne peut se voir accorder le mode TeamsOnly que si l’utilisateur est homed online. Les utilisateurs homed local doivent être déplacés à l’aide `Move-CsUser` de la description ci-après.
- L’octroi d’un mode autre que TeamsOnly ou SfBWithTeamsCollabAndMeetings ne convertit pas les réunions existantes Teams en Skype Entreprise réunions.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Déclencher la migration manuelle de réunions via une cmdlet PowerShell

En plus des migrations de réunions automatiques, les administrateurs peuvent déclencher manuellement la migration de réunion d’un utilisateur en exécutant l’cmdlet. `Start-CsExMeetingMigration` Cette cmdlet place en file d’attente une demande de migration pour l’utilisateur spécifié.  En plus du paramètre obligatoire, il prend deux paramètres facultatifs et , ce qui vous permet de spécifier la manière `Identity` `SourceMeetingType` de `TargetMeetingType` migrer les réunions :

**TargetMeetingType :**

- Utilisation de spécifier que les Skype Entreprise restent Skype Entreprise réunions et que Teams réunions restent Teams `TargetMeetingType Current` réunions. En revanche, les coordonnées de conférence audio peuvent être modifiées et les réunions Skype Entreprise sur site sont migrées vers Skype Entreprise Online. Il s’agit de la valeur par défaut de TargetMeetingType.
- Spécifie que les réunions existantes doivent être migrées vers Teams, que la réunion soit hébergée sur Skype Entreprise online ou sur site, et que des mises à jour de l’audioconférence soient requises ou `TargetMeetingType Teams` non. 

**SourceMeetingType :**
- Indique que seules Skype Entreprise réunions doivent être mises à jour (sur site ou `SourceMeetingType SfB` en ligne).
- Indique `SourceMeetingType Teams` que seules Teams réunions doivent être mises à jour.
- Indique que les réunions Skype Entreprise et Teams doivent `SourceMeetingType All` être mises à jour. Il s’agit de la valeur par défaut de SourceMeetingType.
    

L’exemple ci-dessous montre comment démarrer une migration de réunion pour les utilisateurs ashaw@contoso.com de sorte que toutes les réunions soient migrées vers Teams :

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a>Gestion de MMS

En Windows PowerShell, vous pouvez vérifier l’état des migrations en cours, déclencher manuellement la migration de réunions et désactiver complètement la migration. 

### <a name="check-the-status-of-meeting-migrations"></a>Vérifier le statut des migrations de réunion

Vous utilisez `Get-CsMeetingMigrationStatus` l’cmdlet pour vérifier le statut des migrations de réunion. Vous trouverez ci-dessous plusieurs exemples.

- Pour obtenir un état récapitulatif de toutes les migrations MMS, exécutez la commande suivante qui fournit une vue tabulaire de tous les états de migration :

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- Pour obtenir les détails complets de toutes les migrations d’une période spécifique, utilisez les `StartTime` `EndTime` paramètres et ceux-ci. Par exemple, la commande suivante permet d’obtenir les détails complets de toutes les migrations qui ont eu lieu du 1er au 8 octobre 2018.

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- Pour vérifier l’état de migration d’un utilisateur spécifique, utilisez le `Identity` paramètre. Ainsi, la commande suivante permet d'obtenir le statut de l'utilisateur ashaw@contoso.com :

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
Si des migrations ont échoué, prenez des mesures pour résoudre ces problèmes le plus rapidement possible, car les personnes ne pourront pas se rendre aux réunions organisées par ces utilisateurs tant que vous ne les avez pas résolues. Si des migrations sont dans un état d’échec, `Get-CsMeetingMigrationStatus` effectuez les étapes suivantes :
 
1. Identifiez les utilisateurs concernés. Exécutez la commande suivante pour obtenir la liste des utilisateurs concernés, ainsi que l'erreur spécifique signalée :

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. Pour chaque utilisateur affecté, exécutez l’outil de migration de réunion pour migrer manuellement ses réunions.

3. Si la migration ne fonctionne toujours pas avec l'outil de migration de réunions, vous disposez de deux options :

    - demander aux utilisateurs de créer de nouvelles réunions Skype ;
    - [contacter le support technique](/microsoft-365/Admin/contact-support-for-business-products).

L’cmdlet peut être utilisée pour récupérer l’état des migrations qui ont été déclenchées au cours des `Get-CsMeetingMigrationStatus` 150 derniers jours. Les enregistrements des migrations de plus de 150 jours sont purgés du système.

### <a name="enabling-and-disabling-mms"></a>Activation et désactivation de MMS

MMS est activé par défaut pour toutes les organisations, mais il peut être désactivé comme suit :

- Désactivez entièrement pour le client. 
- Désactivez uniquement pour les modifications liées à l’audioconférence. Dans ce cas, MMS est toujours exécuté lorsqu’un utilisateur est migré de l’expérience en local vers le cloud ou lorsque vous accordez le mode TeamsOnly ou SfBWithTeamsCollabAndMeetings en `TeamsUpgradePolicy` .

Par exemple, vous pouvez migrer manuellement toutes les réunions ou désactiver temporairement MMS tout en a apporter d’importantes modifications aux paramètres d’audioconférence de votre organisation.

Pour voir si MMS est activé pour votre organisation, exécutez la commande suivante. MMS est activé si le `MeetingMigrationEnabled` paramètre est `$true` .
```PowerShell
Get-CsTenantMigrationConfiguration
```
Pour activer ou désactiver MMS entièrement, utilisez la `Set-CsTenantMigrationConfiguration` commande. Par exemple, pour désactiver MMS, exécutez la commande suivante :

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
Si MMS est activé dans l’organisation et que vous voulez vérifier s’il est activé pour les mises à jour d’audioconférence, vérifiez la valeur du paramètre dans la sortie `AutomaticallyMigrateUserMeetings` `Get-CsOnlineDialInConferencingTenantSettings` de. Pour activer ou désactiver MMS pour l’audioconférence, utilisez `Set-CsOnlineDialInConferencingTenantSettings` . Par exemple, pour désactiver MMS pour l’audioconférence, exécutez la commande suivante :

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Rubriques connexes

[Essayez ou achetez l’audioconférence dans Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Déplacer des utilisateurs entre l’environnement local et le cloud](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)
