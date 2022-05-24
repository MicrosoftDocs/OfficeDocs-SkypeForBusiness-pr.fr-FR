---
title: Stratégies de réunion et expiration de la réunion dans Microsoft Teams
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej, brgussin
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Découvrez comment utiliser les paramètres de stratégie de réunion pour contrôler l’expiration de la réunion dans Microsoft Teams.
ms.openlocfilehash: 014989cd2fda0ce28ef96ee53c82908f814ee8c7
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646213"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Stratégies de réunion et expiration de la réunion dans Microsoft Teams

[Les stratégies de réunion](meeting-policies-overview.md) dans Microsoft Teams sont utilisées pour contrôler si les utilisateurs de votre organisation peuvent démarrer et planifier des réunions, ainsi que les fonctionnalités disponibles pour les participants aux réunions planifiées par les utilisateurs. Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et attribuer des stratégies personnalisées. Vous gérez les stratégies de réunion dans le centre d’administration Microsoft Teams ou à l’aide des applets de commande PowerShell [Get](/powershell/module/skype/get-csteamsmeetingpolicy), [New](/powershell/module/skype/new-csteamsmeetingpolicy), [Set](/powershell/module/skype/set-csteamsmeetingpolicy), [Remove](/powershell/module/skype/remove-csteamsmeetingpolicy), [Grant](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy.

Paramètres de stratégie de réunion qui contrôlent si les utilisateurs peuvent démarrer et planifier des réunions, ainsi que contrôler l’expiration des réunions planifiées par les utilisateurs. Lorsqu’un lien de participation à une réunion et un ID de conférence expirent, personne ne peut participer à la réunion. Les paramètres de stratégie de réunion suivants déterminent si les utilisateurs peuvent démarrer et planifier des réunions dans Teams. Nous abordons les paramètres de la réunion dans cet article.

- [Se réunir maintenant dans les canaux](meeting-policies-in-teams-general.md#meet-now-in-channels) : détermine si un utilisateur peut démarrer une réunion impromptue dans un canal.
- [Planification des réunions](meeting-policies-in-teams-general.md#channel-meeting-scheduling) de canal : détermine si un utilisateur peut planifier une réunion dans un canal.
- [Planification de réunion privée](meeting-policies-in-teams-general.md#private-meeting-scheduling) : détermine si un utilisateur peut planifier une réunion privée dans Teams. Une réunion est privée lorsque celle-ci n’est pas publiée dans un canal d’une équipe.
- [Outlook ajouter](meeting-policies-in-teams-general.md#outlook-add-in) : contrôle si un utilisateur peut planifier une réunion privée à partir de Outlook. Une réunion est privée lorsque celle-ci n’est pas publiée dans un canal d’une équipe.
- [Réunion maintenant dans des réunions privées](meeting-policies-in-teams-general.md#meet-now-in-private-meetings) : détermine si un utilisateur peut démarrer une réunion privée impromptue.

Par défaut, ces paramètres sont activés. Lorsque l’un de ces paramètres est désactivé, tout utilisateur auquel la stratégie est affectée ne peut pas démarrer ou planifier de nouvelles réunions de ce type. En même temps, les liens de participation à la réunion et les ID de conférence de toutes les réunions existantes de ce type que l’utilisateur a démarrées ou planifiées expirent.

Par exemple, si une stratégie de réunion est affectée à un utilisateur dans laquelle ces paramètres de stratégie de réunion sont définis **sur Activé**, puis que vous désactivez le paramètre **Autoriser la réunion maintenant dans les canaux** , cet utilisateur ne peut plus démarrer de réunions impromptues dans les canaux, et le canal Meet now join liens que l’utilisateur a créés précédemment sont arrivés à expiration. L’utilisateur peut toujours démarrer et planifier d’autres types de réunions et participer à des réunions organisées par d’autres personnes.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>Que se passe-t-il lorsque le lien de participation à la réunion et l’ID de conférence expirent ?

Lorsque le lien de participation à la réunion et l’ID de conférence d’une réunion expirent, personne ne peut participer à la réunion. Lorsqu’un utilisateur tente de rejoindre la réunion par le biais du lien ou par téléphone, il reçoit un message indiquant que la réunion n’est plus disponible. Les conversations, fichiers, tableaux blancs, enregistrements, transcriptions et autres contenus liés à la réunion sont conservés et les utilisateurs peuvent toujours y accéder.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>Que se passe-t-il lorsque vous activez et désactivez un paramètre de stratégie de réunion ?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Désactiver un paramètre de stratégie de réunion

Lorsqu’un paramètre de stratégie de réunion est **activé, les** utilisateurs auxquels la stratégie est affectée peuvent démarrer ou planifier des réunions de ce type et tout le monde peut y participer. Lorsque vous basculez le paramètre de stratégie de réunion sur **Désactivé**, les utilisateurs auxquels la stratégie est affectée ne peuvent pas démarrer ou planifier de nouvelles réunions de ce type, et les liens de participation à la réunion et les ID de conférence des réunions existantes que l’utilisateur a planifiées précédemment ont expiré.

N’oubliez pas que l’utilisateur peut toujours participer à des réunions organisées par d’autres personnes.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Activer un paramètre de stratégie de réunion

Lorsque vous basculez un paramètre de stratégie de réunion de **désactivé** à **activé**, les utilisateurs auxquels la stratégie est affectée peuvent démarrer ou planifier des réunions de ce type. Si un paramètre de stratégie de réunion est désactivé, puis réactivé pour un utilisateur, toutes les réunions planifiées (et expirées) précédemment organisées par l’utilisateur deviennent actives et les personnes peuvent les rejoindre à l’aide du lien de participation à la réunion ou par téléphone.  

## <a name="meeting-expiration-scenarios"></a>Scénarios d’expiration de réunion

Voici un résumé du fonctionnement de l’expiration de la réunion pour chacun des paramètres de stratégie de réunion abordés dans cet article.

|Si vous voulez...&nbsp;&nbsp; |Procédez comme suit&nbsp;&nbsp;&nbsp;&nbsp;  |Comportement de la participation à une réunion&nbsp;&nbsp;&nbsp;&nbsp;  |
|---------------------------|---------------------|---------|
|Expirer des réunions de réunions privées maintenant démarrées par un utilisateur&nbsp;&nbsp;|Désactivez **La réunion maintenant dans les réunions privées**.&nbsp;&nbsp;|Personne ne peut participer à **la réunion privée maintenant** les réunions démarrées par l’utilisateur.|
|Faire expirer des réunions privées planifiées par un utilisateur&nbsp;&nbsp;|Désactivez **la planification de réunion privée** _et_ désactivez **Outlook complément**. &nbsp;&nbsp;|Personne ne peut participer à des réunions privées planifiées par l’utilisateur. Cela empêche les personnes de participer aux réunions suivantes :<ul><li>Réunions privées qui se sont produites dans le passé.</li><li>Réunions privées prévues pour l’avenir et qui n’ont pas encore eu lieu.</li><li>Instances futures de réunions privées périodiques.</li></ul><br>La **planification de réunion privée** et **le complément Outlook** doivent être désactivés pour expirer les réunions privées planifiées par un utilisateur. Si un paramètre est désactivé et que l’autre est activé, les liens de participation aux réunions et les ID de conférence des réunions existantes restent actifs et n’expireront pas.|
|Réunions **Expire channel Meet now** démarrées par un utilisateur&nbsp;&nbsp;|Désactivez **La réunion maintenant dans les canaux** _et_ désactivez la **planification des réunions de canal**.&nbsp;&nbsp;|Personne ne peut participer aux réunions **de canal Meet now** démarrées par l’utilisateur.|
|Expiration des réunions de canal planifiées par un utilisateur&nbsp;&nbsp;|Désactivez la **planification des réunions de canal**.&nbsp;&nbsp;|Personne ne peut participer aux réunions de canal planifiées par l’utilisateur. Cela empêche les personnes de participer aux réunions suivantes :<ul><li>Réunions de canal qui se sont produites dans le passé.</li><li>Réunions de canal prévues pour l’avenir et qui n’ont pas encore eu lieu.</li><li>Instances futures de réunions de canal périodiques.</li></ul>|

Si vous souhaitez que des personnes accèdent à des réunions précédemment planifiées ou démarrées par un utilisateur particulier, vous pouvez :

- Activez le paramètre de stratégie de réunion pour cet utilisateur.
- Désactivez le paramètre de stratégie de réunion pour cet utilisateur et un autre utilisateur pour lequel le paramètre de stratégie est activé créez une réunion pour remplacer la réunion expirée.

> [!NOTE]
> Si la réunion a été envoyée par un délégué, qui a reçu l’autorisation d’envoyer des invitations à la réunion pour le compte d’une autre personne, telle qu’un responsable, le paramètre de stratégie de réunion est appliqué à la personne qui a accordé l’autorisation (le responsable).

## <a name="changes-to-meeting-expiration"></a>Modifications apportées à l’expiration de la réunion

Tous les enregistrements de réunion de Teams nouvellement créés (TMR) ont une expiration par défaut de 120 jours. Cette option est activée par défaut pour tous les locataires. Cela signifie que par défaut, tous les TMR créés *après l’authentification de cette fonctionnalité* seront supprimés 120 jours après leur date de création. Les administrateurs peuvent également définir des réunions pour **ne jamais expirer automatiquement**. Le système OneDrive et SharePoint surveille la date d’expiration définie sur tous les TMR et déplace automatiquement les TMR vers la corbeille à leur date d’expiration.

> [!NOTE]
> Une copie de la transcription de la réunion est enregistrée dans OneDrive SharePoint et une deuxième copie est enregistrée dans Exchange dans un stockage temporaire. La copie OSDP expire lorsque le TMR expire automatiquement.

L’expiration automatique des réunions est un mécanisme de nettoyage léger pour réduire l’encombrement du stockage créé par les anciens TMR. En moyenne, sur tous les clients, 96 % des TMR ne sont pas surveillés après 60 jours et 99 % ne sont pas surveillés après 110 jours. Nous pensons que presque tous les clients bénéficieront de la réduction de la charge de stockage sur leur locataire en supprimant les enregistrements qui ne seront probablement plus regardés après 60 jours. Notre objectif est de fournir une expérience aussi propre que possible à tous les clients par défaut.

Utilisez l’expiration de la réunion pour limiter les OneDrive ou les SharePoint pour la consommation de stockage cloud pilotée par Teams enregistrements de réunion. Un enregistrement de réunion classique consomme environ 400 Mo par heure d’enregistrement.

> [!NOTE]
> La date d’expiration par défaut maximale pour les utilisateurs A1 est de 30 jours.

### <a name="expiration-date"></a>Date d’expiration

- La date d’expiration est calculée comme le **jour de sa création**, ainsi que le **nombre de jours par défaut défini dans la stratégie Teams par l’administrateur**.
- La lecture n’a pas d’impact sur la date d’expiration.

### <a name="change-the-default-expiration-date"></a>Modifier la date d’expiration par défaut

Les administrateurs peuvent modifier le paramètre d’expiration par défaut dans PowerShell ou le centre d’administration Teams. Toutes les modifications n’auront d’effet que sur les tmrs *nouvellement créés* à partir de ce point. Il n’aura aucun impact sur les enregistrements créés avant cette date. Les administrateurs ne peuvent pas modifier la date d’expiration sur les TMR existants. Cette opération est effectuée pour protéger la décision de l’utilisateur propriétaire du TMR. Les réunions et les appels peuvent être contrôlés par ce paramètre.

La valeur de la date d’expiration peut être définie comme suit :

- Valeur minimale : **1 jour**
- Valeur maximale : **99 999 jours**
- Vous pouvez également définir la date d’expiration sur **-1** afin que les enregistrements n’expirent jamais.

Exemple de commande PowerShell :

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

Vous pouvez définir la date d’expiration dans le centre d’administration Teams sous **Stratégies de réunion.** Une fois que vous avez activé **réunions expirer automatiquement,** vous aurez la possibilité de définir une expiration d’enregistrement.

![Administration capture d’écran du centre de la stratégie d’expiration de la réunion.](media/meeting-expiration-policy.jpg)

### <a name="security-and-compliance"></a>Sécurité et conformité

#### <a name="should-i-rely-on-this-feature-for-strict-security-and-compliance-adherence"></a>Dois-je m’appuyer sur cette fonctionnalité pour un respect strict de la sécurité et de la conformité ?

Non, vous ne devez pas vous fier à cela pour la protection légale, car les utilisateurs finaux peuvent modifier la date d’expiration des enregistrements qu’ils contrôlent.

#### <a name="will-a-retention-andor-deletion-policy-ive-set-in-the-security--compliance-center-override-the-teams-meeting-recording-expiration-setting"></a>Une stratégie de rétention et/ou de suppression que j’ai définie dans le Centre de sécurité & conformité remplacera-t-elle le paramètre d’expiration de l’enregistrement de la réunion Teams ?

Oui, toutes les stratégies que vous avez définies dans le centre de conformité sont prioritaires.

Par exemple :

- Si vous disposez d’une stratégie indiquant que tous les fichiers d’un site doivent être conservés pendant 100 jours et que le paramètre d’expiration d’un enregistrement de réunion Teams est de 30 jours, l’enregistrement est conservé pendant les 100 jours complets.
- Si vous avez une stratégie de suppression indiquant que tous les enregistrements de réunion Teams seront supprimés après cinq jours et que vous disposez d’un paramètre d’expiration pour un enregistrement de réunion Teams de 30 jours, l’enregistrement sera supprimé après cinq jours.

### <a name="will-this-feature-enforce-file-retention"></a>Cette fonctionnalité appliquera-t-elle la rétention des fichiers ?

Non, les fichiers ne seront pas conservés en raison de cette fonctionnalité ou de ses paramètres. Si un utilisateur disposant d’autorisations de suppression tente de supprimer un TMR dont le paramètre d’expiration est défini, l’action de suppression de cet utilisateur ’ est exécutée.

### <a name="what-skus-are-required-for-this-feature"></a>Quelles sont les références SKU requises pour cette fonctionnalité ?

- Toutes les références SKU auront cette fonctionnalité par défaut.
- Les utilisateurs A1 ont la valeur par défaut sur une période d’expiration maximale de 30 jours, mais ils peuvent modifier la date d’expiration en fonction des besoins.

### <a name="what-if-i-want-the-admin-to-have-full-control-over-the-lifecycle-of-meeting-recordings-and-dont-want-to-give-end-users-the-ability-to-override-the-expiration-date"></a>Que se passe-t-il si je veux que l’administrateur ait un contrôle total sur le cycle de vie des enregistrements de réunion et ne souhaite pas donner aux utilisateurs finaux la possibilité de remplacer la date d’expiration ?

Nous vous recommandons d’utiliser les stratégies de conservation et/ou de suppression de sécurité et de conformité. Cette offre vise à résoudre des problèmes juridiques d’administration complexes basés sur des stratégies et des contrats SLA.

La fonctionnalité d’expiration automatique est uniquement conçue comme un mécanisme de nettoyage léger pour réduire l’encombrement du stockage créé à partir des anciens enregistrements de réunion Teams.

### <a name="will-future-tmrs-migrated-from-classic-stream-after-this-feature-is-released-have-auto-expiration-applied-to-them-too"></a>L’expiration automatique sera-t-elle également appliquée aux futures tmrs migrées à partir de Classic Stream après la publication de cette fonctionnalité ?

Non, les tmrs migrés ne sont pas fournis avec un délai d’expiration défini sur eux. Au lieu de cela, nous encourageons les administrateurs à migrer uniquement les TMR qu’ils souhaitent conserver. Vous trouverez plus de détails dans la documentation de migration.

### <a name="how-is-this-feature-different-from-the-expiration-message-i-see-when-a-tmr-upload-to-onedrive-and-sharepoint-fails"></a>En quoi cette fonctionnalité diffère-t-elle du message d’expiration que je vois lorsqu’un chargement TMR vers OneDrive et SharePoint échoue ?

Lorsqu’un enregistrement ne parvient pas à être téléchargé vers OneDrive ou SharePoint, l’application Teams affiche un message dans la conversation indiquant que les utilisateurs disposent de 21 jours pour télécharger le TMR avant qu’il ne soit définitivement supprimé du serveur Teams. Cette expérience d’expiration existante due à l’échec des chargements TMR n’est pas liée à la OneDrive et SharePoint fonctionnalité d’expiration automatique présentée dans le document d’aide.

### <a name="how-do-i-know-the-distribution-of-tmr-playbacks-so-i-know-what-the-optimal-auto-expiration-default-should-be-for-my-tenant"></a>Comment faire connaître la distribution des playbacks TMR afin de savoir ce que la valeur par défaut d’expiration automatique optimale doit être pour mon locataire ?

1. Recherchez la vidéo dans la bibliothèque.
1. Sélectionnez **...** >  **Détails**
1. Sélectionnez le nombre de vues en haut du volet d’informations.

Vous verrez des statistiques de fichier qui montrent :

- Nombre de visionneuses uniques
- Nombre total de vues
- Tendance des téléspectateurs et des affichages au jour le jour au cours des 90 derniers jours
- Rétention de la visionneuse (quelle partie de la vidéo a été consultée ou non)

### <a name="when-will-the-file-be-deleted"></a>Quand le fichier sera-t-il supprimé ?

Le fichier sera supprimé dans les cinq jours suivant la date d’expiration, bien qu’il ne s’agit pas d’une garantie stricte. Le propriétaire du fichier reçoit une notification par e-mail lorsque l’enregistrement expire et est dirigé vers la corbeille pour récupérer l’enregistrement.

> [!NOTE]
> À la date d’expiration, l’enregistrement est déplacé dans la corbeille et le champ date d’expiration est effacé. Si vous récupérez l’enregistrement à partir de la corbeille, il ne sera plus supprimé par cette fonctionnalité, car la date d’expiration a été effacée.

## <a name="related-topics"></a>Voir aussi

[Modifier la date d’expiration de la réunion - Contrôles de l’utilisateur final](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[Gérer les stratégies de réunion dans Teams](meeting-policies-overview.md)

[Attribuer des stratégies à vos utilisateurs](policy-assignment-overview.md)

[Présentation de Teams PowerShell](teams-powershell-overview.md)

[Limites et spécifications de Microsoft Teams](/microsoftteams/limits-specifications-teams)
