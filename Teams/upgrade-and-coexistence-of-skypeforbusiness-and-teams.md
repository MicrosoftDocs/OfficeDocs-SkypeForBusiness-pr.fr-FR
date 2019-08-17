---
title: Mise à niveau de Microsoft teams à partir de Skype entreprise | Modes, coexistence
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen, bjwhalen
description: Des informations sur les modes et modes de coexistence de Skype entreprise et Microsoft Teams, ainsi que la mise à niveau vers des équipes de Skype entreprise avec des exemples de scénario.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords:
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d3c2b53767cb9bbaff3cbe4f2aeacea36fcc01d2
ms.sourcegitcommit: f053b3a51a89751453101978e265efefcb30849c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/16/2019
ms.locfileid: "36437488"
---
![Diagramme de parcours de mise à niveau, mettant l’accent sur l’étape de définition du projet] (media/upgrade-banner-project-definition.png "Étapes du parcours de la mise à niveau, mettant l’accent sur l’étape de définition du projet")

Cet article fait partie de l’étape définition du projet de votre parcours de mise à niveau. Avant de continuer, confirmez que vous avez terminé les activités suivantes:

- [Inscription des parties prenantes du projet](upgrade-enlist-stakeholders.md)
- [Définition de l’objectif de votre projet](https://aka.ms/SkypetoTeams-Scope)
- [Compréhension de la coexistence et de l’interopérabilité de Skype entreprise et équipes](https://aka.ms/SkypeToTeams-Coexist)

# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Choisissez le passage de votre mise à niveau de Skype entreprise à teams

En tant que client Skype entreprise existant, la transition complète vers teams peut prendre un certain temps. Néanmoins, vous pouvez commencer à utiliser teams dès aujourd’hui en permettant à vos utilisateurs d’utiliser teams en même temps que Skype entreprise. Étant donné qu’il existe d’autres fonctionnalités qui se chevauchent entre les deux applications, nous vous conseillons de passer en revue les modes de coexistence et de mise à niveau disponibles pour vous aider à déterminer le chemin approprié pour votre organisation. Par exemple, vous pouvez choisir d’activer toutes les charges de travail sur les deux solutions sans interopérabilité. Vous pouvez également décider de gérer l’utilisation de l’utilisateur, soit en introduisant progressivement les fonctionnalités d’équipe ou en ciblant des groupes d’utilisateurs pour les fonctionnalités sélectionnées, tant que votre organisation n’est pas en mesure de mettre à niveau tout le monde vers Teams. Utilisez le résultat de votre pilote pour vérifier le bon déroulement de la mise à niveau de votre organisation.

> [!IMPORTANT]
> Skype entreprise Online sera supprimé le 31 juillet 2021, mais il ne sera plus accessible ou pris en charge. Pour optimiser la réalisation des avantages et garantir que votre organisation dispose du moment approprié pour mettre en œuvre la mise à niveau, nous vous encourageons à commencer votre trajet vers Microsoft teams dès aujourd’hui.

Cet article présente les différents modes qui vous permettent de gérer les modalités de gestion des modalités de Skype entreprise et équipes disponibles pour les utilisateurs. Comme pour n’importe quel déploiement, nous vous encourageons vivement à [piloter votre plan prévu](pilot-essentials.md) avec un groupe d’utilisateurs sélectionné avant de mettre à niveau votre organisation vers Teams. N’oubliez pas que l’introduction d’une nouvelle technologie peut être perturbatrice pour les utilisateurs. Prenez le temps d’évaluer la compatibilité des utilisateurs et d’implémenter un plan de communication et de formation avant d’implémenter les modes décrits dans les présentes.

> [!TIP]
> Rejoignez-nous pour des ateliers en direct et interactifs qui vous aideront à partager des conseils, des meilleures pratiques et des ressources conçues pour lancer la planification et l’implémentation de la mise à niveau.
>
>Participez d’abord à la planification de votre session de [mise à niveau](https://aka.ms/SkypeToTeamsPlanning) pour commencer.


## <a name="upgrade-journey-building-blocks"></a>Briques de construction de mise à niveau

Pour préparer officiellement votre organisation aux équipes, vous devez commencer à planifier des scénarios de mise à niveau, ce qui permettra finalement à votre organisation d’adopter pleinement teams comme votre solution de communication et de collaboration unique.

Pour vous guider dans le processus de prise de décision, vous devez vous familiariser avec les différents modes, concepts et terminologie pertinents pour la mise à niveau de Skype entreprise vers Teams. Pour plus d’informations, reportez-vous à la rubrique [Microsoft Teams, coexistence et interopérabilité de Skype entreprise](https://aka.ms/SkypeToTeams-Coexist)

Lorsque certains de vos utilisateurs sont prêts à utiliser uniquement les équipes pour leurs communications quotidiennes et leurs besoins en matière de collaboration, vous pouvez commencer à mettre à niveau ces utilisateurs vers teams en autorisant uniquement le mode **équipe** .

S’il n’est pas possible pour l’ensemble de votre organisation de migrer vers Teams, vous pouvez commencer par piloter les **** équipes en même temps que Skype entreprise en mode de coexistence des îlots. Étant donné que les modes de coexistence supplémentaires (par exemple, **Skype entreprise avec la collaboration en équipe** et **Skype entreprise avec la collaboration et les réunions en équipe**) sont devenus complètement disponibles dans les prochains mois, vous pouvez aussi commencer entièrement en adoptant teams en tant que solution de collaboration de groupe, vous devez tout d’abord faire en sorte que Skype entreprise soit une solution de communication unifiée. Il s’agit de la méthode recommandée par Microsoft pour les clients qui utilisent Skype entreprise Server (en local ou en environnement hybride) et leurs clients dont la trajectoire aux équipes inclura une longue période de coexistence.

![Capture d’écran de la mise à niveau de blocs de construction de Skype entreprise vers teams] (media/upgrade_journeys_building_block.png "Capture d’écran de la mise à niveau de blocs de Skype entreprise vers équipes, composée de Skype entreprise avec&ndash;le mode de collaboration en équipe uniquement, Skype entreprise avec le mode de collaboration et les réunions teams Mode&ndash;professionnel uniquement.")

Le tableau suivant compare les modes de coexistence et de mise à niveau.

|Veille |Évolution |Utilisation recommandée |Inconvénients |Inconvénients |
|---|---|---|---|---|
|Archipels |Déploiement de Skype entreprise plus petit ou plus simple<br><br>Capacité et volonté de gérer une certaine complexité à court terme pour une migration plus rapide des équipes |Rendez-vous entièrement opérationnel dans teams<br><br>Conduire une preuve de concept (PoC) d’équipes<br><br>Chemin de mise à niveau recommandée pour les organisations ayant adopté Skype entreprise Online |Simplicité d’utilisation<br><br>Profitez de l’expérience des équipes le plus riche pour toutes les fonctionnalités |Nécessite une bonne communication utilisateur pour éviter toute confusion et favoriser l’utilisation de teams<br><br>La stratégie de fermeture exige que les utilisateurs aient entièrement adopté teams avant de commencer la mise à niveau vers la phase équipes uniquement.<br><br>Pas d’interopérabilité pour les utilisateurs en mode îlot; par ailleurs, aucune Fédération de teams lorsque le compte de l’utilisateur Skype entreprise est hébergé sur site.|
|Collaboration avec teams dans Skype entreprise |Déploiement de Skype entreprise avec des contraintes qui ne sont pas encore satisfaites par Teams (par exemple, mise en conformité avancée)<br><br>Besoin de plus de temps pour les entreprises et/ou pour s’engager sur Skype entreprise|Démarrez rapidement le développement d’équipes, en insistant sur la collaboration de groupe<br><br>Vous voulez conserver toutes les charges de travail de communications unifiées dans Skype entreprise pour le moment<br><br>Utilisation recommandée comme point de départ pour l’organisation du démarrage de ses déplacements depuis local (ou hybride) Skype entreprise|Pas de capacités communes entre teams et Skype entreprise<br><br>La discussion par messagerie instantanée et la planification de réunions se trouvent dans Skype entreprise (lié aux appels)<br><br>Interopérabilité avec les utilisateurs uniquement dans teams|
|Skype entreprise avec collaboration et réunions en équipe |Déploiement de Skype entreprise avec une utilisation significative de la voix et des exigences de l’entreprise qui ne sont pas encore remplies par les appels d’équipes<br><br>Besoin de plus de temps pour les entreprises et/ou pour s’engager sur Skype entreprise<br><br>Vous utilisez peut-être un service de réunion tiers|Commencer rapidement à adopter Teams, au-delà de la collaboration de groupe<br><br>Amélioration de l’interface utilisateur pour les réunions<br><br>Utilisation recommandée pour les organisations locales qui souhaitent tirer parti des réunions d’équipes avant d’être prêt à effectuer une mise à niveau complète (généralement en raison d’une voix entreprise locale). |Aucune fonctionnalité ne chevauchant<br><br>Réunions de grande qualité dans Teams. Introduction aux fonctionnalités, expérience utilisateur et multiplateforme, qualité et fiabilité<br><br>Une expérience «conjointe» entre Skype entreprise et Teams<br><br>Utilisateurs d’interopérabilité uniquement dans Teams.|La messagerie instantanée et la conversation se trouvent dans Skype entreprise (associé aux appels)|
|Équipes uniquement |Teams uniquement représente la destination finale de tous les utilisateurs, en définitive.<br><br>Certains utilisateurs ont besoin de rester sur Skype entreprise<br><br>Vous effectuez la mise à niveau de vos utilisateurs Skype entreprise Online vers teams tout en préservant les utilisateurs locaux de Skype entreprise sur Skype entreprise Server<br><br>Vous avez peut-être déjà déployé des utilisateurs en mode îlot et nous sommes prêts à supprimer Skype entreprise pour les groupes d’utilisateurs |Réduction des coûts variables sur Skype entreprise (opérations serveur locales, contrat d’approvisionnement, etc.)<br><br>Accédez à l’ensemble de l’interface teams aussi rapidement que possible, pour au moins quelques utilisateurs.|Limite la confusion des utilisateurs en n’offrant qu’un seul client pour l’interopérabilité avec les utilisateurs dans Skype entreprise, Skype entreprise, collaboration en équipe, Skype entreprise avec collaboration et réunions en équipe|L’interopérabilité ne prend en charge que les discussions de base et les appels entre Skype entreprise et équipes, et les scénarios d’escalade d’interopérabilité pour le partage de bureau et les appels et les appels multitiers|
|Skype entreprise uniquement |Certains utilisateurs ont besoin de rester sur Skype entreprise<br><br>|Limite la confusion des utilisateurs en fournissant un seul client<br><br>Les utilisateurs peuvent toujours participer à des réunions d’équipes auxquelles ils sont invités|Continuent de répondre aux besoins de votre entreprise qui ne peuvent être satisfaits que par Skype entreprise<br><br>Interopérabilité avec les utilisateurs uniquement dans teams|L’interopérabilité ne prend en charge que les discussions de base et les appels entre Skype entreprise et équipes, et les scénarios d’escalade d’interopérabilité pour le partage de bureau et les appels et les appels multitiers|

> [!TIP]
> Pour vous aider à identifier le mode de mise à niveau recommandé en fonction des fonctionnalités que vous voulez activer dans teams alors que Skype entreprise est toujours en cours d’utilisation, tirez parti de l' [Assistant Mise à niveau de Skype to teams](https://aka.ms/SkypeToTeamsWizard).

## <a name="upgrade-journeys"></a>Déplacements de la mise à niveau

Vous pouvez effectuer plusieurs méthodes pour effectuer une mise à niveau de Skype entreprise (en ligne ou sur site) vers teams:

- Dans le cadre d’une mise à niveau directe, vous devez tout d’abord déployer teams en même temps que Skype entreprise en mode **îlot** dans le cadre de l’évaluation et de l’adoption initiale, puis mettre à niveau vos utilisateurs vers le mode **équipes uniquement** en ayant pour effet de déclasser rapidement Skype entreprise du environnement pour tous les utilisateurs au sein de l’organisation. Il s’agit du voyage recommandé pour les clients de Skype entreprise Online, sauf s’ils ne sont pas concernés par le recours à deux outils pour effectuer la même action (discussions, appels et planification de réunion).
- Un parcours de mise à niveau progressif fournit une coexistence et un mode de mise à niveau spécifiques à un ** groupe d’utilisateurs spécifique (également appelé cohorte), en fonction des besoins en matière de communication et de collaboration. Au fil du temps, l’ensemble de votre organisation pourra se conformer aux équipes uniquement et remplacera éventuellement Skype entreprise. En revanche, si votre organisation a des raisons professionnelles impérieuses de conserver Skype entreprise, par exemple, dépendance sur une solution de UCMA (Unified Communications Managed API) qui s’intègre à des applications métier ou à une solution murale éthique; actuellement disponible uniquement pour Skype entreprise, ou un déploiement voix entreprise complexe dont la mise à niveau vers teams **** ne prend pas de temps, vous pouvez mettre à niveau une partie des utilisateurs vers le mode **équipes uniquement** tout en préservant les utilisateurs de Skype entreprise dans l’un des modes de coexistence pour une portion de votre population d’utilisateurs. Le parcours de mise à niveau progressif est l’approche recommandée pour les clients locaux (et hybrides) commençant par Skype entreprise avec le mode de coexistence collaboration avec teams et passant du mode de placement au mode équipes uniquement lorsque les exigences des utilisateurs sont satisfaites (sans doute par le biais du Skype entreprise avec la collaboration en équipe et le mode de coexistence réunions.

> [!IMPORTANT]
> Dans les deux cas, si votre organisation est actuellement un déploiement local de Skype entreprise, vous devez commencer à planifier la mise en œuvre de Skype entreprise hybride avant de mettre à niveau vos utilisateurs vers le mode **équipes uniquement** . Cela permet également de faciliter l’interopérabilité avec les équipes.

> [!NOTE]
> Le mode **équipes uniquement** nécessite que les utilisateurs qui font partie des cohortes soient hébergés dans Skype entreprise Online et qu’une relation hybride entre votre déploiement Skype entreprise local et votre client Skype entreprise Online est nécessaire pour faciliter le interopérabilité entre Skype entreprise et Teams. Le passage à Skype entreprise Online doit être effectué pour les utilisateurs qui font partie des cohortes avant d’être mis à niveau vers le mode **équipes uniquement** . Skype entreprise Server 2019 et Skype entreprise Server 2015 avec la mise à jour CU8 peuvent simplifier le processus de mise à niveau des utilisateurs locaux en équipes en gérant la migration dans Skype entreprise Online et en mettant à niveau les utilisateurs vers le mode **équipes uniquement** en une seule étape. .

### <a name="direct-upgrade-journey"></a>Voyage de mise à niveau directe

Le diagramme suivant montre comment effectuer une mise à niveau directe.

![Capture d’écran du parcours de la mise à niveau directe] (media/upgrade_journey_direct_upgrade.png "Capture d’écran du parcours de la mise à niveau directe. Tous les utilisateurs utilisent initialement teams en mode îlot, puis transition vers le mode équipes uniquement, avec l’état final de l’organisation entière mise à niveau vers Teams.")

Teams est déployée pour tous les utilisateurs de l’organisation et configuré en mode **îlot** . Lorsque votre organisation détermine que teams est prêt à répondre à tous vos besoins en matière de communication et de collaboration, informez les utilisateurs et mettez-les à niveau en mode **équipes uniquement** . À ce stade, Skype entreprise peut être supprimé de l’environnement.

### <a name="gradual-upgrade-journey"></a>Route de mise à niveau progressive

Le schéma suivant illustre un exemple de parcours de mise à niveau progressif.

![Exemple illustrant le passage de la mise à niveau progressive] (media/upgrade_journey_gradual_upgrade.png "Dans le cas d’une mise à niveau progressive, les cohortes des utilisateurs utilisent initialement teams en mode îlot pour une évaluation, puis dans de nombreux modes de mise à niveau pour une utilisation précoce, côte à côte avec Skype entreprise. Certaines cohortes passent en mode équipes uniquement, tandis que les utilisateurs travaillent avec Skype entreprise avec le mode de collaboration et de réunions en équipe.")

Teams est déployé dans l’organisation en mode **îlot** à des fins d’évaluation, puis passe à différents modes de coexistence et de mise à niveau pour différents groupes d’utilisateurs. Par exemple, un groupe d’utilisateurs peut être activé pour le mode **îles** , une autre pour **Skype entreprise avec le mode de collaboration et de réunions d’équipe** , tandis qu’un troisième groupe d’utilisateurs peut être activé pour la première fois pour **Skype entreprise avec Teams. mode de collaboration uniquement** .

Au fil du temps, des groupes d’utilisateurs peuvent être mis à niveau vers le mode **équipes uniquement** , puis du reste de l’organisation. Pour le moment, l’ensemble de votre organisation sera prêt à supprimer Skype entreprise et utilisera uniquement les équipes de communication et de collaboration, ou, si les besoins de l’entreprise indiquent que Skype entreprise est conservé pour un groupe spécifique, la plupart des utilisateurs dans le l’organisation peut uniquement utiliser les équipes. <br><br>
<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Point de décision</td><td><ul> Quelle est la fréquence de mise à niveau adaptée aux besoins de votre organisation?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Étape suivante</td><td><ul> L’identification de votre modèle de déploiement actuel, des scénarios d’utilisation et des principales considérations relatives à votre organisation informeront les équipes qui sont les plus adaptées à votre organisation.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Point de décision</td><td><ul> Quels sont les scénarios de mise à niveau applicables à votre organisation?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul> Déterminez la chronologie de la mise à niveau de votre organisation sur la base de la messagerie, des réunions et des besoins de l’entreprise.<br><br> Déterminez le fonctionnement supplémentaire requis pour terminer la mise à niveau.<br><br></ul></td></tr>
</table>

Une fois que vous avez choisi le meilleur niveau de mise à niveau pour votre organisation, [effectuez la mise à niveau vers teams](https://aka.ms/SkypeToTeams-Upgrade).
