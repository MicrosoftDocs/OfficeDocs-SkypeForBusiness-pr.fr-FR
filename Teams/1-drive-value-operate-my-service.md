---
title: Guide d’utilisation pour les équipes de Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Les tâches et activités requises pour la gestion des équipes services, y compris la surveillance de l’état du service, d’évaluer et de garantir l’utilisation et la qualité du réseau.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 308ca6bd3ea0dcd847756392d8db721b48aa8d08
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2018
---
# <a name="operate-my-service"></a>Utiliser mon service

Cet article donne une vue d’ensemble de la configuration requise pour l’exploitation avec succès les services vocaux de cloud pour votre organisation. Par vos services de voix de nuage de fonctionnement correctement, vous saurez que vous fournissez une expérience de haute qualité et fiable pour votre organisation.

## <a name="introduction-to-the-operations-guide"></a>Introduction au Guide d’exploitation

Le Guide vous donne une vue d’ensemble de toutes les tâches et activités requises dans le cadre de la fonction de gestion de service pour Microsoft Teams.

Gestion des services est un sujet vaste qui couvre les opérations quotidiennes du service Teams de Microsoft une fois qu’il a été déployé et activé pour les utilisateurs. Le service d’équipes englobe Microsoft Office 365 et les composants d’infrastructure qui sont déploiement sur site (par exemple, mise en réseau).

La notion de gestion des services n’est probablement pas un concept nouveau pour la plupart des organisations. Vous avez peut-être déjà implémenté les processus et les tâches qui sont associées à des services existants. Ceci dit, vous pouvez augmenter probablement de vos processus actuels lorsque vous planifiez dès aujourd'hui pour la gestion de service prendre en charge des équipes dans le futur.

Gestion de service englobe toutes les activités et processus impliqués dans la gestion des équipes de bout en bout. Comme indiqué précédemment, certains composants de gestion des services — l’infrastructure du service Office 365 comprend — sont la responsabilité de Microsoft que vous, le client, sont responsables à vos utilisateurs pour gérer les divers aspects des équipes, le réseau et vous fournissez des points de terminaison.

Les tâches et les activités dans ce guide sont groupées en huit catégories comme illustré dans le diagramme suivant. Chacune de ces catégories détaillent dans les sections suivantes.

Diagramme de ![un représentant une liste de catégories de tâches et des activités qui constituent pour les équipes de gestion des services. Le diagramme illustre également le que la gestion des services est en grande partie d’une tâche client.] Diagramme de (media/operate-my-service-image1.png "un représentant une liste de catégories de tâches et des activités qui constituent pour les équipes de gestion des services. Le diagramme illustre également le que la gestion des services est en grande partie d’une tâche client.")


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Points de décision</td><td><ul><li>Choisir le mode d’implémentation des opérations pour les équipes.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td><td><ul><li>Passez en revue le Guide des opérations dans leur intégralité.</li><li>Mettre en œuvre une stratégie des opérations qui s’aligne avec les objectifs de votre organisation pour offrir la qualité et la fiabilité du nuage des charges de travail voix.</li><li>Consultez le guide de l’examen d’expérience de la qualité.</li><li> Mettre en œuvre une stratégie des opérations pour effectuer régulièrement des analyses d’expérience de qualité pour vous assurer que votre déploiement de voix nuage fonctionne à des fonctionnalités de pointe.</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>Mappage de rôle opérationnel

La planification que vous a engagé pour les opérations au cours de la phase de Envision est critique, car les activités opérationnelles commencent lorsque les utilisateurs du premier projet pilote sont activées. Ce guide répertorie les activités et les tâches qui doivent être effectuées sur une base quotidienne, hebdomadaire, mensuelle ou en fonction des besoins de maintenance d’un déploiement d’équipes de haute qualité. Ce guide fournit des connaissances et des conseils pour savoir comment effectuer ces tâches et les activités critiques.

Il est un composant essentiel de la réussite du déploiement pour vous assurer que la planification que vous effectuez au début de la phase de Envision inclut de déterminer qui sera chargé de l’exécution des activités spécifiques. Une fois que vous avez compris les tâches et les activités qui s’appliquent à votre déploiement, ils doivent être compris et suivi par les groupes ou les personnes que vous leur attribuez.

Chaque équipe identifié doit passer en revue et s’accordent sur les tâches et les responsabilités et commencer à préparer. Cela peut inclure la formation et la préparation, la mise à jour pour le personnel, ou d’assurer les fournisseurs externes sont prêts à fournir.

Les activités et les rôles définis dans ce guide doivent être valides dans la plupart des scénarios, mais chaque déploiement d’équipes est unique ; Par conséquent, vous pouvez utiliser ce guide comme point de départ pour personnaliser les activités et les rôles par défaut pour répondre à vos besoins.

Assurez-vous que chaque équipe responsable a une bonne compréhension des activités qui sont requis pour exécuter le service. Il est essentiel que chaque équipe accepte et approuve sur leurs responsabilités dans votre organisation avant que le premier pilote ne commence.

Après qu’un accord est en place, les équipes correspondants doivent commencer à mettre leurs rôles.

<table>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Étapes suivantes</td>
<td><ul><li>Ce document permet de faciliter l’exercice de mappage de rôle opérationnel.</li><li>Rencontrez les équipes respectives de prise en charge pour attribuer des noms à chaque élément de la liste des activités requises.</li><li>Obtenir l’acceptation ou approbation sur les rôles attribués.</li><li>Assurez-vous que les équipes correspondantes ont la formation appropriée, préparation et ressources pour effectuer leurs activités requises.</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Dépendances de service aux équipes

Teams Microsoft réunit les technologies au sein d’Office 365 pour fournir un concentrateur pour le travail d’équipe. Quelques exemples ;

-   Azure Active Directory fournit les services d’authentification et d’autorisation pour les équipes.

-   Exchange Online fournit des fonctionnalités avancées telles que le gel et e-discovery.

-   SharePoint Online fournit la possibilité de partager des fichiers dans des canaux, et OneDrive pour l’entreprise fournit un mécanisme pour partager des fichiers dans une conversation privée.

Les organisations peuvent également exploiter des investissements dans l’infrastructure sur site. Par exemple, les comptes Active Directory existants sur site utilisable pour l’authentification grâce à Azure Connect d’Active Directory. Certaines versions d’Exchange Server peuvent être utilisées à la place de Exchange en ligne.

Ces technologies sont combinent pour fournir une suite enrichie, collaboration et intelligent de communication pour les utilisateurs. Cette intégration est un avantage clé des équipes, mais il lecteurs également une exigence pour la gestion de service au sein de ces technologies.

Ce guide couvre les domaines de prédilection pour gérer le service d’équipes. Le plus souvent, vous avez les plans de gestion de service en place pour les technologies de prise en charge qui dépend des équipes. Si non, vous devrez établir des plans de gestion de service pour les composants de la technologie (à la fois sur site et en ligne) également. Ceci afin de garantir à que vos utilisateurs profitent d’une expérience de haute qualité et fiable avec des équipes.

#### <a name="references"></a>Références 

[Présentation de Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview)

[Interaction entre Exchange et Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact)

[Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/sharepoint-onedrive-interact)

[Microsoft Teams et Skype pour assurer l’interopérabilité de l’entreprise](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>Activités de Guide des opérations

Les sections suivantes fournissent une vue d’ensemble des activités qui sont requises pour le service Teams de Microsoft. Ils incluent des référence à des outils, des informations contextuelles et du contenu supplémentaire pour vous aider à comprendre l’activité et d’aider à des initiatives de préparation.

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>Fonctionnement du service Moniteur

Il est important que vous compreniez le fonctionnement global du service Teams de Microsoft de sorte que vous pouvez proactive alerter les autres utilisateurs de votre organisation d’un événement qui affecte le service. Comme décrit précédemment, les équipes dépend d’autres services Office 365 comme Azure Active Directory, Exchange Online, SharePoint Online et OneDrive pour les entreprises. Pour cette raison, il est tout aussi important de surveiller l’état de santé des services dépendants.

Incorporer cette activité dans votre processus de gestion des incidents pour informer proactivement les utilisateurs, le support technique et vos équipes d’opérations pour vous préparer à gérer les escalades de l’utilisateur.

Les sections suivantes décrivent les outils que vous pouvez exploiter pour surveiller le [incidents de Service] (https://technet.microsoft.com/library/office-365-service-health.aspx?f=255&MSPPError=-2147217396#Service incidents) qui affecte le service d’équipes. Un résumé des avantages de chaque outil, et lorsque vous devez utiliser chacun d’eux est inclus dans le tableau ci-dessous.

| Outil de surveillance                       | Avantages                                            | Quand utiliser                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Portail Office 365                     | Disponible à partir de n’importe quel périphérique à l’aide d’un navigateur pris en charge. | À utiliser lorsque vous ne nécessitent pas des notifications en temps réel.                                          |
| Application d’administrateur Office 365                  | Fournit des notifications de type Pousser vers votre appareil mobile.  | Lorsque vous avez besoin notification des incidents de service alors que vous êtes en déplacement.                  |
| Microsoft System Center               | Intégration avec Microsoft System Center.           | Vous avez besoin de fonctionnalités avancées de surveillance et de la prise en charge de la notification.                       |
| API de Communications Service Office 365 | Accès par programme à l’intégrité du service Office 365.   | Vous nécessitent une intégration avec un outil de surveillance des parties 3e ou que vous souhaitez créer votre propre solution. |

> [!NOTE]
> Seuls les individus qui sont assignés du rôle **d’administrateur global** ou **l’administrateur de service** peuvent afficher le fonctionnement du service.

### <a name="monitoring-with-the-office-365-portal"></a>Surveillance avec le portail Office 365

Le [portail Office 365](https://portal.office.com/) fournit un [tableau de bord de fonctionnement du Service](https://portal.office.com/adminportal/home#/servicehealth) où vous pouvez afficher l’état actuel du service aux équipes en plus des services qui en dépendent.

### <a name="monitoring-with-the-mobile-app"></a>Surveillance à l’aide de l’application mobile

L’application d’administration d’Office 365 est disponible sur Apple iOS, Android et Windows (PC et mobile). L’application fournit des informations sur le fonctionnement des services et des modifications à venir les administrateurs de service. L’application prend en charge les notifications de type Pousser vous prévenir presque immédiatement après un avis a été validé. Cela vous permet de rester informé sur l’état, la santé et toutes les modifications à venir pour le service. La prise en charge de notification rend l’outil d’analyse recommandé pour les administrateurs. Pour plus d’informations, voir :

[Application de Mobile d’administration d’Office 365](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[Télécharger l’application Mobile de l’administrateur Office 365](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>Surveillance à l’aide de Microsoft System Center

Microsoft System Center est une plate-forme de gestion intégrée que permet de gérer les centre de données, les périphériques client et hybride cloud d’environnements informatiques. Les administrateurs d’Office 365 qui utilisent System Center maintenant ont la possibilité d’importer le Pack d’administration Office 365, qui leur permet d’afficher toutes les communications de service dans le Gestionnaire d’opérations dans System Center. À l’aide de cet outil vous permet d’accéder à l’état de vos services auxquels vous êtes abonnés, les incidents de service actifs et résolus et vos communications centre de messages (modifications à venir). Pour plus d’informations, consultez le suivant [le billet de blog](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true).

Si vous utilisez System Center pour surveiller les équipes service santé (et les services qui en dépendent), vous pouvez personnaliser davantage le pack d’administration pour alerter ou avertir les groupes spécifiques ou des personnes qui ont été identifiés pour réagir aux incidents.
Ces groupes peuvent inclure des propriétaires de services, services, groupes de support technique de troisième niveau et de deuxième niveau et gestionnaires d’incidents dans votre organisation.

### <a name="monitoring-for-advanced-scenarios"></a>Pour les scénarios avancés de surveillance

Vous pouvez surveiller le fonctionnement du service et les modifications à venir en tirant parti de l’API de Communications Service Office 365 pour accéder par programme des modifications et la santé du service Office 365. Cette API permet de créer votre propre contrôle outil ou connecter vos outils d’analyse existants pour les communications de service d’Office 365, potentiellement simplifiant le mode de la surveillance de votre environnement. Pour plus d’informations, consultez [Office 365 pour les développeurs d’entreprise](https://msdn.microsoft.com/library/jj984343(v=office.15).aspx).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/en fonction des besoins

| Activité               | Description                                                                                                                                                                                                               | Cadence   | Équipe affectée |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Fonctionnement du service Moniteur | Surveillance proactive de la santé du service Teams de Microsoft (et les services dépendants) en utilisant les outils disponibles. Incluent les services qui en dépendent : OneDrive de Online, SharePoint Online, Exchange pour les entreprises, Azure Active Directory. | En temps réel |               |
| Notification d’incident  | Notifier les parties prenantes internes des événements qui affectent le service d’équipes. Les parties prenantes internes peuvent inclure les utilisateurs, les services et les responsables de l’incidents.                                                                          | En fonction des besoins |               |

### <a name="references"></a>Références 

[Comment vérifier l’intégrité du service Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[Vérifiez l’intégrité du Service pour les équipes de Microsoft](https://docs.microsoft.com/microsoftteams/service-health)

[Continuité d’activité et de fonctionnement du Service](https://technet.microsoft.com/library/office-365-service-health.aspx)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>Gérer les changements d’organisation

Teams de Microsoft est un service en nuage. Qui s’accompagne de la capacité de fournir les nouvelles fonctions et fonctionnalités à un rythme rapide. Fournir des innovations continues fournit un avantage évident pour les entreprises, mais ces modifications doivent être gérés de façon appropriée au sein de votre organisation afin d’éviter une résistance ou escalade de votre service d’assistance.

Mises à jour aux équipes sont déployées automatiquement à vos utilisateurs. Vos utilisateurs auront toujours le client et les fonctionnalités disponibles dans le service d’équipes plus récente. Il n’est pas possible de gérer le déploiement des mises à jour des équipes à vos utilisateurs, par conséquent, il est extrêmement important gérer le changement, par le biais de programmes d’adoption, de formation et de communication efficaces. Si vos utilisateurs sont conscients de la modification, informés des avantages et habilitées à exploiter les nouvelles capacités de&mdash;il sera en mesure de s’adapter plus rapidement et la modification de l’accueil.

### <a name="monitoring-for-change"></a>Surveillance des modifications

La première étape de la gestion des changements consiste à surveiller les modifications qui sont planifiées pour les équipes. La meilleure source pour la surveillance de ces modifications est le [Plan d’évolution Office 365](https://products.office.com/business/office-365-roadmap), qui répertorie les fonctionnalités qui sont actuellement en cours de développement, déployée sur les clients, ou ont lancé entièrement. Vous pouvez rechercher pour les fonctionnalités spécifiques aux équipes en utilisant le filtre fourni, ou vous pouvez télécharger le programme vers un fichier Excel pour une analyse ultérieure. Pour chaque fonctionnalité, le programme donne une brève description, ainsi que la date de publication prévue.

Dans le [blog d’équipes Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog), vous pouvez obtenir des informations sur les meilleures pratiques, les tendances et les informations sur les mises à jour les équipes. Vous attendre à trouver les mises à jour principales des équipes à annoncer ici. Vous pouvez également vous abonner au blog via un flux RSS. Vous pouvez ensuite ajouter [le flux RSS](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) directement dans un canal d’équipes, afin que toutes les informations importantes sont remies directement dans les équipes.

Toutes les fonctionnalités qui sont libérées sont documentées dans les [Notes de version pour les équipes de Microsoft](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de).
Vous trouverez ici une liste des fonctionnalités qui ont été publiées pour bureau, web et les périphériques mobiles. Le même ensemble de notes de publication sont également disponibles dans l’onglet Notes de version dans les [Équipes de Microsoft T-Bot](https://docs.microsoft.com/microsoftteams/t-bot).

Se familiariser avec les ressources disponibles et assurez-vous que vous affectez des propriétaires d’applicables pour surveiller les modifications.

### <a name="planning-for-change"></a>Pour modifier la planification

Maintenant que vous êtes conscient des modifications à venir pour le service des équipes, l’étape suivante consiste à préparer et planifier en conséquence. Évaluez chaque modification pour déterminer les modifications qui nécessitent la communication, des campagnes de sensibilisation, de formation des utilisateurs pour les équipes de support ou des utilisateurs ou des campagnes d’évaluation et de l’adoption de fonctionnalité. C’est le rôle principal d’une équipe de gestion des modifications dans votre organisation. Ci-dessous est une collection d’exemples de tables qui peuvent vous aider à planifier les modifications.

[//]: # (L’étendue de colonnes et l’étendue de lignes dans cette table sont merveilleux, mais non pris en charge dans la démarque, au moins que le rowspan est. C’est que je pourrais obtenir. Peut-être l’intégralité doit redéfinir.)

#### <a name="feature-cloud-recording-release-date-january-2018"></a>Fonction : Nuage d’enregistrement (date de publication : janvier 2018)

**Suivi général**
| Modifier le niveau de préparation | État   | Notes/étapes suivantes | Propriétaire |
|----|----|----|-----|
| Révision légale   | Terminé     | Cette fonctionnalité est une condition préalable à la formation de l’équipe d’intégration. | Équipe de projet  |

**Gestion des modifications techniques**
| Modifier le niveau de préparation | État   | Notes/étapes suivantes | Propriétaire |
|----|----|----|-----|
| Changements informatiques requis          | Oui                  | Administrateur doit activer l’enregistrement pour les utilisateurs identifiés.      | L’équipe de support           |
| Préparation technique complète | Oui                  |                                                                 | L’équipe de support  
         |
**Gestion des modifications utilisateur** 
| Modifier le niveau de préparation | État   | Notes/étapes suivantes | Propriétaire |
|----|----|----|-----|
| Impact sur les utilisateurs                  | Bas                  |                                                                 |                        |
| Préparation de l’utilisateur      | Oui                  |                                                                 |                        |
| Communications prêtes         | Non                   | E-mail de communication a été élaboré, en attente de révision.            | Équipe de communications    |
| Formation prêts à l’emploi               | Oui                  | Formation exploiteront vidéo de Microsoft existant.                | Formation de l’équipe          |

**Suivi de l’état**
| Modifier le niveau de préparation | État   | Notes/étapes suivantes | Propriétaire |
|----|----|----|-----|
| Statut de lancement               | en cours          | Révision en cours par le soutien de la direction.               | Équipe de gestion des modifications |
| Mise à jour hors connexion             |                      |                                                                 |                        |
| Date de publication                 |                      |                                                                 |                        |

Pour plus d’informations sur la planification de la gestion des modifications avec les équipes, voir [Création d’une stratégie de gestion des modifications pour les équipes de Microsoft](https://docs.microsoft.com/microsoftteams/change-management-strategy).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/en fonction des besoins

| Activité               | Description                                                                                                                                                                                                                | Cadence   | Équipe affectée |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Moniteur pour modification     | Surveillez les modifications à venir au service de Teams de Microsoft.                                                                                                                                                                   | Chaque jour     |               |
| Pour modifier la planification    | Évaluation et planification de nouvelles fonctionnalités et fonctions, y compris les plans de communication, des campagnes de sensibilisation et des formations.                                                                                                     | En fonction des besoins |               |
| Préparation de l’utilisateur             | Effectuer une communication ciblée, sensibilisation ou campagnes de formation afin de garantir aux utilisateurs sont prêtes pour la modification à venir.                                                                                                        | En fonction des besoins |               |
| Prise en charge de la préparation de l’équipe | Effectuer une communication ciblée, sensibilisation ou campagnes de formation afin de garantir à que l’équipe de support est prêt. Les équipes de support peuvent inclure l’équipe de « blanc GANT », services, niveau 2 ou niveau 3 prise en charge, les partenaires externes et ainsi de suite. | En fonction des besoins |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>Évaluer l’utilisation des équipes

Après le début de l’essai pilote initial, il est essentiel d’établir une cadence normale pour mesurer l’utilisation des équipes réelle. Ainsi, votre organisation pour obtenir des informations sur l’utilisation réelle comment s’aligne avec vous prévue au cours de la phase de prévoir l’utilisation de la. Bien que cette section se concentre sur l’utilisation d’équipes, il doit faire partie d’un effort plus large pour mesurer et évaluer l’utilisation d’Office 365 globale.

Consulter l’utilisation fréquemment au début du déploiement vous donne la possibilité de :

-   Contrôler si les utilisateurs utilisent des équipes.

-   Identifier les défis adoption potentiels avant de créer des problèmes critiques dans l’organisation.

-   Comprendre que s’il existe des différences entre les conditions de phase Envision et l’activité réelle.

Si l’utilisation n’est pas le résultat escompté, il peut s’agir d’un problème de déploiement ou le plan d’adoption n’est pas en cours de problème exécutée correctement, ou que d’autres. En fonction de la raison réelle derrière l’utilisation faible, l’administrateur de service doit collaborer avec les équipes associées qui aide à supprimer les obstacles de l’utilisation.

### <a name="measuring-usage-with-the-office-365-admin-center"></a>Mesure de l’utilisation avec le centre d’administration Office 365

Les données d’utilisation des équipes sont disponibles dans le panneau de commandes de création de rapports. Vous trouverez les données d’utilisation des équipes dans trois rapports différents. Le premier rapport fournit une vue de produit vectoriel d’utilisateurs comment communiquent et de collaborent à l’aide de divers services dans Office 365. Ce rapport se trouve ici : [rapport sur les utilisateurs actifs Office 365](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

Les deux autres États sont spécifiques aux équipes et fournissent davantage de détails sur l’utilisation des équipes à partir d’un utilisateur et d’un point de vue de périphérique. Les deux rapports sont disponibles ici :

[Rapport d’utilisation du périphérique Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Rapport d’activité utilisateur Microsoft Teams](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>Autorisations requises

Les rapports d’utilisation dans le centre d’administration est accessible par les personnes qui ont été affectés à un rôle **d’administrateur Global** ou un rôle spécifiques au produit admin (**administrateur Exchange**, **Skype pour l’administrateur d’entreprise**, **SharePoint administrateur**).

En outre, le rôle de **lecteur de rapports** est disponible pour les utilisateurs qui ont besoin d’accéder aux rapports, mais n’exécutent pas les tâches qui nécessitent des autorisations de niveau administrateur. Vous affectez ce rôle pour fournir des rapports d’utilisation à toute personne qui est une parties prenantes, à l’adoption du moniteur et de lecteur. Pour plus d’informations sur les différents rôles disponibles, reportez-vous à la section [rôles d’administration sur Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="assessing-usage"></a>Évaluation de l’utilisation

Une fois que vous avez utilisé le tableau de bord des rapports pour mesurer l’utilisation, il est important de comparer l’utilisation mesurée par rapport à des indicateurs clés de succès (KSIs) que vous avez définies au cours de la phase du projet Envision. Vous pouvez définir un KSI qui peut être défini en tant qu’activité active, ou qui est indirectement lié à l’état actif de l’utilisation.

Il est important d’identifier les éventuelles variations entre utilisation réelle et planifiée avant de reprendre le déploiement sur les autres sites ou d’utilisateurs. Probablement, vous allez identifier les apprentissages d’organisation dans le cadre de cette activité que vous pouvez exploiter pour vous assurer que le lot suivant de sites ou d’utilisateurs ne rencontrent les mêmes problèmes.

Tout d’abord, déterminer s’il s’agit d’un problème technique et/ou d’adoption. Commencez par rechercher les éléments ci-dessous, dans l’ordre, pour déterminer la cause du problème.

1.  Valider la qualité en effectuant un [Examen d’expérience de la qualité](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service#quality-of-experience-review-guide).

2.  Travailler avec l’équipe de support technique pour vérifier qu’il n’y a aucun problème technique des tendances afin d’empêcher les utilisateurs d’accéder à ou l’utilisation du service. Si les tendances n’existent pas, utilisez la section [résolution des problèmes de point de terminaison](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service#endpoint-troubleshooting) , plus loin dans cet article pour tenter de résoudre le problème avant de contacter le support technique.

3.  Travailler avec l’équipe de formation et d’adoption pour recueillir les commentaires des utilisateurs (voir le [sentiment de l’utilisateur évaluer](https://docs.microsoft.com/MicrosoftTeams/1-drive-value-operate-my-service#assess-user-sentiment) plus loin dans cet article) et à contrôler l’efficacité des activités de sensibilisation et d’adoption.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/en fonction des besoins

| Activité                         | Description                                                                                                                      | Cadence   | Équipe affectée |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Utilisation de la mesure (phase de prise en charge) | Mesurer et évaluer l’utilisation des équipes pendant la phase de prise en charge, comme les sites continuent à être onboarded. Résoudre les problèmes d’utilisation si nécessaire. | Toutes les semaines    |               |
| Utilisation de la mesure                    | Mesurer et évaluer l’utilisation des équipes dans la phase de lecteur de valeur (une fois que le déploiement a été effectuée). Résoudre les problèmes d’utilisation si nécessaire. | Deux fois par semaine  |               |
| (phase de valeur de lecteur)              |                                                                                                                                  |           |               |
| Mise à jour du plan d’adoption             | Mettre à jour votre plan d’adoption en fonction de comment mesurée compare l’utilisation de cibles de votre planification.                                         | En fonction des besoins |               |

### <a name="references"></a>Références 

[Sur le centre admin de Office 365](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Rapports d'activité dans le centre d’administration Office 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>Évaluer le sentiment de l’utilisateur

Comprendre le sentiment de l’utilisateur peut agir comme un indicateur clé pour mesurer la réussite de votre déploiement d’équipes. Commentaires d’utilisateur peut entraîner des modifications dans votre organisation ; Cela peut inclure les modifications apportées à vos plans de communication, des programmes de formation ou de la manière que vous proposez un support à vos utilisateurs.

Il est important d’obtenir rapidement des commentaires et de poursuivre l’évaluation le sentiment de l’utilisateur tout au long du cycle de vie du projet et au-delà. Utilisez les instructions suivantes pour déterminer l’intervalle dans lequel votre organisation recherche vos commentaires :

-   **Début du projet**: en évaluant le sentiment de l’utilisateur au début du projet, vous pouvez obtenir une vue au plus tôt dans la façon dont vos utilisateurs opinion à propos de leur expérience des équipes.

-   **Après des jalons majeurs**: en recueillant des commentaires tout au long du cycle de vie du projet, vous pouvez évaluer le sentiment de l’utilisateur sur une base continue et procédez aux modifications nécessaires. Ceci est particulièrement utile après des jalons majeurs.

-   **Conclusion du projet**: évaluer le sentiment de l’utilisateur à la fin d’un projet vous indiquera comment vous avez fait et où travail doit toujours être effectuée et vous permettent de comparer les résultats par rapport à l’enquête précédente.

-   **Permanente**: continuer à mesurer le sentiment de l’utilisateur indéfiniment. Les modifications apportées dans le sentiment de l’utilisateur est peut-être en raison de modifications dans l’environnement de votre organisation, ou dans le service d’équipes. Par mesurer le sentiment de l’utilisateur à intervalles réguliers, vous pouvez comprendre la qualité d’exécution de vos équipes de gestion de service, et comment votre organisation répond aux modifications dans le service d’équipes.

Sentiment de l’utilisateur peut être évaluée par le biais de nombreuses méthodes différentes. Il peut s’agir d’e-mail enquêtes, en personne ou les entretiens par téléphone-style ou tout simplement en créant une chaîne de commentaires dans les équipes ou Yammer. Pour plus d’informations, consultez [méthodes conseillées pour les méthodes de commentaires d’utilisateur dans des équipes de Microsoft](https://docs.microsoft.com/microsoftteams/best-practices-feedback).

Vous pouvez également utiliser une approche à l’échelle de l’industrie afin d’évaluer le sentiment de l’utilisateur appelé Lactococcal net score (NPS), qui est décrite dans la section suivante.

### <a name="nps"></a>NPS 

Score de promoteur de réseau (NPS) est une mesure de la fidélité client pétaoctet et une bonne approche à utiliser pour évaluer le sentiment de l’utilisateur.

NPS peut être calculé en demandant à deux questions : « allez-vous recommander des équipes à un collègue ? », suivi par la question de la forme libre, « Pourquoi ? »

Le serveur NPS est un index, comprise entre – 100 et 100, qui mesure la volonté du client pour recommander des produits d’une société ou un service. NPS est basée sur un sondage anonyme qui est remis aux utilisateurs par courrier électronique ou autre moyen électronique. NPS mesure la fidélité entre un fournisseur et un consommateur. Il se compose d’une seule question, qui demande à l’utilisateur d’évaluer leur expérience de 1 à 10, avec la possibilité de fournir des commentaires supplémentaires. Les utilisateurs sont alors classés selon les niveaux suivants :

-   9 ou 10 sont des facteurs : fidèles passionnés chargées de promouvoir votre service et d’autres de carburant.

-   7 ou 8 sont passif : satisfait mais pas enthousiaste, vulnérable à un autre service ou une autre offre.

-   De 1 à 6 sont détracteurs : insatisfaction de la clientèle qui peut endommager votre service et entraver la croissance.

![Ce diagramme illustre l’échelle du serveur NPS. Il montre que les classements de 0 à 6 sont des détracteurs, sont passif de 7-8 et 9 et 10 sont des facteurs de.] (media/operate-my-service-image2.png "Ce diagramme illustre l’échelle du serveur NPS. Il montre que les classements de 0 à 6 sont des détracteurs, sont passif de 7-8 et 9 et 10 sont des facteurs de.")

Bien que le nombre de base NPS est utile, vous obtiendrez le meilleur parti de l’analyse des commentaires de l’utilisateur. Elles vous aidons à comprendre pourquoi l’utilisateur serait (ne) est recommandé aux équipes à d’autres personnes. Ces commentaires peuvent fournir des commentaires précieux pour aider le projet ou les équipes de gestion de service comprennent les adaptations nécessaires pour fournir un service de qualité.

Pour fournir des enquêtes NPS à votre organisation, vous pouvez exploiter vos favoris de sondage en ligne.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Quotidiennes/hebdomadaires/mensuelles/comme nécessaire des tâches

| Activité              | Description                                                                                                                                                                         | Cadence   | Équipe affectée |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Évaluer le sentiment de l’utilisateur | Capturer et évaluer le sentiment de l’utilisateur à l’aide des enquêtes ou à des entretiens, ou via un canal de commentaires dans les équipes ou Yammer.                                                                 | En fonction des besoins |               |
| Mettre à jour des plans d’adoption | Changement de lecteur de votre organisation en fonction des commentaires des utilisateurs ; Cela peut inclure les modifications apportées à vos plans de communication, des programmes de formation ou de la manière que vous proposez un support à vos utilisateurs. | En fonction des besoins |               |

### <a name="references"></a>Références 

[Score du promoteur NET](https://en.wikipedia.org/wiki/Net_Promoter)

[À l’aide de Yammer pour recueillir les commentaires](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[Pratiques recommandées pour les commentaires des utilisateurs](https://docs.microsoft.com/microsoftteams/best-practices-feedback)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>Gérer la qualité du réseau

De nombreux éléments de planification de base aller en optimisation, redimensionnement et correction de votre infrastructure réseau pour assurer un chemin d’accès de haute qualité et efficace pour le service Teams de Microsoft. Les tâches de planification et les exigences sont décrites dans nos précédents conseils de [Préparation de son réseau](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness) . Souvent, les réseaux évoluent dans le temps en raison des mises à niveau, une expansion ou autres besoins de l’entreprise. Il est important que vous compte pour vos besoins pour les équipes dans vos activités de planification de réseau.

Bien que la planification du réseau est un aspect essentiel d’un déploiement d’équipes, il est tout aussi important d’assurer le réseau reste sain et reste en cours, selon l’évolution des exigences techniques ou professionnelles.

Pour garantir l’intégrité de votre réseau, un certain nombre d’activités d’opérations doit être effectuées à des intervalles réguliers.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/en fonction des besoins

| Activité                                                       | Description                                                                                                                                                                                                                                                                                                                                                                 | Cadence                | Équipe affectée |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| Surveiller Office 365 IPs et des URL                                | Surveiller toute modification apportée à l' [Office 365 URL et les plages d’adresses IP](https://aka.ms/o365ips) à l’aide fournie du [flux RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) et de lancer une demande de modification à des groupes d’accès réseau applicables.                                                                                                                                | Chaque jour                  |               |
| Mise à jour du réseau en fonction des modifications à Office 365, adresses IP et des URL | Mettre à jour les composants applicables de réseau (pare-feu, serveurs proxy, VPN, pare-feu côté client et ainsi de suite) afin de refléter les modifications apportées à [Office 365 URL et les plages d’adresses IP](https://aka.ms/o365ips).                                                                                                                                                              | En fonction des besoins              |               |
| Fournir des données de construction                                          | Fournir les informations de sous-réseau mis à jour le champion de la qualité (ou les parties prenantes concernées) pour garantir que la [Création de définitions de CQD](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) sont à jour. | En fonction des besoins              |               |
| Modification de la mise en œuvre                                               | Mettre en œuvre les modifications sur le réseau pour la prise en charge de modification équipes impératifs commerciaux et techniques. Les éléments de réseau peuvent inclure :<ul><li>Pare-feu</li><li>Réseaux privés virtuels</li><li>Filaires et les réseaux Wi-Fi</li><li>Connectivité Internet et ExpressRoute</li><li>DNS</li></ul>     | En fonction des besoins              |               |
| Réseau de surveillance et de reporting                               | Surveiller le réseau de bout en bout pour la disponibilité, l’utilisation et les tendances de capacité à l’aide de vos outils de gestion réseau tiers existant et reporting des capacités disponibles à partir de vos fournisseurs réseau. Utiliser les données relatives aux tendances pour la planification de la capacité réseau.                                                                                                            | Quotidien, hebdomadaire, mensuel |               |
| Planification de capacité                                              | Collaborez avec les responsables de service aux équipes pour comprendre l’évolution des besoins métiers et techniques qui peuvent entraîner des modifications de la capacité supplémentaire. Exploiter les résultats de l' [Agent de planification de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner) pour s’assurer qu’une bande passante suffisante est disponible pour Microsoft Teams.                               | En fonction des besoins              |               |
| Résolution des problèmes de réseau et de correction                        | Aider les équipes services propriétaires de services et les principales parties prenantes pour dépanner et résoudre les problèmes liés à la qualité, de fiabilité ou de connectivité aux équipes. Les éléments de réseau peuvent inclure :<ul><li>Pare-feu</li><li>Réseaux privés virtuels</li><li>Filaires et les réseaux Wi-Fi</li><li>Connectivité Internet et ExpressRoute</li><li>DNS</li></ul>    | En fonction des besoins              |               |
| Reprise après sinistre et test de la haute disponibilité                | Effectuez régulièrement haute disponibilité et reprise après sinistre sur l’infrastructure réseau pour vous assurer qu’elle satisfait aux objectifs de niveau de service indiquée (SLA) les contrats de niveau de service (SLA) pour le service des équipes de test.                                                                                                                                                  | Tous les mois                |               |


### <a name="references"></a>Références 

[Module de réseau](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner)

[URL et plages d'adresses IP Office 365](https://aka.ms/o365ips)

[Schéma de génération de données](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>Évaluer et de garantir la qualité 

Toutes les organisations ont besoin d’un groupe ou un individu qui sera responsable de la qualité. C’est le rôle le plus important dans la gestion des services. Le rôle de spécialiste de qualité est attribué à une personne ou un groupe qui est passionné par l’expérience de leurs utilisateurs.
Ce rôle nécessite les compétences nécessaires pour identifier les tendances dans l’environnement, ainsi que le parrainage pour travailler avec d’autres équipes pour piloter la mise à jour. En général, le meilleur candidat au rôle de Champion Qualité est le responsable du service clientèle. En fonction de la taille et la complexité de l’organisation, cela peut être toute personne ou un groupe avec une passion pour assurer une expérience utilisateur de qualité.

Le champion de qualité s’appuie sur des outils existants et des processus documentés, tels qu’appeler qualité du tableau de bord (CQD) et le Guide de révision de rencontrer qualité, pour analyser l’expérience de l’utilisateur, identifient les tendances de la qualité et le lecteur de conversion lorsque cela est nécessaire.
Le champion de qualité doit collaborer avec des équipes respectives pour exécuter des actions de mise à jour et de rapport à un comité de direction sur les cours et les problèmes ouverts.

La [Qualité de Guide de révision rencontrer](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) contient des activités qui évalue et fournissent des conseils de remédiation dans des domaines clés qui ont le plus grand impact sur l’amélioration du confort d’utilisation. Les instructions fournies dans le Guide de révision de l’expérience de qualité se concentre sur l’utilisation de CQD en ligne comme le principal outil de rapport et d’observer chaque zone, avec un focus sur audio afin d’optimiser l’adoption et à l’impact. Les optimisations apportées au réseau afin d’améliorer l’expérience audio auront également directement des améliorations dans le partage de vidéo et de bureau.

Nous vous recommandons vivement de vous désigner le champion de qualité dès le début. Après avoir été désigné, ils doivent commencer à se familiariser avec le contenu dans le Guide de révision d’expérience de qualité et les supports de formation associé.

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/en fonction des besoins

| Activité                               | Description                                                                                                                                                                                                                                                                                                 | Cadence                             | Équipe affectée |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| Nommer et de former des champion(s) de qualité | Nommer et former un champion(s) de qualité.                                                                                                                                                                                                                                                                   | En fonction des besoins                           |               |
| Procédez à des examens d’expérience de qualité     | Effectuer un examen d’expérience de la qualité (QER) pour identifier les tendances de qualité et de fiabilité, consultez contre les cibles définies et signalez vers les principales parties prenantes de l’organisation.                                                                                                                            | Mensuel (une fois par semaine au cours des déploiements) |               |
| Conversion du lecteur                      | Coordonner les efforts de réparation dans l’organisation basée sur les évaluations de QER et les conclusions.                                                                                                                                                                                                           | En fonction des besoins                           |               |
| Mettre à jour des données de création de CQD            | Mettre à jour ou ajouter de nouvelles définitions de bâtiment dans CQD lorsque des modifications sont apportées au réseau (voir [les informations de construction de téléchargement](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)). | En fonction des besoins                           |               |
| Remplir le rôle de qualité Champion(s)      | Responsables de bout en bout de la qualité de l’organisation. Cela inclut :<ul><li>Assurez-vous que le QER est effectuée régulièrement.</li><li>Rapport pour les principales parties prenantes sur l’état de qualité.</li><li>Assurez-vous que les données de construction que les définitions sont à jour.</li><li>Coordonner les efforts de réparation dans l’entreprise pour s’assurer que les utilisateurs disposent d’une expérience de haute qualité avec des équipes.</li></ul>          | Chaque jour                               |               |



### <a name="references"></a>Références 

[Découvrez CQD](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Academy?SOFTrainings=Leverage%20the%20Investigate%20Media%20Quality%20using%20CQD%20Videos)

[Informations de construction de téléchargement](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[Qualité de Guide de révision d’expérience](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>Gérer les points de terminaison

Les points de terminaison Teams Microsoft peuvent être définis comme n’importe quel PC, Mac, Tablet PC ou périphérique mobile (ou tout autre) exécutant les équipes clients. Le *point de terminaison* du terme englobe non seulement le périphérique proprement dit, mais comment un utilisateur se connecte au périphérique — par exemple, en utilisant intégré micro du périphérique ou haut-parleurs, écouteurs par ou un casque optimisé. Une fois qu’elles sont déployées, les points de terminaison ne doivent pas oubliés. Les points de terminaison des équipes nécessitent la maintenance et l’entretien permanent. Les sections suivantes décrivent de se concentrer sur des zones spécifiques.

### <a name="endpoint-requirements"></a>Exigences en matière de point de terminaison

Un des principaux avantages des équipes est que le client est mis à jour automatiquement. Les clients sur les PC et les Mac sont mis à jour à l’aide d’un processus en arrière-plan qui vérifie les versions nouvelles et télécharge le nouveau client lorsque l’application est inactive. Les équipes, les applications mobiles sont mises à jour par le biais de leurs magasins respectifs app.

Le client d’équipes a des exigences minimales en termes de la plate-forme logicielle sous-jacente. Ces exigences peuvent changer au fil du temps, et il est donc important de surveiller les modifications. Par exemple, le client d’équipes dispose d’une version d’e/s minimale. Si le client utilise un navigateur internet, le navigateur doit être mis à jour aussi bien. Vous trouverez une liste des plates-formes prises en charge dans [Obtenir des Clients pour les équipes de Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).

### <a name="endpoint-firewalls"></a>Pare-feux de point de terminaison

Les pare-feu côté client peuvent avoir un impact significatif sur l’expérience de l’utilisateur.
Côté client pare-feu peuvent affecter la qualité des appels et même empêcher un appel à partir de l’établissement. Après que les exclusions appropriées sur le pare-feu du client ont été configurées, ils doivent être mis à jour selon les informations contenues dans [les URL d’Office 365 et de plages d’adresses IP](https://aka.ms/o365ips). Votre fournisseur tiers ont des instructions spécifiques sur la mise à jour des exclusions.

### <a name="wi-fi-drivers"></a>Pilotes Wi-Fi

Pilotes Wi-Fi peuvent être problématiques. Par exemple, un pilote peut avoir très agressifs comportements itinérants entre points d’accès qui peuvent induire des points d’accès inutiles de commutation, conduisant à l’appel de mauvaise qualité. Un pilote Wi-Fi médiocres peut être découvert par un examen d’expérience de la qualité (voir la [Qualité d’expérience révision Guide](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/CloudVoice-working/Teams/downloads/quality-of-experience-review-guide.docx?raw=true) pour plus de détails). Il est essentiel d’implémenter un processus de qualité qui surveille les nouveaux pilotes Wi-Fi et s’assure qu’ils sont testés avant le déploiement de la population des utilisateurs généraux.

### <a name="endpoint-management"></a>Gestion de point de terminaison

Un catalogue des périphériques d’interface (tels que les casques) et les points de terminaison pris en charge doit être disponible et mise à jour. Ce catalogue comprend une liste d’appareils approuvés qui ont été sélectionnés et validés dans le cadre des phases de vision et intégration. En général, les périphériques spécifiques sont sélectionnés pour chaque type de personnage dans votre organisation et répond aux besoins les attributs de ce personnage. Tous les points de terminaison ont un cycle de vie, et il est nécessaire de gérer les contrats fournisseurs, la garantie, la remplacement, la distribution et la réparation des stratégies associées à ces périphériques.

### <a name="endpoint-troubleshooting"></a>Résolution des problèmes de point de terminaison

Même si vous avez suivi les recommandations du précédente, les utilisateurs de votre organisation peuvent toujours exécuter des problèmes avec les équipes. Bien que le problème n’est peut-être pas avec le point de terminaison, les symptômes du problème sont généralement émises par le client à l’utilisateur. Le guide suivant est destiné à fournir les étapes générales que vous pouvez prendre pour résoudre le problème ; Il n’est pas conçue pour être un guide de dépannage complet. Les étapes sont fournies dans un ordre spécifique, mais ils ne doivent être suivies de manière explicite et peuvent ne pas être applicables, en fonction de la nature du problème.

1.  **Valider le fonctionnement du service :** Le problème que rencontre peut-être un utilisateur peut être lié à un événement qui affecte le service d’équipes ou de ses services dépendants. Dans un premier temps, nous vous recommandons de vous confirmez qu'aucun problème de service actif. Consultez [comment vérifier l’intégrité du service Office 365](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0).
    N’oubliez pas de vérifier l’état des services dépendants (exemples ; Exchange, SharePoint, OneDrive pour les entreprises). Surveillance de l’intégrité du service est décrit plus en détail dans la section **fonctionnement du Service de surveillance.**

2.  **Vérifier la connectivité du client :** Problèmes de connectivité provoquent des fonctionnalités ou des problèmes de connexion dans des équipes. Nous vous recommandons (en particulier pour les nouveaux sites ou emplacements) que vous validez la connectivité au service. Assurez-vous que les instructions suivantes de [Office 365 URL et les plages d’adresses IP](https://aka.ms/o365ips) sont suivie pour chaque site. Vous pouvez tirer parti de l' [Outil d’évaluation réseau Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) pour effectuer un test de connectivité pour valider que les ports de support ont été ouverts correctement pour les fonctionnalités vocales de nuage. Les étapes détaillées sur la façon d’exécuter les tests de connectivité sont fournies dans le Guide de [Préparation de son réseau](https://docs.microsoft.com/MicrosoftTeams/3-envision-evaluate-my-environment#network-readiness) .

3.  **Vérifier la liste de problèmes connus :** Consultez la [liste des problèmes connus des équipes](https://docs.microsoft.com/MicrosoftTeams/known-issues) pour déterminer si l’utilisateur a été affecté par un de ces problèmes. Suivez la solution de contournement fournie (s’il y en a un) pour résoudre le problème.

4.  **Visitez la Communauté Microsoft Tech :** La [Communauté de technique d’équipes Microsoft](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams) offre des espaces dédiés pour les équipes. La Communauté des équipes fournit une liste de discussion, des billets de blog et des annonces centrés sur les équipes. Vous pouvez publier une question ou rechercher des discussions précédentes solutions à votre problème.

5.  **Contactez le support technique de Microsoft :** Vous pouvez contacter le Support Microsoft pour les problèmes avec les équipes en ligne ou par téléphone. Pour plus d’informations, reportez-vous à la section [Contact de prise en charge des équipes de Microsoft](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
    Pour le Premier clients, prise en charge des demandes peuvent être lancées en suivant les instructions à [Contacter le Support pour les équipes de Microsoft (clients Premier)](https://support.microsoft.com/premier/contacts).

### <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/en fonction des besoins

| Activité                 | Description                                                                                                                                                                                                                                                                                                                                                                     | Cadence   | Équipe affectée |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Exigences en matière de point de terminaison    | Assurez-vous que le point de terminaison de l’équipe continue à répondre à toutes les exigences de logiciels pour les équipes [d’obtenir des clients pour les équipes de Microsoft](https://docs.microsoft.com/microsoftteams/get-clients).                                                                                                                                                                                       | Tous les mois   |               |
| Pare-feux de point de terminaison       | Tenir à jour les exclusions appropriées sur le pare-feu du point de terminaison selon les informations contenues dans l’article [Office 365 URL et les plages d’adresses IP](https://aka.ms/o365ips) . Votre fournisseur tiers ont des instructions spécifiques sur la façon de maintenir les exclusions. S’abonner à ce [flux RSS](https://support.office.com/en-us/o365ip/rss) pour être automatiquement informé des modifications. | En fonction des besoins |               |
| Pilotes Wi-Fi            | Tester et mettre à jour les pilotes Wi-Fi sur le PC. Valider les résultats à l’aide de CQD ([Qualité d’expérience révision Guide](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness-pr/blob/CloudVoice-working/Teams/downloads/quality-of-experience-review-guide.docx?raw=true)).                                                                                                                                                                                                                                                                   | En fonction des besoins |               |
| Gestion de point de terminaison      | Mettre à jour le catalogue de points de terminaison pris en charge et les périphériques d’interface (tels que les casques). Gérer les contrats fournisseurs, de garantie, de distribution, de remplacement et de réparer des stratégies.                                                                                                                                                                                                        | Tous les mois   |               |
| Résolution des problèmes de point de terminaison | Peut inclure des tâches de dépannage ; vérification de la connectivité, la consultation de la liste de problèmes connus, journal de collecte, l’analyse et mise à niveau vers le Support de Microsoft ou des fournisseurs tiers.                                                                                                                                                                                               | En fonction des besoins |               |

### <a name="references"></a>Références 

[URL et plages d'adresses IP Office 365](https://aka.ms/o365ips)

[Obtenir des clients pour Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients)

[Communauté technique Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Problèmes connus pour les équipes de Microsoft](https://docs.microsoft.com/MicrosoftTeams/known-issues)

[Vérifiez l’intégrité du Service pour les équipes de Microsoft](https://docs.microsoft.com/microsoftteams/service-health)

[Contacter le support Office 365 pour les entreprises - Aide de l'administrateur](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b?ui=en-US&rs=en-US&ad=US)

[Premier de contact](https://support.microsoft.com/premier/contacts)

[Résolution des problèmes vidéo d’équipes](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>Gestion des équipes

Une fois que le service Teams de Microsoft a été déployé, vous devez effectuer plusieurs activités relatives à l’administration. La plage des activités d’administrer le service et les utilisateurs individuels à la planification de la capacité et la mise en service des numéros de téléphone et de licences. Les sections suivantes décrivent certaines de ces tâches d’administration courantes.

### <a name="service-administration"></a>Administration du service

Le service d’équipes a plusieurs paramètres qui peuvent être configurés à l’échelle du locataire.
Les modifications apportées aux paramètres clients affectent tous les utilisateurs qui ont été activés pour les équipes. Pour obtenir une liste détaillée de ces paramètres, reportez-vous à la section [Activer les fonctionnalités d’équipes Microsoft dans votre organisation d’Office 365](https://docs.microsoft.com/microsoftteams/enable-features-office-365).

### <a name="user-administration"></a>Administration des utilisateurs

Pour prendre en charge les utilisateurs, une organisation peut nécessiter un nombre quelconque de tâches connexes, les tâches spécifiques varient d’une organisation à l’autre. Au final, ces tâches doivent être gérées par une équipe de support qui a été affectée à ces tâches opérationnelles. Les tâches suivantes sont fréquemment requis pour prendre en charge des utilisateurs dans des équipes.

#### <a name="general-tasks"></a>Tâches générales

[Gérer l'accès des utilisateurs à Microsoft Teams](https://docs.microsoft.com/microsoftteams/user-access)

#### <a name="common-tasks-for-phone-system"></a>Tâches courantes de système téléphonique

[Attribuer, modifier ou supprimer un numéro de téléphone pour un utilisateur](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/assign-change-or-remove-a-phone-number-for-a-user)

[Attribuer ou modifier une adresse d'urgence d'un utilisateur](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[Ajouter, modifier ou supprimer un emplacement pour votre organisation d'urgence](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[Créer et gérer les plans de numérotation](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/create-and-manage-dial-plans)

#### <a name="common-tasks-for-audio-conferencing"></a>Tâches courantes d’audioconférence

[Modifier les paramètres pour un pont d'audioconférence](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge)

[Modifier les numéros de téléphone de votre pont d'audioconférence](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge)

[Gérer les paramètres d'audioconférence d'un utilisateur](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/manage-the-audio-conferencing-settings-for-a-user)

[Réinitialiser le code confidentiel d'audioconférence d'un utilisateur](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/reset-the-audio-conferencing-pin-for-a-user)

### <a name="license-management"></a>Gestion des licences

Tandis que votre organisation grandit ou contrats, il est important que vous prévoyez de licences pour les besoins actuels et futurs. Il existe une licence de base aux équipes, en plus des licences pour les fonctionnalités vocales de cloud ([Système téléphonique](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system?ui=en-US&rs=en-US&ad=US) et [Audioconférence](https://products.office.com/skype-for-business/audio-conferencing)).

Pour les équipes, les licences de système téléphonique nécessitent des licences [d’Appel Plan](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365) associés. Appeler le Plan de gestion de licences vous permet d’effectuer et de recevoir des appels nationaux et/ou internationaux. Ces plans sont basée sur l’utilisation et ont minutes pools associés. Mise en service des [Crédits de Communications](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) veillera à que vous n’exécutez jamais hors service.

Conférence audio permet de conférence tolled accès à distance et des services de conférence de numérotation nationaux. Conférences à distance gratuit ou scénarios d’appels sortants non domestiques peuvent entraîner à payer des frais supplémentaires pour les [Crédits de Communications](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) sont nécessaires.

Crédits de communications peuvent compléter les licences appelant planifier et audioconférence. Appel de planifier des licences et crédits de Communication sont basées sur l’utilisation et par conséquent doivent être surveillés et mis en service en conséquence pour.

Vous pouvez utiliser le [rapport d’utilisation de TLS](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) pour vous aider à surveiller l’utilisation de l’appel de planifier les minutes et les crédits de Communications. Basé sur les résultats de cette activité, vous pouvez ajuster vos licences en conséquence. Bientôt, nous proposerons un rapport de [pool de minute RTPC](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) pour faciliter cette tâche plus efficacement.

### <a name="telephone-number-management"></a>Gestion de numéros de téléphone

Il existe deux méthodes pour acquérir des numéros dans les équipes : vous pouvez porter des numéros de téléphone à partir d’un autre fournisseur, ou vous pouvez configurer les numéros directement à partir de stocks de nombre de Microsoft. Les deux méthodes sont décrites dans [mise en route des numéros de téléphone pour vos utilisateurs](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).

Il existe une limite à la quantité de numéros de téléphone que vous pouvez configurer à partir du stock de numéro de Microsoft. Les limites sont déterminées par un certain nombre de facteurs détaillés dans [le nombre de numéros de téléphone vous obtiendrez](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get).
Les limites dépendent du type des nombres : numéro payant exempt de numéros de service, les numéros de service payant et abonné (utilisateur). Chacun a ses propres limites et doit être géré séparément. Si vous êtes proche de la limite (ou vous avez atteint la limite), vous pouvez appliquer d’un incrément à la limite. Ce processus est décrit dans l’article ci-dessus.

Il peut arriver lorsqu’un nombre n’est pas disponible pour être mis en service dans une région où le service est disponible. Pour plus d’informations sur le processus pour les numéros de demande, voir [Gérer les numéros de téléphone pour votre organisation](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

### <a name="team-creation-optional"></a>Création de l’équipe (facultative)

Par défaut, tous les utilisateurs avec une boîte aux lettres dans Exchange Online ont des autorisations pour créer des groupes d’Office 365 et, par conséquent, une équipe dans Teams de Microsoft. Si vous souhaitez avoir un contrôle plus strict et [restreindre la création de nouvelles équipes](https://docs.microsoft.com/MicrosoftTeams/assign-roles-permissions#permissions-to-create-teams) (et donc la création de nouveaux groupes d’Office 365), vous pouvez déléguer la création d’un groupe et les droits de gestion pour un ensemble d’administrateurs. Si votre organisation souhaite exercer cette option, consultez la procédure décrite dans cet article pour permettre aux utilisateurs de soumettre des demandes qui sont traités par une équipe affectés.

<!--ENDOFSECTION-->

## <a name="dailyweeklymonthlyas-needed-tasks"></a>Tâches quotidiennes/hebdomadaires/mensuelles/en fonction des besoins

| Activité                    | Description                                                                                                                                                                                                                                                                                                                                                                                                             | Cadence   | Équipe affectée |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| Administration du service      | Gestion des paramètres des équipes au niveau du client.                                                                                                                                                                                                                                                                                                                                                                           | En fonction des besoins |               |
| Administration des utilisateurs         | Gestion des paramètres utilisateur et les licences dans les équipes.                                                                                                                                                                                                                                                                                                                                                           | En fonction des besoins |               |
| Gestion des licences          | Planifier les besoins actuels et futurs pour l’utilisateur et la consommation de licences (Plans d’appel et les crédits de Communication) en exploitant le rapport [rapport d’utilisation RTPC](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) et [pool de minute RTPC](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) . | Toutes les semaines    |               |
| Gestion de numéros de téléphone | Gérer les numéros de téléphone disponibles pour la croissance future et de régler les niveaux de stock afin de répondre aux besoins de votre organisation.                                                                                                                                                                                                                                                                                                | Toutes les semaines    |               |
| Création de l’équipe (facultative)    | Processus de révision et les demandes de création d’équipe.                                                                                                                                                                                                                                                                                                                                                                          | En fonction des besoins |               |

<!--ENDOFSECTION-->

## <a name="quality-of-experience-review-guide"></a>Qualité de Guide de révision d’expérience
Le Guide de révision de rencontrer de qualité possède un ensemble d’activités qui évalue et fournir des conseils de remédiation dans des domaines clés qui ont le plus grand impact pour améliorer l’expérience de l’utilisateur, comme illustré dans la figure ci-dessous.

![Les points essentiels à examiner au cours d’une qualité d’expérience examinent : audio, de fiabilité et de résultats de l’enquête,.] (media/plan-my-service-management-image2.png "Les points essentiels à examiner au cours d’une qualité d’expérience examinent : audio, de fiabilité et de résultats de l’enquête,.")

En évaluant en permanence et en corriger les zones décrites dans ce document, vous pouvez réduire leur peuvent affecter négativement l’expérience de l’utilisateur. La plupart des problèmes d’expérience utilisateur rencontré dans un déploiement peuvent être regroupées dans les catégories suivantes :

-   Configuration de pare-feu ou proxy incomplète

-   Une mauvaise couverture de Wi-Fi

-   Bande passante insuffisante

-   VPN

-   Utilisation de non optimisées ou intégrées des périphériques audio

-   Sous-réseaux problématiques ou des périphériques réseau

Les instructions fournies dans le Guide de révision de l’expérience de qualité est consacré à l’aide en ligne du tableau de bord de qualité appeler (CQD) comme outil principal pour signaler et examinez chaque zone décrite, en mettant l’accent sur audio afin d’optimiser l’adoption et à l’impact. Les optimisations apportées au réseau afin d’améliorer l’expérience audio auront également directement des améliorations dans le partage de vidéo et de bureau.

Nous vous recommandons vivement de vous désigner le champion de qualité dès le début. Après avoir été désigné, ils doivent commencer à se familiariser avec le contenu du [Guide de révision expérience de qualité](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/quality-of-experience-review-guide.docx?raw=true).

<!--ENDOFSECTION-->