---
title: Guide d’Analyse de la Qualité d’Expérience pour Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: siunies, gageames
audience: admin
description: Guide pour l’analyse de la performance multimédia en temps réel de Microsoft teams à l’aide du tableau de bord de qualité des appels (bord).
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 91e2763fac952b7188284dcf09e6fc0b7cc4bf16
ms.sourcegitcommit: 48f64fa38509cf7141b944cd3da60409ec51860b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43749861"
---
# <a name="quality-of-experience-review-guide"></a>Guide d’examen de l’expérience de qualité 

<!-- Note that this link to the Word doc is intentionally NOT the aka.ms/qerquide link -->
Ce guide concerne la phase de la valeur de l’unité pour Microsoft teams et Skype entreprise online. 

## <a name="introduction"></a>Introduction

Pour avoir le plus d’impact sur l’amélioration de l’interface utilisateur, les organisations doivent pouvoir effectuer les opérations principales indiquées dans la figure suivante. Les zones supplémentaires incluent l’identification des tâches opérationnelles, la définition de cibles pour les mesures de qualité, la vérification des mesures à utiliser pour évaluer le succès de l’organisation et les domaines d’examen plus étroits selon les besoins.


![Domaines clés pour la qualité de l’utilisation de l’utilisateur](media/qerguide-image-keyareas.png "Les principales zones de la qualité de l’utilisation de l’utilisateur sont les suivantes : audio, fiabilité, enquêtes utilisateur, appareils et clients.")

_Figure 1 : principales zones opérationnelles abordées dans ce guide_

En évaluant et en révisant en permanence les domaines décrits dans ce guide, vous pouvez réduire leur potentiel pour influer sur la qualité de l’utilisation de vos utilisateurs. La plupart des problèmes d'expérience utilisateur rencontrés lors d'un déploiement peuvent être regroupés dans les catégories suivantes :

-   Configuration incomplète du pare-feu ou du proxy
-   Faible couverture Wi-Fi
-   Bande passante insuffisante
-   VPN
-   Versions et pilotes client incohérents ou obsolètes
-   Périphériques audio prédéfinis ou intégrés
-   Sous-réseaux ou périphériques réseau problématiques

Le bon déroulement de la planification et de la conception avant le déploiement d’équipes ou de Skype entreprise Online vous permet de réduire le nombre d’efforts qui seront nécessaires pour garantir une expérience de grande qualité.

Ce guide porte sur l’utilisation du tableau de bord de qualité des appels (bord) en ligne comme outil principal pour signaler et examiner chaque zone, en mettant l’accent sur le son pour optimiser l’adoption et l’impact. Toute amélioration apportée au réseau pour améliorer la qualité audio sera également traduite directement par l’amélioration du partage de la vidéo et du bureau.

Pour accélérer votre évaluation, [deux modèles bord](https://aka.ms/qertemplates) conversés sont fournis : un pour la gestion de tous les réseaux et l’autre pour les réseaux gérés (internes) uniquement. Bien que les rapports de modèles tous les réseaux soient configurés pour afficher des informations sur la création et le réseau, ils peuvent toujours être utilisés lorsque vous travaillez dans le cadre de la collecte et du chargement des informations de bâtiment. Le chargement des informations de bâtiment dans bord permet au service d’améliorer la création de rapports en ajoutant des informations de construction, de réseau et d’emplacement personnalisées en les différenciant des sous-réseaux externes. Pour plus d’informations, consultez la section [mappage de bâtiment](#building-mapping) plus loin dans ce guide.

### <a name="intended-audience"></a>Public ciblé

Ce guide est destiné à être utilisé par les parties prenantes des partenaires et des clients ayant des rôles tels que le chef de service ou l’architecte de la collaboration, le consultant, le responsable de la gestion des changements

Ce guide est également destiné à être utilisé par le ou les champions qualité désignés. Pour plus d’informations, reportez-vous à [la section rôle d’expert qualité](4-envision-plan-my-service-management.md#the-quality-champion-role).

## <a name="assign-roles-for-accessing-cqd"></a>Affecter des rôles pour accéder à bord

Avant d’utiliser ce guide, assurez-vous que vous disposez des [rôles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) de client appropriés pour pouvoir accéder à bord.

Le tableau suivant vous montre les différents rôles possibles dans bord :


|  |Afficher les rapports  |Afficher les champs de EUII  |Créer des rapports  |Télécharger les données de bâtiment  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Administrateur général d’Office 365     |Oui          |Oui          |Oui          |Oui          |
|Administrateur du service Teams     |Oui          |Oui          |Oui          |Oui          |
|Administrateur des communications Teams     |Oui          |Oui          |Oui          |Oui          |
|Ingénieur du support technique pour les communications Teams     |Oui          |Oui          |Oui         |Non         |
|Spécialiste du support des communications teams     |Oui         |Non         |Oui         |Non         |
|Administrateur Skype entreprise     |Oui          |Oui          |Oui          |Oui          |
|Lecteur global Azure AD |Oui          |Oui          |Oui         |Non         |
|Office 365-rapports sur le lecteur<sup>1</sup>     |Oui         |Non         |Oui         |Non         |

<sup>1</sup> en plus de lire des rapports bord, le lecteur de rapports d' 365 Office peut afficher tous les [rapports d’activité](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) dans le centre d’administration et les rapports du [Pack de contenu adoption de Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).

> [!NOTE]
> Si vous ne voyez pas EUII (informations d’identification de l’utilisateur final) et que vous disposez de l’un des rôles qui vous permettent d’accéder à ces informations, gardez à l’esprit que bord ne conserve EUII pendant 30 jours. Les éléments datant de plus de 30 jours sont supprimés.

## <a name="what-is-quality"></a>Qu’est-ce que la qualité ?

Lorsque vous discutez de la qualité dans équipes et Skype entreprise, il est important de définir le terme pour parvenir à une connaissance commune. La qualité définie ici est une combinaison de métriques de service et d’une interface utilisateur.

<!-- Note: need to update graphic-->
![Illustration des métriques du service et de l’utilisation de l’utilisateur](media/qerguide-image-whatisquality.png "Les métriques de service sont composées de faible rapport de flux, de fiabilité, de points de terminaison/de périphériques et de versions clientes. L’utilisation de l’utilisateur est composée de la perception de la qualité du service par l’utilisateur.")

_Figure 2 : qu’est-ce que la qualité ?_

### <a name="service-metrics"></a>Métriques de service

Les métriques de service sont composées de mesures spécifiques basées sur le client. Lors de chaque appel, le client recueille des informations de télémétrie sur l’appel et envoie un rapport à la fin de chaque appel qui peut être accédé par le biais d’une analyse bord ou d’un [appel](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309). Ces métriques sont les suivantes :

-   Débit médiocre en flux continu
-   Taux d’échec d’installation
-   Taux d’échec de dépôt


#### <a name="poor-stream-rate"></a>Débit médiocre en flux continu

Le taux de flux médiocre (V.Q.P.R.D.) représente le pourcentage global de l’organisation de flux présentant une qualité médiocre. Cette métrique est destinée à mettre en évidence les domaines dans lesquels votre organisation peut se concentrer sur l’impact le plus élevé de la réduction de cette valeur et de l’amélioration de l’interface utilisateur, c’est pourquoi les [réseaux gérés](#managed-vs-unmanaged-networks) sont le principal foyer lors de la recherche de v.q.p.r.d.. Les utilisateurs externes sont aussi importants que les utilisateurs externes. Envisagez de fournir des recommandations destinées aux utilisateurs externes et examinez les appels externes indépendamment de l’organisation globale.

La mesure réelle dans bord varie en fonction de la charge de travail, mais dans le cadre de l’évaluation de l’utilisation de la qualité, nous nous concentrerons essentiellement sur la mesure du _pourcentage audio médiocre_ . Le V.Q.P.R.D. est constitué des cinq moyennes métriques du réseau décrites dans le tableau suivant. Pour qu’un flux soit considéré comme médiocre, une seule métrique doit dépasser le seuil défini. Pour plus d’informations sur le processus de classification des flux, voir [cet article](stream-classification-in-call-quality-dashboard.md).

> [!Note]
> BORD indique le « médiocre à cause de... » des mesures pour mieux comprendre quelle condition a entraîné le classement du flux comme médiocre.


_Tableau 1-indicateurs de qualité audio médiocres_

| Moyenne métrique     | Description     | Expérience utilisateur |
|-------------|-----------------|-----------------|
| Scintillement \>de 30 ms        | Il s’agit de la modification moyenne du délai entre les paquets successifs. Les équipes et Skype entreprise peuvent s’adapter à certains niveaux de scintillement par le biais de la mise en mémoire tampon. C’est uniquement lorsque l’instabilité est supérieure à la mise en mémoire tampon qu’un participant a remarqué les effets de gigue.      | Les paquets entrants à des vitesses différentes peuvent entraîner le son de la voix du haut-parleur.   |
| Taux \>de perte de paquets de 10% ou 0,1        | Il s’agit généralement du pourcentage de paquets perdus. La perte de paquets a un effet direct sur la qualité audio (par rapport aux petits paquets perdus) qui n’ont quasiment aucun impact sur les pertes de Burst en retour à la fin de l’audio.     | Les paquets en cours de rejet et ne sont pas à l’origine de la destination prévue dans le média, ce qui génère des syllabes et des mots manqués, ainsi que la vidéo et le partage saccadés. |
| Durée \>de l’aller-retour 500 ms        | Il s’agit du temps nécessaire à l’obtention d’un paquet IP entre le point A et le point B et de nouveau au point A. Ce délai de propagation du réseau est lié à la distance physique entre les deux points et la vitesse de lumière, et inclut une surcharge supplémentaire prélevée par les divers appareils dans le chemin réseau.      | Les paquets prenant trop de temps pour arriver à leur destination entraînent un effet de diaphonie.   |
| NMOS moyenne \>1,0         | Dégradation moyenne d' [avis du réseau (NMOS)](https://docs.microsoft.com/previous-versions/office/communications-server/bb894481(v=office.12)#network-mos) pour le flux. Représente le niveau de perte et de scintillation du réseau ayant affecté la qualité du son reçu et à l’origine du NMOS. | Il s’agit d’une combinaison de gigue, de perte de paquets et, à un niveau inférieur, d’une durée d’aller-retour accrue. Il est possible que l’utilisateur rencontre une combinaison des symptômes suivants.   |
| Taux moyen d’échantillons \>masqués 7% ou 0,07 | Rapport moyen du nombre de trames audio et d’échantillons masqués générés par la correction de perte de paquets sur le nombre total de trames audio. Un échantillon audio dissimulé est une technique permettant de lisser la transition brutale qui serait généralement provoquée par des paquets réseau interrompus.      | Les valeurs élevées indiquent qu’un masquage de niveau de perte élevé a été appliqué et qu’un son est altéré ou perdu.     |

#### <a name="setup-failure-rate"></a>Taux d’échec d’installation

Le taux d’échec d’installation, également connu sous le nom de mesure du _pourcentage d’échec de configuration d’appel_ dans bord, est le nombre de flux pour lesquels le chemin de médias n’a pas pu être établi entre les points de terminaison au début de l’appel.

Cela représente tout flux multimédia qui ne peut pas être établi. En raison de la gravité de l’impact sur l’utilisation mesurée ici, l’objectif est de réduire cette valeur à la valeur la plus proche possible. Une valeur élevée de cette métrique est plus courante dans les nouveaux déploiements avec des règles de pare-feu incomplètes qu’un déploiement mature, mais il est encore important de surveiller régulièrement.

Cette métrique est calculée en prenant en charge le nombre total de flux qui n’ont pas pu être configurés divisé par le nombre total de flux ayant soumis un enregistrement des détails des appels réussi (CDR) :

-   **Taux d’échec** de la configuration = nombre total de flux d’échecs de configuration d’appel/nombre total de flux de CDR disponibles

#### <a name="drop-failure-rate"></a>Taux d’échec de dépôt

Le taux d’échec de la suppression, également connu sous le nom de mesure du _pourcentage d’échec d’appel interrompu_ dans bord, correspond au pourcentage de flux établi pour lesquels le chemin de médias ne s’est pas terminé correctement.

Il s’agit d’un flux multimédia qui s’est arrêté de manière inattendue. Même si l’impact d’une telle opération n’est pas aussi sévère qu’un flux qui n’a pas pu être configuré, cela a un impact négatif sur l’interface utilisateur. Les éléments multimédias soudain et fréquent ne peuvent pas seulement avoir un impact important sur l’interface utilisateur, ce qui a pour effet de reconnecter les utilisateurs et de provoquer une perte de productivité.

La métrique est calculée en prenant le nombre total de flux déplacés divisé par le nombre total de flux configurés correctement :

-   **Taux d’échec de dépôt** = nombre total de flux d’appel interrompus/nombre total de flux d’appel interrompus

### <a name="define-your-target-metrics"></a>Définir vos indicateurs cibles

Cette section présente certaines des métriques de service fondamentales que nous utilisons pour évaluer l’état d’intégrité des services. En évaluant et en continuant à mettre en œuvre les mesures suivantes, vous pouvez vous assurer que vos utilisateurs disposent d’une qualité d’appel homogène et fiable. Pour vous aider à démarrer, les cibles suivantes sont fournies.

_Tableau 2-métriques d’évaluation de l’intégrité des cibles principales_
<table>
<tr>
<th rowspan="2" colspan="2" valign="center">Type de réseau</th><th rowspan="1">Cibles de qualité</th><th colspan="2">Cibles de fiabilité</th></tr>
<tr><th>Débit audio médiocre</th><th>Taux d’échec d’installation</th><th>Taux d’échec de dépôt</th></tr>
<tr><td rowspan="2"><strong>All</strong></td><td>Interne</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>Global</td><td>3,0%</td><td>1,0%</td><td>3,0%</td></tr>
<tr><td rowspan="5"><strong>Conférence</strong></td><td>Interne</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>Câble interne</td><td>1,0%</td><td>0,5%</td><td>1,0%</td></tr>
<tr><td>Wi-Fi 5 GHz Internal</td><td>1,0%</td><td>0,5%</td><td>1,0%</td></tr>
<tr><td>Wi-Fi 2,4 GHz Internal</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>Global</td><td>2,0%</td><td>0,5%</td><td>3,0%</td></tr>
<tr><td rowspan="4"><strong>P2P</strong></td><td>Interne</td><td>2,0%</td><td>0,5%</td><td>2,0%</td></tr>
<tr><td>Câblé/Wi-Fi 5 GHz interne</td><td>1,0%</td><td>0,5%</td><td>1,0%</td></tr>
<tr><td>Câblé/Wi-Fi 5 GHz globalement</td><td>2,0%</td><td>1,0%</td><td>1,0%</td></tr>
<tr><td>Global</td><td>2,0%</td><td>1,0%</td><td>3,0%</td></tr>
</table>


Il est important de discuter et de définir les cibles de votre organisation afin de répondre aux objectifs de votre entreprise.

### <a name="user-experience"></a>Expérience utilisateur

L’analyse de l’utilisation de l’utilisateur est une plus grande art que la science, car les métriques collectées ici ne signifient pas nécessairement qu’il y a un problème avec le réseau ou le service, mais qu’ils indiquent simplement que l’utilisateur a un problème. Microsoft propose un mécanisme d’étude intégré, connu sous le nom de l’option taux mon appel (RMC), pour vous aider à évaluer l’utilisation globale de l’utilisateur. RMC vous aidera à répondre aux questions suivantes du point de vue de vos utilisateurs :

-   Comment utiliser la solution ?
-   La solution est-elle facile à utiliser et intuitive, et est-elle prise en charge par les besoins en matière de communication au jour le jour ?
-   La solution m’aide-t-elle à accomplir mon travail ?
-   Quelle est la perception globale de la solution ?
-   Puis-je utiliser la solution à tout moment, où que je me trouve ?
-   Est-il possible de configurer et de tenir à jour un appel ?

#### <a name="rate-my-call"></a>Évaluer mon appel 

Le taux d’appel (RMC) est intégré aux équipes et à Skype entreprise, et est automatiquement configuré pour être affiché pour le participant après un intervalle de 10 appels ou 10%. Cette courte étude demande à l’utilisateur d’évaluer l’appel et de fournir un peu de contexte pour la qualité de l’appel. Une ou deux évaluations sont considérées comme médiocres, trois à quatre sont bonnes et cinq est excellent. Même s’il s’agit d’un indicateur de plus en plus, il s’agit d’une métrique utile pour découvrir les problèmes que peuvent manquer les métriques de service.

> [!Note]
> Jusqu’à ce que les utilisateurs soient sensibilisés à des enquêtes RMC en leur donnant du bon avis en plus de mauvaises réponses, les réponses sont généralement trop fortes. La plupart des utilisateurs répondent uniquement en cas de mauvaise qualité d’appel. C’est la raison pour laquelle vos rapports centre RMC peuvent être inclinés au mauvais moment même lorsque les métriques de service sont correctes.

Vous pouvez utiliser bord pour signaler les réponses des utilisateurs RMC et des exemples de rapports sont inclus dans le modèle bord. Toutefois, elles ne sont pas décrites en détail dans ce guide. Pour plus d’informations sur RMC dans Skype entreprise Online et sur les conseils pour éduquer les utilisateurs et obtenir des réponses RMC utiles, consultez [ce billet de blog](https://blogs.technet.microsoft.com/jenstr/2015/05/05/rate-my-call-in-skype-for-business-2015/).

#### <a name="client-and-device-readiness"></a>Disponibilité du client et de l’appareil

Vous avez besoin d’une stratégie de client et d’appareil solide pour vous assurer que vos utilisateurs disposent d’une interface utilisateur homogène et positive. Quelques principes clés pilotent chaque stratégie de compatibilité.

##### <a name="client-readiness"></a>Disponibilité du client

Une stratégie de disponibilité du client puissante garantit que vos utilisateurs utilisent la version la plus récente du client tout en profitant de la meilleure utilisation possible. Microsoft répare régulièrement le client Skype entreprise. Il est essentiel de veiller à ce que vous soyez assuré que votre environnement est essentiel pour votre réussite globale. Il est également important de ne pas oublier de corriger les pilotes réseau, vidéo, USB et audio, car ils sont souvent oubliés et peuvent affecter l’utilisation de l’utilisateur. Envisagez d’ajouter des pilotes réseau, Wi-Fi, vidéo, USB et audio à votre processus de gestion des correctifs actuel.

Nous vous recommandons de ne pas laisser les versions de vos clients dépasser de plus de six mois. Si vous utilisez Office « démarrer en un clic », vous êtes déjà en cours de mise à jour par le service. Pour vous aider à effectuer ce processus, utilisez les [versions de client](#client-versions)incluses, comme décrit plus loin dans ce guide. Vous pouvez également tirer parti des rapports d’exemples d’appel pour améliorer davantage votre stratégie de compatibilité client.

> [!IMPORTANT]
> Pour l’instant, les clients teams sont répartis et mis à jour automatiquement via le réseau de distribution de contenu Azure et sont tenus à jour par le service. En raison de cela, les activités d’investigation et de préparation du client ne s’appliquent pas aux équipes.


##### <a name="device-readiness"></a>Compatibilité de l’appareil

Aucune stratégie unique ne peut influer sur l’interface utilisateur en plus de la stratégie de compatibilité de votre appareil. La plupart des organisations sont heureux de supprimer les appareils inutiles (par exemple, les téléphones de bureau ou d’autres périphériques audio dédiés) des utilisateurs, et il s’agit souvent d’une justification essentielle pour le changement d’équipe ou de Skype entreprise. Néanmoins, les mêmes organisations hésitent parfois à proposer des périphériques de remplacement, même si ceux-ci sont moins chers. Les ordinateurs portables et PC modernes, même s’ils sont dotés de micro et de haut-parleurs intégrés, ne sont pas optimisés pour les appels voix sur IP (VoIP). Cela crée souvent une mauvaise interface pour tous les participants, en particulier si l’intervenant est dans un environnement bruyant. Le programme de certification des appareils de Microsoft garantit que lorsqu’un utilisateur participe à un appel téléphonique en utilisant n’importe quel appareil certifié pour teams ou Skype entreprise, il génère une utilisation supérieure à un appareil non certifié. 

Nous recommandons toujours aux utilisateurs de Microsoft teams et de Skype entreprise d’utiliser un casque ou un haut-parleur certifié lorsque vous participez à un appel voix via le client de bureau. Pour plus d’informations sur les appareils certifiés Microsoft, consultez les articles suivants concernant le [programme de certification](/SkypeForBusiness/certification/overview) et consultez le [catalogue solutions des partenaires](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Pour obtenir de l’aide sur la gestion de vos appareils, utilisez le rapport sur les [appareils](#devices), décrit plus loin dans ce guide.


### <a name="categories-of-quality"></a>Catégories de qualité

Le succès de l’opération de déploiement de grande qualité et fiable dépend de votre préversion du fonctionnement. Prenez en particulier en considération les trois catégories illustrées dans l’illustration suivante. ce guide est axé sur les éléments suivants :

-   **Réseau :** Qualité audio focalisée sur la métrique du rapport de flux médiocre (V.Q.P.R.D.), l’utilisation du réseau filaire et les sous-réseaux sans fil et l’identification de l’utilisation des proxys HTTP et du VPN.

-   **Points de terminaison :** Périphériques audio et versions clientes (Skype entreprise uniquement)

-   **Gestion du service :** Cette catégorie comprend deux sections :

    -   Tout d’abord, il incombe à Microsoft de gérer et de tenir à jour les équipes et services Skype entreprise online.

    -   Deuxièmement les tâches que votre organisation doit gérer pour garantir un accès fiable au service, par exemple, la mise à jour des informations de bâtiment et la maintenance des pare-feu pour les nouvelles adresses IP Office 365 lors de l’ajout d’une infrastructure au service.

![Graphique des catégories de qualité dans une organisation](media/qerguide-image-categories.png "Catégories de qualité au sein d’une organisation : gestion du service, points de terminaison et réseau.")

_Figure 3 : catégories critiques pour le déploiement d’équipes et de Skype entreprise Online_

Le graphique suivant décrit les tâches que vous devez exécuter pour chaque catégorie. Nous vous recommandons d’effectuer ces tâches une fois par semaine, au minimum.

La première fois que vous effectuez ces tâches, la première fois que vous effectuez cette opération, il est préférable de valider les configurations de déploiement pour la plupart des itérations. Après avoir atteint l’état souhaité en remplissant les cibles que vous avez définies, l’exécution de ces tâches vous aidera à gérer cet État.

<!--  This is a net new graphic, never was included in the online article. OOPS! -->
![Liste des tâches hebdomadaires par catégorie de qualité](media/qerguide-image-tasks.png "Liste des tâches hebdomadaires par catégorie de qualité")

#### <a name="service-management-tasks"></a>Tâches de gestion des services

Dans un premier monde de niveau Cloud, vous devez effectuer certaines tâches de gestion de service pour garantir une expérience utilisateur de grande qualité. Ces tâches vont de s’assurer qu’il y a suffisamment de bande passante pour parvenir au service sans saturer les liens Internet, en validant la qualité de service (QoS) en place sur toutes les zones réseau gérées et en passant par le reste des [plages d’adresses IP d’Office 365 sur les pare-feu](https://aka.ms/o365ips).

#### <a name="network-tasks"></a>Tâches réseau

Il existe deux catégories de tâches réseau : fiabilité et qualité. Le niveau de fiabilité est axé sur la mesure des capacités de l’utilisateur à passer des appels avec succès et de rester connecté. La qualité porte sur la télémétrie agrégée envoyée aux équipes et Skype entreprise Online par le client de l’utilisateur au cours de l’appel et une fois qu’il a terminé. 

Dans la mesure où la fiabilité s’est produite dans l’interface utilisateur, il est important de commencer à évaluer et à examiner ces mesures avant de plonger en qualité. 

#### <a name="endpoints-tasks"></a>Tâches de points de terminaison

Dans cette catégorie, la tâche principale consiste à valider les versions de client qui exécutent Skype entreprise sur les builds de bureau des 6 derniers mois, afin de s’assurer que les utilisateurs tirent parti des optimisations en continu effectuées par le client de bureau Skype entreprise. Par ailleurs, cette approche simplifie les tâches globales de gestion du client et offre une interface utilisateur homogène.

Le plus important est de surveiller quels appareils sont les plus courants dans votre déploiement et d’utiliser des appareils certifiés pour offrir la meilleure utilisation possible de l’utilisateur.


> [!IMPORTANT]
> Pour l’instant, les clients teams sont répartis et mis à jour automatiquement via le réseau de distribution de contenu Azure et sont tenus à jour par le service. Les activités d’investigation et de préparation du client ne s’appliquent pas aux équipes.

## <a name="cqd-basics"></a>Notions de base sur bord

Cette section décrit les principes de base de l’utilisation de bord. Des instructions sont fournies pour les rubriques suivantes :

-   Qu’est-ce que bord ?
-   Attentes avec bord
-   Trouver votre ID de locataire
-   Création de rapports sur Microsoft teams et Skype entreprise
-   Première et deuxième classification
-   Dimensions, mesures et filtres
-   Flux et appels
-   Appels intéressants, médiocres et non classés
-   Sous-réseaux courants

Pour des formations et des ressources plus détaillées, voir l' [annexe](#other-resources).

### <a name="what-is-cqd"></a>Qu’est-ce que bord ?

Le tableau de bord de qualité des appels (bord) vous permet de mieux comprendre la qualité des appels passés à l’aide d’équipes et de services Skype entreprise. BORD est conçu pour aider les administrateurs de Skype entreprise et équipes et les ingénieurs réseau à optimiser le réseau et à se familiariser avec la qualité, la fiabilité et l’interface utilisateur. BORD examine la télémétrie globale d’une entreprise dans laquelle les modèles globaux peuvent devenir évidents, ce qui permet aux membres du personnel de passer des examens éclairés et de planifier des activités de correction pour optimiser l’impact. BORD fournit des rapports de mesures qui fournissent des indications sur la qualité générale, la fiabilité et l’utilisation de l’utilisateur.

Ce guide va vous aider à comprendre les principaux concepts de bord pour vous aider à optimiser l’impact que vous pouvez apporter pour améliorer l’utilisation de teams ou de Skype entreprise online. Vous trouverez d’autres ressources bord dans l' [annexe](#other-resources).

### <a name="expectations-using-cqd"></a>Attentes avec bord

BORD, même s’il est utile pour analyser des tendances et des sous-réseaux, ne fournit pas toujours une cause spécifique pour un scénario donné. Il est important de comprendre ceci et de définir les attentes appropriées lors de l’utilisation de bord :

-   BORD ne fournit pas la cause racine de chaque scénario.
-   BORD ne contient pas les flux de votre système téléphonique ou de conférence audio.
-   BORD appelle des zones pour une étude plus approfondie en fonction des tendances.

### <a name="report-editions"></a>Éditions de rapport

Il existe deux éditions de rapport dans bord Online : Summary et detailed. Utilisez le menu déroulant situé dans la barre située en haut de l’écran pour ouvrir une édition de rapport. Le nom de l’édition de rapport sélectionnée apparaît en haut de l’écran.

-   Les rapports de synthèse sont statiques et ne peuvent pas être modifiés, téléchargés ou exportés. 
-   Les rapports détaillés sont entièrement personnalisables et peuvent être téléchargés dans un fichier CSV, exporté ou cloné.

Pour une description complète de la différence entre les deux éditions, voir [cet article](turning-on-and-using-call-quality-dashboard.md).

Nouveauté de janvier 2020 : [Télécharger les modèles de requête Power bi pour bord](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modèles Power BI personnalisables que vous pouvez utiliser pour analyser et enregistrer vos données bord.

_Figure 4 : catégories de rapports bord_

Les rapports de synthèse sont répartis en quatre catégories :

-   **Rapports récapitulatifs** insistez sur l’analyse des tendances de qualité avec des rapports quotidiens, mensuels et de tableau pour vous aider à identifier les sous-réseaux de qualité médiocre. Il s’agit de la page d’accueil par défaut lorsque vous vous connectez pour la première fois à bord online.
-   **Les rapports d’emplacement améliorés** vous focalisent sur l’analyse des tendances de qualité en fonction des informations d’emplacement. Pour utiliser ces rapports, vous devez avoir téléchargé un fichier de construction.
-   Les **rapports de fiabilité** s’imposent sur l’analyse des tendances de fiabilité pour l’audio, la vidéo, le partage d’écran vidéo (VBSS) et le partage d’application.
-   Les **rapports qualité de performance** constituent une version « allégée » des modèles QER détaillés, en insistant sur les principaux domaines qui vous intéressent à l’analyse de la qualité et de la fiabilité du son.

### <a name="report-types"></a>Types de rapports

Vous avez le choix entre deux types de rapports dans bord, selon la manière dont vous voulez afficher vos données. Même si ce guide ne couvre pas les spécificités de la création d’un type de rapport sur un autre, les modèles bord QER fournissent une combinaison de rapports graphiques et de tableaux personnalisés que vous pouvez utiliser :

-   Rapports de graphique créez des graphiques à barres graphiques pour représenter les données dans un format visuel. Il est préférable d’utiliser des rapports graphiques pour visualiser les données sur une période donnée.
-   Les rapports de tableau sont utiles pour examiner les mesures et les dimensions individuelles lorsque vous exportez les rapports vers des fichiers CSV pour les manipuler dans Microsoft Excel.

### <a name="tenant-id"></a>ID de locataire

Certains rapports bord requièrent l’inclusion d’un filtre pour votre ID de client. En raison de la façon dont bord agrège les données, la télémétrie des participants fédérés est incluse. Même si cela peut s’avérer utile lors de l’analyse des tendances, des rapports client et d’appareil nécessitent que vous filtrez les données vers un client spécifique pour exclure la télémétrie des participants fédérés. Si vous ne connaissez pas votre ID de client, vous pouvez utiliser l’une des méthodes suivantes pour le Rechercher.

> [!Note]
> Ces méthodes nécessitent les autorisations suivantes :<ul><li>Rôle d’administrateur général</li><li>Rôle d’administrateur Skype entreprise</li></ul>

#### <a name="azure-portal"></a>Portail Azure

1.  Connectez-vous au portail Microsoft Azure :<https://portal.azure.com>

2.  Sélectionnez **Azure Active Directory**.

3.  Sous **gérer**, sélectionnez **Propriétés**. L’ID de locataire est affiché dans la zone ID de l' **Annuaire** .

#### <a name="azure-powershell"></a>Azure PowerShell

1. [Installez le module Microsoft Azure PowerShell Service Management](https://docs.microsoft.com/powershell/azure/servicemanagement/install-azure-ps?view=azuresmps-4.0.0).

2. Ouvrez une fenêtre de commande Azure PowerShell et exécutez le script suivant en entrant vos informations d’identification Office 365 lorsque vous y êtes invité : 

   ```PowerShell
   Login-AzureRmAccount
   ```

3. L’ID de locataire est indiqué dans la sortie.

#### <a name="skype-for-business-online-admin-center"></a>Centre d’administration Skype entreprise Online

1.  Accédez à <https://portal.office.com>.

2.  Connectez-vous à l’aide de votre compte d’administrateur client.

3.  Dans le **Centre d’administration**, sélectionnez **Skype entreprise** .

4.  L’ID de locataire est répertorié en tant qu' **ID d’organisation** dans la page d’accueil.

#### <a name="skype-for-business-online-using-powershell"></a>Skype entreprise Online avec PowerShell

1. [Configurer votre ordinateur pour Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

2. Exécutez la commande suivante :

   ```PowerShell
   (Get-cstenant).tenantid
   ```

3. L’ID de locataire est affiché en tant que GUID.

### <a name="teams-vs-skype-for-business"></a>Équipes et Skype entreprise

BORD pouvez créer des rapports sur les équipes et la télémétrie de Skype entreprise. Néanmoins, il peut arriver que vous souhaitiez créer un rapport pour examiner la télémétrie d’équipes dans Skype entreprise.

#### <a name="summary-reports"></a>Rapports de synthèse

Pour modifier la page rapports de synthèse de sorte qu’il ne s’affiche que dans teams ou Skype entreprise, sélectionnez le menu déroulant **filtre du produit** en haut de l’écran, puis sélectionnez le produit souhaité.

![Capture d’écran du menu déroulant affichant les options de filtrage](media/qerguide-image-productfilter.png)

_Figure 5 : sélectionner un filtre produit_

#### <a name="detailed-reports"></a>Rapports détaillés

Pour filtrer tous les rapports détaillés, dans la barre de navigation, ajoutez le code suivant à la fin de l’URL :

```PowerShell
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Example**

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Pour plus d’informations sur les filtres d’URL, voir [filtrage de rapports](#filtering-reports) plus loin dans cette section.

Pour filtrer un rapport détaillé individuel, ajoutez le filtre ``Is Teams`` au rapport et attribuez-lui la valeur true ou false. Pour plus d’informations, reportez-vous à la section [édition de rapports](#editing-reports) plus loin dans cette section.

![Capture d’écran de la page Ajouter un filtre](media/qerguide-image-addteamsfilter.png)

_Figure 6 : ajouter un filtre Microsoft teams à un rapport_


### <a name="managed-vs-unmanaged-networks"></a>Réseaux gérés et non gérés

Par défaut, tous les points de terminaison dans bord sont classés comme extérieurs. Dès qu’un fichier de création est présenté, nous pouvons commencer à examiner les données du point de terminaison géré. Comme indiqué précédemment, les réseaux dans bord sont définis comme suit :

-   Un _réseau géré_, souvent appelé Internal ou Internal, peut être influencé et contrôlé par l’organisation. Il s’agit du réseau interne local, du réseau WAN distant et du VPN.
-   Un _réseau non géré_, souvent appelé externe ou extérieur, ne peut pas être influencé ou contrôlé par l’organisation. Par exemple, un réseau d’hôtel ou d’aéroport est un réseau non géré.

### <a name="dimensions-measures-and-filters"></a>Dimensions, mesures et filtres

Une requête bord bien formée contient les trois paramètres suivants :

-   **Dimension :** Je souhaite faire pivoter les données.

-   **Action :** Ce que je veux signaler.

-   **Filtrer :** Le mode de réduction du jeu de données retourné par la requête.

Une autre façon de procéder consiste à noter qu’une _dimension_ correspond à la fonction de regroupement, qu’une _mesure_ est une donnée qui m’intéresse et qu’un _filtre_ correspond à la façon dont vous souhaitez affiner les résultats pour les résultats pertinents pour ma requête.

Voici un exemple de requête bien formée : **afficher les flux médiocres [mesure] par sous-réseau [dimension] pour le bâtiment 6 [filtre]**. Pour plus d’informations, voir [dimensions et mesures disponibles dans bord](https://aka.ms/cqd-dm).

### <a name="first-vs-second"></a>Première et deuxième 

De nombreux axes et mesures dans bord sont classés comme premiers ou secondes. BORD n’utilise pas de champs d’appelant/appelants, car ils ont été renommés en _premier_ et en _second_ , car il existe des étapes intermédiaires entre l’appelant et l’appelé. La logique suivante détermine le point de terminaison impliqué comme d’abord :

-   **Tout d’abord** , il s’agit d’un point de terminaison serveur (serveur de conférence, serveur de médiation, etc.) si un serveur est impliqué dans le flux ou dans l’appel.

-   Le **second** sera toujours un point de terminaison client, sauf si le flux est entre deux points de terminaison serveur.

-   Si les deux points de terminaison sont du même type, le choix qui est le premier repose sur le classement interne de la catégorie de l’agent utilisateur. Cela garantit la cohérence de l'organisation.

Pour plus d’informations sur la détermination du premier ou du deuxième point de terminaison, voir [dimensions et mesures disponibles dans bord](https://aka.ms/cqd-dm).

### <a name="stream-vs-call"></a>Flux ou appel

Vous devez comprendre la différence entre un appel et un flux pour choisir correctement les dimensions ou les mesures que vous allez examiner dans bord. Même si le focus principal de bord est sur les flux, les mesures basées sur les appels sont également disponibles.

-   **Flux :** Un _flux_ existe entre deux points de terminaison. Il n’y a qu’un seul flux pour chaque direction, et deux flux sont requis pour la communication. Les flux permettent de rechercher des bâtiments, des réseaux ou des sous-réseaux. Dans certains cas, les appels et les flux sont utilisés dans le nom de la mesure (par exemple, le flux de configuration des appels ou le flux d’appel rejeté). Celles-ci sont toujours classées en flux.

-   **Appel :** Un _appel_ est le regroupement de tous les flux de tous les participants. Un appel se compose d’au moins deux flux. Un seul appel aura au moins deux points de terminaison, chacun avec un minimum d’un flux.

Pour obtenir des instructions supplémentaires sur la façon dont la dimension ou la mesure fait référence à un appel ou à un flux, voir [dimensions et mesures disponibles dans bord](https://aka.ms/cqd-dm)

### <a name="good-poor-and-unclassified-calls"></a>Appels intéressants, médiocres et non classés

Un appel est classé comme bon, médiocre ou non classé. Prenons un moment pour parler de chacun d’eux plus en détail.

-   **Bon ou médiocre :** Un appel bon ou médiocre se compose d’un appel qui contient un ensemble complet de métriques de service pour lequel un rapport QoE complet a été généré et reçu par le service. Le fait de déterminer si un flux est correct ou médiocre est décrit [plus haut dans ce guide](#poor-stream-rate).

-   Non **classées :** Un flux non classé ne contient aucun ensemble complet de métriques de service. Il peut s’agir d’appels courts (généralement moins de 60 secondes) où les moyennes n’ont pas pu être calculées et un rapport QoE n’a pas été généré. Le motif le plus courant pour les appels non classés est qu’il n’y a pas eu de faible taux d’utilisation des paquets. C’est par exemple le tout participant qui rejoint une réunion en silence et ne parle jamais. Le participant reçoit, mais ne transmet pas, de contenu multimédia. Si les éléments multimédias ne sont pas transmis, il n’y a aucune mesure disponible pour bord à utiliser pour classifier le flux multimédia sortant du point de terminaison.

Pour plus d’informations sur le processus de classification des flux, voir [cet article](stream-classification-in-call-quality-dashboard.md).

### <a name="common-subnets"></a>Sous-réseaux courants

Les sous-réseaux courants sont des sous-réseaux privés spécifiques utilisés par des hôtels, des réseaux familiaux, des points d’accès et des zones similaires. Le triage de ces sous-réseaux est difficile en raison de leur utilisation massive. Si votre organisation utilise l’un de ces sous-réseaux communs, il est recommandé de déplacer ce réseau vers un autre sous-réseau. Le création de rapports sera plus simple dans bord. Dans le cas contraire, les rapports du modèle All Networks ont été configurés de manière à exclure ces sous-réseaux pour les éliminer en tant que source de mauvaise qualité. Les sous-réseaux courants sont définis ci-dessous. leurs répercussions varient en fonction de l’organisation.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Lorsque vous étudiez un réseau géré qui utilise un sous-réseau commun, vous devez utiliser la deuxième dimension IP locale réflexive pour les sous-réseaux de groupe. Cette dimension contient l’adresse IP publique du point de terminaison.

## <a name="cqd-online"></a>BORD Online

Cette section décrit les principes de base de l’accès à bord. Des instructions sont fournies pour les rubriques suivantes :

-   Accès à bord Online
-   Commencer à utiliser bord
-   Modification de rapports dans bord
-   Filtrage de rapports dans bord
-   Importation de rapports dans bord

Pour des formations et des ressources plus détaillées, voir l' [annexe](#other-resources).

### <a name="access-cqd-online"></a>Accès à bord Online

Vous pouvez accéder à bord de l’une des trois manières suivantes :

-   Accédez à <https://cqd.teams.microsoft.com>.

-   Accédez au **Centre d’administration Microsoft teams** et sélectionnez le lien vers bord, comme le montre l’illustration suivante.

    ![Capture d’écran du tableau de bord de qualité des appels sélectionné.](media/qerguide-image-mopo.png "Dans le volet de navigation de gauche, le lien vers le tableau de bord de qualité des appels est sélectionné.")

    _Figure 7 : accès à bord par le biais du centre d’administration Microsoft teams_

-   Accédez à l’ancien > **Outils**du **Centre d’administration Skype entreprise**et sélectionnez le lien vers bord, comme le montre l’illustration suivante.

    ![Capture d’écran de bord sélectionnée dans le volet principal.](media/qerguide-image-legacyui.png "Outils est sélectionné dans le volet de navigation gauche, et le lien vers bord est sélectionné dans le volet principal.")

    _Figure 8 : accès à bord par le biais du centre d’administration Skype entreprise_


### <a name="getting-started"></a>Prise en main

Lorsque vous accédez à bord pour la première fois, vous verrez la page rapports de synthèse. La plupart des rapports décrits dans ce guide sont des rapports détaillés personnalisés. Pour commencer à utiliser les rapports détaillés, sélectionnez **rapports de synthèse** dans la partie supérieure de la page, puis sélectionnez **rapports détaillés**.

![Capture d’écran montrant des types de rapports disponibles dans bord](media/qerguide-image-choosereports.png)

_Figure 9 : accéder aux rapports détaillés_

La page rapports détaillés de bord se présente comme suit.

![capture d’écran illustrant des éléments qui composent un rapport détaillé](media/qerguide-image-detailedreportspage.png)

|             |           |
| ------------|-----------|
| ![Icône du numéro 1 qui référence une légende dans la capture d’écran précédente](media/qerguide-image-callout1.png "unes") | Le volet Résumé affiche le contexte pour le jeu de rapports qui s’affiche à droite. |
| ![Icône du numéro 2 qui référence une légende dans la capture d’écran précédente](media/qerguide-image-callout2.png "Color") | Vous pouvez sélectionner **modifier** dans le volet récapitulative pour définir les propriétés de niveau rapport (y compris la hauteur de l’axe y) et importer les nouveaux modèles. |
| ![Icône du numéro 3 qui référence une légende dans la capture d’écran précédente](media/qerguide-image-callout3.png "suivantes") | Le barre de navigation permet aux utilisateurs d’identifier leur emplacement actuel dans la hiérarchie de l’ensemble de rapports. |
| ![Icône du numéro 4, référençant une légende dans la capture d’écran précédente](media/qerguide-image-callout4.png "trois") | Les rapports incluant des rapports enfants apparaissent avec un lien bleu. En sélectionnant le lien, vous pouvez explorer les rapports enfant. |

_Figure 10-page rapports détaillés_

Pointez sur les graphiques à barres et les courbes de tendance dans le rapport pour afficher les valeurs détaillées. Le rapport sur lequel le focus est affiché affiche le menu d’action : **modifier**, **cloner**, **supprimer**, **Télécharger**et **exporter l’arborescence du rapport**.

### <a name="editing-reports"></a>Modification de rapports

Lorsque vous sélectionnez **modifier** dans le menu action d’un rapport, vous ouvrez l’éditeur de requête. Chaque rapport est stocké par une requête dans bord. Il s’agit de la visualisation des données renvoyées par la requête. L’éditeur de requête est une interface utilisateur permettant de modifier ces requêtes en plus des options d’affichage du rapport, comme illustré dans la figure ci-dessous.

![Capture d’écran illustrant des éléments qui composent un état modifié.](media/qerguide-image-queryeditor.png)

|             |           |
| ------------|-----------|
| ![Icône du numéro 1 qui référence une légende dans la capture d’écran précédente](media/qerguide-image-callout1.png "unes") | Pour ce faire, vous pouvez choisir des dimensions, des mesures et des filtres dans le volet gauche. Pointez sur une valeur existante pour afficher un bouton de fermeture (**X**) que vous pouvez sélectionner pour supprimer la valeur.<ul><li>En sélectionnant la cote ou la mesure, vous pouvez modifier le titre en modifiant le champ de **titre** . Vous pouvez également modifier l’ordre en cliquant sur les flèches bleu vers le haut ou le bas dans le volet supérieur.</li><li>Sélectionner (**+**) en regard d’un titre permet d’ouvrir la boîte de dialogue permettant d’ajouter une nouvelle dimension, mesure ou filtre.</li><li>Entrez les premières lettres de la dimension, de la mesure ou du filtre dans le champ **Rechercher** pour filtrer la liste et faciliter la recherche.</li></ul> |
| ![Icône du numéro 2 qui référence une légende dans la capture d’écran précédente](media/qerguide-image-callout2.png "Color") | Le volet supérieur affiche des options de personnalisation du graphique. |
| ![Icône du numéro 3 qui référence une légende dans la capture d’écran précédente](media/qerguide-image-callout3.png "suivantes") | L’éditeur de requête affiche un aperçu de l’État. |
| ![Icône du numéro 4, référençant une légende dans la capture d’écran précédente](media/qerguide-image-callout4.png "trois") | Utilisez la zone d' **édition** en bas de l’écran pour créer ou modifier une description détaillée du rapport. |

_Figure 11-éditeur de requête_

### <a name="filtering-reports"></a>Filtrage de rapports

Les modèles fournis incluent plusieurs requêtes et filtres de rapport intégrés. Les sections suivantes décrivent les filtres les plus fréquemment utilisés dans les modèles.

#### <a name="url-filter"></a>Filtre d’URL

Vous pouvez utiliser un filtre d’URL pour filtrer chaque rapport pour une dimension spécifique. Les filtres d’URL les plus courants permettent de filtrer les rapports de manière à exclure la télémétrie des participants fédérés ou à se concentrer sur teams ou Skype entreprise online. Nous vous recommandons d’utiliser les filtres pour les marquer facilement. 

L’exclusion des données fédérées des rapports bord est utile lorsque vous changez de bâtiment ou de réseau dans lequel les points de terminaison fédérés peuvent influencer vos rapports.

Pour implémenter un filtre d’URL, dans la barre d’adresses du navigateur, ajoutez le code suivant à la fin de l’URL :

```PowerShell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

Example  

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]```

Pour filtrer les rapports pour teams ou Skype entreprise, ajoutez le code suivant à la fin de l’URL :

```PowerShell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

Example

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Is Teams]|[TRUE]```


> [!NOTE]
> Les exemples d’URL ci-dessus sont uniquement destinés à la représentation visuelle. Utilisez le lien bord par défaut de <https://cqd.teams.microsoft.com>.


#### <a name="query-filters"></a>Filtres de requête

Les filtres de requête sont implémentés à l’aide de l’éditeur de requête dans bord. Ces filtres sont utilisés pour réduire le nombre d’enregistrements renvoyés par bord, ce qui a pour effet de limiter les temps d’exécution des requêtes et de la taille globale du rapport. Cela est particulièrement utile pour filtrer les réseaux non gérés. Les filtres répertoriés dans le tableau suivant utilisent des expressions régulières (RegEx).

_Tableau 3 : filtres de requête_

| Filtre         | Description          | Exemple de filtre de requête bord      |
|----------------|----------------------|-------------------------------|
| Pas de valeurs non renseignées   | Certains filtres n’ont pas la possibilité de filtrer les valeurs vides. Pour filtrer les valeurs vides manuellement, utilisez l’expression vide et définissez le filtre sur égal à ou différent de selon vos besoins.      | \< \> Nom \^du \\deuxième bâtiment\*\$                       |
| Exclure les sous-réseaux courants | Si vous n’avez pas de fichier de construction valide pour séparer la gestion de réseaux non gérés, les réseaux domestiques seront inclus dans les rapports. Ces sous-réseaux personnels se trouvent en dehors de la portée du contrôle et peuvent être rapidement exclus d’un rapport. Les sous-réseaux courants, tels que définis dans ce guide, sont 10.0.0.0, 192.168.1.0 et 192.168.0.0. | Deuxième sous \< \> - \| réseau \| 10.0.0.0 192.168.0.0 192.168.1.0 |
| Affichage intérieur uniquement  | Utilisé pour filtrer un rapport pour une gestion (interne) ou non gérée (à l’extérieur). Le modèle bord géré est déjà préconfiguré avec ces filtres.       | Deuxième dans l’entreprise = intérieur        |

#### <a name="report-filters"></a>Filtres de rapport

Pour implémenter des filtres de rapport, vous devez ajouter un filtre au rapport restitué dans l’éditeur de requête ou directement dans le rapport. Les filtres de rapport suivants sont utilisés dans le modèle.

_Tableau 4 : filtres de rapport_

| Filtre     | Description                            | Exemple de filtre de rapport bord         |
|------------|----------------------------------------|-----------------------------------|
| Month      | Commencez par l’année, puis mois. | 2017-10                           |
| Alphabétique | Filtre tout caractère alphabétique. | [a-z]                             |
| Numériques    | Filtre tout caractère numérique.    | [0-9]                             |
| Pourcentage | Filtres pour un pourcentage.              | ([3-9]\\.) \|([3-9])\|([1-9] [0-9]) |

## <a name="import-the-cqd-templates"></a>Importer les modèles bord

Ce guide inclut [deux modèles bord](https://aka.ms/qertemplates). Ces modèles accélèrent l’utilisation de bord et vous permettent de tirer parti des fonctionnalités de bord pour apporter un impact sur les équipes de vos utilisateurs ou sur Skype entreprise. Le modèle tous les réseaux, bien qu’optimisé pour fonctionner avec un fichier de données bâtiment, peut être utilisé lorsque vous travaillez dans le cadre de la collecte et du chargement d’informations de bâtiment dans bord, comme décrit dans la section suivante.

**Pour importer les modèles (. CQDX) dans bord Online**

1. Accédez à <https://cqd.teams.microsoft.com>.

2. S’authentifier à l’aide de vos informations d’identification d’administration Office 365.

   > [!NOTE]
   > Vous devez avoir le rôle d’administrateur général Office 365, d’administrateur Skype entreprise ou de signalement de lecteurs pour accéder à bord. 

3. Sélectionnez le menu **rapports de synthèse** en haut de la page, puis sélectionnez **rapports détaillés**.

4. Dans le volet Résumé, sélectionnez **Importer**. Accédez à l’emplacement CQDX enregistré, sélectionnez le modèle CQDX, puis sélectionnez **ouvrir**.

5. Une fois le modèle chargé, une fenêtre contextuelle affiche le message « l’importation du rapport a réussi ». Sélectionnez **OK.**

   ![Capture d’écran de la notification d’importation réussie](media/qerguide-image-importmessage.png "Notification indiquant que le modèle a été correctement importé")

6. Répétez les étapes 4 et 5 pour le deuxième modèle bord.

> [!NOTE]
> Les modèles bord sont importés par utilisateur. Si d’autres utilisateurs doivent utiliser le rapport, ils doivent se connecter et importer les modèles dans leur instance bord. 


## <a name="building-mapping"></a>Mappage de bâtiment

Dans le cas d’une équipe ou d’un déploiement de Skype entreprise Online, tous les clients sont externes. Par défaut, tous les clients sont signalés comme extérieurs à bord Online, que le client ait été connecté ou non au réseau d’entreprise interne.

Lorsque vous utilisez bord, vous devez connaître l’emplacement d’un point de terminaison et savoir s’il est connecté à un réseau que vous pouvez gérer ou un réseau que vous ne pouvez pas gérer, en partant du principe que vous pouvez uniquement améliorer les réseaux que vous pouvez gérer. En chargeant le sous-réseau et en créant des informations sur bord Online, vous activez bord pour déterminer si le point de terminaison a été connecté à un réseau d’entreprise/géré interne ou à un réseau externe/non géré.

### <a name="building-data-file-structure"></a>Structure du fichier de données

Le format du fichier de données que vous chargez doit respecter les exigences suivantes pour réussir le contrôle de validation avant téléchargement.

-   Il doit s’agir d’un fichier. TSV, ce qui signifie que sur chaque ligne, les colonnes sont séparées par une tabulation ou par un fichier CSV dans lequel chaque colonne est séparée par une virgule.

-   La taille du fichier ne doit pas dépasser 50 Mo.

-   Le contenu du fichier de données *ne doit pas inclure de en-têtes de tableau*. En d’autres termes, la première ligne du fichier de données doit être de véritables données, pas des en-têtes de colonnes telles que « réseau ».

-   Pour chaque colonne, le type de données peut uniquement être chaîne, nombre ou bool. Si le type de données est numérique, la valeur doit être une valeur numérique ; s’il s’agit de bool, la valeur doit être égale à 0 ou 1.

-   Pour chaque colonne, si le type de données est String, les données peuvent être vides (tout en étant tout de même séparées par un délimiteur approprié, c’est-à-dire un caractère de tabulation ou une virgule). Cela affecte simplement le champ à une valeur de chaîne vide.

-   Il doit y avoir 14 colonnes pour chaque ligne (ou 15 si vous souhaitez ajouter la colonne facultatif VPN). Chaque colonne doit avoir le type de données indiqué dans le tableau suivant, et les colonnes doivent être dans l’ordre indiqué dans le tableau.

_Tableau 5 : création d’une structure de fichier_

| Nom de la colonne        | Type de données | Exemple                   | Aide    |
|--------------------|-----------|---------------------------|-------------|
| Réseau            | String    | 192.168.1.0               | Obligatoire    |
| Nom réseau        | String    | États-Unis/Seattle/SEATTLE-SEA-1 | Obligatoire\*  |
| NetworkRange       | Numéro    | 26/08/03                        | Obligatoire    |
| BuildingName       | String    | SEATTLE-SEA-1             | Obligatoire\*  |
| Type de propriété      | String    | Chez                   | Facultatif    |
| Type de bâtiment       | String    | Arrêt            | Facultatif    |
| BuildingOfficeType | String    | Ingénieur               | Facultatif    |
| Ville               | String    | Seattle                   | Recommandation |
| ZipCode            | String    | 98001                     | Recommandation |
| Pays            | String    | Nous                        | Recommandation |
| État              | String    | WA                        | Recommandation |
| Région             | String    | MSUS                      | Recommandation |
| InsideCorp         | Bool      | 1                         | Obligatoire    |
| ExpressRoute       | Bool      | 0,4                         | Obligatoire    |
| VPN                | Bool      | 0,4                         | Facultatif    |

\*S’il n’est pas requis par bord, les modèles sont configurés pour afficher les noms de bâtiment et de réseau.

#### <a name="supernetting"></a>Le Super-réseautage

Vous pouvez utiliser le Super-réseautage, couramment appelé routage entre domaines (CIDR, Classless Inter-Domain Routing) au lieu de définir chaque sous-réseau. Un *super-réseau* est une combinaison de plusieurs sous-réseaux partageant un seul préfixe de routage. Au lieu d’ajouter une entrée pour chaque sous-réseau, vous pouvez utiliser l’adresse superréseau. Le Super-réseautage est pris en charge, mais nous ne recommandons pas son utilisation.

Par exemple, le bâtiment marketing de contoso se compose des sous-réseaux suivants :

-   10.1.0.0/24-premier étage
-   10.1.1.0/24-second étage
-   10.1.2.0/24 : troisième étage
-   10.1.3.0/24-quatrième étage

Au lieu d’ajouter une entrée pour chaque sous-réseau, vous pouvez utiliser l’adresse de super-réseau (dans cet exemple, 10.1.0.0/22).

-   Réseau = 10.1.0.0
-   Plage de réseaux = 22

Voici quelques éléments à prendre en compte avant d’implémenter le super-réseau :

-   Le Super-réseautage ne peut être utilisé que dans un mappage de sous-réseau doté d’un masque de 8 bits à 28 bits.

-   Le Super-affichage prend moins de temps, mais il s’agit du coût de la réduction de la richesse de vos données. Imaginons qu’il y a un problème de qualité lié au sous-réseau 200.1.2.0. Si vous avez implémenté le super-réseau, vous ne savez pas où se trouve dans le bâtiment le sous-réseau ou quel type de réseau il est (par exemple, un laboratoire). Si vous avez défini tous les sous-réseaux pour les informations d’emplacement du étage, vous pouvez voir cette distinction.

-   Il est important de veiller à ce que l’adresse du superréseau soit correcte et qu’elle ne soit pas interceptée.

-   Il est relativement courant de Rechercher 192.168.0.0 dans les données. Dans de nombreuses organisations, cela signifie que l’utilisateur est à la maison. Pour d’autres, il s’agit du schéma d’adresse IP d’un bureau satellite. Si votre organisation dispose de bureaux qui utilisent cette configuration, n’incluez pas celle-ci dans votre fichier de bâtiment, car il est difficile de distinguer les réseaux domestiques et internes à l’aide de sous-réseaux communs. Pour plus d’informations, voir la section sur les [sous-réseaux courants](#common-subnets)plus haut dans ce guide.

> [!IMPORTANT]
> La plage réseau peut être utilisée pour représenter une super-réseau. Les nouveaux téléchargements de fichiers de données de bâtiment seront examinés pour les plages qui se chevauchent. Si vous avez déjà téléchargé un fichier de construction, vous devriez télécharger le fichier actif et le télécharger à nouveau pour identifier les chevauchements et résoudre le problème. Tout chevauchement dans les fichiers précédemment téléchargés peut entraîner des mappages incorrects de sous-réseaux vers les bâtiments dans les rapports.

#### <a name="vpn"></a>VPN

Les données de qualité de l’expertise que les clients envoient à Office 365 (qui est l’endroit où les données bord sont sources) incluent un indicateur VPN. BORD le verra comme le premier VPN et les deuxièmes réseaux VPN. Toutefois, cet indicateur repose sur la création d’un rapport de fournisseurs de réseau privé virtuel (VPN) sur Windows, qui s’est inscrit sur une carte d’accès à distance. Les fournisseurs de réseaux VPN n’inscrivent pas correctement les cartes d’accès distant. Pour cette raison, il est possible que vous ne puissiez pas utiliser les filtres de requête VPN intégrés. Il existe deux approches permettant d’accueillir les sous-réseaux VPN dans le fichier de construction des informations :

- Définissez un **nom de réseau** en utilisant le texte « VPN » dans ce champ pour les sous-réseaux VPN.

  ![Capture d’écran de rapport QCD montrant un VPN utilisant le nom du réseau](media/qerguide-image-vpnnetworkname.png)

  _Figure 12-VPN utilisant le nom du réseau_

- Définissez un **nom de bâtiment** en utilisant le texte « VPN » dans ce champ pour les sous-réseaux VPN.

  ![Capture d’écran de rapport QCD montrant un VPN utilisant le nom de bâtiment](media/qerguide-image-vpnbuildingname.png)

  _Figure 13 : VPN avec nom de bâtiment_

> [!IMPORTANT]
> Certaines implémentations de réseau privé virtuel n’indiquent pas précisément les informations de sous-réseau. Le client VPN est fourni avec un sous-réseau 32 bits.  Comme indiqué dans la section précédente, bord ne peut pas identifier correctement un sous-réseau 32 bits.  Pour identifier avec précision un sous-réseau VPN dans bord, définissez le champ VPN sur 1 dans le fichier de construction.


> [!NOTE]
> Les connexions de réseau privé virtuel (VPN) ont été connues pour identifier de manière Inde une connexion réseau filaire Lorsque la connexion Internet sous-jacente est sans fil. Lorsque vous examinez la qualité de connexions VPN, vous ne pouvez pas supposer que le type de connexion a été correctement identifié.

### <a name="uploading-building-information"></a>Chargement des informations de bâtiment

Le tableau de bord des rapports de synthèse de bord inclut une page de **téléchargement de données de client** accessible en sélectionnant la balise lien de téléchargement de données du **client** dans le coin supérieur droit (recherchez l’icône d’engrenage). Cette page est utilisée pour permettre aux administrateurs de télécharger leurs propres informations, par exemple le mappage de l’adresse IP et des informations géographiques, le mappage de chaque point d’accès sans fil et son adresse MAC, etc.

1. Accédez à bord Online en accédant <https://cqd.teams.microsoft.com>à.

2. Sélectionnez l’icône d’engrenage dans le coin supérieur droit, puis choisissez **Télécharger les données du client** dans la page **rapports de synthèse** .

   ![Capture d’écran de la boîte de dialogue qui s’affiche lorsque les données sont en cours de téléchargement](media/qerguide-image-tenantdataupload.png)

   _Figure 14 : menu télécharger les données du client_

3. Si c’est la première fois que vous visitez bord, vous serez invité à télécharger les données de bâtiment. Vous pouvez sélectionner **Télécharger maintenant** pour accéder rapidement à la page **téléchargement de données du client** .

   ![Capture d’écran d’une bannière permettant à un utilisateur de télécharger des données de bâtiment](media/qerguide-image-buildingdatauploadbanner.png)

   _Figure 15-création d’une bannière de chargement de données_

4. Sur la page **téléchargement de données du client** , sélectionnez **Parcourir** pour choisir un fichier de données.

5. Après avoir sélectionné un fichier de données, spécifiez la **Date de début** et, éventuellement, spécifiez une date de fin.

6. Après avoir sélectionné la **Date de début**, sélectionnez **Télécharger** pour télécharger le fichier sur bord. <br><br>Le fichier est validé avant d’être chargé. En cas d’échec de la validation, un message d’erreur s’affiche et vous demande de corriger le fichier. La figure suivante illustre une erreur qui se produit lorsque le nombre de colonnes dans le fichier de données est incorrect.

   ![Exemple de boîte de dialogue affichant une erreur de chargement de données en bâtiment](media/qerguide-image-buildingdatauploaderror.png)
 
   _Figure 16-génération d’une erreur de chargement de données_

7. S’il n’y a aucune erreur lors de la validation, le chargement du fichier réussit. Vous pouvez ensuite voir le fichier de données chargé dans la table **Mes téléchargements** , qui affiche la liste complète des fichiers téléchargés pour le client actuel en bas de cette page.

> [!NOTE]
> Il faut parfois jusqu’à quatre heures pour terminer le traitement du fichier de construction. <br><br> Si vous avez déjà chargé un fichier de construction et que vous avez besoin d’ajouter des sous-réseaux qui peuvent avoir été manqués ou exclus, modifiez le fichier d’origine en ajoutant le nouveau sous-réseau, supprimez le fichier actif, puis rechargez le fichier que vous venez de modifier. Il ne peut y avoir qu’un seul fichier de données de bâtiment actif dans bord. 


### <a name="updating-a-building-file"></a>Mise à jour d’un fichier de bâtiment

Lors du rassemblement des informations de construction et de sous-réseau, les administrateurs chargent souvent le fichier de construction dans plusieurs itérations, en ajoutant de nouveaux sous-réseaux et leurs informations de bâtiment dès qu’il devient disponible. Lorsque cela se produit, vous devez recharger votre fichier de construction. Ce processus est comme le téléchargement initial comme décrit dans la section précédente, à quelques exceptions près, comme indiqué dans la section suivante.

> [!Important]
> Un seul fichier de construction peut être actif à la fois. Les fichiers de construction multiples ne sont pas cumulés.

#### <a name="adding-net-new-subnets"></a>Ajouter de nouveaux sous-réseaux net

Il peut arriver que vous deviez ajouter des sous-réseaux de nouveaux réseaux aux bord qui n’étaient pas à l’origine dans la topologie de votre réseau. Pour ajouter de nouveaux sous-réseaux à un réseau, procédez comme suit dans le portail de chargement des données du client bord :

1.  Modifiez le fichier de construction d’origine et indiquez une date de fin au moins un jour avant l’acquisition des sous-réseaux.
2.  Téléchargez le fichier d’origine, si vous n’avez pas encore de copie à jour.
3.  Ajoutez les nouveaux sous-réseaux personnels au fichier de construction d’origine.
4.  Transférez le fichier de construction que vous venez de modifier en suivant le processus ci-dessus, puis définissez la date de début pour un jour après la fin du fichier de construction précédent.

#### <a name="updating-the-current-building-file"></a>Mise à jour du fichier de construction actuel

Si un fichier de création est déjà chargé mais que vous devez ajouter des sous-réseaux manquants, procédez comme suit dans le portail de chargement des données du client bord :

1.  Téléchargez le fichier d’origine, si vous n’avez pas encore de copie à jour.
2.  Supprimez le fichier actif dans bord.
3.  Ajoutez les nouveaux sous-réseaux au fichier d’origine.
4.  Téléchargez le fichier de construction. Veillez à définir la date de début sur au moins huit mois avant que bord ne traitera les données historiques.

### <a name="missing-subnets"></a>Sous-réseaux manquants

Une fois que vous avez chargé les informations de bâtiment pour les réseaux gérés, chaque réseau géré doit avoir une association de bâtiment. Toutefois, ce n’est pas toujours le cas. en règle générale, un petit nombre de sous-réseaux est manqué. Cette section explique comment valider les réseaux manquants.

Accédez à la page **rapports détaillés** dans bord Online et accédez au **rapport de sous-réseau manquant** inclus dans les modèles bord. Tous les sous-réseaux avec 10 flux audio ou plus qui ne sont pas définis dans le fichier de données de bâtiment sont marqués comme extérieurs. Assurez-vous qu’il n’y a pas de réseaux gérés dans cette liste. Si le sous-réseau est manquant, mettez-le à jour et rechargez-le sur bord.

> [!IMPORTANT]
> Vous devez ajouter votre ID de locataire comme filtre de requête pour le **deuxième ID de client** à ce rapport afin de filtrer le rapport pour afficher uniquement les données client de votre organisation. Dans le cas contraire, le rapport va afficher des sous-réseaux fédérés.

> [!NOTE] 
> Veillez à ajuster le filtre de rapport mois par année au mois en cours. Sélectionnez **modifier**, puis ajustez le filtre de rapport **mois-année** pour enregistrer le nouveau mois par défaut.

![Capture d’écran montrant un rapport de sous-réseau manquant](media/qerguide-image-missingbuildingreport.png)

_Figure 17-rapport de bâtiment manquant_

### <a name="building-mapping-tools"></a>Outils de mappage de construction

Pour nous, il peut être difficile de mapper les sous-réseaux de votre organisation. Les grands réseaux globaux sont très complexes, les différentes équipes gérant leurs régions respectives, et il est possible qu’il n’y ait aucune seule source de vérité pour la topologie du réseau. Deux outils sont disponibles pour vous aider à démarrer l’exercice de mappage de bâtiment, décrit dans les sections suivantes.

#### <a name="cqd-tools"></a>Outils bord

Ces outils sont basés sur PowerShell et peuvent tirer parti des sites et services Active Directory (AD) et des services Microsoft DHCP pour vous aider à préremplir votre fichier de construction.  Ces outils peuvent vous aider à effectuer les tâches suivantes :

1.  Interrogez les sites et services d’annonces et créez un fichier d’immeuble en fonction des informations contenues dans.
2.  Interrogez un serveur ou un serveur DHCP Microsoft pour extraire des informations de sous-réseau et créer automatiquement un fichier de bâtiment.
3.  Validez un fichier de construction existant, en recherchant les doublons et les chevauchements.
4.  Recherchez les sous-réseaux non mappés dans bord.

Pour plus d’informations sur cet outil, voir [ce billet de blog](https://aka.ms/cqdtools).

#### <a name="network-planner"></a>Planificateur de réseau

Le planificateur de réseaux détermine et organise vos exigences réseau pour le déploiement de votre voix Cloud en quelques étapes simples. En fournissant les informations de mise en réseau de votre organisation et l’utilisation de la voix dans le Cloud, vous pouvez obtenir le calcul approximatif des exigences réseau pour le déploiement de votre voix Cloud, gérer et exporter ces détails pour la création de rapports, et afficher des zones pour une étude plus poussée et suivre les étapes suivantes.

Même si le planificateur de réseaux n’automatise pas entièrement le processus de mappage de bâtiment, une fois que les informations réseau sont entrées dans le planificateur réseau, il peut être exporté vers un fichier de construction prêt pour le chargement.

## <a name="reliability-investigations"></a>Investigations de fiabilité

La première étape pour améliorer la qualité consiste à évaluer l’état de la fiabilité au sein de l’organisation. Dans la mesure où la fiabilité est essentielle pour une utilisation positive de l’utilisateur, nous commençons par les deux composants qui mesurent la fiabilité :

1.  **Échecs de configuration :** L’appel n’a pas pu être établi.

2.  **Échecs de la suppression :** L’appel a été établi et arrêté de manière inattendue.

Dans cette section, nous allons aborder les méthodes permettant d’identifier les deux domaines.

> [!NOTE]
> Tous les rapports inclus dans les modèles ne sont pas abordés dans ce guide.  Toutefois, les méthodes de vérification décrites ci-dessous s’appliquent. Pour plus d’informations, reportez-vous à la description du rapport individuel.


### <a name="setup-failures"></a>Échecs de configuration

Par priorité, vous devez d’abord résoudre les problèmes d’installation liés à l’utilisation de l’interface utilisateur.

Commencez votre examen en évaluant le pourcentage d’échecs de configuration globaux pour l’organisation, puis donnez la priorité aux domaines d’examen en fonction du pourcentage le plus élevé en créant ou en réseau. 

#### <a name="setup-failure-trend-analysis"></a>Analyse des tendances d’échec d’installation

Ce rapport affiche le nombre total de flux, les échecs de configuration de flux et le taux d’échec de configuration de flux. Pointez sur l’une des colonnes pour afficher ses valeurs individuelles, comme illustré dans la figure ci-dessous. 

![Graphique affichant le pourcentage d’échecs de configuration de flux](media/qerguide-image-streamsetupfailures.png)

_Figure 19-échec de la configuration du flux audio_

##### <a name="analysis"></a>Étude

Ce rapport vous permet de répondre aux questions suivantes et de déterminer la marche à suivre suivante :

-   Quel est le pourcentage d’échec de configuration du total d’appels pour le mois en cours ?

-   Est-ce que le pourcentage d’échec de configuration d’un appel inférieur ou au-dessus de la mesure cible définie ?

-   Le problème est-il pire ou supérieur au mois précédent ?

-   La tendance de l’échec augmente-t-elle, elle est constante ou dégressive ?

Quelles que soient les réponses précédentes, prenez le temps de rechercher davantage en utilisant les sous-rapports compagnons pour rechercher des bâtiments ou sous-réseaux individuels susceptibles de nécessiter une correction. Même si le taux d’échec global est peut-être inférieur à la métrique cible, les taux d’échec pour un ou plusieurs bâtiments ou réseaux peuvent être supérieurs à la métrique cible et avoir besoin d’une étude.

#### <a name="setup-failure-investigations"></a>Investigations d’échecs de configuration 

Ce rapport de synthèse permet de détecter et d’isoler tout bâtiment ou réseau susceptible de nécessiter une correction.

> [!NOTE]
> Veillez à ajuster le filtre de rapport mois par année au mois en cours. Sélectionnez **modifier**, puis ajustez le filtre de rapport **mois-année** pour enregistrer le nouveau mois par défaut.


![Capture d’écran montrant les échecs de configuration](media/qerguide-image-setupfailuresbysubnet.png)

_Figure 20-échecs de configuration audio par sous-réseau_

##### <a name="remediation"></a>Remediation 

Focalisez-vous sur votre première action de correction sur les bâtiments ou sous-réseaux présentant le plus grand nombre d’échecs. Cela a un impact sur l’utilisation de l’utilisateur et de l’aide pour réduire rapidement le taux d’échecs de configuration des appels de l’organisation. Le tableau suivant répertorie les deux raisons pour lesquelles les échecs de configuration ont été signalés par bord.

_Tableau 7 : raisons de l’échec de configuration d’un appel_

| Raison de l’échec de configuration d’un appel       | Cause classique                    |
|----------------------------------|----------------------------------|
| Règle d’exemption de paquets | Indique que les équipements réseau en fonction du chemin d’accès ont empêché l’établissement du chemin d’accès multimédia en raison de règles de vérification approfondie des paquets. Cela peut être dû au fait que les règles de pare-feu ne sont pas correctement configurées. Dans ce scénario, l’établissement d’une connexion TCP réussie, mais pas la connexion SSL.      |
| Règle d’exception de bloc IP FW manquante      | Indique que les équipements réseau en fonction du chemin d’accès ont empêché le chemin multimédia d’être établis au réseau Office 365. Cela peut être dû au fait que des règles de proxy ou de pare-feu ne sont pas correctement configurées pour autoriser l’accès aux adresses IP et aux ports utilisés pour le trafic des équipes et Skype entreprise. |

Dès lors que vous commencez votre politique de correction, vous pouvez vous concentrer sur un immeuble ou un sous-réseau particulier. Comme décrit dans le tableau ci-dessus, ces problèmes sont dus à des configurations de pare-feu ou de proxy. Passez en revue les options du tableau suivant pour les actions de correction.

_Tableau 8-étapes suivantes pour la mise à jour de l’échec de configuration d’un appel_


|      Remediation      |                                                                                                                                                                                                                                                                                                                                                                   Aide                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configurer un ou plusieurs pare-feu | Travaillez avec votre équipe réseau et vérifiez la configuration de votre pare-feu par rapport à [la liste d’adresses IP d’Office 365](https://aka.ms/o365ips).<br><br>Vérifiez que les [sous-réseaux](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) et ports de média sont inclus dans les règles de pare-feu. <br><br>Vérifiez que les ports nécessaires (indiqués ci-dessous) sont ouverts dans le pare-feu. La priorité du protocole UDP doit être donnée, car TCP est considéré comme un protocole de restauration automatique pour le partage d’écran audio, vidéo et vidéo, et son utilisation affectera la qualité de l’appel. Le partage d’application RDP hérité utilise TCP uniquement.<br><ul><li>**TCP :** port 443</li><li>**UDP :** ports 3478 – 3481</li><ul> |
|        Vérifier         |                                                                                                                                                                                                                                                                 Utilisez l' [outil Microsoft Network Assessment](https://www.microsoft.com/download/details.aspx?id=53885) pour vérifier la connectivité du bâtiment ou du sous-réseau affecté à l’aide de la fonction de vérification de la connectivité.                                                                                                                                                                                                                                                                  |

### <a name="drop-failures"></a>Ignorer les échecs

Contrairement aux codes d’échec d’installation, CDQ n’a pas de code d’échec de remise pour indiquer la raison pour laquelle les échecs de suppression se produisent, ce qui complique l’isolation d’une cause initiale spécifique. Pour mieux trier les échecs de remise, utilisez une approche inférés. En réservant les centres d’intérêt pour les contenus multimédias, les correctifs de clients et de pilotes, et l’utilisation d’appareils certifiés pour les équipes et Skype entreprise, vous pouvez faire en sorte que les échecs de remise soient refusés.

#### <a name="drop-failure-trend-analysis"></a>Analyse des tendances d’échec de remise

Ce rapport affiche le volume total de flux audio, d’échecs de remise au total et le taux d’échec de la suppression. Pointez sur l’une des colonnes pour afficher ses valeurs, comme illustré dans la figure ci-dessous. 

![Graphique montrant le pourcentage de flux supprimés](media/qerguide-image-droppedstreamrate.png)

_Figure 21 : débit de rejet de flux_

##### <a name="analysis"></a>Étude

En utilisant ce type de rapport, vous pouvez répondre aux questions suivantes :

-   Quel est le taux d’échec de la remise actuelle ?
-   Le taux d’échec de la chute est-il inférieur à la valeur cible définie ?
-   Le problème est-il pire ou supérieur au mois précédent ?
-   La tendance de l’échec augmente-t-elle, elle est constante ou dégressive ?

Quelles que soient les réponses aux questions ci-dessus, prenez le temps de rechercher les bâtiments ou réseaux susceptibles de nécessiter une correction à l’aide de sous-rapports. Même si le taux d’échec de la suppression globale peut être inférieur à la métrique cible, le taux d’échec de la suppression d’un ou de plusieurs bâtiments ou réseaux peut se trouver au-dessus de la métrique cible et avoir besoin d’une étude.

#### <a name="drop-failure-investigations"></a>Échecs de la liste des investigations

Les échecs signalés ici indiquent que l’appel a été interrompu de manière inattendue et ont entraîné une utilisation négative de l’utilisateur. À la différence des rapports de tendance, ces rapports fournissent des informations supplémentaires sur les sous-réseaux spécifiques qui nécessitent des examens supplémentaires.

> [!NOTE]
> Veillez à ajuster le filtre mois en cours au mois en cours. Sélectionnez **modifier**, puis ajustez l' **année du mois** pour enregistrer le nouveau mois par défaut.


![Rapport indiquant le nombre et le pourcentage de perte d’échecs](media/qerguide-image-dropfailuresbysubnet.png)

_Figure 22 : rejeter les échecs par sous-réseau_

##### <a name="remediation"></a>Remediation

L’utilisation des rapports de tableau inclus vous permet d’isoler les zones de problèmes du réseau où le taux de remise est supérieur à la mesure cible que vous avez définie. Focalisez-vous sur votre première action de correction sur les bâtiments ou sous-réseaux qui présentent le nombre total de flux de flux, pour apporter le plus grand impact.

Causes fréquentes des rejets d’appel :

-   Sortie Internet sous-configurée
-   Aucun QoS configuré sur les réseaux contraintes
-   Versions de client plus anciennes
-   Comportement des utilisateurs

Après avoir détecté votre problème, vous pouvez utiliser l' [analyse des appels](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309) pour passer en revue les utilisateurs de ce bâtiment pour des problèmes spécifiques. L’analyse des appels contient des données d’identification personnelle supplémentaires et peut s’avérer utile pour identifier les raisons potentielles des échecs de remise.

Quelle que soit la prochaine étape, il est recommandé de faire savoir au support technique qu’un problème a été détecté dans les bâtiments ou sous-réseaux spécifiques. De cette façon, ils peuvent rapidement répondre aux appels entrants et trier les utilisateurs plus efficacement. Les utilisateurs avec indicateur peuvent ensuite être notifiés à l’équipe d’ingénierie pour de plus amples examens.

Le tableau suivant répertorie quelques méthodes courantes pour gérer et corriger les échecs de suppression.

_Tableau 9-étapes suivantes pour la mise à jour de la remise d’appel_

| Remediation                              | Aide                      |
|------------------------------------------|-------------------------------|
| **Réseau/Internet**                         | **Encombrement**: collaborez avec votre équipe réseau pour contrôler la bande passante sur des bâtiments/sous-réseaux spécifiques pour vérifier qu’il y a des problèmes de surutilisation. Si vous confirmez la congestion du réseau, envisagez d’augmenter la bande passante pour la création ou l’application de QoS. Utilisez les rapports de synthèse de l' [État qualité](#quality-investigations) de la qualité incluse pour passer en revue les sous-réseaux de problèmes afin de résoudre les problèmes de gigue, de latence et de perte de paquets, car ils précèdent souvent un flux interrompu.<br><br>**Qualité**de service (QoS) : si la bande passante augmente ou n’est pas adaptée, envisagez d’implémenter QoS. Cet outil est très efficace pour gérer le trafic congestionné et peut garantir que les paquets multimédias du réseau géré sont classés par priorité au-dessus du trafic non multimédia. Par ailleurs, s’il n’y a pas de justification évidente de la bande passante, envisagez les solutions suivantes :<ul><li>[Conseils QoS de Microsoft teams](qos-in-teams.md)</li></ul><br>**Effectuer une évaluation de la disponibilité du réseau**: une évaluation du réseau fournit des détails sur l’utilisation de la bande passante attendue, sur la gestion de la bande passante et des changements réseau, ainsi que sur les pratiques recommandées pour les équipes et Skype entreprise. En utilisant le tableau précédent comme source, vous disposez d’une liste de bâtiments ou de sous-réseaux qui constituent un excellent choix pour une analyse.<ul><li>[Évaluation de la compatibilité réseau de Microsoft teams](3-envision-evaluate-my-environment.md#test-the-network)</li></ul><br>**Outil Microsoft Network Assessment :** Cet outil vous permet de tester les performances du réseau de manière simple et de déterminer l’efficacité du réseau pour un appel en équipe ou Skype entreprise online. L’outil vous permet d’évaluer les performances d’un sous-réseau et de vérifier la préparation du réseau par rapport [aux exigences](https://aka.ms/performancerequirements)de performances de Microsoft.<ul><li>[Télécharger l’outil d’évaluation du réseau](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul> |
| **Clients (Skype entreprise Online uniquement)** | Certains clients plus anciens présentent des problèmes liés à la fiabilité des médias connus. Passez en revue les rapports d’analyse des appels de plusieurs utilisateurs concernés, ou créez un rapport de table de version de client personnalisée dans bord filtré sur des bâtiments ou sous-réseaux spécifiques avec la mesure% d’échec de l’appel. Les informations ci-dessous vous aideront à comprendre s’il existe une relation entre les chutes d’appel dans ce bâtiment spécifique et une version spécifique du client.     |
| **Appareils**                                  | Nous recommandons que les utilisateurs qui rencontrent des problèmes de mise en place (ou d’appels médiocres en général) puissent utiliser des appareils intégrés [pour être](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) mis en service en tant que source potentielle de qualité médiocre et de fiabilité. |
| **Comportement des utilisateurs**                            | Si vous déterminez que le problème n’est pas lié au réseau, aux appareils ou aux clients, envisagez de développer une stratégie d’adoption des utilisateurs pour éduquer les utilisateurs et les quitter. Les équipes plus intelligentes et les utilisateurs de Skype entreprise auront une meilleure expérience utilisateur pour tous les participants à la réunion. Un utilisateur qui met son ordinateur portable en veille (en fermant le capot) sans quitter la réunion sera considéré comme une chute d’appel inattendue.   |

## <a name="quality-investigations"></a>Examens de qualité

L’étape suivante permettant d’évaluer l’état de la qualité audio au sein de l’Organisation consiste à identifier le taux de transmission médiocre (V.Q.P.R.D.), le TCP et l’utilisation du proxy. Il est important de garder à l’esprit que les données de bord ne vous fournissent pas de raison initiale précise, mais qu’il vous suffit de vous présenter à l’origine de problèmes potentiels pour commencer une conversation de collaboration avec les équipes appropriées en matière d’activités de correction. 

> [!NOTE]
> Tous les rapports inclus dans les modèles ne sont pas abordés dans ce guide ; Toutefois, les méthodes d’enquête expliquées ci-dessous seront toujours applicables pour ces rapports. Pour plus d’informations, reportez-vous à la description du rapport individuel. 

### <a name="quality"></a>Supérieure

Les pourcentages de V.Q.P.R.D. permettent d’indiquer si l’organisation utilise des cibles métriques définies pour une zone de focalisation donnée. Il est important de noter que, même si les pourcentages de haut niveau font partie de la cible définie, il est possible que les sous-réseaux ou les bâtiments individuels ne respectent pas les cibles définies et nécessitent par conséquent une étude plus approfondie. Par exemple, si le pourcentage global de V.Q.P.R.D. correspond à 2% en avril, qui correspond à la cible de l’exemple, les bâtiments et sous-réseaux individuels peuvent malgré tout présenter des expériences médiocres, selon la distribution globale de ces 2%. 

Pour évaluer le pourcentage de flux médiocres, utilisez les rapports qualité. Différents rapports sur la qualité sont fournis pour réviser les indicateurs de mesure pour les appels généraux, de conférence, d’appels RTC, de VPN et de salles de réunion. Le rapport mensuel, hebdomadaire et quotidien est fourni pour vous aider dans le cadre de ce processus. Les rapports hebdomadaires et quotidiens sont limités au modèle réseaux gérés pour une productivité accrue et une réduction du bruit. 

#### <a name="quality-trend-analysis"></a>Analyse des tendances de qualité

Les rapports de tendance affichent des informations de qualité dans le temps et permettent d’identifier et de comprendre les tendances de qualité dans chaque domaine d’intérêt. Comme indiqué plus haut, il existe des arbres de rapport inclus dans les modèles pour examiner la qualité ; Conférences, appels RTC à deux parties, VPN et salles de réunion. Dans le cadre de l’analyse de la qualité, le processus d’investigation est le même. Néanmoins, nous vous conseillons d’abord commencer par les conférences, car toute amélioration apportée à la qualité de la Conférence affectera également tous les autres aspects. 

> [!Note]
> L’examen des salles de réunion et de la fonction d’appel RTC et des salles de réunion est semblable à l’examen des conférences. Le focalisation est d’isloate des bâtiments ou des sous-réseaux présentant une qualité médiocre et d’identifier les raisons de la qualité médiocre.

> [!Important]
> Les rapports basés sur VPN sont filtrés à l’aide de la deuxième dimension VPN. Cette dimension nécessite que la carte réseau VPN soit correctement inscrite en tant qu’adaptateur d’accès distant. Les fournisseurs de réseau privé virtuel n’utilisent pas de manière fiable cet indicateur, et votre kilométrage varie en fonction du fournisseur de VPN déployé au niveau de votre organisation. Suivez les instructions décrites [plus haut dans ce guide](#vpn) pour modifier les rapports VPN si nécessaire à l’aide du nom de bâtiment ou de réseau.

![Graphique illustrant le pourcentage de flux de qualité médiocres](media/qerguide-image-audioqualityconferencing.png)

_Figure 23-qualité audio-conférences_

##### <a name="investigation"></a>Procédure

À l’aide de ces rapports, vous pouvez répondre aux questions suivantes :

-   Quel est le nombre total de V.Q.P.R.D. pour le mois en cours ?
-   Le V.Q.P.R.D. est-il inférieur à la métrique cible définie ?
-   Le V.L.Q.P.R.D. est-il pire ou mieux que le mois précédent ?
-   La tendance du V.Q.P.R.D. augmente-t-elle, elle est constante ou décroissante ?

Quelles que soient les réponses aux questions ci-dessus, prenez le temps de rechercher en utilisant les sous-rapports pour rechercher tout bâtiment ou sous-réseau susceptible d’avoir besoin d’une étude. Même si le V.Q.P.R.D. est peut-être inférieur à la métrique cible, le V.Q.P.R.D. d’un ou de plusieurs bâtiments ou réseaux est supérieur à la métrique et nécessite une correction.

#### <a name="quality-investigations"></a>Examens de qualité

Les rapports de synthèse qualité vous fournissent des informations plus détaillées sur les flux considérés comme médiocres et aident à isoler les zones de problèmes sur le réseau géré.

Bien que les dimensions utilisées soient légèrement différentes entre le rapport, chaque rapport inclut des mesures pour les flux totaux, le nombre total de flux médiocres, le V.Q.P.R.D. et la qualité médiocre. Des rapports ont été créés pour chaque domaine d’intérêt : les conférences, les appels PSTN, les appels RTC et les salles de réunion. Le modèle réseau géré inclut des rapports supplémentaires qui vous permettent de tirer parti des informations d’emplacement téléchargées par le biais du fichier de construction.

> [!NOTE]
> Veillez à ajuster le filtre mois en cours au mois en cours. Sélectionnez **modifier**, puis ajustez l' **année du mois** pour enregistrer le nouveau mois par défaut.

> [!Note]
> Les sous-réseaux courants sont difficiles à trier en raison de leur utilisation massive. Un rapport séparé qui affiche l’adresse IP publique du client (deuxième adresse IP locale réflexive) a été ajouté au modèle tous les réseaux pour faciliter la conversion des bureaux qui utilisent des réseaux communs.


![Capture d’écran montrant le résumé du flux audio médiocre](media/qerguide-image-poorqualitysummary.png)

_Figure 24-Résumé du flux audio médiocre en créant et en sous-réseau-conférences_

##### <a name="remediation"></a>Remediation

Concentrez vos efforts de correction sur des bâtiments ou des sous-réseaux disposant du plus grand volume de flux, car cela permet d’optimiser l’impact et de faciliter l’utilisation rapide de l’utilisateur. Utilisez les mesures de gigue, de perte de paquets et de temps de boucle pour comprendre ce qui contribue à la qualité médiocre (il est possible qu’il y ait plusieurs problèmes) :

-   **Gigue**: les paquets multimédias arrivent à des vitesses différentes, ce qui a pour effet d’entendre un haut-parleur du son.
-   **Perte de paquets**: les paquets multimédias sont déposés, ce qui crée l’effet de mots ou syllabes manquants.
-   **RTT**: les paquets multimédias prennent du temps pour accéder à leur destination, ce qui crée un effet de diaphonie.

Pour vous aider à examiner vos problèmes de qualité, vous pouvez tirer parti de l' [analyse des appels](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309). Avec l’analyse des appels, vous pouvez consulter le rapport détaillé d’une conférence ou d’un utilisateur. Ce rapport contient des données d’identification personnelle et peut s’avérer utile lorsque vous recherchez la cause d’une panne. Une fois que vous connaissez le bâtiment affecté, il est facile d’effectuer le suivi des utilisateurs dans ce bâtiment. 

N’oubliez pas de faire savoir au support technique que ces réseaux rencontrent des problèmes de qualité pour pouvoir trier et répondre rapidement aux appels entrants.

_Tableau 10 : contributeurs courants aux V.Q.P.R.D._

| Remediation                              | Aide                         |
|------------------------------------------|----------------------------------|
| **Réseaux**                                 | **Congestion**: un réseau surutilisé ou sous-approvisionné peut poser des problèmes de qualité multimédia. Collaborer avec l’équipe du réseau pour déterminer si les connexions réseau de l’utilisateur au point de sortie Internet disposent d’une bande passante suffisante pour prendre en charge le contenu multimédia. <br><br>**Effectuer une évaluation de la disponibilité du réseau**: une évaluation du réseau fournit des détails sur l’utilisation de la bande passante attendue, sur la gestion de la bande passante et des changements réseau, ainsi que sur les pratiques recommandées pour les équipes et Skype entreprise. En utilisant le tableau précédent comme source, vous disposez d’une liste de bâtiments ou de sous-réseaux qui constituent un excellent choix pour une analyse.<ul><li>[Évaluation de la compatibilité réseau de Microsoft teams](3-envision-evaluate-my-environment.md#test-the-network)</li></ul><br>**Outil Microsoft Network Assessment :** Cet outil vous permet de tester les performances du réseau de manière simple et de déterminer l’efficacité du réseau pour un appel en équipe ou Skype entreprise online. L’outil vous permet d’évaluer les performances d’un sous-réseau et de vérifier la préparation du réseau par rapport [aux exigences](https://aka.ms/performancerequirements)de performances de Microsoft.<ul><li>[Télécharger l’outil d’évaluation du réseau](https://www.microsoft.com/download/details.aspx?id=53885)</li></ul><br> |
| **Qualité de service (QoS)**  | La qualité de service (QoS) est un outil reconnu qui vous permet de hiérarchiser les paquets sur un réseau encombré pour s’assurer qu’ils arrivent à leur destination intacte et à temps. Envisagez d’implémenter QoS au sein de votre organisation afin d’optimiser la qualité de l’utilisation de la bande passante. La qualité de service (QoS) vous aidera à résoudre les problèmes généralement liés aux niveaux de perte de paquets élevés et à un niveau inférieur pour les temps de scintillement et de boucle.<ul><li>[Conseils QoS de Microsoft teams](qos-in-teams.md)</li></ul> |
| **Wi-Fi**               | Le Wi-Fi peut avoir un impact important sur la qualité des appels. Les déploiements Wi-Fi ne prennent généralement pas en considération la configuration réseau requise pour les services VoIP et sont souvent une source de mauvaise qualité. Pour plus d’informations sur l’optimisation de votre infrastructure Wi-Fi, voir [cet article sur la planification Wi-Fi](/skypeforbusiness/certification/plan-wifi).<br><br>**Pilote sans fil**: Assurez-vous que les pilotes sans fil sont à jour. Cela permet de réduire les problèmes d’utilisation médiocres liés à un pilote obsolète. Beaucoup d’organisations n’incluent pas de pilotes sans fil dans leurs cycles de correctifs, et ces pilotes peuvent être dépourvus d’une année. De nombreux problèmes sans fil sont résolus en s’assurant que les pilotes sans fil sont à jour.<br><br>**WMM**: les extensions multimédias sans fil (WMM), également appelées multimédia Wi-Fi, fournissent des fonctionnalités QoS de base aux réseaux sans fil. Les réseaux sans fil modernes doivent prendre en charge un grand nombre d’appareils. Ces appareils font concurrence de la bande passante et peuvent entraîner des problèmes de qualité pour les services VoIP, où la vitesse et la latence sont vitales. Pour obtenir des détails spécifiques sur votre fabricant sans fil et envisager d’implémenter WMM sur votre réseau sans fil, vous pouvez définir les priorités de Skype entreprise et de teams.<br><br>**Densité de points d’accès**: les points d’accès peuvent être trop éloignés ou ne pas se trouver dans un emplacement idéal. Pour réduire les interférences potentielles, placez des points d’accès supplémentaires dans des salles de conférence et dans des emplacements qui ne sont pas obstrués par des murs ou d’autres objets pour lesquels le signal Wi-Fi est faible.<br><br>**2,4 GHz et 5 GHz**: 5 GHz fournit moins d’interférences en arrière-plan et des débits plus élevés, et devraient être classés par priorité lors du déploiement de VoIP via Wi-Fi. Toutefois, les 5 GHz ne sont pas aussi puissants qu' 2,4 GHz et ne pénètrent pas facilement dans les murs. Passez en revue votre mode de construction pour déterminer la fréquence de votre choix pour la meilleure connexion. |
|**Périphérique réseau** | Les grandes organisations peuvent avoir des centaines d’appareils répartis sur le réseau. Travaillez avec votre équipe réseau pour vous assurer que les appareils réseau de l’utilisateur sur Internet sont gérés et à jour. |
| **VPN**  | Les appareils VPN ne sont généralement pas conçus pour gérer les charges de travail multimédia en temps réel. Certaines configurations VPN empêchent l’utilisation d’UDP (qui est le protocole préféré pour les médias) et ne dépendent que de TCP. Envisagez d’implémenter une solution VPN Split-tunnel pour réduire la qualité du réseau VPN en tant que source de médiocre qualité. |
| **Clients** <br>(Skype entreprise Online uniquement) | Assurez-vous que tous les clients sont mis à jour régulièrement. |
| **Appareils** | L’utilisation de [périphériques optimisés](https://partnersolutions.skypeforbusiness.com/solutionscatalog) peut améliorer considérablement l’expérience utilisateur. Avec tous les éléments égaux, les appareils optimisés sont conçus pour optimiser l’expérience utilisateur avec les équipes et Skype entreprise, et obtenir une qualité supérieure. |
| **Pilote** | Les correctifs de connexion réseau (Ethernet et Wi-Fi), d’audio, de vidéo et de pilotes USB doivent faire partie intégrante de votre stratégie de gestion de correctif globale. De nombreux problèmes de qualité sont résolus en mettant à jour les pilotes. |
| **Salles de réunion en Wi-Fi** | Nous vous recommandons vivement de se connecter au réseau en utilisant au moins une connexion Ethernet 1 Gbit/s. Les appareils de salle de réunion incluent généralement plusieurs flux audio et vidéo, ainsi que le contenu de la réunion, comme le partage d’écran, et présentent des exigences réseau plus élevées que d’autres équipes ou points de terminaison Skype entreprise. Les salles de réunion sont, par définition, des appareils fixes pour lesquels le Wi-Fi ne donne droit qu’au moment de l’installation.<br><br>Les salles de réunion doivent être traitées sans souci et attention pour garantir que l’utilisation de ces appareils est soumise à des attentes. Les problèmes de qualité liés aux salles de réunion seront généralement réaffectés rapidement, car ils sont souvent utilisés par des employés de niveau supérieur.<br><br>Le niveau de performance du Wi-Fi est souvent inférieur à celui d’une connexion câblée. Grâce à l’augmentation des politiques « mettre en place vos propres périphériques » et à la prolifération des ordinateurs portables, les points d’accès Wi-Fi sont souvent plus sollicités. Le contenu multimédia en temps réel peut ne pas être classé sur les réseaux Wi-Fi, ce qui peut entraîner des problèmes de qualité en temps réel. Cette utilisation intensive peut coïncider avec une réunion dans laquelle il peut y avoir une douzaine de personnes à la fois, chacune avec leur propre ordinateur portable et votre smartphone, connectées au même point d’accès Wi-Fi que l’appareil de salle de réunion.<br><br>Le Wi-Fi ne doit être considéré comme une solution temporaire que pour une installation mobile ou lorsque le Wi-Fi a été correctement configuré pour prendre en charge des contenus multimédias professionnels en temps réel. |


### <a name="tcp"></a>TCP

Le protocole TCP est considéré comme un transport de restauration automatique et non par le transport principal que vous voulez pour le média en temps réel. La raison pour laquelle il s’agit d’un transport de restauration automatique est due à la nature dynamique du protocole TCP. Par exemple, si un appel est effectué sur une connexion réseau latente et que les paquets multimédias sont retardés, il y a plus de quelques secondes (qui n’ont plus besoin de la bande passante pour accéder au destinataire), ce qui peut compliquer le problème. Ainsi, le son de la fonction de correction audio et le son s’étirent, ce qui engendre des artefacts audibles, souvent sous la forme d’un scintillement.

Les rapports de cette section ne font pas de distinction entre les flux Good et médiocre. Dans la plupart des cas, il est préférable d’utiliser le protocole TCP pour le partage d’écran vidéo et audio (VBSS). Des débits de flux médiocres permettent de comparer la qualité UDP et la qualité TCP, afin que vous puissiez vous concentrer sur la meilleure qualité de vos efforts. L’utilisation de TCP est principalement causée par des règles de pare-feu incomplètes. Pour plus d’informations sur les règles de pare-feu pour les équipes et Skype entreprise Online, voir [URL et plages d’adresses IP Office 365](https://aka.ms/o365ips).

> [!Important]
> Il est vivement recommandé de disposer d’un [fichier de construction valide](#building-mapping) dans les flux extérieurs lorsque vous examinez l’utilisation de TCP.

> [!Note]
> Les éléments audio, vidéo et VBSS sont tous préférés du protocole UDP comme transport principal. La charge de travail de partage d’application RDP héritée utilise uniquement TCP.

#### <a name="tcp-usage"></a>Utilisation de TCP

Les rapports TCP indiquent l’utilisation globale du protocole TCP au cours des sept derniers mois. Dans cette section, tous les rapports supplémentaires visent à affiner les bâtiments et sous-réseaux spécifiques pour lesquels TCP est le plus souvent utilisé. Des rapports distincts sont disponibles pour les conférences et les flux à deux parties.

![Graphique illustrant le pourcentage de flux audio qui utilisent](media/qerguide-image-audiostreamswithtcp.png)
TCP_figure 25 – flux audio avec utilisation de TCP_


##### <a name="investigation"></a>Procédure

En utilisant ce rapport, vous pouvez répondre aux questions suivantes :

-   Quel est le volume total des flux TCP pour le mois en cours ?
-   Est-il pire ou mieux que le mois précédent ?
-   La tendance de l’utilisation de TCP augmente-t-elle, elle est constante ou dégressive ?
-   Le V.Q.P.R.D. est-il identique au V.Q.P.R.D. global ?

Si vous remarquez que la tendance de l’utilisation de TCP augmente ou dépasse l’utilisation mensuelle normale, prenez le temps de rechercher en utilisant les sous-rapports pour rechercher des bâtiments ou des réseaux susceptibles de nécessiter une correction. Idéalement, il est préférable de disposer d’autant de sessions audio TCP que possible sur le réseau géré.

#### <a name="tcp-vs-udp"></a>TCP et UDP

Ce rapport identifie le volume des rapports d’utilisation TCP et UDP au plus tard pour le partage d’écran vidéo et audio (VBSS). 

![État indiquant le volume de flux utilisant TCP et UDP](media/qerguide-image-tcpvsudp.png)

_Figure 26 : TCP et UDP-Conferencing_

##### <a name="analysis"></a>Étude

Même si vous souhaitez que l’utilisation de TCP soit aussi faible que possible, il est possible que vous rencontriez un peu d’utilisation de TCP dans le cadre d’un déploiement sain. TCP en soi ne contribue pas à un mauvais appel, de sorte que des tarifs de flux sont fournis pour vous aider à déterminer si l’utilisation de TCP est un contributeur de médiocre qualité. 

#### <a name="tcp-investigations"></a>Examens TCP

Dans les modèles bord fournis, naviguez jusqu’aux flux TCP en construisant et en utilisant un rapport de sous-réseau via le modèle réseaux gérés ou tous les réseaux. Dans le cadre de l’examen de l’utilisation de TCP, le processus est le même, c’est pourquoi nous allons nous concentrer sur les conférences.

> [!IMPORTANT]
> Le chargement d’un [fichier de construction](#building-mapping) valide est recommandé pour vous permettre de le distinguer rapidement dans les flux extérieurs lorsque vous examinez l’utilisation de TCP. 

> [!NOTE]
> Veillez à ajuster le filtre mois en cours au mois en cours. Sélectionnez **modifier**, puis ajustez l' **année du mois** pour enregistrer le nouveau mois par défaut.                                  |

![Capture d’écran de l’utilisation de TCP par bâtiment et sous-réseau](media/qerguide-image-tcpstreams.png)

_Figure 27 : flux TCP par bâtiment et sous-réseau-conférences_

##### <a name="remediation"></a>Remediation

Ce rapport identifie les bâtiments et sous-réseaux spécifiques qui contribuent au volume de l’utilisation du protocole TCP. Un rapport supplémentaire est également fourni pour identifier l’adresse IP Microsoft Relay utilisée dans l’appel afin d’isoler les règles de pare-feu manquantes. Concentrez vos efforts de correction sur les bâtiments qui présentent le volume le plus élevé de flux TCP pour optimiser l’impact.

La cause la plus fréquente de l’utilisation du protocole TCP est l’absence de règles d’exception dans les pare-feu ou les proxys. Nous parlerons des proxys dans la section suivante, donc pour mettre au point vos efforts sur les pare-feu. En utilisant le bâtiment ou le sous-réseau fourni, vous pouvez déterminer le pare-feu qui doit être mis à jour.


_Tableau 11-Instructions de correction pour les flux TCP par bâtiment et sous-réseau_

| Remediation        | Aide     |
|--------------------|--------------------------------------|
| Configuration du pare-feu | Vérifiez que les [adresses IP et adresses IP d’Office 365](https://aka.ms/o365ips) sont exclues de votre pare-feu. Pour les problèmes TCP liés aux médias, concentrez-vous sur les points suivants :<ul><li>Vérifiez que les sous-réseaux multimédias du client 13.107.64.0/18 et 52.112.0.0/14 se trouvent dans les règles de pare-feu.</li><li>Ports UDP 3478 – 3481 sont les ports multimédias requis et doivent être ouverts, sinon le client bascule à nouveau vers le port 443.</li></ul> |
| Vérifier             | Utilisez l' [outil Microsoft Network Assessment](https://www.microsoft.com/download/details.aspx?id=53885) pour vérifier les problèmes de connectivité avec des adresses IP et des ports Office 365 spécifiques du bâtiment ou du sous-réseau concernés.    |

### <a name="http-proxy"></a>Proxy HTTP

Les proxys HTTP ne sont pas le chemin préféré pour établir des sessions multimédias pour différentes raisons. Beaucoup contiennent des fonctionnalités d’inspection de paquets complètes qui peuvent empêcher la fin des connexions au service et provoquer des interruptions. De plus, la plupart des serveurs proxy forcent le protocole TCP plutôt que d’autoriser le protocole UDP, ce qui est recommandé pour une qualité audio optimale.

Nous vous recommandons de configurer le client pour vous connecter directement aux équipes et aux services Skype entreprise. Ceci est particulièrement important pour le trafic multimédia.


> [!IMPORTANT]
> Le chargement d’un [fichier de construction](#building-mapping) valide simplifie la distinction correcte entre les flux audio extérieurs lors de l’analyse de l’utilisation du proxy. 


#### <a name="http-proxy-usage"></a>Utilisation du proxy HTTP

Le rapport de flux proxy HTTP dans cette section du modèle ressemble beaucoup au rapport TCP. Il ne s’agit pas de savoir si les appels sont médiocres ou efficaces, mais si l’appel est connecté via HTTP.

![Capture d’écran du rapport de flux audio qui utilise HTTP](media/qerguide-image-audiostreamswithhttp.png)

_Figure 28 : flux audio avec utilisation du proxy HTTP_

##### <a name="analysis"></a>Étude

Vous voulez voir le plus petit flux multimédia HTTP possible. Si des flux traversent votre proxy, consultez votre équipe réseau pour vous assurer que les exclusions appropriées sont en place afin que les clients effectuent un routage direct vers teams ou des sous-réseaux multimédias Skype entreprise online.

Si votre organisation ne comporte qu’un seul proxy Internet, vérifiez les [URL d’Office 365 appropriées et les exclusions de plages d’adresses IP](https://aka.ms/o365ips). S’il existe plusieurs proxy Internet au sein de votre organisation, utilisez le sous-rapport HTTP pour isoler le bâtiment ou le sous-réseau concerné.

S’il s’agit d’organisations qui ne peuvent pas ignorer le proxy, assurez-vous que le client Skype entreprise est configuré de manière à se connecter correctement lorsqu’il se trouve derrière un proxy, comme indiqué dans l’article [Skype entreprise doit utiliser un serveur proxy pour se connecter au lieu d’essayer une connexion directe](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin). 


#### <a name="http-proxy-investigations"></a>Examens du proxy HTTP

Ce rapport identifie les bâtiments et sous-réseaux spécifiques qui participent à l’utilisation de HTTP.

> [!IMPORTANT]
> Le chargement d’un [fichier de construction](#building-mapping) valide simplifie la distinction correcte entre les flux audio extérieurs lors de l’analyse de l’utilisation du proxy.

> [!NOTE]
> Veillez à ajuster le filtre mois en cours au mois en cours. Sélectionnez **modifier**, puis ajustez l' **année du mois** pour enregistrer le nouveau mois par défaut.

![Capture d’écran du rapport sur l’utilisation du proxy HTTP par le biais de la construction et du sous-réseau](media/qerguide-image-httpproxyusage.png)

_Figure 29 – utilisation du proxy HTTP par le biais de la construction et du sous-réseau_

##### <a name="remediation"></a>Remediation

Nous vous [recommandons](proxy-servers-for-skype-for-business-online.md) de toujours ignorer les proxys pour Skype entreprise et équipes, en particulier le trafic multimédia. Les proxys ne permettent pas de sécuriser Skype entreprise, car son trafic est déjà crypté. Des problèmes de performances peuvent s'introduire dans l'environnement par le biais de la latence et la perte de paquets. Des problèmes tels que ceux-ci entraînent une utilisation négative du son, de la vidéo et du partage d’écran, où les flux en temps réel sont essentiels.

La cause la plus fréquente de l’utilisation de HTTP est le manque de règles d’exception dans les proxys. En utilisant le bâtiment ou le sous-réseau fourni, vous pouvez déterminer rapidement quel proxy doit être configuré pour la dérivation multimédia.

Vérifiez que les noms de [domaine complets Office 365](https://aka.ms/o365ips) requis sont autorisés dans votre proxy.

## <a name="endpoint-investigations"></a>Investigations de points de terminaison

Cette section est axée sur les tâches de création de rapports sur les versions du client et l’utilisation des appareils certifiés. Les rapports peuvent être utilisés en mode plan pour les versions de client, le type de client, les périphériques de capture et les pilotes (microphone), les appareils de capture vidéo, les versions de pilotes et de fournisseurs Wi-Fi.

> [!NOTE]
> Tous les rapports inclus dans les modèles ne sont pas abordés dans ce guide ; Toutefois, les méthodes de vérification décrites ci-dessous s’appliquent. Pour plus d’informations, reportez-vous à la description du rapport individuel.

### <a name="client-versions"></a>Versions de client

Les rapports de cet espace se concentrent sur l’identification des versions du client Skype entreprise en cours d’utilisation et leur volume relatif dans l’environnement.

> [!IMPORTANT]
> Pour l’instant, les clients teams sont répartis et mis à jour automatiquement via le réseau de distribution de contenu Azure et sont tenus à jour par le service. Les activités d’investigation et de préparation du client ne s’appliquent pas aux équipes.

> [!Important]
> Les rapports de points de terminaison fédérés incluent les données de télémétrie clientes. Pour exclure des points de terminaison fédérés, vous devez ajouter un [filtre de requête](#query-filters) pour le second ID de client défini sur l' [ID de client](#tenant-id)de votre organisation. Vous pouvez également utiliser un filtre d' [URL](#url-filter) pour exclure la télémétrie de participants fédérés.

> [!NOTE]
> Veillez à ajuster le filtre mois en cours au mois en cours. Sélectionnez **modifier**, puis ajustez l' **année du mois** pour enregistrer le nouveau mois par défaut.

![Capture d’écran du rapport client et périphériques](media/qerguide-image-clientversionreport.png)

_Figure 30-rapport sur la version du client_

#### <a name="remediation"></a>Remediation

Dans le cadre d’une expérience utilisateur de grande qualité, il est nécessaire de s’assurer que les clients gérés exécutent des versions à jour de Skype entreprise, en plus de garantir la mise à jour des pilotes audio, vidéo, réseau et USB. Cela offre plusieurs avantages : 

-   Il est plus facile de gérer quelques versions par rapport à d’autres versions.
-   Il offre un niveau de cohérence.
-   C’est la meilleure façon de résoudre les problèmes de qualité des appels et de convivialité.
-   Microsoft effectue continuellement des améliorations et des optimisations générales dans le produit. Le fait de vérifier que les utilisateurs reçoivent ces mises à jour réduit leur risque de rencontrer un problème qui a déjà été résolu.

Le déploiement d’une version de client de moins de six mois permettra d’améliorer l’utilisation globale et de faciliter la gestion en réduisant le nombre de versions qui doivent être prises en charge.

Si vous utilisez uniquement Office « démarrer en un clic », vous êtes automatiquement dans la fenêtre de six mois. Aucune action supplémentaire n’est requise.

Si vous avez une combinaison des packages démarrer en un clic et du programme d’installation (MSI), vous pouvez utiliser le rapport pour vérifier que les clients MSI sont mis à jour régulièrement. Si vous remarquez que des clients sont en retard, travaillez avec l’équipe responsable de la gestion des mises à jour d’Office et assurez-vous qu’elles approuvent et déploient régulièrement des correctifs client.

Il est également important de prendre en considération et de s’assurer que les pilotes réseau, vidéo, USB et audio sont également mis à jour. Il peut être facile de négliger ces pilotes et de ne pas les inclure dans la stratégie de gestion des correctifs.

Pour plus d’informations sur Skype entreprise, consultez les liens ci-dessous :

-   [Informations de publication des mises à jour d’Office ProPlus](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)
-   [Historique des mises à jour pour Office 365 ProPlus](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date)
-   [Téléchargements et mises à jour de Skype Entreprise](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Appareils

Pour pouvoir utiliser le rapport sur les périphériques de microphone, nous devons comprendre le concept du score moyen d’avis (MOS). La fonction valeur. non. a représente la mesure d’or standard pour évaluer la qualité audio perçue. Elle est représentée sous la forme d’une note entière comprise entre 0 et 5.

La base de toutes les mesures de la qualité de la voix est la façon dont une personne perçoit la qualité vocale. Étant donné qu’il est affecté par la perception humaine, il est fondamentalement subjectif. Il existe plusieurs méthodes différentes pour le test subjectif. La plupart des mesures de qualité de voix sont basées sur une échelle de classification absolue (ACR).

Au cours d’un test subjectif de ACR, le nombre de personnes qui évaluent de manière statistique la qualité de leurs connaissances sur une échelle de 1 à 5 (excellent). La moyenne des scores est le MOS. Le MOS obtenu dépend de la gamme d’expériences exposées au groupe et au type d’expérience notée.

Étant donné qu’il n’est pas pratique de réaliser des tests subjectifs de qualité vocale pour un système de communication en direct, Microsoft teams et Skype entreprise génèrent des valeurs MOS en utilisant des algorithmes avancés pour prévoir objectivement les résultats d’un test subjectif.

L’ensemble disponible de métriques MOS et associées fournit une vue de la qualité de l’interface fournie aux utilisateurs par un périphérique audio. 

En fournissant aux utilisateurs des appareils certifiés pour teams et Skype entreprise, vous réduisez le risque de rencontrer des expériences négatives en raison de l’appareil proprement dit (par exemple, avec des haut-parleurs et des micros intégrés). Pour plus d’informations, reportez-vous aux articles suivants sur le [programme de certification](/SkypeForBusiness/certification/overview) et le [catalogue solutions des partenaires](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs).

Les rapports de périphériques permettent d’évaluer l’utilisation de l’appareil par le volume et le score MOS (audio uniquement), et peuvent être identifiés dans les modèles associés sous clients & appareils. 

> [!IMPORTANT]
> Les rapports de points de terminaison fédérés incluent les données de télémétrie clientes. Pour exclure des points de terminaison fédérés, vous devez ajouter un filtre de requête pour le **second ID de client** défini sur l' [ID de client](#tenant-id)de votre organisation. Vous pouvez également utiliser un filtre d' [URL](#url-filter) pour exclure la télémétrie de participants fédérés.

> [!NOTE] 
> Veillez à ajuster le filtre mois en cours au mois en cours. Sélectionnez **modifier**, puis ajustez l' **année du mois** pour enregistrer le nouveau mois par défaut.

> [!Note]
> Vous remarquerez peut-être lors de l’affichage du rapport que vous voyez le même appareil signalé plusieurs fois. Ce problème est dû au fait que l’appareil est signalé comme étant signalé à bord. Les différences dans les paramètres régionaux du matériel et du système d’exploitation entraînent des différences dans la façon dont les données d’appareil sont communiquées.

![Capture d’écran du rapport périphériques (microphone)](media/qerguide-image-devicesmicrophone.png)

_Figure 31-rapport sur les appareils (microphone)_

##### <a name="remediation"></a>Remediation

En règle générale, vous devez découvrir et sortir des appareils non certifiés et les remplacer par des appareils certifiés. Voici quelques éléments à prendre en compte lors de l’examen des rapports d’appareil :

-   Les appareils utilisent-ils une certification pour teams et Skype entreprise ? 
-   Vous pouvez identifier les utilisateurs d’un appareil spécifique via l' [analyse des appels](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309). Assurez-vous qu’ils disposent des pilotes les plus récents et qu’ils ne sont pas connectés par le biais d’un concentrateur ou d’une station d’accueil USB. 
-   Combien de versions différentes de différents pilotes sont utilisées ? Le correctif est-il régulier ? Pour garantir que les pilotes audio et vidéo, ainsi que les pilotes Wi-Fi, nous vous aiderons à éliminer ces problèmes en tant que source de problèmes de qualité et à optimiser l’utilisation de l’utilisateur.

##### <a name="audio"></a>Audio

La tâche suivante consiste à déterminer l’utilisation globale des [périphériques audio certifiés](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Nous vous recommandons d’utiliser un périphérique audio certifié pour un minimum de 80% de tous les flux audio. Pour effectuer cette opération, exportez le rapport sur les périphériques microphone dans Excel pour calculer l’utilisation des appareils certifiés ou approuvés. En règle générale, les organisations conservent la liste de tous les appareils approuvés, de sorte que le filtrage et le tri des données doivent être simples.

##### <a name="video"></a>Vidéo

Il est important de mettre à jour les pilotes vidéo. Le fait de veiller à ce que les cartes vidéo soient régulièrement corrigées permet d’exclure les pilotes vidéo en tant que source de médiocre qualité des flux vidéo. L’utilisation de [périphériques vidéo certifiés](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) permet d’assurer une utilisation lisse et de qualité de l’utilisateur. Les appareils vidéo qui prennent en charge le codage natif H. 264 sont préférés pour réduire l’utilisation de l’UC lors des conférences vidéo.

##### <a name="wi-fi"></a>Wi-Fi

Les pilotes Wi-Fi doivent également être corrigés en une cadence normale et être inclus dans la stratégie de gestion des correctifs. De nombreux problèmes de qualité peuvent être corrigés en gérant les pilotes Wi-Fi à jour. Pour plus d’informations sur l’optimisation de votre infrastructure Wi-Fi, voir [cet article sur la planification Wi-Fi](/skypeforbusiness/certification/networking-wifi).

## <a name="appendix"></a>A 

### <a name="office-365-network-connectivity-principles"></a>Principes de connectivité réseau d’Office 365

Avant de commencer la planification de votre réseau pour la connectivité réseau à Office 365, il est important de comprendre les principes de connectivité pour gérer le trafic Office 365 en toute sécurité et obtenir les meilleures performances possibles. Les articles suivants vous aideront à comprendre les recommandations les plus récentes pour optimiser la connectivité réseau d’Office 365 :

[Principes de connectivité réseau d’Office 365](https://aka.ms/pnc)

### <a name="planning-for-wi-fi"></a>Planification du Wi-Fi

L’approche de la qualité et de la flexibilité de Microsoft dans les réseaux sans fil est en trois parties : de bout en bout, meilleures pratiques de déploiement et maintenance et opérations proactives. Cette présentation de la solution vous guide tout au long de ce processus pour vous permettre d’utiliser Skype entreprise sans fil pour les entreprises :

[Garantir une découverte sans fil de Skype entreprise pour les entreprises](https://www.microsoft.com/download/details.aspx?id=47257)

### <a name="lync-networking-guide"></a>Guide de mise en réseau Lync

Pour plus d’informations sur les concepts de mise en réseau des équipes et de Skype entreprise et sur les concepts de base, le [Guide de mise en réseau de Lync Server 2013](https://blogs.technet.microsoft.com/nexthop/2013/06/03/lync-server-2013-networking-guide-network-planning-monitoring-and-troubleshooting-with-microsoft-lync-server/) est toujours applicable.

### <a name="network-performance-requirements"></a>Exigences de performances réseau

La qualité de média en temps réel (audio, vidéo et de partage d’application) sur IP est grandement affectée par la qualité de la connectivité réseau de bout en bout. Pour une qualité optimale d’équipe ou de média Skype entreprise, votre réseau doit répondre aux métriques de performance réseau suivantes.

_Tableau 12 : exigences de performances réseau_

| Mesure                            | Client vers Microsoft Edge           | Edge du client à Microsoft Edge    |
|-----------------------------------|------------------------------------|------------------------------------|
| Latence (unidirectionnelle)                 | \<50 ms                            | \<30 ms                            |
| Latence (RTT ou durée de l’aller-retour) | \<100 ms                           | \<60 ms                            |
| Perte de paquets en rafale                 | \<10% pendant tout intervalle de 200-ms   | \<1% pendant tout intervalle de 200-ms    |
| Perte de paquets                       | \<1% durant tout intervalle de 15 secondes    | \<0,1% pendant tout intervalle de 15 secondes  |
| Gigue entre les arrivées de paquets       | \<30 ms pendant tout intervalle de 15 secondes | \<15 ms pendant tout intervalle de 15 secondes |
| Réorganisation des paquets                    | \<0,05% de paquets en souffrance       | \<0,01% de paquets en souffrance      |

Pour plus d’informations, consultez [cet article relatif à la qualité multimédia et aux performances réseau](https://aka.ms/performancerequirements) pour teams et Skype entreprise online.

### <a name="other-resources"></a>Autres ressources

#### <a name="building-data-file"></a>Création d’un fichier de données

-   [Activation et utilisation du tableau de bord de qualité des appels pour Microsoft teams et Skype entreprise Online](turning-on-and-using-call-quality-dashboard.md)

#### <a name="cqd-training"></a>Formation bord

-   <https://aka.ms/sof-cqd>

-   [Introduction au](https://www.skypeoperationsframework.com/Academy?SOFTrainings=Configuring%20Call%20Quality%20Dashboard%20to%20monitor%20your%20Skype%20for%20Business%20Online%20Environment) guide et à l’atelier de bord

-   [Dimensions et mesures disponibles dans le tableau de bord de qualité des appels](https://aka.ms/cqd-dm)

### <a name="call-analytics-training"></a>Formation sur l’analyse des appels

-   [Présentation de l’analyse des appels](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Introducing-Call-Analytics/ba-p/57309)

-   [Configurer l’analyse des appels](set-up-call-analytics.md)

-   [En quoi l'analyse des appels et le tableau de bord de qualité des appels sont-ils différents ?](difference-between-call-analytics-and-call-quality-dashboard.md)

-   [Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

### <a name="call-analytics-support"></a>Prise en charge de l’analyse des appels

-   Communauté : [programme de version préliminaire de Skype entreprise](https://techcommunity.microsoft.com/t5/Skype-for-Business-Preview/bd-p/SkypeforBusinessPreviewProgram)

### <a name="devices"></a>Appareils

-   [Catalogue de solutions Skype entreprise-périphériques personnels & PC](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

### <a name="tenant-reporting"></a>Rapport de locataire

-   [Pack de contenu adoption d’Office 365](https://www.microsoft.com/microsoft-365/blog/2017/05/22/announcing-the-public-preview-of-the-office-365-adoption-content-pack-in-powerbi/)

-   [Analyse de l'utilisation de Microsoft 365](https://support.office.com/article/Microsoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f)

-   [Création de rapports Skype Entreprise Online](/SkypeForBusiness/skype-for-business-online-reporting/skype-for-business-online-reporting)

-   [Rapports Microsoft teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/New-usage-reports-for-Microsoft-Teams/ba-p/132614)
 
