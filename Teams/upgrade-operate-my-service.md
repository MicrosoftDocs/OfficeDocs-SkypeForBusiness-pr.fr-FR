---
title: Opérations pour Microsoft Teams| | de gestion des services Qualité
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Tâches et activités requises pour Teams la gestion des services, notamment la surveillance de l’intégrité du service, l’évaluation et la garantie de la qualité et de l’utilisation du réseau
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 925ab3c7ab6889651e9e66e0b38266f7dbe17e7a
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823233"
---
# <a name="operate-your-service"></a>Exploiter votre service

![Diagramme du parcours de mise à niveau, mettant l’accent sur l’étape d’excellence opérationnelle.](media/upgrade-banner-op-excellence.png "Étapes du parcours de mise à niveau, en mettant l’accent sur la phase d’excellence opérationnelle")

Cet article fait partie de l’étape d’excellence opérationnelle de votre parcours de mise à niveau, qui commence dès que vous avez terminé votre mise à niveau de Skype Entreprise à Teams.

Cet article fournit une vue d’ensemble des conditions requises pour le bon fonctionnement des Teams pour votre organisation après la mise à niveau. En exécutant correctement vos services Teams, vous pouvez être sûr de fournir une expérience fiable et de haute qualité à votre organisation.

## <a name="introduction-to-the-operations-guide"></a>Introduction au Guide des opérations

Le Guide des opérations vous donne une vue d’ensemble de toutes les tâches et activités requises dans le cadre de la fonction de gestion des services pour Microsoft Teams.

La gestion des services est un vaste sujet qui couvre les opérations quotidiennes du service Microsoft Teams après son déploiement et son activation pour les utilisateurs. Le service Teams englobe Microsoft 365 ou Office 365 et les composants d’infrastructure déployés localement (par exemple, la mise en réseau).

La notion de gestion des services n'est probablement pas un concept nouveau pour la plupart des organisations. Vous avez peut-être déjà implémenté des processus et des tâches associés à des services existants. Cela dit, vous pouvez probablement augmenter vos processus actuels lorsque vous prévoyez de gérer les services aujourd’hui pour prendre en charge Teams à l’avenir.

La gestion des services englobe toutes les activités et processus impliqués dans la gestion Teams de bout en bout. Comme indiqué précédemment, certains composants de la gestion des services, c’est-à-dire l’infrastructure que le service Microsoft 365 ou Office 365 lui-même comprend, relèvent de la responsabilité de Microsoft, tandis que vous, le client, êtes responsable envers vos utilisateurs de gérer les différents aspects de Teams, du réseau et des points de terminaison que vous fournissez.

Les tâches et activités de ce guide sont regroupées en huit catégories, comme illustré dans le diagramme suivant. Chacune de ces catégories sera développée dans les sections suivantes.

![Diagramme illustrant une liste de catégories de tâches et d’activités.](media/operate-my-service-image1.png "Diagramme illustrant une liste des catégories de tâches et d’activités que comprend la gestion des services pour Teams. Le diagramme montre également que la gestion des services est en grande partie une tâche du client.")

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Déterminez comment les opérations seront implémentées pour Teams.</li></ul></td></tr>

<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Consultez le Guide des opérations dans son intégralité.</li><li>Implémentez une stratégie d’exploitation qui s’aligne sur les objectifs de votre organisation pour fournir la qualité et la fiabilité des charges de travail Teams.</li><li>Consultez le guide de révision de la qualité de l’expérience.</li><li> Implémentez une stratégie d’opérations pour effectuer régulièrement des révisions de qualité de l’expérience afin de vous assurer que votre déploiement Teams fonctionne à son maximum.</li></ul></td></tr>

</table>

### <a name="operational-role-mapping"></a>Mappage des rôles opérationnels

La planification que vous avez entreprise pour les opérations pendant la phase Devis est essentielle, car les activités opérationnelles commencent lorsque les premiers utilisateurs pilotes sont activés. Ce guide répertorie les activités et les tâches qui doivent être effectuées quotidiennement, hebdomadairement, mensuellement ou selon les besoins pour maintenir un déploiement Teams de haute qualité. Ce guide fournit des connaissances et des conseils sur la façon d’effectuer ces activités et tâches critiques.

L’un des composants essentiels d’un déploiement réussi consiste à s’assurer que la planification que vous effectuez au début de la phase Devis inclut la détermination des responsables de l’exécution d’activités spécifiques. Une fois que vous avez compris quelles tâches et activités s’appliquent à votre déploiement, elles doivent être comprises et suivies par les groupes ou les personnes que vous leur affectez.

Chaque équipe que vous identifiez doit examiner et s’entendre sur les tâches et responsabilités identifiées et commencer la préparation. Cela peut inclure la formation et la préparation, la fourniture de mises à jour du plan de dotation ou la garantie que les fournisseurs externes sont prêts à fournir.

Les activités et rôles définis dans ce guide doivent être valides dans la plupart des scénarios, mais chaque Teams déploiement est unique. Par conséquent, vous pouvez utiliser ce guide comme point de départ pour personnaliser les activités et les rôles par défaut pour répondre à vos besoins.

Assurez-vous que chaque équipe responsable a une bonne compréhension des activités requises pour exécuter le service. Il est essentiel que chaque équipe accepte et se déconnecte de sa responsabilité au sein de votre organisation avant le début du premier pilote.

Une fois qu’un accord est en place, les équipes correspondantes doivent commencer à rendre leurs rôles opérationnels.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td>
<td><ul><li>Utilisez ce document pour faciliter l’exercice de mappage des rôles opérationnels.</li><li>Rencontrez les équipes de support respectives pour attribuer des noms à chaque élément dans la liste des activités requises.</li><li>Obtenez l’acceptation ou la déconnexion des rôles attribués.</li><li>Assurez-vous que les équipes correspondantes disposent de la formation, de la préparation et des ressources appropriées pour effectuer les activités requises.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>dépendances de service Teams

Microsoft Teams réunit des technologies dans Microsoft 365 et Office 365 afin de fournir un hub pour le travail d’équipe. Voici quelques exemples :

- Azure Active Directory (Azure AD) fournit des services d’authentification et d’autorisation pour Teams.

- Exchange Online fournit des fonctionnalités avancées telles que la conservation légale et la découverte électronique.

- SharePoint Online offre la possibilité de partager des fichiers dans des canaux, et OneDrive Entreprise fournit un mécanisme de partage de fichiers au sein d’une conversation privée.

Les organisations peuvent également tirer parti des investissements existants dans l’infrastructure locale. Par exemple, les comptes Active Directory local existants peuvent être utilisés pour l’authentification en tirant parti d’Azure AD Connecter. Certaines versions de Exchange Server peuvent être utilisées à la place de Exchange Online.

Ces technologies se réunissent pour fournir aux utilisateurs une suite de communications riches, collaboratives et intelligentes. Cette intégration étroite est un avantage clé de Teams, mais elle entraîne également une exigence de gestion des services dans ces technologies.

Ce guide décrit les principaux domaines d’intérêt pour gérer le service Teams. Il est probable que des plans de gestion des services sont en place pour les technologies de support dont Teams dépend. Si ce n’est pas le cas, vous devez établir des plans de gestion des services appropriés pour ces composants technologiques (localement et en ligne) également. Ainsi, vos utilisateurs bénéficieront d’une expérience fiable et de haute qualité avec Teams.

#### <a name="references"></a>Références

[Présentation de Microsoft Teams](teams-overview.md)

[Interaction entre Exchange et Microsoft Teams](exchange-teams-interact.md)

[Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams](sharepoint-onedrive-interact.md)

[coexistence et interopérabilité Microsoft Teams et Skype Entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Activités du Guide des opérations

Les sections suivantes donnent une vue d’ensemble des activités requises pour faire fonctionner correctement le service Microsoft Teams. Elles incluent des références aux outils, aux informations contextuelles et au contenu supplémentaire pour vous aider à comprendre l’activité et à faciliter les initiatives de préparation.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Surveiller l’intégrité du service

Il est important que vous compreniez l’intégrité globale du service Microsoft Teams afin de pouvoir alerter de manière proactive les autres membres de votre organisation de tout événement qui affecte le service. Comme décrit précédemment, Teams dépend d’autres services Microsoft 365 et Office 365 tels que Azure Active Directory, Exchange Online, SharePoint Online et OneDrive Entreprise. Pour cette raison, il est tout aussi important de surveiller l’intégrité des services dépendants.

Incorporez cette activité dans votre processus de gestion des incidents pour informer de manière proactive les utilisateurs, le support technique et vos équipes d’opérations pour préparer la gestion des escalades d’utilisateurs.

Les sections suivantes décrivent les outils que vous pouvez utiliser pour surveiller [les incidents de service](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1) qui affectent le service Teams. Un résumé des avantages de chaque outil et du moment où vous devez les utiliser est inclus dans le tableau suivant.

| Outil de surveillance | Avantages | Quand utiliser |
|---|---|---|
| Centre d'administration Microsoft 365 | Disponible à partir de n’importe quel appareil avec un navigateur pris en charge. | Utilisez cette option lorsque vous n’avez pas besoin de notifications en temps réel. |
| application Administration Microsoft 365 | Fournit des notifications Push à votre appareil mobile. | Utilisez cette option lorsque vous devez être averti des incidents de service lorsque vous êtes en déplacement. |
| Microsoft System Center | Intégration à Microsoft System Center. | Utilisez-le lorsque vous avez besoin de fonctionnalités de surveillance avancées et de prise en charge des notifications. |
| API Microsoft 365 Service Communications | Accès par programmation à Microsoft 365 ou à Office 365 Service Health. | Utilisez-le lorsque vous avez besoin d’une intégration à un outil de supervision tiers ou que vous souhaitez créer votre propre solution. |

> [!NOTE]
> Seules les personnes qui se voient attribuer le rôle **d’administrateur général** ou **d’administrateur de service** peuvent afficher l’intégrité du service.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Surveillance avec le Centre d'administration Microsoft 365

Le [Centre d'administration Microsoft 365](https://portal.office.com/) fournit un [tableau de bord Service Health](https://portal.office.com/adminportal/home#/servicehealth) dans lequel vous pouvez afficher l’intégrité actuelle du service Teams en plus des services dépendants.

### <a name="monitoring-with-the-mobile-app"></a>Surveillance avec l’application mobile

L’application Administration Microsoft 365 est disponible sur Apple iOS, Android et Windows (PC et mobile). L’application fournit aux administrateurs des informations sur l’intégrité du service et les modifications à venir. L’application prend en charge les notifications Push qui peuvent vous avertir presque immédiatement après la publication d’un avis. Cela vous permet de rester à jour sur l’état, l’intégrité et les modifications à venir du service. La prise en charge des notifications en fait l’outil de supervision recommandé pour les administrateurs. Pour plus d’informations, consultez :

[application mobile Administration Microsoft 365](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Télécharger l’application mobile Administration Microsoft 365](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Surveillance avec Microsoft System Center

Microsoft System Center est une plateforme de gestion intégrée qui vous aide à gérer les centres de données, les appareils clients et les environnements informatiques cloud hybrides. Microsoft 365 ou Office 365 administrateurs qui utilisent System Center ont désormais la possibilité d’importer le pack d’administration, ce qui leur permet d’afficher toutes les communications de service dans Operations Manager dans System Center. Cet outil vous donne accès à l’état de vos services abonnés, aux incidents de service actifs et résolus, ainsi qu’aux communications de votre Centre de messages (modifications à venir). Pour plus d’informations, reportez-vous au [billet de blog](https://www.microsoft.com/en-us/microsoft-365/blog/2014/07/29/new-office-365-admin-tools/) suivant.

Si vous tirez parti de System Center pour surveiller l’intégrité du service Teams (et les services dépendants), vous pouvez personnaliser davantage le pack d’administration pour alerter ou avertir des groupes ou des personnes spécifiques qui ont été identifiés pour réagir aux incidents.
Ces groupes peuvent inclure des propriétaires de services, des support technique, des groupes de support de deuxième et de troisième niveau et des gestionnaires d’incidents dans votre organisation.

### <a name="monitoring-for-advanced-scenarios"></a>Surveillance des scénarios avancés

Vous pouvez surveiller l’intégrité du service et les modifications à venir en tirant parti de l’API Service Communications pour accéder à l’intégrité du service et aux modifications par programmation. Utilisez cette API pour créer votre propre outil de supervision, ou connectez vos outils de supervision existants à Microsoft 365 ou Office 365 communications de service, ce qui peut simplifier la façon dont vous surveillez votre environnement. Pour plus d’informations, consultez [Microsoft 365 ou Office 365 pour Enterprise développeurs](/office/developer-program/microsoft-365-developer-program-faq).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/en fonction des besoins

| Activité | Description | Cadence | Équipe affectée |
|---|---|---|---|
| Surveiller l’intégrité du service | Surveillez de manière proactive Microsoft Teams l’intégrité des services (et les services dépendants) à l’aide des outils disponibles. Les services dépendants sont les suivants : Exchange Online, SharePoint Online, OneDrive Entreprise, Azure Active Directory. | En temps réel | |
| Notification d’incident | Notifier les parties prenantes internes des événements qui affectent le service Teams. Les parties prenantes internes peuvent inclure des utilisateurs, des support technique et des gestionnaires d’incidents. | Selon les besoins | |

### <a name="references"></a>Références

[Comment vérifier Microsoft 365 ou Office 365'intégrité du service](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Vérifier l’état du service Microsoft Teams](service-health.md)

[Intégrité et continuité des services](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Gérer les changements organisationnels

Microsoft Teams est un service cloud. Avec cela vient la possibilité de fournir de nouvelles fonctionnalités et fonctionnalités à un rythme rapide. La fourniture d’une innovation continue offre un avantage évident aux organisations, mais ces modifications doivent être gérées de manière appropriée au sein de votre organisation afin d’éviter les résistances des utilisateurs ou les escalades vers votre support technique.

Les mises à jour de Teams sont déployées automatiquement pour vos utilisateurs. Vos utilisateurs disposeront toujours des derniers clients et fonctionnalités disponibles dans le service Teams. Il n’est pas possible de gérer le déploiement de Teams mises à jour pour vos utilisateurs. Il est donc essentiel de gérer le changement par le biais de programmes efficaces de communication, de formation et d’adoption. Si vos utilisateurs sont conscients du changement, informés des avantages et habilités à tirer parti des nouvelles fonctionnalités&mdash;, ils seront en mesure de s’adapter plus rapidement et d’accueillir le changement.

### <a name="monitoring-for-change"></a>Surveillance des modifications

La première étape de la gestion des modifications consiste à surveiller les modifications prévues pour Teams. La meilleure source pour surveiller ces modifications est la [feuille de route Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap), qui répertorie les fonctionnalités en cours de développement, en cours de déploiement pour les clients ou qui ont été entièrement lancées. Vous pouvez rechercher des fonctionnalités spécifiques à Teams à l’aide du filtre fourni, ou vous pouvez télécharger la feuille de route dans un fichier Excel pour une analyse plus approfondie. Pour chaque fonctionnalité, la feuille de route fournit une brève description, ainsi que la date de publication prévue.

Dans le [blog Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog), vous pouvez en savoir plus sur les meilleures pratiques, les tendances et les actualités relatives aux mises à jour de produits Teams. Attendez-vous à trouver les principales mises à jour des fonctionnalités à Teams à annoncer ici. Vous pouvez également vous abonner au blog via un flux RSS. Vous pouvez ensuite ajouter [le flux RSS](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) directement dans un canal Teams, de sorte que toutes les nouvelles importantes sont remises directement à l’intérieur de Teams.

Toutes les fonctionnalités publiées sont documentées dans les [notes de publication pour Microsoft Teams](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de).
Vous trouverez ici une liste des fonctionnalités publiées pour les appareils de bureau, web et mobiles. Le même ensemble de notes de publication est également disponible sous **l’onglet Nouveautés de l’aide**.[](get-help-in-microsoft-teams.md)

Familiarisez-vous avec les ressources disponibles et veillez à affecter des propriétaires applicables pour surveiller les modifications.

### <a name="planning-for-change"></a>Planification du changement

Maintenant que vous êtes au courant des modifications à venir apportées au service Teams, l’étape suivante consiste à préparer et planifier en conséquence. Évaluez chaque modification pour déterminer quelles modifications nécessitent une communication avec les utilisateurs, des campagnes de sensibilisation, une formation pour les équipes de support ou les utilisateurs, ou des campagnes d’évaluation et d’adoption des fonctionnalités. Il s’agit du rôle principal d’une équipe de gestion des changements au sein de votre organisation. Vous trouverez ci-dessous une collection d’exemples de tables qui peuvent vous aider à planifier des modifications.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Fonctionnalité : Enregistrement cloud (date de publication : janvier 2018)

**Piste générale**

| Modifier la préparation | Statut | Notes/étapes suivantes | Propriétaire |
|---|---|---|---|
| Révision juridique | Terminé | Cette fonctionnalité est un prérequis pour intégrer l’équipe de formation. | équipe Project |

**Gestion des modifications techniques**

| Modifier la préparation | Statut | Notes/étapes suivantes | Propriétaire |
|---|---|---|---|
| Modifications informatiques requises | Oui | Administration doit activer l’enregistrement pour les utilisateurs identifiés uniquement. | Équipe de support technique |
| Préparation technique terminée | Oui | | Équipe de support technique |
| | | | |

**Gestion des modifications utilisateur**

| Modifier la préparation | Statut | Notes/étapes suivantes | Propriétaire |
|---|---|---|---|
| Impact sur l’utilisateur | Bas | | |
| Préparation de l’utilisateur requise | Oui | | |
| Communications prêtes | Non | L’e-mail de communication a été rédigé, en attente de révision. | Équipe de communication |
| Formation prête | Oui | La formation tirera parti de la vidéo Microsoft existante. | Équipe de formation |

**Suivi de l’état**

| Modifier la préparation | Statut | Notes/étapes suivantes | Propriétaire |
|---|---|---|---|
| État de la mise en production | en cours | Examen en attente par le sponsor exécutif. | Équipe de gestion des modifications |
| Déconnexion de la version | | | |
| Date de publication | | | |

Pour plus d’informations sur la planification de la gestion des changements avec Teams, consultez [Créer une stratégie de gestion des changements pour Microsoft Teams](change-management-strategy.md).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/en fonction des besoins

| Activité| Description| Cadence| Équipe affectée |
|---|---|---|---|
| Surveiller les modifications| Surveillez les modifications à venir apportées au service Microsoft Teams.| Jour||
| Planification du changement| Évaluez et planifiez les nouvelles fonctionnalités, notamment les plans de communication, les campagnes de sensibilisation et la formation.| Selon les besoins ||
| Préparation des utilisateurs| Effectuez des campagnes de communication, de sensibilisation ou de formation ciblées pour vous assurer que les utilisateurs sont prêts pour le changement à venir.| Selon les besoins ||
| Préparation de l’équipe de support | Effectuez des campagnes de communication, de sensibilisation ou de formation ciblées pour vous assurer que l’équipe de support est prête. Les équipes de support peuvent inclure l’équipe « white glove », les supporteurs, le support de niveau 2 ou 3, les partenaires externes, et ainsi de suite. | Selon les besoins ||

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Évaluer l’utilisation Teams

Une fois le pilote initial démarré, il est essentiel d’établir une cadence régulière pour mesurer l’utilisation réelle Teams. Cela permet à votre organisation d’obtenir des insights sur la façon dont l’utilisation réelle s’aligne sur l’utilisation que vous avez prédite pendant la phase Devis. Bien que cette section se concentre sur Teams utilisation, elle doit faire partie d’un effort plus large pour mesurer et évaluer Microsoft 365 ou Office 365 utilisation globale.

Examiner fréquemment l’utilisation au début du déploiement vous donne la possibilité d’effectuer les étapes suivantes :

- Vérifiez si les utilisateurs utilisent Teams.

- Identifiez les problèmes d’adoption potentiels avant de créer des problèmes critiques au sein de l’organisation.

- Découvrez s’il existe des différences entre les exigences de phase Devis et l’utilisation réelle.

Si l’utilisation n’est pas ce que vous attendez, cela peut être dû à un problème de déploiement, ou le plan d’adoption n’est pas exécuté correctement, ou à un autre problème. Selon la raison réelle de la faible utilisation, l’administrateur doit collaborer avec les équipes associées pour aider à supprimer les obstacles à l’utilisation.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Mesure de l’utilisation avec le Centre d'administration Microsoft 365

Les données d’utilisation de Teams sont disponibles dans le tableau de bord Rapports. Teams données d’utilisation se trouvent dans trois rapports différents. Le premier rapport fournit une vue d’ensemble de la façon dont les utilisateurs communiquent et collaborent à l’aide des différents services dans Microsoft 365 ou Office 365. Ce rapport se trouve ici : [Microsoft 365 rapports dans le centre d’administration - Utilisateurs actifs](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Les deux autres rapports sont spécifiques à Teams et fournissent des détails supplémentaires sur Teams utilisation du point de vue de l’utilisateur et de l’appareil. Les deux rapports sont disponibles ici :

[Rapport d’utilisation des périphériques de Microsoft Teams](/microsoftteams/teams-analytics-and-reports/device-usage-report)

[Rapport d’activité des utilisateurs de Microsoft Teams](/microsoft-365/admin/activity-reports/microsoft-teams-user-activity-preview)

#### <a name="required-permissions"></a>Autorisations requises

Les rapports d’utilisation dans le Centre d’administration sont accessibles par des personnes qui ont reçu un rôle **Administrateur général** ou un rôle d’administrateur spécifique au produit (**administrateur Exchange**, **administrateur Skype Entreprise**, **administrateur SharePoint**).

En outre, le rôle **lecteur rapports** est disponible pour les utilisateurs qui ont besoin d’accéder aux rapports, mais n’effectuent aucune tâche nécessitant des autorisations au niveau de l’administrateur. Vous attribuez ce rôle pour fournir des rapports d’utilisation à toute personne qui est une partie prenante, pour surveiller et favoriser l’adoption. Pour plus d’informations sur les différents rôles disponibles, consultez [À propos des rôles d’administrateur Microsoft 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="assessing-usage"></a>Évaluation de l’utilisation

Une fois que vous avez utilisé le tableau de bord Rapports pour mesurer l’utilisation, il est important de comparer l’utilisation mesurée à tous les indicateurs de réussite clés que vous avez définis pendant la phase Devis du projet. Vous pouvez définir une KSI qui peut être définie comme une utilisation active, ou qui est indirectement liée à l’utilisation active.

Il est important d’identifier les écarts entre l’utilisation réelle et l’utilisation planifiée avant de reprendre le déploiement vers des sites ou des utilisateurs supplémentaires. Vous allez probablement identifier les apprentissages organisationnels dans le cadre de cette activité que vous pouvez tirer parti pour vous assurer que le lot suivant de sites ou d’utilisateurs ne rencontre pas les mêmes problèmes.

Tout d’abord, déterminez s’il s’agit d’un problème d’adoption ou d’un problème technique. Commencez par examiner les éléments ci-dessous, afin de déterminer où se trouve le problème.

1. Validez la qualité en effectuant une [révision de la qualité de l’expérience](upgrade-monitor-quality.md).

2. Collaborez avec l’équipe du support technique pour vérifier qu’aucun problème technique de tendance n’empêche les utilisateurs d’accéder ou d’utiliser le service. Si des tendances de problème existent, utilisez la section de [résolution des problèmes de point de terminaison](#endpoint-troubleshooting) plus loin dans cet article pour essayer de résoudre le problème avant d’engager le support.

3. Collaborez avec l’équipe de formation et d’adoption pour recueillir des commentaires directs des utilisateurs (voir [Évaluer les sentiments des utilisateurs](#assess-user-sentiment) plus loin dans cet article) et pour vérifier l’efficacité des activités de sensibilisation et d’adoption.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/en fonction des besoins

| Activité | Description | Cadence | Équipe affectée |
|---|---|---|---|
| Mesurer l’utilisation (phase d’activation) | Mesurez et évaluez Teams utilisation à mesure que les sites continuent d’être intégrés pendant la phase d’activation. Résoudre les problèmes d’utilisation selon les besoins. | Toutes les semaines | |
| Mesurer l’utilisation | Mesurez et évaluez Teams utilisation dans la phase Valeur du lecteur (une fois le déploiement terminé). Résoudre les problèmes d’utilisation selon les besoins. | Toutes les deux semaines | |
| (phase de valeur de lecteur) | | | |
| Mettre à jour le plan d’adoption | Mettez à jour votre plan d’adoption en fonction de la façon dont l’utilisation mesurée se compare à vos objectifs de planification. | Selon les besoins | |

### <a name="references"></a>Références

[À propos de la Centre d'administration Microsoft 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Rapports d’activité dans le Centre d'administration Microsoft 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Évaluer le sentiment de l’utilisateur

Comprendre le sentiment de l’utilisateur peut servir d’indicateur clé pour évaluer la réussite de votre déploiement Teams. Les commentaires des utilisateurs peuvent entraîner des modifications dans votre organisation ; Cela peut inclure des modifications apportées à vos plans de communication, programmes de formation ou la façon dont vous offrez un support à vos utilisateurs.

Il est important d’obtenir des commentaires tôt et de continuer à évaluer les sentiments des utilisateurs tout au long du cycle de vie du projet et au-delà. Utilisez les conseils suivants pour déterminer l’intervalle dans lequel votre organisation recherchera des commentaires :

- **Début du projet** : en évaluant le sentiment de l’utilisateur au début du projet, vous pouvez obtenir un aperçu précoce de la façon dont vos utilisateurs se sentent au sujet de leur expérience Teams.

- **Après les étapes majeures** : en collectant des commentaires tout au long du cycle de vie du projet, vous pouvez évaluer les sentiments des utilisateurs en continu et apporter des modifications en fonction des besoins. Ceci est particulièrement utile après des jalons majeurs.

- **Project conclusion** : l’évaluation du sentiment de l’utilisateur à la fin d’un projet vous indiquera à quel point vous avez bien fait et où le travail doit encore être effectué, et vous permettra de comparer les résultats par rapport à l’enquête précédente.

- **En cours** : continuez à mesurer indéfiniment le sentiment de l’utilisateur. Les changements de sentiment de l’utilisateur peuvent être dus à des modifications dans l’environnement de votre organisation ou à des modifications dans le service Teams. En évaluant les sentiments des utilisateurs à intervalles réguliers, vous pouvez comprendre les performances de vos équipes de gestion des services et la façon dont votre organisation répond aux modifications apportées au service Teams.

Les sentiments des utilisateurs peuvent être évalués par le biais de nombreuses méthodes différentes. Il peut s’agir d’enquêtes par e-mail, d’entrevues en personne ou par téléphone, ou simplement de la création d’un canal de commentaires dans Teams ou Yammer. Pour plus d’informations, consultez [les meilleures pratiques pour les méthodes de commentaires des utilisateurs dans Microsoft Teams](best-practices-feedback.md).

Vous pouvez également utiliser une approche à l’échelle du secteur pour évaluer le sentiment des utilisateurs appelé score de promotion net (NPS), qui est décrit dans la section suivante.

### <a name="nps"></a>NPS

Le score de promoteur net (NPS) est une métrique de fidélité des clients à l’échelle du secteur et une bonne approche à utiliser pour évaluer les sentiments des utilisateurs. NPS peut être calculé en posant deux questions : « Quelle est la probabilité que vous recommandiez Teams à un collègue ? », suivi de la question libre « Pourquoi ? »

NPS est un index compris entre –100 et 100 qui mesure la volonté d’un client de recommander le produit ou le service d’une entreprise. NPS est basé sur une enquête anonyme qui est remise aux utilisateurs par e-mail ou d’autres moyens électroniques. NPS mesure la fidélité entre un fournisseur et un consommateur. Il se compose d’une seule question, qui demande aux utilisateurs d’évaluer leur expérience de 1 à 10, avec la possibilité de fournir des commentaires supplémentaires. Les utilisateurs sont ensuite classés en fonction des évaluations suivantes :

- 9 ou 10 sont des promoteurs: passionnés fidèles qui feront la promotion de votre service et de carburant d’autres.

- 7 ou 8 sont passifs : satisfaits mais nonhussés, vulnérables à un autre service ou offre.

- De 1 à 6 sont les opposants: clients malheureux qui peuvent endommager votre service et entraver la croissance.

![Diagramme illustrant l’échelle NPS.](media/operate-my-service-image2.png "Ce diagramme illustre l’échelle NPS. Il montre que les classements de 0 à 6 sont des opposants, 7 à 8 sont passifs et 9 à 10 sont des promoteurs.")

Bien que le numéro NPS de base soit utile, vous obtiendrez le plus de valeur en analysant les commentaires des utilisateurs. Ils vous aideront à comprendre pourquoi l’utilisateur recommanderait (ou ne recommanderait pas) Teams à d’autres utilisateurs. Ces commentaires peuvent fournir des commentaires utiles pour aider les équipes de gestion de projet ou de service à comprendre les ajustements nécessaires pour fournir un service de qualité.

Pour fournir des enquêtes NPS à votre organisation, vous pouvez tirer parti de votre outil d’enquête en ligne favori.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/selon les besoins

| Activité | Description | Cadence | Équipe affectée |
|---|---|---|---|
| Évaluer le sentiment de l’utilisateur | Capturez et évaluez les sentiments des utilisateurs à l’aide d’enquêtes ou d’entretiens, ou par le biais d’un canal de commentaires dans Teams ou Yammer. | Selon les besoins | |
| Mettre à jour les plans d’adoption | Favoriser le changement dans votre organisation en fonction des commentaires des utilisateurs ; cela peut inclure des modifications apportées à vos plans de communication, à vos programmes de formation ou à la façon dont vous offrez un support à vos utilisateurs. | Selon les besoins | |

### <a name="references"></a>Références

[Score net du promoteur](https://en.wikipedia.org/wiki/Net_Promoter)

[Utilisation de Yammer pour collecter des commentaires](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Meilleures pratiques pour les commentaires des utilisateurs](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Gérer la qualité du réseau

De nombreux éléments de planification de base permettent d’optimiser, de dimensionner et de corriger votre infrastructure réseau pour garantir un chemin d’accès efficace et de haute qualité au service Microsoft Teams. Les tâches et exigences de planification sont traitées dans nos conseils de [préparation du réseau](prepare-network.md) . Les réseaux évoluent souvent au fil du temps en raison des mises à niveau, de l’expansion ou d’autres exigences métier. Il est important de tenir compte de vos besoins en matière de Teams dans vos activités de planification réseau.

Bien que la planification réseau soit un aspect essentiel d’un déploiement Teams, il est tout aussi important de s’assurer que le réseau reste sain et reste à jour, en fonction de l’évolution des exigences métier ou techniques.

Pour garantir l’intégrité de votre réseau, un certain nombre d’activités d’opérations doivent être effectuées à intervalles réguliers.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/en fonction des besoins

| Activité | Description | Cadence | Équipe affectée |
|---|---|---|---|
| Surveiller les adresses IP et URL Microsoft 365 ou Office 365 | Surveillez les modifications [apportées aux URL Office 365 et aux plages d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges) à l’aide du [flux RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) fourni et lancez une demande de modification aux groupes réseau applicables. | Jour | |
| Mettre à jour le réseau en fonction des modifications apportées aux adresses IP et URL Microsoft 365 ou Office 365 | Mettez à jour les composants réseau applicables (pare-feu, serveurs proxy, VPN, pare-feu côté client, et ainsi de suite) pour refléter les modifications [apportées aux URL et aux plages d’adresses IP Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges). | Selon les besoins | |
| Fournir des données de génération | Fournissez des informations de sous-réseau mises à jour au champion de la qualité (ou aux parties prenantes pertinentes) pour vous assurer que [les définitions de bâtiment dans CQD](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) sont à jour. | Selon les besoins | |
| Implémenter la modification | Implémentez des modifications sur le réseau pour prendre en charge la modification Teams exigences métier et techniques. Les éléments réseau peuvent inclure :<ul><li>Pare-feu</li><li>Vpn</li><li>Réseaux câblés et Wi-Fi</li><li>Connectivité Internet et ExpressRoute</li><li>DNS</li></ul> | Selon les besoins | |
| Surveillance et création de rapports réseau | Surveillez les tendances de bout en bout du réseau en matière de disponibilité, d’utilisation et de capacité à l’aide de vos outils de gestion réseau tiers existants et des fonctionnalités de création de rapports disponibles auprès de vos fournisseurs réseau. Utilisez les données de tendance pour la planification de la capacité réseau. | Tous les jours, toutes les semaines, tous les mois | |
| Planification de capacité | Collaborez avec les propriétaires de services Teams pour comprendre l’évolution des exigences métier et techniques susceptibles d’entraîner des changements de capacité supplémentaires.  | Selon les besoins | |
| Résolution et correction des problèmes réseau | Aidez les Teams les supporteurs, les propriétaires de services et les parties prenantes clés à résoudre et résoudre les problèmes liés à Teams connectivité, fiabilité ou qualité. Les éléments réseau peuvent inclure :<ul><li>Pare-feu</li><li>Vpn</li><li>Réseaux câblés et Wi-Fi</li><li>Connectivité Internet et ExpressRoute</li><li>DNS</li></ul> | Selon les besoins | |
| Récupération d’urgence et test de haute disponibilité | Effectuez régulièrement des tests de haute disponibilité et de récupération d’urgence sur l’infrastructure réseau pour vous assurer qu’elle répond aux objectifs de niveau de service (SLA) ou contrats de niveau de service (SLA) énoncés pour le service Teams. | Mois | |

### <a name="references"></a>Références

[URL et plages d’adresses IP Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Génération d’un schéma de données](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Évaluer et garantir la qualité

Toutes les organisations ont besoin d’un groupe ou d’une personne pour être responsables de la qualité. Il s'agit du rôle le plus important dans la gestion des services. Le rôle Champion qualité est attribué à une personne ou un groupe passionné par l’expérience de ses utilisateurs.
Ce rôle exige les compétences nécessaires pour cerner les tendances de l'environnement et le parrainage pour travailler avec d'autres équipes afin d'orienter les mesures correctives. En général, le meilleur candidat au rôle de Champion Qualité est le responsable du service clientèle. Selon la taille et la complexité de l’organisation, il peut s’agir d’une personne ou d’un groupe qui a la passion d’assurer une expérience utilisateur de haute qualité.

Le champion de la qualité tire parti des outils et des processus documentés existants, tels que le tableau de bord de qualité des appels (CQD) et [l’amélioration et la surveillance de la qualité des appels pour Teams](monitor-call-quality-qos.md), pour surveiller l’expérience utilisateur, identifier les tendances de qualité et favoriser la correction si nécessaire.
Le champion de la qualité doit collaborer avec les équipes respectives pour mener des actions de correction et présenter un rapport à un comité directeur sur les progrès réalisés et les problèmes ouverts.

[Améliorer et surveiller la qualité des appels pour Teams](monitor-call-quality-qos.md) inclut des activités qui évaluent et fournissent des conseils de correction dans les domaines clés qui ont le plus d’impact sur l’amélioration de l’expérience utilisateur. Les conseils fournis dans le Guide d’examen de l’expérience de qualité se concentrent sur l’utilisation de CQD Online comme principal outil pour signaler et examiner chaque domaine, en  concentrant sur l’audio afin d’optimiser l’adoption et l’impact. Toutes les optimisations apportées au réseau pour améliorer l'expérience audio se traduiront aussi directement par des améliorations dans le partage de la vidéo et du bureau.

Nous vous recommandons vivement de nommer le champion de la qualité dès le début. Après avoir été nommés, ils doivent commencer à se familiariser avec le contenu dans [Améliorer et surveiller la qualité des appels pour les Teams](monitor-call-quality-qos.md) et les supports de formation associés.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/en fonction des besoins

| Activité | Description | Cadence | Équipe affectée |
|---|---|---|---|
| Nommer et entraîner des champions de qualité | Nommez et entraînez un champion de qualité. | Selon les besoins | |
| Effectuer des révisions de qualité de l’expérience (QER) | Effectuez un QER pour identifier les tendances en matière de qualité et de fiabilité, passer en revue les cibles définies et faire rapport aux parties prenantes clés de l’organisation. | Mensuel (hebdomadaire pendant les déploiements) | |
| Correction des lecteurs | Coordonner les efforts de correction au sein de l’organisation en fonction des évaluations et des résultats de QER. | Selon les besoins | |
| Mettre à jour les données de génération dans CQD | Mettez à jour ou ajoutez de nouvelles définitions de bâtiment dans CQD lorsque des modifications sont apportées au réseau (voir [Télécharger Informations de création](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | Selon les besoins | |
| Remplir le rôle De champion de la qualité | Responsabilité de bout en bout de la qualité au sein de l’organisation. Cela inclut :<ul><li>Assurez-vous que le QER est effectué régulièrement.</li><li>Faire rapport à des parties prenantes clés sur l’état de la qualité.</li><li>Vérifiez que les définitions de données de génération sont à jour.</li><li>Coordonnez les efforts de correction au sein de l’organisation pour vous assurer que les utilisateurs disposent d’une expérience de haute qualité avec Teams.</li></ul> | Jour | |

### <a name="references"></a>Références

[Télécharger informations sur la création](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[Améliorer et surveiller la qualité des appels pour Teams](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Gérer les points de terminaison

Microsoft Teams points de terminaison peuvent être définis comme n’importe quel PC, Mac, tablette ou appareil mobile (ou tout autre) exécutant le client Teams. Le terme point de *terminaison* englobe non seulement l’appareil lui-même, mais également la façon dont un utilisateur se connecte à l’appareil, par exemple à l’aide du micro intégré ou du haut-parleur de l’appareil, d’écouteurs ou d’un casque optimisé. Une fois qu’ils sont déployés, les points de terminaison ne doivent pas être oubliés. Les points de terminaison Teams nécessitent des soins et une maintenance continus. Les sections suivantes décrivent des domaines spécifiques sur lesquels se concentrer.

### <a name="endpoint-requirements"></a>Exigences relatives aux points de terminaison

L’un des principaux avantages de Teams est que le client est mis à jour automatiquement. Les clients sur PC et Mac sont mis à jour à l'aide d'un processus en arrière-plan qui vérifie les nouvelles versions et télécharge le nouveau client lorsque l'application est inactive. Les applications mobiles Teams sont maintenues à jour via leurs magasins d’applications respectifs.

Le client Teams a des exigences minimales en termes de plateforme logicielle sous-jacente. Ces exigences peuvent changer au fil du temps, et il est donc important de les surveiller pour les modifications. Par exemple, le client Teams a une version minimale iOS. Si le client utilise un navigateur Internet, le navigateur doit également être à jour. Vous trouverez la liste des plateformes prises en charge dans [Obtenir des clients pour Microsoft Teams](get-clients.md).

### <a name="endpoint-firewalls"></a>Pare-feu des points de terminaison

Les pare-feu côté client peuvent avoir un impact significatif sur l'expérience utilisateur.
Les pare-feu côté client peuvent affecter la qualité des appels et même empêcher l’établissement d’un appel. Une fois que les exclusions appropriées sur le pare-feu client ont été configurées, elles doivent être mises à jour en fonction des informations [contenues dans Office 365 URL et plages d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Votre fournisseur tiers aura des conseils spécifiques sur la façon de mettre à jour les exclusions.

### <a name="wi-fi-drivers"></a>Pilotes Wi-Fi

Wi-Fi pilotes peuvent être problématiques. Par exemple, un pilote peut avoir des comportements d’itinérance très agressifs entre les points d’accès, ce qui peut entraîner un changement inutile de point d’accès, ce qui entraîne une qualité d’appel médiocre. Un pilote Wi-Fi peu performant peut être découvert par le biais d’une révision de la qualité de l’expérience (voir [Améliorer et surveiller la qualité des appels pour Teams](monitor-call-quality-qos.md) pour plus d’informations). Il est essentiel d’implémenter un processus piloté par la qualité qui surveille les nouveaux pilotes Wi-Fi et garantit qu’ils sont testés avant d’être déployés sur le grand nombre d’utilisateurs.

### <a name="endpoint-management"></a>Gestion des points de terminaison

Un catalogue de points de terminaison et d’appareils d’interface pris en charge (tels que les casques) doit être disponible et géré. Ce catalogue inclut une liste d’appareils approuvés qui ont été sélectionnés et validés dans le cadre des phases Envisager et Intégrer. En règle générale, des appareils spécifiques sont sélectionnés pour chaque type de personnage de votre organisation afin de répondre aux besoins des attributs de ce personnage. Tous les points de terminaison ont un cycle de vie et vous devez gérer les contrats fournisseurs, la garantie, le remplacement, la distribution et les stratégies de réparation associés à ces appareils.

### <a name="endpoint-troubleshooting"></a>Résolution des problèmes liés aux points de terminaison

Même si vous avez suivi les instructions précédentes, les utilisateurs de votre organisation peuvent toujours rencontrer des problèmes avec Teams. Bien que le problème ne soit peut-être pas lié au point de terminaison lui-même, les symptômes du problème sont généralement signalés par le client à l’utilisateur. Les conseils suivants sont destinés à fournir des étapes générales que vous pouvez prendre pour résoudre le problème; il ne s’agit pas d’un guide de dépannage complet. Les étapes sont fournies dans un ordre spécifique, mais elles n’ont pas besoin d’être suivies explicitement et peuvent ne pas être applicables, selon la nature du problème.

1. **Valider l’intégrité du service :** Le problème qu’un utilisateur peut rencontrer peut être lié à un événement qui affecte négativement le service Teams ou ses services dépendants. Dans un premier temps, nous vous recommandons de confirmer qu’il n’existe aucun problème de service actif. Consultez [Comment vérifier Microsoft 365'intégrité du service](/office365/enterprise/view-service-health). N’oubliez pas de vérifier l’état des services dépendants (par exemple, Exchange, SharePoint, OneDrive Entreprise). La surveillance de l’intégrité des services est décrite plus en détail dans la section précédente, [Surveiller l’intégrité des services](#monitor-service-health).

2. **Valider la connectivité du client :** Les problèmes de connectivité provoquent des problèmes de fonctionnalité ou de connexion dans Teams. Nous vous recommandons (en particulier pour les nouveaux sites ou emplacements) de valider la connectivité au service. Assurez-vous que les [instructions suivantes Office 365 URL et plages d’adresses IP sont suivies](/microsoft-365/enterprise/urls-and-ip-address-ranges) pour chaque site. Vous pouvez tirer parti de [Microsoft Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) pour effectuer un test de connectivité afin de vérifier que les ports multimédias ont été ouverts correctement pour Teams fonctionnalités. Des étapes détaillées sur la façon d’exécuter les tests de connectivité sont fournies dans les instructions de [préparation du réseau](prepare-network.md) .

3. **Consultez la liste des problèmes connus :** Consultez [Teams résolution des problèmes](/MicrosoftTeams/troubleshoot/teams) pour déterminer si l’utilisateur a été affecté négativement par l’un de ces problèmes. Suivez la solution de contournement fournie (le cas échéant) pour résoudre le problème.

4. **Visitez la communauté Microsoft Teams :** la [communauté Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) offre des espaces dédiés pour Teams. La communauté Teams fournit une liste de discussions, des billets de blog et des annonces centrées sur Teams. Vous pouvez publier une question ou rechercher des solutions à votre problème dans les discussions précédentes.

5. **Support Microsoft de contact :** vous pouvez contacter Support Microsoft pour les problèmes liés à Teams en ligne ou par téléphone. Pour plus d’informations, consultez [La prise en charge des contacts pour les produits professionnels - Administration aide](/microsoft-365/admin/contact-support-for-business-products). Pour les clients Premier, les demandes de support peuvent être lancées en suivant les instructions fournies dans [contacter le support technique pour Microsoft Teams (clients Premier).](https://support.microsoft.com/premier/contacts)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/en fonction des besoins

| Activité | Description | Cadence | Équipe affectée |
|---|---|---|---|
| Exigences relatives aux points de terminaison | Assurez-vous que le point de terminaison Teams continue de répondre à toutes les exigences logicielles pour Teams répertoriées dans [Obtenir des clients pour Microsoft Teams](get-clients.md). | Mois | |
| Pare-feu des points de terminaison | Conservez les exclusions appropriées sur le pare-feu de points de terminaison en fonction des informations [contenues dans Office 365 URL et plages d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Votre fournisseur tiers aura des conseils spécifiques sur la façon de gérer les exclusions. Abonnez-vous au [flux RSS](https://support.office.com/o365ip/rss) pour être averti automatiquement des modifications. | Selon les besoins | |
| Pilotes Wi-Fi | Testez et mettez à jour Wi-Fi pilotes sur le PC. Validez les résultats à l’aide de CQD ([Améliorez et surveillez la qualité des appels pour Teams](monitor-call-quality-qos.md)). | Selon les besoins | |
| Gestion des points de terminaison | Conservez le catalogue des points de terminaison et des périphériques d’interface pris en charge (tels que les casques). Gérer les contrats fournisseurs, la garantie, la distribution, le remplacement et les stratégies de réparation. | Mois | |
| Résolution des problèmes liés aux points de terminaison | Les tâches de résolution des problèmes peuvent inclure la vérification de la connectivité, la consultation de la liste des problèmes connus, la collecte des journaux, l’analyse et l’escalade vers des fournisseurs Support Microsoft ou tiers. | Selon les besoins | |

### <a name="references"></a>Références

[URL et plages d’adresses IP Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Obtenir des clients pour Microsoft Teams](get-clients.md)

[communauté Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)

[Vérifier l’état du service Microsoft Teams](service-health.md)

[Contacter le support relatif aux produits d’entreprises - Aide de l’administrateur](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

[Contacter le support Premier](https://support.microsoft.com/premier/contacts)

[Résolution des problèmes Teams vidéo](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Gérer Teams

Une fois le service Microsoft Teams déployé, vous devez effectuer plusieurs activités liées à son administration. Les activités vont de l’administration du service et des utilisateurs individuels à la planification de la capacité et à l’approvisionnement des licences et des numéros de téléphone. Les sections suivantes couvrent certaines de ces tâches d’administration courantes.

### <a name="service-administration"></a>Administration du service

Le service Teams a plusieurs paramètres qui peuvent être configurés à l’échelle du locataire.
Les modifications apportées aux paramètres du locataire affectent tous les utilisateurs qui ont été activés pour Teams. Pour obtenir une liste détaillée de ces paramètres, consultez [Gérer Microsoft Teams paramètres pour votre organisation](enable-features-office-365.md).

### <a name="user-administration"></a>Administration des utilisateurs

Pour prendre en charge les utilisateurs, une organisation peut nécessiter un nombre quelconque de tâches connexes : les tâches spécifiques varient d’une organisation à l’autre. En fin de compte, ces tâches doivent être gérées par une équipe de support technique qui a reçu ces tâches opérationnelles. Les tâches suivantes sont généralement nécessaires pour prendre en charge les utilisateurs dans Teams.

#### <a name="general-tasks"></a>Tâches générales

[Gérer l’accès des utilisateurs à Microsoft Teams](user-access.md)

### <a name="team-creation-optional"></a>Création d’équipe (facultatif)

Par défaut, tous les utilisateurs disposant d’une boîte aux lettres dans Exchange Online disposent des autorisations nécessaires pour créer des groupes Microsoft 365 et, par conséquent, une équipe dans Microsoft Teams. Si vous souhaitez avoir un contrôle plus strict et [restreindre la création de nouvelles équipes](assign-roles-permissions.md#permissions-to-create-teams) (et donc la création de nouveaux groupes Microsoft 365), vous pouvez déléguer des droits de création et de gestion de groupe à un ensemble d’administrateurs. Si votre organisation souhaite poursuivre cette option, consultez le processus décrit dans cet article pour permettre aux utilisateurs d’envoyer des demandes traitées par une équipe affectée.

<!--ENDOFSECTION-->

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/en fonction des besoins

| Activité | Description | Cadence | Équipe affectée |
|---|---|---|---|
| Administration du service | Administration des paramètres de Teams à l’échelle du locataire. | Selon les besoins | |
| Administration des utilisateurs | Administration des paramètres et des licences basés sur l’utilisateur dans Teams. | Selon les besoins | |
| Gestion des licences | Planifiez les besoins actuels et futurs pour les licences basées sur l’utilisateur et la consommation (forfaits d’appels et crédits de communication) en tirant parti du [rapport d’utilisation RTC](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) et du rapport des [pools de minutes RTC](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) . | Toutes les semaines | |
| Gestion des numéros de téléphone | Gérez les numéros de téléphone disponibles pour une croissance future et ajustez les niveaux d’inventaire pour répondre aux besoins de votre organisation. | Toutes les semaines | |
| Création d’équipe (facultatif) | Passez en revue et traitez les demandes de création d’équipe. | Selon les besoins | |

<!--ENDOFSECTION-->