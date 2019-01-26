---
title: Opérations pour les équipes Microsoft | Gestion des services | Qualité
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Tâches et activités requises pour la gestion de service d’équipes, y compris la surveillance de l’intégrité du service et d’évaluer et de garantir l’utilisation et la qualité du réseau
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b455d7599f5de8e2eb76f560e593eb5e409ecae
ms.sourcegitcommit: c0679cbaf7df38769f722afd65c4232311d25515
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2019
ms.locfileid: "29562798"
---
![Étapes du voyage mise à niveau, en insistant sur la phase d’Excellence opérationnelle] (media/upgrade-banner-op-excellence.png "Étapes du voyage mise à niveau, en insistant sur la phase d’Excellence opérationnelle")

Cet article fait partie de la phase d’Excellence opérationnelle de votre parcours de mise à niveau, qui démarre dès que vous avez terminé votre mise à niveau à partir de Skype pour les entreprises aux équipes.

# <a name="operate-your-service"></a>Utiliser votre service

Cet article donne une vue d’ensemble de la configuration requise pour le fonctionnement avec succès des équipes pour votre organisation une fois que vous avez mis à niveau. En opérant correctement vos services équipes, vous pouvez être que vous fournissez une expérience de haute qualité et fiable pour votre organisation.

## <a name="introduction-to-the-operations-guide"></a>Introduction au Guide des opérations

Le Guide des opérations vous donne une vue d’ensemble de toutes les tâches et activités requises dans le cadre de la fonction de gestion de service pour Microsoft Teams.

Gestion des services est un sujet vaste qui traite des opérations quotidiennes du service Microsoft Teams après que qu’il a été déployé et activé pour les utilisateurs. Le service d’équipes englobe Microsoft Office 365 et les composants d’infrastructure qui sont déploiement en local (par exemple, mise en réseau).

La notion de gestion des services n’est probablement pas un nouveau concept pour la plupart des organisations. Vous avez peut-être déjà implémenté processus et les tâches qui sont associés à des services existants. Cela étant dit, vous pouvez probablement enrichir vos processus actuels lorsque vous planifiez aujourd'hui pour la gestion de service prendre en charge des équipes à l’avenir.

Gestion des services comprend toutes les activités et processus impliqués dans la gestion des équipes de bout en bout. Comme mentionné plus haut, certains composants de gestion des services — l’infrastructure comprend le service Office 365 lui-même — sont responsabilité de Microsoft, tandis que vous, le client, sont responsables à vos utilisateurs à gérer les différents aspects des équipes, le réseau et points de terminaison que vous fournissez.

Les tâches et activités dans ce guide sont regroupées dans les catégories de huit comme illustré dans le diagramme suivant. Chacune de ces catégories détaillent dans les sections suivantes.

Diagramme de ![A montrant une liste de catégories de tâches et les activités de gestion des services pour les équipes comprend. Le diagramme illustre également que la gestion de service est en grande partie d’une tâche client.] Diagramme de (media/operate-my-service-image1.png "A montrant une liste de catégories de tâches et les activités de gestion des services pour les équipes comprend. Le diagramme illustre également que la gestion de service est en grande partie d’une tâche client.")

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Points de décision</td><td><ul><li>Choisir le mode d’implémentation des opérations pour les équipes.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td><td><ul><li>Consultez le Guide des opérations dans leur intégralité.</li><li>Implémenter une stratégie d’opérations qui s’aligne sur les objectifs de votre organisation pour offrir la qualité et la fiabilité des charges de travail équipes.</li><li>Consultez le guide de l’examen de la qualité de l’expérience.</li><li> Implémenter une stratégie d’opérations pour effectuer régulièrement la qualité d’expérience avis pour vous assurer que votre déploiement équipes fonctionne à ses fonctionnalités de pointe.</li></ul></td></tr>
</table>

### <a name="operational-role-mapping"></a>Mappage de rôle opérationnel

Se sont engagés pour les opérations pendant la phase de prévoir la planification est essentielle, car les activités opérations commencent lorsque les utilisateurs du pilote premier sont activés. Ce guide répertorie les activités et les tâches qui doivent être effectuées sur une base quotidienne, hebdomadaire, mensuelle ou selon les besoins pour mettre à jour un déploiement d’équipes de haute qualité. Ce guide fournit des connaissances et des conseils pour savoir comment effectuer ces tâches et activités critiques.

Un composant essentiel d’un déploiement réussi consiste à vous assurer que la planification que vous effectuez au début de la phase de prévoir inclut l’identification qui sera chargé d’effectuer les activités spécifiques. Une fois que vous avez trouvé les tâches et les activités qui s’appliquent à votre déploiement, ils doivent être comprises et suivi des groupes ou des personnes que vous leur attribuez.

Chaque équipe que vous identifiez doit consulter et accord sur les tâches et les responsabilités et commencer à préparer. Cela peut inclure la formation et la préparation, en fournissant des mises à jour le plan de dotation en personnel ou en vous assurant que les fournisseurs externes sont prêts à fournir.

Les activités et les rôles définis dans ce guide doivent être valides dans la plupart des scénarios, mais chaque déploiement équipes est unique ; Par conséquent, vous pouvez utiliser ce guide comme point de départ pour personnaliser les activités et les rôles par défaut pour répondre à vos besoins.

Assurez-vous que chaque équipe responsable dispose d’une bonne compréhension des activités qui sont requis pour exécuter le service. Il est fondamental que chaque équipe accepte et approuve sous leur responsabilité dans votre organisation avant le premier pilote.

Une fois un accord est en place, les équipes correspondants doivent commencer à mettre leurs rôles.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Étapes suivantes</td>
<td><ul><li>Utilisez ce document pour faciliter l’exercice de mappage de rôle opérationnel.</li><li>Rencontrez les équipes de support respectifs pour attribuer des noms à chaque élément dans la liste des activités requises.</li><li>Obtenir l’acceptation ou approbation sur les rôles attribués.</li><li>Vous assurer que les équipes correspondantes les formations appropriées, préparation et les ressources pour effectuer les activités requises d'entre eux.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Dépendances de service d’équipes

Microsoft Teams réunit les technologies dans Office 365 pour fournir un concentrateur pour le travail d’équipe. Voici quelques exemples :

- Azure Active Directory (AD Azure) fournit des services d’authentification et d’autorisation pour les équipes.

- Exchange Online fournit des fonctionnalités avancées telles que la conservation légale et de détection électronique.

- SharePoint Online offre la possibilité de partager des fichiers dans des canaux et OneDrive entreprise fournit un mécanisme de partage de fichiers au sein d’une conversation privée.

Les organisations peuvent également exploiter les investissements existants dans l’infrastructure locale. Par exemple, les comptes Active Directory sur site existants utilisable pour l’authentification en tirant parti d’Azure AD se connecter. Certaines versions d’Exchange Server peuvent être utilisées à la place Exchange Online.

Ces technologies se retrouvent pour fournir une suite de communications enrichies, collaboration et intelligent pour les utilisateurs. Cette intégration étroite est l’avantage d’équipes, mais il gère également une condition requise pour la gestion de service entre ces technologies.

Ce guide couvre les domaines de prédilection pour gérer le service d’équipes. Vous avez probablement, des plans de gestion de service en place pour les technologies de prise en charge qui dépend d’équipes. Si non, vous devez établir des plans de gestion de service pour les composants de la technologie (à la fois sur site et en ligne) également. Cela aide à vérifier que vos utilisateurs bénéficient d’une expérience de haute qualité et fiable avec des équipes.

#### <a name="references"></a>Références

[Présentation de Microsoft Teams](teams-overview.md)

[Interaction entre Exchange et Microsoft Teams](exchange-teams-interact.md)

[Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams](sharepoint-onedrive-interact.md)

[Microsoft Teams et Skype pour l’interopérabilité et coexistence d’entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Activités de Guide des opérations

Les sections suivantes fournissent une vue d’ensemble des activités qui sont requises pour le service Microsoft Teams. Elles incluent les référence à des outils, des informations contextuelles et de contenu supplémentaire pour vous aider à comprendre l’activité et pour vous aider aux initiatives de préparation.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Surveiller l’intégrité de service

Il est important de comprendre l’intégrité globale du service Microsoft Teams afin que vous pouvez alertes d’autres personnes de votre organisation d’un événement qui affecte le service. Comme indiqué précédemment, les équipes est dépendent d’autres services Office 365 comme Azure Active Directory, Exchange Online, SharePoint Online et OneDrive for Business. Pour cette raison, il est également important de surveiller l’intégrité des services dépendants.

Incorporer cette activité dans votre processus de gestion des incidents pour informer les utilisateurs, le support technique et vos équipes d’opérations pour vous préparer à gérer les escalades utilisateur proactive.

Les sections suivantes décrivent les outils que vous pouvez exploiter pour analyser les [incidents de service](https://technet.microsoft.com/library/office-365-service-health.aspx#Anchor_1) qui affectent le service d’équipes. Un résumé des avantages de chaque outil et vous devez utiliser chacun d’eux, est inclus dans le tableau suivant.

| Outil d’analyse | Avantages | Quand utiliser |
|---|---|---|
| Portail Office 365 | Disponible à partir de n’importe quel appareil avec un navigateur pris en charge. | À utiliser lorsque vous n’avez pas besoin des notifications en temps réel. |
| Application d’administration Office 365 | Fournit des notifications push vers votre appareil mobile. | À utiliser lorsque vous souhaitez être averti d’incidents service pendant que vous êtes en déplacement. |
| Microsoft System Center | Intégration à Microsoft System Center. | À utiliser lorsque vous avez besoin des fonctionnalités avancées de surveillance et de prise en charge de la notification. |
| API de Communications Service Office 365 | Accès par programme à l’intégrité du service Office 365. | À utiliser lorsque vous avez besoin de l’intégration avec un outil de surveillance tiers ou que vous souhaitez créer votre propre solution. |

> [!NOTE]
> Seules les personnes qui sont du rôle **d’administrateur global** ou **administrateur de service** peuvent afficher l’intégrité du service.

### <a name="monitoring-with-the-office-365-portal"></a>Surveillance avec le portail Office 365

Le [portail Office 365](https://portal.office.com/) fournit un [tableau de bord d’intégrité du Service](https://portal.office.com/adminportal/home#/servicehealth) où vous pouvez afficher l’état actuel du service équipes en plus des services dépendants.

### <a name="monitoring-with-the-mobile-app"></a>Surveillance de l’application mobile

L’application d’administration d’Office 365 est disponible sur Apple iOS, Android et Windows (PC et mobile). L’application fournit des informations sur l’intégrité du service et les modifications à venir les administrateurs de service. L’application prend en charge les notifications push qui vous avertit presque immédiatement après un avis a été validé. Ainsi, vous restez informé sur l’état d’intégrité et les modifications à venir au service. La prise en charge de la notification facilite l’outil d’analyse recommandé pour les administrateurs. Pour plus d’informations, voir :

[Application Mobile d’administration Office 365](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Télécharger l’application Mobile d’administration Office 365](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Surveillance avec Microsoft System Center

Microsoft System Center est une plate-forme de gestion intégrés que permet de gérer les centre de données, les périphériques clients et hybride environnements informatiques en nuage. Les administrateurs Office 365 qui utilisent System Center maintenant ont la possibilité d’importer le Pack d’administration Office 365, qui leur permet d’afficher toutes les communications de service dans Operations Manager dans System Center. À l’aide de cet outil vous permet d’accéder à l’état de vos services abonnés, incidents actifs et résolus service et vos communications centre de messages (modifications à venir). Pour plus d’informations, reportez-vous à la suivante [le billet de blog](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true).

Si vous utilisez System Center pour surveiller les équipes service l’intégrité (et les services dépendants), vous pouvez personnaliser davantage le pack d’administration pour l’alerte ou avertir des groupes ou des utilisateurs individuels qui ont été identifiés réagir aux incidents.
Ces groupes peuvent inclure les propriétaires de services, services, des groupes de prise en charge de deuxième et troisième niveau et responsables de l’incidents dans votre organisation.

### <a name="monitoring-for-advanced-scenarios"></a>Surveillance des scénarios avancés

Vous pouvez surveiller l’intégrité du service et les modifications à venir en tirant parti de l’API de Communications du Service Office 365 pour accéder par programme des modifications et intégrité du service Office 365. Cette API permet de créer votre propre contrôle outil ou vous connecter vos outils d’analyse existantes à communications de service Office 365, potentiellement simplification de la surveillance de votre environnement. Pour plus d’informations, voir [Office 365 pour les développeurs d’entreprise](https://msdn.microsoft.com/library/jj984343(v=office.15).aspx).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/selon les besoins

| Activité | Description | Cadence | Équipe affecté |
|---|---|---|---|
| Surveiller l’intégrité de service | Surveillance proactive de l’intégrité du service Microsoft Teams (et les services dépendants) en utilisant les outils disponibles. Incluent des services dépendants : Exchange Online, SharePoint Online, OneDrive entreprise, Azure Active Directory. | En temps réel | |
| Notification d’incident | Informer les parties prenantes internes des événements qui affectent le service d’équipes. Parties prenantes internes peuvent inclure des utilisateurs, les services et les responsables de l’incidents. | Selon vos besoins | |

### <a name="references"></a>Références

[Comment vérifier l’intégrité du service Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Vérifier l'intégrité du service pour Microsoft Teams](service-health.md)

[Continuité d’activité et de fonctionnement du Service](https://technet.microsoft.com/library/office-365-service-health.aspx)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Gérer les modifications de l’organisation

Microsoft Teams est un service en nuage. Avec qui proviennent de la capacité de fournir les nouvelles fonctions et fonctionnalités rapidement. Fournir des innovations en cours fournit un avantage pour les organisations, mais ces modifications doivent être gérées de manière appropriée au sein de votre organisation afin d’éviter de résistance ou escalade pour le support technique.

Mises à jour des équipes sont déployées automatiquement à vos utilisateurs. Vos utilisateurs auront toujours le client et les fonctionnalités disponibles dans le service d’équipes le plus récent. Il n’est pas possible de gérer le déploiement des mises à jour des équipes à vos utilisateurs, par conséquent, il est essentiel pour gérer les modifications par le biais de programmes de communication, des formations et d’adoption efficaces. Si vos utilisateurs sont conscients de la modification, informés des avantages et habilité à tirer parti des nouvelles fonctionnalités&mdash;ils pourront à adapter plus rapidement et la modification de bienvenue.

### <a name="monitoring-for-change"></a>Changement de surveillance

La première étape de la gestion des modifications consiste à surveiller les modifications qui sont planifiées pour les équipes. La meilleure source pour la surveillance de ces modifications est la [Feuille de route Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap), qui répertorie les fonctionnalités qui sont actuellement en développement, en cours de déploiement pour les clients, ou ont lancé entièrement. Vous pouvez rechercher des fonctionnalités spécifiques aux équipes à l’aide du filtre fourni, ou vous pouvez télécharger la feuille de route pour un fichier Excel pour une analyse approfondie. Pour chaque fonctionnalité, la feuille de route donne une brève description, ainsi que la date de publication prévue.

Dans le [blog des équipes Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog), vous pouvez Découvrez les meilleures pratiques, les tendances et les informations sur les mises à jour les équipes. Prévu rechercher les mises à jour principales aux équipes à annoncer ici. Vous pouvez également vous abonner au blog via un flux RSS. Vous pouvez ensuite ajouter [le flux RSS](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) directement dans un canal d’équipes, afin que toutes les informations importantes sont remises directement à l’intérieur d’équipes.

Toutes les fonctionnalités qui sont publiées sont décrits dans les [Notes de publication pour les équipes Microsoft](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de).
Vous trouverez une liste des fonctionnalités qui ont été publiées pour le bureau, web et les appareils mobiles. Le même ensemble de notes de publication sont également disponibles dans l’onglet [aide](get-help-in-microsoft-teams.md)de **ce qui est nouveau** .

Vous familiariser avec les ressources disponibles et assurez-vous que vous affectez propriétaires applicables à surveiller pour modification.

### <a name="planning-for-change"></a>Planification de modification

Maintenant que vous êtes au courant des modifications à venir pour le service d’équipes, l’étape suivante consiste à préparer et planifier en conséquence. Évaluez chaque modification pour déterminer les modifications qui nécessitent la communication à la formation des utilisateurs, des campagnes de sensibilisation, pour la prise en charge des équipes ou des utilisateurs ou des campagnes d’évaluation et de l’adoption de fonctionnalité. Il s’agit du rôle principal d’une équipe de gestion des modifications dans votre organisation. Vous trouverez ci-dessous est une collection d’exemples de tables qui peuvent vous aider à planifier les modifications.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Fonctionnalité : Enregistrement en nuage (date de publication : janvier 2018)

**Suivi général**

| Préparation de la modification | État | Notes/étapes suivantes | Propriétaire |
|---|---|---|---|
| Révision légale | Terminé | Cette fonctionnalité est une condition préalable à la formation de l’équipe d’intégration. | Équipe de projet |

**Gestion des modifications techniques**

| Préparation de la modification | État | Notes/étapes suivantes | Propriétaire |
|---|---|---|---|
| Modifications informatiques requises | Oui | Administrateur doit activer l’enregistrement identifiés uniquement aux utilisateurs. | Équipe de support technique |
| Préparation technique complète | Oui | | Équipe de support technique |
| | | | |

**Gestion des modifications**

| Préparation de la modification | État | Notes/étapes suivantes | Propriétaire |
|---|---|---|---|
| Impact sur l’utilisateur | Bas | | |
| Préparation de l’utilisateur | Oui | | |
| Communications prêtes | Non | Courrier électronique de communication a été rédigé — en attente de révision. | Équipe des communications |
| Formation prêt | Oui | Formation s’appuiera sur vidéo Microsoft existant. | Formation de l’équipe |

**Suivi du statut**

| Préparation de la modification | État | Notes/étapes suivantes | Propriétaire |
|---|---|---|---|
| Statut de lancement | en cours | Révision en attente par sponsor exécutif. | Équipe de gestion des modifications |
| Approbation de publication | | | |
| Date de publication | | | |

Pour plus d’informations sur la planification de la gestion des modifications avec les équipes, voir [créer une stratégie de gestion des modifications pour les équipes Microsoft](change-management-strategy.md).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/selon les besoins

| Activité| Description| Cadence| Équipe affecté |
|---|---|---|---|
| Surveiller les modifications| Surveiller les modifications à venir au service Microsoft Teams.| Jour||
| Planification de modification| Évaluer et planifier des nouvelles fonctionnalités et fonctions, y compris les plans de communication, campagnes de sensibilisation et des formations.| Selon vos besoins ||
| Préparation des utilisateurs| Effectuez communication ciblée, sensibilisation ou campagnes de formation pour les utilisateurs sont prêts pour que les modifications à venir.| Selon vos besoins ||
| Prise en charge de la préparation de l’équipe | Effectuer communication ciblée, sensibilisation ou campagnes de formation pour s’assurer de que l’équipe de support est prête. Équipes de support technique peuvent inclure l’équipe « GANT blanc », services, niveau 2 ou niveau 3 prise en charge, partenaires externes et ainsi de suite. | Selon vos besoins ||

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Évaluer l’utilisation des équipes

Une fois que le pilote initial commence, il est fondamental pour établir une mesure de l’utilisation des équipes réelle préliminaires régulière. Cela permet de votre organisation pour obtenir des informations sur l’utilisation réelle comment s’aligne sur l’utilisation vous prévues pendant la phase de prévoir. Bien que cette section se concentre sur l’utilisation des équipes, il doit s’agir d’un plus large efforts pour mesurer et évaluer l’utilisation d’Office 365 globale.

Révision d’utilisation fréquemment au début du déploiement vous donne la possibilité de :

- Vérifier si les utilisateurs utilisent des équipes.

- Identifier les défis d’adoption potentiels avant de créer des problèmes critiques dans l’organisation.

- Comprendre s’il existe des différences entre les exigences de phase de prévoir et l’utilisation réelle.

Si l’utilisation n’est pas le résultat escompté, il peut s’agir d’un problème de déploiement ou le plan d’adoption n’est pas en cours exécutée correctement, ou tout autre problème. Selon la raison réelle derrière la peu, l’administrateur de service doit collaborer avec les équipes connexes pour vous aider à supprimer les obstacles d’utilisation.

### <a name="measuring-usage-with-the-office-365-admin-center"></a>Mesure de l’utilisation avec le centre d’administration Office 365

Les données d’utilisation des équipes sont disponibles dans le tableau de bord de création de rapports. Vous trouverez les données d’utilisation des équipes dans trois différents rapports. Le premier rapport fournit une vue d’entre les produits d’aux utilisateurs comment communiquent et collaborent à l’aide de divers services dans Office 365. Ce rapport se trouvent ici : [rapport d’utilisateurs actifs Office 365](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Les deux rapports sont des équipes spécifiques, et qu’ils fournissent davantage de détails sur l’utilisation des équipes à partir d’un utilisateur et un point de vue de périphérique. Les deux rapports se trouvent ici :

[Rapport d’utilisation des périphériques de Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Rapport d’activité des utilisateurs de Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>Autorisations requises

Les rapports d’utilisation dans le centre d’administration est accessible par les personnes qui ont été affectés à un rôle **d’administrateur Global** ou un rôle d’administration spécifiques au produit (**administrateur Exchange**, **Skype pour l’administrateur d’entreprise**, **SharePoint administrateur**).

En outre, le rôle de **lecteur de rapports** est disponible pour les utilisateurs qui ont besoin d’accéder aux rapports, mais ne pas effectuer les tâches qui nécessitent des autorisations de niveau administrateur. Vous attribuez ce rôle pour fournir des rapports d’utilisation à toute personne qui est une parties prenantes, à l’adoption de moniteurs et de lecteur. Pour plus d’informations sur les différents rôles disponibles, voir [rôles d’administrateur sur Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="assessing-usage"></a>Évaluation de l’utilisation

Une fois que vous avez utilisé le tableau de bord de création de rapports pour mesurer l’utilisation, il est important de comparer l’utilisation mesurée par rapport à des indicateurs de réussite clés (KSIs) que vous avez défini lors de la phase du projet prévoir. Vous pouvez définir un KSI peut être défini en tant que l’utilisation active, ou celui qui est indirectement lié à l’utilisation active.

Il est important d’identifier les éventuelles variations entre utilisation réelle et prévue avant de reprendre le déploiement sur les sites supplémentaires ou des utilisateurs. Vous allez probablement identifier appris d’organisation dans le cadre de cette activité que vous pouvez exploiter pour vous assurer que le lot suivant de sites ou les utilisateurs ne rencontrer les mêmes problèmes.

Identifier tout d’abord, s’il s’agit d’un problème technique ou un kit d’adoption. Commencer à rechercher les éléments ci-dessous, dans l’ordre, pour déterminer la cause du problème.

1. Valider la qualité en effectuant un [Examen de la qualité de l’expérience](upgrade-monitor-quality.md).

2. Utilisation de l’équipe de support technique pour vérifier qu’il n’y a aucun problème technique tendance empêche les utilisateurs d’accéder à ou l’utilisation du service. Si tendances n’existent pas, utilisez la section [résolution des problèmes de point de terminaison](#endpoint-troubleshooting) plus loin dans cet article pour tenter de résoudre le problème avant prise en charge.

3. Utilisation de l’équipe de formation et d’adoption pour recueillir les commentaires des utilisateurs (voir [Assess sentiment de l’utilisateur](#assess-user-sentiment) plus loin dans cet article) et pour vérifier l’efficacité des activités de sensibilisation et d’adoption.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/selon les besoins

| Activité | Description | Cadence | Équipe affecté |
|---|---|---|---|
| Utilisation de la mesure (phase activation) | Mesurer et évaluer l’utilisation des équipes comme sites continuent d’être onboarded pendant la phase d’activation. Résoudre les problèmes d’utilisation selon les besoins. | Toutes les semaines | |
| Utilisation de mesure | Mesurer et évaluer l’utilisation des équipes lors de la phase de valeur lecteur (après que le déploiement a été effectué). Résoudre les problèmes d’utilisation selon les besoins. | Deux fois par semaine | |
| (phase de valeur lecteur) | | | |
| Mettre à jour le plan d’adoption | Mise à jour en fonction de votre plan d’adoption sur l’utilisation du mode mesurée compare à vos objectifs en termes de planification. | Selon vos besoins | |

### <a name="references"></a>Références

[Sur le centre d’administration Office 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Rapports d'activité dans le centre d’administration Office 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Évaluer le sentiment de l’utilisateur

Présentation sentiment de l’utilisateur peut agir comme un indicateur clé pour mesurer la réussite de votre déploiement d’équipes. Les commentaires des utilisateurs peuvent entraîner des modifications dans votre organisation ; Cela peut inclure des modifications apportées à vos plans de communication, des programmes de formation ou de la manière qui offrent aux utilisateurs.

Il est important de recueillir les commentaires au début et poursuivre l’évaluation sentiment de l’utilisateur tout au long du cycle de vie du projet et au-delà. Utilisez les conseils suivants pour déterminer l’intervalle dans lequel votre organisation recherche commentaires :

- **Début du projet**: en évaluant sentiment de l’utilisateur au début du projet, vous pouvez obtenir une vue au plus tôt dans vos utilisateurs pensent l’expérience de leurs équipes.

- **Après les principales étapes**: en recueillant des commentaires tout au long du cycle de vie du projet, vous pouvez évaluer sentiment de l’utilisateur en continu et apportez les modifications nécessaires. Ceci est particulièrement utile après les principales étapes.

- **Conclusion Project**: évaluation sentiment de l’utilisateur à la fin d’un projet vous indiquera comment vous avez effectué et où travail doit toujours être effectué et vous permettent de comparer les résultats par rapport à l’enquête précédente.

- **Permanente**: continuer à mesurer sentiment de l’utilisateur indéfiniment. Modifications apportées à un sentiment de l’utilisateur peuvent être en raison de modifications dans l’environnement de votre organisation ou dans le service d’équipes. Par mesure sentiment de l’utilisateur à intervalles réguliers, vous pouvez comprendre la qualité d’exécution de vos équipes de gestion de service et comment votre organisation répond aux modifications dans le service d’équipes.

Sentiment de l’utilisateur peut être évaluée par le biais de nombreuses méthodes différentes. Ces peuvent inclure des enquêtes du courrier électronique, en personne ou entretiens style téléphone ou tout simplement en créant un canal de commentaires dans des équipes ou Yammer. Pour plus d’informations, voir [meilleures pratiques pour les méthodes de commentaires des utilisateurs dans les équipes Microsoft](best-practices-feedback.md).

Vous pouvez également utiliser une approche de formation pour évaluer sentiment de l’utilisateur appelé Lactococcal net score (NPS), qui est décrite dans la section suivante.

### <a name="nps"></a>NPS

Score promoteur NET (NPS) est une mesure de fidélité client formation et une bonne approche à adopter pour évaluer sentiment de l’utilisateur. NPS peut être calculée en demandant à deux questions : « quelle est la probabilité que vous recommandiez équipes à un collègue ? », suivi de la forme libre question, « Pourquoi ? »

NPS est un index compris entre – 100 et 100 exhaustive de son désir d’un client de recommander le produit ou le service d’une société. NPS est basé sur une étude anonyme qui est remise aux utilisateurs par le biais de messagerie ou d’autres moyens électroniques. NPS mesure la fidélité entre un fournisseur et un consommateur. Il se compose de qu’une question, qui demande à l’utilisateur d’évaluer leur expérience comprise entre 1 et 10, avec la possibilité de fournir des commentaires supplémentaires. Les utilisateurs sont alors classés selon les niveaux suivants :

- 9 ou 10 sont facteurs : passionnés fidèles qui seront promouvoir votre service et d’autres personnes de combustibles.

- 7 ou 8 sont Passive : satisfait mais pas enthousiaste, vulnérable à un autre service ou offre.

- À partir de 1 à 6 sont détracteurs : nombre de clients mécontents qui permettre endommager votre service et entraver la croissance.

![Ce diagramme montre l’échelle NPS. Il indique que classements comprise entre 0 et 6 sont détracteurs, 7 à 8 sont passive, et 9 et 10 sont des facteurs.] (media/operate-my-service-image2.png "Ce diagramme montre l’échelle NPS. Il indique que classements comprise entre 0 et 6 sont détracteurs, 7 à 8 sont passive, et 9 et 10 sont des facteurs.")

Bien que le nombre de NPS base soit utile, vous récupérez la valeur de l’analyse des commentaires de l’utilisateur. Ils allez vous aider à comprendre pourquoi l’utilisateur serait (ou ne) est recommandé aux équipes à d’autres personnes. Ces commentaires peuvent fournir des commentaires précieux pour le projet ou équipes de gestion de service comprennent les ajustements nécessaires pour assurer un qualité service.

Pour fournir des enquêtes NPS à votre organisation, vous pouvez exploiter votre outil préféré enquête en ligne.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tous les jours/toutes les semaines/mois/comme nécessaires des tâches

| Activité | Description | Cadence | Équipe affecté |
|---|---|---|---|
| Évaluer le sentiment de l’utilisateur | Capturer et évaluer sentiment de l’utilisateur par le biais d’enquêtes ou entretiens ou via un canal de commentaires dans des équipes ou Yammer. | Selon vos besoins | |
| Mettre à jour des plans d’adoption | Modification du lecteur dans votre organisation basée sur les commentaires des utilisateurs ; Cela peut inclure des modifications apportées à vos plans de communication, des programmes de formation ou de la manière qui offrent aux utilisateurs. | Selon vos besoins | |

### <a name="references"></a>Références

[Score promoteur NET](https://en.wikipedia.org/wiki/Net_Promoter)

[Utilisation de Yammer pour recueillir les commentaires](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Meilleures pratiques pour les commentaires des utilisateurs](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Gérer la qualité du réseau

De nombreux éléments de planification principale passent en optimisation, le redimensionnement et correction de votre infrastructure de réseau pour assurer une haute qualité et efficace le chemin d’accès au service Microsoft Teams. Les tâches de planification et les exigences sont abordées dans notre Guide de [Préparation du réseau](upgrade-prepare-environment-prepare-network.md) . Souvent, les réseaux évoluent au fil du temps en raison des mises à niveau, une expansion ou autres impératifs d’entreprise. Il est important de compte pour vos besoins pour les équipes de votre réseau d’activités de planification.

Bien que la planification du réseau est un aspect essentiel d’un déploiement d’équipes, il est également important assurer le réseau reste sain et reste actif, selon l’évolution des exigences techniques ou l’entreprise.

Pour vérifier l’intégrité de votre réseau, un nombre d’opérations activités doivent être effectuées à intervalles réguliers.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/selon les besoins

| Activité | Description | Cadence | Équipe affecté |
|---|---|---|---|
| Surveiller Office 365 IP et des URL | Surveiller des modifications apportées à [Office 365 URL et plages d’adresses IP](https://aka.ms/o365ips) à l’aide fournie sur les [flux RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) et que vous lancez une demande de modification à des groupes réseau applicables. | Jour | |
| Mise à jour du réseau en fonction des modifications apportées à Office 365 IP et des URL | Mettre à jour les composants réseau applicable (pare-feu, serveurs proxy, VPN, pare-feu côté client et ainsi de suite) afin de refléter les modifications apportées à [Office 365 URL et plages d’adresses IP](https://aka.ms/o365ips). | Selon vos besoins | |
| Fournir des données de création | Fournir les informations de sous-réseau mis à jour le poids lourd qualité (ou concernées) pour garantir que la [Création de définitions de CQD](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) sont à jour. | Selon vos besoins | |
| Implémenter des modifications | Implémenter les modifications sur le réseau pour la prise en charge des variables équipes exigences commerciales et techniques. Éléments du réseau peuvent inclure :<ul><li>Pare-feu</li><li>Réseaux privés virtuels</li><li>Filaire et les réseaux Wi-Fi</li><li>La connectivité Internet et ExpressRoute</li><li>DNS</li></ul> | Selon vos besoins | |
| Création de rapports et de surveillance de réseau | Surveiller le réseau de bout en bout de disponibilité, l’utilisation et les tendances de capacité à l’aide de vos outils de gestion réseau tiers existants et création de rapports disponibles auprès de fournisseurs de votre réseau. Utilisez les tendances des données pour la planification de la capacité réseau. | Daily, weekly, monthly | |
| Planification de capacité | Collaborer avec les propriétaires des services aux équipes de comprendre l’évolution des besoins métiers et techniques qui peuvent entraîner des modifications de la capacité supplémentaire. Exploiter les résultats à partir de [Planificateur réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) pour s’assurer que suffisamment de bande passante est disponible pour Microsoft Teams. | Selon vos besoins | |
| Résolution des problèmes de réseau et de correction | Aider les services équipes, les propriétaires de services et les principales parties prenantes à résoudre les problèmes et à résoudre les problèmes liés aux équipes connectivity, la fiabilité ou la qualité. Éléments du réseau peuvent inclure :<ul><li>Pare-feu</li><li>Réseaux privés virtuels</li><li>Filaire et les réseaux Wi-Fi</li><li>La connectivité Internet et ExpressRoute</li><li>DNS</li></ul> | Selon vos besoins | |
| Test de la haute disponibilité et de la récupération d’urgence | Effectuez régulière haute disponibilité et récupération d’urgence test sur l’infrastructure réseau pour vous assurer qu’il répond aux objectifs de niveau de service indiquée (SLA) les contrats de niveau de service (SLA) pour le service d’équipes. | Mois | |

### <a name="references"></a>Références

[Planificateur de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)

[URL et plages d'adresses IP Office 365](https://aka.ms/o365ips)

[Schéma des données de création](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Évaluer et de garantir la qualité

Toutes les organisations besoin d’un groupe ou la personne qui sera responsable de la qualité. Il s’agit d’un rôle essentiel dans la gestion de service. Le rôle de poids lourd qualité est affecté à une personne ou un groupe qui est passionné sur l’expérience des utilisateurs.
Ce rôle nécessite les compétences nécessaires pour identifier les tendances dans l’environnement et le soutien pour travailler avec d’autres équipes pour diriger la mise à jour. En général, le meilleur candidat au rôle de Champion Qualité est le responsable du service clientèle. Selon la taille et la complexité de l’organisation, cela peut être une personne ou un groupe avec une passion pour garantir une expérience utilisateur de qualité.

Le poids lourd qualité tire parti des outils existants et identifient les tendances de qualité des processus documentés, tels que le tableau de bord de la qualité des appels (CQD) et le Guide Quality of Experience révision, de surveiller l’expérience utilisateur et correction du lecteur lorsque cela est nécessaire.
Le poids lourd qualité devrait fonctionner par rapport à un comité directeur sur l’avancement et tous les problèmes et les équipes respectifs pour exécuter des actions de mise à jour.

La [Qualité d’expérience consulter le Guide](https://aka.ms/qerguide) comprend des activités qui évaluer et fournissent des instructions de mise à jour dans les zones clés qui ont le plus grand impact sur l’amélioration de l’expérience utilisateur. Les instructions fournies dans le Guide de révision de l’expérience de qualité se concentre sur l’utilisation CQD en ligne en tant que le principal outil pour signaler et examiner chaque zone, en mettant l’accent sur l’audio à optimiser l’impact d’adoption et de. Les optimisations apportées au réseau pour améliorer l’expérience audio auront également directement des améliorations dans le partage du bureau et vidéo.

Nous vous recommandons vivement de vous désigner le poids lourd qualité dès le début. Après avoir en cours désignés, ils doivent commencer à se familiariser avec le contenu dans le Guide Quality of Experience révision et supports de formation associé.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/selon les besoins

| Activité | Description | Cadence | Équipe affecté |
|---|---|---|---|
| Nommer et former champion(s) de qualité | Nommer et former un champion de qualité. | Selon vos besoins | |
| Effectuer la qualité de l’expérience avis (QERs) | Effectuer un QER pour identifier les tendances de qualité et de fiabilité, passez en revue par rapport à des objectifs définis et rapport principales parties prenantes dans l’organisation. | Tous les mois (toutes les semaines au cours des déploiements) | |
| Lecteur de correction | Coordonner les efforts de correction de l’organisation en fonction des résultats et évaluations QER. | Selon vos besoins | |
| Mettre à jour des données de création de CQD | Mettre à jour ou ajouter de nouvelles définitions de construction dans CQD lorsque des modifications sont apportées au réseau (voir [les informations de construction de téléchargement](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | Selon vos besoins | |
| Remplir le rôle Champion de qualité | Responsables de bout en bout de la qualité de l’organisation. Cela inclut :<ul><li>Assurez-vous que le QER est mené régulièrement.</li><li>Signaler pour les principales parties prenantes sur l’état de la qualité.</li><li>Vérifiez que les données de création de définitions sont à jour.</li><li>Coordonner les efforts de correction de l’organisation pour vous assurer que les utilisateurs ont une expérience de haute qualité avec des équipes.</li></ul> | Jour | |

### <a name="references"></a>Références

[Découvrez CQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos)

[Informations de création de téléchargement](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[Qualité de consulter le Guide de l’expérience](https://aka.ms/qerguide)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Gérer les points de terminaison

Points de terminaison Teams Microsoft peuvent être définis comme n’importe quel PC, Mac, tablette ou l’appareil mobile (ou tout autre) qui exécute le client équipes. terme *point de terminaison* englobe non seulement l’appareil lui-même, mais comment un utilisateur se connecte à l’appareil — par exemple, à l’aide de microphone intégrés du périphérique ou haut-parleur, écouteurs par ou un casque optimisé. Une fois qu’ils sont déployés, les points de terminaison ne doivent pas oubliés. Les points de terminaison équipes requièrent des soins en cours et maintenance. Les sections suivantes décrivent de se concentrer sur des zones spécifiques.

### <a name="endpoint-requirements"></a>Configuration requise du point de terminaison

Un des principaux avantages des équipes est que le client est mis à jour automatiquement. Les clients sur le PC et Mac sont mis à jour à l’aide d’un processus d’arrière-plan qui vérifie les nouvelles versions et télécharge le nouveau client lorsque l’application est inactive. Les applications mobiles équipes sont mises à jour dans les magasins de leur application respectifs.

Le client équipes a la configuration minimale requise en termes de la plate-forme logicielle sous-jacent. Ces besoins peuvent changer au fil du temps, et par conséquent, il est important de surveiller les modifications. Par exemple, le client équipes a une version minimale iOS. Si le client utilise un navigateur internet, le navigateur doit être mis à jour également. Vous trouverez la liste des plateformes prises en charge dans [obtenir des clients pour les équipes Microsoft](get-clients.md).

### <a name="endpoint-firewalls"></a>Pare-feu de point de terminaison

Pare-feu côté client peuvent avoir un impact significatif sur l’expérience utilisateur.
Pare-feu côté client peuvent avoir une incidence sur la qualité des appels et même empêcher un appel à partir de l’établissement. Une fois que les exclusions appropriées sur le pare-feu du client ont été configurées, ils doivent être mis à jour en fonction des informations dans [Office 365 URL et plages d’adresses IP](https://aka.ms/o365ips). Votre fournisseur tiers auront des instructions spécifiques à la mise à jour les exclusions.

### <a name="wi-fi-drivers"></a>Pilotes Wi-Fi

Pilotes Wi-Fi peuvent poser. Par exemple, un pilote peut avoir très agressifs comportements itinérance entre les points d’accès qui peuvent amener les points d’accès inutile de commutation, conduisant à l’appel de mauvaise qualité. Un pilote Wi-Fi médiocres peut être découvert par un examen de la qualité de l’expérience (voir le [Guide Quality of Experience révision](https://aka.ms/qerguide) pour plus de détails). Il est essentiel pour implémenter un processus de qualité qui surveille les nouveaux pilotes Wi-Fi et s’assurer qu’ils sont testés avant le déploiement pour les utilisateurs généraux.

### <a name="endpoint-management"></a>Gestion de point de terminaison

Un catalogue des systèmes d’extrémité pris en charge et les périphériques d’interface (par exemple, casques) doit être disponible et mise à jour. Ce catalogue inclut une liste d’appareils approuvés qui ont été sélectionnés et validées dans le cadre des phases prévoir et Onboard. En règle générale, des appareils spécifiques sont sélectionnées pour chaque type de personnages dans votre organisation pour satisfaire les besoins des attributs de ce personnage. Tous les points de terminaison ont un cycle de vie, et que vous devez gérer les contrats fournisseurs, garantie, remplacement, distribution et réparer les stratégies associées à ces périphériques.

### <a name="endpoint-troubleshooting"></a>Résolution des problèmes de point de terminaison

Même si vous avez suivi les recommandations précédentes, les utilisateurs de votre organisation peuvent toujours exécuter des problèmes avec les équipes. Bien que le problème ne peut pas être avec le point de terminaison, les symptômes signalant le problème sont généralement exposées par le biais du client à l’utilisateur. Les conseils suivants sont conçu pour fournir les étapes générales que permettant de résoudre le problème ; Il n’est pas destiné à être un guide de dépannage complet. Les étapes sont fournies dans un ordre spécifique, mais ils ne doivent être suivies explicitement et peuvent ne pas être applicables, en fonction de la nature du problème.

1. **Valider le fonctionnement du service :** Le problème que rencontre peut-être un utilisateur peut être associé à un événement qui affecte les services itsdependent équipes. Dans un premier temps, nous vous recommandons de vérifier de qu'aucun problème de service active. Consultez [comment vérifier l’intégrité du service Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0). Pensez à vérifier le statut des services dépendants (par exemple, Exchange, SharePoint, OneDrive entreprise). Surveillance de l’intégrité du service est abordée plus en détail dans la section précédente, [surveiller l’intégrité de service](#monitor-service-health).

2. **Valider la connectivité client :** Problèmes de connectivité provoquent des fonctionnalités ou des problèmes de connexion dans les équipes. Nous vous recommandons de (en particulier pour des sites ou des emplacements) valider la connectivité au service. Vérifiez que les instructions suivantes [d’Office 365 URL et plages d’adresses IP](https://aka.ms/o365ips) sont suivie pour chaque site. Vous pouvez utiliser l' [Outil d’évaluation de réseau Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) pour effectuer un test de connectivité pour valider que les ports multimédias ont été ouverts correctement des capacités d’équipes. Étapes détaillées sur la façon d’effectuer les tests de connectivité sont fournies dans le Guide de [Préparation du réseau](upgrade-prepare-environment-prepare-network.md) .

3. **Vérifier la liste des problèmes connus :** Consultez la [liste des problèmes connus d’équipes](known-issues.md) pour déterminer si l’utilisateur a été affecté par un de ces problèmes. Suivez la procédure fournie (le cas échéant) pour résoudre le problème.

4. **Visitez le site de la Communauté Microsoft Teams :** La [Communauté des équipes Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) offre des espaces dédiés pour les équipes. La Communauté des équipes fournit une liste de discussion, des billets de blog et des annonces centrés sur les équipes. Vous pouvez publier une question ou rechercher des discussions précédentes pour les solutions à votre problème.

5. **Contactez le support technique de Microsoft :** Vous pouvez contacter le Support Microsoft pour les problèmes avec les équipes en ligne ou par téléphone. Pour plus d’informations, voir [Contact prend en charge pour les équipes Microsoft](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). Pour le Premier clients, prise en charge des demandes peuvent être lancées en suivant les conseils à [contactez le support technique pour Microsoft Teams (Premier clients)](https://support.microsoft.com/premier/contacts).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/selon les besoins

| Activité | Description | Cadence | Équipe affecté |
|---|---|---|---|
| Configuration requise du point de terminaison | Vérifiez que les équipes de point de terminaison continue pour répondre à tous les logiciels requis pour les équipes répertoriés dans [obtenir des clients pour les équipes Microsoft](get-clients.md). | Mois | |
| Pare-feu de point de terminaison | Mettre à jour les exclusions appropriées sur le pare-feu du point de terminaison en fonction des informations dans [Office 365 URL et plages d’adresses IP](https://aka.ms/o365ips). Votre fournisseur tiers auront des instructions spécifiques à la maintenance des exclusions. S’abonner à ce [flux RSS](https://support.office.com/o365ip/rss) pour être averti automatiquement des modifications. | Selon vos besoins | |
| Pilotes Wi-Fi | Tester et mettre à jour les pilotes Wi-Fi sur le PC. Valider les résultats à l’aide de CQD ([Guide Quality of Experience révision](https://aka.ms/qerguide)). | Selon vos besoins | |
| Gestion de point de terminaison | Gérer le catalogue de points de terminaison pris en charge et les périphériques d’interface (par exemple, casques). Gérer les contrats fournisseurs, garantie, distribution, remplacement et réparer les stratégies. | Mois | |
| Résolution des problèmes de point de terminaison | Résolution des problèmes de tâches peuvent inclure la vérification de la connectivité, consultation de la liste de problèmes connus, collecte des journaux, analyse et mise à niveau vers le Support de Microsoft ou des fournisseurs tiers. | Selon vos besoins | |

### <a name="references"></a>Références

[URL et plages d'adresses IP Office 365](https://aka.ms/o365ips)

[Obtenir des clients pour Microsoft Teams](get-clients.md)

[Communauté Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Problèmes connus concernant Microsoft Teams](known-issues.md)

[Vérifier l'intégrité du service pour Microsoft Teams](service-health.md)

[Contacter le support Office 365 pour les entreprises - Aide de l'administrateur](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

[Support Premier contact](https://support.microsoft.com/premier/contacts)

[Dépannage de la vidéo d’équipes](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Gestion des équipes

Une fois que le service Microsoft Teams a été déployé, vous devez effectuer plusieurs activités liées à l’administration. La plage des activités d’administrer le service et les utilisateurs individuels pour la planification de capacité et de mise en service des numéros de téléphone et de gestion des licences. Les sections suivantes traitent de certaines de ces tâches d’administration courantes.

### <a name="service-administration"></a>Administration du service

Le service d’équipes dispose de plusieurs paramètres qui peuvent être configurés au niveau du client.
Les modifications apportées aux paramètres client affectent tous les utilisateurs qui ont été activés pour les équipes. Pour obtenir une liste détaillée de ces paramètres, voir [fonctionnalités de gérer les équipes Microsoft dans votre organisation Office 365](enable-features-office-365.md).

### <a name="user-administration"></a>Administration des utilisateurs

Pour prendre en charge les utilisateurs, une organisation peut nécessiter un nombre quelconque de tâches connexes — les tâches spécifiques varient d’une organisation à l’autre. Enfin, ces tâches doivent être gérés par l’équipe de support qui a été assignée à ces tâches opérationnelles. Les tâches suivantes sont fréquemment requis pour prendre en charge les utilisateurs dans les équipes.

#### <a name="general-tasks"></a>Tâches générales

[Gérer l'accès des utilisateurs à Microsoft Teams](user-access.md)

### <a name="team-creation-optional"></a>Création de l’équipe (facultative)

Par défaut, tous les utilisateurs avec une boîte aux lettres dans Exchange Online disposent des autorisations pour créer des groupes d’Office 365 et, par conséquent, une équipe dans Microsoft Teams. Si vous souhaitez avoir un contrôle plus strict et [restreindre la création de nouvelles équipes](assign-roles-permissions.md#permissions-to-create-teams) (et la création de nouveaux groupes d’Office 365), vous pouvez déléguer des droits de gestion à un ensemble d’administrateurs et de création d’un groupe. Si votre organisation souhaite adopter cette option, voir la procédure décrite dans cet article pour permettre aux utilisateurs de soumettre des demandes sont traitées par une équipe affectée.

<!--ENDOFSECTION-->

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/selon les besoins

| Activité | Description | Cadence | Équipe affecté |
|---|---|---|---|
| Administration du service | Administration des paramètres des équipes au niveau du client. | Selon vos besoins | |
| Administration des utilisateurs | Administration des paramètres utilisateur et gestion des licences dans les équipes. | Selon vos besoins | |
| Gestion des licences | Planifier les besoins actuels et futurs pour les utilisateurs et en fonction de la consommation de licences (appel Plans et Communication crédits) grâce à l’état de [rapport d’utilisation PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) et [pools minutes PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) . | Toutes les semaines | |
| Gestion de numéros de téléphone | Gérer les numéros de téléphone disponibles pour la croissance future et de régler les niveaux de stock pour répondre aux besoins de votre organisation. | Toutes les semaines | |
| Création de l’équipe (facultative) | Processus de révision et les demandes de création d’équipe. | Selon vos besoins | |

<!--ENDOFSECTION-->
