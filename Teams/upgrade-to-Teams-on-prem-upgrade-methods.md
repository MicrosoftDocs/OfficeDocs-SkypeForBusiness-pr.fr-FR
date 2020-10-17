---
title: Effectuer une mise à niveau vers teams à partir d’un déploiement local de Skype entreprise-Microsoft teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Mise à niveau de Skype Entreprise vers Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2dc8afc48db6264cef5c5ad959f33dd7e738e116
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515791"
---
# <a name="upgrade-methods-mdash-for-it-administrators"></a>Méthodes de mise à niveau &mdash; pour les administrateurs informatiques

Cet article décrit les méthodes de mise à niveau pour migrer vers Teams. Cet article est le second de ceux qui décrivent des concepts et de l’implémentation de la mise à niveau pour les administrateurs informatiques.  

- [Vue d’ensemble](upgrade-to-teams-on-prem-overview.md)
- **Méthodes de mise à niveau** (cet article)
- [Outils de gestion de votre mise à niveau](upgrade-to-teams-on-prem-tools.md)
- [Autres considérations concernant les organisations avec Skype entreprise en local](upgrade-to-teams-on-prem-considerations.md)
- [Implémentation de votre mise à niveau](upgrade-to-teams-on-prem-implement.md)
- [Considérations relatives au réseau téléphonique public commuté (RTC)](upgrade-to-teams-on-prem-pstn-considerations.md)

De plus, les articles suivants décrivent des concepts importants de mise à niveau et des comportements de coexistence :

- [Coexistence des équipes et de Skype entreprise](upgrade-to-teams-on-prem-coexistence.md)
- [Modes de coexistence-référence](migration-interop-guidance-for-teams-with-skype.md)
- [Expérience client Teams et conformité aux modes coexistence](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="upgrade-methods"></a>Méthodes de mise à niveau

Deux méthodes s’offrent à vous pour effectuer la mise à niveau d’une organisation existante avec Skype entreprise (en ligne ou en local) en équipes : méthodes de superposition et méthode Select. Cet article vous permet de choisir la méthode correcte pour votre organisation en décrivant les deux méthodes et en présentant les avantages et inconvénients de chacune d’elles. 

- [Méthode de superposition des capacités (à l’aide du mode îlot)](#overlapping-capabilities-method-using-islands-mode)

   Les utilisateurs d’une organisation Skype entreprise existante sont introduits dans teams pour qu’ils puissent utiliser les deux clients pendant une phase de transition. Pendant ce laps de temps, la plupart des fonctionnalités d’équipe sont disponibles. Le mode de cette configuration est appelé îlots, et il s’agit du mode par défaut de toute organisation existante avec Skype entreprise. Lorsque l’organisation est prête, l’administrateur déplace les utilisateurs vers le mode TeamsOnly.

- [Sélectionner une méthode de fonctions (à l’aide d’un ou de plusieurs modes Skype entreprise)](#select-capabilities-method-using-skype-for-business-modes)

   L’administrateur gère la transition (de Skype entreprise à Teams) de la fonctionnalité de conversation, d’appel et de planification de réunion pour les utilisateurs de leur organisation.  Chacune de ces fonctions est disponible dans Skype entreprise ou Teams, mais pas les deux. Les administrateurs utilisent TeamsUpgradePolicy pour contrôler le moment auquel décaler cette fonctionnalité vers équipes pour leurs utilisateurs. Les utilisateurs qui ne sont pas encore en mode TeamsOnly continuent d’utiliser Skype entreprise pour les discussions et les appels, et les deux utilisateurs peuvent communiquer par le biais de fonctionnalités d’interopérabilité. Les administrateurs gèrent la transition en migrant progressivement de plus utilisateurs vers le mode TeamsOnly.  

Après avoir compris et choisi votre méthode de mise à niveau, vous pouvez en savoir plus sur les [outils de gestion de la mise à niveau de votre organisation vers teams](upgrade-to-teams-on-prem-tools.md).

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Méthode de superposition des capacités (à l’aide du mode îlot)

Grâce à la méthode de superposition des capacités, les utilisateurs peuvent utiliser des équipes et des clients Skype entreprise pour la messagerie instantanée, les appels VoIP et les réunions. Cet État est connu sous le nom de « îles », car le trafic de communication pour Skype entreprise et teams reste différent (même pour le même utilisateur) et les deux clients ne communiquent jamais entre eux (pour les utilisateurs au sein de la même organisation). Par exemple, supposons que l’utilisateur A est en mode îlot :

- Les communications déclenchées à partir du client Skype entreprise d’un autre utilisateur seront toujours portées sur le client Skype entreprise d’un utilisateur.

- La communication lancée à partir du client teams d’un autre utilisateur sera toujours terrestre dans le client teams de l’utilisateur, *si ce dernier est dans la même organisation*. 

- La communication lancée à partir du client teams d’un autre utilisateur sera toujours effectuée sur le client Skype entreprise d’un utilisateur, *si ce dernier est dans une organisation fédérée*.

Le mode îlot est le mode par défaut de TeamsUpgradePolicy pour toutes les organisations existantes qui n’ont pas encore été mises à niveau vers TeamsOnly. Lorsque vous affectez une licence Microsoft 365 ou Office 365, les licences équipes et Skype entreprise Online sont affectées par défaut. (Cela s’applique même si l’utilisateur est hébergé sur site dans Skype entreprise Server. Que l’utilisateur réside en local ou en ligne, laissez la licence Skype entreprise Online activée, car elle est actuellement requise pour les fonctionnalités d’équipe complètes.) En fait, si vous n’avez pas effectué de modification de la configuration par défaut, il est possible que vous ayez une utilisation significative des équipes au sein de votre organisation.  C’est l’un des avantages de l’approche des fonctionnalités qui se chevauchent. Elle permet une adoption rapide et rapide par l’utilisateur au sein d’une organisation.

Pour que cette méthode fonctionne efficacement, tous les utilisateurs doivent exécuter les deux clients simultanément. Les discussions et les appels entrants au sein de l’organisation à un utilisateur en mode d’îlot peuvent débarquer dans le client Skype entreprise ou équipes, et ce n’est pas le contrôle du destinataire. Si l’expéditeur et le destinataire sont au sein de la même organisation, il dépend du client utilisé par l’expéditeur pour initier la communication. Si l’expéditeur et le destinataire se trouvent dans différentes organisations, les appels et les discussions entrants à un utilisateur en mode îlot sont toujours terrains dans le client Skype entreprise.  

Par exemple, si le destinataire du mode îlot exécute Skype entreprise, mais pas Teams, et qu’un membre de la même organisation en reçoit un message, le destinataire du mode îles ne verra pas le message (mais il recevra un message électronique indiquant qu’il a manqué un message dans Teams). De même, si un utilisateur travaille sur Teams, mais pas sur Skype entreprise, et qu’il est adressé à un utilisateur de Skype entreprise, il ne verra pas la discussion.  Il recevra un message électronique indiquant qu’un message a été manqué. Le comportement dans chacun de ces cas est similaire pour les appels. Si les utilisateurs ne sont pas en mesure d’exécuter les deux clients, ils peuvent facilement susciter votre frustration.

Lorsque l’utilisateur a est en mode îlot, la présence de l’utilisateur A comme vu par d’autres utilisateurs dans Microsoft teams et dans Skype entreprise est indépendante :

- Les autres utilisateurs, lors de l’utilisation d’équipes, verront leur présence en fonction de l’activité de l’utilisateur dans Teams. 
- Les autres utilisateurs, lors de l’utilisation de Skype entreprise, verront leur présence en fonction de l’activité de l’utilisateur A dans Skype entreprise. 

Cela signifie que d’autres utilisateurs peuvent voir des États de présence différents pour l’utilisateur A, en fonction du client qu’il utilise. Pour plus d’informations, voir [presence](upgrade-to-teams-on-prem-coexistence.md#presence).

Lorsque vous êtes prêt à mettre à niveau les utilisateurs vers le mode TeamsOnly, vous pouvez mettre à niveau les utilisateurs individuellement ou procéder à la mise à niveau du client entier en une fois à l’aide de la stratégie à l’échelle du client. Une fois qu’un utilisateur a procédé à la mise à niveau vers le mode TeamsOnly, il reçoit toutes les discussions et les appels entrants dans Teams. (Notez que la migration de réunions Skype entreprise vers des réunions teams n’est déclenchée que lorsque vous appliquez TeamsUpgradePolicy à des utilisateurs individuels, et non au niveau de chaque client. Pour plus d’informations, voir migration de la [réunion](upgrade-to-teams-on-prem-tools.md#meeting-migration) .

Toutefois, les destinataires non mis à niveau en mode îlot peuvent continuer à recevoir des conversations et des appels de la part d’un utilisateur TeamsOnly dans leurs clients Skype entreprise ou équipes.  En effet, le client teams gère des threads de conversation distinctes pour la communication équipes-à---------Skype entreprise, même pour le même utilisateur.  (Voir [conversations d’équipe-interopérabilité et threads natifs](upgrade-to-teams-on-prem-coexistence.md#teams-conversations---interop-versus-native-threads).)  Par exemple, supposons que l’utilisateur A utilise teams pour TeamsOnly l’utilisateur B. Lorsque l’utilisateur B répond à cette discussion, la communication s’affiche dans le client teams de l’utilisateur. Supposons que l’utilisateur A utilise le client Skype entreprise pour envoyer un message à TeamsOnly l’utilisateur B. l’utilisateur B recevra la discussion dans Teams, mais il s’agira d’une conversation distincte dans le client teams de l’utilisateur b par rapport à l’autre conversation. Si l’utilisateur B répond à cette conversation avec l’utilisateur A, il sera débarqué dans le client Skype entreprise de l’utilisateur. 

Le tableau suivant résume l’interface du mode de travail de l’équipe et du mode TeamsOnly :  

| Expertise dans teams | En mode îlot | En mode TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Discussions entrantes et appels reçus dans :|  Teams ou Skype entreprise | Équipes |
| Appels RTC reçus dans : | Skype Entreprise <br>(L’utilisation de la fonctionnalité RTC dans teams n’est pas prise en charge en mode îlot.)    | Équipes |   
 |Présence  | La présence dans Skype entreprise et équipes est indépendante. Les utilisateurs peuvent voir des États différents pour les mêmes utilisateurs d’îlot, en fonction du client qu’ils utilisent. | La présence est basée uniquement sur l’activité de l’utilisateur dans Teams. Tous les autres utilisateurs, quel que soit le client qu’ils utilisent, voient leur présence. | 
 | Planification de réunions   | Par défaut, les utilisateurs peuvent planifier des réunions dans teams ou Skype entreprise. Ces deux compléments s’afficheront dans Outlook. |   Les utilisateurs planifient uniquement les réunions dans Teams. Le complément équipes n’est disponible que dans Outlook. | 

Le tableau suivant récapitule les avantages et inconvénients de l’utilisation de la méthode de superposition de capacités pour migrer votre organisation vers Teams.

| Spécialistes     |       Argument |
| :------------------ | :---------------- |
| Autorise une adoption rapide au sein d’une organisation.| Potentiel pour la confusion des utilisateurs finaux, car il existe deux clients dotés de fonctionnalités similaires, mais différentes interfaces utilisateur. Par ailleurs, ils n’ont aucun contrôle sur le client sur lequel les discussions/appels entrants sont débarqués. |
| Permet aux utilisateurs de se familiariser avec les équipes tout en possédant un accès complet à Skype entreprise. | Potentiel pour une insatisfaction de l’utilisateur final en raison de messages manqués si l’utilisateur n’exécute pas les deux clients. Les utilisateurs peuvent se plaindrs de ne pas recevoir de messages.|
| Effort d’administration minimal pour la mise en route dans Teams. | Il peut être difficile de mettre en place le mode « extraire des îles » et de basculer vers le mode TeamsOnly si tous les utilisateurs de l’organisation n’utilisent pas Teams, en particulier si les utilisateurs ne sont pas actifs dans Teams. Par exemple, une fois qu’un sous-ensemble d’utilisateurs est mis à niveau vers le mode TeamsOnly, ils sont envoyés uniquement dans Teams. Pour le reste de la population en mode îlot, ces messages seront toujours présents dans Teams. Mais si certains de ces populations n’exécutent pas Teams, ils peuvent considérer ces messages comme manqués. |
|  | Lors de l’utilisation d’équipes, les utilisateurs disposant d’un compte local dans Skype entreprise Server ne disposent pas de la prise en charge de l’interopérabilité ou de la Fédération.  Cela peut éventuellement générer une confusion si vous avez une combinaison d’utilisateurs d’îlots, dont certains sont hébergés dans Skype entreprise Online et d’autres dans Skype entreprise local.   |

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Sélectionner une méthode de fonctions (à l’aide du mode Skype entreprise)

Certaines organisations peuvent proposer à leurs utilisateurs finaux une utilisation plus simple et plus prévisible de la transition de Skype entreprise à Teams. Dans ce modèle, les administrateurs informatiques ont recours à l’un des modes Skype entreprise de TeamsUpgradePolicy pour désigner explicitement les utilisateurs de Skype entreprise avant de procéder à la migration vers le mode TeamsOnly. Étant donné qu’ils sont prêts à décaler les utilisateurs sélectionnés vers le mode TeamsOnly, l’administrateur doit mettre à jour le mode de ces utilisateurs pour qu’ils TeamsOnly. Au fur et à mesure de l’évolution du déploiement, de plus en plus d’utilisateurs sont migrés de Skype entreprise vers le mode TeamsOnly.  Lors de cette transition :

- Les utilisateurs de Skype entreprise reçoivent toutes les discussions et les appels entrants dans leur client Skype entreprise, que la communication provient de l’équipe ou du client Skype entreprise. Par ailleurs, pour ces utilisateurs Skype entreprise, les fonctionnalités d’appel et de discussion dans le client teams sont désactivées pour éviter toute confusion et garantir le routage approprié. 

- Les utilisateurs en mode TeamsOnly reçoivent toutes les discussions et les appels entrants dans leur client Teams, quel que soit le lieu d’origine de la communication : Teams, Skype entreprise ou tout type d’utilisateur fédéré. 

Contrairement à la méthode îlots, dans la méthode sélectionner des fonctions, les utilisateurs Skype entreprise et les utilisateurs de TeamsOnly peuvent communiquer entre eux. La communication entre un utilisateur de Skype entreprise et des équipes est appelée interopérabilité ou « interopérabilité ». La communication d’interopérabilité est possible sur une base un-à-un pour les conversations et les appels entre un utilisateur dans Skype entreprise et un autre utilisateur dans Teams. Toutefois, certaines fonctionnalités avancées peuvent ne pas être disponibles. (Voir [interopérabilité](upgrade-to-teams-on-prem-coexistence.md#interoperability).) De plus, les utilisateurs invités peuvent toujours participer à une réunion Skype entreprise ou Teams, mais ils doivent utiliser un client correspondant au type de réunion. Pour plus d’informations, reportez-vous à la section [réunions](upgrade-to-teams-on-prem-coexistence.md#meetings).

Dans la mesure où les utilisateurs d’une transition à l’aide de la fonctionnalité SELECT ne sont généralement pas en mode îlot, la présence d’un utilisateur est cohérente quel que soit le client utilisé par l’autre utilisateur. Si l’utilisateur se trouve dans l’un des modes Skype entreprise, tous les autres utilisateurs voient leur présence en fonction de l’activité de l’utilisateur dans Skype entreprise. De même, si un utilisateur est en mode TeamsOnly, tous les autres utilisateurs voient leur présence en fonction de l’activité de l’utilisateur dans Teams. Pour plus d’informations, voir [présence](upgrade-to-teams-on-prem-coexistence.md#presence).

Dans le cas d’une organisation qui n’a pas encore commencé à utiliser Teams, l’administrateur doit changer le mode de travail à l’échelle du client de îlot à SfbWithTeamsCollab. (Pour les organisations disposant déjà de l’utilisation de teams, l’administrateur doit avoir le « grand nombre d’utilisateurs » déjà actifs dans teams pour s’assurer que le changement ne leur est pas applicable. Pour plus d’informations, reportez-vous à [la rubrique sélectionner des capacités pour une organisation qui utilise déjà teams en mode îlot](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode).)

Lorsque le mode passe d’îlot à SfbWithTeamsCollab, un utilisateur qui ne les utilise jamais n’aura pas de différence dans la façon dont il utilise Skype entreprise. Toutefois, si l’utilisateur commence à utiliser Teams, il ne serait exposé qu’aux fonctionnalités telles que les équipes & le canal et les fichiers. Les discussions, les appels et la planification de réunions ne seront pas disponibles dans Teams, dans la mesure où l’administrateur dispose de Skype entreprise (pour le moment) pour ces fonctions.  

Remarque : lorsque l’utilisateur A passe d’îlot à l’un des modes Skype entreprise, le client teams de tout autre utilisateur qui communique avec l’utilisateur A doit savoir que le mode de l’utilisateur a changé de sorte qu’il puisse diriger la communication vers le client approprié pour l’utilisateur A.  Pour tous les utilisateurs qui ont déjà établi des discussions d’équipes ou d’équipes natives avec l’utilisateur A, il peut s’écouler jusqu’à 36 heures pour que les clients teams d’autres utilisateurs sachent que le mode d’appel d’îles est en mode Skype entreprise.   En revanche, les modifications apportées à un utilisateur existant en mode TeamsOnly sont découvertes par d’autres clients dans un délai de 2 heures.

Lorsque les administrateurs sont prêts, ils peuvent passer des conversations, des appels et une planification de réunion pour un utilisateur donné aux équipes en une seule fois en mettant à jour le mode de l’utilisateur sur TeamsOnly.  

Par ailleurs, l’administrateur peut commencer par changer uniquement la planification des réunions en équipes, tout en laissant les fonctions de conversation et d’appel dans Skype entreprise à l’aide du mode SfBWithTeamsCollabAndMeetings. Ce mode permet aux organisations de migrer vers les équipes pour les réunions, si les utilisateurs ne sont pas encore en mesure d’accéder au mode TeamsOnly (en général, un délai supplémentaire peut être nécessaire pour migrer les fonctionnalités RTC existantes). Ce scénario de transition est appelé d' [abord réunions](meetings-first.md).

Le tableau suivant récapitule les avantages et inconvénients de l’utilisation du mode Skype entreprise comme étape de transition vers le mode TeamsOnly.


| Spécialistes     |       Argument |
| :------------------ | :---------------- |
| Routage prévisible pour l’utilisateur final.  Tous les appels et messages instantanés dans Skype entreprise ou équipes (mais pas les deux), en fonction de la sélection de l’administrateur.  | Les conversations d’interopérabilité ne prennent pas en charge le texte enrichi, le partage de fichiers et le partage d’écran.  Cela peut être utilisé avec des réunions à la demande, mais cela n’est pas aussi simple que possible.  |
| Éliminer la confusion des utilisateurs finaux, car une fonctionnalité donnée est disponible uniquement dans un client.  | Les utilisateurs ne peuvent pas essayer les deux clients côte à côte pour le même ensemble de fonctionnalités. Le facteur de place est particulièrement important si les utilisateurs perçoivent le changement de Skype entreprise par rapport aux équipes en tant que déphasage de paradigme majeure. |
| Permet une présentation incrémentielle des équipes.  |  | |
| L’administrateur contrôle entièrement le passage de Skype entreprise à Teams. |  | | 
| Permet à une organisation d’utiliser des équipes pour les réunions, même si elle n’est pas encore prête pour le passage entièrement au mode TeamsOnly. |  | |
| Le statut de présence d’un utilisateur donné affiché par les autres est le même quel que soit le client qu’il utilise.  |  | |

## <a name="summary-of-upgrade-methods"></a>Résumé des méthodes de mise à niveau

Le tableau suivant récapitule les méthodes de mise à niveau :

| Fonctionnalités qui se chevauchent (à l’aide du mode îlot)     |      Sélectionner des capacités (à l’aide du mode Skype entreprise) |
| :------------------ | :---------------- |
| Avant la mise à niveau vers TeamsOnly, les utilisateurs doivent exécuter les deux clients simultanément, dans la mesure où les conversations et les appels entrants peuvent débarquer dans l’un ou l’autre client.   | Discussions et appels uniquement terrestres d’un client, en fonction du mode du destinataire. Les utilisateurs non mis à niveau peuvent exécuter les deux clients, mais il n’y a pas de chevauchement fonctionnel (les appels et les discussions ne sont pas disponibles dans Teams).  Les administrateurs peuvent également contrôler si les utilisateurs planifient des réunions dans teams ou Skype entreprise.   |
| Les utilisateurs peuvent utiliser Skype entreprise et équipes côte à côte pour de mêmes fonctionnalités.   | Permet aux administrateurs de présenter de nouvelles fonctionnalités de Microsoft teams aux utilisateurs finaux (équipes et canaux), sans offrir de nouvelles fonctionnalités dans Skype entreprise.   |
|L’interopérabilité entre Skype entreprise et équipes n’existe pas tant que les deux utilisateurs sont en mode îlot. Après avoir effectué la mise à niveau vers TeamsOnly, certains utilisateurs peuvent se produire entre ces utilisateurs et d’autres utilisateurs toujours en mode îlot. Toutefois, l’utilisateur de l’archipel peut choisir d’utiliser teams et d’éviter la conversation d’interopérabilité. | L’interopérabilité est requis pour la communication entre les utilisateurs de Skype entreprise et Teams.   |


## <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer une connectivité hybride entre Skype entreprise Server et Microsoft 365 ou Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Utiliser le service de migration de réunion (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

