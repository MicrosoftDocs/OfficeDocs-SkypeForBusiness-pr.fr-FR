---
title: Effectuer une mise à niveau vers teams à partir d’un déploiement local de Skype entreprise-Microsoft teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Mise à niveau de Skype Entreprise vers Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b9bac6ee38c166250746b6ce9f4fb48afe3cbfe2
ms.sourcegitcommit: eb2182617d8f72f8a7ea95f7af101d10c6f4e9a0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/07/2020
ms.locfileid: "41852101"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Mise à niveau de Skype entreprise vers &mdash; teams pour les administrateurs informatiques

## <a name="overview"></a>Vue d’ensemble

Lorsque vous procédez à la mise à niveau de Skype entreprise vers équipes, certaines organisations requièrent un lancement progressif qui est planifié et géré par leurs services informatiques. Cet article s’adresse principalement aux administrateurs informatiques des organisations locales de grande taille, mais il peut également s’appliquer à certaines organisations Skype entreprise online.  Avant de lire cet article, assurez-vous de lire la [mise à niveau de votre équipe](upgrade-start-here.md) et de [l’infrastructure de mise à niveau](upgrade-framework.md).

>[!NOTE]
>Cet article utilise les conditions générales de Skype entreprise Online, Skype entreprise local et Skype entreprise.  Ce terme fait référence à des versions en ligne et locales.

Un utilisateur ayant migré vers teams n’utilise plus un client Skype entreprise, à l’exception de la participation à une réunion hébergée dans Skype entreprise.  Toutes les conversations et les appels entrants dans le client teams de l’utilisateur, que l’expéditeur utilise teams ou Skype entreprise. Toutes les nouvelles réunions organisées par l’utilisateur migré seront planifiées en tant que réunions d’équipes. Si l’utilisateur tente d’utiliser le client Skype entreprise, l’ouverture de conversations et d’appels est bloquée.  Toutefois, l’utilisateur peut (et doit) toujours utiliser le client Skype entreprise pour participer aux réunions auxquelles il est invité. (Les anciens clients Skype entreprise livrés avant 2017 ne respectent pas TeamsUpgradePolicy. Vérifiez que vous utilisez la dernière version du client Skype entreprise.)
 
Les administrateurs gèrent leur transition vers teams à l’aide du concept de [mode](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes), qui est une propriété de [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). Un utilisateur migré vers teams comme décrit ci-dessus est en mode « TeamsOnly ».  Dans le cas d’une organisation migrant vers Teams, l’objectif ultime consiste à déplacer tous les utilisateurs vers le mode TeamsOnly.

Il existe deux méthodes pour migrer une organisation existante avec Skype entreprise (en ligne ou sur site) vers teams :

- **Méthode de superposition de capacités** (avec le mode îlot) : les utilisateurs d’une organisation Skype entreprise existante sont introduits dans teams pour qu’ils puissent utiliser les deux clients pendant une phase de transition. Pendant ce laps de temps, la plupart des fonctionnalités d’équipe sont disponibles. Le mode de cette configuration est appelé îlots, et il s’agit du mode par défaut de toute organisation existante avec Skype entreprise. Lorsque l’organisation est prête, l’administrateur déplace les utilisateurs vers le mode TeamsOnly.

- **Sélectionner une méthode de fonctions** (à l’aide d’un ou de plusieurs modes Skype entreprise) : l’administrateur gère la transition (de Skype entreprise à Teams) de la fonctionnalité de conversation, d’appel et de planification de réunion pour les utilisateurs de leur organisation.  Chacune de ces fonctions est disponible dans Skype entreprise ou Teams, mais pas les deux. Les administrateurs utilisent TeamsUpgradePolicy pour contrôler le moment auquel décaler cette fonctionnalité vers équipes pour leurs utilisateurs. Les utilisateurs qui ne sont pas encore en mode TeamsOnly continuent d’utiliser Skype entreprise pour les discussions et les appels, et les deux utilisateurs peuvent communiquer par le biais de fonctionnalités d’interopérabilité. Les administrateurs gèrent la transition en migrant progressivement de plus utilisateurs vers le mode TeamsOnly.  

Cet article vous permet de choisir la méthode correcte pour votre organisation en décrivant les deux méthodes et en présentant les avantages et inconvénients de chacune d’elles. 

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Méthode de superposition des capacités (à l’aide du mode îlot)

Grâce à la méthode de superposition des capacités, les utilisateurs peuvent utiliser des équipes et des clients Skype entreprise pour la messagerie instantanée, les appels VoIP et les réunions. Cet État est connu sous le nom de « îles », car le trafic de communication pour Skype entreprise et teams reste différent (même pour le même utilisateur) et les deux clients ne communiquent jamais entre eux (pour les utilisateurs au sein de la même organisation). Par exemple, supposons que l’utilisateur A est en mode îlot :

- Les communications déclenchées à partir du client Skype entreprise d’un autre utilisateur seront toujours portées sur le client Skype entreprise d’un utilisateur.
- La communication lancée à partir du client teams d’un autre utilisateur sera toujours terrestre dans le client teams de l’utilisateur, *si ce dernier est dans la même organisation*. 
- La communication lancée à partir du client teams d’un autre utilisateur sera toujours effectuée sur le client Skype entreprise d’un utilisateur, *si ce dernier est dans une organisation fédérée*.

Le mode îlot est le mode par défaut de TeamsUpgradePolicy pour toute organisation existante qui n’est pas encore TeamsOnly. Lorsque vous affectez une licence Office 365, les équipes et les licences Skype entreprise Online sont affectées par défaut. (Cela s’applique même si l’utilisateur est hébergé sur site dans Skype entreprise Server. Que l’utilisateur réside en local ou en ligne, laissez la licence Skype entreprise Online activée, car elle est actuellement requise pour les fonctionnalités d’équipe complètes.) En fait, si vous n’avez pas effectué de modification de la configuration par défaut, il est possible que vous ayez une utilisation significative des équipes au sein de votre organisation.  C’est l’un des avantages de l’approche des fonctionnalités qui se chevauchent. Elle permet une adoption rapide et rapide par l’utilisateur au sein d’une organisation.

Pour que cette méthode fonctionne efficacement, tous les utilisateurs doivent exécuter les deux clients simultanément. Les discussions et les appels entrants au sein de l’organisation à un utilisateur en mode d’îlot peuvent débarquer dans le client Skype entreprise ou équipes, et ce n’est pas le contrôle du destinataire. Tout dépend du client utilisé par l’expéditeur pour initier la communication. Si l’expéditeur et le destinataire se trouvent dans différentes organisations, les appels et les discussions entrants à un utilisateur en mode îlot sont toujours terrains dans le client Skype entreprise.  

Par exemple, si le destinataire du mode de la société travaille sur Skype entreprise, mais pas sur Teams, et qu’une personne a envoyé un message à partir de teams, le destinataire du mode îles ne verra pas le message (mais il obtiendra finalement un message électronique indiquant qu’il a manqué un message dans Teams). De même, si un utilisateur travaille sur Teams, mais pas sur Skype entreprise, et qu’il est adressé à un utilisateur de Skype entreprise, il ne verra pas la discussion.  Il recevra un message électronique indiquant qu’un message a été manqué. Le comportement dans chacun de ces cas est similaire pour les appels. Si les utilisateurs ne sont pas en mesure d’exécuter les deux clients, ils peuvent facilement susciter votre frustration.

Lorsque l’utilisateur a est en mode îlot, la présence de l’utilisateur A comme vu par d’autres utilisateurs dans Microsoft teams et dans Skype entreprise est indépendante :

- Les autres utilisateurs, lors de l’utilisation d’équipes, verront leur présence en fonction de l’activité de l’utilisateur dans Teams. 
- Les autres utilisateurs, lors de l’utilisation de Skype entreprise, verront leur présence en fonction de l’activité de l’utilisateur A dans Skype entreprise. 

Cela signifie que d’autres utilisateurs peuvent voir des États de présence différents pour l’utilisateur A, en fonction du client qu’il utilise. Pour en savoir plus, voir [présence](#presence).

Lorsque vous êtes prêt à mettre à niveau les utilisateurs vers le mode TeamsOnly, vous pouvez mettre à niveau les utilisateurs individuellement ou procéder à la mise à niveau du client entier en une fois à l’aide de la stratégie à l’échelle du client. Une fois qu’un utilisateur a procédé à la mise à niveau vers le mode TeamsOnly, il reçoit toutes les discussions et les appels entrants dans Teams. (Notez que la migration de réunions Skype entreprise vers des réunions teams n’est déclenchée que lorsque vous appliquez TeamsUpgradePolicy à des utilisateurs individuels, et non au niveau de chaque client. Pour plus d’informations, voir migration de la [réunion](#meeting-migration) .

Toutefois, les destinataires non mis à niveau en mode îlot peuvent continuer à recevoir des conversations et des appels de la part d’un utilisateur TeamsOnly dans leurs clients Skype entreprise ou équipes.  En effet, le client teams gère des threads de conversation distinctes pour la communication équipes-à---------Skype entreprise, même pour le même utilisateur.  (Voir [conversations d’équipe-interopérabilité et threads natifs](#teams-conversations---interop-versus-native-threads).)  Par exemple, supposons que l’utilisateur A utilise teams pour TeamsOnly l’utilisateur B. Lorsque l’utilisateur B répond à cette discussion, la communication s’affiche dans le client teams de l’utilisateur. Supposons que l’utilisateur A utilise son client Skype entreprise pour envoyer un message à TeamsOnly l’utilisateur B. l’utilisateur B recevra la discussion dans Teams, mais il s’agira d’une conversation distincte dans le client teams de l’utilisateur b par rapport à l’autre conversation. Si l’utilisateur B répond à cette conversation avec l’utilisateur A, il sera débarqué dans le client Skype entreprise de l’utilisateur. 

Le tableau suivant résume l’interface du mode de travail de l’équipe et du mode TeamsOnly :  

| Expertise dans teams | En mode îlot | En mode TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Discussions entrantes et appels reçus dans :|  Teams ou Skype entreprise | Équipes |
| Appels RTC reçus dans : | Skype Entreprise <br>(L’utilisation de la fonctionnalité RTC dans teams n’est pas prise en charge en mode îlot.)    | Équipes |   
 |Présence  | La présence dans Skype entreprise et équipes est indépendante. Les utilisateurs peuvent voir des États différents pour les mêmes utilisateurs d’îlot, en fonction du client qu’ils utilisent. | La présence est basée uniquement sur l’activité de l’utilisateur dans Teams. Tous les autres utilisateurs, quel que soit le client qu’ils utilisent, voient leur présence. | 
 | Planification de réunions   | Les utilisateurs peuvent planifier des réunions dans teams ou Skype entreprise. Ces deux compléments s’afficheront dans Outlook. |   Les utilisateurs planifient uniquement les réunions dans Teams. Le complément équipes n’est disponible que dans Outlook. | 

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

Contrairement à la méthode îlots, dans la méthode sélectionner des fonctions, les utilisateurs Skype entreprise et les utilisateurs de TeamsOnly peuvent communiquer entre eux. La communication entre un utilisateur de Skype entreprise et des équipes est appelée interopérabilité ou « interopérabilité ». (Voir [interopérabilité](#interoperability).) La communication d’interopérabilité est possible sur une base un-à-un pour les conversations et les appels entre un utilisateur dans Skype entreprise et un autre utilisateur dans Teams. De plus, les utilisateurs invités peuvent toujours participer à une réunion Skype entreprise ou Teams, mais ils doivent utiliser un client correspondant au type de réunion. Pour plus d’informations, reportez-vous à la section [réunions](#meetings).

Dans la mesure où les utilisateurs d’une transition à l’aide de la fonctionnalité SELECT ne sont généralement pas en mode îlot, la présence d’un utilisateur est cohérente quel que soit le client utilisé par l’autre utilisateur. Si l’utilisateur se trouve dans l’un des modes Skype entreprise, tous les autres utilisateurs voient leur présence en fonction de l’activité de l’utilisateur dans Skype entreprise. De même, si un utilisateur est en mode TeamsOnly, tous les autres utilisateurs voient leur présence en fonction de l’activité de l’utilisateur dans Teams. Pour plus d’informations, voir [présence](#presence).

Dans le cas d’une organisation qui n’a pas encore commencé à utiliser Teams, l’administrateur doit changer le mode de travail à l’échelle du client de îlot à SfbWithTeamsCollab. (Pour les organisations disposant déjà de l’utilisation de teams, l’administrateur doit avoir le « grand nombre d’utilisateurs » déjà actifs dans teams pour s’assurer que le changement ne leur est pas applicable. Pour plus d’informations, reportez-vous [à la rubrique sélection de fonctionnalités pour une organisation qui utilise déjà teams en mode îlot](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode).)

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

## <a name="tools-for-managing-the-upgrade"></a>Outils de gestion de la mise à niveau

Pour l’une des méthodes décrites ci-dessus, les administrateurs gèrent la transition vers TeamsOnly à l’aide de [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), qui contrôle le mode de coexistence d’un utilisateur. Pour plus d’informations sur chacun des modes, voir [modes de coexistence](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes).

Que l’administrateur effectue une transition sélection de fonctionnalités en utilisant les modes Skype entreprise ou qu’il passe simplement au mode TeamsOnly à partir de la configuration des îles par défaut, TeamsUpgradePolicy est l’outil principal.  À l’instar des autres stratégies dans Teams, TeamsUpgradePolicy peut être attribué directement à un utilisateur et peut également être défini en tant que client par défaut. Tout devoir d’un utilisateur est prioritaire sur le paramètre par défaut du client.  Elle peut être gérée à la fois dans la console d’administration teams et dans PowerShell.

Les administrateurs peuvent attribuer n’importe quel mode de TeamsUpgradePolicy aux utilisateurs, que l’utilisateur soit hébergé dans Skype entreprise Online ou en local, à l’exception du mode TeamsOnly ne peut être attribué qu’à un utilisateur déjà associé à Skype entreprise online. En effet, l’interopérabilité avec les utilisateurs Skype entreprise et la Fédération n’est possible que si l’utilisateur est hébergé dans Skype entreprise online.

Les utilisateurs disposant d’un compte Skype entreprise sur site hébergé sur site [doivent être déplacés en ligne](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (à partir de Skype entreprise Online ou directement à Teams) à l’aide de Move-Csuser dans l’ensemble d’outils Skype entreprise local. Ces utilisateurs peuvent être déplacés vers TeamsOnly en 1 ou 2 étapes :

-   1 étape : spécifiez le commutateur-MoveToTeams dans Move-CsUser. Pour cela, vous devez disposer de Skype entreprise Server 2019 ou de Skype entreprise Server 2015 avec CU8.

-   2 étapes : après avoir exécuté Move-CsUser, octroyez le mode TeamsOnly à l’utilisateur à l’aide de TeamsUpgradePolicy.

Contrairement aux autres stratégies, il n’est pas possible de créer de nouvelles instances de TeamsUpgradePolicy dans Office 365. Toutes les instances existantes sont intégrées au service.  (Notez que le mode est une propriété dans TeamsUpgradePolicy, plutôt que le nom d’une instance de stratégie.) Dans certains cas, mais pas dans tous les cas, le nom de l’instance de stratégie est le même que le mode. En particulier, pour affecter le mode TeamsOnly à un utilisateur, vous devez attribuer l’instance « UpgradeToTeams » de TeamsUpgradePolicy à cet utilisateur. Pour afficher une liste de toutes les instances, vous pouvez exécuter la commande suivante :

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Pour mettre à niveau un utilisateur en ligne vers le mode TeamsOnly, attribuez l’instance « UpgradeToTeams » : 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Pour passer d’un utilisateur Skype entreprise local au mode TeamsOnly, utilisez Move-CsUser dans l’ensemble d’outils local :

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

Pour modifier le mode de tous les utilisateurs du client, à l’exception de ceux qui ont une autorisation explicite par utilisateur (prioritaire), exécutez la commande suivante :

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Si vos utilisateurs disposent d’un compte Skype entreprise local, vous ne devez pas affecter le mode TeamsOnly au niveau du client, sauf si vous affectez explicitement un autre mode à tous les utilisateurs disposant de comptes Skype entreprise locaux.


### <a name="using-notifications-in-skype-for-business-clients"></a>Utilisation des notifications dans les clients Skype entreprise

Les administrateurs ont la possibilité de fournir des notifications aux utilisateurs finaux dans le client Skype entreprise pour informer les utilisateurs qu’ils seront bientôt mis à niveau vers Teams, comme illustré dans le schéma suivant. Par exemple, une semaine, avant que l’administrateur ne prévoit de mettre à niveau un groupe d’utilisateurs vers le mode TeamsOnly, l’administrateur peut activer ces notifications pour ce groupe d’utilisateurs. Ces notifications sont activées à l’aide d’une instance de TeamsUpgradePolicy avec NotifySfbUsers = true.  Pour tous les modes autres que TeamsOnly, il existe en réalité deux instances par mode, correspondant aux deux valeurs de NotifySfbUsers.  Pour tous les modes autres que TeamsOnly, il existe en réalité deux instances par mode, correspondant aux deux valeurs de NotifySfbUsers. 

![Diagramme présentant des notifications](media/teams-upgrade-sfb-with-notifications.png)

Si vos utilisateurs sont familiaux dans Skype entreprise Online, il vous suffit d’affecter l’instance de la stratégie ayant le même mode que l’utilisateur, mais avec NotifySfbUsers = true. 

Si vos utilisateurs sont hébergés dans Skype entreprise Server en local, vous devez utiliser l’ensemble d’outils local et vous aurez besoin de Skype entreprise Server 2019 ou CU8 pour Skype entreprise Server 2015. Dans la fenêtre PowerShell locale, créez une nouvelle instance de TeamsUpgradePolicy avec NotifySfbUsers = true :

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Ensuite, à l’aide de la même fenêtre PowerShell locale, attribuez cette nouvelle stratégie aux utilisateurs souhaités :

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

### <a name="meeting-migration"></a>Migration de réunion

Lorsqu’un utilisateur est déplacé vers le mode TeamsOnly, par défaut, les réunions Skype entreprise existantes qu’il a organisées seront converties en équipes. Vous pouvez éventuellement désactiver le comportement par défaut lors de l’attribution du mode TeamsOnly à un utilisateur. Lorsque vous déplacez des utilisateurs d’un environnement local, les réunions doivent être déplacées vers le Cloud pour fonctionner avec le compte d’utilisateur en ligne, mais si vous ne spécifiez pas-MoveToTeams, les réunions seront déplacées en tant que réunions Skype entreprise, et non converties en équipes. 

Lors de l’attribution du mode TeamsOnly au niveau du client, la migration de la réunion n’est déclenchée pour aucun utilisateur. Si vous souhaitez affecter le mode TeamsOnly au niveau du client et migrer des réunions, vous pouvez utiliser PowerShell pour obtenir la liste des utilisateurs dans le client (par exemple, en utilisant Get-CsOnlineUser avec les filtres requis), puis en boucle sur chacun de ces utilisateurs pour déclencher la réunion. migration à l’aide de Start-CsExMeetingMigration. Pour plus d’informations, consultez [utilisation du service de migration de réunion (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).


### <a name="additional-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Autres considérations concernant les organisations avec Skype entreprise Server en local

- La configuration de Skype entreprise hybride est une condition préalable à la migration vers le mode TeamsOnly. Même s’il est possible d’utiliser les équipes en mode d’îlot sans qu’elles soient hybrides, la transition vers le mode TeamsOnly ne peut pas être effectuée tant que l’utilisateur n’est pas transféré de Skype entreprise sur site à Skype entreprise Online (via [Move-Csuser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)). Pour plus d’informations, voir [configurer une connectivité hybride](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).

- Les utilisateurs teams disposant d’un compte Skype entreprise local (autrement dit, ils n’ont pas encore été déplacés vers le Cloud à l’aide de Move-CsUser) ne peuvent pas interagir avec des utilisateurs de Skype entreprise, et ne peuvent pas être fédérer avec des utilisateurs externes. Cette fonctionnalité n’est disponible que lorsque les utilisateurs sont déplacés vers le Cloud (en mode îlot ou en tant qu’utilisateurs TeamsOnly). 

- Si vos utilisateurs disposent d’un compte Skype entreprise local, vous ne devez pas affecter le mode TeamsOnly au niveau du client, sauf si vous affectez explicitement un autre mode à tous les utilisateurs disposant de comptes Skype entreprise locaux. 

- Vous devez vous assurer que vos utilisateurs sont correctement synchronisés avec Azure AD avec les attributs Skype entreprise appropriés. Ces attributs sont des préfixes avec « msRTCSIP- ». Si les utilisateurs ne sont pas synchronisés correctement avec Azure AD, les outils de gestion dans Teams ne seront pas en mesure de gérer ces utilisateurs. Pour plus d’informations, reportez-vous à la rubrique [configuration d’Azure ad Connect pour les équipes et Skype entreprise](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Pour créer un nouveau TeamsOnly ou un utilisateur de Skype entreprise Online au sein d’une organisation hybride, *vous devez d’abord activer l’utilisateur dans Skype entreprise Server en local*, puis déplacer l’utilisateur de local vers le Cloud à l’aide de Move-Csuser.  La création de l’utilisateur sur site permet de s’assurer que tous les autres utilisateurs Skype entreprise restants pourront diriger vers l’utilisateur nouvellement créé. Une fois tous les utilisateurs déplacés en ligne, il n’est plus nécessaire d’activer d’abord les utilisateurs en local.

- Lorsque l’utilisateur passe du Cloud local, les réunions organisées par cet utilisateur sont déplacées vers Skype entreprise Online ou Teams, selon que le commutateur-MoveToTeams est ou non spécifié.

- Si vous souhaitez afficher les notifications dans le client Skype entreprise pour les utilisateurs locaux, vous devez utiliser TeamsUpgradePolicy dans l’ensemble d’outils local. Seul le paramètre NotifySfbUsers est pertinent pour les utilisateurs locaux.  Les utilisateurs sur site reçoivent leur mode provenant des instances en ligne d’TeamsUpgradePolicy. Voir les remarques dans [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). 

>[!NOTE]
> Tout nouveau client créé après le 3 septembre 2019 est créé en tant que client TeamsOnly sans permettre aux administrateurs d’effectuer une mise à niveau vers une version antérieure. Les organisations disposant de Skype entreprise Server sur site qui n’avaient pas encore bénéficié d’un abonnement Office 365 avant le 3 septembre, 2019 doivent contacter le support technique de Microsoft pour faire en sorte qu’ils soient mis à niveau vers la version antérieure, dès qu’ils acquièrent un abonnement avec Office 365. 


## <a name="perform-the-upgrade-for-your-organization"></a>Procéder à la mise à niveau de votre organisation

Cette section décrit les options de mise à niveau suivantes :

- Mise à niveau des fonctionnalités qui se chevauchent (à l’aide du mode îlot)
- Mise à niveau des fonctionnalités SELECT pour une organisation qui n’a pas encore commencé à utiliser teams
- Mise à niveau des fonctionnalités SELECT pour une organisation qui utilise déjà teams en mode îlot

### <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Mise à niveau des fonctionnalités qui se chevauchent (à l’aide du mode îlot)

Pour l’option de mise à niveau des fonctionnalités qui se chevauchent :

- Cette option est utile si vous pouvez effectuer une mise à niveau rapide de votre organisation globale.  Dans la mesure où il existe des risques potentiels de confusion lors de l’exécution de ces deux clients, il est préférable de réduire ce délai. Vous devez veiller à ce que les utilisateurs sachent exécuter les deux clients.

- Cette option est le modèle de la boîte et ne nécessite pas d’action de l’administrateur pour commencer à utiliser teams à l’exception de l’attribution de la licence Office 365. Si vos utilisateurs disposent déjà de Skype entreprise Online, il est possible que vous soyez déjà dans ce modèle.

- Il peut être difficile de sortir du mode de superposition des capacités et de migrer vers TeamsOnly. Étant donné que les utilisateurs mis à niveau communiquent uniquement par le biais d’équipes, tout autre utilisateur de l’organisation qui communique avec cet utilisateur doit utiliser Teams.  Si certains de vos utilisateurs ne sont pas encore en cours d’utilisation, ils seront exposés à des messages manquants. De plus, ils ne verront pas les utilisateurs de TeamsOnly en ligne dans Skype entreprise. Certaines organisations choisissent de procéder à une mise à niveau du client à l’aide de la stratégie globale du client pour éviter cela, mais cela nécessite l’attente que tous les utilisateurs soient prêts à être mis à niveau.


### <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Mise à niveau des fonctionnalités SELECT pour une organisation qui n’a pas encore commencé à utiliser teams

Si votre organisation n’a pas encore de personnes actives dans Teams, la première étape consiste à définir la stratégie à l’échelle de locataire par défaut de TeamsUpgradePolicy sur l’un des modes Skype entreprise, par exemple, SfbWithTeamsCollab.  Les utilisateurs qui n’ont pas encore commencé à utiliser Teams ne noteront aucune différence de comportement. Toutefois, la définition de cette stratégie au niveau du client permet de commencer à mettre à niveau les utilisateurs vers le mode TeamsOnly et de s’assurer que les utilisateurs mis à niveau peuvent toujours communiquer avec des utilisateurs non mis à niveau.  Une fois que vous avez identifié vos utilisateurs pilotes, vous pouvez les mettre à niveau vers TeamsOnly.  S’il s’agit d’un environnement local, utilisez Move-CsUser. S’il est connecté, affectez-lui simplement le mode TeamsOnly à l’aide de TeamsUpgradePolicy.  Par défaut, toutes les réunions Skype entreprise planifiées par ces utilisateurs seront déplacées vers Teams.

Voici les commandes clés :

1. Définissez la valeur par défaut du client sur mode SfbWithTeamsCollab comme suit :

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Effectuez une mise à niveau vers TeamsOnly en procédant comme suit :

   - Si l’utilisateur est déjà connecté :

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - Si l’utilisateur se trouve en local :

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

Remarques
 
- Au lieu de définir la stratégie à l’échelle du client sur SfbWithTeamsCollab, vous pouvez la définir sur SfbWithTeamsCollabAndMeetings. Ainsi, tous les utilisateurs peuvent planifier toutes les nouvelles réunions dans Teams.
- Move-CsUser est une cmdlet dans les outils locaux. Le commutateur MoveToTeams nécessite Skype entreprise Server 2019 ou Skype entreprise Server 2015 avec CU8. Si vous utilisez une version antérieure, vous pouvez d’abord déplacer l’utilisateur vers Skype entreprise Online, puis accorder le mode TeamsOnly à cet utilisateur.
- Par défaut, les réunions Skype entreprise sont déplacées vers teams lors de la mise à niveau vers le mode TeamsOnly ou lors de l’attribution du mode SfbWithTeamsCollabAndMeetings.  

Le diagramme ci-dessous présente les phases conceptuelles de la mise à niveau de fonctionnalités sélectionnées pour une organisation sans utilisation antérieure d’Teams. La hauteur des barres représente le nombre d’utilisateurs. Pendant une phase de la mise à niveau, tous les utilisateurs peuvent communiquer entre eux.  Les utilisateurs de Skype entreprise communiquent avec des utilisateurs de TeamsOnly à l’aide d’interopérabilité, et inversement.

![Diagramme illustrant la mise à niveau de fonctionnalités sélectionnées sans utilisation antérieure des équipes](media/teams-upgrade-1.png)


### <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Mise à niveau des fonctionnalités SELECT pour une organisation qui utilise déjà teams en mode îlot

Si certains utilisateurs de votre organisation utilisent activement teams en mode îlot, il est probable que vous ne vouliez pas supprimer les fonctionnalités des utilisateurs existants. Par conséquent, une étape supplémentaire est requise avant de modifier la stratégie à l’échelle du client. La solution est de « grand-moi », qui sont des utilisateurs d’équipes actives actuellement en mode îlot, avant de définir la stratégie à l’échelle du client sur SfbWithTeamsCollab.  Une fois cette opération effectuée, vous pourrez procéder au déploiement comme décrit ci-dessus, mais vous aurez deux groupes d’utilisateurs qui migrent vers TeamsOnly : les utilisateurs qui ont été actifs dans teams seront en mode d’îlot de travail et les utilisateurs restants seront en mode SfbWithTeamsCollab. Vous pouvez déplacer progressivement ces utilisateurs vers le mode TeamsOnly.

1. Recherchez les utilisateurs actifs dans teams en procédant comme suit :

   1. Dans le portail d’administration Office 365, dans le volet de navigation gauche, accédez à rapports, puis utilisation. 
   2. Dans la liste déroulante « Sélectionner un rapport », cliquez sur Microsoft Teams, puis sur activité de l’utilisateur. Cela permet de fournir une table exportable d’utilisateurs qui ont été actifs dans Teams. 
   3. Cliquez sur Exporter, ouvrir Excel et filtre pour afficher uniquement les utilisateurs actifs dans Teams.

2. Pour chaque utilisateur d’équipe actif trouvé à l’étape 1, attribuez-lui le mode îlots dans Remote PowerShell. Cela vous permet d’accéder à l’étape suivante et de ne pas modifier l’interface utilisateur.  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. Définissez la stratégie à l’échelle du client sur SfbWithTeamsCollab :

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. Mettre à niveau les utilisateurs sélectionnés vers le mode TeamsOnly. Vous pouvez choisir de mettre à niveau les utilisateurs en mode îlot ou SfbWithTeamsCollab, même si vous souhaitez que la mise à niveau des utilisateurs en mode îlot soit prioritaire pour réduire le risque de confusion lorsque les utilisateurs sont en mode îlot.   

   Pour les utilisateurs hébergés dans Skype entreprise Online :  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   Pour les utilisateurs hébergés dans Skype entreprise Server en local :  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

Le diagramme ci-dessous présente les phases conceptuelles d’une transition de sélection de fonctionnalités dans laquelle les utilisateurs d’îlots sont actifs au début. La hauteur des barres représente le nombre d’utilisateurs. Pendant une phase de la mise à niveau, tous les utilisateurs peuvent communiquer entre eux.  Les utilisateurs de Skype entreprise communiquent avec des utilisateurs de TeamsOnly à l’aide d’interopérabilité, et inversement.


![Diagramme illustrant l’option Sélectionner les fonctionnalités mise à niveau avec des utilisateurs actifs en mode d’îlot](media/teams-upgrade-2.png)

   

## <a name="considerations-for-pstn-calling"></a>Remarques concernant la fonction d’appel RTC

Si la fonctionnalité d’appel RTC est impliquée, il existe quatre scénarios possibles lors du passage au mode TeamsOnly :

- *Un utilisateur de Skype entreprise Online avec un plan d’appels Microsoft*. Suite à la mise à niveau, cet utilisateur aura besoin d’un plan d’appels Microsoft.

- *Un utilisateur de Skype entreprise Online avec la fonction vocale locale* via Skype entreprise local ou édition Cloud Connector. La mise à niveau de l’utilisateur vers teams doit être coordonnée avec la migration de l’utilisateur pour diriger le routage afin de garantir que l’utilisateur TeamsOnly dispose de la fonctionnalité RTC.

- *Un utilisateur de Skype entreprise sur site avec voix entreprise, qui va basculer vers une connectivité RTC sur site*.  La migration de cet utilisateur vers teams nécessite le passage du compte Skype entreprise local de l’utilisateur dans le Cloud, et le coordination du déplacement avec la migration de celui-ci pour le routage directe. 

- *Un utilisateur de Skype entreprise sur site avec voix entreprise*, qui sera déplacé vers en ligne et utilisant un forfait d’appel Microsoft.  La migration de cet utilisateur vers teams nécessite le passage du compte Skype entreprise local de l’utilisateur dans le Cloud, et la coordination de la migration à l’aide de l’un des numéros de téléphone de l’utilisateur vers un forfait d’appel Microsoft ou un nouveau numéro d’abonné de régions disponibles.

Cet article fournit une vue d’ensemble de haut niveau. Pour plus d’informations, reportez-vous à la section routage et [appels](calling-plan-landing-page.md) [directs du système téléphonique](direct-routing-landing-page.md) . Par ailleurs, Notez que l’utilisation d’un système téléphonique avec teams est uniquement prise en charge lorsque l’utilisateur est en mode TeamsOnly.  Si l’utilisateur est en mode îlot, le système téléphonique est uniquement pris en charge par Skype entreprise. 

### <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>À partir de Skype entreprise Online avec les offres d’appel Microsoft 

Il s’agit du scénario de mise à niveau le plus simple avec la voix. 

1. Vérifiez que les utilisateurs ont reçu une licence d’équipe. Par défaut, lorsque vous attribuez une licence Office 365, teams est activé, de sorte que si vous n’avez pas encore désactivé la licence Teams, aucune action n’est nécessaire.

2.  Si les utilisateurs ont déjà une offre d’appels Microsoft avec un numéro de téléphone, la seule modification obligatoire consiste à affecter le mode TeamsOnly de l’utilisateur dans TeamsUpgradePolicy.  Avant d’affecter le mode TeamsOnly, les appels RTC entrants apparaissent sur le client Skype entreprise de l’utilisateur. Après la mise à niveau vers le mode TeamsOnly, les appels RTC entrants s’afficheront dans le client teams de l’utilisateur.  

### <a name="from-skype-for-business-online-with-on-premises-voice"></a>À partir de Skype entreprise Online avec la voix locale

Dans ce scénario, l’utilisateur se trouve déjà dans Skype entreprise Online, mais sa connectivité PSTN est locale, soit avec Skype entreprise Server en mode hybride, soit dans la version Cloud Connector. La migration de ces utilisateurs vers le mode TeamsOnly avec la fonctionnalité RTC implique de les activer pour le routage direct, dans lesquels les Trunks RTC se connectent directement au service de routage direct dans le Cloud, via votre contrôleur de bordure de session (SBC) local.

Les étapes de base sont décrites ci-dessous.  Les étapes 1-4 sont répertoriées dans la séquence proposée, mais peuvent être effectuées dans n’importe quel ordre. La clé consiste à ce que toutes ces instructions soient achevées avant l’étape 5.

1. Si vous définissez la stratégie à l’échelle du client sur l’un des modes Skype entreprise, veillez à ce que tous les utilisateurs d’îlot existants en leur attribuant explicitement le mode d’attribution, comme décrit précédemment.

2. Configurer votre client pour le routage direct. Voir [Résumé de la configuration par client du routage direct](#summary-of-per-tenant-configuration-of-direct-routing).

3. Si vous le souhaitez, configurez différentes stratégies d’équipes pour ces utilisateurs (par exemple, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Vous pouvez effectuer cette opération à tout moment, mais si vous voulez vous assurer que les utilisateurs disposent de la configuration correcte lors de la mise à niveau, nous vous conseillons de le faire avant de procéder à la mise à niveau vers le mode TeamsOnly.

4. Préparer la migration de certains utilisateurs pour la boîte vocale : 
   - Le cas échéant, attribuez la licence Teams.  En supposant que l’utilisateur est déjà opérationnel dans Skype entreprise Online, l’utilisateur dispose déjà de Skype entreprise plan 2 ainsi que du système Microsoft Phone. Laissez ces offres activées, y compris la licence de plan 2 de Skype entreprise online.  
   - Assignez la OnlineVoiceRoutingPolicy souhaitée. 

5. Mise à niveau de l’utilisateur : les étapes suivantes doivent être coordonnées. 

   - Dans Office 365, effectuez une mise à niveau vers le mode TeamsOnly (Grant-CsTeamsUpgradePolicy).
   - Sur la SBC, configurez le routage de la voix pour permettre les appels entrants en envoyant des appels vers le routage direct plutôt que vers le serveur de médiation local.


### <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>De Skype entreprise Server en local, avec Enterprise Voice, pour le routage direct

Dans ce scénario, l’utilisateur est toujours hébergé sur site dans Skype entreprise et sa connectivité PSTN est également locale. La migration de ces utilisateurs vers le mode TeamsOnly avec la fonctionnalité RTC implique de les activer pour le routage direct, puis de déplacer l’utilisateur vers le Cloud. 
 
Les étapes de base sont décrites ci-dessous.  Les étapes 1-5 sont répertoriées dans la séquence proposée, mais peuvent être effectuées dans n’importe quel ordre. La clé consiste à ce que toutes ces instructions soient exécutées avant l’étape 6.

1. Si vous définissez la stratégie à l’échelle du client sur l’un des modes Skype entreprise, veillez à ce que les utilisateurs de l’îlot actuel en attribuant explicitement le mode d’îlot, comme décrit précédemment.

2. Si vous ne l’avez pas déjà fait, [configurez l’Organisation pour Skype entreprise hybride](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Configurer votre client pour le routage direct. Voir [Résumé de la configuration par client du routage direct](#summary-of-per-tenant-configuration-of-direct-routing).

4. Si vous le souhaitez, configurez différentes politiques d’équipe pour ces utilisateurs (par exemple, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Vous pouvez effectuer cette opération à tout moment, mais si vous voulez vous assurer que les utilisateurs disposent de la configuration correcte lors de la mise à niveau, nous vous conseillons de le faire avant de procéder à la mise à niveau vers TeamsOnly.

5. Attribuez les licences Office 365 si nécessaire.  L’utilisateur doit disposer des équipes et de Skype entreprise Online plan 2, ainsi que du système téléphonique. Si le plan 2 de Skype entreprise Online est désactivé, réactivez-le.  

6. Mise à niveau de l’utilisateur : les étapes suivantes doivent être coordonnées. 

   - À l’aide des outils Skype entreprise en local, exécutez l’option Move-CsUser with-MoveToTeams. Si vous utilisez une version de Skype entreprise Server qui ne prend pas en charge le commutateur-MoveToTeams, vous devez d’abord lancer Move-CsUser, puis attribuer le mode TeamsOnly dans la console d’administration distante du client ou Teams.

   - Sur la SBC, configurez le routage de la voix pour permettre les appels entrants en envoyant des appels vers le routage direct plutôt que vers le serveur de médiation local. 

   - Dans Office 365 : attribuez le OnlineVoiceRoutingPolicy approprié pour autoriser les appels sortants. 


### <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>De Skype entreprise Server en local, avec Enterprise Voice, à l’offre d’appels Microsoft

Dans ce scénario, l’utilisateur est toujours hébergé sur site dans Skype entreprise et sa connectivité PSTN est également locale. La migration de ces utilisateurs vers le mode TeamsOnly avec la fonctionnalité RTC implique le déplacement de l’utilisateur dans le Cloud, en transférant son numéro entre l’ancien opérateur et un plan d’appel Microsoft ou en attribuant un nouveau numéro à l’utilisateur. 

Les étapes de base sont décrites ci-dessous.Les étapes 1-5 sont répertoriées dans la séquence proposée, mais peuvent être effectuées dans n’importe quel ordre. La clé consiste à ce que toutes ces instructions soient exécutées avant l’étape 6. 

1. Si vous définissez la stratégie à l’échelle du client sur l’un des modes Skype entreprise, veillez à ce que les utilisateurs de l’îlot actuel en attribuant explicitement le mode d’îlot, comme décrit précédemment. 

2. Si vous ne l’avez pas déjà fait, [configurez l’Organisation pour Skype entreprise hybride](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity). 

3. Si vous le souhaitez, configurez différentes stratégies d’équipes pour ces utilisateurs (par exemple, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Vous pouvez effectuer cette opération à tout moment, mais si vous voulez vous assurer que les utilisateurs disposent de la configuration correcte lors de la mise à niveau, nous vous conseillons de le faire avant de procéder à la mise à niveau vers TeamsOnly. 

4. Attribuez les licences Office 365 si nécessaire.L’utilisateur doit disposer des équipes et de Skype entreprise Online plan 2, ainsi que du système téléphonique. Si le plan 2 de Skype entreprise Online est désactivé, réactivez-le.  

5. Obtenez des numéros de téléphone pour vos utilisateurs. (Pour plus d’informations, voir [gérer les numéros de téléphone pour votre organisation](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).)

   - Si vous voulez réutiliser les numéros, envoyez une demande de portage à votre opérateur.  
   - Vous pouvez aussi acheter de nouveaux numéros directement auprès de Microsoft. 

6. Mettez à niveau l’utilisateur. À l’aide des outils Skype entreprise locaux, exécutez Move-CsUser avec le commutateur-MoveToTeams.  

    - Si vous transférez des numéros vers Microsoft, vous devez coordonner le minutage de cette opération pour qu’il se produise lorsque le port intervient. 

    - Si vous utilisez de nouveaux numéros de Microsoft, vous devez modifier le LineUri de l’utilisateur.Pour cela, vous devez effectuer cette opération dans les outils locaux, puis synchronisés avec le Cloud via Azure AD Connect. Nous vous conseillons de prendre le temps que l’opération de déplacement-CsUser doit être simultanée quand Azure AD Connect synchronise la modification. 

### <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Résumé de la configuration par client du routage direct 

1. Assurez-vous que votre contrôleur de bordure de session (SBC) est compatible avec le routage direct en passant en revue [cette liste](direct-routing-border-controllers.md). Vous devez également vérifier que vous disposez de la version de microprogramme correcte.  

2. Associez votre SBC local au service de routage direct Teams. Pour plus d’informations, voir [jumeler l’SBC au service de routage direct du système téléphonique](direct-routing-configure.md#pair-the-sbc-to-the-direct-routing-service-of-phone-system). 

3. Cette configuration est essentiellement un miroir de la configuration locale. La configuration en ligne se compose des éléments suivants : 
   - OnlineVoiceRoutingPolicy (sur la base de la VoiceRoutingPolicy locale lors de la migration des utilisateurs de Skype entreprise Online et sur la base d’VoicePolicy lors de la migration des utilisateurs de Skype entreprise à l’aide de la voix entreprise).
   - Objets OnlinePSTNUsage (sur la base de l’utilisation RTC locale). 
   - Objets OnlineVoiceRoute (en fonction de VoiceRoute locale). 

Pour plus d’informations, consultez [configurer le routage direct](direct-routing-configure.md). 

### <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Gérer la propriété EnterpriseVoiceEnabled lors de la migration 

Qu’il s’agisse de l’utilisation d’un routage direct ou d’un plan d’appels Microsoft, un utilisateur doit avoir EnterpriseVoiceEnabled = true dans Azure AD pour que l’utilisateur dispose de la fonctionnalité RTC.  EnterpriseVoiceEnabled (« EV-Enabled ») est une propriété (pas une stratégie) qui existe dans un répertoire local et dans le Cloud. La valeur du Cloud est le sujet de l’équipe.  La logique exacte de la façon dont le mode EV est défini sur true dépend du scénario suivant : 

- Si l’utilisateur est doté du service EV dans un serveur Skype entreprise local et qu’une licence de système téléphonique est affectée à l’utilisateur avant de le déplacer vers le Cloud grâce à Move-CsUser, l’utilisateur en ligne est configuré avec EV-enabled = true. 

- Si un utilisateur TeamsOnly existant ou Skype entreprise Online dispose d’une licence de système téléphonique, le EV est activé par défaut.  C’est également le cas si un utilisateur local est déplacé vers le Cloud avant d’affecter la licence du système téléphonique. Dans les deux cas, l’administrateur doit spécifier l’applet de commande suivante : 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="coexistence-of-teams-with-skype-for-business"></a>Coexistence de teams avec Skype entreprise

Cette section résume le comportement qui peut être rencontré lors de l’exécution d’équipes et de clients Skype entreprise au sein d’une même organisation, indépendamment du mode et de la méthode de mise à niveau utilisée :

- [Meetings](#meetings)
- [Interopérabilité](#interoperability)
- [Conversations teams-interopérabilité et threads natifs](#teams-conversations---interop-versus-native-threads)
- [Présence](#presence)
- [Fédération](#federation)
- [Contacts](#contacts)

### <a name="meetings"></a>Meetings

Quels que soient leur mode, les utilisateurs peuvent toujours participer à n’importe quel type de réunion auxquelles ils sont invités, qu’il s’agisse de Skype entreprise ou d’équipes.  Toutefois, les utilisateurs doivent rejoindre la réunion avec un client correspondant qui correspond au type de la réunion :

- S’il s’agit d’une réunion en équipe, tous les participants (qu’il s’agisse de TeamsOnly, d’îlots ou d’utilisateurs Skype entreprise) utilisent le client teams pour rejoindre la réunion. Si teams n’est pas installé, l’utilisateur sera dirigé vers le Web lors d’une tentative de participation à une réunion.

- S’il s’agit d’une réunion Skype entreprise, tous les participants (qu’il s’agisse d’TeamsOnly, d’îlots ou d’utilisateurs Skype entreprise) utilisent le client Skype entreprise pour rejoindre la réunion. Si le client Skype entreprise n’est pas installé, l’utilisateur est dirigé vers le Web pour s’y joindre par le biais de l’application de réunion Skype.

Lors de l’organisation de réunions, le type de réunion qui est planifié est basé sur le mode de l’organisateur, comme indiqué dans le tableau suivant :

| Mode de l’organisateur    |      Comportement |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Toutes les réunions planifiées dans Teams. Le complément Skype entreprise n’est pas disponible dans Outlook. | 
| SfbWithTeamsCollab, SfbOnly   | Toutes les réunions planifiées dans Skype entreprise. Le complément teams n’est pas disponible dans Outlook. | 
| Archipels |     Vous pouvez planifier des réunions dans Skype entreprise ou Teams. Les deux compléments sont disponibles dans Outlook. | 


### <a name="interoperability"></a>Interopérabilité

Teams prend en charge l’interopérabilité (« interopérabilité ») avec Skype entreprise dans certains cas. La communication d’interopérabilité fait référence à une discussion ou un appel entre un utilisateur de Skype entreprise et un utilisateur de teams.  La communication interopérabilité est possible uniquement entre deux utilisateurs. la discussion ou l’ajout d’utilisateurs supplémentaires n’est pas pris en charge.

Une discussion ou un appel d’interopérabilité entre deux utilisateurs est créé lorsque les conditions suivantes sont remplies :

- Un utilisateur travaille en équipe et l’autre utilise Skype entreprise.

- Le mode du destinataire de la communication initiale n’est pas un îlot (sinon la communication ne serait pas disponible sur le même client) si les deux utilisateurs appartiennent à la même organisation. Dans les scénarios fédérés, l’utilisateur expéditeur utilise équipes, et le destinataire n’est pas en mode TeamsOnly. 

- L’utilisateur d’équipes n’a pas de compte Skype entreprise local hébergé sur site. 

Dans le cadre de la communication d’interopérabilité, les discussions sont en texte brut uniquement. Par ailleurs, le partage de fichiers et le partage d’écran ne sont pas possibles *dans la discussion d’interopérabilité*. Toutefois, les utilisateurs d’une conversation d’interopérabilité peuvent facilement atteindre le partage de fichiers et/ou d’écran en créant une réunion à la demande à partir de la discussion d’interopérabilité, comme décrit ci-dessous :

- Si l’utilisateur teams tente de partager son écran, une réunion teams à la demande est créée automatiquement et un lien d’invitation à cette réunion est envoyé au client de l’utilisateur Skype entreprise. Lorsque vous cliquez sur le lien, l’utilisateur de Skype entreprise ouvre teams et joint la réunion. Les deux utilisateurs travaillent désormais à une réunion teams et peuvent partager selon les besoins.

- Si l’utilisateur Skype entreprise utilise un client à partir de 2018 ou une version ultérieure et tente de partager du contenu, une réunion Skype entreprise à la demande est créée automatiquement et un lien d’invitation à cette réunion est envoyé au client de l’utilisateur Teams. Lorsque vous cliquez sur le lien, l’utilisateur teams tente de participer à la réunion Skype entreprise. Si l’utilisateur de teams a installé le client Skype entreprise, il s’ouvre et l’utilisateur est invité à se connecter (s’il n’y a pas encore de connexion).  Si le client Skype entreprise n’est pas installé sur l’utilisateur Teams, l’utilisateur est invité à utiliser la version Web. Lorsque les deux utilisateurs sont connectés, ils sont dans une réunion Skype entreprise et peuvent partager selon les besoins.

### <a name="teams-conversations---interop-versus-native-threads"></a>Conversations teams-interopérabilité et threads natifs

Étant donné que les communications d’interopérabilité ne prennent pas en charge toutes les fonctionnalités de conversation d’équipe native, le client teams gère des threads de conversation distinctes pour la communication équipes-à-équipes et équipes-Skype entreprise. Ces conversations sont rendues différemment dans l’interface utilisateur : les threads d’interopérabilité peuvent être différenciés d’un thread d’équipe natif ordinaire, en procédant comme suit :

- Absence de contrôles pour la mise en forme de texte enrichi, de partage de fichiers ou d’écrans, incapacité à ajouter des utilisateurs.
- Modification de l’icône de l’utilisateur cible, avec le « S » pour Skype entreprise.

Ces différences apparaissent dans les captures d’écran suivantes :

Conversation d’équipes en équipes native avec test de l’utilisateur G3

![Diagramme illustrant une conversation d’équipes en équipes Native](media/teams-upgrade-native-thread.png)

Conversation d’interopérabilité avec le même test de l’utilisateur G3

![Diagramme illustrant une conversation d’équipe à teams](media/teams-upgrade-interop-thread.png)

Une fois qu’un fil de discussion est créé, son type n’est jamais modifié. Une fois créé, un thread d’interopérabilité dans teams sera toujours acheminé vers le client Skype entreprise de l’utilisateur cible. Un thread natif sera toujours acheminé vers le client teams de l’utilisateur cible.  Si le mode de l’utilisateur d’un destinataire change, il est possible que les threads teams existants vers cet utilisateur ne fonctionnent plus et qu’une remarque s’affiche dans la conversation avec un lien pour démarrer une nouvelle conversation native, comme illustré dans la capture d’écran suivante. Pour plus d’informations, reportez-vous à la rubrique [conversations et appels à partir de threads existants](coexistence-chat-calls-presence.md#chats-and-calls-from-pre-existing-threads).


![Diagramme montrant une discussion avec un utilisateur de Skype entreprise mis à niveau](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Présence

La présence d’un utilisateur donné est basée sur l’activité de l’utilisateur dans le service via le client. La présence est alors publiée pour que d’autres utilisateurs puissent la voir.  Skype entreprise et équipes étant des services distincts avec des clients distincts, chaque service dispose de son propre état de présence pour un utilisateur.   Il existe également une synchronisation entre les services de présence dans équipes et dans Skype entreprise online.  Cela permet à un service de publier la présence de l’utilisateur à partir de l’autre service, si nécessaire. 

Le comportement de publication de présence repose sur le mode de l’utilisateur. Il existe trois cas de base :

- Si un utilisateur est en mode TeamsOnly, tous les autres utilisateurs voient la présence d’équipes pour cet utilisateur, quel que soit le client utilisé.

- Si un utilisateur se trouve dans l’un des modes Skype entreprise, tous les autres utilisateurs voient la présence Skype entreprise pour cet utilisateur, quel que soit le client utilisé.

- Si un utilisateur est en mode d’îlot, le statut de présence publié dans Skype entreprise et équipes est indépendant, de sorte que les présences des utilisateurs au sein de la même organisation varient selon le client de l’autre utilisateur. Les utilisateurs des organisations fédérées verront la présence de cet utilisateur en fonction de son activité Skype entreprise, car le trafic fédéré vers le mode d’utilisation des classeurs dans Skype entreprise.

Par exemple, supposons que l’utilisateur A est en mode îlot. Si l’utilisateur A est actif dans Teams, mais n’est pas connecté à Skype entreprise, les autres utilisateurs verront que l’utilisateur A est actif à partir du client de leur équipe, mais dans leur client Skype entreprise, ils verront l’utilisateur A déconnectée. C’est par conception, car l’utilisateur A ne peut pas être contacté s’il n’exécute pas le client. 

Pour plus d’informations, voir [presence](coexistence-chat-calls-presence.md#presence).

### <a name="federation"></a>Fédération

La Fédération entre teams et un autre utilisateur de Skype entreprise nécessite que l’utilisateur de teams soit à domicile en ligne dans Skype entreprise. TeamsUpgradePolicy gère le routage des conversations et appels fédérés entrants. Le comportement de routage fédéré est le même que pour les mêmes scénarios de client, sauf dans le mode îlot. Lorsque les destinataires sont en mode îlot :

- Discussions et appels passés à partir de teams dans Skype entreprise si le destinataire est dans un client fédéré.
- Les conversations et les appels passés à partir de teams dans teams si le destinataire est dans le même client.
- Les conversations et les appels passés à partir de Skype entreprise sont toujours terrains dans Skype entreprise.

Une discussion fédérée entre un utilisateur d’équipes et Skype entreprise est un fil d’interopérabilité, afin que le texte et le partage enrichis ne soient pas possibles. Dans l’interface utilisateur, les discussions fédérées sont similaires aux threads d’interopérabilité des locataires, sauf qu’il existe une remarque indiquant que l’utilisateur est externe.

Lorsque les équipes introduisent la Fédération pour la première fois, une discussion fédérée entre les deux équipes utilisateurs d’Teams était également un thread d’interopérabilité, mais à l’avenir, la Fédération d’équipes Native sera introduite et fournit des fonctionnalités complètes pour les conversations entre les utilisateurs qui utilisent le mode TeamsOnly. . 

Pour en savoir plus, voir [routage fédéré pour les nouvelles conversations ou appels](coexistence-chat-calls-presence.md#federated-routing-for-new-chats-or-calls).

### <a name="contacts"></a>Contacts

Les équipes et Skype entreprise disposent de listes de contacts distinctes. Cela signifie que les ajouts de contacts, la suppression et les modifications apportées dans un système ne sont pas synchronisés avec l’autre système. En revanche, lorsque l’un ou l’autre des deux événements suivants se produit, vos contacts Skype entreprise sont automatiquement copiés dans teams : 

- Pour tout utilisateur de Skype entreprise Online, lors de la première connexion à Teams, les contacts de Skype entreprise seront copiés dans Teams.  Ce comportement n’est pas disponible pour les utilisateurs disposant d’un compte local dans Skype entreprise Server.  

- Une fois qu’un utilisateur a procédé à la mise à niveau vers TeamsOnly (par le biais de l’attribution d’TeamsUpgradePolicy ou par le biais de Move-CsUser-MoveToTeams), la prochaine fois qu’un utilisateur se connecte à Teams, les contacts existants dans Skype entreprise sont fusionnés avec les contacts existants déjà dans Teams. Ce comportement se produit si le compte Skype entreprise de l’utilisateur est hébergé sur site ou en ligne. 

Dans les deux cas, le transfert de contacts de Skype entreprise à teams est asynchrone et peut donc être de quelques minutes avant l’affichage des contacts dans Teams. Les deux événements ci-dessus sont le déclencheur de la copie.  

## <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer une connectivité hybride entre Skype entreprise Server et Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Utiliser le service de migration de réunion (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

