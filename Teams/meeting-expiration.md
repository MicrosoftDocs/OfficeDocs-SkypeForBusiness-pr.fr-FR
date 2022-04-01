---
title: Stratégies de réunion et expiration des réunions dans Microsoft Teams
author: KarliStites
ms.author: kastites
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
description: Découvrez comment utiliser les paramètres de stratégie de réunion pour contrôler l’expiration d’une réunion Microsoft Teams.
ms.openlocfilehash: ed76ea0278cdbf8a00bbd0d3e8434103aad2f270
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592809"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Stratégies de réunion et expiration des réunions dans Microsoft Teams

[](meeting-policies-overview.md) Les stratégies de réunion dans Microsoft Teams sont utilisées pour contrôler si les utilisateurs de votre organisation peuvent démarrer et planifier des réunions, ainsi que les fonctionnalités disponibles aux participants à la réunion pour les réunions qui sont programmées par les utilisateurs. Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et attribuer des stratégies personnalisées. Vous gérez les stratégies de réunion dans le Microsoft Teams d’administration ou à l’aide des cmdlets PowerShell [Get](/powershell/module/skype/get-csteamsmeetingpolicy), [New](/powershell/module/skype/new-csteamsmeetingpolicy), [Set](/powershell/module/skype/set-csteamsmeetingpolicy), [Remove](/powershell/module/skype/remove-csteamsmeetingpolicy), [Grant](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy.

Les paramètres de stratégie de réunion qui contrôlent si les utilisateurs peuvent commencer et planifier des réunions, et contrôler également l’expiration des réunions programmées par les utilisateurs. Lorsqu’un lien de connexion à une réunion et l’ID de conférence d’une réunion expirent, personne ne peut y participer. Les paramètres de stratégie de réunion suivants déterminent si les utilisateurs peuvent démarrer et planifier des réunions dans Teams. Nous abordons les paramètres de la réunion dans cet article.

- [Conférence maintenant dans les canaux](meeting-policies-in-teams-general.md#meet-now-in-channels) : contrôle si un utilisateur peut démarrer une réunion improvisée dans un canal.
- [Planification des réunions de canal](meeting-policies-in-teams-general.md#channel-meeting-scheduling) : contrôle si un utilisateur peut planifier une réunion dans un canal.
- [Planification de réunion privée](meeting-policies-in-teams-general.md#private-meeting-scheduling) : contrôle si un utilisateur peut planifier une réunion privée dans Teams. Une réunion est privée lorsque celle-ci n’est pas publiée dans un canal d’une équipe.
- [Outlook : contrôle si](meeting-policies-in-teams-general.md#outlook-add-in) un utilisateur peut planifier une réunion privée à partir d’Outlook. Une réunion est privée lorsque celle-ci n’est pas publiée dans un canal d’une équipe.
- [Se réunir maintenant dans des réunions privées](meeting-policies-in-teams-general.md#meet-now-in-private-meetings) : contrôle si un utilisateur peut démarrer une réunion privée improvisée.

Par défaut, ces paramètres sont sous.jour. Lorsque l’un de ces paramètres est désactivé, tout utilisateur affecté à la stratégie ne peut pas démarrer ni planifier de nouvelles réunions de ce type. En même temps, la réunion joint les liens et les ID de conférence de toutes les réunions existantes de ce type que l’utilisateur a précédemment commencées ou dont l’expiration a été programmée.

Par exemple, si un utilisateur se voit attribuer une stratégie de réunion dans laquelle ces paramètres de stratégie de réunion sont réglés sur **Activer, puis** que vous désactiverez le paramètre Autoriser la réunion maintenant dans les canaux, cet utilisateur ne peut plus démarrer de réunions improvisées dans les canaux et le canal Conférence maintenant joint les liens que l’utilisateur a créés précédemment a expiré. L’utilisateur peut toujours commencer et planifier d’autres types de réunions et participer à des réunions organisées par d’autres personnes.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>Que se passe-t-il lorsque le lien d’entrée et l’ID de conférence expirent ?

Lorsque le lien d’adhésion à la réunion et l’ID de conférence d’une réunion expirent, personne ne peut y participer. Lorsqu’un utilisateur tente de participer à la réunion via le lien ou par téléphone, il reçoit un message lui indique que la réunion n’est plus disponible. Les conversations, fichiers, tableaux blancs, enregistrements, transcriptions et autres contenus liés à la réunion sont conservés et les utilisateurs peuvent toujours y accéder.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>Que se passe-t-il lorsque vous activer et désactiver un paramètre de stratégie de réunion ?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Passer d’un paramètre de stratégie de réunion à un paramètre de réunion

Lorsqu’un paramètre de stratégie de réunion est réglé sur **On, les** utilisateurs à qui la stratégie est attribuée peuvent démarrer ou planifier des réunions de ce type et tout le monde peut y participer. Lorsque vous basculez le paramètre de stratégie de réunion sur **Non, les** utilisateurs à qui la stratégie est attribuée ne peuvent pas démarrer ou planifier de nouvelles réunions de ce type, et les liens de participer à la réunion et les ID de conférence des réunions existantes précédemment programmées par l’utilisateur ont expiré.

Gardez à l’esprit que l’utilisateur peut toujours participer à des réunions organisées par d’autres personnes.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Passer d’un paramètre de stratégie de réunion à un paramètre de réunion

Lorsque vous basculez d’un paramètre  de stratégie de réunion d’Off à **On**, les utilisateurs à qui la stratégie est attribuée peuvent démarrer ou planifier des réunions de ce type. Si un paramètre de stratégie de réunion est désactivé, puis réorganisé pour un utilisateur, toutes les réunions précédemment programmées (et expirées) organisées par l’utilisateur deviennent actives et les personnes peuvent les rejoindre à l’aide du lien d’accès à la réunion ou par téléphone.  

## <a name="meeting-expiration-scenarios"></a>Scénarios d’expiration de réunion

Voici un résumé du fonctionnement de l’expiration des réunions pour chacun des paramètres de stratégie de réunion évoqués dans cet article.

|Si vous souhaitez...&nbsp;&nbsp; |Pour ce faire,&nbsp;&nbsp;&nbsp;&nbsp;  |Comportement d’adhésion à une réunion&nbsp;&nbsp;&nbsp;&nbsp;  |
|---------------------------|---------------------|---------|
|Expiration des réunions Conférence maintenant privées démarrées par un utilisateur&nbsp;&nbsp;|Désactiver Conférence **maintenant dans les réunions privées**.&nbsp;&nbsp;|Personne ne peut participer à des réunions **Privées Conférence maintenant** démarrées par l’utilisateur.|
|Expiration des réunions privées programmées par un utilisateur&nbsp;&nbsp;|Désactiver la **planification de réunion** _privée et désactiver_ **Outlook-in**. &nbsp;&nbsp;|Personne ne peut participer à des réunions privées programmées par l’utilisateur. Cela empêche les personnes de participer aux réunions suivantes :<ul><li>Réunions privées qui se sont déjà produites dans le passé.</li><li>Réunions privées prévues pour l’avenir et qui ne se sont pas encore produites.</li><li>Prochaines instances de réunions privées périodiques.</li></ul><br>La **planification des réunions** privées et **Outlook le** plus doivent être éteints pour expirer les réunions privées prévues par un utilisateur. Si l’un des paramètres est éteint et que l’autre est actif, les liens de participation à des réunions et les ID de conférence des réunions existantes restent actifs et ne sont pas expirés.|
|Expire channel **Meet now** meetings started by a user&nbsp;&nbsp;|Désactiver Conférence **maintenant dans les canaux** _et_ désactiver la planification des réunions **du canal**.&nbsp;&nbsp;|Personne ne peut rejoindre les réunions **Conférence maintenant** du canal commencées par l’utilisateur.|
|Expiration des réunions de canal prévues par un utilisateur&nbsp;&nbsp;|Désactiver la **planification des réunions du canal**.&nbsp;&nbsp;|Personne ne peut participer aux réunions de canal programmées par l’utilisateur. Cela empêche les personnes de participer aux réunions suivantes :<ul><li>Réunions de canal qui se sont déjà produites dans le passé.</li><li>Réunions de canal prévues pour l’avenir et qui ne se sont pas encore produites.</li><li>Prochaines instances de réunions de canal périodiques.</li></ul>|

Si vous souhaitez que les personnes accèdent à des réunions précédemment programmées ou démarrées par un utilisateur particulier, vous pouvez :

- Activer le paramètre de stratégie de réunion pour cet utilisateur.
- Désactiver le paramètre de stratégie de réunion pour cet utilisateur et permettre à un autre utilisateur dont le paramètre de stratégie est activé de créer une réunion en remplacement de la réunion expirée.

> [!NOTE]
> Si la réunion a été envoyée par un délégué, qui a reçu l’autorisation d’envoyer des invitations à la réunion au nom d’une autre personne( par exemple, un responsable), le paramètre de stratégie de réunion est appliqué à la personne qui a accordé l’autorisation (le responsable).

## <a name="changes-to-meeting-expiration"></a>Modifications apportées à l’expiration d’une réunion

Tous les enregistrements des Teams de réunion nouvellement créés ont une durée d’expiration de 120 jours. Cette option est optionnée par défaut pour tous les locataires. Cela signifie que, par défaut, tous les tmrs créés après l’option seront supprimés 120 jours après la date de création. Les administrateurs peuvent également configurer les réunions pour **qu’ils n’expirent jamais automatiquement**. Le OneDrive et SharePoint de contrôle des détails des tmrs surveille la date d’expiration définie sur toutes les tmrs et déplace automatiquement les tmR vers la Corbeille à la date d’expiration.

> [!NOTE]
> Une copie de la transcription de la réunion est enregistrée dans OneDrive SharePoint et une deuxième copie dans Exchange stockage temporaire. La copie du système d’exploitation expire lorsque la copie automatique de tmR arrive à expiration.

L’expiration automatique des réunions est un mécanisme de tâches de tâches léger qui permet de réduire l’encombrement du stockage créé par les anciennes tmRs. En moyenne, sur l’ensemble des clients, 96 % des tmrs ne sont pas regardés après 60 jours et 99 % ne le sont pas après 110 jours. Nous pensons que presque tous les clients bénéficieront de la charge de stockage réduite sur leur client en supprimant les enregistrements qui ne seront probablement pas regardés à nouveau après 60 jours. Notre objectif est d’offrir par défaut une expérience aussi propre que possible à tous les clients.

Utilisez l’expiration d’une réunion pour limiter OneDrive ou SharePoint la consommation de stockage cloud, pilotée par Teams enregistrements de réunion. L’enregistrement d’une réunion classique consomme environ 400 Mo par heure d’enregistrement.

> [!NOTE]
> La date d’expiration par défaut maximale pour les utilisateurs A1 est de 30 jours.

### <a name="expiration-date"></a>Date d’expiration

- La date d’expiration est calculée en tant que jour de **création, ainsi** que le nombre de jours par défaut Teams la stratégie par **l’administrateur**.
- La lecture n’a aucun impact sur la date d’expiration.

### <a name="change-the-default-expiration-date"></a>Modifier la date d’expiration par défaut

Les administrateurs peuvent modifier le paramètre d’expiration par défaut dans PowerShell ou le Teams d’administration. Les modifications n’auront d’effet *que sur les* tmR nouvellement créées à partir de ce point. Les enregistrements créés avant cette date n’auront aucun impact. Les administrateurs ne peuvent pas modifier la date d’expiration des tmrs existants. Cela permet de protéger la décision de l’utilisateur propriétaire de la tmR. Ces deux paramètres contrôlent les réunions et les appels.

La valeur de date d’expiration peut être définie comme suit :

- Valeur minimale : **1 jour**
- Valeur maximale : **99 999 jours**
- Vous pouvez également définir la date d’expiration sur **-1 afin** que les enregistrements n’expirent jamais.

Exemple de commande PowerShell :

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

Vous pouvez définir la date d’expiration dans le centre Teams d’administration sous **Stratégies de réunion.** Une fois que vous avez activer **l’option Réunions expirer automatiquement,** vous avez la possibilité de définir l’expiration d’un enregistrement.

![Capture d’écran du Centre d’administration de la stratégie d’expiration des réunions.](media/meeting-expiration-policy.jpg)

### <a name="security-and-compliance"></a>Sécurité et conformité

#### <a name="should-i-rely-on-this-feature-for-strict-security-and-compliance-adherence"></a>Dois-je m’appuyer sur cette fonctionnalité pour respecter strictement la sécurité et la conformité ?

Non, vous ne devez pas vous baser sur cette protection juridique, car les utilisateurs finaux peuvent modifier la date d’expiration de tous les enregistrements qu’ils contrôlent.

#### <a name="will-a-retention-andor-deletion-policy-ive-set-in-the-security--compliance-center-override-the-teams-meeting-recording-expiration-setting"></a>Une stratégie de rétention et/ou de suppression définie dans le Centre de sécurité et conformité & remplace-t-elle le paramètre d’expiration de l’enregistrement Teams réunion ?

Oui, toutes les stratégies que vous avez définies dans le Centre de conformité sont prioritaire.

Par exemple :

- Si vous avez une stratégie qui indique que tous les fichiers d’un site doivent être conservés pendant 100 jours et que le paramètre d’expiration pour un enregistrement de réunion Teams est de 30 jours, l’enregistrement est conservé pendant 100 jours.
- Si vous avez une stratégie de suppression qui indique que tous les enregistrements de réunion Teams seront supprimés au bout de cinq jours et que vous avez un paramètre d’expiration pour un enregistrement de réunion Teams de 30 jours, l’enregistrement sera supprimé au bout de cinq jours.

### <a name="will-this-feature-enforce-file-retention"></a>Cette fonctionnalité appliquera-t-elle la rétention des fichiers ?

Non, les fichiers ne sont pas conservés en raison de cette fonctionnalité ou de ses paramètres. Si un utilisateur disposant d’autorisations de suppression tente de supprimer un TMR dont le paramètre d’expiration est défini, l’action de suppression de cet utilisateur ’ est exécutée.

### <a name="what-skus-are-required-for-this-feature"></a>Quelles sont les références SKU requises pour cette fonctionnalité ?

- Toutes les références SKU auront cette fonctionnalité par défaut.
- La valeur par défaut des utilisateurs A1 est une période d’expiration de 30 jours au maximum, mais ils peuvent modifier la date d’expiration selon les besoins.

### <a name="what-if-i-want-the-admin-to-have-full-control-over-the-lifecycle-of-meeting-recordings-and-dont-want-to-give-end-users-the-ability-to-override-the-expiration-date"></a>Que faire si je souhaite que l’administrateur contrôle entièrement le cycle de vie des enregistrements des réunions et que je ne souhaite pas donner aux utilisateurs finaux la possibilité de remplacer la date d’expiration ?

Nous vous recommandons d’utiliser les stratégies de rétention et/ou de suppression des services de sécurité et conformité. Cette offre vise à résoudre des problèmes juridiques d’administration complexes basés sur des stratégies et des contrats SLA.

La fonctionnalité d’expiration automatique est uniquement destinée à un mécanisme de réparation légère afin de réduire l’encombrement du stockage créé à partir d’Teams d’anciennes réunions.

### <a name="will-future-tmrs-migrated-from-classic-stream-after-this-feature-is-released-have-auto-expiration-applied-to-them-too"></a>L’expiration automatique sera-t-elle également appliquée aux futures tmrs migrées à partir de Classic Stream après la publication de cette fonctionnalité ?

Non, les tmrs migrés ne sont pas fournis avec un délai d’expiration défini sur eux. Au lieu de cela, nous encourageons les administrateurs à migrer uniquement les TMR qu’ils souhaitent conserver. Vous trouverez plus de détails dans la documentation de migration.

### <a name="how-is-this-feature-different-from-the-expiration-message-i-see-when-a-tmr-upload-to-onedrive-and-sharepoint-fails"></a>En quoi cette fonctionnalité est-elle différente du message d’expiration qui s’OneDrive en cas d’échec d’une SharePoint TMR ?

Lorsqu’un enregistrement ne parvient pas à être téléchargé sur OneDrive ou SharePoint, l’application Teams affiche un message dans la conversation que les utilisateurs ont jusqu’à 21 jours pour télécharger la tmR avant sa suppression définitive du serveur Teams. Cette expérience d’expiration existante en raison de l’échec des téléchargements de TMR n’est pas liée à la fonctionnalité d’expiration automatique OneDrive et SharePoint abordée dans le document d’aide.

### <a name="how-do-i-know-the-distribution-of-tmr-playbacks-so-i-know-what-the-optimal-auto-expiration-default-should-be-for-my-tenant"></a>Comment faire de connaître la distribution des lectures par TMR. Je sais donc quelles sont les valeurs par défaut d’expiration automatique optimales pour mon client ?

1. Recherchez la vidéo dans la bibliothèque.
1. **Sélectionnez ...** >  **Détails**
1. Sélectionnez le nombre d’affichages dans la partie supérieure du volet d’informations.

Les statistiques des fichiers qui s’afficheront sont les les plus récentes :

- Le nombre de visionneuses uniques
- Nombre total de vues
- Tendance des visionneuses et des affichages au jour le jour au cours des 90 derniers jours
- Rétention de la visionneuse (partie de la vidéo qui a été vue ou non)

## <a name="related-topics"></a>Sujets associés

[Modifier la date d’expiration des réunions - Contrôles de l’utilisateur final](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[Gérer les stratégies de réunion dans Teams](meeting-policies-overview.md)

[Attribuer des stratégies à vos utilisateurs](policy-assignment-overview.md)

[Présentation de Teams PowerShell](teams-powershell-overview.md)


