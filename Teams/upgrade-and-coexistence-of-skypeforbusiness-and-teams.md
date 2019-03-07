---
title: Mettre à niveau Microsoft Teams Skype pour les entreprises | Modes de Coexistence
author: lsomi
ms.author: lsomi
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen, bjwhalen
description: Détails de Skype pour les options de coexistence Business et Microsoft Teams modes et trajets mise à niveau pour les équipes de Skype pour les entreprises avec des exemples de scénarios.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7bf81e18970366fee397504642b181f6e8c40add
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461611"
---
![Étapes du voyage mise à niveau, en mettant l’accent sur le déploiement et la phase d’implémentation] (media/upgrade-banner-deployment.png "Étapes du voyage mise à niveau, en mettant l’accent sur le déploiement et la phase d’implémentation")

Cet article fait partie de la phase de déploiement et l’implémentation de votre parcours de mise à niveau. Avant de continuer, vérifiez que vous avez effectué les activités suivantes :

- [Inscrit les parties prenantes du projet](upgrade-enlist-stakeholders.md)
- [Définies par l’étendue de votre projet](https://aka.ms/SkypetoTeams-Scope)
- [Comprendre la coexistence et l’interopérabilité de Skype pour professionnels et les équipes](https://aka.ms/SkypeToTeams-Coexist)

# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Choisissez votre mise à niveau parcours Skype pour les entreprises aux équipes

Comme un Skype existante pour le client d’entreprise, votre transition aux équipes complète peut prendre du temps. Toutefois, vous pouvez commencer l’optimisation des équipes aujourd'hui, grâce à vos utilisateurs d’utiliser des équipes à côté de Skype pour les entreprises. Étant donné qu’il existe certaines fonctionnalités communes entre les deux applications, nous vous recommandons de consulter la coexistence disponible et de mise à niveau des modes pour aider à déterminer le chemin d’accès est adapté à votre organisation. Par exemple, vous pourrez choisir d’activer tous les charges de travail sur les deux solutions sans l’interopérabilité. Ou bien, vous pouvez décider de gérer l’expérience utilisateur, par l’introduction progressive fonctionnalités équipes ou en ciblant les groupes d’utilisateurs des capacités de select, jusqu'à ce que votre organisation est prête à mettre à niveau tout le monde aux équipes. Utilisez le résultat de votre pilote pour vous aider à évaluer la route droite mise à niveau pour votre organisation.

> [!IMPORTANT]
> Cet article décrit les différents modes qui vous permettent de gérer les modalités dans Skype pour les entreprises et les équipes sont disponibles pour vos utilisateurs. Comme avec tout déploiement, nous vous invitons à [piloter votre plan concerné](pilot-essentials.md) avec un groupe d’utilisateurs sélectionné avant la mise à niveau de votre organisation aux équipes. N’oubliez pas de présentation de la nouvelle technologie peut être sans interruption de service pour les utilisateurs. Prendre le temps d’évaluer la préparation de l’utilisateur et implémenter un plan de formation avant l’implémentation les modes décrites dans le présent document et de communication.

## <a name="upgrade-journey-building-blocks"></a>Mise à niveau de blocs de construction de route

Pour officiellement préparer votre organisation pour son voyage aux équipes, vous devez commencer à planifier pour les scénarios de mise à niveau afin de pouvoir éventuellement votre organisation entièrement favorablement équipes en tant que votre solution de collaboration et de communication unique.

Pour aider votre processus de décision, familiarisez-vous avec les différents modes, concepts et la terminologie appropriée à la mise à niveau de Skype pour les entreprises aux équipes. Pour plus d’informations, voir [les équipes Microsoft et Skype pour l’interopérabilité et coexistence d’entreprise](https://aka.ms/SkypeToTeams-Coexist)

Lorsque certains de vos utilisateurs sont prêts à utiliser uniquement des équipes pour leurs communications quotidiennes et de collaboration a besoin, vous pouvez commencer la mise à niveau de ces utilisateurs aux équipes en activant le mode **Équipes uniquement** pour les.

S’il n’est pas possible pour toute l’organisation atteindre les équipes, vous pouvez démarrer en appliquant les équipes à côté de Skype pour les entreprises en mode de coexistence **(îles)** . Comme les modes de coexistence supplémentaires ( **Skype pour les entreprises avec la collaboration des équipes** et **Skype pour l’entreprise grâce à des réunions et la collaboration des équipes**), sont deviennent progressivement totalement disponibles dans les prochains mois, vous pouvez également démarrer en entièrement l’adoption d’équipes en tant que solution de collaboration d’un groupe tout d’abord tout en conservant Skype pour les entreprises en tant que solution de communications unifiées de votre organisation. C’est le chemin recommandé par Microsoft pour les clients qui utilisent Skype pour Business Server (locale ou hybride) et les clients avec la complexité importante dont trajectoire aux équipes inclura une période de coexistence de type long.

![Capture d’écran de mise à niveau des blocs de construction de Skype pour les entreprises aux équipes, constituée de Skype pour les entreprises avec la collaboration des équipes&ndash;mode uniquement, Skype pour les entreprises avec collaboration des équipes et mode de réunions, mode (îles), les équipes seule et Skype pour Business&ndash;mode uniquement.](media/upgrade_journeys_building_block.png)

Le tableau suivant compare les modes de mise à niveau et de coexistence.

|Mode |Situation |Utilisation recommandée |Avantages |Avertissements |
|---|---|---|---|---|
|(Îles) |Skype plus petit ou plus simple pour le déploiement d’entreprise<br><br>Capacité et sa volonté de gérer une complexité à court terme pour atteindre plus rapidement des équipes |Accédez à l’expérience d’équipes complète aussi rapidement que possible<br><br>Réaliser une preuve de concept (PoC) des équipes<br><br>Chemin d’accès de la mise à niveau recommandée pour les organisations qui ont adopté Skype pour Business Online |Simple à utiliser<br><br>Les équipes plus riche expérience initial pour toutes les fonctionnalités |Requiert une communication efficace pour éviter toute confusion et à l’utilisation du lecteur vers des équipes<br><br>Stratégie de sortie requiert que les utilisateurs ont adopté entièrement équipes avant de commencer la mise à niveau vers la phase équipes uniquement<br><br>Aucune interopérabilité pour les utilisateurs en mode (îles) ; également aucun fédération des équipes lorsque Skype l’utilisateur pour un compte professionnel est ne hébergé sur site|
|Skype pour les entreprises avec la collaboration des équipes |Skype pour le déploiement d’entreprise avec ne sont pas encore requise par les équipes (par exemple, avancées de conformité)<br><br>Devoir à long terme et/ou engagement Skype pour les entreprises|Adoption des équipes de démarrer rapidement, recherchant tout d’abord sur la collaboration de groupe<br><br>Pour conserver toutes les charges de travail de communications unifiées sur Skype pour les entreprises pour l’instant<br><br>Recommandé d’utiliser comme point de départ pour l’organisation commençant leur voyage de site (ou hybride) Skype pour les entreprises|Aucune fonctionnalité qui se chevauchent entre les équipes et Skype pour les entreprises<br><br>Messagerie instantanée de conversation et de planifier des réunions résideront dans Skype pour les entreprises (liée à l’appel)<br><br>Interopérabilité avec les utilisateurs des équipes uniquement|
|Skype pour l’entreprise grâce à des réunions et la collaboration des équipes |Skype pour le déploiement d’entreprise avec à utiliser d’enterprise voice et ne sont pas encore requise par les équipes d’appel<br><br>Devoir à long terme et/ou engagement Skype pour les entreprises<br><br>Peut utiliser un service de réunion de tiers|Kit d’adoption des équipes de démarrer rapidement, allant au-delà de collaboration de groupe<br><br>Améliorer l’expérience de réunions de vos utilisateurs<br><br>Conseillé d’utiliser sur des organisations de site qui souhaitent tirer parti des réunions d’équipes avant de se préparer à la mise à niveau complète (généralement en raison d’Enterprise Voice sur site). |Aucune fonctionnalité qui se chevauchent<br><br>Réunions supérieures des équipes. Plateforme de feuille de route, expérience utilisateur et autres fonctionnalités, la qualité et la fiabilité<br><br>« Documents better Together » rencontre entre les équipes et Skype pour les entreprises<br><br>Utilisateurs de l’interopérabilité d’équipes uniquement.|Messagerie instantanée et conversation résideront dans Skype pour les entreprises (liée à l’appel)|
|Équipes uniquement |Certains utilisateurs doivent rester sur Skype pour les entreprises<br><br>Vous mettez à niveau votre Skype pour les utilisateurs professionnels Online aux équipes pendant que Skype pour les entreprises de conserver les utilisateurs locaux sur Skype pour Business Server<br><br>Vous a peut-être déjà déployé les utilisateurs en mode (îles) et que vous êtes prêt à retirer Skype pour les entreprises pour les groupes d’utilisateurs |Réduire les coûts de variable sur Skype pour les entreprises (opérations du serveur local, contrat d’externalisation et ainsi de suite)<br><br>Accédez à l’expérience d’équipes complète aussi rapidement que possible, pour au moins certains utilisateurs|Limite la confusion de l’utilisateur en fournissant un seul client pour fonctionner avec l’interopérabilité avec les utilisateurs de Skype pour Business uniquement, Skype pour entreprise avec la Collaboration des équipes, Skype pour l’entreprise grâce à des réunions et la Collaboration des équipes|Interopérabilité prend uniquement en charge la conversation de base et l’appel entre Skype pour professionnels et les équipes et d’escalade interopérabilité scénarios pour le partage du bureau et de conversation à plusieurs et appel|
|Skype pour les entreprises uniquement |Certains utilisateurs doivent rester sur Skype pour les entreprises<br><br>|Limite la confusion de l’utilisateur en fournissant un seul client pour travailler avec<br><br>Utilisateur peut toujours participer aux réunions d’équipes qu’ils sont invités à|Continuer à répondre aux besoins d’entreprise actuellement peuvent uniquement être satisfaits par Skype pour les entreprises<br><br>Interopérabilité avec les utilisateurs des équipes uniquement|Interopérabilité prend uniquement en charge la conversation de base et l’appel entre Skype pour professionnels et les équipes et d’escalade interopérabilité scénarios pour le partage du bureau et de conversation à plusieurs et appel|

## <a name="upgrade-journeys"></a>Parcours de mise à niveau

Vous pouvez effectuer plusieurs approches de mise à niveau à partir de Skype pour les entreprises, soit en ligne ou sur site, aux équipes :

- Dans un trajet de mise à niveau direct, équipes avec Skype pour les entreprises d’abord déployer en mode **(îles)** dans le cadre d’évaluation et d’adoption au plus tôt et puis mise à niveau de vos utilisateurs **Équipes uniquement** en mode dans le but de rapidement le retrait Skype pour les entreprises à partir de la environnement pour tous les utilisateurs dans l’organisation. Il s’agit de voyage recommandé pour les clients en ligne Skype métiers, sauf s’ils sont concernés que ne seront pas les utilisateurs d’avoir deux outils pour effectuer la même action (conversation, appel, la planification de la réunion).
- Un parcours de mise à niveau progressif offre un mode de mise à niveau et une coexistence spécifique à un groupe spécifique d’utilisateurs (également appelé une *cohorte*), en fonction de leurs besoins de collaboration et de communications. Au fil du temps, l’organisation toute entière peut convergent en utilisant uniquement les équipes et remplacer par la suite Skype pour les entreprises. Toutefois, si votre organisation a des raisons commerciales incontournables pour conserver Skype pour les entreprises — par exemple une dépendance sur une solution Unified Communications Managed API UCMA qui s’intègre avec line-of-business applications, ou d’une solution de séparation déontologique actuellement disponible pour Skype pour les entreprises uniquement ou un déploiement Enterprise Voice complexe prend du temps de mise à niveau vers **Les équipes uniquement**, vous pouvez mettre à niveau une partie des utilisateurs **Équipes uniquement** en mode tout en conservant Skype pour les utilisateurs professionnels d’une du modes de coexistence pour une partie de vos utilisateurs. Voyage au pays de la mise à niveau progressive est l’approche recommandée pour locale (et hybride) les clients commençant par Skype pour les entreprises avec le mode de coexistence de Collaboration des équipes et déplacement à partir de là équipes uniquement en mode lorsque remplies requis pour les utilisateurs (et éventuellement la Skype pour l’entreprise grâce à des réunions et la Collaboration des équipes de cohabitation).

> [!IMPORTANT]
> Pour les deux types de voyage au pays de mise à niveau, si votre organisation est actuellement un Skype pour le déploiement local de Business uniquement, vous devez démarrer l’implémentation Skype pour un environnement hybride Business avant la mise à niveau de vos utilisateurs **Équipes uniquement** en mode de planification. Cela vous permet également de faciliter l’interopérabilité avec des équipes.
>
> Utilisez [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) pour guider votre Skype pour l’implémentation de hybride Business.

> [!NOTE]
> **Équipes uniquement** en mode nécessite que les utilisateurs qui font partie de cohortes être hébergés sur Skype pour Business Online, et une relation hybride entre votre Skype pour le déploiement local de Business et votre Skype pour client Business Online est requise pour faciliter la interopérabilité entre les équipes et Skype pour les entreprises. Le déplacement à Skype pour Business Online doit être réalisée pour les utilisateurs qui font partie du cohortes avant qu’ils sont mis à niveau vers **Les équipes uniquement** en mode. Skype pour Business Server 2019 et Skype pour Business Server 2015 avec mise à jour CU8 peuvent simplifier les mécanismes de mise à niveau des utilisateurs locaux aux équipes à la gestion de la migration vers Skype pour Business Online et de mise à niveau des utilisateurs **Équipes uniquement** en mode en une seule étape .

### <a name="direct-upgrade-journey"></a>Voyage au pays de la mise à niveau directe

Mise à niveau direct voyage est illustré dans le diagramme suivant.

![Capture d’écran du parcours de mise à niveau direct. Tous les utilisateurs à l’origine équipes dans mode (îles), puis effectuer la transition en mode équipes uniquement, avec l’état final de l’organisation toute entière mis à niveau vers les équipes.](media/upgrade_journey_direct_upgrade.png)

Les équipes est déployé sur tous les utilisateurs dans l’organisation et configuré en mode **(îles)** . Lorsque votre organisation a déterminé que les équipes est prête répondre à tous vos communications et la collaboration doit, avertir les utilisateurs et les mettre à niveau vers le mode **Équipes uniquement** . À ce stade, Skype pour les entreprises peut être retiré de l’environnement.

### <a name="gradual-upgrade-journey"></a>Voyage au pays de la mise à niveau progressive

Vous trouverez un exemple d’un trajet de mise à niveau progressif dans le diagramme suivant.

![Du processus de mise à niveau progressive, cohortes d’utilisateurs utilisent initialement équipes en mode d’évaluation (îles), puis en différents modes de mise à niveau pour adoption au plus tôt, en côte à côte Skype pour les entreprises. Une transition cohortes équipes uniquement en mode, tandis qu’un groupe d’utilisateurs reste avec Skype pour les entreprises avec le mode de réunions et de collaboration des équipes.](media/upgrade_journey_gradual_upgrade.png)

Équipes est déployée dans l’organisation en mode **(îles)** pour l’évaluation et puis déplacer vers la coexistence de différents modes pour différents groupes d’utilisateurs de la mise à niveau. Par exemple, un groupe d’utilisateurs peut être activé pour le mode **(îles)** , un autre activé pour le mode **Skype pour l’entreprise grâce à des réunions et la collaboration des équipes** , pendant un groupe d’utilisateurs tiers peut être activé à l’origine pour **Skype pour les entreprises avec des équipes collaboration uniquement** mode.

Au fil du temps, groupes d’utilisateurs peuvent être mis à niveau en mode **Équipes uniquement** , suivi par le reste de l’organisation. Finalement, l’organisation toute entière sera prête à retirer Skype pour les entreprises et d’utiliser des équipes uniquement pour les communications et la collaboration, ou, si les exigences commerciales imposent que Skype pour les entreprises être conservé pour un groupe spécifique — la majorité des utilisateurs dans le organisation peut utiliser uniquement les équipes. <br><br>
<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Point de décision</td><td><ul> Les parcours de mise à niveau est adapté aux besoins de votre organisation ?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étape suivante</td><td><ul> Identifier votre modèle de déploiement actuel, utilisez des cas et des considérations importantes pour votre organisation informe voyage aux équipes qui est la mieux adapté à votre organisation.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Point de décision</td><td><ul> Quel scénario de mise à niveau est applicable à votre organisation ?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul> Décider du scénario du parcours de mise à niveau de votre organisation en fonction de la messagerie, réunions et les impératifs de l’appel.<br><br> Déterminez le travail supplémentaire requis pour effectuer votre parcours de mise à niveau.<br><br></ul></td></tr>
</table>

Après avoir choisi la meilleur voyage mise à niveau pour votre organisation, [effectuez la mise à niveau pour les équipes](https://aka.ms/SkypeToTeams-Upgrade).
