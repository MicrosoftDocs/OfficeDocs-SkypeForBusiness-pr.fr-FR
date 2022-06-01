---
title: Effectuer un pilote utilisateur pour évaluer et tester le fonctionnement de Microsoft Teams dans votre organisation
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Conseils pour démarrer un pilote Microsoft Teams afin d’explorer tout ce que Teams pouvez offrir à votre organisation, tout en continuant à utiliser Skype Entreprise
ms.localizationpriority: medium
ms.custom: Teams-upgrade-guidance
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae69bab918a9c8bd542e5ec70a95df7544677d8d
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823223"
---
# <a name="conduct-a-user-pilot"></a>Réaliser un pilote utilisateur

![Diagramme de parcours de mise à niveau, mettant en évidence le déploiement et l’implémentation.](media/upgrade-banner-deployment.png "Étapes du parcours de mise à niveau, en mettant l’accent sur la phase de déploiement et d’implémentation")

Cet article fait partie de la phase déploiement et implémentation de votre parcours de mise à niveau, et partage des insights pour l’exécution d’un pilote efficace. Avant de continuer, vérifiez que vous avez terminé les activités suivantes :

- [Inscription des parties prenantes de votre projet](upgrade-enlist-stakeholders.md)
- [Définition de l’étendue de votre projet](./upgrade-define-project-scope.md)
- [Compréhension de la coexistence et de l’interopérabilité des Skype Entreprise et des Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Choix de votre parcours de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Préparer votre environnement](./upgrade-prepare-environment.md)
- [Préparation de votre organisation](./upgrade-prepare-organization.md)

En déployant de nouvelles technologies, votre organisation peut réaliser des économies de coûts, la conformité à la sécurité, la satisfaction des employés et l’efficacité opérationnelle, mais elle peut également affecter la productivité et l’infrastructure organisationnelle de vos utilisateurs (votre réseau). Avant d’activer de nouvelles technologies au sein de votre organisation, effectuez un pilote utilisateur formel. Tout comme vous peindreiez un petit patch de couleur sur un mur avant de peindre toute la pièce, vous testeriez un déploiement à grande échelle à plus petite échelle en effectuant un pilote pour valider la préparation technique et utilisateur, identifier et atténuer les problèmes, et aider à garantir une implémentation réussie à l’échelle de l’organisation.

Pour obtenir les résultats les plus réalistes, le pilote doit impliquer des utilisateurs réels, imiter la façon dont ils communiquent et collaborent, et vérifier les expériences techniques et utilisateurs. Que votre organisation envisage d’exécuter Skype Entreprise et Teams côte à côte, de procéder à une mise à niveau vers Teams à l’avenir ou de déployer de nouvelles fonctionnalités telles qu’un appel ou une conférence, un pilote peut vous aider à identifier le bon chemin d’accès pour votre organisation. Parfois considéré comme la phase 1 d’un déploiement, le pilote idéal tire parti de la préparation que vous avez déjà commencée et implémente votre plan défini avec un groupe ciblé d’utilisateurs.

|&nbsp; | &nbsp;|
|---|---|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Comment utiliserez-vous un pilote pour informer l’orientation du projet ?</li></ul> |
| ![Icône montrant l’étape suivante.](media/audio_conferencing_image9.png)<br/>Étape suivante|<ul><li>Suivez les instructions ci-dessous pour concevoir et exécuter votre pilote formel.</li></ul>|

> [!Tip]
> Utilisez les exemples de [ressources pilotes](https://aka.ms/UpgradeSuccessKit) pour vous aider à concevoir vos communications, votre plan de test et votre enquête sur les commentaires.

## <a name="1-outline-pilot-logistics"></a>1. Structure de la logistique pilote

Un pilote réussi a défini des dates de début et de fin, ainsi que des [objectifs clairement définis](upgrade-define-project-scope.md#project-goals) pour mesurer la réussite. Ces objectifs doivent s’aligner sur l’étendue de votre projet plus large, comme vous l’avez documenté lorsque vous [avez défini l’étendue de votre projet](upgrade-define-project-scope.md), et seront utilisés pour indiquer votre chemin d’accès après la fin de votre projet pilote. Vous devez également vous assurer que vous avez inclus les parties prenantes appropriées pendant la durée du projet. Veillez à laisser suffisamment de temps pour exécuter le pilote et évaluer son impact : nous vous recommandons un minimum de 30 jours.

Démarrez petit et ajoutez à votre pilote le cas échéant, qu’il s’agisse d’ajouter des charges de travail ou des fonctionnalités ou des utilisateurs supplémentaires, en prenant le temps d’évaluer les résultats et d’ajuster votre pilote au fur et à mesure de l’itération. Vous pouvez même choisir d’exécuter les pilotes suivants, car de nouvelles fonctionnalités Teams sont publiées conformément à la feuille de route.

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a>2. Sélectionnez vos participants pilotes et les scénarios de test

L'une des plus importantes tâches d'une planification pilote consiste à sélectionner des participants de manière judicieuse. N’oubliez pas que Teams est optimisée pour le travail d’équipe. Veillez donc à sélectionner les participants pilotes non seulement en fonction de rôles ou de personnages, mais également en fonction de leur projet et de leur travail entre équipes. Un excellent point de départ consiste à demander à vos parties prenantes et à vos responsables de service des projets réels que vous pouvez valider dans Teams. Un exemple de projet basé sur des rôles peut être d’utiliser Teams avec votre organisation commerciale pour vous assurer que les représentants de champ peuvent facilement accéder aux ressources dont ils ont besoin et partager des insights avec d’autres membres du champ. Un exemple de travail basé sur un projet peut être la coordination d’un événement de lancement de produit avec les équipes de marketing, de formation, de relations publiques et de planification d’événements. Quels que soient les scénarios que vous sélectionnez, le pilote doit s’étendre aux personnes clés dans l’informatique, la formation et votre support technique, afin que vous puissiez valider complètement la solution tout en optimisant pleinement les ressources de gestion de projet.

> [!Tip]
> Lorsque vous sélectionnez vos participants de groupe pilote Teams, veillez à inclure les principaux utilisateurs de Skype Entreprise. Vérifiez auprès de ces utilisateurs comment ils utilisent Skype Entreprise aujourd’hui, puis créez un plan de test pour vérifier que Teams pouvez répondre à leurs besoins actuels.

## <a name="3-design-your-test-plan-and-feedback-survey"></a>3. Concevoir votre plan de test et votre enquête de commentaires

Pour une expérience pilote réussie, donnez à vos participants des tâches clairement définies à effectuer, ainsi qu’un moyen pour eux de partager leurs commentaires. Regroupez des tâches pour offrir des scénarios réels à vos utilisateurs, ce qui démontre la pertinence de leurs activités quotidiennes. Laissez les cas d’usage que vous avez définis dans [Évaluer la préparation aux changements organisationnels](./upgrade-org-change-readiness.md) guider votre plan de test.

Votre organisation peut choisir de piloter toutes les fonctionnalités à la fois ou d’utiliser une approche progressive , par exemple, la collaboration pilote d’abord, puis les réunions, puis la conversation et l’appel. Vérifiez que vous disposez d’un canal de commentaires ouvert pour suivre la progression et mesurer les résultats. Utilisez une enquête prédéfinie comme moyen simple de capturer et d’évaluer les résultats du pilote; la conception de l’enquête doit être basée sur les scénarios et les fonctionnalités de votre plan de test.

## <a name="4-create-your-communications-plan"></a>4. Créer votre plan de communication

Il est essentiel pour le succès de votre pilote d’informer les participants pilotes sur ce qui se passe, quand et pourquoi, et ce qu’on attend d’eux. Pour susciter l’enthousiasme et la participation maximale, veillez à inclure la messagerie de valeur utilisateur en plus des liens vers la formation et le support où les utilisateurs peuvent obtenir des informations supplémentaires à mesure qu’ils progressent dans le pilote. Voici quelques exemples de ressources pour vous aider à démarrer avec votre plan de communication pilote :

- [Ressources pilotes](https://aka.ms/UpgradeSuccessKit), notamment des modèles de courrier électronique et des exemples de questions sur l’enquête sur les commentaires
- [Basculez vers Teams à partir de Skype Entreprise](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964), un guide de démarrage rapide conçu pour aider Skype Entreprise utilisateurs à bien démarrer avec Teams

## <a name="5-conduct-your-pilot"></a>5. Conduire votre pilote

Avec toute la logistique en place, vous êtes maintenant prêt à commencer votre pilote. La conduite de votre projet pilote inclut la communication avec vos utilisateurs, la surveillance de votre réseau et de votre utilisation pour garantir que les performances de votre réseau et la qualité des appels restent saines, la collecte des commentaires des participants et l’examen des tickets de support technique pour les questions relatives à Teams.

### <a name="tips-for-pilot-success"></a>Astuces pour la réussite du pilote

Les conseils suivants peuvent vous aider à garantir la réussite de votre pilote :

- Avant de commencer votre pilote, vérifiez que tous les participants pilotes sont activés pour le [mode de coexistence] approprié.
- (https://aka.ms/SkypeToTeams-SetCoexistence) que vous souhaitez valider.
- Chaque semaine, tout au long de votre projet pilote, rencontrez les parties prenantes de votre projet pour passer en revue les commentaires des utilisateurs, les données d’utilisation, les données réseau et les tickets de support technique pour vous assurer que votre pilote fonctionne correctement. Effectuez les ajustements nécessaires.

### <a name="suggested-timeline"></a>Chronologie suggérée

Voici une suggestion de calendrier pour un projet pilote de 30 jours :

- Une semaine avant le lancement du pilote : envoyer une communication initiale aux utilisateurs pilotes.
- Jour 1 : Envoyer une communication de lancement aux utilisateurs pilotes.
- Jour 7 : Tenir la première réunion hebdomadaire de point de contrôle de l’équipe de projet.
- Jour 14 : Envoyez une communication à mi-temps à vos utilisateurs pilotes, organisez une réunion hebdomadaire de point de contrôle de l’équipe de projet.
- Jour 21 : Tenir une réunion hebdomadaire de point de contrôle de l’équipe de projet.
- Jour 30 : Envoyer la communication finale à vos utilisateurs pilotes.
- Jours 31 à 45 : Évaluez les résultats du pilote et planifiez les étapes suivantes.

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a>6. Évaluer les apprentissages et évaluer votre plan d’avenir

Une fois votre projet pilote terminé, il est temps de recueillir tous les sondages de commentaires, les statistiques réseau finales et les tickets de support pour l’analyse de vos objectifs et de déterminer si vous allez implémenter votre plan d’aller de l’avant. Vous pouvez constater que votre organisation est prête pour un déploiement à grande échelle, ou que vous souhaitez étendre votre projet pilote à davantage d’utilisateurs, ou que vous souhaitez revoir le pilote ultérieurement une fois que les problèmes que vous avez identifiés ont été atténués. N’oubliez pas que votre pilote est un excellent moyen de prédire les résultats techniques et utilisateur dans un environnement _contrôlé_ ; être réfléchi à l’avance trop rapidement.

Si vos résultats indiquent :

- **Vos objectifs pilotes (par exemple, la satisfaction des utilisateurs et la qualité du réseau) ont été atteints**. Vous devez être prêt à passer à la phase suivante de votre déploiement. Selon les objectifs de votre projet, il peut s’agir de l’un des éléments suivants :
  - Extension du pilote à d’autres participants
  - [Activation de Teams en même temps que Skype Entreprise (mode **Îles**) pour une partie ou l’ensemble de votre organisation](./setting-your-coexistence-and-upgrade-settings.md)
  - [Mise à niveau des utilisateurs de Skype Entreprise vers Teams (**mode Teams uniquement**) pour une partie ou l’ensemble de votre organisation](./setting-your-coexistence-and-upgrade-settings.md)
- **Votre pilote n’a pas atteint les résultats souhaités (par exemple, la satisfaction des utilisateurs et la qualité du réseau),** prenez le temps d’apporter les ajustements appropriés à votre plan et de revoir votre projet pilote.

> [!Tip]
> Faites appel à vos participants pilotes en tant que pairs champions pour aider à évangéliser et à intégrer de nouveaux utilisateurs à Teams. Les pairs champions peuvent facilement communiquer avec d’autres utilisateurs, partager leurs propres expériences et apprentissages, et offrir un support et des conseils à leurs collègues. Apprenez-en davantage sur les [champions](
https://adoption.microsoft.com/become-a-champion/) et sur la façon dont vous pouvez les utiliser dans votre propre déploiement.