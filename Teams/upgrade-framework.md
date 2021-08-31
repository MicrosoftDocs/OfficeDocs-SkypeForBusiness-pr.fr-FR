---
title: À propos de l’infrastructure de mise à niveau Skype Entreprise à Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Utilisez une infrastructure de réussite éprouvée pour faciliter le parcours de mise à niveau de votre organisation, du plus Skype Entreprise au Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f18f35a061334e9a7e426614574afcc6eda42df9
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728473"
---
# <a name="about-the-upgrade-framework"></a>À propos du cadre de mise à niveau

Pour vous aider à réaliser les estimations dans le cadre de votre voyage de mise à niveau, nous avons utilisé une infrastructure éprouvée pour l’implémentation des changements. Comme illustré ci-dessous, chaque étape de la structure est mise en place à l’étape précédente et, pour des résultats optimaux, nous vous recommandons de suivre les étapes dans l’ordre.  

Commencez par réunir les parties prenantes concernées et définissez votre plan de mise à niveau (par exemple, étendue, objectifs et chronologie). Avec un plan en place, confirmez que votre environnement technique et vos utilisateurs finaux sont prêts à l’Teams. Ensuite, implémentez votre mise à niveau en plusieurs phases, en passant d’une mise à niveau pilote à l’échelle de l’organisation lorsque vous êtes prêt. Une fois que votre organisation est Teams, établissez un plan opérationnel qui surveille la qualité et accélère l’adoption par les utilisateurs.

![Illustration de l’infrastructure de voyage de mise à niveau.](media/upgrade-banner-main.png "Assurez-vous que votre projet est prêt pour réussir avec la bonne équipe de projet. Définissez l’étendue, les objectifs et la chronologie de votre projet. Confirmez la disponibilité des utilisateurs et techniques. Exécutez votre plan de déploiement. Maintenez la dynamique pour optimiser les résultats.")

Recherchez ce graphique d’infrastructure sur des pages liées pour identifier l’étape du processus de mise à niveau.

## <a name="sample-upgrade-timeline"></a>Exemple de chronologie de mise à niveau

Votre voyage de mise à niveau commence lorsque vous commencez à planifier le changement. En tirant parti du cadre de réussite comme directive, vous trouverez ci-dessous un exemple de chronologie qui vous fait passer de la phase de pré-mise à niveau où vous allez planifier et préparer votre mise à niveau, à la mise à niveau et à la phase opérationnelle après la mise à niveau, conçue pour soutenir et amplifier vos résultats. 

> [!NOTE]
> Nous comprenons que votre chemin d’accès à Teams peut impliquer de tirer parti de plusieurs [modes](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)et de mettre à niveau des groupes d’utilisateurs à différents moments, ce qui vous permettra de contrôler l’expérience de mise à niveau des utilisateurs tout en maintenant une bonne dynamique   avec Teams.  

Pour vous aider à montrer la manière dont votre voyage de mise à niveau peut être érossé, nous avons fourni un exemple de plan ci-dessous qui définit un voyage allant de Skype Entreprise Online au mode Teams uniquement. En outre, l’exemple de plan décrit une organisation qui a divisé ses utilisateurs en quatre groupes de mise à niveau, ou des clients. En utilisant ce modèle, personnalisez le plan afin d’inclure votre chemin spécifique vers la Teams, en incorporant les différents [modes](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)que vous utiliserez et le nombre de groupes de mise à niveau dans le segment de vos   utilisateurs. 

## <a name="pre-upgrade"></a>Avant la mise à niveau

**Préparez votre organisation pour l’Teams.** Pour garantir la réussite d’une mise à niveau Teams niveau, il est important d’allouer un temps suffisant pour la préparation. Non seulement votre organisation sera en mesure de commencer rapidement à réaliser la valeur de Teams, vous serez en mesure d’accélérer votre mise à niveau à partir de Skype Entreprise dès qu’Teams est prêt. Si vous avez déjà activé Teams en même temps que Skype Entreprise, utilisez ces activités de pré-mise à niveau comme point de contrôle pour vérifier la disponibilité de votre organisation avant de mettre à niveau les utilisateurs vers Teams. 

> [!TIP]
> Téléchargez le Kit de réussite [de](https://aka.ms/UpgradeSuccessKit)la mise à niveau pour les modèles de matériel de préparation des utilisateurs, tels que des communications et des enquêtes auprès des utilisateurs, en plus d’un exemple de plan de projet de mise à niveau et de   plan de test pilote. Les éléments disponibles dans le kit sont marqués par un astérisque (*) dans les listes ci-dessous.

### <a name="plan-create-your-upgrade-plan-to-help-ensure-your-organization-is-set-up-for-long-term-success"></a>Plan : créer votre plan de mise à niveau pour garantir la réussite de votre organisation à long terme

| Étape |&nbsp;| Résumé | Ressource |
|------|--|---------|----------|
| **1** | **Définir les parties prenantes** | Affectez des membres de l’équipe de projet responsables de la réussite de la mise à niveau. | [Demandez à vos parties prenantes](upgrade-enlist-stakeholders.md) |
| **2** | **Définir la vision et l’étendue de votre projet** | Concevez votre vision d’ensemble et l’étendue du projet en cours pour créer un plan pour votre voyage de mise à niveau. | [Project vision](upgrade-define-project-scope.md#project-vision) <br> <br>[Project étendue](upgrade-define-project-scope.md#project-scope) |
| **3** | **Définir vos objectifs de projet** | Définissez des objectifs ciblés qui vous permettent de mesurer l’avancement et de réussir le projet. | [Project objectifs](upgrade-define-project-scope.md#project-goals) |
| **4** | **Identifier les risques et les plans d’atténuation** | Établissez un plan d’atténuation pour vous assurer que vous pouvez rapidement remettre votre projet sur de bonnes rails en cas de problèmes. | [Risques et atténuation](upgrade-define-project-scope.md#risks-and-mitigation) |
| **5** | **Définir votre chronologie** | Définissez une chronologie et des jalons clés pour aider votre projet à rester en temps et en respectant le budget. | [Chronologie](upgrade-define-project-scope.md#timeline) <br><br> [Kit de réussite de la mise à niveau](https://aka.ms/UpgradeSuccessKit) |
| **6** | **Définir la stratégie de mise Skype Entreprise et de coexistence Teams et appropriée** | Map vous permet de suivre votre chemin d’accès le plus Skype Entreprise à Teams pour votre organisation. | [Comprendre Microsoft Teams coexistence et Skype Entreprise interopérabilité](teams-and-skypeforbusiness-coexistence-and-interoperability.md) <br><br>[Comprendre les Système téléphonique de connectivité PSTN](cloud-voice-landing-page.md)<br><br>  [Choix de votre parcours de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) |


### <a name="prepare-evaluate-your-organizations-readiness-for-teams"></a>Préparer : évaluer la disponibilité de votre organisation pour l’Teams

| Étape |&nbsp;  | Résumé | Ressource |
|------|--|---------|----------|
| **1** | **Évaluer votre environnement et effectuer une intégration Teams technique** | Assurez-vous que votre environnement est prêt pour Teams optimiser l’expérience utilisateur et faciliter votre mise à niveau au fil du temps. | [Évaluez votre environnement avant de mettre à niveau vers Teams.](upgrade-plan-journey-evaluate-environment.md)<br><br> [Préparer votre service pour la mise à niveau vers Teams](upgrade-prepare-environment-prepare-service.md) |
| **2** | **Optimiser le réseau pour Teams, en particulier pour les scénarios multimédias en temps réel** | Si vous déployez des réunions audio, vidéo ou vidéo, vous devez suivre ces étapes supplémentaires pour optimiser votre réseau pour cette fonctionnalité. | [Préparer votre réseau pour la mise à niveau vers Teams](prepare-network.md) |
| **3** | **Évaluer la préparation pour les changements d’organisation et définir des scénarios de travail d’équipe** | Comprenez votre base d’utilisateurs pour préparer la bonne valeur messagerie et niveau de formation afin de faciliter et d’accélérer l’adoption par les utilisateurs. | [Préparation pour les changements d’organisation](upgrade-org-change-readiness.md#organizational-change-readiness) |
| **4** | **Préparer un plan de disponibilité des utilisateurs pour définir la manière dont vous communiquerez, formerez et soutenirz les utilisateurs** | Personnalisez vos communications, votre formation et votre plan de support pour garantir une personnalisation optimale de la nouvelle technologie. | [Préparer un plan de préparation utilisateur](upgrade-user-readiness.md)<br><br>[Kit de réussite de la mise à niveau](https://aka.ms/UpgradeSuccessKit) |
| **5** | **Annoncer le lancement en attente d’Microsoft Teams** | Communiquez en avant-première pour aider les utilisateurs à se sentir inclus, à éviter toute confusion et à susciter de l’enthousiasme. | [Kit de réussite de la mise à niveau](https://aka.ms/UpgradeSuccessKit) |
| **6** | **Préparer votre personnel it pour l’Teams** | Confirmez que votre équipe technique et de support dispose de tout ce dont elle a besoin pour préparer et prendre en charge votre environnement technique pour Teams. | [Préparer votre personnel it pour l’Microsoft Teams](upgrade-prepare-it-pros.md) <br><br> [Kit de réussite de la mise à niveau](https://aka.ms/UpgradeSuccessKit) |

### <a name="pilot-run-a-pilot-to-confirm-that-your-organization-is-ready-and-inform-your-optimal-journey-to-teams"></a>Pilote : exécutez un pilote pour confirmer que votre organisation est prête et vous informer de votre expérience optimale pour Teams

| Étape | &nbsp; | Résumé | Ressource |
|------|--|---------|----------|
| **1** | **Plan de logistique du pilote** | Définissez une logistique pilote formelle pour valider la disponibilité de votre organisation en matière de mise à niveau ou de coexistence. | [Plan de logistique du pilote](pilot-essentials.md#1-outline-pilot-logistics) |
| **2** | **Sélectionnez vos participants pilotes et scénarios de test** | Identifiez les utilisateurs qui peuvent aider à valider les scénarios d’équipe et à Teams préparation. | [Sélectionnez vos participants pilotes et scénarios de test](pilot-essentials.md#2-select-your-pilot-participants-and-test-scenarios) |
| **3** | **Concevoir votre plan de test et votre enquête de commentaires** | Identifiez les tâches clairement définies que les participants doivent effectuer et un moyen pour eux de partager leurs commentaires. | [Concevoir votre plan de test et votre enquête de commentaires](pilot-essentials.md#3-design-your-test-plan-and-feedback-survey) |
| **4** | **Créer votre plan de communication pilote** | Expliquer aux participants pilotes ce qui se passe, quand, pourquoi et ce qu’on attend d’eux. | [Créer votre plan de communication](pilot-essentials.md#4-create-your-communications-plan)<br><br>[Kit de réussite de la mise à niveau](https://aka.ms/UpgradeSuccessKit) |
| **5** | **Conduire votre pilote** | Démarrez votre pilote, suivez la progression et itérer le cas nécessaire pour optimiser vos résultats pilotes. | [Conduire votre pilote](pilot-essentials.md#5-conduct-your-pilot) |
| **6** | **Évaluer les apprentissages et évaluer votre plan de avance** | Recueillez les commentaires des utilisateurs, les statistiques réseau et les tickets de support à des fins d’analyse par rapport à vos objectifs et déterminez votre plan de prise en charge. | [Évaluer les apprentissages et évaluer votre plan de avance](pilot-essentials.md#6-assess-learnings-and-evaluate-your-go-forward-plan)

### <a name="deploy-run-teams-in-coexistence-with-skype-for-business"></a>Déploiement : exécuter une Teams coexistence avec d’Skype Entreprise

| Étape |&nbsp;  | Résumé | Ressource |
|------|--|---------|----------|
| **1** | **Annoncer le lancement officiel de l’Teams** | Générez de l’enthousiasme et une dynamique en envoyant une annonce de lancement officiel lorsque Teams êtes prêt. | [Kit de réussite de la mise à niveau](https://aka.ms/UpgradeSuccessKit) |
| **2** | **Implémenter votre mise à niveau** | Les étapes à suivre dépendent de votre déploiement actuel de Skype Entreprise. | [Implémenter votre mise à niveau](upgrade-to-teams.md) |
| **3** | **Restez informé de la feuille de route Teams’équipe** | Surveillez la Teams feuille de route pour identifier le moment exact où votre organisation doit passer à l’Teams. | [Teams feuille de route](https://aka.ms/teamsroadmap) |
| **4** | **Envoyez des communications supplémentaires et engagez les champions Teams de l’enthousiasme et de l’adoption de Teams** | Encouragez l’adoption par les utilisateurs et favorisez l’Teams des communications et des champions continus. | [Microsoft 365 Programme Champions](https://aka.ms/O365Champions) |

## <a name="upgrade"></a>Mise à niveau 

**Effectuer le déplacement officiel vers Teams.** Lorsque vous mettre à niveau vos utilisateurs, vous les déplacez Teams mode uniquement. Teams devient leur application principale pour la conversation, les réunions, les appels et la collaboration, et l’accès à Skype Entreprise’application est désactivé. Bien que les aspects techniques de cette phase soient relativement simples, examinez l’effet de ce changement sur l’expérience utilisateur et laissez les utilisateurs le temps de faire officiellement passer leurs activités de Skype Entreprise à Teams. Pour réduire le nombre d’utilisateurs ayant des expériences différentes avec différents clients, essayez de limiter la fenêtre de mise à niveau de bout en bout à 45 jours environ.

### <a name="upgrade-implement-your-upgrade-from-skype-for-business-to-teams"></a>Mise à niveau : Implémenter la mise à niveau Skype Entreprise vers Teams

| Étape |&nbsp;  | Résumé | Ressource |
|------|--|---------|----------|
| **1** | **Vérifier que vous avez terminé les activités de pré-mise à niveau décrites ci-dessus** | Garantissez le succès de la mise à niveau en confirmant l’achèvement de toutes les activités de planification et de préparation. | Tout ce qui précède |
| **2** | **Démarrer des communications avec les utilisateurs de votre premier groupe de mise à niveau** | Informez les utilisateurs du démarrage des mises à niveau et gardez-les informés tout au long du processus. | [Préparer un plan de préparation utilisateur](upgrade-user-readiness.md) <br><br> [Kit de réussite de la mise à niveau](https://aka.ms/UpgradeSuccessKit) |
| **3** | **Activer le mode de coexistence Teams uniquement pour les utilisateurs de votre premier groupe de mise à niveau** | Suivez les étapes adaptées à votre environnement Skype Entreprise pour effectuer la migration des utilisateurs techniques. | [Mise à niveau de Skype Entreprise Online vers Teams](upgrade-to-Teams-execute-SkypeforBusinessOnline.md) <br><br>[Mettre à niveau Skype Entreprise locaux vers Teams](upgrade-to-Teams-execute-SkypeforBusinessHybridOnprem.md)
| **4** | **Répéter les activités de mise à niveau précédentes pour les groupes de mise à niveau restants sur un cycle en cours** | Continuez à conduire votre plan de communication en cours et à mettre à niveau les groupes d’utilisateurs en fonction de votre plan. | |
| **5** | **Envoyer des enquêtes de commentaires après la mise à niveau à tous les utilisateurs** | Utilisez une enquête de commentaires pour capturer des commentaires et des informations des utilisateurs. | [Kit de réussite de la mise à niveau](https://aka.ms/UpgradeSuccessKit) |

## <a name="post-upgrade"></a>Après la mise à niveau

**Optimisez la valeur métier avec Teams.** Une fois que votre organisation est entièrement mise à niveau vers Teams, prenez le temps d’évaluer votre réussite par rapport à vos objectifs et implémentez un plan pour continuer sur une bonne dynamique. 

### <a name="operate-measure-the-success-of-your-upgrade"></a>Utiliser : mesurer le succès de votre mise à niveau

| Étape | &nbsp; | Résumé | Ressource |
|------|--|---------|----------|
| **1** | **Évaluer le succès de votre mise à niveau initiale** | Évaluez la progression par rapport aux objectifs que vous avez fixés au cours de la phase de pré-mise à niveau. | [Project objectifs](upgrade-define-project-scope.md#project-goals) |
| **2** | **Implémenter un plan d’atténuation pour les objectifs non fixés** | Définissez des stratégies d’atténuation ou de correction des cours pour les objectifs non atteints. | [Project objectifs](upgrade-define-project-scope.md#project-goals) |
| **3** | **Surveiller l’état et la qualité du réseau** | Implémentez un plan de vérification et de surveillance de la qualité pour garantir une expérience utilisateur positive et réduire les appels vers votre support technique. | [Surveiller l’état et la qualité du réseau](continue-journey.md#monitor-for-network-health-and-quality) |
| **4** | **Stimuler la dynamique et l’adoption des utilisateurs** | Encouragez l’adoption par les utilisateurs et favorisez l’Teams’adoption continue. | [Stimuler la dynamique et l’adoption des utilisateurs](continue-journey.md#drive-user-momentum-and-adoption) |
| **5** | **Préparer la nouvelle fonctionnalité** | Réalisez une valeur maximale en établissant un cycle de changement pour les nouvelles innovations et les améliorations apportées aux produits. | [Préparer la nouvelle fonctionnalité](continue-journey.md#prepare-for-new-functionality)


> [!Note]
> Notre contenu de mise à niveau ne cesse d’évoluer. N’oubliez pas de consulter les dernières instructions et de consulter [le blog Teams’équipe.](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog) 

> [!Important]
> Skype Entreprise Online sera supprimé le 31 juillet 2021. Après cette date, il ne sera plus accessible ni pris en charge. Pour optimiser l’utilisation des avantages et vous assurer que votre organisation dispose du temps approprié pour implémenter votre mise à niveau, nous vous encourageons à commencer votre chemin vers Microsoft Teams aujourd’hui. N’oubliez pas qu’une mise à niveau réussie aligne les niveaux de préparation technique et utilisateur. N’oubliez pas de tirer parti des recommandations ci-après lorsque vous naviguez vers Microsoft Teams.