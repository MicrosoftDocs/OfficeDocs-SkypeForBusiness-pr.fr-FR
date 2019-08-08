---
title: Expérience client Teams et conformité aux modes coexistence
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Découverte et transformation du client teams en modes de coexistence
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 85f74b63f465bd0004e8b9a2ef93c79b00196495
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243904"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Expérience client Teams et conformité aux modes coexistence

> [!NOTE]
> Cette page décrit les modifications importantes apportées récemment au comportement du client teams lorsque les utilisateurs travaillent dans l’un des modes Skype entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).


Le mode de coexistence est d’offrir une utilisation simple et prévisible aux utilisateurs finaux dans le cadre de la transition de Skype entreprise à Teams.  Dans le cas d’une organisation migrant vers Teams, le mode TeamsOnly est la destination finale de chaque utilisateur, mais tous les utilisateurs ne doivent pas avoir besoin d’être TeamsOnly (ou n’importe quel autre mode) en même temps.  Dans le cas où les utilisateurs accèdent au mode TeamsOnly, les organisations peuvent utiliser n’importe quel mode Skype entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) pour garantir une communication prévisible entre les utilisateurs TeamsOnly et ceux qui ne le sont pas encore. 

Lorsque l’utilisateur se trouve dans l’un des modes Skype entreprise, toutes les conversations et tous les appels entrants sont acheminés vers le client Skype entreprise de l’utilisateur. Afin d’éviter la confusion des utilisateurs finaux et de veiller à ce que le routage, les appels et les discussions appropriés dans le client teams soient désactivés lorsqu’un utilisateur se trouve dans l’un des modes Skype entreprise. De la même façon, la planification de réunions en équipes est désactivée explicitement lorsque les utilisateurs se trouvent dans les modes SfBOnly ou SfBWithTeamsCollab, et activés de manière explicite lorsqu’un utilisateur est en mode SfBWithTeamsCollabAndMeetings.   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Comment les fonctionnalités disponibles dans teams client changent en fonction du mode
Les fonctionnalités disponibles dans teams dépendent du mode de coexistence de l’utilisateur, tel qu’il est défini par TeamsUpgradePolicy. Le tableau ci-dessous résume le comportement:

|Mode d’efficacité de l’utilisateur|Découvrir le client Microsoft teams|
|---|---|
|Tout mode Skype entreprise|Les appels et les discussions sont désactivés.|
|SfBWithTeamsCollabAndMeetings|La planification de réunion est disponible|
|SfBWithTeamsCollab ou SfBOnly<sup>1</sup>|La planification de la réunion n’est pas disponible|
|||

Les captures d’écran ci-dessous illustrent la différence entre le mode TeamsOnly ou le mode îlot et tous les autres modes. Notez que les icônes de discussion et d’appels sont disponibles en mode TeamsOnly ou îlots (capture de la gauche), mais pas avec les autres modes (capture d’écran de droite):

![Comparaison côte à côte des modes d’équipe](media/teams-mode-comparison.png)


 
**Remarque:**
<sup>1</sup> pour le moment, SfBwithTeamsCollab et SfBOnly se comportent de la même façon, mais l’intention est pour le mode SfBOnly de désactiver également les fonctionnalités canaux et fichiers dans Teams. en revanche, il n’existe actuellement aucun paramètre permettant de désactiver cette fonctionnalité dans Teams.


## <a name="impact-of-mode-on-other-policy-settings"></a>Impact du mode sur les autres paramètres de stratégie
Comme décrit ci-dessus, les fonctionnalités du mode de coexistence d’un utilisateur sont celles disponibles dans le client teams de l’utilisateur. Cela signifie que la valeur du mode peut être prioritaire par rapport à d’autres paramètres de stratégie, en fonction du mode. Plus précisément, le mode de coexistence a un impact sur le respect des paramètres de stratégie suivants:

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

Lors de l’utilisation de `Grant-CsTeamsUpgradePolicy` PowerShell, l’applet de contrôle vérifie la configuration des paramètres correspondants dans TeamsMessagingPolicy, TeamsCallingPolicy et TeamsMeetingPolicy pour déterminer si ces paramètres sont remplacés par TeamsUpgradePolicy et, si tel est le cas, un le message d’information est fourni dans PowerShell.  Comme indiqué plus haut, il n’est plus nécessaire de définir les autres paramètres de stratégie. Vous trouverez ci-dessous un exemple d’avertissement dans PowerShell:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a>Voir aussi

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




