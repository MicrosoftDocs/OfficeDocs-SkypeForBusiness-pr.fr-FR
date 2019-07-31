---
title: Mise à niveau de Microsoft teams Parcours
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Suivez ces instructions si vous vous trouvez dans une grande entreprise ou si vous avez énormément personnalisé votre déploiement Skype entreprise.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 68c2f0f74d1f5f2ba13518c8f56afc1244480a14
ms.sourcegitcommit: 195a4e1bbab46034408a22d636874c10f797945a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/30/2019
ms.locfileid: "35934541"
---
# <a name="upgrade-pro"></a>Mise à niveau Pro

Conçu pour des organisations de plus grande taille ou des déploiements complexes de Skype entreprise (par exemple, des déploiements vocaux hybrides ou Cloud), mettre à niveau des comptes pour une mise à niveau plus longue et de nombreux scénarios de mise à niveau, y compris Microsoft Teams avec Skype entreprise tant que teams n’est pas disponible pour votre organisation.

Segmenté en trois phases, la mise à niveau vers:

|**[Avant la mise à niveau](#pre-upgrade)** |**[Mise à niveau](#upgrade)** |**[Après la mise à niveau](#post-upgrade)** |
|---|---|---|
|Exploitez la valeur de teams<ul><li>Préparez votre environnement</li><li>Adoption d’équipes pour la collaboration, les réunions et/ou les appels</li><li>Planifier la mise à niveau de Skype entreprise vers équipes au fil du temps</li></ul> |Migration des utilisateurs de Skype entreprise<ul><li>Informer et prêter vos utilisateurs</li><li>Déplacer les utilisateurs en mode équipes uniquement</li><li>Suivre l’avancement de l’utilisation par rapport aux objectifs</li></ul> | Amplifier votre retour sur investissement <ul><li>Surveiller l’État et la qualité du réseau</li><li>Maintien de l’enthousiasme pour les utilisateurs</li><li>Plan pour les innovations en cours en équipe</li></ul>|

> [!NOTE]
> Nous comprenons que votre déplacement vers teams peut impliquer l’utilisation de plusieurs [modes](https://aka.ms/skypetoteams-coexist) et la mise à niveau de groupes d’utilisateurs à différents moments, ce qui vous permet de contrôler l’utilisation de la mise à niveau utilisateur tout en préservant la fluidité des équipes. <br><br>
Pour vous aider à montrer le déroulement du déroulement de votre mise à niveau, nous avons présenté ci-dessous un exemple de plan qui définit le passage de Skype entreprise au mode **îles** uniquement. En outre, l’exemple de plan décrit une organisation qui a divisé ses utilisateurs en quatre groupes de mise à niveau __ ou des cohortes. À l’aide de ce modèle en tant que modèle, personnalisez le plan pour inclure votre voyage spécifique dans Teams, en incluant les différents [modes](https://aka.ms/skypetoteams-coexist) que vous utiliserez et le nombre de groupes de mise à niveau dans lesquels vous segmenterez vos utilisateurs.

## <a name="pre-upgrade"></a>Avant la mise à niveau

**Préparez votre organisation pour Teams.** Pour garantir la réussite de la mise à niveau vers Teams, il est important d’allouer un délai approprié pour la préparation. Par le biais de votre organisation, votre organisation pourra à tout moment commencer à créer rapidement des équipes, vous serez en mesure d’accélérer la mise à niveau de Skype entreprise dès que teams sera prêt pour vous. Surveiller la [documentation](https://aka.ms/O365Roadmap) pour les améliorations apportées aux équipes; Cela vous aidera à identifier le planning de mise à niveau approprié pour votre organisation. Si vous avez déjà activé teams en même temps que Skype entreprise, utilisez ces activités de pré-mise à niveau pour vérifier la préparation de votre organisation avant de mettre à niveau les utilisateurs vers Teams.

> [!Tip]
> Téléchargez le [Kit de réussite de mise à niveau](https://aka.ms/UpgradeSuccessKit) pour les documents de préparation des utilisateurs de modèles tels que les communications et les enquêtes utilisateur, en plus d’un exemple de plan de projet de mise à niveau et d’un plan de test pilote. Les éléments disponibles dans le kit sont marqués d’un astérisque (\*) dans les listes ci-dessous.

### <a name="days-1ndash7-create-your-upgrade-plan-to-help-ensure-your-organization-is-set-up-for-long-term-success"></a>Jours 1&ndash;7: création de votre plan de mise à niveau pour vous assurer que votre organisation est configurée pour le succès à long terme

|Étape||Résumé |Ressources |
|---|---|---|---|
|**1** |**Définir les parties prenantes** |Tenez compte de l’objectif de votre projet et identifiez les parties prenantes en matière de préparation technique et de préparation des utilisateurs afin d’améliorer la responsabilité et la réussite. |[Inscrire les parties prenantes](upgrade-enlist-stakeholders.md) |
|**2** |**Définir votre vision de projet** |Votre vision est l’état de «grande image» ou l’état de fin de l’éventualité qui répondra à la question «pourquoi est-ce que nous effectuons ce projet?» Une vision idéale répond aux axes stratégiques de votre organisation et à la valeur utilisateur. |[Vision du projet](upgrade-define-project-scope.md#project-vision) |
|**3** |**Définition de l’étendue de votre projet** |Votre vision peut seulement être réalisée au fil du temps, par différentes phases. L’étendue du projet définit le focus de votre projet à ce stade et vous permet de garder le focus sur les tâches actuelles de votre équipe de projet, ce qui vous permet de vous familiariser avec votre vision à long terme. |[Étendue du projet](upgrade-define-project-scope.md#project-scope) |
|**4** |**Définir les objectifs du projet** |Vos buts définissent le résultat que vous souhaitez et vous permettent de mesurer le succès du projet. Vous pouvez définir les objectifs en tant qu’objectifs et résultats clés (OKRs), et les mesures de réussite du projet peuvent être définies en tant qu’indicateurs de réussite clés (KSIs). Il est essentiel que vous obteniez une participation complète des parties prenantes de Project en définissant OKRs et KSIs, afin de vous assurer qu’elles ne se trouvent pas et qu’elles alignent ces mesures de réussite aux tâches de projet définies. Les objectifs doivent inclure une combinaison de réussite ciblée par l’utilisateur et par le biais du support technique. |[Objectifs du projet](upgrade-define-project-scope.md#project-goals) |
|**5** |**Identifier les risques et les plans d’atténuation** |Il est important de procéder de manière proactive aux risques potentiels et de définir un plan d’atténuation pour la résolution des problèmes pouvant se produire, afin que votre projet puisse continuer à atteindre vos objectifs. Un registre de risques est un excellent outil pour suivre les risques d’un projet, ainsi que le niveau de probabilité qu’il s’agisse d’un impact potentiel et de la capture de votre plan d’atténuation. Le tableau suivant montre un exemple de registre de risques. |[Risques et réduction](upgrade-define-project-scope.md#risks-and-mitigation) |
|**6** |**Définir votre chronologie** |Définissez une chronologie pour les jalons clés (par exemple, en permettant aux équipes de se conformer à Skype entreprise pour tous les utilisateurs ou à la mise à niveau par phases des utilisateurs) en plus de la date d’achèvement. Une chronologie définie permet à votre équipe de projet de se connecter à un état de fin cohérent et de vérifier que le bon déroulement de votre projet est maintenu. Prenez en considération une chronologie qui n’est pas trop accélérée (où les tâches peuvent être répertoriées). |['](upgrade-define-project-scope.md#timeline)<br><br>[Kit de réussite de la mise à niveau](https://aka.ms/UpgradeSuccessKit)|
|**7** |**Définir la stratégie de mise à niveau et de coexistence de Skype entreprise et des équipes** |En tant que client Skype entreprise existant, la transition complète vers teams peut prendre un certain temps. Néanmoins, vous pouvez commencer à utiliser teams dès aujourd’hui en permettant à vos utilisateurs d’utiliser teams en même temps que Skype entreprise. Étant donné qu’il existe d’autres fonctionnalités qui se chevauchent entre les deux applications, nous vous conseillons de passer en revue les modes de coexistence et de mise à niveau disponibles pour vous aider à déterminer le chemin approprié pour votre organisation. Pour une meilleure connaissance, vous pouvez piloter votre stratégie de coexistence prévue avant de procéder à un déploiement large pour tous les utilisateurs. |[Comprendre Microsoft teams et la coexistence et l’interopérabilité de Skype entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)<br><br>[Choix de votre parcours de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)|

### <a name="days-8ndash15-evaluate-your-organizations-readiness-for-teams"></a>Jours 8&ndash;15: Évaluez la disponibilité de votre organisation pour teams

|Étape | |Résumé |Ressources |
|---|---|---|---|
|**1** |**Évaluez votre environnement existant pour identifier les risques et les exigences.** |L’évaluation de votre environnement vous permet d’identifier les risques et les exigences qui influenceront votre déploiement global. En identifiant ces éléments de manière proactive, vous pouvez ajuster votre planification pour garantir le succès. |[Évaluez votre environnement avant de procéder à la mise à niveau vers teams](upgrade-plan-journey-evaluate-environment.md) |
|**2** |**Office 365 et Microsoft teams-intégration technique** |L’utilisation des listes de vérification de l’intégration existante pour identifier les tâches et les activités afin de compléter la compatibilité technique des fonctionnalités de collaboration et de voix avec Teams. |[Préparer votre service pour la mise à niveau vers teams](upgrade-prepare-environment-prepare-service.md) |
|**3** |**Optimiser le réseau pour les équipes, en particulier pour les scénarios multimédias en temps réel** |Si vous déployez des fichiers audio, vidéo ou de réunion, vous pouvez effectuer des étapes supplémentaires pour optimiser votre réseau pour cette fonctionnalité. Teams utilise une technologie audio et vidéo (codecs) qui peut&mdash;s’adapter à et,&mdash;par conséquent, fonctionner mieux dans la plupart des conditions de réseau. Pour garantir des performances optimales et cohérentes, vous devez préparer votre réseau pour Teams. |[Préparer votre réseau pour la mise à niveau vers teams](upgrade-prepare-environment-prepare-network.md) |
|**4** |**Évaluer la préparation au changement de l’organisation** |Pour tirer parti de la valeur des équipes, les utilisateurs doivent réellement les utiliser. Le simple fait d’activer Teams ne garantit pas que vous atteignez votre objectif. Les utilisateurs ont différentes circonstances d’utilisation et différents styles d’apprentissage, et ils s’adaptent à de nouvelles technologies à différentes vitesses. Le fonctionnement de votre base d’utilisateurs vous permet de préparer le niveau d’études approprié pour faciliter et accélérer l’adoption des utilisateurs. |[Disponibilité du changement d’organisation](upgrade-org-change-readiness.md#organizational-change-readiness) |
|**5** |**Préparer un plan de vérification de l’utilisateur afin de définir la manière dont vous allez communiquer, former et prendre en charge les utilisateurs** |Pour garantir une receptiveness optimale à la nouvelle technologie, utilisez une combinaison de messages à grande portée (intégration de la messagerie de vision/valeur et des cas d’utilisation universelles) et de la messagerie, de la formation et de la prise en charge adaptées aux personnages et aux cohortes que vous avez définies et également à votre laggards, le cas échéant. Ce plan personnalisé contribue à faciliter l’adoption par les utilisateurs, en permettant aux utilisateurs de plus en plus rapidement en relation avec les équipes, tout en montrant que vous comprenez leurs besoins. Vous pouvez vous en servir pour vous piloter, à l’intégration et à la mise à niveau vers Teams. |[Préparer un plan de préparation utilisateur](upgrade-user-readiness.md)<br><br>[Kit de réussite de la mise à niveau](https://aka.ms/UpgradeSuccessKit)<br><br>[Vidéo de formation teams](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7?wt.mc_id=otc_home)<br><br>[Basculer vers Teams à partir de Skype Entreprise](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964) |
|**6** |**Annoncer le lancement en attente de Microsoft teams** |Communiquer avec vos utilisateurs à l’avance permet aux utilisateurs de se sentir à l’esprit, de réduire la confusion et de susciter l’intérêt de Microsoft Teams, ce qui facilite la mise à niveau de Skype entreprise dans le temps. | [Kit de réussite de la mise à niveau](https://aka.ms/UpgradeSuccessKit) |
|**7** |**Préparer votre équipe informatique pour teams** |Vos administrateurs de clients d’Office 365, les prospectus techniques et l’assistance technique sont responsables pour une interface utilisateur de grande qualité. Cela implique de vérifier que votre réseau est prêt pour la prise en charge des équipes, de configurer teams pour vos utilisateurs et de pouvoir résoudre efficacement les problèmes qui peuvent survenir. |[Préparer votre équipe informatique pour Microsoft teams](https://docs.microsoft.com/microsoftteams/upgrade-prepare-it-pros)<br><br>[Kit de réussite de la mise à niveau](https://aka.ms/UpgradeSuccessKit) |

### <a name="days-16ndash60-run-a-pilot-to-confirm-that-your-organization-is-ready-and-inform-your-optimal-journey-to-teams"></a>Jours 16&ndash;60: exécution d’un pilote pour vérifier que votre organisation est prête et informer votre voyage d’équipe

|Étape | |Résumé |Ressources |
|---|---|---|---|
|**1** |**Plan de logistique du pilote** |Un pilote réussi a défini des dates de début et de fin, ainsi que des objectifs clairement définis pour la mesure du succès. Ces objectifs doivent s’aligner sur l’étendue de votre projet plus large et être utilisés pour informer votre chemin d’accès après le transfert de votre pilote. |[Plan de logistique du pilote](pilot-essentials.md#1-outline-pilot-logistics) |
|**2** |**Sélectionner les participants au programme pilote et les scénarios de test** |Sélectionner les participants au programme pilote non seulement en fonction des rôles ou des personnes, mais en fonction de leur projet et de leur travail entre les équipes. Le pilote doit s’étendre aux personnes qui s’y trouvent, à la formation et à votre support technique, afin que vous puissiez valider pleinement la solution tout en optimisant pleinement les ressources de gestion de projet, vous devez inclure les meilleurs utilisateurs de Skype entreprise. |[Sélectionner les participants au programme pilote et les scénarios de test](pilot-essentials.md#2-select-your-pilot-participants-and-test-scenarios) |
|**3** |**Concevoir votre plan de test et votre enquête de commentaires** |Identifiez les tâches clairement définies devant être effectuées par les participants et de façon à ce qu’ils puissent partager leurs commentaires. Regroupez les tâches pour permettre aux utilisateurs de faire des scénarios réalistes, en présentant la pertinence de leurs activités quotidiennes. |[Concevoir votre plan de test et votre enquête de commentaires](pilot-essentials.md#3-design-your-test-plan-and-feedback-survey) |
|**4** |**Créer votre plan de communication pilote** |Informez les participants au programme pilote sur ce qui se passe et pourquoi et ce qui est attendu. Pour favoriser votre enthousiasme et votre participation au maximum, veillez à inclure la messagerie de valeurs utilisateur en plus des liens vers des formations et de l’assistance pour lesquelles les utilisateurs peuvent obtenir des informations supplémentaires à mesure qu’ils avancent dans le cadre du projet pilote. |[Créer votre plan de communication](pilot-essentials.md#4-create-your-communications-plan)<br><br>[Kit de réussite de la mise à niveau](https://aka.ms/UpgradeSuccessKit) |
|**5** |**Conduire votre pilote** |La conduite de votre pilote implique de communiquer avec vos utilisateurs, de surveiller votre réseau et de votre utilisation pour garantir les performances de votre réseau et la qualité des appels, recueillir les commentaires des participants et consulter les tickets d’assistance pour les questions relatives à Associations. |[Conduire votre pilote](pilot-essentials.md#5-conduct-your-pilot) |
|**6** |**Évaluez les connaissances et évaluez votre plan de transfert** |Rassemblez tous les examens de commentaires, les statistiques finales sur le réseau et les tickets de support pour analyse par rapport à vos objectifs et déterminez si vous allez mettre en œuvre votre plan de transfert. |[Évaluez les connaissances et évaluez votre plan de transfert](pilot-essentials.md#6-assess-learnings-and-evaluate-your-go-forward-plan) |

### <a name="day-60-until-upgrade-deploy-teams-in-coexistence-with-skype-for-business"></a>Jour 60 jusqu’à la mise à niveau: déploiement d’équipes pour coexistence avec Skype entreprise

|Étape | |Résumé |Ressources |
|---|---|---|---|
|**1** |**Annoncer le lancement officiel d’équipes** |Communiquez avec vos utilisateurs à propos du démarrage de votre organisation d’équipes pour garantir la sensibilisation et la valeur foncière et profiter des avantages pour les utilisateurs. Envisagez de multiples formes de communication incluant un événement de lancement et la messagerie électronique. |[Kit de réussite de la mise à niveau](https://aka.ms/UpgradeSuccessKit) |
|**2** |**Activez le mode de coexistence approprié pour vos utilisateurs.** |Suivez les étapes permettant de définir le ou les modes de coexistence appropriés pour votre organisation. |[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md) |
|**3** |**Restez informé des formations d’équipes** |Suivez la procédure et évaluez en permanence le bon déroulement de l’organisation afin d’identifier le temps que votre organisation est approprié pour déplacer vers Teams. |[Plan d’équipes](https://aka.ms/teamsroadmap) |
|**4** |**Envoyer des communications supplémentaires et impliquer des champions en équipe pour renforcer** l’enthousiasme et l’adoption des équipes |Encourager les utilisateurs à adopter une équipe de communications et des champions en toute facilité. |[Programme Microsoft 365 champions](https://aka.ms/O365Champions) |

## <a name="upgrade"></a>Mise à niveau

**Faire passer le fonctionnaire aux équipes.** Lorsque vous effectuez une mise à niveau de vos utilisateurs, vous les déplacez dans le mode de coexistence **équipes** . Teams devient son application principale pour la discussion, les réunions, les appels et la collaboration, et l’accès à l’application Skype entreprise est désactivé. Même si les aspects techniques de cette phase sont assez simples, envisagez l’impact qu’il peut avoir sur l’action de l’utilisateur et de permettre aux utilisateurs de transférer officiellement leurs activités de Skype entreprise à Teams. Pour réduire le nombre d’expériences utilisateur différentes avec différents clients, essayez de limiter la fenêtre de mise à niveau de bout en bout à 45 jours.

### <a name="days-1ndash45-implement-your-upgrade-from-skype-for-business-to-teams"></a>Jours 1&ndash;45: mettre en œuvre la mise à niveau de Skype entreprise vers teams

|Étape | |Résumé |Ressources |
|---|---|---|---|
|**1** |**Vérifiez que vous avez terminé les activités de pré-mise à niveau décrites ci-dessus.** |Contribuez à garantir la réussite de votre mise à niveau en confirmant la fin de toutes les activités de planification et de préparation. |Toutes les réponses précédentes |
|**2** |**Lancer des communications aux utilisateurs de votre premier groupe de mise à niveau** |Lancez l’exécution de votre plan de communication avant et après la mise à niveau afin de promouvoir votre sensibilisation, de définir les attentes et de partager l’avantage de teams avec les utilisateurs avant la mise à niveau. |[Préparer un plan de préparation utilisateur](upgrade-user-readiness.md)<br><br>[Kit de réussite de la mise à niveau](https://aka.ms/UpgradeSuccessKit)<br><br>[Vidéo de formation teams](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7?wt.mc_id=otc_home)<br><br>[Basculer vers Teams à partir de Skype Entreprise](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964) |
|**3** |**Activez le mode de coexistence aux équipes uniquement pour les utilisateurs de votre premier groupe de mise à niveau** |Suivez les étapes adaptées à votre environnement Skype entreprise pour effectuer la migration des utilisateurs techniques. |[Mise à niveau de Skype Entreprise Online vers Teams](upgrade-to-teams-execute-skypeforbusinessonline.md)<br><br>[Mise à niveau d’un déploiement hybride Skype entreprise vers teams](upgrade-to-teams-execute-skypeforbusinesshybrid.md)<br><br>[Effectuer une mise à niveau d’un déploiement local de Skype entreprise vers teams](upgrade-to-teams-execute-skypeforbusinessonpremises.md) |
|**4** |**Répéter les activités de mise à niveau précédentes pour les groupes de mise à niveau restants sur un cycle roulant** |Continuez à piloter votre plan de communication en continu et à mettre à niveau les groupes d’utilisateurs selon votre plan. | |
|**5** |**Envoyer des enquêtes de commentaires après la mise à niveau à tous les utilisateurs** |Tirez parti d’une enquête de commentaires pour capturer des commentaires et des informations auprès des utilisateurs. |[Kit de réussite de la mise à niveau](https://aka.ms/UpgradeSuccessKit) |

## <a name="post-upgrade"></a>Après la mise à niveau

**Optimisez votre valeur commerciale avec Teams.** Une fois votre organisation entièrement mise à niveau vers Teams, prenez le temps d’évaluer votre réussite par rapport à vos objectifs et de mettre en place un plan de reprise.

### <a name="days-1ndash14-measure-the-success-of-your-upgrade"></a>Jours 1&ndash;14: évaluer la réussite de votre mise à niveau

|Étape | |Résumé |Ressources |
|---|---|---|---|
|**1** |**Évaluer la réussite de votre mise à niveau initiale** |Évaluez la progression par rapport aux objectifs que vous avez établis lors de la phase de pré-mise à niveau. |[Objectifs du projet](upgrade-define-project-scope.md#project-goals) |
|**2** |**Implémentez un plan d’atténuation pour n’importe quel objectif qui n’est pas sur le suivi.** |Définissez des stratégies de correction ou de correction de cours pour les objectifs qui ne sont pas satisfaits. |[Objectifs du projet](upgrade-define-project-scope.md#project-goals) |

### <a name="ongoing"></a>Façon

|Étape | |Résumé |Ressources |
|---|---|---|---|
|**1** |**Surveiller l’intégrité et la qualité du réseau** |La mise en œuvre d’un plan de surveillance et de réduction de l’intégrité du réseau contribue à garantir une utilisation positive des utilisateurs en plus de réduire les appels vers votre support technique. |[Surveiller l’intégrité et la qualité du réseau](continue-journey.md#monitor-for-network-health-and-quality) |
|**2** |**Libérer de l’élan et de l’adoption des utilisateurs** |Encourager les utilisateurs à adopter des équipes et à en assurer l’enthousiasme, |[Libérer de l’élan et de l’adoption des utilisateurs](continue-journey.md#drive-user-momentum-and-adoption) |
|**3** |**Préparer une nouvelle fonctionnalité** |Le cycle de modification de votre organisation vous permet de vous assurer que vous êtes prêt à gérer les améliorations de la collaboration en continu et à tirer le meilleur parti. |[Préparer une nouvelle fonctionnalité](continue-journey.md#prepare-for-new-functionality) |

> [!Note]
> Notre contenu de mise à niveau est en perpétuelle évolution. Assurez-vous de consulter les informations les plus récentes et lisez le [blog teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog).

> [!Important]
> Skype entreprise Online sera supprimé le 31 juillet 2021, mais il ne sera plus accessible ou pris en charge. Pour optimiser la réalisation des avantages et garantir que votre organisation dispose du moment approprié pour mettre en œuvre la mise à niveau, nous vous encourageons à commencer votre trajet vers Microsoft teams dès aujourd’hui. Rappelez-vous qu’une mise à niveau réussie aligne les techniques et les capacités de l’utilisateur, veillez donc à tirer parti de ces instructions lorsque vous naviguez dans votre voyage vers Microsoft Teams.
