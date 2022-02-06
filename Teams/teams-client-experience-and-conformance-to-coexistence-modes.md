---
title: Expérience client Teams et conformité aux modes coexistence
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: 'En savoir Teams expérience cliente et la conformité aux modes de coexistence (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).'
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
---

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Expérience client Teams et conformité aux modes coexistence

<a name="about-upgrade-basic"></a>

L’objectif des modes de coexistence Skype Entreprise (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) est d’offrir aux utilisateurs finaux une expérience simple et prévisible au sein de la transition entre Skype Entreprise et Teams.  Pour une organisation passant à Teams, le mode **Teams** Seul est la destination finale pour chaque utilisateur, même si tous les utilisateurs ne doivent pas être affectés **Teams** Uniquement (ou tout autre mode) en même temps.  Avant que les utilisateurs n’atteignent le mode TeamsOnly, les organisations peuvent utiliser n’importe quel mode de coexistence Skype Entreprise pour assurer une communication prévisible entre les utilisateurs qui utilisent **Teams** uniquement et ceux qui ne le sont pas encore. 

Lorsqu’un utilisateur est dans l’un des modes Skype Entreprise, toutes les conversations et appels entrants sont acheminés vers le client de messagerie Skype Entreprise’utilisateur. Pour éviter la confusion des utilisateurs finaux et garantir un routage approprié, les fonctionnalités d’appel et de conversation dans le client Teams sont désactivées lorsqu’un utilisateur est dans l’un Skype Entreprise modes. De même, la planification de réunions dans Teams est explicitement désactivée lorsque les utilisateurs sont dans les modes SfBOnly ou SfBWithTeamsCollab et sont explicitement activés lorsqu’un utilisateur est en mode SfBWithTeamsCollabAndMeetings.

Étant donné que la présence est une indication de l’accessibilité par le biais de la conversation et des appels, lorsque la conversation et les appels sont désactivés, la présence autonome dans Teams (autrement dit, l’affichage de sa propre présence dans le client Teams dans l’image de l’utilisateur) est également masquée. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Changement des fonctionnalités disponibles dans Teams client en fonction du mode

Les fonctionnalités disponibles dans Teams dépendent du mode de coexistence de l’utilisateur, tel que le définisse TeamsUpgradePolicy. Le tableau suivant résume le comportement :

|Mode effectif de l’utilisateur|Expérience dans Teams client|
|---|---|
|N’importe Skype Entreprise mode|Les appels, les discussions et la présence autonome sont désactivés.|
|SfBWithTeamsCollabAndMeetings|La planification de réunion est disponible|
|SfBWithTeamsCollab ou SfBOnly1<sup></sup>|La planification de réunion n’est pas disponible|
|||

Les captures d’écran suivantes illustrent la différence **entre Teams** **mode** Îles uniquement et tous les autres modes. Notez que les icônes de conversation et d’appel sont disponibles par défaut avec **le mode Teams** Uniquement ou **Îles** (capture d’écran de gauche), mais pas avec les autres modes (capture d’écran de droite) :

![Comparaison des différents modes d’Teams côte à côte.](media/teams-mode-comparison.png)

De plus, la présence automatique n’est pas disponible dans les autres modes, comme illustré ici.

![Capture d’écran de l’auto-présence dans Réunions Tout d’abord.](media/meetings-first-no-self-presence-general.png)
 
**Remarque :**
 <sup>1</sup> Pour le moment, SfBwithTeamsCollab et SfBOnly se comportent à l’identique, mais l’objectif est que le mode SfBOnly désactive également la fonctionnalité Canaux et fichiers dans Teams. Les canaux peuvent être masqués temporairement à l’aide de la stratégie Autorisations d’application.


## <a name="impact-of-mode-on-other-policy-settings"></a>Impact du mode sur les autres paramètres de stratégie
Comme décrit ci-dessus, le mode de coexistence d’un utilisateur a une incidence sur la fonctionnalité disponible dans le client Teams utilisateur. Cela signifie que la valeur du mode peut être prioritaire sur la valeur des autres paramètres de stratégie, selon le mode. Plus précisément, le mode coexistence a un impact si les paramètres de stratégie suivants sont respecter :

|**Modalité (Application)**|**Policy.Setting**|
|---|---|
|Conversation|TeamsMesspolicy.AllowUserChat|
|Appel|TeamsCallingPolicy.AllowPrivateCalling|
|Planification de réunions|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Les administrateurs  n’ont pas besoin de définir explicitement ces paramètres de stratégie lors de l’utilisation du mode de co-existence, mais il est important de comprendre que ces paramètres se comportent de façon efficace comme suit pour un mode donné. 

|Mode|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly ou Islands|Activé|Activé|Activé|Activé|
|SfBWithTeamsCollabAndMeetings|Désactivé|Désactivé|Activé|Activé|
|SfBWithTeamsCollab ou SfBOnly|Désactivé|Désactivé|Désactivé|Désactivé|
||||||

Lors de l’utilisation de PowerShell, `Grant-CsTeamsUpgradePolicy` l’cmdlet vérifie la configuration des paramètres correspondants dans TeamsMess niveauPolicy, TeamsCallingPolicy et TeamsMeetingPolicy pour déterminer si ces paramètres doivent être supersedés par TeamsUpgradePolicy et, si c’est le cas, un message d’information est fourni dans PowerShell.  Comme indiqué ci-dessus, il n’est plus nécessaire de définir ces autres paramètres de stratégie. Voici un exemple de l’avertissement PowerShell :

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Voir aussi

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](./migration-interop-guidance-for-teams-with-skype.md)