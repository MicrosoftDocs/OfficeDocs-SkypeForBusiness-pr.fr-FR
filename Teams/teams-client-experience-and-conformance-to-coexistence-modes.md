---
title: Expérience client Teams et conformité aux modes coexistence
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Découvrez l’expérience client Teams et la conformité aux modes de coexistence (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91ea07d74bf9b08f627d86191ea08fc0eda1ac4c
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605833"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Expérience client Teams et conformité aux modes coexistence

<a name="about-upgrade-basic"></a>

L’objectif des modes de coexistence Skype Entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) est de fournir une expérience simple et prévisible aux utilisateurs finaux lorsque les organisations passent de Skype Entreprise à Teams.  Pour une organisation qui passe à Teams, le mode **Teams uniquement** est la destination finale pour chaque utilisateur, mais tous les utilisateurs n’ont pas besoin d’être affectés à **Teams uniquement** (ou tout autre mode) en même temps.  Avant que les utilisateurs n’atteignent le mode TeamsOnly, les organisations peuvent utiliser l’un des modes de coexistence Skype Entreprise pour garantir une communication prévisible entre les utilisateurs qui sont **uniquement Teams** et ceux qui ne le sont pas encore. 

Lorsqu’un utilisateur se trouve dans l’un des modes Skype Entreprise, tous les appels et conversations entrants sont acheminés vers le client Skype Entreprise de l’utilisateur. Pour éviter toute confusion de l’utilisateur final et garantir que les fonctionnalités de routage, d’appel et de conversation appropriées dans le client Teams sont désactivées lorsqu’un utilisateur se trouve dans l’un des modes Skype Entreprise. De même, la planification des réunions dans Teams est explicitement désactivée quand les utilisateurs sont dans les modes SfBOnly ou SfBWithTeamsCollab, et explicitement activée lorsqu’un utilisateur est en mode SfBWithTeamsCollabAndMeetings.

Étant donné que la présence est une indication de l’accessibilité par le biais de la conversation et de l’appel, lorsque la conversation et l’appel sont désactivés, l’auto-présence dans Teams (autrement dit, l’affichage de sa propre présence dans le client Teams dans l’image de l’utilisateur) est également masquée. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Comment les fonctionnalités disponibles dans le client Teams changent en fonction du mode

La fonctionnalité disponible dans Teams dépend du mode de coexistence de l’utilisateur, tel que défini par TeamsUpgradePolicy. Le tableau suivant résume le comportement :

|Mode effectif de l’utilisateur|Expérience dans le client Teams|
|---|---|
|Tout mode Skype Entreprise|L’appel, la conversation et la présence personnelle sont désactivés.|
|SfBWithTeamsCollabAndMeetings|La planification des réunions est disponible|
|SfBWithTeamsCollab ou SfBOnly<sup>1</sup>|La planification des réunions n’est pas disponible|
|||

Les captures d’écran suivantes illustrent la différence entre le mode **Teams uniquement** ou **Islands** et tous les autres modes. Notez que les icônes de conversation et d’appel sont disponibles par défaut avec **le mode Teams Uniquement** ou **Islands** (capture d’écran de gauche), mais pas avec les autres modes (capture d’écran de droite) :

![Comparaison côte à côte des modes Teams.](media/teams-mode-comparison.png)

En outre, l’auto-présence n’est pas disponible dans les autres modes, comme illustré ici.

![Capture d’écran de l’auto-présence dans Meetings First.](media/meetings-first-no-self-presence-general.png)
 
**Note:**
 <sup>1</sup> À ce stade, SfBwithTeamsCollab et SfBOnly se comportent de la même façon, mais l’intention est que le mode SfBOnly désactive également les fonctionnalités Canaux et fichiers dans Teams. Dans l’intervalle, les canaux peuvent être masqués à l’aide de la stratégie d’autorisations d’application.


## <a name="impact-of-mode-on-other-policy-settings"></a>Impact du mode sur d’autres paramètres de stratégie
Comme décrit ci-dessus, le mode de coexistence d’un utilisateur a un impact sur les fonctionnalités disponibles dans le client Teams de l’utilisateur. Cela signifie que la valeur du mode peut être prioritaire sur la valeur des autres paramètres de stratégie, en fonction du mode. Plus précisément, le mode de coexistence détermine si les paramètres de stratégie suivants sont respectés :

|**Modalité (Application)**|**Policy.Setting**|
|---|---|
|Conversation|TeamsMessagingPolicy.AllowUserChat|
|Appel|TeamsCallingPolicy.AllowPrivateCalling|
|Planification des réunions|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Les administrateurs *n’ont pas* besoin de définir explicitement ces paramètres de stratégie lors de l’utilisation du mode de coexistence, mais il est important de comprendre que ces paramètres se comportent efficacement comme suit pour un mode donné. 

|Mode|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly ou Îles|Activé|Activé|Activé|Activé|
|SfBWithTeamsCollabAndMeetings|Désactivé|Désactivé|Activé|Activé|
|SfBWithTeamsCollab ou SfBOnly|Désactivé|Désactivé|Désactivé|Désactivé|
||||||

Lors de l’utilisation de PowerShell, l’applet `Grant-CsTeamsUpgradePolicy` de commande vérifie la configuration des paramètres correspondants dans TeamsMessagingPolicy, TeamsCallingPolicy et TeamsMeetingPolicy pour déterminer si ces paramètres seraient remplacés par TeamsUpgradePolicy et, le cas échéant, un message d’information est fourni dans PowerShell.  Comme indiqué ci-dessus, il n’est plus nécessaire de définir ces autres paramètres de stratégie. Voici un exemple de l’avertissement PowerShell :

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Sujets associés

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](./migration-interop-guidance-for-teams-with-skype.md)