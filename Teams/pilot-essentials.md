---
title: Conduire un pilote d’utilisateur pour évaluer et tester le fonctionnement de Microsoft Teams dans votre organisation
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Instructions pour démarrer un pilote Microsoft Teams afin d’explorer tout ce que Teams peut offrir à votre organisation, tandis que vous continuez à utiliser Skype Entreprise
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
ms.openlocfilehash: 22ee8e22f7954814aa98b43d1eac250ac38b17cd
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014608"
---
# <a name="conduct-a-user-pilot"></a>Réaliser un pilote utilisateur

![Diagramme de voyage de mise à niveau, mettant en évidence le déploiement et l’implémentation.](media/upgrade-banner-deployment.png "Étapes du parcours de mise à niveau, avec l’accent sur l’étape déploiement et implémentation")

Cet article fait partie de la phase déploiement et implémentation de votre parcours de mise à niveau et partage des informations pour la mise en place d’un pilote efficace. Avant de poursuivre, confirmez que vous avez effectué les activités suivantes :

- [Demandez aux parties prenantes de votre projet](upgrade-enlist-stakeholders.md)
- [Étendue définie de votre projet](./upgrade-define-project-scope.md)
- [Coexistence et interopérabilité comprises de Skype Entreprise et Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Nous avons choisi votre chemin de mise à niveau](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Préparé votre environnement](./upgrade-prepare-environment.md)
- [Préparé votre organisation](./upgrade-prepare-organization.md)

En déployant de nouvelles technologies, votre organisation peut réaliser des économies, la conformité à la sécurité, la satisfaction des employés et des efficacités opérationnelles, mais elle peut également affecter la productivité et l’infrastructure organisationnelle de vos utilisateurs (votre réseau). Avant d’activer la nouvelle technologie au sein de votre organisation, effectuez un pilote utilisateur formel. De la même manière que vous peindreiez un petit morceau de couleur sur un mur avant de peindre toute la pièce, vous testeriez un déploiement large à plus petite échelle en conduire un pilote pour vérifier la disponibilité technique et des utilisateurs, identifier et réduire les problèmes et contribuer à la réussite de l’implémentation à l’échelle de l’organisation.

Pour obtenir les résultats les plus réalistes, le pilote doit impliquer des utilisateurs réels, reproduire la façon dont ils communiquent et collaborent, et vérifier les expériences tant techniques que utilisateur. Que votre organisation envisage d’utiliser Skype Entreprise et Teams côte à côte, de mettre à niveau vers Teams à l’avenir ou de déployer de nouvelles fonctionnalités telles que les appels ou les conférences, un pilote peut vous aider à identifier le bon chemin d’accès pour votre organisation. Parfois considéré comme la phase 1 d’un déploiement, le pilote idéal tire parti de la préparation que vous avez déjà commencée et implémente votre plan défini avec un groupe d’utilisateurs ciblé.

|&nbsp; | &nbsp;|
|---|---|
| ![Icône montrant les points de décision](media/audio_conferencing_image7.png) <br/>Point de décision|<ul><li>Comment utiliserez-vous un pilote pour informer l’orientation du projet ?</li></ul> |
| ![Icône montrant l’étape suivante.](media/audio_conferencing_image9.png)<br/>Étape suivante|<ul><li>Utilisez les instructions ci-dessous pour concevoir et exécuter votre pilote formel.</li></ul>|

> [!Tip]
> Utilisez les [exemples de ressources pilotes pour](https://aka.ms/UpgradeSuccessKit) vous aider à concevoir vos communications, votre plan de test et votre enquête de commentaires.

## <a name="1-outline-pilot-logistics"></a>1. Plan de logistique du pilote

Un pilote réussi a défini des dates de début et de fin, et des objectifs clairement [définis](upgrade-define-project-scope.md#project-goals) pour mesurer le succès. Ces objectifs doivent s’aligner sur l’étendue de votre projet à grande échelle, comme indiqué lorsque vous avez défini l’étendue du [projet,](upgrade-define-project-scope.md)et seront utilisés pour informer votre chemin d’accès une fois votre pilote terminé. Vous devez également vous assurer d’avoir inclus les parties prenantes concernées pendant toute la durée du projet. Nous vous conseillons de laisser suffisamment de temps pour exécuter le pilote et évaluer son impact : nous vous recommandons d’avoir au moins 30 jours.

Commencez modestement et ajoutez-y le cas échéant, que vous ajoutiez des charges de travail ou des fonctionnalités ou des utilisateurs supplémentaires, en faisant le temps d’évaluer les résultats et de modifier votre pilote à mesure que vous l’itétiez. Vous pouvez même choisir d’exécuter d’autres phases pilotes lorsque de nouvelles fonctionnalités de Teams sont publiées dans la feuille de route.

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a>2. Sélectionnez vos participants pilotes et scénarios de test

L'une des plus importantes tâches d'une planification pilote consiste à sélectionner des participants de manière judicieuse. N’oubliez pas que Teams est optimisé pour le travail d’équipe. Assurez-vous donc de sélectionner des participants pilotes non seulement en fonction de rôles ou de rôles, mais également en fonction de leur projet et du travail entre équipes. Vous pouvez commencer par demander à vos parties prenantes et responsables de département les projets réels que vous pouvez valider dans Teams. Un exemple de projet basé sur un rôle peut être d’utiliser Teams avec votre organisation commerciale pour vous assurer que les représentants de champ peuvent facilement accéder aux ressources dont ils ont besoin et partager des informations avec d’autres membres de champ. La coordination d’un événement de lancement de produit avec les équipes de marketing, de formation, de relations publiques et de planification d’événements est un exemple de travail basé sur un projet. Quels que soient les scénarios que vous sélectionnez, le pilote doit s’étendre aux personnes clés du service it, de la formation et de votre aide, afin que vous pouvez valider la solution de façon approfondie tout en optimisant pleinement les ressources de gestion de projet.

> [!Tip]
> Lorsque vous sélectionnez les participants de votre groupe pilote Teams, n’oubliez pas d’inclure les principaux utilisateurs de Skype Entreprise. Vérifiez avec ces utilisateurs comment ils utilisent Skype Entreprise aujourd’hui, puis créez un plan de test pour vérifier que Teams peut répondre à leurs besoins actuels.

## <a name="3-design-your-test-plan-and-feedback-survey"></a>3. Concevoir votre plan de test et votre enquête de commentaires

Pour une expérience pilote réussie, indiquez aux participants des tâches clairement définies, ainsi qu’un moyen pour eux de partager leurs commentaires. Groupez des tâches afin d’offrir des scénarios réels à vos utilisateurs, montrant la pertinence de leurs activités quotidiennes. Laissez les cas d’utilisation définis dans [Évaluer la](./upgrade-org-change-readiness.md) préparation au changement d’organisation guident votre plan de test.

Votre organisation peut choisir de piloter toutes les fonctionnalités en une fois ou d’utiliser une approche progressive , par exemple, la collaboration pilote d’abord, les réunions, puis les discussions et les appels. Assurez-vous d’avoir un canal de commentaires ouvert pour suivre l’avancement et mesurer les résultats. Utilisez une enquête prédéfinisée pour capturer et évaluer facilement les résultats pilotes. la conception de l’enquête doit être basée sur les scénarios et fonctionnalités de votre plan de test.

## <a name="4-create-your-communications-plan"></a>4. Créer votre plan de communication

Pour réussir votre pilote, il est essentiel d’informer les participants pilotes sur ce qui se passe, quand, pourquoi et ce qu’on attend d’eux. Pour stimuler l’enthousiasme et le nombre maximal de participants, n’oubliez pas d’inclure la messagerie de valeur utilisateur en plus des liens vers la formation et le support technique, qui permet aux utilisateurs d’obtenir des informations supplémentaires tout au long de la phase pilote. Voici quelques exemples de ressources pour vous aider à prendre en compte votre plan de communication pilote :

- [Ressources pilotes,](https://aka.ms/UpgradeSuccessKit)notamment des modèles de courrier électronique et des exemples de questions d’enquête de commentaires
- [Basculez vers Teams à partir de Skype Entreprise,](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964)un guide de démarrage rapide conçu pour aider les utilisateurs de Skype Entreprise à commencer à utiliser Teams

## <a name="5-conduct-your-pilot"></a>5. Conduire votre pilote

Avec toute la logistique en place, vous êtes maintenant prêt à commencer votre pilote. La conduite de votre pilote inclut la communication avec vos utilisateurs, une surveillance de votre réseau et de votre utilisation pour garantir que les performances et la qualité des appels réseau demeurent saines, rassemblez les commentaires des participants et examinez les tickets de service d’aide pour les questions liées à Teams.

### <a name="tips-for-pilot-success"></a>Conseils pour la réussite du pilote

Les conseils suivants peuvent vous aider à garantir la réussite de votre pilote :

- Avant de commencer votre pilote, confirmez que tous les participants pilotes sont activés pour le mode de coexistence approprié.
- ( https://aka.ms/SkypeToTeams-SetCoexistence) vous voulez valider.
- Réunion hebdomadaire, tout au long de votre phase pilote, avec les parties prenantes de votre projet pour examiner les commentaires des utilisateurs, les données d’utilisation, les données réseau et les tickets de aide pour s’assurer que votre pilote fonctionne correctement. Ajustons-les si nécessaire.

### <a name="suggested-timeline"></a>Chronologie suggérée

Voici une suggestion de calendrier pour un projet pilote de 30 jours :

- Une semaine avant le lancement du pilote : envoyer une communication initiale aux utilisateurs pilotes.
- Jour 1 : envoyer une communication de lancement aux utilisateurs pilotes.
- Jour 7 : Organiser la première réunion hebdomadaire de point de contrôle de l’équipe de projet.
- Jour 14 : Envoyez une communication intermédiaire à vos utilisateurs pilotes, organisez une réunion hebdomadaire de point de contrôle de l’équipe de projet.
- Jour 21 : Organiser une réunion hebdomadaire de point de contrôle de l’équipe de projet.
- Jour 30 : Envoyer la communication finale à vos utilisateurs pilotes.
- Jours 31 à 45 : Évaluez les résultats des phases pilotes et planifiez les étapes suivantes.

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a>6. Évaluer les apprentissages et évaluer votre plan de avance

Une fois votre pilote terminé, vous devez rassembler toutes les enquêtes de commentaires, les statistiques réseau finales et les tickets de support pour effectuer des analyses par rapport à vos objectifs et déterminer si vous allez implémenter votre plan de retour à l’avenir. Vous pouvez trouver que votre organisation est prête pour un déploiement à grande échelle, que vous souhaitez étendre votre pilote à davantage d’utilisateurs, ou que vous souhaitez revoir le pilote ultérieurement après avoir quelque peu réduit les problèmes identifiés. N’oubliez pas que votre pilote est un excellent moyen de prédire les résultats techniques et utilisateurs dans _un environnement_ contrôlé. penser à avancer trop rapidement.

Si vos résultats indiquent :

- **Vos objectifs pilotes (par exemple,** la satisfaction des utilisateurs et la qualité du réseau) ont été atteints, vous devriez être prêt à passer à la phase suivante de votre déploiement. Selon les objectifs de votre projet, cela peut être l’un des suivants :
  - Extension du pilote à d’autres participants
  - [Activation de Teams avec Skype Entreprise (mode **Îles)** pour l’ensemble ou une partie de votre organisation](./setting-your-coexistence-and-upgrade-settings.md)
  - [Mise à niveau des utilisateurs de Skype Entreprise vers Teams (mode **Teams** uniquement) pour tout ou partie de votre organisation](./setting-your-coexistence-and-upgrade-settings.md)
- Votre pilote n’a pas obtenu les résultats **souhaités (par exemple,** la satisfaction des utilisateurs et la qualité du réseau), prenez le temps d’apporter les ajustements appropriés à votre plan et de revoir votre pilote.

> [!Tip]
> Demandez à vos participants pilotes en tant qu’homologues de contribuer à l’intégration et à la intégration de nouveaux utilisateurs à Teams. Les pairs champions peuvent facilement s’y mettre en relation avec d’autres utilisateurs, partager leurs propres expériences et apprentissages, et offrir de l’aide et des conseils à leurs collègues. Découvrez les [champions et](https://go.microsoft.com/fwlink/?linkid=859068) la manière de les utiliser dans votre propre déploiement.