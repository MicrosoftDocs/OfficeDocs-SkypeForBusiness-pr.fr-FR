---
title: Expérience client Teams et conformité aux modes coexistence
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Apprenez-en davantage sur l’interface client et la conformité des modes de coexistence de Teams (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
localization_priority: Normal
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
ms.openlocfilehash: 0c67046128c79608f19a4a1f4474164a949f37ef
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903359"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Expérience client Teams et conformité aux modes coexistence

<a name="about-upgrade-basic"></a>

L’objectif des modes de coexistence Skype entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) est d’offrir une interface simple et prévisible aux utilisateurs finaux lors de la transition de Skype entreprise à Teams.  Dans le cas d’une organisation qui migre vers Teams, le mode **équipes uniquement** représente la destination finale de chaque utilisateur, mais tous les utilisateurs ne doivent pas être disposant **uniquement d’équipes** (ou d’autres modes) en même temps.  Avant d’atteindre le mode TeamsOnly, les organisations peuvent utiliser n’importe quel mode de coexistence Skype entreprise pour garantir une communication prévisible entre les utilisateurs qui sont des **équipes uniquement** et ceux qui ne le sont pas encore. 

Lorsque l’utilisateur se trouve dans l’un des modes Skype entreprise, toutes les conversations et tous les appels entrants sont acheminés vers le client Skype entreprise de l’utilisateur. Afin d’éviter la confusion des utilisateurs finaux et de veiller à ce que le routage, les appels et les discussions appropriés dans le client teams soient désactivés lorsqu’un utilisateur se trouve dans l’un des modes Skype entreprise. De la même façon, la planification de réunions en équipes est désactivée explicitement lorsque les utilisateurs se trouvent dans les modes SfBOnly ou SfBWithTeamsCollab, et activés de manière explicite lorsqu’un utilisateur est en mode SfBWithTeamsCollabAndMeetings.

Dans la mesure où la présence est une indication d’une accessibilité par le biais d’une conversation ou d’un appel, lorsque les discussions et les appels sont désactivés, la présence automatique dans Teams (autrement dit, l’affichage de la propre présence d’une personne dans teams dans l’image de l’utilisateur) est également cachée. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Comment les fonctionnalités disponibles dans teams client changent en fonction du mode

Les fonctionnalités disponibles dans teams dépendent du mode de coexistence de l’utilisateur, tel qu’il est défini par TeamsUpgradePolicy. Le tableau suivant récapitule le comportement :

|Mode d’efficacité de l’utilisateur|Découvrir le client Microsoft teams|
|---|---|
|Tout mode Skype entreprise|Les appels, les discussions et la présence automatique sont désactivés.|
|SfBWithTeamsCollabAndMeetings|La planification de réunion est disponible|
|SfBWithTeamsCollab ou SfBOnly<sup>1</sup>|La planification de la réunion n’est pas disponible|
|||

Les captures d’écran suivantes montrent la différence entre les **équipes uniquement** ou le mode **îlot** et tous les autres modes. Notez que les icônes de discussion et d’appels sont disponibles par défaut avec les **équipes uniquement** ou le mode **îlots** (capture vers la gauche), mais pas pour les autres modes (capture d’écran droite) :

![Comparaison côte à côte des modes d’équipe](media/teams-mode-comparison.png)

De plus, la présence automatique n’est pas disponible dans les autres modes, comme le montre l’illustration ci-dessous.

![Capture d’écran de l’auto-présence dans les réunions](media/meetings-first-no-self-presence-general.png)
 
**Remarque :**
<sup>1</sup> pour le moment, SfBwithTeamsCollab et SfBOnly se comportent de la même façon, mais l’intention est pour le mode SfBOnly de désactiver également les fonctionnalités canaux et fichiers dans Teams. Par intérim, les canaux peuvent être masqués à l’aide de la stratégie d’autorisations des applications.


## <a name="impact-of-mode-on-other-policy-settings"></a>Impact du mode sur les autres paramètres de stratégie
Comme décrit ci-dessus, les fonctionnalités du mode de coexistence d’un utilisateur sont celles disponibles dans le client teams de l’utilisateur. Cela signifie que la valeur du mode peut être prioritaire par rapport à d’autres paramètres de stratégie, en fonction du mode. Plus précisément, le mode de coexistence a un impact sur le respect des paramètres de stratégie suivants :

|**Modalité (application)**|**Policy. Setting**|
|---|---|
|Conversation|TeamsMessagingPolicy.AllowUserChat|
|Appels|TeamsCallingPolicy.AllowPrivateCalling|
|Planification de réunions|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Les administrateurs ont besoin de *ne pas* définir explicitement ces paramètres de stratégie lors de l’utilisation du mode de coexistence, mais il est important de se familiariser avec ces paramètres comme suit pour un mode donné. 

|Veille|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly ou îles|Activé|Activé|Activé|Activé|
|SfBWithTeamsCollabAndMeetings|Désactivé|Désactivé|Activé|Activé|
|SfBWithTeamsCollab ou SfBOnly|Désactivé|Désactivé|Désactivé|Désactivé|
||||||

Lors de l’utilisation de `Grant-CsTeamsUpgradePolicy` PowerShell, l’applet de contrôle vérifie la configuration des paramètres correspondants dans TeamsMessagingPolicy, TeamsCallingPolicy et TeamsMeetingPolicy pour déterminer si ces paramètres sont remplacés par TeamsUpgradePolicy et, si tel est le cas, un message d’information est fourni dans PowerShell.  Comme indiqué plus haut, il n’est plus nécessaire de définir les autres paramètres de stratégie. Voici un exemple d’avertissement de PowerShell :

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Sujets associés

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




