---
title: Stratégies de réunion et expiration des réunions dans Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej
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
ms.openlocfilehash: 484a873e319a6af46640f8eb3b17a5edc7c175e2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843987"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Stratégies de réunion et expiration des réunions dans Microsoft Teams

[](meeting-policies-overview.md) Les stratégies de réunion dans Microsoft Teams sont utilisées pour contrôler si les utilisateurs de votre organisation peuvent démarrer et planifier des réunions, ainsi que les fonctionnalités disponibles pour les participants à la réunion qui sont programmées par les utilisateurs. Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) ou créer et attribuer des stratégies personnalisées. Vous gérez les stratégies de réunion dans le Microsoft Teams d’administration ou à l’aide des cmdlets PowerShell [Get,](/powershell/module/skype/get-csteamsmeetingpolicy) [New,](/powershell/module/skype/new-csteamsmeetingpolicy) [Set,](/powershell/module/skype/set-csteamsmeetingpolicy) [Remove,](/powershell/module/skype/remove-csteamsmeetingpolicy) [Grant](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy PowerShell.

Les paramètres de stratégie de réunion qui contrôlent si les utilisateurs peuvent commencer et planifier des réunions, et contrôler également l’expiration des réunions programmées par les utilisateurs. Lorsqu’un lien de connexion à une réunion et l’ID de conférence d’une réunion expirent, personne ne peut y participer. Les paramètres de stratégie de réunion suivants déterminent si les utilisateurs peuvent commencer et planifier des réunions dans Teams. Nous abordons les paramètres de la réunion dans cet article.

- [Autoriser la conférence maintenant dans les canaux](meeting-policies-in-teams-general.md#allow-meet-now-in-channels): contrôle si un utilisateur peut démarrer une réunion improvisée dans un canal.
- [Autoriser la planification de réunions de canal](meeting-policies-in-teams-general.md#allow-channel-meeting-scheduling): contrôle si un utilisateur peut planifier une réunion dans un canal.
- [Autoriser la planification de réunions privées](meeting-policies-in-teams-general.md#allow-scheduling-private-meetings): contrôle si un utilisateur peut planifier une réunion privée dans Teams. Une réunion est privée lorsque celle-ci n’est pas publiée dans un canal d’une équipe.
- [Autoriser la Outlook d’ajout](meeting-policies-in-teams-general.md#allow-the-outlook-add-in): contrôle si un utilisateur peut planifier une réunion privée à partir d’Outlook. Une réunion est privée lorsque celle-ci n’est pas publiée dans un canal d’une équipe.
- [Autoriser la réunion maintenant dans les réunions privées](meeting-policies-in-teams-general.md#allow-meet-now-in-private-meetings): contrôle si un utilisateur peut commencer une réunion privée improvisée.

Par défaut, ces paramètres sont sous.jour. Lorsque l’un de ces paramètres est désactivé, tout utilisateur affecté à la stratégie ne peut pas démarrer ni planifier de nouvelles réunions de ce type. En même temps, la réunion joint les liens et les ID de conférence de toutes les réunions existantes de ce type que l’utilisateur a précédemment commencées ou dont l’expiration a été programmée.

Par exemple, si un utilisateur se voit attribuer une stratégie de réunion dans laquelle  ces paramètres de stratégie de réunion sont réglés sur **Activer,** puis que vous désactiverez le paramètre Autoriser la réunion maintenant dans les canaux, cet utilisateur ne peut plus démarrer de réunions improvisées dans les canaux et le canal Conférence maintenant joint les liens que l’utilisateur a créés précédemment a expiré. L’utilisateur peut toujours commencer et planifier d’autres types de réunions et participer à des réunions organisées par d’autres personnes.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>Que se passe-t-il lorsque le lien d’entrée et l’ID de conférence expirent ?

Lorsque le lien d’adhésion à la réunion et l’ID de conférence d’une réunion expirent, personne ne peut y participer. Lorsqu’un utilisateur tente de participer à la réunion via le lien ou par téléphone, il reçoit un message lui indique que la réunion n’est plus disponible. Les conversations, fichiers, tableaux blancs, enregistrements, transcriptions et autres contenus liés à la réunion sont conservés et les utilisateurs peuvent toujours y accéder.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>Que se passe-t-il lorsque vous activer et désactiver un paramètre de stratégie de réunion ?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>Passer d’un paramètre de stratégie de réunion à un paramètre de réunion

Lorsqu’un paramètre de stratégie de réunion est réglé sur **On,** les utilisateurs à qui la stratégie est attribuée peuvent démarrer ou planifier des réunions de ce type et tout le monde peut y participer. Lorsque vous basculez le paramètre de stratégie de réunion sur **Non,** les utilisateurs à qui la stratégie est attribuée ne peuvent pas démarrer ou planifier de nouvelles réunions de ce type, et les liens de participer à la réunion et les ID de conférence des réunions existantes précédemment programmées par l’utilisateur ont expiré.

Gardez à l’esprit que l’utilisateur peut toujours participer à des réunions organisées par d’autres personnes.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>Passer d’un paramètre de stratégie de réunion à un paramètre de réunion

Lorsque vous basculez d’un paramètre de stratégie de réunion de Off à **On,** les utilisateurs à qui la stratégie est attribuée peuvent démarrer ou planifier des réunions de ce type.  Si un paramètre de stratégie de réunion est désactivé, puis réorganisé pour un utilisateur, toutes les réunions précédemment programmées (et expirées) organisées par l’utilisateur deviennent actives et les personnes peuvent les rejoindre à l’aide du lien d’accès à la réunion ou par téléphone.  

## <a name="meeting-expiration-scenarios"></a>Scénarios d’expiration de réunion

Voici un résumé du fonctionnement de l’expiration des réunions pour chacun des paramètres de stratégie de réunion évoqués dans cet article.

|Si vous souhaitez...&nbsp;&nbsp; |Pour ce faire,&nbsp;&nbsp;&nbsp;&nbsp;  |Comportement d’adhésion à une réunion&nbsp;&nbsp;&nbsp;&nbsp;  |
|---------------------------|---------------------|---------|
|Expiration des réunions Conférence maintenant privées démarrées par un utilisateur&nbsp;&nbsp;|Désactiver Autoriser **la réunion maintenant dans les réunions privées.**&nbsp;&nbsp;|Personne ne peut participer à des réunions **Privées Conférence maintenant** démarrées par l’utilisateur.|
|Expiration des réunions privées programmées par un utilisateur&nbsp;&nbsp;|Désactiver autoriser **la planification de réunions privées** _et_ désactiver l’Outlook **la réunion.** &nbsp;&nbsp;|Personne ne peut participer à des réunions privées programmées par l’utilisateur. Cela empêche les personnes de participer aux réunions suivantes :<ul><li>Réunions privées qui se sont déjà produites dans le passé.</li><li>Réunions privées prévues pour l’avenir et qui ne se sont pas encore produites.</li><li>Prochaines instances de réunions privées périodiques.</li></ul><br>Autoriser la planification de  **réunions privées** et Autoriser le Outlook à expirer les réunions privées prévues par un utilisateur. Si l’un des paramètres est éteint et que l’autre est actif, les liens de participation à des réunions et les ID de conférence des réunions existantes restent actifs et ne sont pas expirés.|
|Expire channel **Meet now** meetings started by a user&nbsp;&nbsp;|Désactiver Autoriser la **réunion maintenant dans les canaux** _et_ Autoriser la planification de réunions **de canal.**&nbsp;&nbsp;|Personne ne peut rejoindre les réunions **Conférence maintenant** du canal commencées par l’utilisateur.|
|Expiration des réunions de canal prévues par un utilisateur&nbsp;&nbsp;|Désactiver **l’autoriser à planifier des réunions de canal.**&nbsp;&nbsp;|Personne ne peut participer aux réunions de canal programmées par l’utilisateur. Cela empêche les personnes de participer aux réunions suivantes :<ul><li>Réunions de canal qui se sont déjà produites dans le passé.</li><li>Réunions de canal prévues pour l’avenir et qui ne se sont pas encore produites.</li><li>Prochaines instances de réunions de canal périodiques.</li></ul>|

Si vous souhaitez que les personnes accèdent à des réunions précédemment programmées ou démarrées par un utilisateur particulier, vous pouvez :

- Activer le paramètre de stratégie de réunion pour cet utilisateur.
- Désactiver le paramètre de stratégie de réunion pour cet utilisateur et permettre à un autre utilisateur dont le paramètre de stratégie est activé de créer une réunion en remplacement de la réunion expirée.

> [!NOTE]
> Si la réunion a été envoyée par un délégué, qui a reçu l’autorisation d’envoyer des invitations à la réunion au nom d’une autre personne( par exemple, un responsable), le paramètre de stratégie de réunion est appliqué à la personne qui a accordé l’autorisation (le responsable).

## <a name="related-topics"></a>Voir aussi

[Gérer les stratégies de réunion dans Teams](meeting-policies-overview.md)

[Attribuer des stratégies à vos utilisateurs](policy-assignment-overview.md)

[Présentation de Teams PowerShell](teams-powershell-overview.md)
