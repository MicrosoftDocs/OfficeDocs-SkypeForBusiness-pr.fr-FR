---
title: Guides des opérations de Microsoft Teams
author: rmw2890
ms.author: Rowille
audience: admin
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Tâches et activités requises pour la gestion des services Teams, notamment la surveillance de l’intégrité du service, ainsi que l’évaluation et la garantie de la qualité et de l’utilisation du réseau.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: be2cea73868bbd6a974242e2a6f8c3d31730e087
ms.sourcegitcommit: 0760416ee0bead3ada93f4d37f8aebc74222bd3c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2022
ms.locfileid: "69019440"
---
# <a name="operate-my-service"></a>Exploiter mon service

Cet article fournit une vue d’ensemble des conditions requises pour faire fonctionner correctement les services vocaux cloud pour votre organisation. En exploitant correctement vos services vocaux cloud, vous pouvez être sûr de fournir une expérience fiable et de haute qualité à votre organisation.

## <a name="introduction-to-the-operations-guide"></a>Introduction au Guide des opérations

Le Guide des opérations vous donne une vue d’ensemble de toutes les tâches et activités requises dans le cadre de la fonction de gestion des services pour Microsoft Teams.

La gestion des services est un vaste sujet qui couvre les opérations quotidiennes du service Microsoft Teams après son déploiement et son activation pour les utilisateurs. Le service Teams englobe Microsoft 365 ou Office 365 et les composants d’infrastructure déployés localement (par exemple, la mise en réseau).

La notion de gestion des services n'est probablement pas un concept nouveau pour la plupart des organisations. Vous avez peut-être déjà implémenté des processus et des tâches associés à des services existants. Cela dit, vous pouvez probablement augmenter vos processus actuels lorsque vous planifiez la gestion des services aujourd’hui pour prendre en charge Teams à l’avenir.

La gestion des services englobe toutes les activités et processus impliqués dans la gestion de Teams de bout en bout. Comme indiqué précédemment, certains composants de la gestion des services , l’infrastructure que le service Microsoft 365 ou Office 365 lui-même comprend, relèvent de la responsabilité de Microsoft, tandis que vous, le client, êtes responsable devant vos utilisateurs de gérer les différents aspects de Teams, le réseau et les points de terminaison que vous fournissez.

Les tâches et activités de ce guide sont regroupées en huit catégories, comme illustré dans le diagramme suivant. Chacune de ces catégories sera développée dans les sections suivantes.

![Diagramme illustrant une liste de catégories de tâches et d’activités.](media/operate-my-service-image1.png "Diagramme illustrant une liste de catégories de tâches et d’activités que la gestion des services pour Teams comprend. Le diagramme montre également que la gestion des services est en grande partie une tâche du client.")


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Points de décision</td><td><ul><li>Déterminez comment les opérations seront implémentées pour Teams.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td><td><ul><li>Consultez le Guide des opérations dans son intégralité.</li><li>Implémentez une stratégie d’exploitation qui s’aligne sur les objectifs de votre organisation pour fournir la qualité et la fiabilité des charges de travail vocales cloud.</li><li>Passez en revue [Surveiller la qualité des appels](monitor-call-quality-qos.md).</li><li> Implémentez une stratégie d’exploitation pour effectuer régulièrement des révisions de qualité de l’expérience pour vous assurer que votre déploiement de voix cloud fonctionne à ses capacités maximales.</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>Mappage des rôles opérationnels

La planification que vous avez effectuée pour les opérations pendant la phase Devision est essentielle, car les activités d’exploitation commencent lorsque les premiers utilisateurs pilotes sont activés. Ce guide répertorie les activités et les tâches qui doivent être effectuées sur une base quotidienne, hebdomadaire, mensuelle ou selon les besoins pour maintenir un déploiement Teams de haute qualité. Ce guide fournit des connaissances et des conseils sur la façon d’effectuer ces activités et tâches critiques.

L’un des éléments essentiels d’un déploiement réussi consiste à vous assurer que la planification que vous effectuez au début de la phase Devision inclut la détermination des personnes qui seront responsables de l’exécution d’activités spécifiques. Une fois que vous avez déterminé quelles tâches et activités s’appliquent à votre déploiement, elles doivent être comprises et suivies par les groupes ou les individus que vous leur affectez.

Chaque équipe que vous identifiez doit passer en revue et s’entendre sur les tâches et responsabilités identifiées et commencer la préparation. Cela peut inclure la formation et la préparation, la mise à jour du plan de dotation ou la garantie que les fournisseurs externes sont prêts à fournir.

Les activités et les rôles définis dans ce guide doivent être valides dans la plupart des scénarios, mais chaque déploiement Teams est unique . Par conséquent, vous pouvez utiliser ce guide comme point de départ pour personnaliser les activités et les rôles par défaut en fonction de vos besoins.

Assurez-vous que chaque équipe responsable a une bonne compréhension des activités requises pour exécuter le service. Il est essentiel que chaque équipe accepte et signe sa responsabilité dans votre organisation avant le début du premier pilote.

Une fois qu’un accord est en place, les équipes correspondantes doivent commencer à rendre leurs rôles opérationnels.

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Étapes suivantes</td>
<td><ul><li>Utilisez ce document pour faciliter l’exercice de mappage des rôles opérationnels.</li><li>Rencontrez les équipes de support respectives pour attribuer des noms à chaque élément dans la liste des activités requises.</li><li>Obtenez l’acceptation ou l’approbation des rôles attribués.</li><li>Assurez-vous que les équipes correspondantes disposent de la formation, de la préparation et des ressources appropriées pour effectuer les activités requises.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Dépendances du service Teams

Microsoft Teams regroupe des technologies dans Microsoft 365 ou Office 365 pour fournir un hub pour le travail d’équipe. Voici quelques exemples :

-   Azure Active Directory (Azure AD) fournit des services d’authentification et d’autorisation pour Teams.

-   Exchange Online fournit des fonctionnalités avancées telles que la conservation légale et la découverte électronique.

-   SharePoint Online permet de partager des fichiers dans des canaux, et OneDrive Entreprise fournit un mécanisme de partage de fichiers dans une conversation privée.

Les organisations peuvent également tirer parti des investissements existants dans l’infrastructure locale. Par exemple, les comptes Active Directory local existants peuvent être utilisés pour l’authentification en tirant parti d’Azure AD Connect. Certaines versions de Exchange Server peuvent être utilisées à la place de Exchange Online.

Ces technologies s’associent pour fournir aux utilisateurs une suite de communications riche, collaborative et intelligente. Cette intégration étroite est un avantage clé de Teams, mais elle entraîne également une exigence de gestion des services dans l’ensemble de ces technologies.

Ce guide couvre les principaux domaines d’intérêt pour gérer le service Teams. Très probablement, vous avez mis en place des plans de gestion des services pour les technologies de prise en charge dont Dépend Teams. Si ce n’est pas le cas, vous devez également établir des plans de gestion de service appropriés pour ces composants technologiques (locaux et en ligne). Cela permet de s’assurer que vos utilisateurs bénéficient d’une expérience fiable et de haute qualité avec Teams.

#### <a name="references"></a>Références 

[Présentation de Microsoft Teams](teams-overview.md)

[Interaction entre Exchange et Microsoft Teams](exchange-teams-interact.md)

[Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams](sharepoint-onedrive-interact.md)

[Microsoft Teams et Skype Entreprise coexistence et interopérabilité](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Activités du Guide des opérations

Les sections suivantes donnent une vue d’ensemble des activités nécessaires au bon fonctionnement du service Microsoft Teams. Ils incluent des références à des outils, des informations contextuelles et du contenu supplémentaire pour vous aider à comprendre l’activité et à faciliter les initiatives de préparation.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Surveiller l’intégrité du service

Il est important que vous compreniez l’intégrité globale du service Microsoft Teams afin de pouvoir alerter de manière proactive les autres membres de votre organisation de tout événement qui affecte le service. Comme décrit précédemment, Teams dépend d’autres services Microsoft 365 ou Office 365 tels qu’Azure Active Directory, Exchange Online, SharePoint Online et OneDrive Entreprise. Pour cette raison, il est tout aussi important de surveiller l’intégrité des services dépendants.

Incorporez cette activité dans votre processus de gestion des incidents pour informer de manière proactive les utilisateurs, le support technique et vos équipes d’exploitation de se préparer à gérer les escalades d’utilisateurs.

Les sections suivantes décrivent les outils que vous pouvez utiliser pour surveiller [les incidents de service](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1) qui affectent le service Teams. Le tableau suivant présente un résumé des avantages de chaque outil et du moment auquel vous devez utiliser chacun d’eux.

| Outil de surveillance                       | Avantages                                            | Quand utiliser                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Centre d’administration Microsoft 365                     | Disponible à partir de n’importe quel appareil avec un navigateur pris en charge. | Utilisez quand vous n’avez pas besoin de notifications en temps réel.                                          |
| Application Microsoft 365 ou Office 365 Admin                  | Fournit des notifications Push à votre appareil mobile.  | Utilisez lorsque vous devez être averti des incidents de service lorsque vous êtes en déplacement.                  |
| Microsoft System Center               | Intégration à Microsoft System Center.           | Utilisez lorsque vous avez besoin de fonctionnalités de supervision avancées et de prise en charge des notifications.                       |
| API Microsoft 365 ou Office 365 Service Communications | Accès par programmation à Microsoft 365 ou Office 365 service Health.   | Utilisez lorsque vous avez besoin d’une intégration avec un outil de supervision tiers ou si vous souhaitez créer votre propre solution. |

> [!NOTE]
> Seules les personnes à qui le rôle **d’administrateur général** ou **d’administrateur de service** est attribué peuvent afficher l’intégrité du service.

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>Surveillance avec le Centre d'administration Microsoft 365

Le [Centre d'administration Microsoft 365](https://portal.office.com/) fournit un [tableau de bord Service Health](https://portal.office.com/adminportal/home#/servicehealth) dans lequel vous pouvez afficher l’intégrité actuelle du service Teams en plus des services dépendants.

### <a name="monitoring-with-the-mobile-app"></a>Surveillance avec l’application mobile

L’application Microsoft 365 ou Office 365 Admin est disponible sur Apple iOS, Android et Windows (PC et mobile). L’application fournit aux administrateurs de service des informations sur l’intégrité du service et les modifications à venir. L’application prend en charge les notifications Push qui peuvent vous alerter presque immédiatement après la publication d’un avis. Cela vous permet de rester informé de l’état, de l’intégrité et des modifications à venir apportées au service. La prise en charge des notifications en fait l’outil de surveillance recommandé pour les administrateurs. Pour plus d’informations, consultez :

[application mobile Office 365 Admin](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Télécharger l’application mobile Office 365 Admin](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Supervision avec Microsoft System Center

Microsoft System Center est une plateforme de gestion intégrée qui vous permet de gérer les centres de données, les appareils clients et les environnements informatiques cloud hybrides. Office 365 administrateurs qui utilisent System Center ont désormais la possibilité d’importer le pack d’administration Office 365, ce qui leur permet d’afficher toutes les communications de service dans Operations Manager dans System Center. L’utilisation de cet outil vous permet d’accéder à l’état de vos services abonnés, aux incidents de service actifs et résolus, ainsi qu’aux communications de votre Centre de messages (modifications à venir). Pour plus d’informations, reportez-vous au [billet de blog](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true) suivant.

Si vous utilisez System Center pour surveiller l’intégrité du service Teams (et les services dépendants), vous pouvez personnaliser davantage le pack d’administration pour alerter ou avertir des groupes ou des personnes spécifiques qui ont été identifiés pour réagir aux incidents.
Ces groupes peuvent inclure les propriétaires de services, les services d’assistance, les groupes de support de deuxième et de troisième niveau et les gestionnaires d’incidents de votre organisation.

### <a name="monitoring-for-advanced-scenarios"></a>Surveillance des scénarios avancés

Vous pouvez surveiller l’intégrité du service et les modifications à venir en tirant parti de l’API Office 365 Service Communications pour accéder à Office 365 intégrité du service et aux modifications par programme. Utilisez cette API pour créer votre propre outil de supervision, ou connectez vos outils de supervision existants à Office 365 communications de service, ce qui simplifie potentiellement la façon dont vous surveillez votre environnement. Pour plus d’informations, consultez [Office 365 pour les développeurs d’entreprise](https://developer.microsoft.com/office).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/selon les besoins

| Activité               | Description                                                                                                                                                                                                               | Cadence   | Équipe affectée |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Surveiller l’intégrité du service | Surveillez de manière proactive l’intégrité du service Microsoft Teams (et les services dépendants) à l’aide des outils disponibles. Les services dépendants incluent : Exchange Online, SharePoint Online, OneDrive Entreprise, Azure Active Directory. | Temps réel |               |
| Notification d’incident  | Informer les parties prenantes internes des événements qui affectent le service Teams. Les parties prenantes internes peuvent inclure des utilisateurs, des services d’assistance et des gestionnaires d’incidents.                                                                          | Selon les besoins |               |

### <a name="references"></a>Références 

[Comment vérifier l’intégrité du service Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Vérifier l’état du service Microsoft Teams](service-health.md)

[Intégrité et continuité des services](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Gérer les changements organisationnels

Microsoft Teams est un service basé sur le cloud. Avec cela vient la possibilité de fournir de nouvelles fonctionnalités à un rythme rapide. La fourniture d’une innovation continue offre un avantage évident pour les organisations, mais ces modifications doivent être gérées de manière appropriée au sein de votre organisation pour éviter la résistance des utilisateurs ou les escalades vers votre support technique.

Mises à jour à Teams sont déployées automatiquement pour vos utilisateurs. Vos utilisateurs auront toujours le client et les dernières fonctionnalités disponibles dans le service Teams. Il n’est pas possible de gérer le déploiement des mises à jour Teams pour vos utilisateurs. Par conséquent, il est extrêmement important de gérer les changements par le biais de programmes efficaces de communication, de formation et d’adoption. Si vos utilisateurs sont conscients du changement, informés des avantages et autorisés à tirer parti des nouvelles fonctionnalités&mdash;qu’ils pourront adapter plus rapidement et accueillir le changement.

### <a name="monitoring-for-change"></a>Surveillance des modifications

La première étape de la gestion des modifications consiste à surveiller les modifications planifiées pour Teams. La meilleure source pour surveiller ces modifications est la [feuille de route Office 365](https://products.office.com/business/office-365-roadmap), qui répertorie les fonctionnalités en cours de développement, en cours de déploiement pour les clients ou qui ont été entièrement lancées. Vous pouvez rechercher des fonctionnalités spécifiques à Teams à l’aide du filtre fourni, ou vous pouvez télécharger la feuille de route dans un fichier Excel pour une analyse plus approfondie. Pour chaque fonctionnalité, la feuille de route fournit une brève description, ainsi que la date de publication prévue.

Dans le [blog Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog), vous pouvez découvrir les meilleures pratiques, les tendances et les actualités sur les mises à jour des produits Teams. Attendez-vous à trouver les principales mises à jour des fonctionnalités de Teams à annoncer ici. Vous pouvez également vous abonner au blog via un flux RSS. Vous pouvez ensuite ajouter [le flux RSS](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) directement dans un canal Teams, afin que toutes les actualités importantes soient transmises directement à l’intérieur de Teams.

Toutes les fonctionnalités publiées sont documentées dans les [Notes de publication de Microsoft Teams](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de).
Vous trouverez ici une liste des fonctionnalités publiées pour les appareils de bureau, web et mobiles. Le même ensemble de notes de publication est également disponible sous **l’onglet Nouveautés de l’aide**.[](get-help-in-microsoft-teams.md)

Familiarisez-vous avec les ressources disponibles et veillez à affecter des propriétaires applicables pour surveiller les modifications.

### <a name="planning-for-change"></a>Planification des modifications

Maintenant que vous êtes conscient des modifications à venir apportées au service Teams, l’étape suivante consiste à préparer et à planifier en conséquence. Évaluez chaque modification pour déterminer les modifications qui nécessitent une communication avec les utilisateurs, des campagnes de sensibilisation, des formations pour les équipes ou les utilisateurs du support technique, ou des campagnes d’évaluation et d’adoption des fonctionnalités. Il s’agit du rôle principal d’une équipe de gestion des changements dans votre organisation. Vous trouverez ci-dessous une collection d’exemples de tables qui peuvent vous aider à planifier les modifications.

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Fonctionnalité : Enregistrement cloud (date de publication : janvier 2018)

**Piste générale**

| Préparation aux modifications | Statut   | Notes/étapes suivantes | Propriétaire |
|----|----|----|-----|
| Révision juridique   | Terminé     | Cette fonctionnalité est une condition préalable à l’intégration de l’équipe de formation. | Équipe de projet  |

**Gestion des modifications techniques**

|       Préparation aux modifications       | Statut |                      Notes/étapes suivantes                      |    Propriétaire     |
|------------------------------|--------|------------------------------------------------------------|--------------|
|     Modifications informatiques requises      |  Oui   | Administration devez activer l’enregistrement uniquement pour les utilisateurs identifiés. | Équipe de support technique |
| Préparation technique terminée |  Oui   |                                                            | Équipe de support technique |
|                              |        |                                                            |              |

**Gestion des modifications utilisateur** 

| Préparation aux modifications | Statut   | Notes/étapes suivantes | Propriétaire |
|----|----|----|-----|
| Impact sur l’utilisateur                  | Bas                  |                                                                 |                        |
| Préparation de l’utilisateur requise      | Oui                  |                                                                 |                        |
| Prêt pour les communications         | Non                   | L’e-mail de communication a été rédigé, en attente de révision.            | Équipe de communication    |
| Prêt pour la formation               | Oui                  | La formation tirera parti de la vidéo Microsoft existante.                | Équipe de formation          |

**Suivi de l’état**

| Préparation aux modifications | Statut   | Notes/étapes suivantes | Propriétaire |
|----|----|----|-----|
| État de la mise en production               | en cours          | En attente d’examen par le sponsor exécutif.               | Équipe de gestion des modifications |
| Déconnexion de la mise en production             |                      |                                                                 |                        |
| Date de publication                 |                      |                                                                 |                        |

Pour plus d’informations sur la planification de la gestion des modifications avec Teams, consultez [Créer une stratégie de gestion des modifications pour Microsoft Teams](change-management-strategy.md).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/selon les besoins

| Activité               | Description                                                                                                                                                                                                                | Cadence   | Équipe affectée |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Surveiller les modifications     | Surveillez les modifications à venir apportées au service Microsoft Teams.                                                                                                                                                                   | Jour     |               |
| Planification des modifications    | Évaluez et planifiez les nouvelles fonctionnalités et fonctionnalités, notamment les plans de communication, les campagnes de sensibilisation et la formation.                                                                                                     | Selon les besoins |               |
| Préparation de l’utilisateur             | Effectuez des campagnes de communication, de sensibilisation ou de formation ciblées pour vous assurer que les utilisateurs sont prêts pour le changement à venir.                                                                                                        | Selon les besoins |               |
| Préparation de l’équipe de support technique | Effectuez des campagnes de communication, de sensibilisation ou de formation ciblées pour vous assurer que l’équipe de support est prête. Les équipes de support peuvent inclure l’équipe de « gant blanc », les services d’assistance, le support de niveau 2 ou 3, les partenaires externes, etc. | Selon les besoins |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Évaluer l’utilisation de Teams

Une fois le pilote initial commencé, il est essentiel d’établir une cadence régulière pour mesurer l’utilisation réelle de Teams. Cela permet à votre organisation d’obtenir des insights sur la façon dont l’utilisation réelle s’aligne sur l’utilisation que vous avez prédite pendant la phase Devision. Bien que cette section se concentre sur l’utilisation de Teams, cela doit faire partie d’un effort plus large pour mesurer et évaluer Office 365 utilisation globale.

L’examen fréquent de l’utilisation au début du déploiement vous donne la possibilité de :

-   Vérifiez si les utilisateurs utilisent Teams.

-   Identifiez les défis d’adoption potentiels avant qu’ils ne créent des problèmes critiques au sein de l’organisation.

-   Déterminez s’il existe des différences entre les exigences de la phase d’vision et l’utilisation réelle.

Si l’utilisation n’est pas celle que vous attendez, cela peut être dû à un problème de déploiement, ou au plan d’adoption qui n’est pas exécuté correctement, ou à un autre problème. En fonction de la raison réelle de la faible utilisation, l’administrateur de service doit collaborer avec les équipes associées pour aider à supprimer les barrières d’utilisation.

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>Mesure de l’utilisation avec le Centre d'administration Microsoft 365

Les données d’utilisation de Teams sont disponibles dans le tableau de bord Rapports. Les données d’utilisation de Teams se trouvent dans trois rapports différents. Le premier rapport fournit une vue inter-produits de la façon dont les utilisateurs communiquent et collaborent à l’aide des différents services dans Office 365. Ce rapport est disponible ici : [Office 365 rapport des utilisateurs actifs](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Les deux autres rapports sont spécifiques à Teams et fournissent des détails supplémentaires sur l’utilisation de Teams du point de vue de l’utilisateur et de l’appareil. Les deux rapports sont disponibles ici :

[Rapport d’utilisation des périphériques de Microsoft Teams](/microsoftteams/teams-analytics-and-reports/device-usage-report)

[Rapport d’activité des utilisateurs de Microsoft Teams](/microsoftteams/teams-analytics-and-reports/user-activity-report)

#### <a name="required-permissions"></a>Autorisations requises

Les rapports d’utilisation dans le Centre d’administration sont accessibles aux personnes qui ont reçu un rôle **Administrateur général** ou un rôle d’administrateur spécifique au produit (**administrateur Exchange**, **administrateur Skype Entreprise**, **administrateur SharePoint**).

En outre, le rôle **Lecteur de rapports** est disponible pour les utilisateurs qui ont besoin d’accéder aux rapports, mais qui n’effectuent aucune tâche nécessitant des autorisations de niveau administrateur. Vous attribuez ce rôle pour fournir des rapports d’utilisation à toute personne partie prenante, pour surveiller et favoriser l’adoption. Pour plus d’informations sur les différents rôles disponibles, consultez [À propos des rôles d’administrateur Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="assessing-usage"></a>Évaluation de l’utilisation

Une fois que vous avez utilisé le tableau de bord Reporting pour mesurer l’utilisation, il est important de comparer l’utilisation mesurée par rapport aux indicateurs de réussite clés (KSI) que vous avez définis pendant la phase Devision du projet. Vous pouvez définir un KSI qui peut être défini comme une utilisation active ou indirectement lié à l’utilisation active.

Il est important d’identifier les écarts entre l’utilisation réelle et l’utilisation planifiée avant de reprendre le déploiement sur d’autres sites ou utilisateurs. Vous identifierez probablement les apprentissages organisationnels dans le cadre de cette activité que vous pouvez exploiter pour vous assurer que le lot suivant de sites ou d’utilisateurs ne rencontre pas les mêmes problèmes.

Tout d’abord, identifiez s’il s’agit d’un problème d’adoption ou technique. Commencez par examiner les éléments ci-dessous, afin de déterminer où se trouve le problème.

1.  Validez la qualité en effectuant une révision de la qualité de l’expérience (consultez [Améliorer et surveiller la qualité des appels pour Teams](monitor-call-quality-qos.md) pour plus de détails).

2.  Collaborez avec l’équipe du support technique pour vérifier qu’il n’existe aucun problème technique courant empêchant les utilisateurs d’accéder ou d’utiliser le service. Si des tendances de problème existent, utilisez la section [résolution des problèmes de point de terminaison](#endpoint-troubleshooting) plus loin dans cet article pour essayer de résoudre le problème avant d’engager le support.

3.  Collaborez avec l’équipe de formation et d’adoption pour recueillir des commentaires directs des utilisateurs (voir [Évaluer les sentiments des utilisateurs](#assess-user-sentiment) plus loin dans cet article) et pour vérifier l’efficacité des activités de sensibilisation et d’adoption.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/selon les besoins

| Activité                         | Description                                                                                                                      | Cadence   | Équipe affectée |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Mesurer l’utilisation (phase d’activation) | Mesurez et évaluez l’utilisation de Teams à mesure que les sites continuent d’être intégrés pendant la phase d’activation. Résolvez les problèmes d’utilisation en fonction des besoins. | Toutes les semaines    |               |
| Utilisation de la mesure (phase de valeur de lecteur)                           | Mesurez et évaluez l’utilisation de Teams dans la phase Valeur du lecteur (une fois le déploiement terminé). Résolvez les problèmes d’utilisation en fonction des besoins. | Toutes les deux semaines  |               |
| Mettre à jour le plan d’adoption             | Mettez à jour votre plan d’adoption en fonction de la comparaison de l’utilisation mesurée par rapport à vos objectifs de planification.                                         | Selon les besoins |               |

### <a name="references"></a>Références 

[À propos du Centre d'administration Microsoft 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Rapports d’activité dans le Centre d'administration Microsoft 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Évaluer les sentiments de l’utilisateur

Comprendre les sentiments des utilisateurs peut agir comme un indicateur clé pour évaluer la réussite de votre déploiement Teams. Les commentaires des utilisateurs peuvent entraîner des modifications au sein de votre organisation. Cela peut inclure des modifications apportées à vos plans de communication, programmes de formation ou la façon dont vous proposez un support à vos utilisateurs.

Il est important d’obtenir des commentaires tôt et de continuer à évaluer les sentiments des utilisateurs tout au long du cycle de vie du projet et au-delà. Utilisez les conseils suivants pour déterminer l’intervalle pendant lequel votre organisation va rechercher des commentaires :

-   **Début du projet** : en évaluant les sentiments des utilisateurs au début du projet, vous pouvez obtenir une vue d’ensemble de la façon dont vos utilisateurs pensent de leur expérience Teams.

-   **Après les jalons majeurs** : en collectant des commentaires tout au long du cycle de vie du projet, vous pouvez évaluer les sentiments des utilisateurs en continu et apporter des modifications en fonction des besoins. Cela est particulièrement utile après des jalons majeurs.

-   **Conclusion du projet** : L’évaluation des sentiments des utilisateurs à la fin d’un projet vous indiquera dans quelle mesure vous avez fait et où le travail doit encore être effectué, et vous permettra de comparer les résultats à l’enquête précédente.

-   **En cours** : continuez à mesurer indéfiniment le sentiment de l’utilisateur. Les changements de sentiment de l’utilisateur peuvent être dus à des modifications dans l’environnement de votre organisation ou à des modifications dans le service Teams. En évaluant les sentiments des utilisateurs à intervalles réguliers, vous pouvez comprendre les performances de vos équipes de gestion des services et la façon dont votre organisation répond aux changements dans le service Teams.

Les sentiments de l’utilisateur peuvent être évalués par de nombreuses méthodes différentes. Il peut s’agir d’enquêtes par e-mail, d’entretiens en personne ou par téléphone, ou simplement de la création d’un canal de commentaires dans Teams ou Yammer. Pour plus d’informations, consultez [Meilleures pratiques pour les méthodes de commentaires utilisateur dans Microsoft Teams](best-practices-feedback.md).

Vous pouvez également utiliser une approche à l’échelle du secteur d’activité pour évaluer les sentiments des utilisateurs appelée net promotor score (NPS), qui est décrite dans la section suivante.

### <a name="nps"></a>Nps 

Net Promoter Score (NPS) est une métrique de fidélisation des clients à l’échelle du secteur et une bonne approche à utiliser pour évaluer le sentiment des utilisateurs. NpS peut être calculé en posant deux questions : « Quelle est la probabilité de recommander Teams à un collègue ? », suivie de la question de forme libre« Pourquoi ? »

NPS est un index, compris entre -100 et 100, qui mesure la volonté d’un client de recommander le produit ou le service d’une entreprise. NPS est basé sur une enquête anonyme qui est remise aux utilisateurs par e-mail ou par d’autres moyens électroniques. NPS mesure la loyauté entre un fournisseur et un consommateur. Il se compose d’une seule question, qui demande aux utilisateurs d’évaluer leur expérience de 1 à 10, avec la possibilité de fournir des commentaires supplémentaires. Les utilisateurs sont ensuite classés en fonction des évaluations suivantes :

-   9 ou 10 sont des Promoteurs : Des passionnés fidèles qui feront la promotion de votre service et alimenteront les autres.

-   7 ou 8 sont passifs : satisfaits mais peu enthousiastes, vulnérables à un autre service ou offre.

-   De 1 à 6 sont détracteurs: clients mécontents qui peuvent endommager votre service et nuire à la croissance.

![Diagramme illustrant l’échelle NPS.](media/operate-my-service-image2.png "Ce diagramme illustre l’échelle NPS. Il montre que les classements de 0 à 6 sont des détracteurs, 7 à 8 sont passifs et 9 à 10 sont des promoteurs.")

Bien que le numéro NPS de base soit utile, vous obtenez le meilleur résultat de l’analyse des commentaires utilisateur. Ils vous aideront à comprendre pourquoi l’utilisateur recommanderait (ou non) Teams à d’autres personnes. Ces commentaires peuvent fournir des commentaires précieux pour aider les équipes de gestion du projet ou du service à comprendre les ajustements nécessaires pour fournir un service de qualité.

Pour fournir des enquêtes NPS à votre organisation, vous pouvez tirer parti de votre outil d’enquête en ligne favori.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/selon les besoins

| Activité              | Description                                                                                                                                                                         | Cadence   | Équipe affectée |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Évaluer les sentiments de l’utilisateur | Capturez et évaluez les sentiments des utilisateurs à l’aide d’enquêtes ou d’entretiens, ou via un canal de commentaires dans Teams ou Yammer.                                                                 | Selon les besoins |               |
| Mettre à jour les plans d’adoption | Favoriser le changement dans votre organisation en fonction des commentaires des utilisateurs ; cela peut inclure des modifications apportées à vos plans de communication, à vos programmes de formation ou à la façon dont vous proposez un support à vos utilisateurs. | Selon les besoins |               |

### <a name="references"></a>Références 

[Net Promoter Score](https://en.wikipedia.org/wiki/Net_Promoter)

[Utilisation de Yammer pour recueillir des commentaires](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Meilleures pratiques pour les commentaires des utilisateurs](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Gérer la qualité du réseau

De nombreux éléments de planification de base permettent d’optimiser, de dimensionner correctement et de corriger votre infrastructure réseau pour garantir un chemin d’accès efficace et de haute qualité au service Microsoft Teams. Les tâches de planification et les exigences sont abordées dans notre guide de [préparation du réseau](3-envision-evaluate-my-environment.md#network-readiness) . Les réseaux évoluent souvent au fil du temps en raison des mises à niveau, de l’expansion ou d’autres besoins de l’entreprise. Il est important de tenir compte de vos besoins pour Teams dans vos activités de planification réseau.

Bien que la planification réseau soit un aspect essentiel d’un déploiement Teams, il est tout aussi important de s’assurer que le réseau reste sain et à jour, en fonction de l’évolution des exigences métier ou techniques.

Pour garantir l’intégrité de votre réseau, un certain nombre d’activités d’opérations doivent être effectuées à intervalles réguliers.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/selon les besoins

| Activité                                                       | Description                                                                                                                                                                                                                                                                                                                                                                 | Cadence                | Équipe affectée |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| Surveiller les adresses IP et les URL Office 365                                | Surveillez les modifications apportées aux [URL Office 365 et aux plages d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges) à l’aide du [flux RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) fourni et lancez une demande de modification aux groupes de mise en réseau applicables.                                                                                                                                | Jour                  |               |
| Mettre à jour le réseau en fonction des modifications apportées aux adresses IP et aux URL Office 365 | Effectuez des mises à jour des composants réseau applicables (pare-feu, serveurs proxy, VPN, pare-feu côté client, etc.) pour refléter les modifications apportées aux [URL Office 365 et aux plages d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges).                                                                                                                                                              | Selon les besoins              |               |
| Fournir des données de construction                                          | Fournissez des informations de sous-réseau mises à jour au champion de la qualité (ou aux parties prenantes concernées) pour vous assurer que les [définitions de bâtiment dans CQD](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) sont tenues à jour. | Selon les besoins              |               |
| Implémenter la modification                                               | Implémentez les modifications sur le réseau pour prendre en charge l’évolution des exigences métier et techniques de Teams. Les éléments réseau peuvent inclure :<ul><li>Pare-feu</li><li>Vpn</li><li>Réseaux câblés et Wi-Fi</li><li>Connectivité Internet et ExpressRoute</li><li>DNS</li></ul>     | Selon les besoins              |               |
| Surveillance et création de rapports réseau                               | Surveillez le réseau de bout en bout pour connaître les tendances en matière de disponibilité, d’utilisation et de capacité à l’aide de vos outils de gestion de réseau tiers existants et des fonctionnalités de création de rapports disponibles auprès de vos fournisseurs de réseau. Utilisez les données tendances pour la planification de la capacité réseau.                                                                                                            | Quotidienne, hebdomadaire, mensuelle |               |
| Planification de capacité                                              | Collaborez avec les propriétaires de service Teams pour comprendre l’évolution des exigences métier et techniques susceptibles d’entraîner des changements de capacité supplémentaires.                                | Selon les besoins              |               |
| Résolution des problèmes et correction du réseau                        | Aidez les services d’assistance Teams, les propriétaires de services et les parties prenantes clés à résoudre les problèmes liés à la connectivité, à la fiabilité ou à la qualité de Teams. Les éléments réseau peuvent inclure :<ul><li>Pare-feu</li><li>Vpn</li><li>Réseaux câblés et Wi-Fi</li><li>Connectivité Internet et ExpressRoute</li><li>DNS</li></ul>    | Selon les besoins              |               |
| Récupération d’urgence et tests de haute disponibilité                | Effectuez régulièrement des tests de haute disponibilité et de récupération d’urgence sur l’infrastructure réseau pour vous assurer qu’elle répond aux objectifs de niveau de service (SLO) ou aux contrats de niveau de service (SLA) pour le service Teams.                                                                                                                                                  | Mois                |               |


### <a name="references"></a>Références 

[URL et plages d’adresses IP Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Création d’un schéma de données](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Évaluer et garantir la qualité 

Toutes les organisations ont besoin qu’un groupe ou un individu soit responsable de la qualité. Il s'agit du rôle le plus important dans la gestion des services. Le rôle de champion de la qualité est attribué à une personne ou à un groupe passionné par l’expérience de ses utilisateurs.
Ce rôle exige les compétences nécessaires pour cerner les tendances de l'environnement et le parrainage pour travailler avec d'autres équipes afin d'orienter les mesures correctives. En général, le meilleur candidat au rôle de Champion Qualité est le responsable du service clientèle. Selon la taille et la complexité de l’organisation, il peut s’agir de n’importe quelle personne ou groupe ayant la passion d’assurer une expérience utilisateur de haute qualité.

Le champion de la qualité tire parti des outils existants et des processus documentés, tels que le tableau de bord de qualité des appels (CQD), pour surveiller l’expérience utilisateur, identifier les tendances de la qualité et apporter des corrections si nécessaire.
Le champion de la qualité doit travailler avec les équipes respectives pour mener des actions de correction et faire rapport à un comité directeur sur les progrès et les problèmes en cours.

Lisez [Améliorer et surveiller la qualité des appels pour Teams](monitor-call-quality-qos.md), qui décrit les activités qui évaluent et fournissent des conseils de correction dans les domaines clés qui ont le plus d’impact sur l’amélioration de l’expérience utilisateur. Les conseils fournis dans cet article se concentrent sur l’utilisation du CQD comme outil principal pour signaler et examiner chaque domaine, avec un focus sur l’audio pour optimiser l’adoption et l’impact. Toutes les optimisations apportées au réseau pour améliorer l'expérience audio se traduiront aussi directement par des améliorations dans le partage de la vidéo et du bureau.

Nous vous recommandons vivement de nommer le champion de qualité dès le début. Après avoir été nominé, ils doivent commencer à se familiariser avec [le contenu de la qualité des appels monitor](monitor-call-quality-qos.md) et les supports de formation associés.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/selon les besoins

| Activité                               | Description                                                                                                                                                                                                                                                                                                 | Cadence                             | Équipe affectée |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| Nommer et former des champions de qualité | Nommer et former un champion de qualité.                                                                                                                                                                                                                                                                   | Selon les besoins                           |               |
| Effectuer des évaluations de la qualité de l’expérience (QER)     | Effectuez un QER pour identifier les tendances en matière de qualité et de fiabilité, passer en revue les cibles définies et faire rapport aux principales parties prenantes de l’organisation.                                                                                                                            | Mensuel (hebdomadaire pendant les déploiements) |               |
| Correction de lecteur                      | Coordonner les efforts de correction au sein de l’organisation en fonction des évaluations et des résultats QER.                                                                                                                                                                                                           | Selon les besoins                           |               |
| Mettre à jour les données de génération dans CQD            | Mettez à jour ou ajoutez de nouvelles définitions de bâtiment dans CQD lorsque des modifications sont apportées au réseau (voir [Charger les informations de génération](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | Selon les besoins                           |               |
| Remplir le rôle Champion de la qualité      | Responsabilité de bout en bout de la qualité dans l’organisation. Il s’agit notamment des éléments suivants :<ul><li>Assurez-vous que le QER est effectué régulièrement.</li><li>Signaler aux principales parties prenantes l’état de qualité.</li><li>Vérifiez que les définitions de données de création sont à jour.</li><li>Coordonner les efforts de correction au sein de l’organisation pour s’assurer que les utilisateurs disposent d’une expérience de haute qualité avec Teams.</li></ul>          | Jour                               |               |



### <a name="references"></a>Références 


[Charger des données de locataire et de génération dans CQD](CQD-upload-tenant-building-data.md)

[Améliorer et surveiller la qualité des appels pour Teams](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Gérer les points de terminaison

Les points de terminaison Microsoft Teams peuvent être définis comme n’importe quel PC, Mac, tablette ou appareil mobile (ou tout autre) appareil exécutant le client Teams. Le terme *point de terminaison* englobe non seulement l’appareil lui-même, mais aussi la façon dont un utilisateur se connecte à l’appareil, par exemple, en utilisant le micro ou haut-parleur intégré de l’appareil, des écouteurs ou un casque optimisé. Une fois qu’ils sont déployés, les points de terminaison ne doivent pas être oubliés. Les points de terminaison Teams nécessitent une maintenance et une maintenance continues. Les sections suivantes décrivent des domaines spécifiques sur lesquels se concentrer.

### <a name="endpoint-requirements"></a>Exigences relatives aux points de terminaison

L’un des principaux avantages de Teams est que le client est automatiquement mis à jour. Les clients sur PC et Mac sont mis à jour à l'aide d'un processus en arrière-plan qui vérifie les nouvelles versions et télécharge le nouveau client lorsque l'application est inactive. Les applications mobiles Teams sont mises à jour via leurs magasins d’applications respectifs.

Le client Teams a des exigences minimales en termes de plateforme logicielle sous-jacente. Ces exigences peuvent changer au fil du temps, et il est donc important de les surveiller pour les modifications. Par exemple, le client Teams a une version iOS minimale. Si le client utilise un navigateur Internet, le navigateur doit également être maintenu à jour. Vous trouverez la liste des plateformes prises en charge dans [Obtenir des clients pour Microsoft Teams](get-clients.md).

### <a name="endpoint-firewalls"></a>Pare-feu des points de terminaison

Les pare-feu côté client peuvent avoir un impact significatif sur l'expérience utilisateur.
Les pare-feu côté client peuvent affecter la qualité des appels et même empêcher l’établissement d’un appel. Une fois que les exclusions appropriées sur le pare-feu du client ont été configurées, elles doivent être tenues à jour en fonction des informations [contenues dans Office 365 URL et plages d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Votre fournisseur tiers aura des conseils spécifiques sur la façon de mettre à jour les exclusions.

### <a name="wi-fi-drivers"></a>Pilotes Wi-Fi

Wi-Fi pilotes peuvent être problématiques. Par exemple, un pilote peut avoir des comportements d’itinérance très agressifs entre les points d’accès, ce qui peut entraîner un basculement de point d’accès inutile, entraînant une mauvaise qualité des appels. Un pilote de Wi-Fi peu performant peut être découvert par le biais d’un examen de la qualité de l’expérience (pour plus d’informations, consultez [Améliorer et surveiller la qualité des appels pour Teams](monitor-call-quality-qos.md) ). Il est essentiel d’implémenter un processus axé sur la qualité qui surveille les nouveaux Wi-Fi pilotes et garantit qu’ils sont testés avant d’être déployés sur le public d’utilisateurs en général.

### <a name="endpoint-management"></a>Gestion des points de terminaison

Un catalogue de points de terminaison et d’appareils d’interface pris en charge (tels que les casques) doit être disponible et géré. Ce catalogue inclut une liste des appareils approuvés qui ont été sélectionnés et validés dans le cadre des phases Devision et Onboard. En règle générale, des appareils spécifiques sont sélectionnés pour chaque type de personnage dans votre organisation afin de répondre aux besoins des attributs de ce personnage. Tous les points de terminaison ont un cycle de vie, et vous devez gérer les contrats du fournisseur, les stratégies de garantie, de remplacement, de distribution et de réparation associées à ces appareils.

### <a name="endpoint-troubleshooting"></a>Résolution des problèmes de point de terminaison

Même si vous avez suivi les instructions précédentes, les utilisateurs de votre organisation peuvent toujours rencontrer des problèmes avec Teams. Bien que le problème ne soit pas lié au point de terminaison lui-même, les symptômes du problème sont généralement exposés à l’utilisateur via le client. Les conseils suivants sont destinés à fournir des étapes générales que vous pouvez prendre pour résoudre le problème . il n’est pas destiné à être un guide de résolution des problèmes complet. Les étapes sont fournies dans un ordre spécifique, mais elles n’ont pas besoin d’être suivies explicitement et peuvent ne pas être applicables, selon la nature du problème.

1.  **Valider l’intégrité du service :** Le problème qu’un utilisateur peut rencontrer peut être lié à un événement qui affecte négativement le service Teams ou ses services dépendants. Dans un premier temps, nous vous recommandons de confirmer qu’il n’y a aucun problème de service actif. Consultez [Guide pratique pour vérifier Office 365'intégrité du service](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0).
    N’oubliez pas de vérifier l’état des services dépendants (par exemple, Exchange, SharePoint, OneDrive Entreprise). La surveillance de l’intégrité du service est décrite plus en détail dans la section précédente, [Surveiller l’intégrité du service](#monitor-service-health).

2.  **Valider la connectivité du client :** Les problèmes de connectivité provoquent des problèmes de fonctionnalité ou de connexion dans Teams. Nous vous recommandons (en particulier pour les nouveaux sites ou emplacements) de valider la connectivité au service. Vérifiez que les instructions suivantes [concernant les URL Office 365 et les plages d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges) sont suivies pour chaque site. Vous pouvez tirer parti de [l’outil d’évaluation du réseau Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) pour effectuer un test de connectivité afin de vérifier que les ports multimédias ont été ouverts correctement pour les fonctionnalités vocales cloud. Des étapes détaillées sur la façon d’exécuter les tests de connectivité sont fournies dans les conseils de [préparation du réseau](3-envision-evaluate-my-environment.md#network-readiness) .

3.  **Consultez la liste des problèmes connus :** Consultez [Résolution des problèmes teams](/MicrosoftTeams/troubleshoot/teams) pour déterminer si l’utilisateur a été affecté négativement par l’un de ces problèmes. Suivez la solution de contournement fournie (le cas échéant) pour résoudre le problème.

4.  **Visitez la communauté Microsoft Teams :** La [communauté Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) propose des espaces dédiés pour Teams. La communauté Teams fournit une liste de discussion, des billets de blog et des annonces centrées sur Teams. Vous pouvez publier une question ou rechercher des solutions à votre problème dans les discussions précédentes.

5.  **Contacter Support Microsoft :** vous pouvez contacter Support Microsoft pour les problèmes liés à Teams en ligne ou par téléphone. Pour plus d’informations, consultez [Contacter le support technique pour les produits professionnels](/microsoft-365/admin/contact-support-for-business-products).
    Pour les clients Premier, les demandes de support peuvent être lancées en suivant les instructions fournies dans [Contacter le support pour Microsoft Teams (clients Premier).](https://support.microsoft.com/premier/contacts)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/selon les besoins

| Activité                 | Description                                                                                                                                                                                                                                                                                                                                                                     | Cadence   | Équipe affectée |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Exigences relatives aux points de terminaison    | Assurez-vous que le point de terminaison Teams continue de répondre à toutes les exigences logicielles pour Teams répertoriées dans [Obtenir des clients pour Microsoft Teams](get-clients.md).                                                                                                                                                                                       | Mois   |               |
| Pare-feu des points de terminaison       | Conservez les exclusions appropriées sur le pare-feu de point de terminaison en fonction des informations [contenues dans Office 365 URL et plages d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Votre fournisseur tiers aura des conseils spécifiques sur la façon de gérer les exclusions. Abonnez-vous au [flux RSS](https://support.office.com/o365ip/rss) pour être averti automatiquement des modifications. | Selon les besoins |               |
| Pilotes Wi-Fi            | Testez et mettez à jour les pilotes Wi-Fi sur le PC. Validez les résultats à l’aide du CQD ([Améliorer et surveiller la qualité des appels pour Teams](monitor-call-quality-qos.md)).                                                                                                                                                                                                                                                                   | Selon les besoins |               |
| Gestion des points de terminaison      | Gérer le catalogue des points de terminaison et des périphériques d’interface pris en charge (tels que les casques). Gérer les contrats des fournisseurs, la garantie, la distribution, le remplacement et les stratégies de réparation.                                                                                                                                                                                                        | Mois   |               |
| Résolution des problèmes de point de terminaison | Les tâches de dépannage peuvent inclure la vérification de la connectivité, la consultation de la liste des problèmes connus, la collecte des journaux, l’analyse et l’escalade vers des fournisseurs Support Microsoft ou tiers.                                                                                                                                                                                               | Selon les besoins |               |

### <a name="references"></a>Références 

[URL et plages d’adresses IP Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[Obtenir des clients pour Microsoft Teams](get-clients.md)

[Communauté Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)

[Vérifier l’état du service Microsoft Teams](service-health.md)

[Contacter le support relatif aux produits d’entreprises - Aide de l’administrateur](/microsoft-365/admin/contact-support-for-business-products)

[Contacter le support Premier](https://support.microsoft.com/premier/contacts)

[Vidéo sur la résolution des problèmes liés à Teams](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Gérer Teams

Une fois le service Microsoft Teams déployé, vous devez effectuer plusieurs activités relatives à son administration. Les activités vont de l’administration du service et des utilisateurs individuels à la planification de la capacité et à l’approvisionnement des licences et des numéros de téléphone. Les sections suivantes couvrent certaines de ces tâches d’administration courantes.

### <a name="service-administration"></a>Administration des services

Le service Teams a plusieurs paramètres qui peuvent être configurés à l’échelle du locataire.
Les modifications apportées aux paramètres du locataire affectent tous les utilisateurs qui ont été activés pour Teams. Pour obtenir la liste détaillée de ces paramètres, consultez [Gérer les paramètres Microsoft Teams pour votre organisation](enable-features-office-365.md).

### <a name="user-administration"></a>Administration des utilisateurs

Pour prendre en charge les utilisateurs, une organisation peut avoir besoin d’un certain nombre de tâches associées: les tâches spécifiques varient d’une organisation à l’autre. En fin de compte, ces tâches doivent être gérées par une équipe de support à qui ces tâches opérationnelles ont été affectées. Les tâches suivantes sont généralement nécessaires pour prendre en charge les utilisateurs dans Teams.

#### <a name="general-tasks"></a>Tâches générales

[Gérer l’accès des utilisateurs à Microsoft Teams](user-access.md)

#### <a name="common-tasks-for-phone-system"></a>Tâches courantes pour le système téléphonique

[Affectation, modification ou suppression du numéro de téléphone d’un utilisateur](./assign-change-or-remove-a-phone-number-for-a-user.md)

[Attribuer ou modifier une adresse d'urgence d'un utilisateur](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[Ajouter, modifier ou supprimer un emplacement d’urgence pour votre organisation](/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[Créer et gérer les plans de numérotation](create-and-manage-dial-plans.md)

#### <a name="common-tasks-for-audio-conferencing"></a>Tâches courantes pour l’audioconférence

[Modifier les paramètres d’un pont d’audioconférence.](change-the-settings-for-an-audio-conferencing-bridge.md)

[Modifier les numéros de téléphone de votre pont d'audioconférence](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

[Gestion des paramètres d'audioconférence d'un utilisateur](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

[Réinitialiser le code confidentiel d’audioconférence](reset-the-audio-conferencing-pin-in-teams.md)

### <a name="license-management"></a>Gestion des licences

À mesure que votre organisation croît ou contracte, il est important que vous planifiiez les licences pour les besoins actuels et futurs. Il existe une licence Teams de base, en plus des licences pour les fonctionnalités vocales cloud [Système téléphonique](here-s-what-you-get-with-phone-system.md) et [audioconférence](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing#requirements-for-audio-conferencing).

Pour Teams, les licences de système téléphonique nécessitent des licences [plans d’appels](calling-plan-landing-page.md) associées. La licence du forfait d’appels vous permet d’effectuer et de recevoir des appels téléphoniques nationaux et/ou internationaux. Ces plans sont basés sur l’utilisation et sont associés à des pools de minutes. L’approvisionnement des [crédits de communication](what-are-communications-credits.md) vous permet de ne jamais manquer de service.

L’audioconférence permet d’utiliser des services de conférence rendez-vous payants et des services de conférence rendez-vous nationaux. Les scénarios de conférence rendez-vous gratuits ou d’appels sortants non nationaux peuvent entraîner des frais supplémentaires pour lesquels des [crédits de communication](what-are-communications-credits.md) sont requis.

Les crédits de communication peuvent compléter les licences de forfait d’appels et d’audioconférence. Les licences de forfait d’appels et les crédits de communication sont tous deux basés sur l’utilisation et doivent donc être surveillés et approvisionnés en conséquence.

Vous pouvez tirer parti du [rapport d’utilisation RTC](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) pour vous aider à surveiller votre utilisation des minutes de forfait d’appels et des crédits de communication. En fonction des résultats de cette activité, vous pouvez ajuster vos licences en conséquence. Bientôt, nous proposerons un rapport de [pools de minutes RTC](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) pour vous aider plus efficacement dans cette tâche.

### <a name="telephone-number-management"></a>Gestion des numéros de téléphone

Il existe deux méthodes pour acquérir des numéros dans Teams : vous pouvez transférer des numéros de téléphone d’un autre fournisseur ou vous pouvez approvisionner les numéros directement à partir de l’inventaire des numéros de Microsoft. Les deux méthodes sont décrites dans [Obtention de numéros de téléphone pour vos utilisateurs](getting-phone-numbers-for-your-users.md).

Il existe une limite au nombre de numéros de téléphone que vous pouvez provisionner à partir de l’inventaire des numéros de Microsoft. Les limites sont déterminées par un certain nombre de facteurs détaillés dans [Combien de numéros de téléphone pouvez-vous obtenir ?](how-many-phone-numbers-can-you-get.md).
Les limites dépendent du type de numéros : numéros de service gratuits, numéros de service payant et numéros d’abonnés (utilisateurs). Chacun a ses propres limites et doit être géré indépendamment. Si vous approchez de la limite (ou si vous avez atteint la limite), vous pouvez demander un incrément à la limite. Ce processus est décrit dans l’article du paragraphe précédent.

Il peut arriver qu’un nombre ne soit pas disponible pour être provisionné dans une région où le service est disponible. Pour plus d’informations sur le processus de demande de numéros, consultez [Gérer les numéros de téléphone de votre organisation](/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

### <a name="team-creation-optional"></a>Création d’équipe (facultatif)

Par défaut, tous les utilisateurs disposant d’une boîte aux lettres dans Exchange Online disposent des autorisations nécessaires pour créer des groupes Microsoft 365 et, par conséquent, une équipe dans Microsoft Teams. Si vous souhaitez avoir un contrôle plus strict et [restreindre la création de nouvelles équipes](assign-roles-permissions.md) (et donc la création de nouveaux groupes Microsoft 365), vous pouvez déléguer des droits de création et de gestion de groupe à un ensemble d’administrateurs. Si votre organisation souhaite utiliser cette option, consultez le processus décrit dans cet article pour permettre aux utilisateurs d’envoyer des demandes qui sont traitées par une équipe affectée.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/selon les besoins

| Activité                    | Description                                                                                                                                                                                                                                                                                                                                                                                                             | Cadence   | Équipe affectée |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Administration des services      | Administration des paramètres Teams à l’échelle du locataire.                                                                                                                                                                                                                                                                                                                                                                           | Selon les besoins |               |
| Administration des utilisateurs         | Administration des paramètres basés sur l’utilisateur et des licences dans Teams.                                                                                                                                                                                                                                                                                                                                                           | Selon les besoins |               |
| Gestion des licences          | Planifiez les besoins actuels et futurs pour les licences utilisateur et basées sur la consommation (forfaits d’appels et crédits de communication) en tirant parti du [rapport d’utilisation RTC](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) et du rapport des [pools de minutes RTC](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) . | Toutes les semaines    |               |
| Gestion des numéros de téléphone | Gérez les numéros de téléphone disponibles pour une croissance future et ajustez les niveaux d’inventaire pour répondre aux besoins de votre organisation.                                                                                                                                                                                                                                                                                                | Toutes les semaines    |               |
| Création d’équipe (facultatif)    | Passez en revue et traitez les demandes de création d’équipe.                                                                                                                                                                                                                                                                                                                                                                          | Selon les besoins |               |

<!--ENDOFSECTION-->

## <a name="improve-and-monitor-call-quality"></a>Améliorer et surveiller la qualité des appels

[Améliorer et surveiller la qualité des appels pour Teams](monitor-call-quality-qos.md) comprend un ensemble d’activités qui évaluent et fournissent des conseils de correction dans les domaines clés qui ont le plus d’impact sur l’amélioration de l’expérience utilisateur, comme illustré ci-dessous.

![Diagramme des domaines à examiner lors d’un examen de la qualité de l’expérience.](media/plan-my-service-management-image2.png "Les principaux aspects à examiner lors d’un examen de la qualité de l’expérience : audio, fiabilité et résultats de l’enquête auprès des utilisateurs.")

En évaluant et en corrigeant continuellement les zones décrites dans le guide, vous pouvez réduire leur potentiel d’impact négatif sur l’expérience utilisateur. La plupart des problèmes d'expérience utilisateur rencontrés lors d'un déploiement peuvent être regroupés dans les catégories suivantes :

-   Configuration incomplète du pare-feu ou du proxy

-   Faible couverture Wi-Fi

-   Bande passante insuffisante

-   VPN

-   Utilisation d'appareils audio non optimisés ou intégrés

-   Sous-réseaux ou périphériques réseau problématiques

Les conseils fournis dans [Améliorer et surveiller la qualité des appels pour Teams](monitor-call-quality-qos.md) se concentrent sur l’utilisation du tableau de bord de qualité des appels (CQD) Online comme outil principal pour signaler et examiner chaque domaine décrit, avec un focus sur l’audio pour optimiser l’adoption et l’impact. Toutes les optimisations apportées au réseau pour améliorer l'expérience audio se traduiront aussi directement par des améliorations dans le partage de la vidéo et du bureau.

Nous vous recommandons vivement de nommer le champion de qualité dès le début. Après avoir été nominé, ils doivent commencer à se familiariser avec le contenu dans [Améliorer et surveiller la qualité des appels pour Teams](monitor-call-quality-qos.md).

<!--ENDOFSECTION-->