---
title: FAQ sur la mise à niveau de Skype Entreprise vers Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Forum aux questions sur le passage de Skype Entreprise à Microsoft Teams.
localization_priority: Priority
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
ms.openlocfilehash: 0192f6d822d19b2efd22beba81c1865197aff53c
ms.sourcegitcommit: c49698e03fa3bdd7c82496189b200ac6bb4e05a1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48320899"
---
# <a name="faq--upgrading-from-skype-for-business-to-microsoft-teams"></a>FAQ – Mise à niveau de Skype Entreprise vers Microsoft Teams


## <a name="general-questions"></a>Questions d’ordre général

**Les clients doivent-ils passer de Skype Entreprise Online à Teams à une date précise ?**<br>
Oui. [Skype Entreprise Online](skype-for-business-online-retirement.md) sera supprimé le 31 juillet 2021. À partir de cette date, il ne sera plus accessible ni pris en charge. Nous encourageons les clients Skype Entreprise Online à commencer à utiliser Teams et à commencer à planifier leurs mises à niveau dès maintenant afin de pouvoir terminer la mise à niveau avant la date de retrait.


**Combien de temps prendra la transition vers Teams de mon organisation ?**<br>
Vous pouvez définir le parcours de mise à niveau de Skype Entreprise vers Teams de votre organisation. Pour vous aider dans le cadre de la planification et de l’exécution, nous avons développé des conseils de mise à niveau complets basés sur un cadre éprouvé conçu pour vous aider à naviguer dans les éléments techniques et organisationnels de la modification. Commencez votre parcours en vous familiarisant avec notre [infrastructure de réussite de la mise à niveau](upgrade-framework.md) et des ressources associées qui constituent l’élément central de votre navigation entre Skype Entreprise et Teams.


**Existe-t-il une mise à niveau recommandée pour Skype Entreprise ?**<br>
Nous vous recommandons de planifier votre migration de Skype Entreprise à Teams en tirant parti des conseils et ressources sur [aka.ms/SkypetoTeams](upgrade-start-here.md) et de participer à un [atelier gratuit sur la planification de la mise à niveau](upgrade-workshops-landing-page.yml) pour identifier et implémenter le chemin de mise à niveau le mieux adapté aux besoins de votre organisation.

**Où puis-je en savoir plus sur les modes de coexistence dans le Centre d’administration Microsoft Teams ?**<br>
Dans le centre d'administration Microsoft Teams, des modes de coexistence supplémentaires apparaîtront, afin que votre organisation puisse gérer la transition de Skype Entreprise vers Teams qui lui convient. En savoir plus [sur les modes de coexistence et de mise à niveau](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

**Que dois-je faire pour me préparer à la mise à niveau ?**<br>
Une mise à niveau réussie inclut la validation de la préparation technique, outre la préparation de l’acceptation par l’utilisateur. Même si vous déterminez que votre organisation n’est pas tout à fait prête pour la mise à niveau vers Teams, vous pouvez commencer le processus de planification dès aujourd’hui. De plus, vous pouvez commencer à vous rendre compte de la valeur de Teams en activant Teams parallèlement à Skype Entreprise. Prise en main de votre [chemin Skype vers Teams[(https://aka.ms/skypetoteams-home) aujourd’hui.

Microsoft propose également des ateliers en direct et interactifs dans lesquels nous partageons des conseils, des pratiques recommandées et des ressources conçues pour lancer la mise à niveau de la planification et de l’implémentation. [En savoir plus sur les ateliers de planification](https://aka.ms/SkypeToTeamsPlanning).


**Mon organisation exécute déjà Teams parallèlement à Skype Entreprise. Est-ce que je peux simplement désactiver Skype Entreprise ?**<br>
Non, vous devez basculez les utilisateurs sur le mode Teams uniquement pour terminer la mise à niveau vers Teams. Si votre organisation est prête à passer à Teams, prenez le temps de communiquer avec les utilisateurs pour leur faire savoir ce qui se passe et leur laisser le temps de s'habituer à Teams. Cela permettra de garantir que leur expérience de mise à niveau est positive et de réduire le nombre d’appels à votre service d’assistance. Pour des exemple de modèles de communication, téléchargez notre [Kit de réussite de la mise à niveau](https://aka.ms/UpgradeSuccessKit).


**Qui puis-je contacter si j’ai des questions sur le processus de mise à niveau ?**<br>
Pour les questions concernant votre mise à niveau, contactez vos points de contact actuels, qui peuvent inclure votre équipe du compte Microsoft désignée, partenaire ou [FastTrack](https://www.microsoft.com/en-us/fasttrack?rtc=1). Vous pouvez également ouvrir un ticket d’aide à partir de votre [Centre d’administration Microsoft Teams](https://admin.teams.microsoft.com/) en cliquant sur le bouton **Besoin d’aide**.

![Bouton Besoin d’aide](media/need-help-button.png)


**Dois-je mettre à niveau tous les utilisateurs sur mon client ou est-ce que je peux choisir de mettre à niveau des utilisateurs spécifiques à tour de rôle ?**<br>
Vous avez la possibilité de mettre à niveau les utilisateurs vers Teams au fur et à mesure de vos besoins, qu’il s’agisse de personnes spécifiques, de groupes d’utilisateurs ou de l’ensemble de votre organisation. Pour vous aider à déterminer l’approche optimale pour votre organisation, évaluez les différents [modes de coexistence et de mise à niveau](teams-and-skypeforbusiness-coexistence-and-interoperability.md) que vous pouvez activer.


**Que se passe-t-il une fois que mes utilisateurs ont été mis à niveau ?**<br>

Après la mise à niveau de vos utilisateurs vers Teams (mode **Teams uniquement**) :

- Leur client Skype Entreprise sera désactivé et ne pourra plus être utilisé, et toutes les discussions et tous les appels seront transférés dans Teams. Ce client continuera à être utilisé pour les réunions Skype Entreprise planifiées auparavant. Si ce client de bureau est désinstallé, les utilisateurs seront redirigés pour accéder aux réunions Skype Entreprise planifiées auparavant via l'application web Skype Entreprise.

- Toutes les réunions Skype Entreprise planifiées avant la mise à niveau fonctionneront comme prévu, mais toutes les nouvelles réunions seront planifiées dans Teams. Si des utilisateurs tentent de se connecter à Skype Entreprise, ils recevront une notification de leur client leur signalant qu’ils ont été mis à niveau vers Teams. Les utilisateurs devront désinstaller manuellement le client Skype Entreprise sur leur appareil mobile.



**Les utilisateurs pourront-ils continuer à utiliser Skype Entreprise une fois que j’aurai activé la notification de mise à niveau dans leur client ?**<br>
La notification de mise à niveau avertira simplement les utilisateurs que Skype Entreprise sera mis à niveau vers Teams et les invitera à commencer à utiliser Teams, s’ils ne l'ont pas déjà fait. Nous recommandons de compléter cette notification par une campagne de sensibilisation (e-mails, FAQ, préparation du service d’assistance, affiches/panneaux) pour communiquer plus de détails spécifiques à votre organisation, tels que le calendrier de la mise à niveau, des appels à l’action pour l’utilisateur, l’accès à une formation, etc. Pour des modèles de communication, téléchargez notre [Kit de réussite de la mise à niveau](https://aka.ms/UpgradeSuccessKit).


**Que cela signifie-t-il en termes de licence ? Comment les clients devront-ils payer pour les services de communications intelligentes dans Teams ?**<br>
Teams est disponible dans les suites Microsoft 365 et Office 365. Les fonctionnalités qui constituent actuellement des charges de travail Premium dans Skype Entreprise Online continueront de l’être dans Teams. Les licences actuelles acquises par les clients seront toujours valables avec Teams. Par exemple, si un client a acheté une licence autonome ou E5 d’audioconférence avec Skype Entreprise, le service d’audioconférence sera activé dans Teams tel qu’il l’est aujourd’hui.


**Microsoft prévoit-il des planifications de mise à niveau ?**<br>
Actuellement, nous n'avons prévu aucun plan de mise à niveau pour les entreprises. Les clients peuvent choisir de passer à Teams si cela est utile pour leur organisation avant la date de retrait de Skype Entreprise Online, le 31 juillet 2021. Nous fournirons aux administrateurs et aux utilisateurs des outils et des instructions pour les aider à effectuer la transition vers Teams.

Afin d’accompagner les organisations de taille modeste qui n’ont pas de ressources informatiques dédiées, Microsoft fournit des mises à niveau automatisées de Skype Entreprise Online vers Teams. Les clients éligibles sont avertis de la mise à niveau par le biais d’e-mails et de notifications du Centre de messages. Des informations plus détaillées sont fournies dans les communications. Pour plus d’informations, voir [Mises à niveau automatisées de Skype Entreprise Online vers Microsoft Teams](upgrade-automated.md).



## <a name="microsoft-teams-capabilities-and-roadmap"></a>Fonctionnalités de Microsoft Teams et feuille de route

**Quels sont les avantages de l'infrastructure principale de Teams ?**<br>
Teams a été créée pour le cloud sur une architecture de microservices très évolutive optimisée en termes de consommation de bande passante, qui fournit une télémétrie plus robuste et qui permet d’effectuer des opérations de maintenance et des mises à jour avec une perturbation minimale. En conséquence, les utilisateurs pourront rejoindre les réunions plus rapidement et bénéficieront d'une meilleure expérience de navigateur sans devoir télécharger de plug-ins. Cette infrastructure moderne permettra d’utiliser plus facilement les services cognitifs Microsoft, qui incluent des fonctionnalités de transcription, de conversion, de reconnaissance vocale et d’apprentissage machine, et qui rendent la communication et la collaboration plus simples et efficaces.

**Comment les clients seront-ils informés de la disponibilité des fonctionnalités de Skype Entreprise dans Teams ?**<br>
Reportez-vous à la [Feuille de route de Microsoft 365](https://aka.ms/O365Roadmap).

**Quels sont les API et SDK qui seront disponibles pour Teams ?**<br>
Pour des informations sur les API et SDK disponibles, consultez la [plateforme pour développeurs Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/).


**Les possibilités de développement tiers seront-elles prises en charge dans Teams ?**<br>
Oui, l'intégration d'applications est l'un des principaux avantages de l'adoption de Teams. Nous prenons actuellement en charge les bots, connecteurs et extensions tiers dans Teams. Un vaste écosystème de compléments est également disponible dans la boutique d’applications Microsoft Teams.

**Teams est-il disponible dans Microsoft 365 Éducation ?**<br>
Teams est disponible dans toutes la suite de licences Microsoft 365 Éducation (Microsoft A1, A3 et A5).

**Teams est-il disponible dans le cloud communautaire du secteur public (GCC) ?**<br>
Oui, Teams est disponible pour la communauté Cloud du gouvernement américain (GCC). Pour plus d’informations, voir [Planifier les déploiements de Microsoft 365 GCC](https://docs.microsoft.com/microsoftteams/plan-for-government-gcc).



## <a name="calling-capabiities"></a>Fonctionnalités d’appel

**Quels sont les projets concernant les fonctionnalités vocales en ligne de Microsoft ?**<br>
L’essentiel de notre solution vocale est le système téléphonique disponible aujourd’hui. Les clients peuvent également ajouter un plan d’appels Microsoft qui fournit une prise en charge complète pour les appels, notamment l’acquisition de numéros et l’affectation directement dans Microsoft 365. Les clients désireux de conserver leurs circuits téléphoniques télécom peuvent utiliser le routage direct (inclus dans le système téléphonique). Combinez et faites correspondre les deux éléments ensemble selon les besoins de votre organisation pour qu’elle bénéficie d’une solution vocale complète.

**Que préconisez-vous pour les clients ayant déjà déployé le système téléphonique (Cloud PBX) dans Skype Entreprise Online ?**<br>
L’appel dans Microsoft Teams répondra à tous vos besoins en matière de communication. Nous encourageons tous clients Microsoft 365 à commencer à utiliser Teams, de manière indépendante ou parallèlement à Skype Entreprise.


**Quelles sont les recommandations pour les clients utilisant Voix Entreprise aujourd’hui qui souhaitent migrer vers Teams et utiliser les fonctionnalités d’appel ?**<br>
Les clients qui souhaitent mettre en œuvre leur propre service téléphonique dans Teams peuvent maintenant le faire avec la disponibilité générale du [routage direct](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359). Le routage direct et les forfaits d’appels sont les deux possibilités de tonalité dans Microsoft Teams.

## <a name="meeting-capabilities"></a>Fonctionnalités de réunion


**La couverture de l’audioconférence dans Teams est-elle différente dans Skype Entreprise ?**<br>
Sa disponibilité dans Teams n’entraînera aucune modification de la couverture de l’audioconférence. La couverture actuelle de plus de 90 pays et plus de 400 villes sera maintenue dans les deux produits. Pour obtenir la liste complète, reportez-vous à la section [Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).



**Les fournisseurs d’audioconférence (ACP) tiers sont-ils pris en charge dans Teams **?<br>
Il n’est pas prévu que les fournisseurs d’audioconférence (ACP) tiers soient pris en charge dans Teams. Nous pensons que l’expérience d’audioconférence optimale pour les clients qui utilisent Teams et Skype Entreprise sera d'utiliser nos services d’audioconférence. Les clients qui ont besoin d’avoir recours à notre prise en charge des ACP dans les réunions Skype Entreprise peuvent continuer à utiliser leur client Skype Entreprise pour rejoindre les réunions Skype Entreprise. Les réunions planifiées dans Teams devront utiliser les services de conférence audio de Microsoft 365.

La prise en charge de l’intégration de fournisseurs d’audioconférence (ACP) tiers dans Skype Entreprise Online a été prolongée jusqu’au 31 juillet 2021, avec une prise en charge limitée des clients actifs restants afin d’autoriser une transition supplémentaire. Il s’agit d’une mise à jour de la chronologie ACP annoncée en avril 2018.



**Quel est le projet pour la prise en charge de l'interopérabilité vidéo dans les réunions Teams ?**<br>
[Les périphériques de salle de réunion](https://products.office.com/microsoft-teams/across-devices) sont essentiels à notre approche d'espace de travail moderne. [Des services d'interopérabilité vidéo cloud](https://docs.microsoft.com/microsoftteams/cloud-video-interop) pour prendre en charge les réunions Teams avec les systèmes VTC existants sont disponibles par l'intermédiaire de nos partenaires Pexip, Polycom et Blue Jeans.

**La dernière génération des systèmes Skype Room v2 prendra-t-elle en charge les réunions dans Teams ?**<br>
Nous avons rebaptisé les systèmes de salle Skype aux salles de Microsoft Teams, qui prennent entièrement en charge les réunions Microsoft Teams et simplifient la migration de Skype Entreprise vers Teams en autorisant simplement Teams sur l’appareil.

En plus de la possibilité pour les utilisateurs d’identifier les salles Microsoft Teams proches avec la détection de proximité, les réunions Teams peuvent être jointes à l’aide d’un simple clic, prise en charge de l’écran double, tableau blanc de Microsoft, et nous continuons d’ajouter des fonctionnalités innovantes comme une caméra de contenu avec la capture intelligente.


**La version v1 des systèmes Skype Room sera-t-elle mise à jour pour prendre en charge les réunions Teams ?**<br>
Les appareils Lync Room System (LRS) avec Skype Room System version 1 (SRS v1) ont atteint la fin du support le 9 octobre 2018. Cela signifie que Skype Room Systems v1 ne recevra plus de mises à jour de produit ou de correctifs. Les clients disposant d’appareils de salle Lync utilisant Skype Room v1 sont invités à mettre à niveau leurs appareils vers les salles Microsoft Teams. Pour plus d’informations, voir [Migrer les appareils Lync Room System (LRS) vers les salles Microsoft Teams](https://docs.microsoft.com/microsoftteams/rooms/lrs-migration).

**La diffusion de réunion Skype est-elle être supprimée en même temps que Skype Entreprise Online ?**<br>
Oui. [Événements en direct Teams](https://docs.microsoft.com/microsoftteams/teams-live-events/what-are-teams-live-events) est le successeur de diffusion de réunion Skype.


## <a name="management-capabilities"></a>Fonctionnalités de gestion

**Qu’est-ce que l’expérience de gestion de Teams ?**<br>
Comme la console d’administration de Skype Entreprise, l’[administration Microsoft Teams](https://admin.teams.microsoft.com/) au sein du Centre d’administration Microsoft 365 constitue un emplacement unique pour gérer les nouvelles expériences de Teams. Grâce à ce portail, nous pourrons créer des stratégies de présence personnalisée, de conversation, d'application, de réunion et vocale et les affecter aux utilisateurs de Teams.

## <a name="device-compatibility"></a>Compatibilité des périphériques

**Puis-je utiliser Teams sur Surface Hub ?**<br>
Les réunions Teams sont à présent disponibles sur Surface Hub avec une expérience d’appels et de réunions. Pour plus d’informations, voir [Déployer Microsoft Teams pour Surface Hub](https://docs.microsoft.com/microsoftteams/teams-surface-hub).

**Les téléphones IP tiers actuels (3PIP) seront-ils toujours compatibles avec Microsoft Teams ? Qu’en est-il des téléphones SIP tiers ?**<br>
La possibilité d’utiliser du matériel existant vous permet de réaliser des économies importantes lors de la transition vers un nouveau système téléphonique. Microsoft a étendu la prise en charge des téléphones Skype Entreprise (3PIP) au-delà de 2023. Vous pouvez continuer à utiliser vos téléphones Skype Antreprise existants à mesure que vous les parcourez. Par ailleurs, depuis la première moitié de 2021, Teams prendra en charge les fonctionnalités d’appels de base sur les téléphones SIP de Cisco, Yealink, Polycom, etc.

**Les téléphones Skype Entreprise Online certifiés fonctionnent-ils avec Teams ?**<br>
Pour toutes les questions relatives à la compatibilité des téléphones, consultez l'article [Téléphones Skype Entreprise Online certifiés et ce que cela signifie pour Teams](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/bc-p/125309).
