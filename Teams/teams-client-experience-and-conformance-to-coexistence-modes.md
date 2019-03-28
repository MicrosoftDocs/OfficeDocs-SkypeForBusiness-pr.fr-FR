---
title: Expérience client Teams et conformité aux modes coexistence
author: dearbeen
ms.author: bjwhalen
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: Équipes de l’expérience client et comformance aux modes de coexistence
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4865d66d4d3ff1257d0fc4bd355a65c7c1330101
ms.sourcegitcommit: 5b33cfc828906917f76b0d2a9ae402c9336388a1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30934787"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Expérience client Teams et conformité aux modes coexistence

> [!NOTE]
> Cette page décrit les modifications importantes, récemment publiées dans le comportement du client équipes lorsque vous êtes dans une de le Skype pour les modes d’entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).


L’objectif des modes de coexistence est de fournir une expérience prévisible simple pour les utilisateurs finaux en tant que la transition des organisations de Skype pour les entreprises aux équipes.  Pour une organisation déplacement aux équipes, le mode TeamsOnly est la destination finale pour chaque utilisateur, même si tous les utilisateurs ne doivent être attribués TeamsOnly (ou tout autre mode) en même temps.  Avant d’atteindre le mode TeamsOnly des utilisateurs, organisations peuvent utiliser de la Skype pour les modes d’entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) pour assurer la communication entre les utilisateurs qui sont TeamsOnly et ceux qui ne sont pas encore prévisible. 

Lorsqu’un utilisateur est dans un de la Skype pour les modes d’entreprise, toutes les conversations entrantes et les appels sont routés vers Skype l’utilisateur pour client d’entreprise. Pour éviter toute confusion d’utilisateur final et garantir un routage correct, les fonctionnalités d’appel et de conversation dans le client d’équipes sont désactivée lorsqu’un utilisateur est dans un de la Skype pour les modes d’entreprise. De même, planifier des réunions dans les équipes est désactivé lorsque vous êtes dans les modes SfBOnly ou SfBWithTeamsCollab et explicitement activée lorsqu’un utilisateur est en mode SfBWithTeamsCollabAndMeetings.   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Comment les fonctionnalités disponibles dans le client équipes changent selon le mode
Les fonctionnalités disponibles dans les équipes dependes sur le mode de coexistence de l’utilisateur, tel que défini par TeamsUpgradePolicy. Le tableau ci-dessous résume le comportement :

|Mode efficace de l’utilisateur|Expérience client d’équipes|
|---|---|
|N’importe quel Skype pour le mode d’entreprise|L’appel et de conversation<sup>1</sup> sont désactivées.|
|SfBWithTeamsCollabAndMeetings|Planification de la réunion est disponible|
|SfBWithTeamsCollab ou SfBOnly<sup>2</sup>|Planification de la réunion n’est pas disponible|
|||

Les captures d’écran suivantes illustrent la différence entre le mode TeamsOnly ou (îles) et tous les autres modes. Notez que les icônes de conversation et d’appel sont disponibles avec TeamsOnly ou (îles) mode (capture d’écran de gauche), mais pas avec les autres modes (capture d’écran droite) :

![Affiche les comparaisons de mode d’équipes](media/teams-mode-comparison.png)


 
**Remarques :**
<sup>1</sup> session est toujours disponible.

<sup>2</sup> pour l’instant, SfBwithTeamsCollab et SfBOnly ont les mêmes, mais l’objectif est de mode SfBOnly également désactiver la fonctionnalité de canaux et les fichiers dans les équipes ; Toutefois, il n’existe actuellement aucun paramètre qui permet cette fonctionnalité dans les équipes à désactiver.


## <a name="impact-of-mode-on-other-policy-settings"></a>Impact du Mode d’autres paramètres de stratégie
Comme indiqué ci-dessus, l’impact de l’utilisateur coexistence en mode fonctionnalité est disponible dans le client de l’utilisateur aux équipes. Cela signifie que la valeur de mode a priorité sur la valeur d’autres paramètres de stratégie, selon le mode. Plus précisément, de cohabitation a un impact sur si les paramètres de stratégie suivants sont respectés :

|**Modalité (application)**|**Policy.Setting**|
|---|---|
|Conversation|TeamsMessagingPolicy.AllowUserChat|
|Appels|TeamsCallingPolicy.AllowPrivateCalling|
|Planification de la réunion|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Les administrateurs doivent *pas* explicitement définies avant de ces paramètres de stratégie à l’aide du mode de coexistence, mais il est important de comprendre que ces paramètres efficacement se comportent comme suit pour un mode donné. 

|Mode|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly ou (îles)|Activé|Activé|Activé|Activé|
|SfBWithTeamsCollabAndMeetings|Désactivé|Désactivé|Activé|Activé|
|SfBWithTeamsCollab ou SfBOnly|Désactivé|Désactivé|Désactivé|Désactivé|
||||||

Dans un avenir proche, le `Grant-CsTeamsUpgradePolicy` cmdlet vérifiera la configuration des paramètres correspondants dans TeamsMessagingPolicy, TeamsCallingPolicy et TeamsMeetingPolicy pour déterminer si ces paramètres seront être remplacés par TeamsUpgradePolicy et dans ce cas, un message d’information est fournie dans PowerShell.  Comme mentionné ci-dessus, n’est plus nécessaire de définir les autres paramètres de stratégie. Voici un exemple de quel l’avertissement PowerShell ressemble à :

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a>Rubriques connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




