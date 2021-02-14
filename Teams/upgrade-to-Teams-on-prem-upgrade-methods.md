---
title: Mise à niveau vers Teams à partir d’un déploiement local de Skype Entreprise - Microsoft Teams
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

Cet article décrit les méthodes de mise à niveau pour la migration vers Teams. Cet article est le deuxième de ceux qui décrivent les concepts de mise à niveau et d’implémentation pour les administrateurs informatiques.  

- [Vue d’ensemble](upgrade-to-teams-on-prem-overview.md)
- **Méthodes de mise à niveau** (cet article)
- [Outils de gestion de votre mise à niveau](upgrade-to-teams-on-prem-tools.md)
- [Autres éléments à prendre en considération pour les organisations avec Skype Entreprise sur site](upgrade-to-teams-on-prem-considerations.md)
- [Mise en œuvre de votre mise à niveau](upgrade-to-teams-on-prem-implement.md)
- [Considérations sur le réseau téléphonique commuté (PSTN)](upgrade-to-teams-on-prem-pstn-considerations.md)

De plus, les articles suivants décrivent les concepts de mise à niveau et les comportements de coexistence importants :

- [Coexistence de Teams et de Skype Entreprise](upgrade-to-teams-on-prem-coexistence.md)
- [Modes de coexistence - Référence](migration-interop-guidance-for-teams-with-skype.md)
- [Expérience client Teams et conformité aux modes coexistence](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="upgrade-methods"></a>Méthodes de mise à niveau

Deux méthodes s’offrent à vous pour mettre à niveau une organisation existante avec Skype Entreprise (en ligne ou en local) vers Teams : la méthode Des fonctionnalités superposées et la méthode Sélection. Cet article vous aide à choisir la méthode qui s’offre à vous dans votre organisation en décrivant les deux méthodes et en présentant les avantages et les inconvénients de chacune d’elles. 

- [Méthode des capacités superposées (à l’aide du mode Îles)](#overlapping-capabilities-method-using-islands-mode)

   Les utilisateurs d’une organisation Skype Entreprise existante sont introduits dans Teams de sorte qu’ils peuvent utiliser les deux clients lors d’une phase de transition. Pendant cette période, la plupart des fonctionnalités de Teams ne sont pas disponibles. Le mode pour cette configuration est appelé Îles. Il s’agit du mode par défaut pour toute organisation existante utilisant Skype Entreprise. Une fois que l’organisation est prête, l’administrateur déplace les utilisateurs en mode TeamsOnly.

- [Sélectionner la méthode des fonctionnalités (à l’aide d’un ou plusieurs modes Skype Entreprise)](#select-capabilities-method-using-skype-for-business-modes)

   L’administrateur gère la transition (de Skype Entreprise vers Teams) des fonctionnalités de conversation, d’appel et de planification de réunion pour les utilisateurs de leur organisation.  Chacune de ces fonctions est disponible dans Skype Entreprise ou Teams, mais pas les deux. Les administrateurs utilisent TeamsUpgradePolicy pour contrôler quand déplacer cette fonctionnalité vers Teams pour leurs utilisateurs. Les utilisateurs qui ne sont pas encore en mode TeamsOnly continuent d’utiliser Skype Entreprise pour les appels et les discussions, et les deux ensembles d’utilisateurs peuvent communiquer via les fonctionnalités interop. Les administrateurs gèrent la transition en migrant progressivement d’autres utilisateurs en mode TeamsOnly.  

Après avoir compris et choisi votre méthode de mise à niveau, vous pouvez en savoir plus sur les outils de gestion de la mise à niveau de votre organisation [vers Teams.](upgrade-to-teams-on-prem-tools.md)

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Méthode des capacités superposées (à l’aide du mode Îles)

Grâce à la méthode des fonctionnalités qui se chevauchent, les utilisateurs peuvent utiliser les clients Teams et Skype Entreprise pour les discussions, les appels VoIP et les réunions. Cet État est appelé mode « Îles », car le trafic des communications pour Skype Entreprise et Teams reste distinct (même pour le même utilisateur) et les deux clients ne communiquent jamais entre eux (pour les utilisateurs au sein de la même organisation). Par exemple, supposons que l’utilisateur A du destinataire soit en mode Îles :

- Les communications lancées à partir du client Skype Entreprise d’un autre utilisateur seront toujours dans le client Skype Entreprise de l’utilisateur A.

- Les communications lancées à partir du client Teams d’un autre utilisateur seront toujours propriétés dans le client Teams de l’utilisateur A, si l’autre utilisateur fait *partie de la même organisation.* 

- Les communications lancées à partir du client Teams d’un autre utilisateur seront toujours propriétés dans le client Skype Entreprise de l’utilisateur A, si l’autre utilisateur fait partie *d’une organisation fédérée.*

Le mode Îles est le mode par défaut de TeamsUpgradePolicy pour toute organisation existante qui n’a pas encore mis à niveau vers TeamsOnly. Lorsque vous affectez une licence Microsoft 365 ou Office 365, les licences Teams et Skype Entreprise Online sont affectées par défaut. (C’est vrai même si l’utilisateur est domicile sur site dans Skype Entreprise Server. Que l’utilisateur soit domicile sur site ou en ligne, laissez la licence Skype Entreprise Online activée, car elle est actuellement nécessaire pour la fonctionnalité complète de Teams.) En fait, si vous n’avez pas pris de mesures pour modifier la configuration par défaut, il se peut que vous uxiez déjà une utilisation significative de Teams dans votre organisation.  C’est l’un des avantages de l’approche de fonctionnalités qui se chevauchent. Il permet une adoption rapide, pilotée par les utilisateurs finaux, au sein d’une organisation.

Pour que cette méthode fonctionne efficacement, tous les utilisateurs doivent exécuter les deux clients simultanément. Les conversations et appels entrants et en provenance de l’organisation à un utilisateur en mode Îles peuvent se trouver dans le client Skype Entreprise ou Teams, et ce n’est pas sous le contrôle du destinataire. Si l’expéditeur et le destinataire font partie de la même organisation, cela dépend du client utilisé par l’expéditeur pour démarrer la communication. Si l’expéditeur et le destinataire sont dans différentes organisations, les appels et conversations entrants avec un utilisateur en mode Îles arrivent toujours dans le client Skype Entreprise.  

Par exemple, si un destinataire en mode Îles exécute Skype Entreprise mais pas Teams, et qu’une personne de la même organisation les envoie des messages à partir de Teams, le destinataire du mode Îles ne verra pas le message (mais il recevra un e-mail lui disant qu’il a manqué un message dans Teams). De même, si un utilisateur exécute Teams, mais pas Skype Entreprise, et qu’un utilisateur de Skype Entreprise ne voit pas cette conversation.  Ils vont recevoir un e-mail disant qu’un message a été manqué. Dans chacun de ces cas, le comportement est similaire pour les appels. Si les utilisateurs n’exécutent pas les deux clients, cela peut facilement entraîner de la frustration.

Lorsque l’utilisateur A est en mode Îles, la présence de l’utilisateur A telle que vue par les autres utilisateurs dans Teams et dans Skype Entreprise est indépendante :

- D’autres utilisateurs, lors de l’utilisation de Teams, voient les informations de présence en fonction de l’activité de l’utilisateur A dans Teams. 
- D’autres utilisateurs, lorsque vous utilisez Skype Entreprise, voient les informations de présence en fonction de l’activité de l’utilisateur A dans Skype Entreprise. 

Cela signifie que d’autres utilisateurs peuvent voir des états de présence différents pour l’utilisateur A, selon le client qu’ils utilisent. Pour plus d’informations, voir [Présence.](upgrade-to-teams-on-prem-coexistence.md#presence)

Lorsque vous êtes prêt à mettre à niveau les utilisateurs vers le mode TeamsOnly, vous pouvez mettre à niveau les utilisateurs individuellement ou mettre à niveau l’ensemble du client en une seule fois à l’aide de la stratégie à l’échelle du client. Une fois qu’un utilisateur est mis à niveau en mode TeamsOnly, il reçoit toutes les conversations et appels entrants dans Teams. (Notez que la migration des réunions Skype Entreprise vers des réunions Teams est déclenchée uniquement lors de l’application de TeamsUpgradePolicy à des utilisateurs individuels, et non pas par client. Pour [plus d’informations,](upgrade-to-teams-on-prem-tools.md#meeting-migration) voir Migration de réunion.)

Toutefois, les destinataires non mis à niveau en mode Îles peuvent continuer à recevoir des conversations et des appels d’un utilisateur TeamsOnly dans ses clients Skype Entreprise ou Teams.  En effet, le client Teams tient des threads de conversation distincts pour les communications entre équipes et entre les équipes Skype Entreprise, même pour le même utilisateur.  (Voir [Conversations Teams - Interop ou threads natifs.)](upgrade-to-teams-on-prem-coexistence.md#teams-conversations---interop-versus-native-threads)  Par exemple, supposons que l’utilisateur d’îles A utilise Teams pour envoyer un message à l’utilisateur B de Teams. Lorsque l’utilisateur B répond à cette conversation, la communication se place dans le client Teams de l’utilisateur A. Supposons maintenant que l’utilisateur A utilise le client Skype Entreprise pour envoyer un message à TeamsOnly Utilisateur B. L’utilisateur B recevra la conversation dans Teams, mais il s’agit d’une conversation distincte dans le client Teams de l’utilisateur B par rapport à l’autre conversation. Si l’utilisateur B répond à cette conversation avec l’utilisateur A, il se place dans le client Skype Entreprise de l’utilisateur A. 

Le tableau suivant récapitule l’expérience Teams pour le mode Îles et le mode TeamsOnly :  

| Expérience Teams | En mode Îles | En mode TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Conversations et appels entrants reçus dans :|  Teams ou Skype Entreprise | Équipes |
| Appels PSTN reçus dans : | Skype Entreprise <br>(L’utilisation de la fonctionnalité PSTN dans Teams n’est pas prise en charge en mode Îles.)    | Équipes |   
 |Présence  | La présence dans Skype Entreprise et Teams est indépendante. Les utilisateurs peuvent voir des états différents pour le même utilisateur des îles, selon le client qu’ils utilisent. | La présence est basée uniquement sur l’activité de l’utilisateur dans Teams. Tous les autres utilisateurs, quel que soit le client qu’ils utilisent, voient cette présence. | 
 | Planification de réunions   | Par défaut, les utilisateurs peuvent planifier des réunions dans Teams ou Skype Entreprise. Ils voient les deux modules dans Outlook. |   Les utilisateurs ne peuvent planifier des réunions que dans Teams. Seul le add-in Teams est disponible dans Outlook. | 

Le tableau suivant récapitule les avantages et les inconvénients de l’utilisation de la méthode de fonctionnalités de chevauchement pour migrer votre organisation vers Teams.

| Professionnels     |       Inconvénients |
| :------------------ | :---------------- |
| Permet une adoption rapide au sein d’une organisation.| Possible de confusion chez les utilisateurs finaux, car deux clients ont des fonctionnalités similaires, mais des interfaces utilisateur différentes. En outre, ils n’ont aucun contrôle sur le client auquel les conversations/appels entrants arrivent. |
| Permet aux utilisateurs d’apprendre et de se familiariser avec Teams tout en ayant un accès total à Skype Entreprise. | Possible d’insatisfaction de l’utilisateur final suite à l’insatisfaction des messages manqués si l’utilisateur n’exécute pas les deux clients. Les utilisateurs peuvent se plaignent de ne pas recevoir de messages.|
| Minimum d’efforts d’administration pour la mise en place de Teams. | Il peut être difficile de « sortir des îles » et de passer en mode TeamsOnly si tous les membres de l’organisation n’utilisent pas Teams, en particulier si tous les utilisateurs ne sont pas actifs dans Teams. Par exemple, une fois qu’un sous-ensemble d’utilisateurs est mis à niveau en mode TeamsOnly, ces utilisateurs enverront uniquement des messages dans Teams. Pour le reste de la population en mode Îles, ces messages sont toujours reçus dans Teams. Mais si une partie de cette population n’exécute pas Teams, elle aura l’impression que ces messages sont manqués. |
|  | Lors de l’utilisation de Teams, les utilisateurs qui ont un compte local dans Skype Entreprise Server ne peuvent pas utiliser interop ou la fédération.  Cela peut potentiellement semer la confusion si vous avez un mélange d’utilisateurs d’îles : certains d’entre eux ent domicile dans Skype Entreprise Online et d’autres à Skype Entreprise sur site.   |

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Sélectionner la méthode des fonctionnalités (à l’aide des modes Skype Entreprise)

Certaines organisations préféreront peut-être offrir à leurs utilisateurs finaux une expérience plus simple et plus prévisible au moment de la transition de Skype Entreprise vers Teams. Dans ce modèle, les administrateurs informatiques utilisent l’un des modes Skype Entreprise dans TeamsUpgradePolicy pour désigner explicitement les utilisateurs qui restent dans Skype Entreprise avant d’être migrés vers le mode TeamsOnly. Étant prêt à déplacer les utilisateurs sélectionnés en mode TeamsOnly, l’administrateur met à jour le mode pour ces utilisateurs vers TeamsOnly. À mesure que le déploiement progresse, de plus en plus d’utilisateurs sont transitionés de Skype Entreprise vers le mode TeamsOnly.  Au cours de cette transition :

- Les utilisateurs toujours sur Skype Entreprise reçoivent toutes les conversations et appels entrants dans leur client Skype Entreprise, que la communication provienne des équipes de l’autre utilisateur ou du client Skype Entreprise. De plus, pour ces utilisateurs Skype Entreprise, les fonctionnalités d’appel et de conversation dans le client Teams sont désactivées pour éviter toute confusion de l’utilisateur final et assurer un routage approprié. 

- Les utilisateurs en mode TeamsOnly reçoivent toutes les conversations et appels entrants dans leur client Teams, quelle que soit l’origine de la communication : Teams, Skype Entreprise ou tout type d’utilisateur fédéré. 

Contrairement à la méthode des îles, dans la méthode des fonctionnalités sélectionnées, les utilisateurs de Skype Entreprise et les utilisateurs de TeamsOnly peuvent communiquer entre eux. La communication entre un utilisateur De Skype Entreprise et l’utilisateur de Teams est appelée interopérabilité ou « interop ». La communication interop est possible en tête-à-tête pour les conversations et les appels entre un utilisateur dans Skype Entreprise et un autre utilisateur dans Teams. toutefois, certaines fonctionnalités avancées peuvent ne pas être disponibles. (Voir [Interopérabilité.)](upgrade-to-teams-on-prem-coexistence.md#interoperability) De plus, les utilisateurs invités peuvent toujours participer à une réunion Skype Entreprise ou Teams, toutefois, ils doivent utiliser un client correspondant au type de réunion. Pour plus d’informations, [voir Réunions.](upgrade-to-teams-on-prem-coexistence.md#meetings)

Étant donné que les utilisateurs dans une transition de fonctionnalités sélectionnées ne sont généralement pas en mode Îles, la présence d’un utilisateur est cohérente quel que soit le client utilisé par l’autre utilisateur. Si l’utilisateur est dans l’un des modes Skype Entreprise, tous les autres utilisateurs voient la présence en fonction de l’activité de cet utilisateur dans Skype Entreprise. De même, si un utilisateur est en mode TeamsOnly, tous les autres utilisateurs voient la présence en fonction de l’activité de cet utilisateur dans Teams. Pour plus d’informations, [consultez Présence.](upgrade-to-teams-on-prem-coexistence.md#presence)

Pour une organisation qui n’a pas encore commencé à utiliser Teams, l’administrateur doit changer le mode à l’échelle du client de Islands à SfbWithTeamsCollab. (Pour les organisations qui ont déjà une utilisation de Teams, l’administrateur doit « dé- utiliser » les utilisateurs déjà actifs dans Teams pour s’assurer que cette modification ne s’applique pas à eux. Pour plus d’informations, consultez une méthode de sélection des fonctionnalités pour une organisation qui utilise [déjà Teams en mode Îles.)](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Lorsque le mode passe d’Islands à SfbWithTeamsCollab, un utilisateur qui n’a jamais utilisé Teams ne voit aucune différence dans l’utilisation de Skype Entreprise. Toutefois, si cet utilisateur commence à utiliser Teams, il sera exposé uniquement à des fonctionnalités telles que Teams & Channel et Fichiers. Les fonctionnalités de conversation, d’appel et de planification de réunions ne sont pas disponibles dans Teams, car l’administrateur a (pour l’instant) désigné Skype Entreprise comme client souhaité pour ces fonctions.  

Remarque : lorsque l’utilisateur A passe d’Îles à l’un des modes Skype Entreprise, le client Teams d’un autre utilisateur qui communique avec l’utilisateur A a besoin de savoir que le mode de l’utilisateur A a changé pour pouvoir router la communication vers le client approprié pour l’utilisateur A.  Pour les utilisateurs qui ont déjà établi des conversations Entre équipes natives avec l’utilisateur A, jusqu’à 36 heures peuvent être avant que les clients Teams de ces autres utilisateurs sachent que le mode d’utilisation de Islands vers n’importe quel mode Skype Entreprise peut être changé.   En revanche, les modifications apportées au mode TeamsOnly d’un utilisateur existant sont découvertes par d’autres clients dans les 2 heures.

Lorsque les administrateurs sont prêts, ils peuvent modifier la conversation, les appels et la planification de réunions pour un utilisateur donné dans Teams en mettant à jour le mode de l’utilisateur sur TeamsOnly.  

Par contre, l’administrateur peut tout d’abord déplacer uniquement la planification des réunions vers Teams, tout en laissant les fonctions de conversation et d’appel dans Skype Entreprise à l’aide du mode SfBWithTeamsCollabAndMeetings. Ce mode permet aux organisations de passer à Teams pour les réunions - si les utilisateurs ne sont pas encore prêts à passer en mode TeamsOnly (généralement parce qu’il peut être nécessaire de plus de temps pour migrer la fonctionnalité PSTN existante). Ce scénario d’urgence est appelé [Réunions en premier.](meetings-first.md)

Le tableau suivant récapitule les avantages et les inconvénients de l’utilisation des modes Skype Entreprise comme une étape de transition vers le mode TeamsOnly.


| Professionnels     |       Inconvénients |
| :------------------ | :---------------- |
| Routage prévisible pour l’utilisateur final.  Tous les appels et conversations sont soit dans Skype Entreprise, soit dans Teams (mais pas les deux), sur la base de la sélection de l’administrateur.  | Il manque à Vos conversations Interop la prise en charge du texte enrichi, du partage de fichiers et du partage d’écran.  Ce problème peut être contourner avec les réunions à la demande, mais ce n’est pas aussi transparent.  |
| Éliminez la confusion des utilisateurs, car une fonctionnalité donnée n’est disponible que dans un seul client.  | Les utilisateurs ne peuvent pas essayer les deux clients côte à côte pour le même ensemble de fonctionnalités. Cela peut particulièrement être un facteur si les utilisateurs perçoivent la transition de Skype Entreprise vers Teams comme un changement de paradigme majeur. |
| Permet d’obtenir une introduction incrémentielle de Teams.  |  | |
| L’administrateur contrôle entièrement la transition de Skype Entreprise à Teams. |  | | 
| Permet à une organisation d’utiliser Teams pour les réunions, même si elle n’est pas encore prête à passer entièrement en mode TeamsOnly. |  | |
| La présence d’un utilisateur donné telle qu’elle est vue par d’autres est la même, quel que soit le client qu’il utilise.  |  | |

## <a name="summary-of-upgrade-methods"></a>Résumé des méthodes de mise à niveau

Le tableau suivant récapitule les méthodes de mise à niveau :

| Capacités superposées (à l’aide du mode Îles)     |      Sélectionner des fonctionnalités (à l’aide des modes Skype Entreprise) |
| :------------------ | :---------------- |
| Avant la mise à niveau vers TeamsOnly, les utilisateurs doivent exécuter les deux clients simultanément, car les conversations et appels entrants peuvent être dirigés vers l’un ou l’autre client.   | Les conversations et appels n’ont lieu que dans un seul client, selon le mode du destinataire. Les utilisateurs non mis à niveau peuvent exécuter les deux clients, mais il n’existe aucun chevauchement fonctionnel (les appels et les discussions ne sont pas disponibles dans Teams).  Les administrateurs peuvent également déterminer si les utilisateurs peuvent planifier des réunions dans Teams ou Skype Entreprise.   |
| Les utilisateurs peuvent utiliser Skype Entreprise et Teams côte à côte pour les mêmes fonctionnalités.   | Permet aux administrateurs d’introduire de nouvelles fonctionnalités nettes de Teams aux utilisateurs finaux (Équipes et canaux), sans fournir les mêmes fonctionnalités que celle qui existe également dans Skype Entreprise.   |
|Il n’existe pas d’interop entre Skype Entreprise et Teams lorsque les deux utilisateurs sont en mode Îles. Une fois que certains utilisateurs ont été mis à niveau vers TeamsOnly, une conversation interop peut se produire entre ces utilisateurs et d’autres utilisateurs toujours en mode Îles. Toutefois, l’utilisateur des îles peut choisir d’utiliser Teams et d’éviter la conversation interop. | Interop est requis pour la communication entre les utilisateurs de Skype Entreprise et Teams.   |


## <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Utilisation du service Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

