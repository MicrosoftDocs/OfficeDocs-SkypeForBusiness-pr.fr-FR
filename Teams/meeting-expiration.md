---
title: Stratégies de réunion et expiration de la réunion dans Microsoft teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Découvrez comment utiliser les paramètres de stratégie de réunion pour contrôler l’expiration de la réunion dans Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e25ea1c55890a78e9e492dd2c2dd419a6ed34f2
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640978"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Stratégies de réunion et expiration de la réunion dans Microsoft teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Vue d’ensemble

Les [stratégies de réunion](meeting-policies-in-teams.md) dans Microsoft teams permettent de contrôler si les utilisateurs de votre organisation peuvent démarrer et planifier des réunions et les fonctionnalités qui sont disponibles pour les réunions planifiées par les utilisateurs. Vous pouvez utiliser la stratégie globale par défaut de l’organisation ou créer et attribuer des stratégies personnalisées. Vous pouvez gérer les stratégies de réunion dans le centre d’administration Microsoft teams ou à [Set](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)l’aide [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmeetingpolicy) [des](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)applets [de CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingpolicy)PowerShell. [Grant](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy)

Les paramètres de stratégie de la réunion qui contrôlent les heures de début et de planification des réunions contrôlent également l’expiration des réunions planifiées par les utilisateurs. Lorsqu’un lien de participation à une réunion ou un ID de conférence d’une réunion expire, personne ne peut rejoindre la réunion. Les paramètres de stratégie de réunion suivants déterminent si les utilisateurs peuvent démarrer et planifier des réunions dans teams et s’y référer dans cet article.

- [Autoriser la Conférence maintenant dans les canaux](meeting-policies-in-teams.md#allow-meet-now-in-channels): contrôle si un utilisateur peut démarrer une réunion improvisée dans un canal.
- [Autoriser la planification des réunions de canal](meeting-policies-in-teams.md#allow-channel-meeting-scheduling): contrôle si un utilisateur peut planifier une réunion dans un canal.
- [Autoriser la planification de réunions privées](meeting-policies-in-teams.md#allow-scheduling-private-meetings): détermine si un utilisateur peut planifier une réunion privée dans Teams. Une réunion est privée lorsque celle-ci n’est pas publiée sur un canal d’une équipe.
- [Autoriser le complément Outlook](meeting-policies-in-teams.md#allow-the-outlook-add-in): contrôle si un utilisateur peut planifier une réunion privée à partir d’Outlook. Une réunion est privée lorsque celle-ci n’est pas publiée sur un canal d’une équipe.
- [Autoriser la Conférence maintenant dans les réunions privées](meeting-policies-in-teams.md#allow-meet-now-in-private-meetings): détermine si un utilisateur peut démarrer une réunion privée improvisée.

Par défaut, ces paramètres sont activés. Lorsque l’un de ces paramètres est désactivé, tout utilisateur affecté à la stratégie ne peut pas démarrer ou planifier de nouvelles réunions de ce type. En même temps, les liens et les ID de conférences de toutes les réunions existantes dont l’utilisateur a commencé ou prévu ont expiré.

Par exemple, si une stratégie de réunion est **affectée à un**utilisateur et que vous désactivez le paramètre autoriser les conférences **dans les canaux** , cela signifie que l’utilisateur ne peut plus lancer de réunions impromptues dans les canaux, et que le canal rencontrent désormais des liens que l’utilisateur a précédemment créés. L’utilisateur peut toujours commencer et planifier d’autres types de réunion et participer à des réunions organisées par d’autres personnes.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>Que se passe-t-il lorsque le lien de participation à la réunion et l’ID de conférence arrivent à expiration ?

Lorsque le lien de participation à la réunion et l’ID de conférence d’une réunion expirent, personne ne peut participer à la réunion. Lorsqu’un utilisateur tente de participer à la réunion par le biais du lien ou par téléphone, il reçoit un message indiquant que la réunion n’est plus disponible. Les conversations, les fichiers, les tableaux blancs, les enregistrements, les transcriptions et d’autres contenus liés à la réunion sont conservés et les utilisateurs peuvent toujours y accéder.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>Que se passe-t-il lorsque vous activez et désactivez un paramètre de stratégie de réunion ?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Basculer un paramètre de stratégie de réunion de activé à désactivé

Lorsque le paramètre d’une stratégie de réunion est défini **sur activé**, les utilisateurs auxquels la stratégie est affectée peuvent commencer ou planifier des réunions de ce type, et tout le monde peut y participer. Lorsque vous basculez le paramètre de stratégie de la réunion sur **désactivé**, les utilisateurs auxquels la stratégie est affectée ne peuvent pas commencer ou planifier de nouvelles réunions de ce type, et les liens de la réunion et les ID de conférence des réunions existantes que l’utilisateur a déjà planifiées sont arrivés à expiration.

Gardez à l’esprit que l’utilisateur peut quand même participer à des réunions organisées par d’autres personnes.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Basculer un paramètre de stratégie de réunion de désactivé à activé

Lorsque vous basculez un paramètre de stratégie de réunion de **désactivé** à **activé**, les utilisateurs qui ont reçu la stratégie pourront commencer ou planifier des réunions de ce type. S’il s’agit d’un paramètre de stratégie de réunion désactivé et réactivé pour un utilisateur, toutes les réunions précédemment programmées (et expirées) organisées par l’utilisateur deviennent actives, et les utilisateurs peuvent y accéder à l’aide du lien de participation à la réunion ou par téléphone.  

## <a name="meeting-expiration-scenarios"></a>Scénarios d’expiration de réunion

Vous trouverez ci-dessous un résumé du fonctionnement de l’expiration de la réunion pour chacun des paramètres de stratégie de réunion mentionnés dans cet article. 

|Si vous souhaitez... |Procédez comme suit…  |Comportement de participation à une réunion  |
|---------|---------|---------|
|Date d’expiration du canal Conférence maintenant démarrée par un utilisateur  |Désactivez **l’option autoriser la Conférence maintenant dans les canaux**.|Personne ne peut rejoindre un canal organiser des réunions désormais lancées par l’utilisateur.         |
|Expiration des réunions de canal planifiées par un utilisateur   |Désactivez l’option **autoriser la planification des réunions de canal**.         |Personne ne peut participer à des réunions de canal planifiées par l’utilisateur. Cela empêche les utilisateurs de rejoindre ce qui suit :<ul><li>Réunions de canal passées par le passé.</li> <li>Réunions de canal planifiées pour le futur et qui n’ont pas encore été effectuées.</li><li>Instances futures des réunions de canal périodiques.</li></ul>       |
|Expiration des réunions privées planifiées par un utilisateur    |Désactivez l’option **autoriser la planification de réunions privées** *et* désactivez **l’option autoriser le complément Outlook**.          |Personne ne peut participer à des réunions privées planifiées par l’utilisateur. Cela empêche les utilisateurs de rejoindre ce qui suit : <ul><li>Réunions privées effectuées auparavant.</li> <li>Réunions privées planifiées pour le futur et qui n’ont pas encore été effectuées.</li><li>Instances futures de réunions privées périodiques.</li></ul> Les deux **permettent de planifier des réunions privées** et de ne pas **autoriser le complément Outlook** à expirer les réunions privées planifiées par un utilisateur. Si l’un des deux paramètres est désactivé et l’autre est activé, les liens de participation à la réunion et les ID de conférence des réunions existantes resteront actifs et ne seront pas expirés.      |
|Faire expirer les réunions de Conférence maintenant privées démarrées par un utilisateur  |Désactivez **l’option autoriser la Conférence maintenant dans les réunions privées**.          |Personne ne peut participer à des réunions privées Conférence maintenant démarrées par l’utilisateur.         |

Si vous souhaitez que les utilisateurs accèdent à des réunions déjà planifiées ou démarrées par un utilisateur particulier, vous pouvez :

- Activez le paramètre de stratégie de réunion pour cet utilisateur.
- Désactivez le paramètre de stratégie de réunion pour cet utilisateur et demandez à un autre utilisateur qui dispose du paramètre de stratégie d’activer l’option créer une nouvelle réunion pour remplacer la réunion expirée.

> [!NOTE]
> Si la réunion a été envoyée par un délégué, qui dispose des autorisations d’envoi d’invitations à une réunion au nom d’une autre personne, par exemple un responsable, le paramètre de stratégie de réunion est appliqué à la personne qui a accordé l’autorisation (le responsable).

## <a name="related-topics"></a>Voir aussi

[Gérer les stratégies de réunion dans teams](meeting-policies-in-teams.md)

[Attribuer des stratégies à vos utilisateurs dans teams](assign-policies.md)

[Présentation de Teams PowerShell](teams-powershell-overview.md)