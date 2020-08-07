---
title: Utiliser bord pour gérer la qualité des appels et des réunions dans Microsoft teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies, gageames
audience: admin
description: Découvrez comment analyser et gérer les performances multimédias en temps réel dans Microsoft teams à l’aide du tableau de bord de qualité des appels (bord).
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
ms.openlocfilehash: f4221b08742d27b4dbe360dfd345142795640588
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581185"
---
#  <a name="use-cqd-to-manage-call-and-meeting-quality-in-microsoft-teams"></a>Utiliser bord pour gérer la qualité des appels et des réunions dans Microsoft teams 

Cet article est destiné aux administrateurs d’équipes ou au support technique et aux ingénieurs du support technique pour développer un processus de surveillance et de maintenance de la qualité des appels et des réunions de votre organisation à l’aide du tableau de bord de qualité des appels de Microsoft Teams (bord). Nos conseils mettent en évidence les scénarios de qualité audio, car toutes les améliorations apportées au réseau pour améliorer l’interface audio seront traduites par l’amélioration de la vidéo et du partage.

La clé de ces recommandations est l’un des deux [modèles bords](https://aka.ms/QERtemplates) , nous vous recommandons de les télécharger avant de suivre les instructions de cet article.

Cet article part du principe que vous avez déjà [configuré bord](turning-on-and-using-call-quality-dashboard.md).


## <a name="categories-to-monitor-and-maintain"></a>Catégories à surveiller et à mettre à jour

Une fois que vous avez déployé des réunions et de la voix dans Teams, vous avez besoin d’un plan de surveillance et de maintenance en cours. Cela permet de s’assurer que les équipes s’exécutent toujours de façon optimale. Ce plan doit inclure les principales zones répertoriées ci-dessous. Vous devez également établir des cibles pour les mesures de qualité ainsi qu’un plan de résolution des problèmes et d’isolation en temps réel.

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
<p>Divisez les mesures par des appels internes (au sein de votre organisation, tels que les réseaux privés, WiFi, filaires) ou les appels externes</p>
<p>Découper les métriques en créant ou en réseau</p>
<p>Appels VPN</p>
<p>Appels en utilisant TCP, UDP ou proxy</p>
</td>
</tr>
<tr class="even">
<td><strong>Fiabilité des appels</strong></td>
<td><p>Identifier et résoudre les problèmes de réseau ou de pare-feu</p>
<p>Familiarisez-vous avec les pourcentages de configuration des appels et les échecs de remise.</p>
<p>En savoir plus sur la plupart des échecs de configuration d’appel et de suppression</p>
</td>
</tr>
<tr class="odd">
<td><strong>Étude des utilisateurs</strong></td>
<td>
<p>Utiliser les données d’évaluation de mes appels pour en savoir plus sur l’utilisation réelle des utilisateurs</p>
<p>Où se produisent les mauvaises expériences ?</p>
<p>Mettre en corrélation la qualité médiocre de la qualité d’appel, de la fiabilité et des appareils</p>
</td>
</tr>
<tr class="even">
<td><strong>Appareils</strong></td>
<td><p>Découvrez quels sont les micros et les haut-parleurs les plus fréquemment utilisés et leurs répercussions sur la qualité des appels.</p>
<p>La prise en charge des pilotes audio, vidéo, USB et WiFi est-elle régulièrement corrigée ?</p>
</td>
</tr>
<tr class="odd">
<td><strong>Clients</strong></td>
<td>
<p>En savoir plus sur les types de client et les versions utilisés et leurs répercussions sur la qualité et la fiabilité des appels  </p>
</ol></td>
</tr>
</tbody>
</table>

En évaluant et en révisant en permanence les domaines mentionnés dans cet article, vous pouvez réduire leur potentiel pour les affecter à vos utilisateurs. La plupart des problèmes utilisateur peuvent être regroupés dans les catégories suivantes :

-   Configuration incomplète du pare-feu ou du proxy
-   Faible couverture Wi-Fi
-   Bande passante insuffisante
-   VPN
-   Versions et pilotes client incohérents ou obsolètes
-   Périphériques audio prédéfinis ou intégrés
-   Sous-réseaux ou périphériques réseau problématiques

Le bon déroulement de la planification et de la conception avant le déploiement d’équipes ou de Skype entreprise Online vous permet de réduire le nombre d’efforts qui seront nécessaires pour garantir une expérience de grande qualité.

Cet article porte sur l’utilisation du tableau de bord de qualité des appels (bord) en ligne en tant qu’outil principal permettant de signaler et d’examiner chaque zone, en mettant en évidence le son pour optimiser l’adoption et l’impact. Toute amélioration apportée au réseau pour améliorer la qualité audio sera également traduite directement par l’amélioration du partage de la vidéo et du bureau.

Pour accélérer votre évaluation, [deux modèles bord](https://aka.ms/qertemplates) conversés sont fournis : un pour la gestion de tous les réseaux et l’autre pour les réseaux gérés (internes) uniquement. Bien que les rapports de modèles tous les réseaux soient configurés pour afficher des informations sur la création et le réseau, ils peuvent toujours être utilisés lorsque vous travaillez dans le cadre de la collecte et du chargement des informations de bâtiment. Le chargement des informations de bâtiment dans bord permet au service d’améliorer la création de rapports en ajoutant des informations de construction, de réseau et d’emplacement personnalisées en les différenciant des sous-réseaux externes. Pour plus d’informations, voir [mappage de bâtiment](CQD-building-mapping.md).

### <a name="intended-audience"></a>Public ciblé

Cet article est destiné à être utilisé par les parties prenantes des partenaires et des clients ayant des rôles tels que le chef de service ou l’architecte de la collaboration, le consultant, le responsable de la gestion des changements

Cet article est également destiné à être utilisé par le ou les champions qualité désignés. Pour plus d’informations, reportez-vous à [la section rôle d’expert qualité](4-envision-plan-my-service-management.md#the-quality-champion-role).


## <a name="what-is-quality"></a>Qu’est-ce que la qualité ?

Dans ce contexte, la qualité est une combinaison d’indicateurs de service et d’une interface utilisateur.


### <a name="service-metrics"></a>Métriques de service

Les métriques de service sont composées de mesures spécifiques basées sur le client. Lors de chaque appel, le client récupère la télémétrie de l’appel et envoie un rapport à la fin de chaque appel, qui est accessible par la suite dans bord ou dans une [analyse d’appel par utilisateur](set-up-call-analytics.md). Ces mesures incluent (sans s’y limiter) :

-   Flux médiocre (entrant et sortant)
-   Taux d’échec d’installation
-   Taux d’échec de dépôt


#### <a name="poor-stream-rate"></a>Débit médiocre en flux continu

Le taux de flux médiocre (V.Q.P.R.D.) représente le pourcentage global de l’organisation de flux présentant une qualité médiocre. Cette métrique est destinée à mettre en évidence les domaines dans lesquels votre organisation peut se concentrer sur l’impact le plus élevé de la réduction de cette valeur et de l’amélioration de l’interface utilisateur, c’est pourquoi les [réseaux gérés](#managed-versus-unmanaged-networks) sont le principal foyer lors de la recherche de v.q.p.r.d.. Les utilisateurs externes sont aussi importants que les utilisateurs externes. Envisagez de fournir des recommandations destinées aux utilisateurs externes et examinez les appels externes indépendamment de l’organisation globale.

La mesure réelle dans bord varie en fonction de la charge de travail, mais dans le cadre de cet article, nous nous concentrerons essentiellement sur la mesure du _pourcentage audio médiocre_ . Le V.Q.P.R.D. est constitué des cinq moyennes métriques du réseau décrites dans le tableau suivant. Pour qu’un flux soit considéré comme médiocre, une seule métrique doit dépasser le seuil défini. BORD indique le « médiocre à cause de... » des mesures pour mieux comprendre quelle condition a entraîné le classement du flux comme médiocre. Pour en savoir plus, voir [classification des flux dans bord](stream-classification-in-call-quality-dashboard.md).

> [!Note]
> BORD indique le « médiocre à cause de... » des mesures pour mieux comprendre quelle condition a entraîné le classement du flux comme médiocre.


##### <a name="audio-poor-quality-metrics"></a>Mesures de qualité audio médiocres

| Moyenne métrique     | Description     | Expérience utilisateur |
|-------------|-----------------|-----------------|
| Scintillement de \> 30 ms        | Il s’agit de la modification moyenne du délai entre les paquets successifs. Les équipes et Skype entreprise peuvent s’adapter à certains niveaux de scintillement par le biais de la mise en mémoire tampon. C’est uniquement lorsque l’instabilité est supérieure à la mise en mémoire tampon qu’un participant a remarqué les effets de gigue.      | Les paquets entrants à des vitesses différentes peuvent entraîner le son de la voix du haut-parleur.   |
| Taux de perte \> de paquets de 10% ou 0,1        | Il s’agit généralement du pourcentage de paquets perdus. La perte de paquets a un effet direct sur la qualité audio (par rapport aux petits paquets perdus) qui n’ont quasiment aucun impact sur les pertes de Burst en retour à la fin de l’audio.     | Les paquets en cours de rejet et ne sont pas à l’origine de la destination prévue dans le média, ce qui génère des syllabes et des mots manqués, ainsi que la vidéo et le partage saccadés. |
| Durée de l’aller-retour \> 500 ms        | Il s’agit du temps nécessaire à l’obtention d’un paquet IP entre le point A et le point B et de nouveau au point A. Ce délai de propagation du réseau est lié à la distance physique entre les deux points et la vitesse de lumière, et inclut une surcharge supplémentaire prélevée par les divers appareils dans le chemin réseau.      | Les paquets prenant trop de temps pour arriver à leur destination entraînent un effet de diaphonie.   |
| NMOS moyenne \> 1,0         | Dégradation moyenne d' [avis du réseau (NMOS)](https://docs.microsoft.com/previous-versions/office/communications-server/bb894481(v=office.12)#network-mos) pour le flux. Représente le niveau de perte et de scintillation du réseau ayant affecté la qualité du son reçu et à l’origine du NMOS. | Il s’agit d’une combinaison de gigue, de perte de paquets et, à un niveau inférieur, d’une durée d’aller-retour accrue. Il est possible que l’utilisateur rencontre une combinaison des symptômes suivants.   |
| Taux moyen d’échantillons masqués \> 7% ou 0,07 | Rapport moyen du nombre de trames audio et d’échantillons masqués générés par la correction de perte de paquets sur le nombre total de trames audio. Un échantillon audio dissimulé est une technique permettant de lisser la transition brutale qui serait généralement provoquée par des paquets réseau interrompus.      | Les valeurs élevées indiquent qu’un masquage de niveau de perte élevé a été appliqué et qu’un son est altéré ou perdu.     |

##### <a name="why-do-we-prefer-to-use-streams-instead-of-calls"></a>Pourquoi préférez-vous utiliser des flux au lieu d’appels ?

Les flux nous indiquent que la jambe de l’appel a été médiocre ou sortante. Lorsque vous examinez les données d’analyse des appels, vous pouvez déterminer si le problème est dû à un mauvais appel en raison du flux de l’appelant (sortant) ou du flux de l’appelant (entrant). Il est encore plus important de déterminer quel flux a un impact sur la qualité des appels. Si vous examinez uniquement les données d’appel, vous verrez le nombre de conférences auxquelles une personne a participé, mais vous ne verrez pas les personnes qui sont actives dans le partage d’écran.

Les données d’appel vous fournissent des indicateurs d’utilisation, mais ne vous conduisent pas nécessairement à la cause de la mauvaise qualité des appels. Lorsque vous examinez la direction du flux, vous pouvez identifier les facteurs tels qu’un appel qui ne se trouve pas sur un réseau géré, un appel provenant d’un autre employé (par exemple, un fournisseur ou une personne située sur un autre réseau). Dans ces cas, si la connexion réseau de l’autre personne était médiocre, l’appel complet sera considéré comme médiocre. Comme vous ne pouvez rien d’autre à faire des facteurs externes, ces données ne sont pas utiles.

Le sens du flux peut également vous aider à identifier les appareils ou clients posant problème.

 - Par exemple, si vous disposez d’un budget limité pour les appareils et que vous souhaitez fournir des appareils uniquement aux utilisateurs de contenus audio importants, utilisez le rapport d’utilisation audio (VoIP) et filtrez les flux sortants et les conférences. Recherchez les utilisateurs de périphériques audio de grande qualité qui parlent de micros intégrés, tels que la qualité des appels (et vous souhaiterez peut-être fournir des périphériques audio pour ces personnes). Pour plus de clarté, vous pouvez filtrer l’utilisation des paquets, ce qui vous permet de cibler des utilisateurs plus importants en volume. 

  - Un autre exemple concerne le partage d’écran. Si un client utilise un ancien client Teams, les performances du partage d’écran risquent d’être affectées. Pour résoudre ce problème, nous vous conseillons de définir la priorité des mises à niveau du client pour les personnes qui partagent un grand nombre de partage d’écran.

 - En identifiant quelle direction d’un flux entraîne une mauvaise qualité de l’appel, vous pouvez déterminer si vous rencontrez un problème de qualité de service (QoS ou bande passante). Si vous n’avez pas entièrement implémenté QoS, ou si vous n’avez marqué que les paquets sur le client et non sur le flux entrant, il est possible que la qualité d’appel soit médiocre. En observant la direction du flux, vous pouvez obtenir une vue plus granulaire de la perte de paquets, de la latence ou du scintillement dans une direction spécifique. 

   - Par exemple, imaginons qu’un utilisateur se plaigne de son robotisé sur une connexion câblée (gigue). En examinant le flux et la direction, vous pouvez déterminer que le problème se produit sur le flux entrant, uniquement pour un ensemble de sous-réseaux spécifiques. Une fois que vous avez envoyé ces informations à votre équipe de mise en réseau, celles-ci peuvent effectuer le suivi d’un accélérateur WAN incorrectement configuré sans ignorer le trafic multimédia. Lorsque l’équipe du réseau reconfigure l’accélérateur WAN, la gigue disparaît et la qualité d’appel est améliorée. 


#### <a name="setup-failure-rate"></a>Taux d’échec d’installation

Le taux d’échec d’installation, également connu sous le nom de mesure du _pourcentage d’échec de configuration d’appel_ dans bord, est le nombre de flux pour lesquels le chemin de médias n’a pas pu être établi entre les points de terminaison au début de l’appel.

Cela représente tout flux multimédia qui ne peut pas être établi. En raison de la gravité du problème lié à l’utilisation de l’utilisateur, l’objectif est de réduire cette valeur à la valeur la plus proche possible. Une valeur élevée de cette métrique est plus courante dans les nouveaux déploiements avec des règles de pare-feu incomplètes qu’un déploiement mature, mais il est encore important de surveiller régulièrement.

Cette métrique est calculée en prenant en charge le nombre total de flux qui n’ont pas pu être configurés divisé par le nombre total de flux ayant soumis un enregistrement des détails des appels réussi (CDR) :

-   **Taux d’échec** de la configuration = nombre total de flux d’échecs de configuration d’appel/nombre total de flux de CDR disponibles

#### <a name="drop-failure-rate"></a>Taux d’échec de dépôt

Le taux d’échec de la suppression, également connu sous le nom de mesure du _pourcentage d’échec d’appel interrompu_ dans bord, correspond au pourcentage de flux établi pour lesquels le chemin de médias ne s’est pas terminé correctement.

Il s’agit d’un flux multimédia qui s’est arrêté de manière inattendue. Même si l’impact d’une telle opération n’est pas aussi sévère qu’un flux qui n’a pas pu être configuré, il affecte tout de même le processus utilisateur. Les chutes de média soudaines et fréquentes ne peuvent avoir un impact important sur l’interface utilisateur, ce qui a pour effet de reconnecter les utilisateurs, ce qui a perdu la productivité (sans mentionner la frustration).

La métrique est calculée en prenant le nombre total de flux déplacés divisé par le nombre total de flux configurés correctement :

-   **Taux d’échec de dépôt** = nombre total de flux d’appel interrompus/nombre total de flux d’appel interrompus

### <a name="define-your-target-metrics"></a>Définir vos indicateurs cibles

Cette section présente certaines des métriques de service fondamentales que nous utilisons pour évaluer l’état des services. En évaluant et en continuant à mettre en œuvre les mesures suivantes, vous pouvez vous assurer que vos utilisateurs disposent d’une qualité d’appel homogène et fiable. Comme point de départ, utilisez les cibles suggérées dans le tableau ci-dessous. Ajustez les cibles selon les besoins pour répondre aux objectifs de votre entreprise.

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

### <a name="user-experience"></a>Expérience utilisateur

L’analyse de l’utilisation de l’utilisateur est une plus grande art que la science, car les métriques collectées ici ne signifient pas nécessairement qu’il y a un problème avec le réseau ou le service, mais qu’ils indiquent simplement que l’utilisateur a un problème. BORD inclut un mécanisme d’étude intégré (le centre RMC) pour vous aider à évaluer l’utilisation globale de l’utilisateur. RMC vous donne un aperçu des questions suivantes du point de vue de vos utilisateurs :

-   Comment utiliser la solution ?
-   La solution est-elle facile à utiliser et intuitive, et est-elle prise en charge par les besoins en matière de communication au jour le jour ?
-   La solution m’aide-t-elle à accomplir mon travail ?
-   Quelle est la perception globale de la solution ?
-   Puis-je utiliser la solution à tout moment, où que je me trouve ?
-   Est-il possible de configurer et de tenir à jour un appel ?

#### <a name="rate-my-call"></a>Évaluer mon appel 

Notez que mon appel est intégré aux équipes et à Skype entreprise. Le message s’affiche automatiquement après un appel ou 10%. Cette courte étude demande à l’utilisateur d’évaluer l’appel et de fournir un peu de contexte pour la qualité de l’appel. Une ou deux évaluations sont considérées comme médiocres, trois à quatre sont bonnes et cinq est excellent. Même s’il s’agit d’un indicateur de plus en plus, il s’agit d’une métrique utile pour découvrir les problèmes que peuvent manquer les métriques de service.

> [!Note]
> Le facteur humain : les utilisateurs ignorent souvent l’enquête lorsque la qualité d’appel est bonne et qu’ils le remplissent lorsque la qualité d’appel est mauvaise. Par conséquent, vos rapports centre RMC peuvent être inclinés au mauvais niveau même alors que les métriques de service conviennent.

Vous pouvez utiliser bord pour signaler les réponses des utilisateurs RMC et des exemples de rapports sont inclus dans le modèle bord. Toutefois, elles ne sont pas décrites en détail dans cet article. 

#### <a name="client-and-device-readiness"></a>Disponibilité du client et de l’appareil

Vous avez besoin d’une stratégie de client et d’appareil solide pour vous assurer que vos utilisateurs disposent d’une interface utilisateur homogène et positive. Quelques principes clés pilotent chaque stratégie de compatibilité.

##### <a name="client-readiness"></a>Disponibilité du client

La mise à jour du client teams permet à vos utilisateurs d’obtenir toujours la meilleure utilisation possible. Microsoft publie régulièrement des [mises à jour du client teams](teams-client-update.md) (la mise à jour s’installe en arrière-plan, sauf si vous avez désactivé cette fonctionnalité, ce que nous déconseillons). Il est également important de ne pas oublier de corriger les pilotes réseau, vidéo, USB et audio, car ils sont souvent oubliés et peuvent affecter la qualité des appels et des réunions. Envisagez d’ajouter des pilotes réseau, Wi-Fi, vidéo, USB et audio à votre processus de gestion des correctifs actuel.


##### <a name="device-readiness"></a>Compatibilité de l’appareil

Aucune stratégie unique ne peut influer sur l’interface utilisateur en plus de la stratégie de compatibilité de votre appareil. Par exemple, les utilisateurs qui s’appuient sur leurs haut-parleurs et le micro de leur ordinateur portable connaissent de nombreux bruits de fond dans les appels et les réunions. Teams est conçu pour fonctionner sur n’importe quel appareil, mais si vous rencontrez des problèmes liés à un appareil, voir [téléphone pour teams](phones-for-teams.md).


### <a name="categories-of-quality"></a>Catégories de qualité

Opérationnel d’un ensemble de pratiques en matière de gestion de la qualité : cela vous permet d’obtenir la meilleure qualité d’appel et de qualité de la réunion. Un plan de gestion de bonne qualité répond aux catégories suivantes :

-   **Réseau :** Qualité audio focalisée sur la métrique du rapport de flux médiocre (V.Q.P.R.D.), l’utilisation des protocoles filaire et sans fil et l’identification de l’utilisation des proxys HTTP et du VPN

-   **Points de terminaison :** Périphériques audio et clients à jour

-   **Gestion du service :** Cette catégorie comprend deux sections :

    -   Tout d’abord, il incombe à Microsoft de gérer et de tenir à jour les équipes et services Skype entreprise online.

    -   Deuxièmement les tâches que votre organisation gère pour garantir un accès fiable au service, par exemple, la mise à jour des informations de bâtiment et la maintenance des pare-feu pour les nouvelles adresses IP d’Office 365 lors de l’ajout d’une infrastructure au service.

![Graphique des catégories de qualité dans une organisation](media/qerguide-image-categories.png "Catégories de qualité au sein d’une organisation : gestion du service, points de terminaison et réseau.")

Passez en revue la liste de tâches recommandée pour garantir la qualité de votre présentation. Vous devez effectuer ces tâches de façon régulière (par exemple, hebdomadaire).

#### <a name="service-management-tasks"></a>Tâches de gestion des services

Ces tâches vont de s’assurer qu’il y a suffisamment de bande passante pour parvenir au service sans saturer les liens Internet, en validant la qualité de service (QoS) en place sur toutes les zones réseau gérées et en restant au top des [plages d’adresses IP d’Office 365 sur les pare-feu](https://aka.ms/o365ips).

#### <a name="network-tasks"></a>Tâches réseau

Il existe deux catégories de tâches réseau : fiabilité et qualité. Le niveau de fiabilité est axé sur la mesure des capacités de l’utilisateur à passer des appels avec succès et de rester connecté. La qualité porte sur la télémétrie agrégée envoyée aux équipes et Skype entreprise Online par le client de l’utilisateur au cours de l’appel et une fois qu’il a terminé. 

Dans la mesure où la fiabilité s’est produite dans l’interface utilisateur, nous vous recommandons d’évaluer et d’examiner les mesures de fiabilité avant de vous plonger dans la qualité. 

#### <a name="endpoints-tasks"></a>Tâches de points de terminaison

Tâche principale de cette catégorie supprimant les obstacles aux [mises à jour du client d’équipes](teams-client-update.md)normales. Par défaut, les équipes sont automatiquement mises à jour régulièrement (sauf si vous désactivez ce paramètre, ce que nous déconseillons). 

Vous devez également surveiller les appareils et fournir des mises à jour chaque fois que vous identifiez des problèmes liés à un appareil.

## <a name="use-cqd-to-manage-call-quality"></a>Utiliser bord pour gérer la qualité des appels

Une fois que vous avez [configuré bord](turning-on-and-using-call-quality-dashboard.md), vous pouvez commencer à l’utiliser pour gérer la qualité des appels et des réunions pour votre organisation.

La plupart des problèmes liés aux performances d’une équipe appartiennent aux catégories suivantes :

-   Configuration incomplète du pare-feu ou du proxy
-   Faible couverture Wi-Fi
-   Bande passante insuffisante
-   VPN
-   Versions et pilotes client incohérents ou obsolètes
-   Périphériques audio prédéfinis ou intégrés
-   Sous-réseaux ou périphériques réseau problématiques

Si vous prenez le temps de mettre en place les équipes pour évaluer ces domaines et remédier aux déficiences, vous pouvez réduire le nombre d’efforts nécessaires pour garantir une meilleure qualité de l’utilisation des équipes de tous vos utilisateurs. Pour obtenir de l’aide sur le déploiement de votre réseau pour votre déploiement d’équipe, lisez [conseiller pour teams](use-advisor-teams-roll-out.md) et [Préparez votre réseau pour teams](prepare-network.md).

### <a name="expectations-using-cqd"></a>Attentes avec bord

Utilisez le tableau de bord de qualité des appels (bord) pour mieux comprendre la qualité des appels passés à l’aide d’équipes et de services Skype entreprise. BORD est conçu pour permettre aux équipes et aux ingénieurs du réseau et aux équipes de se familiariser avec les équipes et les ingénieurs réseau d’optimiser le réseau et d’avoir un œil plus étroit sur la qualité, la fiabilité et l’interface utilisateur. BORD examine la télémétrie globale d’une entreprise entière, où les modèles globaux peuvent apparaître ; Cela vous permet de passer des examens éclairés et de planifier la correction. BORD fournit des rapports de mesures qui fournissent des indications sur la qualité générale, la fiabilité et l’utilisation de l’utilisateur.

BORD, même s’il est utile pour analyser des tendances et des sous-réseaux, ne fournit pas toujours une cause spécifique pour un scénario donné. Il est important de comprendre ceci et de définir les attentes appropriées lors de l’utilisation de bord :

-   BORD ne fournit pas la cause racine de chaque scénario.
-   BORD ne contient pas le système téléphonique ou les flux de conférences audio.
-   BORD appelle des zones pour une étude plus approfondie en fonction des tendances

### <a name="cqd-reports-overview"></a>Vue d’ensemble des rapports bord

Utilisez le menu déroulant en haut de l’écran pour ouvrir un rapport. Pour obtenir la liste des données fournies dans chaque rapport, voir [données disponibles dans les rapports bord](CQD-data-and-reports.md#data-available-in-cqd-reports).

Nouveauté de janvier 2020 : [Télécharger les modèles de requête Power bi pour bord](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modèles Power BI personnalisables que vous pouvez utiliser pour analyser et enregistrer vos données bord.


### <a name="teams-vs-skype-for-business"></a>Équipes et Skype entreprise

BORD pouvez créer des rapports sur les équipes et Skype entreprise. Néanmoins, il peut arriver que vous souhaitiez créer un rapport pour examiner la télémétrie d’équipes dans Skype entreprise.

#### <a name="summary-reports"></a>Rapports de synthèse

Pour modifier la page rapports de synthèse de sorte qu’il ne s’affiche que dans teams ou Skype entreprise, sélectionnez le menu déroulant **filtre du produit** en haut de l’écran, puis sélectionnez le produit souhaité.

![Capture d’écran du menu déroulant affichant les options de filtrage](media/qerguide-image-productfilter.png)

#### <a name="detailed-reports"></a>Rapports détaillés

Pour filtrer tous les rapports détaillés, dans la barre de navigation, ajoutez le code suivant à la fin de l’URL :

```PowerShell
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Example**

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Pour plus d’informations sur les filtres d’URL, voir afficher des [rapports de filtrage](CQD-data-and-reports.md#report-filters) plus loin dans cette section.

Pour filtrer un rapport détaillé individuel, ajoutez le filtre ``Is Teams`` au rapport et attribuez-lui la valeur true ou false.

![Capture d’écran de la page Ajouter un filtre](media/qerguide-image-addteamsfilter.png)

### <a name="managed-versus-unmanaged-networks"></a>Gestion des réseaux gérés et non gérés

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

-   **Bon ou médiocre :** Un appel bon ou médiocre se compose d’un appel qui contient un ensemble complet de métriques de service pour lequel un rapport QoE complet a été généré et reçu par le service. Le fait de déterminer si un flux est correct ou médiocre est décrit [plus haut dans cet article](#poor-stream-rate).

-   Non **classées :** Un flux non classé ne contient aucun ensemble complet de métriques de service. Il peut s’agir d’appels courts (généralement moins de 60 secondes) où les moyennes n’ont pas pu être calculées et un rapport QoE n’a pas été généré. Le motif le plus courant pour les appels non classés est qu’il n’y a pas eu de faible taux d’utilisation des paquets. C’est par exemple le tout participant qui rejoint une réunion en silence et ne parle jamais. Le participant reçoit, mais ne transmet pas, de contenu multimédia. Si les éléments multimédias ne sont pas transmis, il n’y a aucune mesure disponible pour bord à utiliser pour classifier le flux multimédia sortant du point de terminaison.

Pour en savoir plus, voir [classification des flux dans bord](stream-classification-in-call-quality-dashboard.md).

### <a name="common-subnets"></a>Sous-réseaux courants

Les sous-réseaux courants sont des sous-réseaux privés spécifiques utilisés par des hôtels, des réseaux familiaux, des points d’accès et des zones similaires. Le triage de ces sous-réseaux est difficile en raison de leur utilisation massive. Si votre organisation utilise l’un de ces sous-réseaux communs, il est recommandé de déplacer ce réseau vers un autre sous-réseau. Le création de rapports sera plus simple dans bord. Dans le cas contraire, les rapports du modèle All Networks ont été configurés de manière à exclure ces sous-réseaux pour les éliminer en tant que source de mauvaise qualité. Les sous-réseaux courants sont définis ci-dessous. leurs répercussions varient en fonction de l’organisation.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Lorsque vous étudiez un réseau géré qui utilise un sous-réseau commun, vous devez utiliser la deuxième dimension IP locale réflexive pour les sous-réseaux de groupe. Cette dimension contient l’adresse IP publique du point de terminaison.


## <a name="reliability-investigations"></a>Investigations de fiabilité

La première étape pour améliorer la qualité consiste à évaluer l’état de la fiabilité au sein de l’organisation. Dans la mesure où la fiabilité est essentielle pour une utilisation positive de l’utilisateur, nous commençons par les deux composants qui mesurent la fiabilité :

1.  **Échecs de configuration :** L’appel n’a pas pu être établi.

2.  **Échecs de la suppression :** L’appel a été établi et arrêté de manière inattendue.

Dans cette section, nous allons aborder les méthodes permettant d’identifier les deux domaines.

> [!NOTE]
> Tous les rapports inclus dans les modèles ne sont pas abordés dans cet article. Toutefois, les méthodes de vérification décrites ci-dessous s’appliquent. Pour plus d’informations, reportez-vous à la description du rapport individuel.


### <a name="setup-failures"></a>Échecs de configuration

Par priorité, vous devez d’abord résoudre les problèmes d’installation liés à l’utilisation de l’interface utilisateur.

Commencez votre examen en évaluant le pourcentage d’échecs de configuration globaux pour l’organisation, puis donnez la priorité aux domaines d’examen en fonction du pourcentage le plus élevé en créant ou en réseau. 

#### <a name="setup-failure-trend-analysis"></a>Analyse des tendances d’échec d’installation

Ce rapport affiche le nombre total de flux, les échecs de configuration de flux et le taux d’échec de configuration de flux. Pointez sur l’une des colonnes pour afficher ses valeurs individuelles. 

##### <a name="analysis"></a>Étude

Ce rapport vous permet de répondre aux questions suivantes et de déterminer la marche à suivre suivante :

-   Quel est le pourcentage d’échec de configuration du total d’appels pour le mois en cours ?

-   Est-ce que le pourcentage d’échec de configuration d’un appel inférieur ou au-dessus de la mesure cible définie ?

-   Le problème est-il pire ou supérieur au mois précédent ?

-   La tendance de l’échec augmente-t-elle, elle est constante ou dégressive ?

Quelles que soient les réponses à ces questions, prenez le temps de vous familiariser avec les sous-rapports pour rechercher des bâtiments ou sous-réseaux individuels susceptibles de nécessiter une correction. Même si le taux d’échec global est peut-être inférieur à la métrique cible, les taux d’échec pour un ou plusieurs bâtiments ou réseaux peuvent être supérieurs à la métrique cible et avoir besoin d’une étude.

#### <a name="setup-failure-investigations"></a>Investigations d’échecs de configuration 

Ce rapport de synthèse permet de détecter et d’isoler tout bâtiment ou réseau susceptible de nécessiter une correction.

> [!NOTE]
> Veillez à ajuster le filtre de rapport mois par année au mois en cours. Sélectionnez **modifier**, puis ajustez le filtre de rapport **mois-année** pour enregistrer le nouveau mois par défaut.

##### <a name="remediation"></a>Remediation 

Focalisez-vous sur votre première action de correction sur les bâtiments ou sous-réseaux présentant le plus grand nombre d’échecs. Cela a un impact sur l’utilisation de l’utilisateur et de l’aide pour réduire rapidement le taux d’échecs de configuration des appels de l’organisation. Le tableau suivant répertorie les deux raisons pour lesquelles les échecs de configuration ont été signalés par bord.

| Raison de l’échec de configuration d’un appel       | Cause classique                    |
|----------------------------------|----------------------------------|
| Règle d’exemption de paquets | Indique que les équipements réseau en fonction du chemin d’accès ont empêché l’établissement du chemin d’accès multimédia en raison de règles de vérification approfondie des paquets. Cela peut être dû au fait que les règles de pare-feu ne sont pas correctement configurées. Dans ce scénario, l’établissement d’une connexion TCP réussie, mais pas la connexion SSL.      |
| Règle d’exception de bloc IP FW manquante      | Indique que les équipements réseau en fonction du chemin d’accès ont empêché le chemin multimédia d’être établis au réseau Microsoft 365 ou Office 365. Cela peut être dû au fait que des règles de proxy ou de pare-feu ne sont pas correctement configurées pour autoriser l’accès aux adresses IP et aux ports utilisés pour le trafic des équipes et Skype entreprise. |

Lorsque vous commencez votre politique de correction, vous pouvez vous concentrer sur un bâtiment ou un sous-réseau particulier. Comme décrit dans le tableau ci-dessus, ces problèmes sont dus à des configurations de pare-feu ou de proxy. Passez en revue les options du tableau suivant pour les actions de correction.

|      Remediation      |Aide  |
|-----------------------|----------|
| Configurer des pare-feu | Travaillez avec votre équipe réseau et vérifiez la configuration de votre pare-feu par rapport à [la liste d’adresses IP d’Office 365](https://aka.ms/o365ips).<br><br>Vérifiez que les [sous-réseaux](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) et ports de média sont inclus dans les règles de pare-feu. <br><br>Vérifiez que les [ports nécessaires](prepare-network.md) sont ouverts dans le pare-feu. La priorité du protocole UDP doit être donnée, car TCP est considéré comme un protocole de restauration automatique pour le partage d’écran audio, vidéo et vidéo, et son utilisation affectera la qualité de l’appel. Le partage d’application RDP hérité utilise TCP uniquement.|

### <a name="drop-failures"></a>Ignorer les échecs

Contrairement aux codes d’échec d’installation, bord n’a pas de code d’échec de remise pour indiquer la raison pour laquelle les échecs de suppression se produisent, ce qui complique l’isolation d’une cause initiale spécifique. Pour mieux trier les échecs de remise, utilisez une approche inférés. En réservant les centres d’intérêt pour les contenus multimédias, les correctifs de clients et de pilotes, et l’utilisation d’appareils certifiés pour les équipes et Skype entreprise, vous pouvez faire en sorte que les échecs de remise soient refusés.

#### <a name="drop-failure-trend-analysis"></a>Analyse des tendances d’échec de remise

Ce rapport affiche le volume total de flux audio, d’échecs de remise au total et le taux d’échec de la suppression. Pointez sur l’une des colonnes pour afficher ses valeurs. 


##### <a name="analysis"></a>Étude

En utilisant ce type de rapport, vous pouvez répondre aux questions suivantes :

-   Quel est le taux d’échec de la remise actuelle ?
-   Le taux d’échec de la chute est-il inférieur à la valeur cible définie ?
-   Le problème est-il pire ou supérieur au mois précédent ?
-   La tendance de l’échec augmente-t-elle, elle est constante ou dégressive ?

Quelles que soient les réponses aux questions ci-dessus, prenez le temps de rechercher les bâtiments ou réseaux susceptibles de nécessiter une correction à l’aide de sous-rapports. Même si le taux d’échec de la suppression globale peut être inférieur à la métrique cible, le taux d’échec de la suppression d’un ou de plusieurs bâtiments ou réseaux peut se trouver au-dessus de la métrique cible et avoir besoin d’une étude.

#### <a name="drop-failure-investigations"></a>Échecs de la liste des investigations

Les échecs signalés ici indiquent que l’appel a été interrompu de manière inattendue et ont entraîné une utilisation négative de l’utilisateur. À la différence des rapports de tendance, ces rapports fournissent des informations supplémentaires sur les sous-réseaux spécifiques qui nécessitent des examens supplémentaires.


##### <a name="remediation"></a>Remediation

L’utilisation des rapports de tableau inclus vous permet d’isoler les zones de problèmes du réseau où le taux de remise est supérieur à la mesure cible que vous avez définie. Focalisez-vous sur votre première action de correction sur les bâtiments ou sous-réseaux qui présentent le nombre total de flux de flux, pour apporter le plus grand impact.

Causes fréquentes des rejets d’appel :

-   Sortie Internet sous-configurée
-   Aucun QoS configuré sur les réseaux contraintes
-   Versions de client plus anciennes
-   Comportement des utilisateurs

Après avoir détecté les zones à problème, vous pouvez utiliser une [analyse d’appel par utilisateur](use-call-analytics-to-troubleshoot-poor-call-quality.md) pour passer en revue les utilisateurs de ce bâtiment pour des problèmes spécifiques. L’analyse des appels contient d’autres données EUII et peut s’avérer utile pour isoler davantage les raisons potentielles des échecs de remise.

Quelle que soit la prochaine étape, il est conseillé d’informer votre support technique qu’un problème a été détecté dans les bâtiments ou sous-réseaux spécifiques. Cela permet au support technique de répondre rapidement aux appels entrants et de trier les utilisateurs plus efficacement. Les utilisateurs avec indicateur peuvent ensuite être notifiés à l’équipe d’ingénierie pour de plus amples examens.

Le tableau suivant répertorie quelques méthodes courantes pour gérer et corriger les échecs de suppression.

| Remediation                              | Aide                      |
|------------------------------------------|-------------------------------|
| **Réseau/Internet**                         | **Encombrement**: collaborez avec votre équipe réseau pour contrôler la bande passante sur des bâtiments/sous-réseaux spécifiques pour vérifier qu’il y a des problèmes de surutilisation. Si vous confirmez la congestion du réseau, envisagez d’augmenter la bande passante pour la création ou l’application de QoS. Utilisez les rapports de synthèse de l' [État qualité](#quality-investigations) de la qualité incluse pour passer en revue les sous-réseaux de problèmes afin de résoudre les problèmes de gigue, de latence et de perte de paquets, car ils précèdent souvent un flux interrompu.<br><br>**Qualité**de service (QoS) : si la bande passante augmente ou n’est pas adaptée, envisagez d’implémenter QoS. Cet outil est très efficace pour gérer le trafic congestionné et peut garantir que les paquets multimédias du réseau géré sont classés par priorité au-dessus du trafic non multimédia. Par ailleurs, s’il n’y a pas de justification évidente de la bande passante, envisagez les solutions suivantes :<ul><li>[Conseils QoS de Microsoft teams](qos-in-teams.md)</li></ul><br>**Effectuer une évaluation de la disponibilité du réseau**: une évaluation du réseau fournit des détails sur l’utilisation de la bande passante attendue, sur la gestion de la bande passante et des changements réseau, ainsi que sur les pratiques recommandées pour les équipes et Skype entreprise. En utilisant le tableau précédent comme source, vous disposez d’une liste de bâtiments ou de sous-réseaux qui constituent un excellent choix pour une analyse.<ul><li>[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)</li></ul> |
| **Clients (Skype entreprise Online uniquement)** | Certains clients Skype entreprise anciens présentent des problèmes liés à la fiabilité des médias connus. Passez en revue les rapports d’analyse des appels de plusieurs utilisateurs concernés, ou créez un rapport de table de version de client personnalisée dans bord filtré sur des bâtiments ou sous-réseaux spécifiques avec la mesure% d’échec de l’appel. Les informations ci-dessous vous aideront à comprendre s’il existe une relation entre les chutes d’appel dans ce bâtiment spécifique et une version spécifique du client.     |
| **Appareils**                                  |Si les appareils sont à l’origine de problèmes de qualité d’appel, envisagez de mettre à jour des périphériques posant problème. Pour en savoir plus, voir [téléphones pour les équipes](phones-for-teams.md) . |
| **Comportement des utilisateurs**                            | Si vous déterminez que le problème n’est pas lié au réseau, aux appareils ou aux clients, envisagez de développer une stratégie d’adoption des utilisateurs pour éduquer les utilisateurs et les quitter. Les équipes plus intelligentes et les utilisateurs de Skype entreprise auront une meilleure expérience utilisateur pour tous les participants à la réunion. Par exemple, un utilisateur qui met son ordinateur portable en veille (en fermant le capot) sans quitter la réunion sera considéré comme une chute d’appel inattendue.   |

## <a name="quality-investigations"></a>Examens de qualité

L’étape suivante permettant d’évaluer l’état de la qualité audio au sein de l’Organisation consiste à identifier le taux de transmission médiocre (V.Q.P.R.D.), le TCP et l’utilisation du proxy. Il est important de garder à l’esprit que les données de bord ne vous fournissent pas de raison initiale précise, mais qu’il vous suffit de vous présenter à l’origine de problèmes potentiels pour commencer une conversation de collaboration avec les équipes appropriées en matière d’activités de correction. 

> [!NOTE]
> Tous les rapports inclus dans les modèles ne sont pas abordés dans cet article. Toutefois, les méthodes d’enquête expliquées ci-dessous seront toujours applicables pour ces rapports. Pour plus d’informations, reportez-vous à la description du rapport individuel. 

### <a name="quality"></a>Supérieure

Les pourcentages de V.Q.P.R.D. permettent d’indiquer si l’organisation utilise des cibles métriques définies pour une zone de focalisation donnée. Il est important de noter que, même si les pourcentages de haut niveau font partie de la cible définie, il est possible que les sous-réseaux ou les bâtiments individuels ne respectent pas les cibles définies et nécessitent par conséquent une étude plus approfondie. Par exemple, si le pourcentage global de V.Q.P.R.D. correspond à 2% en avril, qui correspond à la cible de l’exemple, les bâtiments et sous-réseaux individuels peuvent malgré tout présenter des expériences médiocres, selon la distribution globale de ces 2%. 

Pour évaluer le pourcentage de flux médiocres, utilisez les rapports qualité. Différents rapports sur la qualité sont fournis pour réviser les indicateurs de mesure pour les appels généraux, de conférence, d’appels RTC, de VPN et de salles de réunion. Le rapport mensuel, hebdomadaire et quotidien est fourni pour vous aider dans le cadre de ce processus. Les rapports hebdomadaires et quotidiens sont limités au modèle réseaux gérés pour une productivité accrue et une réduction du bruit. 

#### <a name="quality-trend-analysis"></a>Analyse des tendances de qualité

Les rapports de tendance affichent des informations de qualité dans le temps et permettent d’identifier et de comprendre les tendances de qualité dans chaque domaine d’intérêt. Comme indiqué plus haut, il existe des arbres de rapport inclus dans les modèles pour examiner la qualité ; Conférences, appels RTC à deux parties, VPN et salles de réunion. Dans le cadre de l’analyse de la qualité, le processus d’investigation est le même. Néanmoins, nous vous conseillons d’abord commencer par les conférences, car toute amélioration apportée à la qualité de la Conférence affectera également tous les autres aspects. 

> [!Note]
> L’examen des salles de réunion et de la fonction d’appel RTC et des salles de réunion est semblable à l’examen des conférences. Le focalisation consiste à isoler les bâtiments ou les sous-réseaux présentant la meilleure qualité de qualité et à identifier les raisons de la qualité médiocre.

> [!Important]
> Les rapports basés sur VPN sont filtrés à l’aide de la deuxième dimension VPN. Cette dimension nécessite que la carte réseau VPN soit correctement inscrite en tant qu’adaptateur d’accès distant. Les fournisseurs de réseau privé virtuel n’utilisent pas de manière fiable cet indicateur, et votre kilométrage varie en fonction du fournisseur de VPN déployé au niveau de votre organisation. Modifiez les rapports [VPN](CQD-upload-tenant-building-data.md#vpn) si nécessaire à l’aide du nom de bâtiment ou de réseau.

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


> [!Note]
> Les sous-réseaux courants sont difficiles à trier en raison de leur utilisation massive. Un rapport séparé qui affiche l’adresse IP publique du client (deuxième adresse IP locale réflexive) a été ajouté au modèle tous les réseaux pour faciliter la conversion des bureaux qui utilisent des réseaux communs.


![Capture d’écran montrant le résumé du flux audio médiocre](media/qerguide-image-poorqualitysummary.png)

##### <a name="remediation"></a>Remediation

Concentrez vos efforts de correction sur des bâtiments ou des sous-réseaux disposant du plus grand volume de flux, car cela permet d’optimiser l’impact et de faciliter l’utilisation rapide de l’utilisateur. Utilisez les mesures de gigue, de perte de paquets et de temps de boucle pour comprendre ce qui contribue à la qualité médiocre (il est possible qu’il y ait plusieurs problèmes) :

-   **Gigue**: les paquets multimédias arrivent à des vitesses différentes, ce qui a pour effet d’entendre un haut-parleur du son.
-   **Perte de paquets**: les paquets multimédias sont déposés, ce qui crée l’effet de mots ou syllabes manquants.
-   **RTT**: les paquets multimédias prennent du temps pour accéder à leur destination, ce qui crée un effet de diaphonie.

Pour vous aider à examiner les problèmes de qualité, utilisez [une analyse d’appel par utilisateur](use-call-analytics-to-troubleshoot-poor-call-quality.md). Grâce à la fonction d’analyse des appels, vous pouvez examiner le rapport d’appel d’une conférence ou d’un utilisateur spécifique. Ce rapport contient des données de EUII/informations d’identification personnelle et peut s’avérer utile lorsque vous recherchez la cause d’une panne. Une fois que vous connaissez le bâtiment affecté, il est facile d’effectuer le suivi des utilisateurs dans ce bâtiment. 

N’oubliez pas de faire savoir au support technique que ces réseaux rencontrent des problèmes de qualité pour pouvoir trier et répondre rapidement aux appels entrants.

| Remediation                              | Aide                         |
|------------------------------------------|----------------------------------|
| **Réseaux**                                 | **Congestion**: un réseau surutilisé ou sous-approvisionné peut poser des problèmes de qualité multimédia. Collaborer avec l’équipe du réseau pour déterminer si les connexions réseau de l’utilisateur au point de sortie Internet disposent d’une bande passante suffisante pour prendre en charge le contenu multimédia. <br><br>**Effectuer une évaluation de la disponibilité du réseau**: une évaluation du réseau fournit des détails sur l’utilisation de la bande passante attendue, sur la gestion de la bande passante et des changements réseau, ainsi que sur les pratiques recommandées pour les équipes et Skype entreprise. En utilisant le tableau précédent comme source, vous disposez d’une liste de bâtiments ou de sous-réseaux qui constituent un excellent choix pour une analyse.<ul><li>[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)</li></ul>|
| **Qualité de service (QoS)**  | La qualité de service (QoS) est un outil reconnu qui vous permet de hiérarchiser les paquets sur un réseau encombré pour s’assurer qu’ils arrivent à leur destination intacte et à temps. Envisagez d’implémenter QoS au sein de votre organisation afin d’optimiser la qualité de l’utilisation de la bande passante. La qualité de service (QoS) vous aidera à résoudre les problèmes généralement liés aux niveaux de perte de paquets élevés et à un niveau inférieur pour les temps de scintillement et de boucle.<ul><li>[Conseils QoS teams](qos-in-teams.md)</li></ul> |
| **Wi-Fi**               | Le Wi-Fi peut avoir un impact important sur la qualité des appels. Les déploiements Wi-Fi ne prennent généralement pas en considération la configuration réseau requise pour les services VoIP et sont souvent une source de mauvaise qualité. Pour plus d’informations sur l’optimisation de votre infrastructure Wi-Fi, voir [cet article sur la planification Wi-Fi](/skypeforbusiness/certification/plan-wifi).<br><br>**Pilote sans fil**: Assurez-vous que les pilotes sans fil sont à jour. Cela permet de réduire les problèmes d’utilisation médiocres liés à un pilote obsolète. Beaucoup d’organisations n’incluent pas de pilotes sans fil dans leurs cycles de correctifs, et ces pilotes peuvent être dépourvus d’une année. De nombreux problèmes sans fil sont résolus en s’assurant que les pilotes sans fil sont à jour.<br><br>**WMM**: les extensions multimédias sans fil (WMM), également appelées multimédia Wi-Fi, fournissent des fonctionnalités QoS de base aux réseaux sans fil. Les réseaux sans fil modernes doivent prendre en charge un grand nombre d’appareils. Ces appareils font concurrence de la bande passante et peuvent entraîner des problèmes de qualité pour les services VoIP, où la vitesse et la latence sont vitales. Pour obtenir des détails spécifiques sur votre fabricant sans fil et envisager d’implémenter WMM sur votre réseau sans fil, vous pouvez définir les priorités de Skype entreprise et de teams.<br><br>**Densité de points d’accès**: les points d’accès peuvent être trop éloignés ou ne pas se trouver dans un emplacement idéal. Pour réduire les interférences potentielles, placez des points d’accès supplémentaires dans des salles de conférence et dans des emplacements qui ne sont pas obstrués par des murs ou d’autres objets pour lesquels le signal Wi-Fi est faible.<br><br>**2,4 GHz et 5 GHz**: 5 GHz fournit moins d’interférences en arrière-plan et des débits plus élevés, et devraient être classés par priorité lors du déploiement de VoIP via Wi-Fi. Toutefois, les 5 GHz ne sont pas aussi puissants qu' 2,4 GHz et ne pénètrent pas facilement dans les murs. Passez en revue votre mode de construction pour déterminer la fréquence de votre choix pour la meilleure connexion. |
|**Périphérique réseau** | Les grandes organisations peuvent avoir des centaines d’appareils répartis sur le réseau. Travaillez avec votre équipe réseau pour vous assurer que les appareils réseau de l’utilisateur sur Internet sont gérés et à jour. |
| **VPN**  | Les appareils VPN ne sont généralement pas conçus pour gérer les charges de travail multimédia en temps réel. Certaines configurations VPN empêchent l’utilisation d’UDP (qui est le protocole préféré pour les médias) et ne dépendent que de TCP. Envisagez d’implémenter une solution VPN Split-tunnel pour réduire la qualité du réseau VPN en tant que source de médiocre qualité. |
| **Clients** <br>(Skype entreprise Online uniquement) | Assurez-vous que tous les clients sont mis à jour régulièrement. |
| **Appareils** | Si les appareils sont à l’origine de problèmes de qualité d’appel, envisagez de mettre à jour des périphériques posant problème. Pour en savoir plus, voir [téléphones pour les équipes](phones-for-teams.md) . |
| **Pilote** | Les correctifs de connexion réseau (Ethernet et Wi-Fi), d’audio, de vidéo et de pilotes USB doivent faire partie intégrante de votre stratégie de gestion de correctif globale. De nombreux problèmes de qualité sont résolus en mettant à jour les pilotes. |
| **Salles de réunion en Wi-Fi** | Nous vous recommandons vivement de se connecter au réseau en utilisant au moins une connexion Ethernet 1 Gbit/s. Les appareils de salle de réunion incluent généralement plusieurs flux audio et vidéo, ainsi que le contenu de la réunion, comme le partage d’écran, et présentent des exigences réseau plus élevées que d’autres équipes ou points de terminaison Skype entreprise. Les salles de réunion sont, par définition, des appareils fixes pour lesquels le Wi-Fi ne donne droit qu’au moment de l’installation.<br><br>Les salles de réunion doivent être traitées sans souci et attention pour garantir que l’utilisation de ces appareils est soumise à des attentes. Les problèmes de qualité liés aux salles de réunion seront généralement réaffectés rapidement, car ils sont souvent utilisés par des employés de niveau supérieur.<br><br>Le niveau de performance du Wi-Fi est souvent inférieur à celui d’une connexion câblée. Grâce à l’augmentation des politiques « mettre en place vos propres périphériques » et à la prolifération des ordinateurs portables, les points d’accès Wi-Fi sont souvent plus sollicités. Le contenu multimédia en temps réel peut ne pas être classé sur les réseaux Wi-Fi, ce qui peut entraîner des problèmes de qualité en temps réel. Cette utilisation intensive peut coïncider avec une réunion dans laquelle il peut y avoir une douzaine de personnes à la fois, chacune avec leur propre ordinateur portable et votre smartphone, connectées au même point d’accès Wi-Fi que l’appareil de salle de réunion.<br><br>Le Wi-Fi ne doit être considéré comme une solution temporaire que pour une installation mobile ou lorsque le Wi-Fi a été correctement configuré pour prendre en charge des contenus multimédias professionnels en temps réel. |


### <a name="tcp"></a>TCP 

Le protocole TCP (Transmission Control Protocol) est considéré comme un transport de restauration automatique et non par le transport principal que vous voulez pour le média en temps réel. La raison pour laquelle il s’agit d’un transport de restauration automatique est due à la nature dynamique du protocole TCP. Par exemple, si un appel est effectué sur une connexion réseau latente et que les paquets multimédias sont retardés, il y a plus de quelques secondes (qui n’ont plus besoin de la bande passante pour accéder au destinataire), ce qui peut compliquer le problème. Ainsi, le son de la fonction de correction audio et le son s’étirent, ce qui engendre des artefacts audibles, souvent sous la forme d’un scintillement.

Les rapports de cette section ne font pas de distinction entre les flux Good et médiocre. Dans la plupart des cas, il est préférable d’utiliser le protocole TCP pour le partage d’écran vidéo et audio (VBSS). Des débits de flux médiocres permettent de comparer la qualité UDP et la qualité TCP, afin que vous puissiez vous concentrer sur la meilleure qualité de vos efforts. L’utilisation de TCP est principalement causée par des règles de pare-feu incomplètes. Pour plus d’informations sur les règles de pare-feu pour les équipes et Skype entreprise Online, voir les [URL et plages d’adresses IP de Microsoft 365 et Office 365](https://aka.ms/o365ips).

> [!Note]
> Les éléments audio, vidéo et VBSS sont tous préférés du protocole UDP comme transport principal. La charge de travail de partage d’application RDP héritée utilise uniquement TCP.

#### <a name="tcp-usage"></a>Utilisation de TCP

Les rapports TCP indiquent l’utilisation globale du protocole TCP au cours des sept derniers mois. Dans cette section, tous les rapports supplémentaires visent à affiner les bâtiments et sous-réseaux spécifiques pour lesquels TCP est le plus souvent utilisé. Des rapports distincts sont disponibles pour les conférences et les flux à deux parties.

![Graphique illustrant le pourcentage de flux audio qui utilise TCP](media/qerguide-image-audiostreamswithtcp.png)

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

##### <a name="analysis"></a>Étude

Même si vous souhaitez que l’utilisation de TCP soit aussi faible que possible, il est possible que vous rencontriez un peu d’utilisation de TCP dans le cadre d’un déploiement sain. TCP en soi ne contribue pas à un mauvais appel, de sorte que des tarifs de flux sont fournis pour vous aider à déterminer si l’utilisation de TCP est un contributeur de médiocre qualité. 

#### <a name="tcp-investigations"></a>Examens TCP

Dans les modèles bord fournis, naviguez jusqu’aux flux TCP en construisant et en utilisant un rapport de sous-réseau via le modèle réseaux gérés ou tous les réseaux. Dans le cadre de l’examen de l’utilisation de TCP, le processus est le même, c’est pourquoi nous allons nous concentrer sur les conférences.


##### <a name="remediation"></a>Remediation

Ce rapport identifie les bâtiments et sous-réseaux spécifiques qui contribuent au volume de l’utilisation du protocole TCP. Un rapport supplémentaire est également fourni pour identifier l’adresse IP Microsoft Relay utilisée dans l’appel afin d’isoler les règles de pare-feu manquantes. Concentrez vos efforts de correction sur les bâtiments qui présentent le volume le plus élevé de flux TCP pour optimiser l’impact.

La cause la plus fréquente de l’utilisation du protocole TCP est l’absence de règles d’exception dans les pare-feu ou les proxys. Nous parlerons des proxys dans la section suivante, donc pour mettre au point vos efforts sur les pare-feu. En utilisant le bâtiment ou le sous-réseau fourni, vous pouvez déterminer le pare-feu qui doit être mis à jour.

| Remediation        | Aide     |
|--------------------|--------------------------------------|
| Configuration du pare-feu | Vérifiez que les [adresses IP de Microsoft 365 ou Office 365](https://aka.ms/o365ips) sont exclues de votre pare-feu. Pour les problèmes TCP liés aux médias, concentrez-vous sur les points suivants :<ul><li>Vérifiez que les sous-réseaux multimédias du client 13.107.64.0/18 et 52.112.0.0/14 se trouvent dans les règles de pare-feu.</li><li>Ports UDP 3478 – 3481 sont les ports multimédias requis et doivent être ouverts, sinon le client bascule à nouveau vers le port 443.</li></ul> |
| Vérifier             | Utilisez l' [outil Microsoft Network Assessment](https://www.microsoft.com/download/details.aspx?id=53885) pour vérifier les problèmes liés à la connectivité à des adresses IP Microsoft 365 ou Office 365 spécifiques et aux ports du bâtiment ou du sous-réseau concernés.    |

### <a name="http-proxy"></a>Proxy HTTP

Les proxys HTTP ne sont pas le chemin préféré pour établir des sessions multimédias pour différentes raisons. Beaucoup contiennent des fonctionnalités d’inspection de paquets complètes qui peuvent empêcher la fin des connexions au service et provoquer des interruptions. De plus, la plupart des serveurs proxy forcent le protocole TCP plutôt que d’autoriser le protocole UDP, ce qui est recommandé pour une qualité audio optimale.

Nous vous recommandons de configurer le client pour vous connecter directement aux équipes et aux services Skype entreprise. Ceci est particulièrement important pour le trafic multimédia.


> [!IMPORTANT]
> Nous vous recommandons de charger un [fichier de construction valide](CQD-upload-tenant-building-data.md) pour pouvoir faire la distinction entre les flux audio extérieurs lors de l’analyse de l’utilisation du proxy. 


#### <a name="http-proxy-usage"></a>Utilisation du proxy HTTP

Le rapport de flux proxy HTTP dans cette section du modèle ressemble beaucoup au rapport TCP. Il ne s’agit pas de savoir si les appels sont médiocres ou efficaces, mais si l’appel est connecté via HTTP.

![Capture d’écran du rapport de flux audio qui utilise HTTP](media/qerguide-image-audiostreamswithhttp.png)

##### <a name="analysis"></a>Étude

Vous voulez voir autant de flux multimédia HTTP que possible. Si des flux traversent votre proxy, consultez votre équipe réseau pour vous assurer que les exclusions appropriées sont en place afin que les clients effectuent un routage direct vers teams ou des sous-réseaux multimédias Skype entreprise online.

Si votre organisation ne comporte qu’un seul proxy Internet, vérifiez les [URL d’URL et de plages d’adresses IP appropriées Microsoft 365 ou Office 365](https://aka.ms/o365ips). S’il existe plusieurs proxy Internet au sein de votre organisation, utilisez le sous-rapport HTTP pour isoler le bâtiment ou le sous-réseau concerné.

S’il s’agit d’organisations qui ne peuvent pas ignorer le proxy, assurez-vous que le client Skype entreprise est configuré de manière à se connecter correctement lorsqu’il se trouve derrière un proxy, comme indiqué dans l’article [Skype entreprise doit utiliser un serveur proxy pour se connecter au lieu d’essayer une connexion directe](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin). 


#### <a name="http-proxy-investigations"></a>Examens du proxy HTTP

Ce rapport identifie les bâtiments et sous-réseaux spécifiques qui participent à l’utilisation de HTTP.


##### <a name="remediation"></a>Remediation

Nous vous [recommandons](proxy-servers-for-skype-for-business-online.md) de toujours ignorer les proxys pour Skype entreprise et équipes, en particulier le trafic multimédia. Les proxys ne permettent pas de sécuriser Skype entreprise, car son trafic est déjà crypté. Des problèmes de performances peuvent s'introduire dans l'environnement par le biais de la latence et la perte de paquets. Des problèmes tels que ceux-ci entraînent une utilisation négative du son, de la vidéo et du partage d’écran, où les flux en temps réel sont essentiels.

La cause la plus fréquente de l’utilisation de HTTP est le manque de règles d’exception dans les proxys. En utilisant le bâtiment ou le sous-réseau fourni, vous pouvez déterminer rapidement quel proxy doit être configuré pour la dérivation multimédia.

Vérifiez que les noms de [domaine complets Microsoft 365 ou Office 365](https://aka.ms/o365ips) requis sont autorisés dans votre proxy.

## <a name="endpoint-investigations"></a>Investigations de points de terminaison

Cette section est axée sur les tâches de création de rapports sur les versions du client et l’utilisation des appareils certifiés. Les rapports peuvent être utilisés en mode plan pour les versions de client, le type de client, les périphériques de capture et les pilotes (microphone), les appareils de capture vidéo, les versions de pilotes et de fournisseurs Wi-Fi.

> [!NOTE]
> Tous les rapports inclus dans les modèles ne sont pas abordés dans cet article. Toutefois, les méthodes de vérification décrites ci-dessous s’appliquent. Pour plus d’informations, reportez-vous à la description du rapport individuel.

### <a name="client-versions"></a>Versions de client

Ce rapport se focalise sur l’identification des versions du client Skype entreprise en cours d’utilisation et leur volume relatif dans l’environnement.

> [!IMPORTANT]
> Pour l’instant, les clients teams sont répartis et mis à jour automatiquement via le réseau de distribution de contenu Azure et sont tenus à jour par le service. Par conséquent, vous n’avez pas besoin de surveiller les versions du client Teams (sauf si vous désactivez la mise à jour automatique, ce que nous ne recommandons pas).

Les rapports de points de terminaison fédérés incluent les données de télémétrie clientes. Pour exclure des points de terminaison fédérés, vous devez ajouter un filtre de requête pour le second ID de client défini sur l' [ID de client](CQD-data-and-reports.md#how-to-find-your-tenant-id)de votre organisation. Vous pouvez également utiliser un filtre d' [URL](CQD-data-and-reports.md#url-filters) pour exclure la télémétrie de participants fédérés.



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

-   [Informations de publication des mises à jour apportées aux applications Microsoft 365](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)
-   [Historique des mises à jour pour les applications Microsoft 365 pour les entreprises](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date)
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
> Les rapports de points de terminaison fédérés incluent les données de télémétrie clientes. Pour exclure des points de terminaison fédérés, vous devez ajouter un filtre de requête pour le **second ID de client** défini sur l' [ID de client](CQD-data-and-reports.md#how-to-find-your-tenant-id)de votre organisation. Vous pouvez également utiliser un filtre d' [URL](CQD-data-and-reports.md#url-filters) pour exclure la télémétrie de participants fédérés.


> [!Note]
> Vous remarquerez peut-être lors de l’affichage du rapport que vous voyez le même appareil signalé plusieurs fois. Ce problème est dû au fait que l’appareil est signalé comme étant signalé à bord. Les différences dans les paramètres régionaux du matériel et du système d’exploitation entraînent des différences dans la façon dont les données d’appareil sont communiquées.

##### <a name="remediation"></a>Remediation

En règle générale, vous devez découvrir et sortir des appareils non certifiés et les remplacer par des appareils certifiés. Voici quelques éléments à prendre en compte lors de l’examen des rapports d’appareil :

-   Les appareils utilisent-ils une certification pour teams et Skype entreprise ? 
-   Vous pouvez identifier les utilisateurs d’un appareil spécifique en utilisant une [analyse d’appel par utilisateur](use-call-analytics-to-troubleshoot-poor-call-quality.md). Assurez-vous qu’ils disposent des pilotes les plus récents et qu’ils ne sont pas connectés par le biais d’un concentrateur ou d’une station d’accueil USB. 
-   Combien de versions différentes de différents pilotes sont utilisées ? Le correctif est-il régulier ? Pour garantir que les pilotes audio et vidéo, ainsi que les pilotes Wi-Fi, nous vous aiderons à éliminer ces problèmes en tant que source de problèmes de qualité et à optimiser l’utilisation de l’utilisateur.

##### <a name="audio"></a>Audio

La tâche suivante consiste à déterminer l’utilisation globale des [périphériques audio certifiés](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs). Nous vous recommandons d’utiliser un périphérique audio certifié pour un minimum de 80% de tous les flux audio. Pour effectuer cette opération, exportez le rapport sur les périphériques microphone dans Excel pour calculer l’utilisation des appareils certifiés ou approuvés. En règle générale, les organisations conservent la liste de tous les appareils approuvés, de sorte que le filtrage et le tri des données doivent être simples.

##### <a name="video"></a>Vidéo

Il est important de mettre à jour les pilotes vidéo. Le fait de veiller à ce que les cartes vidéo soient régulièrement corrigées permet d’exclure les pilotes vidéo en tant que source de médiocre qualité des flux vidéo. L’utilisation de [périphériques vidéo certifiés](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) permet d’assurer une utilisation lisse et de qualité de l’utilisateur. Les appareils vidéo qui prennent en charge le codage natif H. 264 sont préférés pour réduire l’utilisation de l’UC lors des conférences vidéo.

##### <a name="wi-fi"></a>Wi-Fi

Les pilotes Wi-Fi doivent également être corrigés en une cadence normale et être inclus dans la stratégie de gestion des correctifs. De nombreux problèmes de qualité peuvent être corrigés en gérant les pilotes Wi-Fi à jour. Pour plus d’informations sur l’optimisation de votre infrastructure Wi-Fi, voir [cet article sur la planification Wi-Fi](/skypeforbusiness/certification/networking-wifi).


## <a name="related-topics"></a>Voir aussi

[Utiliser le conseiller pour les équipes](use-advisor-teams-roll-out.md)

[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)

[Principes de connectivité réseau d’Office 365](https://aka.ms/pnc)

[Analyses et rapports Teams](teams-analytics-and-reports/teams-reporting-reference.md)

[Gérer vos périphériques dans Teams](device-management.md)

[Améliorer et surveiller la qualité des appels pour teams](monitor-call-quality-qos.md)

[Qu’est-ce que bord ?](CQD-what-is-call-quality-dashboard.md)

[Configurer le tableau de bord de qualité des appels (bord)](turning-on-and-using-call-quality-dashboard.md)

[Télécharger le client et générer des données](CQD-upload-tenant-building-data.md)

[Rapports et données bord](CQD-data-and-reports.md)

[Dimensions et mesures disponibles dans bord](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification des flux dans bord](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser des données de bord](CQD-Power-BI-query-templates.md)
