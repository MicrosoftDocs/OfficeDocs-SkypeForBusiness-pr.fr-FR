---
title: Utiliser CQD pour gérer la qualité des appels et des réunions dans Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies, gageames
audience: admin
description: Découvrez comment analyser et gérer les performances multimédias en temps réel dans Microsoft Teams à l’aide du tableau de bord de qualité des appels (CQD).
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 182cd98825948a4d7732513c9f2eb3a884539354
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794582"
---
#  <a name="use-cqd-to-manage-call-and-meeting-quality-in-microsoft-teams"></a>Utiliser CQD pour gérer la qualité des appels et des réunions dans Microsoft Teams 

Cet article vous aidera , l’administrateur Teams ou l’ingénieur support technique, à développer un processus de surveillance et de maintenance de la qualité des appels et des réunions pour votre organisation à l’aide du tableau de bord de qualité des appels (CQD) Microsoft Teams. Nos conseils mettent l’accent sur les scénarios de qualité audio, car toutes les améliorations réseau que vous apportez pour améliorer l’expérience audio se traduisent par des améliorations dans la vidéo et le partage.

Les deux [modèles CQD organisés](https://aka.ms/QERtemplates) constituent la clé de ce guide : nous vous recommandons de les télécharger avant de suivre les instructions de cet article.

Cet article part du principe que vous avez déjà [configuré le CQD](turning-on-and-using-call-quality-dashboard.md).


## <a name="categories-to-monitor-and-maintain"></a>Catégories à surveiller et à gérer

Une fois que vous avez déployé les réunions et la voix dans Teams, vous avez besoin d’un plan pour la surveillance et la maintenance continues. Cela garantit que Teams s’exécute toujours de façon optimale. Ce plan doit inclure les zones clés répertoriées ci-dessous. Vous devez également établir des cibles pour les métriques de qualité et un plan de dépannage et d’isolation des problèmes lorsqu’ils se produisent.

<table>
<thead>
<tr class="header">
<th>Catégorie</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Qualité des appels</strong></td>
<td>
<p>Décomposez les métriques par appels internes (au sein de votre organisation, tels que VPN, WiFi, câblé) ou des appels externes</p>
<p>Décomposer les métriques en créant ou en réseau</p>
<p>Appels VPN</p>
<p>Appels utilisant TCP, UDP ou proxy</p>
</td>
</tr>
<tr class="even">
<td><strong>Fiabilité des appels</strong></td>
<td><p>Identifier et corriger les problèmes de réseau ou de pare-feu</p>
<p>Obtenir des insights sur les pourcentages d’échecs de configuration et de suppression des appels</p>
<p>Découvrez où se produisent la majorité des échecs de configuration et de suppression d’appel</p>
</td>
</tr>
<tr class="odd">
<td><strong>Enquête auprès des utilisateurs</strong></td>
<td>
<p>Utiliser les données Rate My Call pour en savoir plus sur l’expérience réelle des utilisateurs</p>
<p>Où se produisent les mauvaises expériences?</p>
<p>Mettre en corrélation la mauvaise expérience avec la qualité, la fiabilité et les appareils des appels</p>
</td>
</tr>
<tr class="even">
<td><strong>Appareils</strong></td>
<td><p>Découvrez quels microphones et haut-parleurs sont le plus couramment utilisés et leur impact sur la qualité des appels</p>
<p>Les pilotes audio, vidéo, USB et WiFi de prise en charge sont-ils régulièrement corrigés ?</p>
</td>
</tr>
<tr class="odd">
<td><strong>Clients</strong></td>
<td>
<p>Découvrez quels types de clients et versions sont utilisés et leur impact sur la qualité et la fiabilité des appels  </p>
</ol></td>
</tr>
</tbody>
</table>

En évaluant et en corrigeant en permanence les zones décrites dans cet article, vous pouvez réduire leur risque d’affecter négativement vos utilisateurs. La plupart des problèmes d’utilisateur peuvent être regroupés dans les catégories suivantes :

-   Configuration incomplète du pare-feu ou du proxy
-   Faible couverture Wi-Fi
-   Bande passante insuffisante
-   VPN
-   Versions et pilotes client incohérents ou obsolètes
-   Appareils audio non optimaux ou intégrés
-   Sous-réseaux ou périphériques réseau problématiques

Grâce à une planification et une conception appropriées avant de déployer Teams ou Skype Entreprise Online, vous pouvez réduire la quantité d’efforts nécessaires pour maintenir des expériences de haute qualité.

Cet article se concentre sur l’utilisation du tableau de bord de qualité des appels (CQD) Online comme principal outil pour signaler et examiner chaque domaine, en mettant l’accent sur l’audio pour optimiser l’adoption et l’impact. Toute amélioration apportée au réseau pour améliorer l’expérience audio se traduira également directement par des améliorations dans le partage vidéo et de bureau.

Pour accélérer votre évaluation, [deux modèles CQD organisés](https://aka.ms/qertemplates) sont fournis : l’un est destiné à la gestion de tous les réseaux et l’autre est filtré pour les réseaux gérés (internes) uniquement. Bien que les rapports de modèle Tous les réseaux soient configurés pour afficher les informations de génération et réseau, ils peuvent toujours être utilisés pendant que vous travaillez à la collecte et au chargement des informations de construction. Le chargement d’informations de génération dans CQD permet au service d’améliorer la création de rapports en ajoutant des informations personnalisées sur la création, le réseau et l’emplacement, tout en différenciant les sous-réseaux internes des sous-réseaux externes. Pour plus d’informations, consultez [Mappage de bâtiments](CQD-building-mapping.md).

### <a name="intended-audience"></a>Public prévu

Cet article est destiné aux partenaires et aux parties prenantes des clients ayant des rôles tels que Responsable de collaboration/Architecte, Consultant, Spécialiste de la gestion des modifications/adoption, Responsable support/Support technique, Responsable réseau, Responsable de bureau et Administration informatique.

Cet article est également destiné à être utilisé par le ou les champions de qualité désignés. Pour plus [d’informations, consultez le rôle Champion qualité](4-envision-plan-my-service-management.md#the-quality-champion-role).


## <a name="what-is-quality"></a>Qu’est-ce que la qualité ?

Dans ce contexte, la qualité est une combinaison de métriques de service et d’expérience utilisateur.


### <a name="service-metrics"></a>Métriques de service

Les métriques de service sont constituées de métriques clientes spécifiques. Au cours de chaque appel, le client collecte les données de télémétrie pour l’appel et envoie un rapport à la fin de chaque appel accessible ultérieurement dans CQD ou dans [l’analytique des appels par utilisateur](set-up-call-analytics.md). Ces métriques incluent (mais ne sont pas limitées à) :

-   Mauvais flux (entrant et sortant)
-   Taux d’échec de l’installation
-   Taux d’échecs de suppression


#### <a name="poor-stream-rate"></a>Taux de flux médiocre

Le faible taux de flux (PSR) représente le pourcentage global de flux dont la qualité est médiocre. Cette métrique est destinée à mettre en évidence les domaines dans lesquels votre organisation peut concentrer ses efforts afin d’avoir l’impact le plus fort sur la réduction de cette valeur et l’amélioration de l’expérience utilisateur, c’est pourquoi les [réseaux managés](#managed-versus-unmanaged-networks) sont le principal objectif lorsque vous examinez la RSE. Les utilisateurs externes sont également importants, mais l’investigation diffère d’une organisation à l’autre. Envisagez de fournir les meilleures pratiques pour les utilisateurs externes et d’examiner les appels externes indépendamment de l’ensemble de l’organisation.

La mesure réelle dans CQD varie en fonction de la charge de travail, mais pour les besoins de cet article, nous nous concentrons principalement sur la mesure _du pourcentage audio médiocre_ . La RSE est constituée des cinq moyennes de métriques réseau décrites dans le tableau suivant. Pour qu’un flux soit classé comme médiocre, une seule métrique doit dépasser le seuil défini. CQD fournit le « Poor Due To... » mesures pour mieux comprendre la condition à l’origine de la classification du flux comme médiocre. Pour en savoir plus, lisez [la classification de flux dans CQD](stream-classification-in-call-quality-dashboard.md).

> [!Note]
> CQD fournit le « Pauvre en raison de... » mesures pour mieux comprendre la condition à l’origine de la classification du flux comme médiocre.


##### <a name="audio-poor-quality-metrics"></a>Métriques de qualité audio médiocres

| Moyenne des métriques     | Description     | Expérience utilisateur |
|-------------|-----------------|-----------------|
| Gigue \>30 ms        | Il s’agit de la modification moyenne du délai entre les paquets successifs. Teams et Skype Entreprise peuvent s’adapter à certains niveaux de gigue grâce à la mise en mémoire tampon. Ce n’est que lorsque la gigue dépasse la mise en mémoire tampon qu’un participant remarque les effets de la gigue.      | Les paquets arrivant à des vitesses différentes provoquent un son robotique de la voix d’un haut-parleur.   |
| Taux de \>perte de paquets 10 % ou 0,1        | Il s’agit souvent d’un pourcentage de paquets perdus. La perte de paquets affecte directement la qualité audio, des petits paquets perdus individuels qui n’ont presque aucun impact sur les pertes de rafales dos à dos qui entraînent une coupure complète de l’audio.     | Les paquets supprimés et n’arrivant pas à leur destination prévue provoquent des lacunes dans les médias, ce qui entraîne des syllabes et des mots manqués, ainsi qu’une vidéo et un partage agitées. |
| Durée aller-retour \>500 ms        | Il s’agit du temps nécessaire pour obtenir un paquet IP du point A au point B et du point A au point A. Ce délai de propagation réseau est lié à la distance physique entre les deux points et la vitesse de la lumière, et inclut une surcharge supplémentaire prise par les différents appareils dans le chemin d’accès réseau.      | Les paquets qui prennent trop de temps pour arriver à leur destination provoquent un effet walkie-talkie.   |


##### <a name="why-do-we-prefer-to-use-streams-instead-of-calls"></a>Pourquoi préférons-nous utiliser des flux plutôt que des appels ?

Les flux nous indiquent quelle étape particulière de l’appel était médiocre : sortante ou entrante. Lorsque vous examinez l’analyse des appels pour un appel médiocre, déterminez si l’appel médiocre était dû au flux de cet appelant (sortant) ou au flux de l’appelant (entrant). Il est encore plus important de déterminer quel flux a un impact sur la qualité des appels pour les conférences. Si vous examinez uniquement les données d’appel, vous verrez le nombre de conférences auxquelles une personne participe, mais vous ne verrez pas les personnes qui sont des haut-parleurs actifs, en partageant le plus d’écran.

Les données d’appel vous donnent des métriques d’utilisation, mais elles ne vous mèneront pas nécessairement à la cause racine de la mauvaise qualité des appels. En examinant la direction du flux, vous pouvez identifier des facteurs tels qu’un appel qui n’est pas sur un réseau géré, un appel d’un non-employé (par exemple, un fournisseur ou une personne sur un autre réseau). Dans ce cas, si la connexion réseau de l’autre personne était médiocre, l’appel entier sera marqué comme médiocre. Vous ne pouvez rien faire sur les facteurs externes. Ces données ne sont donc pas utiles.

La direction du flux peut également vous aider à identifier les appareils ou clients problématiques.

 - Par exemple, si vous avez un budget limité pour les appareils et que vous souhaitez fournir des appareils uniquement pour les utilisateurs audio lourds, utilisez le rapport d’utilisation audio (VoIP) et filtrez les flux sortants et les conférences. Recherchez les utilisateurs audio à volume élevé qui parlent dans des microphones intégrés . Ceux-ci peuvent être corrélés à une qualité d’appel plus faible (et vous souhaiterez peut-être fournir des périphériques audio pour ces personnes). Pour plus de clarté, vous pouvez filtrer l’utilisation des paquets, ce qui vous permet de cibler des utilisateurs audio particulièrement volumineux. 

  - Un autre exemple concerne le partage d’écran. Si un client utilise un ancien client Teams, les performances de partage d’écran peuvent être affectées. Vous pouvez résoudre ce problème en hiérarchisant les mises à niveau des clients pour les personnes qui partagent beaucoup d’écran.

 - En identifiant la direction d’un flux à l’origine d’une qualité d’appel médiocre, vous pouvez déterminer si vous avez un problème lié à la qualité de service ou à la bande passante. Si vous n’avez pas entièrement implémenté QoS, ou si vous marquez uniquement des paquets sur le client et non dans le flux entrant, vous risquez de voir une qualité d’appel plus faible. En examinant la direction du flux, vous pouvez obtenir une vue plus granulaire de la perte de paquets, de la latence ou de la gigue dans une direction spécifique. 

   - Par exemple, supposons qu’un utilisateur se plaint de l’audio robotisé lors d’une connexion câblée (gigue). En examinant le flux et la direction, vous pouvez déterminer que le problème se produit sur le flux entrant, uniquement pour un ensemble spécifique de sous-réseaux. Une fois que vous avez donné ces informations à votre équipe de mise en réseau, elle peut les suivre jusqu’à un accélérateur WAN mal configuré qui ne contournait pas le trafic multimédia. Une fois que l’équipe réseau reconfigure l’accélérateur WAN, la gigue disparaît et la qualité des appels s’améliore. 


#### <a name="setup-failure-rate"></a>Taux d’échec de l’installation

Le taux d’échec de l’installation, également appelé mesure pourcentage d’échec d’installation _d’appel total_ dans CQD, correspond au nombre de flux dans lesquels le chemin d’accès multimédia n’a pas pu être établi entre les points de terminaison au début de l’appel.

Cela représente tout flux multimédia qui n’a pas pu être établi. Étant donné la gravité de l’impact de ce problème sur l’expérience utilisateur, l’objectif est de réduire cette valeur au plus près de zéro que possible. Une valeur élevée pour cette métrique est plus courante dans les nouveaux déploiements avec des règles de pare-feu incomplètes qu’un déploiement mature, mais il est toujours important de les surveiller régulièrement.

Cette métrique est calculée en prenant le nombre total de flux qui n’ont pas pu être configurés divisé par le nombre total de flux qui ont soumis un enregistrement de détails d’appel réussi (CDR) :

-   **Taux d’échec de l’installation** = Nombre total d’échecs d’installation d’appels / Nombre total de flux disponibles cdr

#### <a name="drop-failure-rate"></a>Taux d’échecs de suppression

Le taux d’échec de baisse, également appelé mesure _du pourcentage total d’échecs supprimés d’appel_ dans CQD, est le pourcentage de flux correctement établis où le chemin d’accès du média ne s’est pas terminé normalement.

Cela représente tout flux multimédia qui s’est arrêté de manière inattendue. Bien que l’impact de cette opération ne soit pas aussi grave qu’un flux qui n’a pas pu être configuré, il affecte toujours négativement l’expérience utilisateur. Les baisses de média soudaines et fréquentes peuvent non seulement avoir un impact grave sur l’expérience utilisateur, mais elles entraînent la nécessité pour les utilisateurs de se reconnecter, ce qui entraîne une perte de productivité (sans parler de frustration).

La métrique est calculée en prenant le nombre total de flux supprimés divisé par le nombre total de flux qui ont été correctement configurés :

-   **Drop Failure Rate** = Total Call Dropped Stream Count / Total Call Setup Succeeded Stream Count

### <a name="define-your-target-metrics"></a>Définir vos métriques cibles

Cette section traite de certaines des principales métriques de service que nous utilisons pour évaluer l’intégrité des services. En évaluant en permanence et en mettant en place des efforts pour maintenir ces métriques en dessous de leurs cibles définies, vous allez vous assurer que vos utilisateurs connaissent une qualité d’appel cohérente et fiable. Comme point de départ, utilisez les cibles suggérées dans le tableau ci-dessous. Ajustez les objectifs en fonction des besoins pour atteindre vos objectifs métier.

<table>
<tr>
<th rowspan="2" colspan="2" valign="center">Type de réseau</th><th rowspan="1">Objectifs de qualité</th><th colspan="2">Objectifs de fiabilité</th></tr>
<tr><th>Taux de flux audio médiocre</th><th>Taux d’échec de l’installation</th><th>Taux d’échecs de suppression</th></tr>
<tr><td rowspan="2"><strong>All</strong></td><td>Interne</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Global</td><td>3.0%</td><td>1.0%</td><td>3.0%</td></tr>
<tr><td rowspan="5"><strong>Conférence</strong></td><td>Interne</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Interne câblé</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Wi-Fi 5 GHz internes</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Wi-Fi interne de 2,4 GHz</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Global</td><td>2.0%</td><td>0.5%</td><td>3.0%</td></tr>
<tr><td rowspan="4"><strong>P2P</strong></td><td>Interne</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Wired/Wi-Fi 5 GHz interne</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Wired/Wi-Fi 5 GHz global</td><td>2.0%</td><td>1.0%</td><td>1.0%</td></tr>
<tr><td>Global</td><td>2.0%</td><td>1.0%</td><td>3.0%</td></tr>
</table>

### <a name="user-experience"></a>Expérience utilisateur

L’analyse de l’expérience utilisateur est plus artistique que scientifique, car les métriques collectées ici ne signifient pas toujours qu’il existe un problème avec le réseau ou le service, mais plutôt qu’elles indiquent simplement que l’utilisateur perçoit un problème. CQD inclut un mécanisme d’enquête intégré ( Rate My Call (RMC) ) pour vous aider à évaluer l’expérience utilisateur globale. RMC vous donnera des insights sur les questions suivantes du point de vue de vos utilisateurs :

-   Est-ce que je sais comment utiliser la solution ?
-   La solution est-elle facile à utiliser et intuitive, et prend-elle en charge mes besoins quotidiens en matière de communication ?
-   La solution m’aide-t-elle à faire mon travail ?
-   Quelle est ma perception globale de la solution ?
-   Puis-je utiliser la solution à tout moment, où que je sois ?
-   Puis-je configurer et gérer un appel ?

#### <a name="rate-my-call"></a>Évaluer mon appel 

Rate My Call (RMC) est intégré à Teams et Skype Entreprise. Il s’affiche automatiquement après un appel sur 10, soit 10 %. Cette brève enquête demande à l’utilisateur d’évaluer l’appel et de fournir un peu de contexte pour expliquer pourquoi la qualité de l’appel a pu être médiocre. Une ou deux évaluations sont considérées comme médiocres, trois à quatre sont bonnes et cinq sont excellentes. Bien qu’il s’agit d’un indicateur en retard, il s’agit d’une métrique utile pour détecter les problèmes que les métriques de service peuvent manquer.

> [!Note]
> Le facteur humain : les utilisateurs ignorent souvent l’enquête lorsque la qualité des appels est bonne, et ils le remplissent quand la qualité des appels est mauvaise. Par conséquent, vos rapports RMC peuvent être biaisés du côté médiocre, même si les métriques de service sont bonnes.

Vous pouvez utiliser CQD pour générer des rapports sur les réponses des utilisateurs RMC, et les exemples de rapports sont inclus dans le modèle CQD. Toutefois, ils ne sont pas abordés en détail dans cet article. 

#### <a name="client-and-device-readiness"></a>Préparation du client et de l’appareil

Vous avez besoin d’une solide stratégie de client et d’appareil pour vous assurer que vos utilisateurs bénéficient d’une expérience utilisateur cohérente et positive. Quelques principes clés déterminent chaque stratégie de préparation.

##### <a name="client-readiness"></a>Préparation du client

Maintenir le client Teams à jour garantit que vos utilisateurs bénéficient toujours de la meilleure expérience possible. Microsoft publie des [mises à jour fréquentes du client Teams](teams-client-update.md) (la mise à jour s’installe en arrière-plan, sauf si vous avez désactivé cette fonctionnalité , ce que nous ne recommandons pas). Il est également important de se rappeler de corriger les pilotes réseau, vidéo, USB et audio, car ils sont souvent négligés et peuvent affecter la qualité des appels et des réunions. Envisagez d’ajouter des pilotes réseau, Wi-Fi, vidéo, USB et audio à votre processus de gestion des correctifs actuel.


##### <a name="device-readiness"></a>Préparation de l’appareil

Aucune stratégie ne peut affecter davantage l’expérience utilisateur que votre stratégie de préparation des appareils. Par exemple, les utilisateurs qui s’appuient sur les haut-parleurs et le microphone de leur ordinateur portable rencontrent beaucoup de bruit de fond lors des appels et des réunions. Teams est conçu pour fonctionner avec presque n’importe quel appareil, mais si vous rencontrez des problèmes liés à l’appareil, consultez [Téléphone pour Teams](./devices/phones-for-teams.md).


### <a name="categories-of-quality"></a>Catégories de qualité

Mettez en place un ensemble de pratiques de gestion de la qualité, ce qui vous donne les meilleures chances de qualité des appels et des réunions. Un plan de gestion de la qualité répond aux catégories suivantes :

-   **Réseau:** Qualité audio axée sur la métrique PSR (Poor Stream Ratio), l’utilisation TCP, les sous-réseaux câblés et sans fil, et l’identification de l’utilisation de proxys HTTP et VPN

-   **Terminaison:** Appareils audio et clients à jour

-   **Gestion des services :** Cette catégorie comprend deux sections :

    -   Tout d’abord, il incombe à Microsoft de gérer et de gérer les services Teams et Skype Entreprise Online.

    -   Deuxièmement, les tâches que votre organisation gère pour garantir un accès fiable au service, telles que la mise à jour des informations de génération et la maintenance des pare-feu pour les nouvelles adresses IP Office 365 à mesure que l’infrastructure est ajoutée au service.

![Graphique des catégories de qualité dans une organisation.](media/qerguide-image-categories.png "Catégories de qualité dans une organisation : gestion des services, points de terminaison et réseau.")

Passez en revue la liste suivante des tâches recommandées pour maintenir la qualité. Vous devez effectuer ces tâches régulièrement , par exemple, toutes les semaines.

#### <a name="service-management-tasks"></a>Tâches de gestion des services

Ces tâches vont de la vérification de la bande passante suffisante pour atteindre le service sans saturer les liaisons Internet, la validation de la qualité de service (QoS) sur toutes les zones réseau gérées et le maintien au-dessus de [Office 365 plages d’adresses IP sur les pare-feu](/microsoft-365/enterprise/urls-and-ip-address-ranges).

#### <a name="network-tasks"></a>Tâches réseau

Il existe deux catégories de tâches réseau : la fiabilité et la qualité. La fiabilité se concentre sur la mesure de la capacité de l’utilisateur à passer des appels avec succès et à rester connecté. La qualité se concentre sur les données de télémétrie agrégées envoyées à Teams et Skype Entreprise Online par le client de l’utilisateur pendant l’appel et après sa fin. 

Étant donné l’impact critique de la fiabilité sur l’expérience utilisateur, nous vous recommandons d’évaluer et d’examiner les métriques de fiabilité avant de vous plonger dans la qualité. 

#### <a name="endpoints-tasks"></a>Tâches de points de terminaison

Tâche principale de cette catégorie qui supprime tous les obstacles aux mises à [jour régulières du client Teams](teams-client-update.md). Par défaut, Teams se met automatiquement à jour régulièrement (sauf si vous désactivez ce paramètre, ce que nous ne recommandons pas). 

Vous devez également surveiller les appareils et fournir des mises à jour chaque fois que vous identifiez les problèmes liés à un appareil.

## <a name="use-cqd-to-manage-call-quality"></a>Utiliser CQD pour gérer la qualité des appels

Une fois que vous avez [configuré le CQD](turning-on-and-using-call-quality-dashboard.md), vous êtes prêt à l’utiliser pour gérer la qualité des appels et des réunions pour votre organisation.

La plupart des problèmes liés aux performances de Teams sont classés dans les catégories suivantes :

-   Configuration incomplète du pare-feu ou du proxy
-   Faible couverture Wi-Fi
-   Bande passante insuffisante
-   VPN
-   Versions et pilotes client incohérents ou obsolètes
-   Appareils audio non optimaux ou intégrés
-   Sous-réseaux ou périphériques réseau problématiques

Si vous prenez le temps avant de déployer Teams pour évaluer ces domaines et corriger les lacunes, vous réduisez la quantité d’efforts nécessaires pour maintenir une expérience Teams de haute qualité pour tous vos utilisateurs. Pour obtenir de l’aide sur l’évaluation de votre réseau en vue de votre déploiement Teams, lisez [Advisor for Teams](use-advisor-teams-roll-out.md) et [préparez votre réseau pour Teams](prepare-network.md).

### <a name="expectations-using-cqd"></a>Attentes à l’aide de CQD

Utilisez le tableau de bord de qualité des appels (CQD) pour obtenir des informations sur la qualité des appels effectués à l’aide de Teams et des services Skype Entreprise. CQD est conçu pour aider Teams et Skype Entreprise administrateurs et ingénieurs réseau à optimiser le réseau et à garder un œil sur la qualité, la fiabilité et l’expérience utilisateur. CQD examine les données de télémétrie agrégées pour l’ensemble d’une organisation, où les modèles globaux peuvent devenir apparents ; cela vous permet d’effectuer des évaluations éclairées et de planifier la correction. CQD fournit des rapports de métriques qui fournissent des insights sur la qualité globale, la fiabilité et l’expérience utilisateur.

Le CQD, bien qu’utile pour analyser les tendances et les sous-réseaux, ne fournit pas toujours une cause spécifique pour un scénario donné. Il est important de comprendre cela et de définir les attentes correctes lors de l’utilisation du CQD :

-   Le CQD ne fournit pas la cause racine de chaque scénario
-   Le CQD ne contiendra pas de flux de système téléphonique ou d’audioconférence
-   Le CQD appellera des domaines pour une investigation plus approfondie en fonction des tendances

### <a name="cqd-reports-overview"></a>Vue d’ensemble des rapports CQD

Utilisez le menu déroulant en haut de l’écran pour ouvrir un rapport. Pour obtenir la liste des données fournies dans chaque rapport, lisez [les données disponibles dans les rapports CQD](CQD-data-and-reports.md#data-available-in-cqd-reports).

Nouveauté de janvier 2020 : [Télécharger Power BI modèles de requête pour les](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)CQD . Modèles de Power BI personnalisables que vous pouvez utiliser pour analyser et signaler vos données CQD.


### <a name="teams-vs-skype-for-business"></a>Teams et Skype Entreprise

CQD peut générer des rapports sur Teams et Skype Entreprise. Toutefois, il peut arriver que vous souhaitiez développer un rapport pour examiner les données de télémétrie Teams distinctes de Skype Entreprise.

#### <a name="summary-reports"></a>Rapports récapitulatifs

Pour modifier la page des rapports récapitulatifs pour examiner uniquement Teams ou Skype Entreprise, sélectionnez le menu déroulant **Filtre de produit** en haut de l’écran, puis sélectionnez le produit souhaité.

![Capture d’écran du menu déroulant montrant les options de filtre.](media/qerguide-image-productfilter.png)

#### <a name="detailed-reports"></a>Rapports détaillés

Pour filtrer tous les rapports détaillés, dans la barre du navigateur, ajoutez ce qui suit à la fin de l’URL :

```PowerShell
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Exemple:**

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Pour plus d’informations sur les filtres d’URL, lisez [les rapports de filtrage](CQD-data-and-reports.md#report-filters) plus loin dans cette section.

Pour filtrer un rapport détaillé individuel, ajoutez le filtre ``Is Teams`` au rapport et définissez-le sur True ou False.

![Capture d’écran de la page Ajouter un filtre.](media/qerguide-image-addteamsfilter.png)

### <a name="managed-versus-unmanaged-networks"></a>Réseaux managés et non managés

Par défaut, tous les points de terminaison dans CQD sont classés comme externes. Dès qu’un fichier de génération est introduit, nous pouvons commencer à examiner les données de point de terminaison managé. Comme indiqué précédemment, les réseaux dans CQD sont définis comme suit :

-   Un _réseau managé_, souvent appelé interne ou interne, peut être influencé et contrôlé par l’organisation. Cela inclut le réseau local interne, le WAN distant et le VPN.
-   Un _réseau non managé_, souvent appelé externe ou externe, ne peut pas être influencé ou contrôlé par l’organisation. Un réseau d’hôtels ou d’aéroports est un exemple de réseau non géré.

### <a name="dimensions-measures-and-filters"></a>Dimensions, mesures et filtres

Une requête CQD bien formée contient les trois paramètres suivants :

-   **Dimension:** Comment je veux pivoter sur les données.

-   **Mesure:** Ce sur quoi je veux faire rapport.

-   **Filtre:** Comment je souhaite réduire le jeu de données retourné par la requête.

Une autre façon d’examiner cela est qu’une _dimension_ est la fonction de regroupement, une _mesure_ est les données qui m’intéressent, et un _filtre_ est la façon dont je veux limiter les résultats à ceux qui sont pertinents pour ma requête.

Un exemple de requête bien formée est **Show me Poor Streams [Measure] by Subnet [Dimension] for Building 6 [Filter]**. Pour plus d’informations, consultez [Dimensions et mesures disponibles dans CQD](./dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="first-vs-second"></a>Premier et deuxième 

La plupart des dimensions et mesures du CQD sont classées en premier ou en deuxième. Le CQD n’utilise pas les champs appelant/appelé , ceux-ci ont été renommés _en premier_ et _en deuxième_ , car il existe des étapes intermédiaires entre l’appelant et l’appelé. La logique suivante détermine quel point de terminaison est étiqueté en premier :

-   **Tout d’abord** , il s’agit toujours d’un point de terminaison de serveur (serveur de conférence, serveur de médiation, et ainsi de suite) si un serveur est impliqué dans le flux ou l’appel.

-   **Le deuxième** sera toujours un point de terminaison client, sauf si le flux se trouve entre deux points de terminaison de serveur.

-   Si les deux points de terminaison sont du même type, le choix est d’abord basé sur l’ordre interne de la catégorie de l’agent utilisateur. Cela garantit la cohérence de l'organisation.

Pour plus d’informations sur la détermination du premier ou du deuxième point de terminaison lorsqu’ils sont tous les deux [identiques, consultez Dimensions et mesures disponibles dans CQD](./dimensions-and-measures-available-in-call-quality-dashboard.md).

### <a name="stream-vs-call"></a>Flux et appel

Vous devez comprendre la différence entre un appel et un flux pour choisir correctement les dimensions ou mesures que vous allez examiner dans CQD. Bien que le CQD se concentre principalement sur les flux, des mesures basées sur les appels sont également disponibles.

-   **Flux:** Un _flux_ existe uniquement entre deux points de terminaison. Il n’existe qu’un seul flux pour chaque direction, et deux flux sont nécessaires pour la communication. Les flux sont utiles pour examiner les bâtiments, les réseaux ou les sous-réseaux. Dans certains cas, l’appel et le flux sont utilisés dans le nom de la mesure (par exemple, flux d’installation d’appel ou flux supprimé d’appel). Ceux-ci sont toujours classés en tant que flux.

-   **Appeler:** Un _appel_ est un regroupement de tous les flux de tous les participants. Un appel se compose, au minimum, de deux flux. Un seul appel aura au moins deux points de terminaison, chacun avec un minimum d’un flux.

Pour obtenir des conseils supplémentaires sur la question de savoir si la dimension ou la mesure fait référence à un appel ou à un flux, consultez [Dimensions et mesures disponibles dans CQD](./dimensions-and-measures-available-in-call-quality-dashboard.md)

### <a name="good-poor-and-unclassified-calls"></a>Appels bons, pauvres et non classés

Un appel est classé comme bon, médiocre ou non classé. Prenons un moment pour parler de chacun d’eux plus en détail.

-   **Bon ou pauvre :** Un bon ou un mauvais appel se compose d’un appel qui contient un ensemble complet de métriques de service, pour lequel un rapport QoE complet a été généré et reçu par le service. La détermination de la qualité ou de la mauvaise qualité d’un flux est décrite [plus haut dans cet article](#poor-stream-rate).

-   **Non classé :** Un flux non classifié ne contient pas un ensemble complet de métriques de service. Il peut s’agir d’appels courts(généralement inférieurs à 60 secondes) où les moyennes n’ont pas pu être calculées et où aucun rapport QoE n’a été généré. La raison la plus courante pour laquelle les appels ne sont pas classés est qu’il y avait peu ou pas d’utilisation des paquets. Par exemple, un participant qui participe à une réunion sur le son et ne parle jamais. Le participant reçoit, mais ne transmet pas, les médias. Sans transmission de média, aucune métrique n’est disponible pour le CQD afin de classifier le flux multimédia sortant du point de terminaison.

Pour en savoir plus, lisez [la classification de flux dans CQD](stream-classification-in-call-quality-dashboard.md).

### <a name="common-subnets"></a>Sous-réseaux courants

Les sous-réseaux courants sont des sous-réseaux privés spécifiques qui sont utilisés par les hôtels, les réseaux domestiques, les points d’accès et les zones similaires. Ces sous-réseaux sont difficiles à trier en raison de leur utilisation généralisée. Si votre organisation utilise l’un de ces sous-réseaux courants, nous vous recommandons de déplacer ce réseau vers un autre sous-réseau. Cela facilite la création de rapports dans CQD. Lorsqu’ils sont notés, les rapports du modèle Tous les réseaux ont été configurés pour exclure ces sous-réseaux afin de les éliminer comme source de mauvaise qualité. Les sous-réseaux courants sont définis ci-dessous ; leur impact varie selon l’organisation.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Lorsque vous examinez un réseau managé qui utilise un sous-réseau commun, vous devez utiliser la deuxième dimension d’adresse IP locale réflexive pour regrouper des sous-réseaux. Cette dimension contient l’adresse IP publique du point de terminaison.


## <a name="reliability-investigations"></a>Investigations de fiabilité

La première étape pour améliorer la qualité consiste à évaluer l’état de fiabilité au sein de l’organisation. Étant donné que la fiabilité est essentielle pour une expérience utilisateur positive, nous commençons par les deux composants qui mesurent la fiabilité :

1.  **Échecs de configuration :** Impossible d’établir l’appel.

2.  **Échecs de suppression :** L’appel a été établi et s’est arrêté de manière inattendue.

Tout au long de cette section, nous allons aborder les méthodes permettant d’examiner les deux domaines.

> [!NOTE]
> Tous les rapports inclus dans les modèles ne sont pas abordés dans cet article. Toutefois, les méthodes d’investigation décrites ci-dessous s’appliquent toujours. Pour plus d’informations, reportez-vous à la description individuelle du rapport.


### <a name="setup-failures"></a>Échecs d’installation

Hiérarchisez d’abord les échecs d’installation dans ce domaine, car ces échecs ont un impact négatif significatif sur l’expérience utilisateur.

Commencez votre enquête en évaluant le pourcentage d’échecs d’installation globaux pour l’organisation, puis en hiérarchisant les domaines d’investigation en fonction du pourcentage le plus élevé par génération ou réseau. 

#### <a name="setup-failure-trend-analysis"></a>Analyse des tendances des échecs de configuration

Ce rapport affiche la quantité totale de flux, les échecs d’installation de flux et le taux d’échec de l’installation du flux. Pointez sur l’une des colonnes pour afficher ses valeurs individuelles. 

##### <a name="analysis"></a>Analyse

À l’aide de ce rapport, vous pouvez répondre aux questions suivantes et déterminer votre prochaine action :

-   Quel est le pourcentage total d’échecs d’installation des appels pour le mois en cours ?

-   Le pourcentage total d’échecs d’installation des appels est-il inférieur ou supérieur à la métrique cible définie ?

-   La tendance des défaillances est-elle pire ou meilleure que le mois précédent ?

-   La tendance à l’échec augmente-t-elle, se stabilise-t-elle ou diminue-t-elle ?

Quelles que soient vos réponses à ces questions, prenez le temps d’examiner plus en détail à l’aide des sous-rapports complémentaires pour rechercher des bâtiments individuels ou des sous-réseaux qui pourraient nécessiter une correction. Bien que le taux d’échec global puisse être inférieur à la métrique cible, les taux de défaillance d’un ou de plusieurs bâtiments ou réseaux peuvent être supérieurs à la métrique cible et nécessiter une investigation.

#### <a name="setup-failure-investigations"></a>Investigations sur les échecs de configuration 

Ce rapport récapitulatif permet de découvrir et d’isoler les bâtiments ou réseaux susceptibles d’avoir besoin d’être corrigés.

> [!NOTE]
> Veillez à ajuster le filtre du rapport Mois de l’année au mois en cours. Sélectionnez **Modifier** et ajustez le filtre de rapport **Mois année** pour enregistrer le nouveau mois par défaut.

##### <a name="remediation"></a>Assainissement 

Concentrez vos premiers efforts de correction sur les bâtiments ou sous-réseaux qui ont le plus grand volume de défaillances. Cela maximisera l’impact sur l’expérience utilisateur et aidera à réduire rapidement le taux d’échecs de configuration des appels organisationnels. Le tableau suivant répertorie les deux raisons des échecs d’installation signalés par le CQD.

| Raison des échecs d’installation des appels       | Cause typique                    |
|----------------------------------|----------------------------------|
| Règle d’exemption d’inspection approfondie des paquets FW manquante | Indique que l’équipement réseau le long du chemin d’accès a empêché l’établissement du chemin d’accès multimédia en raison de règles d’inspection approfondies des paquets. Cela est probablement dû au fait que les règles de pare-feu ne sont pas correctement configurées. Dans ce scénario, l’établissement d’une liaison TCP a réussi, mais ce n’est pas le cas de la négociation SSL.      |
| Règle d’exception de bloc IP FW manquante      | Indique que l’équipement réseau le long du chemin d’accès a empêché l’établissement du chemin d’accès multimédia au réseau Microsoft 365 ou Office 365. Cela peut être dû au fait que les règles de proxy ou de pare-feu ne sont pas correctement configurées pour autoriser l’accès aux adresses IP et aux ports utilisés pour Teams et le trafic Skype Entreprise. |

Lorsque vous commencez votre correction, vous pouvez concentrer vos efforts sur un bâtiment ou un sous-réseau particulier. Comme le montre le tableau précédent, ces problèmes sont dus à des configurations de pare-feu ou de proxy. Passez en revue les options du tableau suivant pour les actions de correction.

|      Assainissement      |Aide  |
|-----------------------|----------|
| Configurer des pare-feu | Collaborez avec votre équipe réseau et vérifiez la configuration de vos pare-feu par [rapport à la liste d’adresses IP Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges).<br><br>Vérifiez que les [sous-réseaux et ports multimédias](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) sont inclus dans les règles de pare-feu. <br><br>Vérifiez que les [ports nécessaires](prepare-network.md) sont ouverts dans le pare-feu. UDP doit être prioritaire, car TCP est considéré comme un protocole de restauration automatique pour le partage d’écran audio, vidéo et vidéo, et son utilisation affectera la qualité de l’appel. Le partage d’applications RDP hérité utilise TCP uniquement.|

### <a name="drop-failures"></a>Échecs de suppression

Contrairement aux codes d’échec d’installation, CQD n’a pas de code d’échec de suppression pour indiquer pourquoi des échecs de suppression se produisent, ce qui rend difficile l’isolation d’une cause racine spécifique. Pour mieux trier les échecs de suppression, utilisez une approche déduite. En corrigeant tous les domaines d’intérêt pour les médias, en corrigeant les clients et les pilotes, et en activant l’utilisation d’appareils certifiés pour Teams et Skype Entreprise, vous pouvez vous attendre à ce que les échecs de suppression diminuent.

#### <a name="drop-failure-trend-analysis"></a>Analyse des tendances des échecs de suppression

Ce rapport affiche la quantité totale de flux audio, le nombre total d’échecs de suppression et le taux d’échecs de suppression. Pointez sur l’une des colonnes pour afficher ses valeurs. 


##### <a name="analysis"></a>Analyse

À l’aide de ce type de rapport, vous pouvez répondre aux questions suivantes :

-   Quel est le taux d’échecs de baisse actuel ?
-   Le taux d’échec d’abandon est-il inférieur à la métrique cible définie ?
-   La tendance des défaillances est-elle pire ou meilleure que le mois précédent ?
-   La tendance à l’échec augmente-t-elle, se stabilise-t-elle ou diminue-t-elle ?

Quelle que soit la réponse aux questions ci-dessus, prenez le temps d’examiner l’utilisation des sous-rapports pour rechercher les bâtiments ou réseaux qui pourraient nécessiter une correction. Bien que le taux d’échec de la baisse global puisse être inférieur à la métrique cible, le taux d’échec de la baisse pour un ou plusieurs bâtiments ou réseaux peut être supérieur à la métrique cible et nécessiter une investigation.

#### <a name="drop-failure-investigations"></a>Supprimer les enquêtes sur les échecs

Les échecs signalés ici indiquent que l’appel a été supprimé de manière inattendue et a entraîné une expérience utilisateur négative. Contrairement aux rapports de tendance, ces rapports fournissent des insights supplémentaires sur des sous-réseaux spécifiques qui nécessitent une investigation plus approfondie.


##### <a name="remediation"></a>Assainissement

À l’aide des rapports de table inclus, vous pouvez isoler les zones problématiques du réseau où le taux de baisse est supérieur à la métrique cible que vous avez définie. Concentrez vos premiers efforts de correction sur les bâtiments ou les sous-réseaux qui ont le plus grand nombre total de flux, pour avoir le plus grand impact.

Causes courantes des suppressions d’appels :

-   Sortie réseau ou Internet sous-approvisionnée
-   Aucun QoS configuré sur des réseaux contraints
-   Versions antérieures du client
-   Comportement de l’utilisateur

Une fois que vous avez découvert vos domaines problématiques, vous pouvez utiliser [l’analytique des appels par utilisateur](use-call-analytics-to-troubleshoot-poor-call-quality.md) pour examiner plus en détail les utilisateurs de ce bâtiment pour identifier des problèmes spécifiques. L’analytique des appels contient des données EUII supplémentaires et peut être utile pour isoler davantage les raisons potentielles des échecs de suppression.

Quelle que soit l’étape suivante, il est recommandé d’informer votre support technique qu’un problème a été détecté avec des bâtiments ou sous-réseaux spécifiques. Cela permet au support technique de répondre rapidement aux appels entrants et de trier les utilisateurs plus efficacement. Les utilisateurs marqués d’un indicateur peuvent ensuite être signalés à l’équipe d’ingénierie pour une investigation plus approfondie.

Le tableau suivant répertorie certaines méthodes courantes pour gérer et corriger les échecs de suppression.

| Assainissement                              | Aide                      |
|------------------------------------------|-------------------------------|
| **Réseau/Internet**                         | **Congestion** : collaborez avec votre équipe réseau pour surveiller la bande passante sur des bâtiments/sous-réseaux spécifiques afin de vérifier qu’il existe des problèmes de surutilisation. Si vous confirmez qu’il y a une congestion du réseau, envisagez d’augmenter la bande passante pour ce bâtiment ou d’appliquer QoS. Utilisez les [rapports récapitulatifs](#quality-investigations) de qualité médiocre inclus pour passer en revue les sous-réseaux de problèmes liés à la gigue, à la latence et à la perte de paquets, car ils précèdent souvent un flux supprimé.<br><br>**QoS** : Si l’augmentation de la bande passante n’est pas pratique ou coûteuse, envisagez d’implémenter QoS. Cet outil est très efficace pour gérer le trafic ingéré et peut garantir que les paquets multimédias sur le réseau managé sont hiérarchisés au-dessus du trafic non multimédia. Sinon, s’il n’existe aucune preuve claire que la bande passante est responsable, envisagez les solutions suivantes :<ul><li>[Conseils QoS Microsoft Teams](qos-in-teams.md)</li></ul><br>**Effectuer une évaluation de la préparation du réseau** : une évaluation réseau fournit des détails sur l’utilisation attendue de la bande passante, la façon de gérer les changements de bande passante et de réseau, ainsi que les pratiques de mise en réseau recommandées pour Teams et Skype Entreprise. En utilisant le tableau précédent comme source, vous disposez d’une liste de bâtiments ou de sous-réseaux qui sont d’excellents candidats pour une évaluation.<ul><li>[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)</li></ul> |
| **Clients (Skype Entreprise En ligne uniquement)** | Certains clients plus anciens Skype Entreprise ont connu des problèmes documentés liés à la fiabilité des médias. Passez en revue les rapports Analyse des appels de plusieurs utilisateurs affectés, ou créez un rapport de table de version du client personnalisé dans CQD filtré sur des bâtiments ou sous-réseaux spécifiques avec la mesure Total Call Dropped Failure % (% d’échec total). Ces informations vous aideront à comprendre si une relation existe entre les suppressions d’appel dans ce bâtiment spécifique et une version spécifique du client.     |
| **Appareils**                                  |Si les appareils sont responsables des problèmes de qualité des appels, envisagez de mettre à jour les appareils incriminés. Pour en savoir plus, consultez [Téléphones pour Teams](./devices/phones-for-teams.md) . |
| **Comportement de l’utilisateur**                            | Si vous déterminez qu’aucun réseau, appareil ou client n’est le problème, envisagez de développer une stratégie d’adoption des utilisateurs pour informer les utilisateurs sur la meilleure façon de participer aux réunions et de les quitter. Un utilisateur Teams et Skype Entreprise plus intelligent produira une meilleure expérience utilisateur pour tous les participants à la réunion. Par exemple, un utilisateur qui met son ordinateur portable en veille (en fermant le couvercle) sans quitter la réunion sera classé comme une goutte d’appel inattendue.   |

## <a name="quality-investigations"></a>Examens de qualité

L’étape suivante pour évaluer l’état de la qualité audio au sein de l’organisation consiste à examiner le taux de diffusion médiocre (PSR), le protocole TCP et l’utilisation du proxy. Il est important de se rappeler que les données de CQD ne vous fournissent pas une cause racine spécifique, mais qu’elles vous fournissent plutôt des domaines problématiques susceptibles de commencer une conversation collaborative avec les équipes appropriées pour les activités de correction. 

> [!NOTE]
> Tous les rapports inclus dans les modèles ne sont pas abordés dans cet article ; toutefois, les méthodes d’investigation décrites ci-dessous s’appliqueront toujours à ces rapports. Pour plus d’informations, reportez-vous à la description individuelle du rapport. 

### <a name="quality"></a>Qualité

Les pourcentages PSR sont utilisés pour indiquer si l’organisation atteint les cibles de métriques définies pour une zone de focus donnée. Il est important de noter que même si les pourcentages élevés se trouvent dans la cible définie, les sous-réseaux ou bâtiments individuels peuvent ne pas atteindre les cibles définies et, par conséquent, avoir besoin d’une investigation plus approfondie. Par exemple, si le pourcentage de rtc audio global est de 2 p. 100 en avril, ce qui correspond à l’échantillon cible, les bâtiments individuels et les sous-réseaux peuvent toujours avoir des expériences médiocres, selon la distribution globale de ces 2 p. 100. 

Pour évaluer le pourcentage de flux pauvres, utilisez les rapports de qualité. Divers rapports de qualité sont fournis pour passer en revue les métriques pour l’ensemble, les conférences, les conférences, les appels RTC, le VPN et les salles de réunion. Des rapports mensuels, hebdomadaires et quotidiens sont fournis pour faciliter ce processus. Les rapports hebdomadaires et quotidiens sont limités au modèle Réseaux managés pour accroître leur efficacité et réduire le bruit. 

#### <a name="quality-trend-analysis"></a>Analyse des tendances de qualité

Les rapports de tendance affichent des informations de qualité au fil du temps et sont utilisés pour identifier et comprendre les tendances de qualité dans chaque domaine d’intérêt. Comme indiqué ci-dessus, des arborescences de rapports sont incluses dans les modèles pour l’examen de la qualité; conférences, conférences à deux, appels RTC, VPN et salles de réunion. Pour l’analyse de la qualité, le processus d’enquête est le même. Toutefois, nous vous recommandons de commencer par la conférence en premier, car toute amélioration de la qualité des conférences aura également un impact positif sur tous les autres domaines. 

> [!Note]
> L’examen des appels à deux parties, des appels RTC et des salles de réunion est similaire à l’examen des conférences. L’objectif est d’isoler les bâtiments ou les sous-réseaux qui ont la pire qualité et d’identifier la raison de la mauvaise qualité.

> [!Important]
> Les rapports basés sur VPN sont filtrés à l’aide de la deuxième dimension VPN. Cette dimension nécessite que la carte réseau VPN soit correctement inscrite en tant qu’adaptateur d’accès à distance. Les fournisseurs VPN n’utilisent pas de manière fiable cet indicateur, et votre kilométrage varie en fonction du fournisseur VPN déployé auprès de votre organisation. Modifiez les rapports [VPN](CQD-upload-tenant-building-data.md#vpn) si nécessaire à l’aide du nom du bâtiment ou du réseau.

##### <a name="investigation"></a>Enquête

À l’aide de ces rapports, vous pouvez répondre aux questions suivantes :

-   Quel est le nombre total de demandes de remboursement pour le mois en cours ?
-   La demande de remise est-elle inférieure à la métrique cible définie ?
-   La RSE est-elle pire ou meilleure que le mois précédent ?
-   La tendance de la demande de récupération d’informations est-elle en hausse, stable ou décroissante ?

Quelle que soit la réponse aux questions ci-dessus, prenez le temps d’examiner à l’aide des sous-rapports pour rechercher les bâtiments ou sous-réseaux qui pourraient nécessiter une enquête. Bien que la demande de récupération d’urgence globale puisse être inférieure à la métrique cible, la demande de récupération d’urgence pour un ou plusieurs bâtiments ou réseaux est souvent supérieure à la métrique et nécessite une correction.

#### <a name="quality-investigations"></a>Examens de qualité

Les rapports récapitulatifs de qualité vous donnent un aperçu plus approfondi de ce qui a contribué à la classification médiocre des flux et permettent d’isoler les zones problématiques dans le réseau géré.

Bien que les dimensions utilisées puissent différer légèrement d’un rapport à l’autre, chaque rapport inclut des mesures pour le nombre total de flux, le nombre total de flux médiocres, la RSP et la mauvaise qualité due à. Des rapports ont été créés pour chaque domaine d’intérêt : conférence, conférence à deux, appel RTC, VPN et salles de réunion. Le modèle de réseau managé inclut des rapports supplémentaires pour tirer parti des informations d’emplacement chargées via le fichier de construction.


> [!Note]
> Les sous-réseaux courants sont difficiles à trier en raison de leur utilisation généralisée. Un rapport distinct qui affiche l’adresse IP publique du client (deuxième adresse IP locale réflexive) a été ajouté au modèle Tous les réseaux pour faciliter la correction des bureaux qui utilisent des réseaux communs.


![Capture d’écran montrant le résumé du flux audio médiocre.](media/qerguide-image-poorqualitysummary.png)

##### <a name="remediation"></a>Assainissement

Concentrez vos efforts de correction sur les bâtiments ou sous-réseaux qui ont le plus grand volume de flux, car cela maximisera l’impact et aidera à améliorer rapidement l’expérience utilisateur. Utilisez les mesures de gigue, de perte de paquets et de temps aller-retour (RTT) pour comprendre ce qui contribue à la mauvaise qualité (il est possible qu’il y ait plusieurs problèmes) :

-   **Gigue** : Les paquets multimédias arrivent à des vitesses différentes, ce qui fait qu’un haut-parleur sonne robotisé.
-   **Perte de paquets** : les paquets multimédias sont supprimés, ce qui crée l’effet de mots ou de syllabes manquants.
-   **RTT** : Les paquets multimédias prennent beaucoup de temps pour atteindre leur destination, ce qui crée un effet walkie-talkie.

Pour faciliter votre investigation sur les problèmes de qualité, utilisez [l’analytique des appels par utilisateur](use-call-analytics-to-troubleshoot-poor-call-quality.md). Avec Call Analytics, vous pouvez examiner une conférence spécifique ou le rapport d’appel de l’utilisateur. Ce rapport contient des données EUII/PII et est utile lorsque vous recherchez la cause d’une défaillance. Une fois que vous savez quel bâtiment est affecté, il doit être simple de suivre les utilisateurs de ce bâtiment. 

N’oubliez pas d’informer votre support technique que ces réseaux rencontrent des problèmes de qualité, afin qu’ils puissent rapidement trier et répondre aux appels entrants.

| Assainissement                              | Aide                         |
|------------------------------------------|----------------------------------|
| **Réseaux**                                 | **Congestion** : un réseau surutilné ou sous-approvisionné peut entraîner des problèmes de qualité des médias. Collaborez avec l’équipe réseau pour déterminer si les connexions réseau de l’utilisateur au point de sortie Internet disposent d’une bande passante suffisante pour prendre en charge les médias. <br><br>**Effectuer une évaluation de la préparation du réseau** : une évaluation réseau fournit des détails sur l’utilisation attendue de la bande passante, la façon de gérer les changements de bande passante et de réseau, ainsi que les pratiques de mise en réseau recommandées pour Teams et Skype Entreprise. En utilisant le tableau précédent comme source, vous disposez d’une liste de bâtiments ou de sous-réseaux qui sont d’excellents candidats pour une évaluation.<ul><li>[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)</li></ul>|
| **Qualité de service (QoS)**  | QoS est un outil éprouvé qui permet de hiérarchiser les paquets sur un réseau congestionné pour s’assurer qu’ils arrivent à destination intacts et à l’heure. Envisagez d’implémenter QoS au sein de votre organisation pour optimiser la qualité de l’expérience utilisateur où la bande passante est limitée. QoS vous aidera à résoudre les problèmes généralement associés à des niveaux élevés de perte de paquets et, dans une moindre mesure, des temps de gigue et d’aller-retour.<ul><li>[Conseils sur la QoS Teams](qos-in-teams.md)</li></ul> |
| **Wi-Fi**               | Wi-Fi peut avoir un impact significatif sur la qualité des appels. Wi-Fi déploiements ne prennent généralement pas en compte la configuration réseau requise pour les services VoIP et sont souvent une source de mauvaise qualité. Pour plus d’informations sur l’optimisation de votre infrastructure Wi-Fi, consultez [cet article sur la planification Wi-Fi](/skypeforbusiness/certification/plan-wifi).<br><br>**Pilote sans fil** : assurez-vous que les pilotes sans fil sont à jour. Cela permet d’atténuer toute mauvaise expérience utilisateur liée à un pilote obsolète. De nombreuses organisations n’incluent pas de pilotes sans fil dans leurs cycles de correctifs, et ces pilotes peuvent ne pas être corrigés pendant des années. De nombreux problèmes sans fil sont résolus en veillant à ce que les pilotes sans fil soient à jour.<br><br>**WMM** : WMM (Wireless Multimedia Extensions), également appelé Wi-Fi Multimédia, fournit des fonctionnalités QoS de base aux réseaux sans fil. Les réseaux sans fil modernes doivent être compatibles avec de nombreux appareils. Ces appareils sont en concurrence pour la bande passante et peuvent entraîner des problèmes de qualité pour les services VoIP, où la vitesse et la latence sont essentielles. Consultez votre fournisseur de services sans fil pour obtenir des détails et envisagez d’implémenter WMM sur votre réseau sans fil pour hiérarchiser Skype Entreprise et les médias Teams.<br><br>**Densité des points d’accès** : les points d’accès peuvent être trop éloignés ou ne pas se trouver dans un emplacement idéal. Pour réduire les interférences potentielles, placez des points d’accès supplémentaires dans les salles de conférence et dans des emplacements qui ne sont pas obstrués par des murs ou d’autres objets où le signal Wi-Fi est faible.<br><br>**2,4 GHz contre 5 GHz** : 5 GHz offrent moins d’interférences en arrière-plan et des vitesses plus élevées, et doivent être hiérarchisés lors du déploiement de VoIP sur Wi-Fi. Toutefois, 5 GHz n’est pas aussi fort que 2,4 GHz et ne pénètre pas les murs aussi facilement. Passez en revue la disposition de votre bâtiment pour déterminer la fréquence sur laquelle vous pouvez vous appuyer pour la meilleure connexion. |
|**Périphérique réseau** | Les grandes organisations peuvent avoir des centaines d’appareils répartis sur le réseau. Collaborez avec votre équipe réseau pour vous assurer que les appareils réseau de l’utilisateur à Internet sont maintenus et à jour. |
| **VPN**  | Les appliances VPN ne sont généralement pas conçues pour gérer les charges de travail multimédias en temps réel. Certaines configurations VPN interdisent l’utilisation d’UDP (qui est le protocole préféré pour les médias) et s’appuient uniquement sur TCP. Envisagez d’implémenter une solution de tunnel fractionné VPN pour réduire le VPN comme source de mauvaise qualité. |
| **Clients** <br>(Skype Entreprise En ligne uniquement) | Vérifiez que tous les clients sont régulièrement mis à jour. |
| **Appareils** | Si les appareils sont responsables des problèmes de qualité des appels, envisagez de mettre à jour les appareils incriminés. Pour en savoir plus, consultez [Téléphones pour Teams](./devices/phones-for-teams.md) . |
| **Pilotes** | La mise à jour corrective des pilotes réseau (Ethernet et Wi-Fi), audio, vidéo et USB doit faire partie de votre stratégie globale de gestion des correctifs. De nombreux problèmes de qualité sont résolus par la mise à jour des pilotes. |
| **Salles de réunion sur Wi-Fi** | Nous recommandons vivement que les appareils de salle de réunion soient connectés au réseau à l’aide d’une connexion Ethernet d’au moins 1 Gbit/s. Les appareils de salle de réunion incluent généralement plusieurs flux audio et vidéo, ainsi que du contenu de réunion tel que le partage d’écran, et ont des exigences réseau plus élevées que les autres points de terminaison Teams ou Skype Entreprise. Les salles de réunion sont, par définition, des appareils fixes où Wi-Fi offre un avantage uniquement pendant l’installation.<br><br>Les salles de réunion doivent être traitées avec un soin et une attention supplémentaires pour s’assurer que l’utilisation de ces appareils répond aux attentes ou dépasse les attentes. Les problèmes de qualité liés aux salles de réunion vont généralement être rapidement réaffectés, car ils sont souvent utilisés par les cadres supérieurs.<br><br>Toutes choses étant égales (à part la commodité), Wi-Fi performances est souvent inférieure à une connexion câblée. Avec l’augmentation des stratégies « apportez votre propre appareil » et la prolifération des ordinateurs portables, Wi-Fi points d’accès sont souvent sur-utilisés. Les médias en temps réel peuvent ne pas être hiérarchisés sur Wi-Fi réseaux, ce qui peut entraîner des problèmes de qualité pendant les heures de pointe. Cette utilisation intensive peut coïncider avec une réunion où il peut y avoir une douzaine de personnes présentes, chacune avec son propre ordinateur portable et smartphone, tous connectés au même point d’accès Wi-Fi que l’appareil de salle de réunion.<br><br>Wi-Fi ne doit être considérée que comme une solution temporaire, pour une installation mobile, ou lorsque Wi-Fi a été correctement approvisionnée pour prendre en charge les médias en temps réel de classe affaires. |


### <a name="tcp"></a>TCP 

Le protocole TCP (Transmission Control Protocol) est considéré comme un transport de restauration automatique et non comme le transport principal souhaité pour les médias en temps réel. La raison pour laquelle il s’agit d’un transport de restauration automatique est due à la nature avec état de TCP. Par exemple, si un appel est effectué sur un réseau latent et que les paquets multimédias sont retardés, les paquets d’il y a quelques secondes, qui ne sont plus utiles, concurrencent la bande passante pour accéder au récepteur, ce qui peut aggraver une mauvaise situation. Cela rend le point de cicatrisation audio et étirer l’audio, ce qui entraîne des artefacts audibles, souvent sous la forme de gigue.

Les rapports de cette section ne font pas de distinction entre les flux bons et pauvres. Étant donné que le protocole UDP est préféré, les rapports recherchent l’utilisation de TCP pour le partage d’écran audio, vidéo et vidéo (VBSS). Des taux de flux médiocres sont fournis pour vous aider à comparer la qualité UDP et la qualité TCP afin que vous puissiez concentrer vos efforts là où l’impact est le plus important. L’utilisation de TCP est principalement due à des règles de pare-feu incomplètes. Pour plus d’informations sur les règles de pare-feu pour Teams et Skype Entreprise Online, consultez [Microsoft 365 et Office 365 URL et plages d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges).

> [!Note]
> L’audio, la vidéo et VBSS préfèrent tous UDP comme transport principal. La charge de travail de partage d’applications RDP héritée utilise uniquement TCP.

#### <a name="tcp-usage"></a>Utilisation de TCP

Les rapports TCP indiquent l’utilisation globale de TCP au cours des sept derniers mois. Tous les autres rapports de cette section se concentreront sur le rétrécissement de bâtiments et de sous-réseaux spécifiques où TCP est le plus couramment utilisé. Des rapports distincts sont disponibles pour les flux de conférence et les flux à deux parties.

![Graphique montrant le pourcentage de flux audio qui utilisent TCP.](media/qerguide-image-audiostreamswithtcp.png)

##### <a name="investigation"></a>Enquête

À l’aide de ce rapport, vous pouvez répondre aux questions suivantes :

-   Quel est le volume total de flux TCP pour le mois en cours ?
-   Est-ce pire ou mieux que le mois précédent ?
-   La tendance à l’utilisation de TCP augmente-t-elle, stable ou décroît-elle ?
-   La demande PSR TCP est-elle la même que ma demande de remise globale ?

Si vous remarquez que la tendance d’utilisation de TCP augmente ou dépasse l’utilisation mensuelle normale, prenez le temps d’examiner à l’aide des sous-rapports pour rechercher les bâtiments ou réseaux qui peuvent nécessiter une correction. Dans l’idéal, vous souhaitez avoir le moins de sessions audio TCP possible sur le réseau managé.

#### <a name="tcp-vs-udp"></a>TCP et UDP

Ce rapport identifie le volume de rapports d’utilisation TCP et UDP sur le dernier mois pour le partage d’écran audio, vidéo et vidéo (VBSS). 

![Rapport montrant le volume de flux qui utilisent TCP et UDP.](media/qerguide-image-tcpvsudp.png)

##### <a name="analysis"></a>Analyse

Bien que vous souhaitiez que l’utilisation de TCP soit aussi faible que possible, vous pouvez voir un peu d’utilisation de TCP dans un déploiement autrement sain. TCP en lui-même ne contribue pas à un mauvais appel. Les tarifs de flux sont donc fournis pour vous aider à déterminer si l’utilisation de TCP contribue à une mauvaise qualité. 

#### <a name="tcp-investigations"></a>Enquêtes TCP

Dans les modèles CQD fournis, accédez aux flux TCP en créant et en sous-réseaux des rapports à l’aide du modèle Réseaux managés ou Tous les réseaux. Dans le but d’examiner l’utilisation de TCP, le processus est le même. Nous allons donc concentrer la discussion ici sur la conférence.


##### <a name="remediation"></a>Assainissement

Ce rapport identifie des bâtiments et des sous-réseaux spécifiques qui contribuent au volume d’utilisation de TCP. Un rapport supplémentaire est également inclus pour identifier l’adresse IP Microsoft Relay qui a été utilisée dans l’appel pour aider à isoler les règles de pare-feu manquantes. Concentrez vos efforts de correction sur les bâtiments qui ont le volume le plus élevé de flux TCP pour optimiser l’impact.

La cause la plus courante de l’utilisation de TCP est l’absence de règles d’exception dans les pare-feu ou proxys. Nous allons parler de proxys dans la section suivante. Pour l’instant, concentrez vos efforts sur les pare-feu. En utilisant le bâtiment ou le sous-réseau fourni, vous pouvez déterminer le pare-feu à mettre à jour.

| Assainissement        | Aide     |
|--------------------|--------------------------------------|
| Configurer le pare-feu | Vérifiez que les [ports et adresses IP Microsoft 365 ou Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges) sont exclus de votre pare-feu. Pour les problèmes TCP liés aux médias, concentrez vos efforts initiaux sur les éléments suivants :<ul><li>Vérifiez que les sous-réseaux multimédias clients 13.107.64.0/18 et 52.112.0.0/14 figurent dans vos règles de pare-feu.</li><li>Les ports UDP 3478-3481 sont les ports multimédias requis et doivent être ouverts. Sinon, le client revient au port TCP 443.</li></ul> |
| Vérifier             | Utilisez [l’outil d’évaluation du réseau Microsoft](https://www.microsoft.com/download/details.aspx?id=53885) pour rechercher les problèmes de connectivité à des adresses IP et ports Microsoft 365 ou Office 365 spécifiques à partir du bâtiment ou du sous-réseau concerné.    |

### <a name="http-proxy"></a>Proxy HTTP

Les proxys HTTP ne sont pas le chemin d’accès par défaut pour l’établissement de sessions multimédias, pour une multitude de raisons. Beaucoup contiennent des fonctionnalités d’inspection approfondie des paquets qui peuvent empêcher l’achèvement des connexions au service et introduire des interruptions. En outre, presque tous les proxys forcent TCP au lieu d’autoriser UDP, ce qui est recommandé pour une qualité audio optimale.

Nous vous recommandons toujours de configurer le client pour qu’il se connecte directement à Teams et Skype Entreprise services. Ceci est particulièrement important pour le trafic multimédia.


> [!IMPORTANT]
> Nous vous recommandons de charger un [fichier de construction valide](CQD-upload-tenant-building-data.md) afin de pouvoir faire la distinction entre les flux audio externes lors de l’analyse de l’utilisation du proxy. 


#### <a name="http-proxy-usage"></a>Utilisation du proxy HTTP

Le rapport de flux de proxy HTTP dans cette section du modèle ressemble beaucoup aux rapports TCP. Il ne vérifie pas si les appels sont médiocres ou bons, mais si l’appel est connecté via HTTP.

![Capture d’écran du rapport de flux audio qui utilisent HTTP.](media/qerguide-image-audiostreamswithhttp.png)

##### <a name="analysis"></a>Analyse

Vous souhaitez voir le moins de flux multimédia HTTP possible. Si vous avez des flux qui traversent votre proxy, consultez votre équipe réseau pour vous assurer que les exclusions appropriées sont en place afin que les clients soient directement routages vers Teams ou Skype Entreprise sous-réseaux multimédias en ligne.

Si vous n’avez qu’un seul proxy Internet dans votre organisation, vérifiez les [URL microsoft 365 ou Office 365 appropriées et les exclusions de plage d’adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Si plusieurs proxys Internet sont configurés dans votre organisation, utilisez le sous-rapport HTTP pour isoler le bâtiment ou le sous-réseau affecté.

Pour les organisations qui ne peuvent pas contourner le proxy, assurez-vous que le client Skype Entreprise est configuré pour se connecter correctement lorsqu’il se trouve derrière un proxy, comme indiqué dans l’article [Skype Entreprise devez utiliser le serveur proxy pour se connecter au lieu d’essayer une connexion directe](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin). 


#### <a name="http-proxy-investigations"></a>Investigations de proxy HTTP

Ce rapport identifie des bâtiments et des sous-réseaux spécifiques qui contribuent à l’utilisation du protocole HTTP.


##### <a name="remediation"></a>Assainissement

Nous vous [recommandons](proxy-servers-for-skype-for-business-online.md) de toujours contourner les proxys pour Skype Entreprise et Teams, en particulier le trafic multimédia. Les proxys ne rendent pas Skype Entreprise plus sécurisé, car son trafic est déjà chiffré. Des problèmes de performances peuvent s'introduire dans l'environnement par le biais de la latence et la perte de paquets. Ces problèmes entraînent une expérience négative du partage audio, vidéo et d’écran, où les flux en temps réel sont essentiels.

La cause la plus courante de l’utilisation de HTTP est l’absence de règles d’exception dans les proxys. En utilisant le bâtiment ou le sous-réseau fourni, vous pouvez rapidement déterminer le proxy à configurer pour la déviation du trafic multimédia.

Vérifiez que les noms de domaine [complets Microsoft 365 ou Office 365 requis sont ajoutés](/microsoft-365/enterprise/urls-and-ip-address-ranges) à une liste verte dans votre proxy.

## <a name="endpoint-investigations"></a>Examens de point de terminaison

Cette section se concentre sur les tâches de création de rapports sur les versions clientes et l’utilisation d’appareils certifiés. Des rapports sont disponibles pour décrire l’utilisation des versions client, du type de client, des périphériques de capture et des pilotes (microphone), des périphériques de capture vidéo et Wi-Fi versions du fournisseur et du pilote.

> [!NOTE]
> Tous les rapports inclus dans les modèles ne sont pas abordés dans cet article ; toutefois, les méthodes d’investigation décrites ci-dessous s’appliquent toujours. Pour plus d’informations, reportez-vous à la description individuelle du rapport.

### <a name="client-versions"></a>Versions clientes

Ces rapports se concentrent sur l’identification des Skype Entreprise versions clientes utilisées et leur volume relatif dans l’environnement.

> [!IMPORTANT]
> Actuellement, les clients Teams sont distribués et mis à jour automatiquement via le réseau de distribution de contenu Azure et seront tenus à jour par le service. Par conséquent, vous n’avez pas besoin de surveiller les versions du client Teams (sauf si vous désactivez la mise à jour automatique, ce que nous ne recommandons pas).

Sauf si vous excluez les données des participants fédérés, ces rapports incluent la télémétrie du client à partir de points de terminaison fédérés. Pour exclure les points de terminaison fédérés, vous devez ajouter un filtre de requête pour le deuxième ID de locataire défini à [l’ID de locataire](CQD-data-and-reports.md#how-to-find-your-tenant-id) de votre organisation. Vous pouvez également utiliser un [filtre d’URL](CQD-data-and-reports.md#url-filters) pour exclure les données de télémétrie des participants fédérés.



#### <a name="remediation"></a>Assainissement

Une partie essentielle de la conduite des expériences utilisateur de haute qualité consiste à s’assurer que les clients gérés exécutent des versions à jour de Skype Entreprise, en plus de s’assurer que les pilotes audio, vidéo, réseau et USB de prise en charge sont à jour. Cela offre plusieurs avantages, parmi lesquels : 

-   Il est plus facile de gérer quelques versions que de nombreuses versions.
-   Il fournit un niveau de cohérence de l’expérience.
-   Il facilite la résolution des problèmes liés à la qualité et à la facilité d’utilisation des appels.
-   Microsoft apporte continuellement des améliorations générales et des optimisations sur l’ensemble du produit. S’assurer que les utilisateurs reçoivent ces mises à jour réduit leur risque de rencontre d’un problème qui a déjà été résolu.

La limitation de votre déploiement aux versions clientes de moins de six mois améliorera l’expérience utilisateur globale et améliorera la facilité de gestion en réduisant le nombre de versions qui doivent être prises en charge.

Si vous utilisez uniquement Office Démarrer en un clic, vous êtes automatiquement dans la fenêtre de six mois. Aucune autre action n’est requise.

Si vous disposez d’un mélange de packages « Démarrer en un clic » et de packages d’installation (MSI), vous pouvez utiliser le rapport pour vérifier que les clients MSI sont régulièrement mis à jour. Si vous constatez que les clients sont en retard, collaborez avec l’équipe chargée de gérer les mises à jour Office et assurez-vous qu’ils approuvent et déploient régulièrement des correctifs clients.

Il est également important de prendre en compte et de s’assurer que les pilotes réseau, vidéo, USB et audio sont également corrigés. Il peut être facile d’ignorer ces pilotes et de ne pas les inclure dans votre stratégie de gestion des correctifs.

Les numéros de version pour Skype Entreprise sont disponibles via les liens ci-dessous :

-   [Informations de publication pour les mises à jour de Microsoft 365 Apps](/officeupdates/release-notes-office365-proplus)
-   [Historique des mises à jour pour Applications Microsoft 365 pour les grandes entreprises](/officeupdates/update-history-office365-proplus-by-date)
-   [Téléchargements et mises à jour de Skype Entreprise](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Appareils

Pour utiliser le rapport d’appareil microphone, nous devons comprendre le concept du score d’opinion moyen (MOS). MOS est la mesure standard pour évaluer la qualité audio perçue. Il est représenté sous la forme d’une évaluation entière comprise entre 0 et 5.

La base de toutes les mesures de la qualité de la voix est la façon dont une personne perçoit la qualité de la parole. Parce qu’il est affecté par la perception humaine, il est intrinsèquement subjectif. Il existe plusieurs méthodologies différentes pour les tests subjectifs. La plupart des mesures de qualité vocale sont basées sur une échelle ACR (Absolute Categorization Rating).

Dans un test subjectif ACR, un nombre statistiquement significatif de personnes évaluent leur qualité d’expérience sur une échelle de 1 (mauvais) à 5 (excellent). La moyenne des scores est le MOS. Le MOS résultant dépend de la plage d’expériences qui ont été exposées au groupe et du type d’expérience évalué.

Étant donné qu’il n’est pas pratique d’effectuer des tests subjectifs de la qualité vocale pour un système de communication dynamique, Microsoft Teams et Skype Entreprise générer des valeurs MOS à l’aide d’algorithmes avancés pour prédire objectivement les résultats d’un test subjectif.

L’ensemble disponible de MOS et les métriques associées fournissent une vue de la qualité de l’expérience fournie aux utilisateurs par un périphérique audio. 

En fournissant aux utilisateurs des appareils certifiés pour Teams et Skype Entreprise, vous réduisez la probabilité de rencontrer des expériences négatives en raison de l’appareil lui-même (ce qui est plus probable, par exemple, avec des haut-parleurs et des microphones d’ordinateur portable intégrés). Pour plus d’informations, consultez ces articles sur le [programme de certification](/SkypeForBusiness/certification/overview) et le [catalogue de solutions partenaires](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

Les rapports d’appareil sont utilisés pour évaluer l’utilisation des appareils par volume et score MOS (audio uniquement) et se trouvent dans les modèles qui les accompagnent sous Clients & Appareils. 

> [!IMPORTANT]
> Sauf si vous excluez les données des participants fédérés, ces rapports incluent la télémétrie du client à partir de points de terminaison fédérés. Pour exclure les points de terminaison fédérés, vous devez ajouter un filtre de requête pour **le deuxième ID de locataire** défini à l’ID de [locataire](CQD-data-and-reports.md#how-to-find-your-tenant-id) de votre organisation. De manière ALternative, vous pouvez utiliser un [filtre d’URL](CQD-data-and-reports.md#url-filters) pour exclure les données de télémétrie des participants fédérés.


> [!Note]
> Vous pouvez remarquer lors de l’affichage de ce rapport que le même appareil est signalé plusieurs fois. Cela est dû à la façon dont l’appareil est signalé au CQD. Les différences dans les paramètres régionaux du matériel et du système d’exploitation entraînent des différences dans la façon dont les données d’appareil sont signalées.

##### <a name="remediation"></a>Assainissement

En règle générale, vous devez découvrir et supprimer progressivement les appareils non certifiés et les remplacer par des appareils certifiés. Voici quelques considérations à prendre en compte lors de l’examen des rapports d’appareil :

-   Les appareils utilisés sont-ils certifiés pour Teams et Skype Entreprise ? 
-   Vous pouvez identifier les utilisateurs d’un appareil spécifique à l’aide de [l’analytique des appels par utilisateur](use-call-analytics-to-troubleshoot-poor-call-quality.md). Vérifiez qu’ils disposent des derniers pilotes d’appareil et que leur appareil n’est pas connecté via un hub USB ou une station d’accueil. 
-   Combien de versions différentes de différents pilotes sont utilisées ? Sont-ils régulièrement corrigés ? S’assurer que les pilotes audio, vidéo et Wi-Fi sont régulièrement corrigés vous aidera à les éliminer en tant que source de problèmes de qualité et à rendre l’expérience utilisateur plus prévisible et cohérente.

##### <a name="audio"></a>Audio

La tâche suivante consiste à déterminer l’utilisation globale des [périphériques audio certifiés](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Nous recommandons qu’au moins 80 % de tous les flux audio utilisent un périphérique audio certifié. Pour ce faire, il est préférable d’exporter le rapport des appareils microphone vers Excel pour calculer l’utilisation d’appareils certifiés ou approuvés. Les organisations conservent généralement une liste de tous les appareils approuvés. Le filtrage et le tri des données doivent donc être simples.

##### <a name="video"></a>Vidéo

Les pilotes vidéo sont également importants pour rester à jour. S’assurer que les cartes vidéo sont régulièrement corrigés aidera à exclure les pilotes vidéo comme source de mauvaise qualité pour les flux vidéo. L’utilisation [d’appareils vidéo certifiés](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) permet de garantir une expérience utilisateur fluide et de haute qualité. Les périphériques vidéo qui prennent en charge l’encodage natif H.264 sont préférés pour réduire l’utilisation du processeur pendant la vidéoconférence.

##### <a name="wi-fi"></a>Wi-Fi

Wi-Fi pilotes doivent également être corrigés à une cadence régulière et doivent également être inclus dans votre stratégie de gestion des correctifs. De nombreux problèmes de qualité peuvent être corrigés en conservant des pilotes Wi-Fi à jour. Pour plus d’informations sur l’optimisation de votre infrastructure Wi-Fi, consultez [cet article sur la planification Wi-Fi](/skypeforbusiness/certification/networking-wifi).


## <a name="related-topics"></a>Sujets associés

[Utiliser Advisor pour Teams](use-advisor-teams-roll-out.md)

[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)

[Principes de connectivité réseau Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Analyses et rapports Teams](teams-analytics-and-reports/teams-reporting-reference.md)

[Gérer vos périphériques dans Teams](./devices/device-management.md)

[Améliorer et surveiller la qualité des appels pour Teams](monitor-call-quality-qos.md)

[Qu’est-ce que le TBQA ?](CQD-what-is-call-quality-dashboard.md)

[Configurer le tableau de bord de qualité des appels (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Charger le client et créer des données](CQD-upload-tenant-building-data.md)

[Données et rapports du TBQA](CQD-data-and-reports.md)

[Dimensions et mesures disponibles dans le TBQA](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification de flux de données dans le TBQA](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser les données TBQA](CQD-Power-BI-query-templates.md)
