---
title: Opérations pour Microsoft teams | Gestion des services | Supérieure
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dearbeen
description: Tâches et activités requises pour la gestion des services d’équipe, y compris la surveillance de l’état du service et l’évaluation et l’utilisation de la qualité et de l’utilisation du réseau
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d5f6614c076b212935908d8bb77973df5c3b867
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548532"
---
![Diagramme de parcours de mise à niveau, mettant l’accent sur le stade d’excellence opérationnel] (media/upgrade-banner-op-excellence.png "Étapes du voyage de la mise à niveau, avec mise en évidence de l’étape d’excellence opérationnelle")

Cet article fait partie de l’étape du fonctionnement de votre mise à niveau du fonctionnement de votre mise à niveau, qui commence dès que vous avez terminé la mise à niveau de Skype entreprise vers Teams.

# <a name="operate-your-service"></a>Exploiter votre service

Cet article fournit une vue d’ensemble de la configuration requise pour le fonctionnement des équipes avec succès après la mise à niveau. En opérant correctement vos services d’équipe, vous pouvez être sûr d’offrir une utilisation fiable et de grande qualité pour votre organisation.

## <a name="introduction-to-the-operations-guide"></a>Introduction au Guide des opérations

Le guide des opérations vous donne une vue d’ensemble de toutes les tâches et activités requises dans le cadre de la fonction de gestion des services de Microsoft Teams.

La gestion des services est un vaste sujet qui couvre les opérations quotidiennes du service Microsoft Teams après son déploiement et son activation pour les utilisateurs. Le service Teams englobe Microsoft Office 365 et les composants d'infrastructure déployés sur site (par exemple, la mise en réseau).

La notion de gestion des services n'est probablement pas un concept nouveau pour la plupart des organisations. Vous avez peut-être déjà implémenté des processus et des tâches associés à des services existants. Cela dit, vous pouvez probablement augmenter votre processus actuel lorsque vous planifiez la gestion de service dès aujourd’hui pour prendre en charge les équipes à l’avenir.

La gestion des services englobe toutes les activités et processus impliqués dans la gestion des équipes de bout en bout. Comme indiqué plus haut, certains composants de la gestion des services, l’infrastructure qui est le service 365 d’Office lui-même, sont responsables par Microsoft, alors que vous, le client, êtes responsable de vos utilisateurs pour gérer les différents aspects des équipes, le réseau ainsi que les points de terminaison que vous fournissez.

Les tâches et les activités de ce guide sont regroupées en huit catégories, comme illustré dans le schéma suivant. Chacune de ces catégories sera développée sur les sections suivantes.

![Diagramme illustrant une liste de catégories de tâches et d’activités] (media/operate-my-service-image1.png "Diagramme illustrant une liste de catégories de tâches et d’activités que la gestion de service pour teams comporte. Le diagramme montre également que la gestion des services est essentiellement une tâche client.")

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Déterminez comment les opérations seront implémentées pour les équipes.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Passez en revue le Guide de fonctionnement complet.</li><li>Implémentez une stratégie de fonctionnement qui s’adapte aux objectifs de votre organisation afin de garantir la qualité et la fiabilité des charges de travail de l’équipe.</li><li>Passez en revue le Guide de vérification de la qualité de l’utilisation.</li><li> Implémentez une stratégie d’opérations pour effectuer régulièrement des révisions de qualité d’utilisation afin de vous assurer que le déploiement de votre équipe fonctionne aux pointe.</li></ul></td></tr>
</table>

### <a name="operational-role-mapping"></a>Mappage des rôles opérationnels

Le planning que vous avez effectué pour les opérations lors de la phase enVision est essentiel, car les activités d’opérations commencent lorsque les premiers utilisateurs pilote sont activés. Ce Guide dresse la liste des activités et tâches qui doivent être effectuées sur une base quotidienne, hebdomadaire, mensuelle ou en cas de besoin pour gérer un déploiement d’équipes de grande qualité. Ce guide fournit des informations et des conseils pour effectuer ces activités et tâches critiques.

Un composant essentiel d’un déploiement réussi consiste à s’assurer que la planification que vous effectuez le plus rapidement dans le cadre de la phase enVision implique de déterminer qui sera responsable de l’exécution d’activités spécifiques. Une fois que vous avez choisi les tâches et les activités qui s’appliquent à votre déploiement, elles doivent être comprises et suivies par les groupes ou les personnes que vous leur attribuez.

Chaque équipe que vous identifiez doit revoir et accepter les tâches et les responsabilités identifiés et commencer la préparation. Il peut s’agir de la formation et de la disponibilité, de la mise à jour du plan de personnel ou de la possibilité de faire en sorte que les fournisseurs externes soient prêts à effectuer.

Les activités et rôles définis dans ce guide doivent être valides dans la plupart des cas, mais chaque déploiement d’équipes est unique. par conséquent, vous pouvez utiliser ce guide comme point de départ pour personnaliser les activités et les rôles par défaut en fonction de vos besoins.

Assurez-vous que chaque équipe responsable dispose d’une bonne compréhension des activités nécessaires à l’exécution du service. Il est essentiel que chaque équipe accepte et ferme ses responsabilités au sein de votre organisation avant le début du premier pilote.

Une fois qu’un contrat est en place, les équipes correspondantes doivent commencer à faire fonctionner leurs rôles.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td>
<td><ul><li>Utilisez ce document pour faciliter l’exercice du mappage de rôles opérationnels.</li><li>Rencontrez les équipes du support technique appropriées pour attribuer des noms à chaque élément dans la liste des activités requises.</li><li>Obtenir une acceptation ou une connexion sur les rôles qui vous sont attribués.</li><li>Assurez-vous que les équipes correspondantes disposent des ressources nécessaires pour effectuer les activités requises.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Dépendances des services teams

Microsoft teams réunit les technologies dans Office 365 pour proposer un Hub pour le travail en équipe. Par exemple:

- Azure Active Directory (Azure AD) fournit des services d’authentification et d’autorisation pour Teams.

- Exchange Online fournit des fonctionnalités avancées telles que la conservation légale et la découverte électronique.

- SharePoint Online vous permet de partager des fichiers dans des canaux, et OneDrive entreprise fournit un mécanisme de partage de fichiers au sein d’une conversation privée.

Les organisations peuvent également tirer parti d’investissements existants dans l’infrastructure locale. Par exemple, les comptes Active Directory locaux existants peuvent être utilisés pour l’authentification en tirant parti d’Azure AD Connect. Certaines versions d’Exchange Server peuvent être utilisées à la place d’Exchange Online.

Ces technologies s’associent pour fournir une suite de communications complète, collaborative et intelligente aux utilisateurs. Cette intégration étroite est un atout clé de teams, mais il est également nécessaire de gérer les services à l’échelle de ces technologies.

Ce guide décrit les principaux domaines du mise au point pour gérer le service Teams. C’est probablement parce que vous disposez de plans de gestion de service pour les technologies de support dont dépend Teams. Si ce n’est pas le cas, vous devez créer des plans de gestion de service appropriés pour ces composants de technologie (local et en ligne). Cela permet de garantir que vos utilisateurs apprécieront une connaissance de grande qualité et fiable de teams.

#### <a name="references"></a>Références

[Présentation de Microsoft Teams](teams-overview.md)

[Interaction entre Exchange et Microsoft Teams](exchange-teams-interact.md)

[Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams](sharepoint-onedrive-interact.md)

[Coexistence et interopérabilité de Microsoft teams et de Skype entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Activités du Guide des opérations

Les sections suivantes offrent une vue d’ensemble des activités requises pour le bon fonctionnement du service Microsoft Teams. Ils incluent des références à des outils, des informations contextuelles et du contenu supplémentaire qui vous aideront à comprendre les activités et à faciliter les initiatives de préparation.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Surveiller l’état du service

Il est important de bien comprendre le fonctionnement global du service Microsoft Teams, afin que vous puissiez avertir les autres personnes de votre organisation de tout événement affectant ce service. Comme décrit précédemment, teams dépend d’autres services Office 365 tels que Azure Active Directory, Exchange Online, SharePoint Online et OneDrive entreprise. Pour cette raison, il est également important de surveiller l’état des services dépendants.

Incorporez cette activité dans votre processus de gestion des incidents pour informer de manière proactive les utilisateurs, le support technique et vos équipes opérationnelles à se préparer pour gérer les escalades des utilisateurs.

Les sections suivantes décrivent les outils que vous pouvez utiliser pour surveiller les [incidents de service](https://technet.microsoft.com/library/office-365-service-health.aspx#Anchor_1) affectant le service équipes. Le tableau suivant récapitule les avantages de chaque outil et les situations dans lesquelles vous devriez utiliser chacun d’eux.

| Outil de surveillance | Avantages | Quand utiliser |
|---|---|---|
| Portail Office 365 | Disponible sur n’importe quel appareil doté d’un navigateur pris en charge. | À utiliser quand vous n’avez pas besoin de notifications en temps réel. |
| Application d’administration Office 365 | Fournit des notifications de transmission sur votre appareil mobile. | À utiliser quand vous avez besoin d’être informé des incidents de service lors de vos opérations de passage. |
| Centre de systèmes Microsoft | Intégration à Microsoft System Center. | À utiliser lorsque vous avez besoin d’une prise en charge des fonctionnalités d’analyse avancée et des notifications. |
| API de communication de service Office 365 | Accès par programmation à l’état du service Office 365. | À utiliser lorsque vous avez besoin d’une intégration avec un outil de surveillance tiers ou si vous voulez créer votre propre solution. |

> [!NOTE]
> Seules les personnes disposant du rôle administrateur **général** ou **administrateur de services** peuvent afficher l’état du service.

### <a name="monitoring-with-the-office-365-portal"></a>Surveiller avec le portail Office 365

Le [portail Office 365](https://portal.office.com/) fournit un [tableau de bord d’État du service](https://portal.office.com/adminportal/home#/servicehealth) , qui vous permet d’afficher l’état actuel du service teams en plus des services dépendants.

### <a name="monitoring-with-the-mobile-app"></a>Surveillance avec l’application mobile

L’application Office 365 admin est disponible sur Apple iOS, Android et Windows (PC et appareil mobile). L’application fournit aux administrateurs de services des informations sur l’état du service et les changements à venir. L’application prend en charge les notifications de transmission qui peuvent vous alerter presque immédiatement après la publication d’un avis. Cela vous permet de rester informé de l’état du service, de l’état d’intégrité et des changements à venir du service. La prise en charge de la notification rend son outil de contrôle recommandé aux administrateurs. Pour plus d’informations, consultez:

[Application mobile Office 365 admin](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Télécharger l’application mobile Office 365 admin](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Analyse à l’aide de Microsoft System Center

Microsoft System Center est une plate-forme de gestion intégrée qui vous permet de gérer les centres de connaissances, les appareils clients et les environnements informatiques Cloud hybrides. Les administrateurs d’Office 365 qui utilisent System Center peuvent désormais importer le pack d’administration Office 365, qui leur permet d’afficher toutes les communications de service dans Operations Manager dans System Center. Cet outil vous permet d’accéder à l’état de vos services abonnés, aux incidents de service actifs et résolus ainsi qu’aux communications de votre centre de messages (changements à venir). Pour plus d’informations, consultez le [billet de blog](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true)suivant.

Si vous utilisez System Center pour surveiller l’état du service Teams (et les services dépendants), vous pouvez personnaliser davantage le pack d’administration pour alerter ou informer des groupes ou des individus spécifiques qui ont été identifiés pour réagir aux incidents.
Ces groupes peuvent inclure les propriétaires de service, les support technique, les groupes de support de second niveau et de troisième niveau, ainsi que les responsables d’incident au sein de votre organisation.

### <a name="monitoring-for-advanced-scenarios"></a>Surveiller des scénarios avancés

Vous pouvez surveiller l’état du service et les changements à venir en tirant parti de l’API de communications du service Office 365 pour accéder à l’état du service Office 365 et aux modifications par programme. Utilisez cette API pour créer votre propre outil de surveillance ou connecter vos outils d’analyse existants aux communications du service Office 365, tout en simplifiant le contrôle de votre environnement. Pour plus d’informations, reportez-vous à la rubrique [développeurs Office 365 pour les entreprises](https://msdn.microsoft.com/library/jj984343(v=office.15).aspx).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidienne/hebdomadaire/mensuelle/selon les besoins

| Interactive | Description | Cadence | Équipe affectée |
|---|---|---|---|
| Surveiller l’état du service | Surveiller de manière proactive le fonctionnement du service Microsoft Teams, (et les services dépendants) à l’aide des outils disponibles. Les services dépendants sont les suivants: Exchange Online, SharePoint Online, OneDrive entreprise, Azure Active Directory. | Temps réel | |
| Notification d’incident | Informer les parties prenantes internes des événements affectant le service Teams. Les parties prenantes internes peuvent inclure des utilisateurs, du support technique et des gestionnaires d’incident. | Selon vos besoins | |

### <a name="references"></a>Références

[Comment vérifier l’état du service Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Vérifier l’état du service Microsoft Teams](service-health.md)

[État et continuité du service](https://technet.microsoft.com/library/office-365-service-health.aspx)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Gérer le changement d’organisation

Microsoft teams est un service basé sur le Cloud. C’est la possibilité de proposer de nouvelles fonctionnalités à un rythme rapide. Le fait d’innover et de proposer des avantages évidents pour les entreprises, mais ces modifications doivent être gérées de manière appropriée au sein de votre organisation afin d’éviter toute remise ou réaffectation de l’utilisateur à votre support technique.

Les mises à jour d’équipes sont transférées automatiquement à vos utilisateurs. Vos utilisateurs ont toujours accès au client et aux fonctionnalités les plus récents dans le service Teams. Il n’est pas possible de gérer le lancement des mises à jour de teams pour vos utilisateurs, c’est pourquoi il est essentiel de gérer le changement par le biais de programmes de communication, de formation et d’adoption efficaces. Si vos utilisateurs ont accès au changement, ont été informés des avantages et profitent des nouvelles fonctionnalités&mdash;qu’ils pourront utiliser pour s’adapter plus rapidement et nous préparer.

### <a name="monitoring-for-change"></a>Suivi des modifications

La première étape de la gestion des modifications consiste à surveiller les modifications planifiées pour Teams. Le meilleur moyen de surveiller ces modifications est la présentation de [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap)qui dresse la liste des fonctionnalités en cours de développement, qui sont déployées pour les clients ou qui ont été entièrement lancées. Vous pouvez effectuer des recherches sur des fonctionnalités spécifiques aux équipes à l’aide du filtre fourni ou télécharger la présentation dans un fichier Excel pour analyse approfondie. Pour chaque fonctionnalité, la procédure fournit une brève description, ainsi que la date de publication prévue.

Le [blog Microsoft teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)vous permet d’en savoir plus sur les meilleures pratiques, les tendances et les informations sur les mises à jour de produits Teams. Il est possible que les principales mises à jour apportées aux équipes soient annoncées ici. Vous pouvez également vous abonner au blog par le biais d’un flux RSS. Vous pouvez ensuite ajouter [le flux RSS](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) directement dans un canal d’équipe, de sorte que toutes les informations importantes soient transmises directement dans Teams.

Toutes les fonctionnalités qui sont disponibles sont décrites dans les [notes de publication de Microsoft teams](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de).
Vous trouverez ci-dessous la liste des fonctionnalités qui ont été publiées pour les appareils de bureau, le Web et les appareils mobiles. Le même ensemble de notes de publication sont également disponibles dans l’onglet **Nouveautés** de l' [aide](get-help-in-microsoft-teams.md).

Familiarisez-vous avec les ressources disponibles et assurez-vous d’affecter les propriétaires concernés pour contrôler les changements.

### <a name="planning-for-change"></a>Planification des modifications

Maintenant que vous connaissez les modifications à venir du service Teams, l’étape suivante consiste à préparer et planifier en conséquence. Évaluez chaque modification pour déterminer quelles modifications nécessitent une communication aux utilisateurs, des campagnes de sensibilisation, des formations pour les équipes de support technique ou des utilisateurs, ou des campagnes d’évaluation et d’adoption de fonctionnalités. Il s’agit du principal rôle d’une équipe de gestion des modifications au sein de votre organisation. Vous trouverez ci-dessous une collection d’exemples de tables susceptibles de vous aider à planifier la modification.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Fonctionnalité: enregistrement Cloud (date de publication: 2018 de janvier)

**Suivi général**

| Modification de la disponibilité | État | Remarques/étapes suivantes | Propriétaire |
|---|---|---|---|
| Examen légal | Terme | Cette fonctionnalité est une prérequis de l’intégration de l’équipe de formation. | Équipe de projet |

**Gestion des changements techniques**

| Modification de la disponibilité | État | Remarques/étapes suivantes | Propriétaire |
|---|---|---|---|
| Modification obligatoire | Oui | L’administrateur doit activer l’enregistrement pour les utilisateurs identifiés uniquement. | Équipe de support technique |
| Compatibilité technique achevée | Oui | | Équipe de support technique |
| | | | |

**Gestion du changement d’utilisateur**

| Modification de la disponibilité | État | Remarques/étapes suivantes | Propriétaire |
|---|---|---|---|
| Impact sur les utilisateurs | Bas | | |
| Disponibilité requise pour l’utilisateur | Oui | | |
| Communications prêtes | Non | Le message de communication a été brouillon et en attente de révision. | Équipe de communication |
| Formation prête | Oui | La formation utilisera la vidéo Microsoft existante. | Équipe de formation |

**Suivi d’État**

| Modification de la disponibilité | État | Remarques/étapes suivantes | Propriétaire |
|---|---|---|---|
| État de la publication | en cours | Examen en attente par le commanditaire de la direction. | Équipe de gestion des changements |
| Déconnexion | | | |
| Date de publication | | | |

Pour plus d’informations sur la planification de la gestion des modifications avec Teams, voir [créer une stratégie de gestion des modifications pour Microsoft teams](change-management-strategy.md).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidienne/hebdomadaire/mensuelle/selon les besoins

| Interactive| Description| Cadence| Équipe affectée |
|---|---|---|---|
| Surveiller le changement| Surveiller les prochains changements apportés au service Microsoft Teams.| Jour||
| Planification des modifications| Évaluez et planifiez de nouvelles fonctionnalités, notamment des plans de communication, des campagnes de sensibilisation et une formation.| Selon vos besoins ||
| Compatibilité utilisateur| Exécuter des campagnes de communication, de sensibilisation ou de formation ciblées pour garantir que les utilisateurs soient prêts pour le changement à venir.| Selon vos besoins ||
| Prise en charge de l’équipe | Effectuez des campagnes de communication, de sensibilisation ou de formation ciblées pour vous assurer que l’équipe de support technique est prête. Les équipes de support technique peuvent inclure l’équipe «gant blanc», le support technique, le support de niveau 2 ou 3, les partenaires externes, etc. | Selon vos besoins ||

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Evaluer l’utilisation des équipes

Après le début du pilote initial, il est essentiel de définir une cadence normale pour mesurer l’utilisation réelle des équipes. Cela permet à votre organisation d’accéder à des informations sur la façon dont l’utilisation réelle s’aligne sur l’utilisation que vous avez prévue lors de la phase enVision. Même si cette section porte sur l’utilisation des équipes, cela devrait faire partie d’un effort plus large pour mesurer et évaluer l’utilisation globale d’Office 365.

La vérification de l’utilisation du moment du déploiement vous donne accès aux éléments suivants:

- Vérifiez si les utilisateurs utilisent Teams.

- Identifiez les problèmes potentiels liés à l’adoption avant de créer des problèmes importants au sein de l’organisation.

- Comprenez s’il existe des différences entre les exigences de la phase enVision et l’utilisation réelle.

Si l’utilisation ne correspond pas à ce que vous attendez, cela peut être dû à un problème de déploiement, ou le plan d’adoption ne s’exécute pas correctement ou tout autre problème. En fonction de la raison pour laquelle l’utilisation est faible, l’administrateur du service doit collaborer avec les équipes associées pour vous aider à supprimer les barrières d’utilisation.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Mesure de l’utilisation avec le centre d’administration Microsoft 365

Les données d’utilisation de teams sont disponibles dans le tableau de bord de création de rapports. Les données d’utilisation de teams se trouvent dans trois rapports différents. Le premier rapport offre une vue d’ensemble illustrant la façon dont les utilisateurs communiquent et collaborent en utilisant les différents services dans Office 365. Ce rapport est disponible ici: [rapport d’utilisateurs actifs d’Office 365](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Les deux autres rapports sont spécifiques aux équipes et fournissent des informations supplémentaires sur l’utilisation des équipes du point de vue de l’utilisateur et de l’appareil. Les deux rapports sont accessibles à l’adresse suivante:

[Rapport d’utilisation des périphériques de Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Rapport d’activité des utilisateurs de Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>Autorisations requises

Les rapports d’utilisation du centre d’administration sont accessibles aux personnes qui ont été affectées d’un rôle d' **administrateur général** ou d’un rôle d’administrateur spécifique au produit (**administrateur Exchange**, **administrateur Skype entreprise**, **SharePoint administrateur**).

De plus, le rôle de **lecteur de rapports** est disponible pour les utilisateurs qui ont besoin d’accéder aux rapports, mais n’effectue pas de tâches qui nécessitent des autorisations au niveau de l’administrateur. Vous attribuez ce rôle pour fournir des rapports d’utilisation à toute personne qui est une partie prenante, surveiller et conduire une adoption. Pour plus d’informations sur les différents rôles disponibles, voir [à propos des rôles d’administrateur Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="assessing-usage"></a>Évaluation de l’utilisation

Après avoir utilisé le tableau de bord de création de rapports pour mesurer l’utilisation, il est important de comparer l’utilisation mesurée aux indicateurs de réussite (KSIs) que vous avez définis lors de la phase enVision du projet. Vous pouvez définir un KSI qui peut être défini comme utilisation active ou qui est indirectement lié à une utilisation active.

Il est important d’identifier les variations éventuelles entre l’utilisation réelle et prévue avant de reprendre le déploiement pour les sites ou les utilisateurs supplémentaires. Vous identifierez probablement les connaissances organisationnelles dans le cadre de cette activité que vous pouvez utiliser pour vous assurer que le lot de sites ou d’utilisateurs suivant ne rencontre pas les mêmes problèmes.

Tout d’abord, identifiez s’il s’agit d’une adoption ou d’un problème technique. Commencez par examiner les éléments ci-dessous afin de déterminer où se trouve le problème.

1. Confirmez la qualité en effectuant un [examen qualité de l’expertise](upgrade-monitor-quality.md).

2. Collaborer avec l’équipe du support technique pour vérifier qu’il n’y a aucun problème technique de tendance qui empêche les utilisateurs d’accéder au service ou de les utiliser. S’il existe des tendances de problèmes, utilisez la section [résolution des problèmes de point de terminaison](#endpoint-troubleshooting) , plus loin dans cet article, pour essayer de résoudre le problème avant d’être pris en charge.

3. Collaborer avec l’équipe de formation et d’adoption pour collecter des commentaires directs auprès des utilisateurs (voir évaluer les commentaires des [utilisateurs](#assess-user-sentiment) plus loin dans cet article) et vérifier l’efficacité des activités de sensibilisation et d’adoption.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidienne/hebdomadaire/mensuelle/selon les besoins

| Interactive | Description | Cadence | Équipe affectée |
|---|---|---|---|
| Mesurer l’utilisation (phase d’activation) | Mesurez et évaluez l’utilisation des équipes à mesure que les sites continuent à être intégrés lors de la phase d’activation. Résoudre les problèmes d’utilisation d’adresse selon les besoins. | Toutes les semaines | |
| Mesurer l’utilisation | Mesurez et évaluez l’utilisation des équipes lors de la phase de valeur de l’unité (une fois le déploiement terminé). Résoudre les problèmes d’utilisation d’adresse selon les besoins. | Bihebdomadaire | |
| (phase d’une valeur d’unité) | | | |
| Plan de mise à jour d’adoption | Mettez à jour votre plan d’adoption en fonction de la façon dont l’utilisation mesurée est comparée aux cibles de votre planification. | Selon vos besoins | |

### <a name="references"></a>Références

[À propos du centre d’administration Microsoft 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Rapports d’activité dans le centre d’administration Microsoft 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Évaluer l’sentiment des utilisateurs

Comprendre que l’utilisateur peut agir en tant qu’indicateur clé pour vous permettre de déterminer le succès de votre déploiement d’équipes. Les commentaires des utilisateurs peuvent favoriser le changement de votre organisation. Il peut s’agir de modifications apportées à vos plans de communication, de programmes de formation ou de la façon dont vous pouvez fournir l’assistance à vos utilisateurs.

Il est important de bien vouloir nous faire part de vos commentaires tout au long du cycle de vie du projet. Utilisez les instructions suivantes pour déterminer l’intervalle pendant lequel votre organisation va chercher des commentaires:

- **Début du projet**: en évaluant l’opinion des utilisateurs au début du projet, vous pouvez obtenir une vue d’ensemble de la façon dont vos utilisateurs s’en soucient.

- **Après les principales étapes**: en collectant des commentaires tout au long du cycle de vie du projet, vous pouvez évaluer les utilisateurs de manière continue et apporter des modifications selon vos besoins. Cette fonction est particulièrement utile après les principales étapes.

- **Conclusion du projet**: en évaluant le sentiment de l’utilisateur à la fin d’un projet, vous serez en mesure de faire votre travail et à l’endroit où le travail doit avoir lieu et vous pourrez comparer les résultats à l’enquête précédente.

- En **cours**: continuez à mesurer indéfiniment les utilisateurs. Les modifications apportées par l’utilisateur peuvent être dues aux modifications de l’environnement de votre organisation ou aux modifications du service Teams. En apportant des informations sur les utilisateurs à intervalles réguliers, vous pouvez comprendre le fonctionnement de vos équipes de gestion des services et la façon dont votre organisation répond aux modifications apportées au service Teams.

L’utilisation de diverses méthodes peut être évaluée par l’utilisateur. Il peut s’agir d’enquêtes par e-mail, d’entretiens en personne ou de type téléphone ou simplement de créer un canal de commentaires dans teams ou Yammer. Pour plus d’informations, consultez [meilleures pratiques en matière de méthodes de commentaires des utilisateurs dans Microsoft teams](best-practices-feedback.md).

Vous pouvez également utiliser une approche industrywide pour évaluer les sentiments d’utilisation de l’utilisateur, qui est décrit dans la section suivante.

### <a name="nps"></a>IGNOR

Le score du promoteur net (NPS) est une mesure de loyauté du client industrywide et une bonne approche à utiliser pour évaluer l’sentiment des utilisateurs. Le mode NPS peut être calculé en demandant deux questions: «dans quelle mesure êtes-vous susceptible de recommander des équipes à un collègue?», suivi de la question libre

NPS est un index allant de-100 à 100 qui mesure la volonté d’un client de recommander le produit ou le service d’une entreprise. NPS repose sur une enquête anonyme qui est remise aux utilisateurs par le biais de la messagerie électronique ou d’un autre moyen électronique. NPS mesure la loyauté entre un fournisseur et un consommateur. Il s’agit d’une seule question, qui demande aux utilisateurs d’évaluer leur connaissance de 1 à 10, avec la possibilité de fournir des commentaires supplémentaires. Les utilisateurs sont alors classés en fonction des évaluations suivantes:

- 9 ou 10 est le promoteur: passionnés de promotion de votre service et de votre carburant.

- 7 ou 8 sont passifs: satisfait mais inenthousiaste, vulnérable à un autre service ou offre.

- Entre 1 et 6: les détenteurs qui peuvent endommager votre service et entraver la croissance.

![Diagramme illustrant l’échelle NPS] (media/operate-my-service-image2.png "Ce diagramme montre l’échelle NPS. Il indique que les rangs de 0 à 6 sont des tracteurs de 0 à 6 sont passifs et les promoteurs 9 à 10.")

Même si le numéro NPS de base est utile, vous obtiendrez la plus grande valeur de l’analyse des commentaires des utilisateurs. Ils vous aideront à comprendre la raison pour laquelle l’utilisateur serait (ou aurait) recommander des équipes. Ces commentaires peuvent fournir des commentaires intéressants pour aider les équipes de gestion de projet ou de service à comprendre les ajustements nécessaires pour fournir un service qualité.

Pour fournir des enquêtes NPS à votre organisation, vous pouvez tirer parti de votre outil d’enquête en ligne favori.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidienne/hebdomadaire/mensuelle/au besoin

| Interactive | Description | Cadence | Équipe affectée |
|---|---|---|---|
| Évaluer l’sentiment des utilisateurs | Capturez et évaluez le sentiment des utilisateurs en utilisant des enquêtes ou des entretiens ou via un canal de commentaires dans teams ou Yammer. | Selon vos besoins | |
| Mettre à jour les plans d’adoption | Modification de votre organisation sur la base des commentaires des utilisateurs; Il peut s’agir de modifications apportées à vos plans de communication, programmes de formation ou la manière dont vous pouvez fournir l’assistance à vos utilisateurs. | Selon vos besoins | |

### <a name="references"></a>Références

[Score du promoteur net](https://en.wikipedia.org/wiki/Net_Promoter)

[Utilisation de Yammer pour recueillir les commentaires](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Recommandations en matière de commentaires des utilisateurs](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Gestion de la qualité du réseau

De nombreux éléments de planification principaux s’imvoient à l’optimisation, au dimensionnement à droite et à la correction de votre infrastructure réseau pour garantir un chemin d’accès efficace et de haute qualité au service Microsoft Teams. Les tâches de planification et les exigences sont décrites dans nos recommandations en matière de [disponibilité du réseau](upgrade-prepare-environment-prepare-network.md) . Les réseaux évoluent souvent dans le temps en raison de mises à niveau, d’extensions ou d’autres exigences métiers. Il est important de tenir compte de vos exigences relatives aux équipes dans les activités de planification de votre réseau.

Bien que la planification du réseau soit un aspect essentiel du déploiement d’équipes, il est également important de veiller à ce que le réseau reste sain et reste actif, en fonction de l’évolution des besoins métiers ou techniques.

Pour garantir l’état de votre réseau, plusieurs activités d’opérations doivent être effectuées à intervalles réguliers.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidienne/hebdomadaire/mensuelle/selon les besoins

| Interactive | Description | Cadence | Équipe affectée |
|---|---|---|---|
| Surveiller les adresses IP et IPs Office 365 | Surveiller les modifications apportées aux [URL et plages d’adresses IP d’Office 365](https://aka.ms/o365ips) à l’aide du [flux RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) fourni et lancer une demande de modification aux groupes de réseaux applicables. | Jour | |
| Mise à jour du réseau en fonction des modifications apportées aux URL et adresses IP dans Office 365 | Effectuez des mises à jour des composants réseau applicables (pare-feu, serveurs proxy, VPN, pare-feu côté client, etc.) pour répercuter les modifications apportées aux [URL et plages d’adresses IP d’Office 365](https://aka.ms/o365ips). | Selon vos besoins | |
| Fournir des données de bâtiment | Fournir des informations de sous-réseau mises à jour au spécialiste de qualité (ou les parties prenantes en considération) pour s’assurer que les [définitions de bâtiment dans bord](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) sont tenues à jour; | Selon vos besoins | |
| Implémenter la modification | Implémenter les modifications sur le réseau pour prendre en charge le changement d’impératif des équipes et les exigences techniques. Les éléments réseau peuvent être:<ul><li>Pare-feu</li><li>VPN</li><li>Réseaux filaires et Wi-Fi</li><li>Connectivité Internet et ExpressRoute</li><li>DNS</li></ul> | Selon vos besoins | |
| Surveillance et signalement du réseau | Surveiller la fin du réseau en fonction de la disponibilité, de l’utilisation et des tendances en fonction de vos outils de gestion du réseau tiers et des fonctionnalités de création de rapports disponibles auprès de vos fournisseurs réseau. Utiliser des données de tendance pour la planification de la capacité réseau. | Quotidienne, hebdomadaire, mensuelle | |
| Planification de capacité | Collaborez avec les propriétaires de service teams pour mieux comprendre les exigences commerciales et techniques qui peuvent conduire à des changements de capacité supplémentaires. Tirez parti des résultats du [Planificateur de réseaux](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) pour vous assurer qu’une bande passante suffisante est disponible pour Microsoft Teams. | Selon vos besoins | |
| Résolution des problèmes de réseau et de mise à jour | Aidez les techniciens du support technique Teams, les propriétaires de services et les principales parties prenantes à résoudre les problèmes liés à la connectivité, la fiabilité ou la qualité des équipes. Les éléments réseau peuvent être:<ul><li>Pare-feu</li><li>VPN</li><li>Réseaux filaires et Wi-Fi</li><li>Connectivité Internet et ExpressRoute</li><li>DNS</li></ul> | Selon vos besoins | |
| Reprise après sinistre et test de haute disponibilité | Effectuez des tests de haute disponibilité et de récupération d’urgence normaux sur l’infrastructure réseau pour vérifier qu’il répond aux objectifs de niveau de service ou aux contrats de niveau de service (SLA) mentionnés pour le service équipes. | Mois | |

### <a name="references"></a>Références

[Planificateur de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)

[URL et plages d’adresses IP Office 365](https://aka.ms/o365ips)

[Création du schéma de données](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Evaluer et garantir la qualité

Toutes les organisations ont besoin d’un groupe ou d’une personne pour la qualité. Il s'agit du rôle le plus important dans la gestion des services. Le rôle d’expert qualité est attribué à une personne ou à un groupe qui s’est engagé sur l’interface de ses utilisateurs.
Ce rôle exige les compétences nécessaires pour cerner les tendances de l'environnement et le parrainage pour travailler avec d'autres équipes afin d'orienter les mesures correctives. En général, le meilleur candidat au rôle de Champion Qualité est le responsable du service clientèle. Selon la taille et la complexité de l’organisation, il peut s’agir d’une personne ou d’un groupe ayant une passion pour garantir une meilleure qualité de l’utilisation de l’utilisateur.

Le spécialiste qualité tire parti des outils et processus documentés existants, tels que le tableau de bord de qualité des appels (bord) et le Guide de la qualité de l’utilisation, pour contrôler l’utilisation de l’utilisateur, identifier les tendances en matière de qualité et piloter la correction le cas échéant.
Le spécialiste de la qualité doit collaborer avec les équipes respectives pour diriger les actions de correction et signaler à une Commission d’orientation la progression et les problèmes en cours.

Le [Guide de vérification de la qualité de l’utilisation](https://aka.ms/qerguide) inclut des activités qui évaluent et fournissent des recommandations en matière de correction dans des domaines clés ayant un impact élevé sur l’amélioration de l’utilisation de l’utilisateur. Les recommandations fournies dans le Guide de vérification de la qualité de l’utilisation de bord Online en tant qu’outil principal permettent de rapporter et d’examiner chaque zone, en ayant une focalisation sur le son pour optimiser l’adoption et l’impact. Toutes les optimisations apportées au réseau pour améliorer l'expérience audio se traduiront aussi directement par des améliorations dans le partage de la vidéo et du bureau.

Nous vous conseillons vivement de le nommer rapidement. Après avoir été désignée, elle doit commencer à se familiariser avec le contenu du Guide de vérification de la qualité de l’utilisation et des supports de cours associés.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidienne/hebdomadaire/mensuelle/selon les besoins

| Interactive | Description | Cadence | Équipe affectée |
|---|---|---|---|
| Nommer et former un ou des champions de la qualité | Désignation et formation d’un spécialiste qualité. | Selon vos besoins | |
| Effectuer des révisions de qualité d’expérimentation (QERs) | Effectuer un QER pour identifier les tendances en matière de qualité et de fiabilité, revoir par rapport aux cibles définies et signaler les principales parties prenantes au sein de l’organisation. | Par mois (hebdomadaire lors des déploiements) | |
| Correction de l’entraînement | Coordonner les efforts de correction au sein de l’organisation en fonction des évaluations et conclusions de QER. | Selon vos besoins | |
| Mettre à jour les données de bâtiment dans bord | Mettre à jour ou ajouter de nouvelles définitions de bâtiment dans bord lorsque des modifications sont apportées au réseau (voir [Télécharger des informations de bâtiment](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | Selon vos besoins | |
| Remplir le rôle de défenseur | Responsabilité de bout en bout de la qualité au sein de l’organisation. Cela comprend les éléments suivants:<ul><li>Assurez-vous que le QER est mené régulièrement.</li><li>Signalez aux principales parties prenantes l’état de qualité.</li><li>Vérifiez que les définitions des données de bâtiment sont à jour.</li><li>Coordonnez les efforts de correction au sein de l’Organisation pour garantir aux utilisateurs une meilleure qualité de l’équipe.</li></ul> | Jour | |

### <a name="references"></a>Références

[Apprendre le CQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos)

[Télécharger les informations de bâtiment](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[Guide d’examen de l’expérience de qualité](https://aka.ms/qerguide)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Gérer les points de terminaison

Les points de terminaison Microsoft teams peuvent être définis comme n’importe quel appareil mobile, de Mac, de tablette ou mobile (ou tout autre appareil) exécutant le client Teams. Le *point de terminaison* du terme n’englobe pas uniquement le périphérique lui-même, mais le mode de connexion de l’utilisateur à l’appareil (par exemple, à l’aide du micro ou du haut-parleur intégré du périphérique, de confortables ou d’un casque optimisé). Après le déploiement, les points de terminaison ne doivent pas être oubliés. Les points de terminaison d’équipes nécessitent des soins et des maintenances en cours. Les sections suivantes décrivent des zones spécifiques sur lesquelles vous pouvez vous concentrer.

### <a name="endpoint-requirements"></a>Exigences relatives aux points de terminaison

L’un des principaux avantages de teams est que le client est automatiquement mis à jour. Les clients sur PC et Mac sont mis à jour à l'aide d'un processus en arrière-plan qui vérifie les nouvelles versions et télécharge le nouveau client lorsque l'application est inactive. Les applications mobiles teams sont conservées par le biais de leurs magasins d’applications respectifs.

La configuration minimale requise pour le client teams est strictement requise. Ces exigences peuvent changer dans le temps et par conséquent, il est important de les surveiller pour les modifications. Par exemple, le client teams a une version iOS minimum. Si le client utilise un navigateur Internet, le navigateur doit également être maintenu. Pour plus d’informations sur la prise en charge des [clients de Microsoft teams](get-clients.md), consultez la liste des plateformes prises en charge.

### <a name="endpoint-firewalls"></a>Pare-feu des points de terminaison

Les pare-feu côté client peuvent avoir un impact significatif sur l'expérience utilisateur.
Les pare-feu côté client peuvent influer sur la qualité des appels et même empêcher l’établissement d’un appel. Une fois les exclusions appropriées sur le pare-feu client configurées, elles doivent être mises à jour en fonction des informations contenues dans les [URL et plages d’adresses IP d’Office 365](https://aka.ms/o365ips). Votre fournisseur tiers disposera d’instructions spécifiques pour la mise à jour des exclusions.

### <a name="wi-fi-drivers"></a>Pilotes Wi-Fi

Les pilotes Wi-Fi peuvent poser problème. Par exemple, un pilote peut présenter des comportements d’itinérance très agressives entre des points d’accès qui peuvent provoquer un changement de points d’accès inutiles en entraînant une mauvaise qualité d’appel. Un pilote Wi-Fi incorrect peut être détecté par le biais d’un examen de qualité de l’utilisation (voir le guide sur la [qualité de l’utilisation](https://aka.ms/qerguide) pour plus d’informations). Il est essentiel de mettre en œuvre un processus piloté par la qualité qui analyse les nouveaux pilotes Wi-Fi et vérifie qu’ils sont testés avant d’être déployés dans la population des utilisateurs généraux.

### <a name="endpoint-management"></a>Gestion des points de terminaison

Un catalogue des points de terminaison et des appareils d’interface pris en charge (par exemple, des casques) devrait être disponible et entretenu. Ce catalogue inclut une liste des appareils approuvés sélectionnés et validés dans le cadre des phases enVision et Onboard. En règle générale, des périphériques spécifiques sont sélectionnés pour chaque type de personnage de votre organisation afin de répondre aux besoins des attributs de ce personnage. Tous les points de terminaison disposent d’un cycle de vie et vous devez gérer les contrats de contrat, de garantie, de remplacement, de distribution et de réparation associés à ces périphériques.

### <a name="endpoint-troubleshooting"></a>Résolution des problèmes de point de terminaison

Même si vous avez suivi les instructions ci-dessus, les utilisateurs de votre organisation peuvent rencontrer des problèmes avec Teams. Même si le problème provient peut-être de l’un des points de terminaison, les symptômes du problème sont généralement recherchés par l’utilisateur dans le client. Les recommandations suivantes sont destinées à vous fournir des étapes générales à suivre pour résoudre le problème. il ne s’agit pas d’un guide de dépannage complet. Les étapes sont fournies dans un ordre spécifique, mais elles ne doivent pas être suivies explicitement et peuvent ne pas être applicables, en fonction de la nature du problème.

1. **Valider l’état du service:** Le problème auquel un utilisateur peut être confronté peut être lié à un événement qui a un impact négatif sur le service teams ou les services itsdependent. Pour commencer, il est recommandé de vérifier qu’il n’y a pas de problème de service actif. Découvrez [Comment vérifier l’état du service Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0). N’oubliez pas de vérifier l’état des services dépendants (par exemple, Exchange, SharePoint, OneDrive entreprise). La surveillance de l’état du service est décrite plus en détail dans la section précédente, [surveiller l’état du service](#monitor-service-health).

2. **Valider la connectivité du client:** Les problèmes de connectivité entraînent des fonctionnalités ou des problèmes de connexion dans Teams. Nous vous conseillons de valider la connectivité au service (en particulier pour les nouveaux sites et emplacements). Assurez-vous que les instructions d' [URL et de plages d’adresses IP d’Office 365](https://aka.ms/o365ips) suivantes sont suivies pour chaque site. Vous pouvez tirer parti de l' [outil d’évaluation du réseau Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) pour effectuer un test de connectivité afin de vérifier que les ports multimédias ont été ouverts correctement pour les fonctionnalités d’équipe. Les étapes détaillées d’exécution des tests de connectivité sont fournies dans les recommandations relatives à la [préparation du réseau](upgrade-prepare-environment-prepare-network.md) .

3. **Consultez la liste des problèmes connus:** Consultez la [liste des problèmes connus de](known-issues.md) Microsoft teams pour déterminer si l’utilisateur a été lésé par l’un de ces problèmes. Pour résoudre le problème, suivez la solution de contournement fournie (le cas échéant).

4. **Visitez la communauté Microsoft teams:** La [communauté Microsoft teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) propose des espaces dédiés pour Teams. La communauté équipes fournit une liste de discussion, des billets de blog et des annonces centrées sur les équipes. Vous pouvez publier une question ou effectuer une recherche dans les discussions précédentes pour trouver des solutions à votre problème.

5. **Contacter le support Microsoft:** Vous pouvez contacter le support technique de Microsoft pour plus d’problèmes avec teams Online ou par téléphone. Pour plus d’informations, consultez [contacter le support technique pour les produits pour les entreprises](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json). Pour les clients premier, des demandes d’assistance peuvent être entamées en suivant les instructions de la rubrique [contacter le support technique de Microsoft Teams (clients de premier plan)](https://support.microsoft.com/premier/contacts).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidienne/hebdomadaire/mensuelle/selon les besoins

| Interactive | Description | Cadence | Équipe affectée |
|---|---|---|---|
| Exigences relatives aux points de terminaison | Assurez-vous que le point de terminaison teams continue de respecter toutes les configurations logicielles requises pour les équipes répertoriées dans la liste [obtenir des clients pour Microsoft teams](get-clients.md). | Mois | |
| Pare-feu des points de terminaison | Conservez les exclusions appropriées sur le pare-feu du point de terminaison en fonction des informations contenues dans les [URL et plages d’adresses IP Office 365](https://aka.ms/o365ips). Votre fournisseur tiers disposera d’instructions spécifiques pour vous permettre de gérer les exclusions. Abonnez-vous au [flux RSS](https://support.office.com/o365ip/rss) pour être informé automatiquement des modifications. | Selon vos besoins | |
| Pilotes Wi-Fi | Testez et mettez à jour les pilotes Wi-Fi sur le PC. Validez les résultats à l’aide de bord ([Quality of performance Review Guide](https://aka.ms/qerguide)). | Selon vos besoins | |
| Gestion des points de terminaison | Tenir à jour le catalogue des points de terminaison et des appareils d’interface pris en charge (comme les casques). Gestion des contrats de fournisseur, de garantie, de distribution, de remplacement et de réparation. | Mois | |
| Résolution des problèmes de point de terminaison | Les tâches de dépannage permettent de vérifier la connectivité, de consulter la liste des problèmes connus, de collecter, d’analyser et de réaffectation de journaux au support Microsoft ou aux fournisseurs tiers. | Selon vos besoins | |

### <a name="references"></a>Références

[URL et plages d’adresses IP Office 365](https://aka.ms/o365ips)

[Obtenir des clients pour Microsoft Teams](get-clients.md)

[Communauté Microsoft teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Problèmes connus concernant Microsoft Teams](known-issues.md)

[Vérifier l’état du service Microsoft Teams](service-health.md)

[Contacter le support relatif aux produits d’entreprises- Aide de l’administrateur](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

[Contacter le support premier](https://support.microsoft.com/premier/contacts)

[Résolution des problèmes vidéo dans teams](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Gérer Teams

Après le déploiement du service Microsoft Teams, vous devez effectuer plusieurs activités concernant son administration. La plage activités de l’administration du service et des utilisateurs individuels à la planification de la capacité et aux numéros de licence et aux numéros de téléphone. Les sections suivantes décrivent quelques-unes des tâches d’administration courantes.

### <a name="service-administration"></a>Administration des services

Le service équipes dispose de plusieurs paramètres qui peuvent être configurés à l’échelle du client.
Les modifications apportées aux paramètres de locataire affectent tous les utilisateurs qui ont été activés pour Teams. Pour obtenir une liste détaillée de ces paramètres, voir [gérer les paramètres de Microsoft teams pour votre organisation](enable-features-office-365.md).

### <a name="user-administration"></a>Administration des utilisateurs

Pour la prise en charge des utilisateurs, une organisation peut nécessiter un certain nombre de tâches associées: les tâches spécifiques varient d’une organisation à la suivante. En fin de compte, ces tâches doivent être gérées par une équipe de support technique ayant reçu ces fonctions opérationnelles. Les tâches suivantes sont généralement nécessaires pour prendre en charge les utilisateurs dans Teams.

#### <a name="general-tasks"></a>Tâches générales

[Gérer l’accès des utilisateurs à Microsoft Teams](user-access.md)

### <a name="team-creation-optional"></a>Création d’équipe (facultatif)

Par défaut, tous les utilisateurs disposant d’une boîte aux lettres dans Exchange Online disposent des autorisations nécessaires pour créer des groupes Office 365 et, par conséquent, une équipe Microsoft Teams. Si vous souhaitez disposer d’un contrôle plus étroit et [limiter la création de nouvelles équipes](assign-roles-permissions.md#permissions-to-create-teams) (et donc la création de nouveaux groupes Office 365), vous pouvez déléguer les droits de création et de gestion de groupes à un ensemble d’administrateurs. Si votre organisation veut poursuivre cette option, consultez la procédure décrite dans cet article pour permettre aux utilisateurs d’effectuer des demandes traitées par une équipe affectée.

<!--ENDOFSECTION-->

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidienne/hebdomadaire/mensuelle/selon les besoins

| Interactive | Description | Cadence | Équipe affectée |
|---|---|---|---|
| Administration des services | Administration des paramètres d’équipes à l’échelle du client. | Selon vos besoins | |
| Administration des utilisateurs | Administration des paramètres utilisateur et des licences dans Teams. | Selon vos besoins | |
| Gestion des licences | Planifiez des besoins actuels et futurs pour la gestion des licences utilisateur et de la consommation (appels d’offres et de communications) en tirant parti du rapport sur l' [utilisation RTC](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) et du rapport de pools de [minutes RTC](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) . | Toutes les semaines | |
| Gestion des numéros de téléphone | Gérez les numéros de téléphone disponibles pour une croissance future et ajustez les niveaux d’inventaire pour répondre aux besoins de votre organisation. | Toutes les semaines | |
| Création d’équipe (facultatif) | Réviser et traiter les demandes de création d’équipe. | Selon vos besoins | |

<!--ENDOFSECTION-->
