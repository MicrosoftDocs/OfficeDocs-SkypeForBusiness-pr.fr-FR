---
title: Utilisation du service de migration de réunion (MMS)
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
description: Meeting Migration Service (MMS) est un service qui s’exécute en arrière-plan et met automatiquement à jour Skype Entreprise et Microsoft Teams réunions pour les utilisateurs.
ms.openlocfilehash: a7e917a5b579c60ff84c3e1a5e6468a28f75faff
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671640"
---
# <a name="using-the-meeting-migration-service-mms"></a>Utilisation du service de migration de réunion (MMS)

Le service de migration de réunion (MMS) est un service qui met à jour les réunions existantes d’un utilisateur dans les scénarios suivants :

- Lorsqu’un utilisateur est migré de l’environnement local vers le cloud.
- Lorsqu’un administrateur modifie les paramètres d’audioconférence de l’utilisateur
- Lorsqu’un utilisateur en ligne est mis à niveau vers Teams uniquement, ou quand le mode d’un utilisateur dans TeamsUpgradePolicy est défini sur SfBwithTeamsCollabAndMeetings
- Lorsque vous utilisez PowerShell

Par défaut, MMS est déclenché automatiquement dans chacun de ces cas. En outre, les administrateurs peuvent utiliser une applet de commande PowerShell pour déclencher manuellement la migration de réunion pour un utilisateur donné.

**Limitations** : le service de migration de réunion ne peut pas être utilisé si l’un des éléments suivants s’applique :

- La boîte aux lettres de l’utilisateur est hébergée dans Exchange local.
- L’utilisateur est migré du cloud vers Skype Entreprise Server localement.

## <a name="how-mms-works"></a>Fonctionnement de MMS

Quand MMS est déclenché pour un utilisateur donné, une demande de migration pour cet utilisateur est placée dans une file d’attente. Pour éviter toute condition de concurrence, la demande en file d’attente n’est délibérément pas traitée tant qu’au moins 90 minutes ne sont pas passées. Une fois que MMS traite la demande, il effectue les tâches suivantes :

1. Il recherche dans la boîte aux lettres de cet utilisateur toutes les réunions existantes organisées par cet utilisateur et planifiées à l’avenir.
2. En fonction des informations trouvées dans la boîte aux lettres de l’utilisateur, il met à jour ou planifie de nouvelles réunions dans Teams pour cet utilisateur, selon le scénario exact.
3. Dans le message électronique, il remplace le bloc de réunion en ligne dans les détails de la réunion.
4. Il envoie la version mise à jour de cette réunion à tous les destinataires de la réunion au nom de l’organisateur de la réunion. Les invités à une réunion recevront une mise à jour de réunion avec les coordonnées de réunion mises à jour dans leur e-mail.

    ![Bloc de réunion mis à jour par MMS.](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

À partir du moment où MMS est déclenché, la migration des réunions de l’utilisateur prend généralement environ 2 heures. Toutefois, si l’utilisateur a un grand nombre de réunions, cela peut prendre plus de temps. Si MMS rencontre une erreur lors de la migration d’une ou de plusieurs réunions pour l’utilisateur, il réessaye régulièrement jusqu’à 9 fois sur une période de 24 heures.

**Remarques** :

- Lorsqu'une réunion est migrée, MMS remplace tous les éléments du bloc d'information de la réunion en ligne. Ainsi, si un utilisateur a modifié ce bloc, ses modifications sont écrasées. Le contenu indiqué dans les détails de la réunion et qui ne fait pas partie du bloc d'informations de la réunion en ligne n'est pas modifié. Cela signifie que tous les fichiers joints à l’invitation à la réunion seront toujours inclus.
- Seules les réunions Skype Entreprise ou Microsoft Teams planifiées en cliquant sur le bouton **Ajouter Skype réunion** dans Outlook sur le Web ou en utilisant le complément Réunion Skype pour Outlook sont migrées. Si un utilisateur copie et colle les Skype informations de réunion en ligne d’une réunion à une nouvelle réunion, cette nouvelle réunion ne sera pas mise à jour, car il n’existe aucune réunion dans le service d’origine.
- Le contenu de la réunion qui a été créé ou attaché à la réunion (tableaux blancs, sondages, et ainsi de suite) ne sera pas conservé après l’exécution de MMS. Si vos organisateurs de réunion ont joint du contenu aux réunions à l’avance, le contenu doit être recréé après l’exécution de MMS.
- Le lien vers les notes de réunion partagées dans l'élément du calendrier, ainsi que dans Skype, est également écrasé. Notez que les notes de réunion réelles stockées dans OneNote seront toujours là ; il s’agit uniquement du lien vers les notes partagées qui est remplacé.
- Les réunions comptant plus de 250 participants (organisateur inclus) ne feront pas l'objet d'une migration.
- Certains caractères UNICODE dans le corps de l’invitation peuvent être mis à jour incorrectement vers l’un des caractères spéciaux suivants : ï, ¿, 1/2, .

## <a name="triggering-mms-for-a-user"></a>Déclenchement de MMS pour un utilisateur

Cette section décrit ce qui se passe quand MMS est déclenché dans chacun des cas suivants :

- Lorsqu’un utilisateur est migré de l’environnement local vers le cloud
- Lorsqu’un administrateur modifie les paramètres d’audioconférence de l’utilisateur
- Lorsque le mode de l’utilisateur dans TeamsUpgradePolicy est défini sur TeamsOnly ou SfBWithTeamsCollabAndMeetings (à l’aide de PowerShell ou du portail Teams Administration)
- Lorsque vous utilisez l’applet de commande PowerShell, Start-CsExMeetingMigration

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a>Mise à jour des réunions lorsque vous déplacez un utilisateur local vers le cloud

Il s’agit du scénario le plus courant où MMS permet de créer une transition plus fluide pour vos utilisateurs. Sans la migration des réunions, les réunions existantes organisées par un utilisateur dans Skype Entreprise Server local ne fonctionneraient plus une fois l’utilisateur déplacé en ligne. Par conséquent, lorsque vous utilisez les outils d’administration locaux (`Move-CsUser`ou le Administration Panneau de configuration) pour déplacer un utilisateur vers le cloud, les réunions existantes sont automatiquement déplacées vers le cloud et converties en TeamsOnly.

Si une licence Audioconférence a été attribuée à l’utilisateur avant d’être déplacé vers le cloud, les réunions sont créées avec des coordonnées d’accès. Si vous déplacez un utilisateur d’un emplacement local vers le cloud et que vous prévoyez que cet utilisateur utilise Audioconférence, nous vous recommandons d’attribuer d’abord la conférence audio avant de déplacer l’utilisateur afin qu’une seule migration de réunion soit déclenchée.

### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a>Mise à jour des réunions quand les paramètres d’audioconférence d’un utilisateur changent

Dans les cas suivants, MMS met à jour les réunions Skype Entreprise et Microsoft Teams existantes pour ajouter, supprimer ou modifier des coordonnées de connexion :

- Lorsque vous attribuez ou supprimez une licence de service Microsoft Audioconférence à un utilisateur, et que cet utilisateur n’est pas activé pour un fournisseur d’audioconférence tiers.
- Lorsque vous modifiez le fournisseur d’audioconférence d’un utilisateur d’un autre fournisseur vers Microsoft, à condition qu’une licence Microsoft Audioconférence lui soit attribuée. Pour plus d’informations, consultez [Affecter Microsoft en tant que fournisseur d’audioconférence](./assign-microsoft-as-the-audio-conferencing-provider.md). Notez également que la prise en charge des fournisseurs d’audioconférence tiers est prévue pour la fin de vie le 1er avril 2019, comme [annoncé précédemment](../legal-and-regulatory/end-of-integration-with-3rd-party-providers.md).
- Lorsque vous activez ou désactivez l’audioconférence pour un utilisateur.
- Lorsque vous modifiez ou réinitialisez l’ID de conférence pour un utilisateur configuré pour utiliser des réunions publiques.
- Lorsque vous déplacez l’utilisateur vers un nouveau pont d’audioconférence.
- Lorsqu’un numéro de téléphone d’un pont d’audioconférence n’est pas attribué. Il s’agit d’un scénario complexe qui nécessite des étapes supplémentaires. Pour plus d’informations, consultez [Modifier les numéros de téléphone sur votre pont d’audioconférence](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).

Toutes les modifications apportées aux paramètres d’audioconférence d’un utilisateur ne déclenchent pas MMS. Les deux modifications suivantes n'entraînent pas la mise à jour des réunions par MMS :

- la modification de l'adresse SIP de l'organisateur de la réunion (qu'il s'agisse de son nom d'utilisateur SIP ou son domaine SIP) ;
- Lorsque vous modifiez l’URL de réunion de votre organisation à l’aide de la `Update-CsTenantMeetingUrl` commande.

### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a>Mise à jour des réunions lors de l’affectation de TeamsUpgradePolicy

Par défaut, la migration de réunion est déclenchée automatiquement lorsqu’une instance de `TeamsUpgradePolicy` with `mode=TeamsOnly` ou `mode= SfBWithTeamsCollabAndMeetings`. Si vous ne souhaitez pas migrer des réunions lors de l’octroi de l’un de ces modes, spécifiez `MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy` dans (si vous utilisez PowerShell) ou décochez la case pour migrer des réunions lors de la définition du mode de coexistence d’un utilisateur (si vous utilisez le portail d’administration Teams).

Notez également les points suivants :

- La migration de réunion est appelée uniquement lorsque vous accordez `TeamsUpgradePolicy` pour un utilisateur spécifique. Si vous accordez `TeamsUpgradePolicy` avec `mode=TeamsOnly` ou `mode=SfBWithTeamsCollabAndMeetings` à *l’échelle du locataire* , la migration de réunion n’est pas appelée.
- Un utilisateur ne peut se voir accorder le mode TeamsOnly que si l’utilisateur est hébergé en ligne. Les utilisateurs hébergés localement doivent être déplacés à l’aide `Move-CsUser` de ce qui a été décrit précédemment.
- L’octroi d’un mode autre que TeamsOnly ou SfBWithTeamsCollabAndMeetings ne convertit pas les réunions Teams existantes en réunions Skype Entreprise.

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a>Déclencher la migration de réunion manuellement via l’applet de commande PowerShell

En plus des migrations de réunion automatiques, les administrateurs peuvent déclencher manuellement la migration de réunion pour un utilisateur en exécutant l’applet de commande `Start-CsExMeetingMigration`. Cette applet de commande met en file d’attente une demande de migration pour l’utilisateur spécifié.  En plus du paramètre requis `Identity` , il prend deux paramètres facultatifs, `SourceMeetingType` et `TargetMeetingType`, qui vous permettent de spécifier comment migrer des réunions :

**TargetMeetingType :**

- L’utilisation `TargetMeetingType Current` spécifie que les réunions Skype Entreprise restent Skype Entreprise réunions et Teams réunions restent Teams réunions. Toutefois, les coordonnées d’audioconférence peuvent être modifiées et toutes les réunions Skype Entreprise locales sont migrées vers Skype Entreprise Online. Il s’agit de la valeur par défaut pour TargetMeetingType.
- L’utilisation `TargetMeetingType Teams` spécifie que toute réunion existante doit être migrée vers Teams, que la réunion soit hébergée dans Skype Entreprise en ligne ou localement, et que des mises à jour d’audioconférence soient requises ou non.

**SourceMeetingType :**

- L’utilisation `SourceMeetingType SfB` indique que seules Skype Entreprise réunions (locales ou en ligne) doivent être mises à jour.
- L’utilisation `SourceMeetingType Teams` indique que seules Teams réunions doivent être mises à jour.
- L’utilisation `SourceMeetingType All` indique que les réunions Skype Entreprise et Teams réunions doivent être mises à jour. Il s’agit de la valeur par défaut pour SourceMeetingType.

L’exemple ci-dessous montre comment lancer la migration des réunions pour les ashaw@contoso.com utilisateur afin que toutes les réunions soient migrées vers Teams :

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```

## <a name="managing-mms"></a>Gestion de MMS

À l’aide de Windows PowerShell, vous pouvez vérifier l’état des migrations en cours, déclencher manuellement la migration de réunion et désactiver complètement la migration.

### <a name="check-the-status-of-meeting-migrations"></a>Vérifier l’état des migrations de réunion

Vous utilisez l’applet `Get-CsMeetingMigrationStatus` de commande pour vérifier l’état des migrations de réunion. Vous trouverez ci-dessous plusieurs exemples.

- Pour obtenir un état récapitulatif de toutes les migrations MMS, exécutez la commande suivante qui fournit une vue tabulaire de tous les états de migration :

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed        2
    Succeeded   131
    ```

- Pour obtenir des détails complets sur toutes les migrations au cours d’une période spécifique, utilisez les paramètres et `EndTime` les `StartTime` paramètres. Par exemple, la commande suivante retourne des détails complets sur toutes les migrations qui se sont produites du 1er octobre 2018 au 8 octobre 2018.

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```

- Pour vérifier l’état de la migration pour un utilisateur spécifique, utilisez le `Identity` paramètre. Ainsi, la commande suivante permet d'obtenir le statut de l'utilisateur ashaw@contoso.com :

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```

Si des migrations ont échoué, prenez des mesures pour résoudre ces problèmes dès que possible, car les utilisateurs ne pourront pas se connecter aux réunions organisées par ces utilisateurs tant que vous ne les aurez pas résolus. Si `Get-CsMeetingMigrationStatus` des migrations sont en état d’échec, procédez comme suit :

1. Identifiez les utilisateurs concernés. Exécutez la commande suivante pour obtenir la liste des utilisateurs concernés, ainsi que l'erreur spécifique signalée :

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```

2. Pour chaque utilisateur affecté, passez en revue la valeur de la propriété LastMessage pour déterminer pourquoi la migration de la réunion a échoué et quelle action corrective prendre. Une fois que des mesures correctives ont été prises, relancez la migration de réunion pour les utilisateurs concernés à l’aide du `Start-CsExMeetingMigration` cmldet PowerShell, comme décrit ci-dessus.

3. Si la migration ne fonctionne toujours pas, vous disposez de deux options :

    - demander aux utilisateurs de créer de nouvelles réunions Skype ;
    - [contacter le support technique](/microsoft-365/Admin/contact-support-for-business-products).

L’applet `Get-CsMeetingMigrationStatus` de commande peut être utilisée pour récupérer l’état des migrations qui ont été déclenchées au cours des 150 derniers jours. Les enregistrements des migrations antérieures à 150 jours sont supprimés du système.

### <a name="enabling-and-disabling-mms"></a>Activation et désactivation de MMS

MMS est activé par défaut pour toutes les organisations, mais il peut être désactivé comme suit :

- Désactiver entièrement pour le locataire.
- Désactiver uniquement pour les modifications liées à l’audioconférence. Dans ce cas, MMS s’exécute quand un utilisateur est migré de l’environnement local vers le cloud ou lorsque vous accordez le mode TeamsOnly ou le mode SfBWithTeamsCollabAndMeetings en `TeamsUpgradePolicy`.

Par exemple, vous pouvez migrer manuellement toutes les réunions ou désactiver temporairement MMS tout en apportant des modifications substantielles aux paramètres d’audioconférence de votre organisation.

Pour voir si MMS est activé pour votre organisation, exécutez la commande suivante. MMS est activé si le `MeetingMigrationEnabled` paramètre est `$true`.

```PowerShell
Get-CsTenantMigrationConfiguration
```

Si MMS est activé dans l’organisation et que vous souhaitez vérifier s’il est activé pour les mises à jour de l’audioconférence, vérifiez la valeur du `AutomaticallyMigrateUserMeetings` paramètre dans la sortie à partir de `Get-CsOnlineDialInConferencingTenantSettings`. Pour activer ou désactiver MMS pour l’audioconférence, utilisez `Set-CsOnlineDialInConferencingTenantSettings`. Par exemple, pour désactiver MMS pour l’audioconférence, exécutez la commande suivante :

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a>Voir aussi

[Essayer ou acheter des Audioconférence dans Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[Déplacer des utilisateurs entre l’environnement local et le cloud](../../SfbHybrid/hybrid/move-users-between-on-premises-and-cloud.md)
