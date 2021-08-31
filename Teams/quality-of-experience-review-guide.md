---
title: Utiliser le CQD pour gérer les appels et la qualité des réunions dans Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies, gageames
audience: admin
description: Découvrez comment analyser et gérer les performances multimédias en temps réel dans Microsoft Teams à l’aide du tableau de bord de qualité des appels.
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
ms.openlocfilehash: 8f9ea93f972f542adb743f0dba066e703358912d
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732303"
---
#  <a name="use-cqd-to-manage-call-and-meeting-quality-in-microsoft-teams"></a>Utiliser le CQD pour gérer les appels et la qualité des réunions dans Microsoft Teams 

Cet article vous aide, en tant qu’administrateur ou support technique Teams, à développer un processus de surveillance et de maintenance des appels et de la qualité des réunions pour votre organisation à l’aide du tableau de bord de qualité des appels d’Microsoft Teams. Nos recommandations mettent l’accent sur les scénarios de qualité audio, car les améliorations que vous a apportées au réseau en matière d’amélioration de l’expérience audio se traduit par des améliorations en matière de vidéo et de partage.

Les deux [modèles organisés de DQD](https://aka.ms/QERtemplates) sont clés pour ces conseils. Nous vous recommandons de les télécharger avant de passer en revue les instructions de cet article.

Cet article part du principe que vous avez déjà [installé le CQD.](turning-on-and-using-call-quality-dashboard.md)


## <a name="categories-to-monitor-and-maintain"></a>Catégories à surveiller et à gérer

Une fois que vous avez déployé les réunions et la voix sur Teams, vous avez besoin d’un plan de surveillance et de maintenance continus. Ainsi, vous vous assurerez que Teams fonctionne toujours de façon optimale. Ce plan doit inclure les principaux domaines répertoriés ci-dessous. Vous devez également établir des objectifs pour les mesures de qualité et établir un plan de résolution et d’isolement des problèmes lorsqu’ils se produisent.

<table>
<thead>
<tr class="header">
<th>Catégorie</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Qualité de l’appel</strong></td>
<td>
<p>Décomposez les mesures par appels internes (au sein de votre organisation, tels que VPN, WiFi, câblés) ou appels externes</p>
<p>Décomposer les mesures en bâtiment ou en réseau</p>
<p>Appels VPN</p>
<p>Appels à l’aide de protocole TCP, UDP ou proxy</p>
</td>
</tr>
<tr class="even">
<td><strong>Fiabilité des appels</strong></td>
<td><p>Identifier et corriger les problèmes de réseau ou de pare-feu</p>
<p>Obtenir des informations sur les pourcentages de configuration d’appel et d’échecs de chute</p>
<p>Découvrez où se produisent la majorité des échecs de configuration et de chute d’appel</p>
</td>
</tr>
<tr class="odd">
<td><strong>Enquête sur les utilisateurs</strong></td>
<td>
<p>Utiliser les données Évaluer mon appel pour en savoir plus sur l’expérience réelle des utilisateurs</p>
<p>Où se produisent les expériences médiocres ?</p>
<p>Corréler la mauvaise expérience avec la qualité, la fiabilité et les périphériques des appels</p>
</td>
</tr>
<tr class="even">
<td><strong>Appareils</strong></td>
<td><p>Découvrez les micros et haut-parleurs les plus utilisés et leur impact sur la qualité des appels</p>
<p>Les pilotes audio, vidéo, USB et WiFi de prise en charge sont-ils régulièrement mis à jour ?</p>
</td>
</tr>
<tr class="odd">
<td><strong>Clients</strong></td>
<td>
<p>Découvrez les types et versions des clients utilisés et leur impact sur la qualité et la fiabilité des appels  </p>
</ol></td>
</tr>
</tbody>
</table>

En evaluant et en réstant les points décrits dans cet article, vous pouvez réduire leur risque d’affecter négativement vos utilisateurs. La plupart des problèmes liés aux utilisateurs peuvent être regroupés dans les catégories suivantes :

-   Configuration incomplète du pare-feu ou du proxy
-   Faible couverture Wi-Fi
-   Bande passante insuffisante
-   VPN
-   Versions clientes et pilotes incohérents ou obsolètes
-   Appareils audio non dostés ou intégrés
-   Sous-réseaux ou périphériques réseau problématiques

Par le biais d’une planification et d’une conception adéquates avant de déployer Teams ou Skype Entreprise Online, vous pouvez réduire la quantité d’efforts nécessaires pour assurer une expérience de haute qualité.

Cet article se concentre sur l’utilisation du tableau de bord de qualité des appels en ligne comme principal outil pour signaler et examiner chaque zone, avec une accentuation particulière sur l’audio pour optimiser l’adoption et l’impact. Toute amélioration apportée au réseau pour améliorer l’expérience audio se traduit également directement par des améliorations en matière de partage de vidéo et de bureau.

Pour accélérer votre évaluation, deux modèles de nom de la recherche de contenu [organisés](https://aka.ms/qertemplates) sont fournis : un pour la gestion de tous les réseaux et l’autre pour les réseaux gérés (internes) uniquement. Bien que les rapports de modèle Tous les réseaux soient configurés pour afficher les informations de bâtiment et de réseau, ils peuvent toujours être utilisés pendant que vous collectez et téléchargez des informations de bâtiment. Le chargement des informations de bâtiment dans le CQD permet au service d’améliorer la création de rapports en ajoutant des informations de bâtiment, de réseau et d’emplacement personnalisées tout en différencient les sous-réseaux internes des sous-réseaux externes. Pour plus d’informations, lisez [Mappage des bâtiments.](CQD-building-mapping.md)

### <a name="intended-audience"></a>Public cible

Cet article est destiné aux partenaires et aux parties prenantes ayant des rôles tels que Responsable de collaboration, Consultant, Spécialiste de la gestion des changements/Adoption, Responsable de support/Support technique, Responsable réseau, Responsable de bureau et Administrateur informatique.

Cet article est également destiné à être utilisé par le ou les champions de qualité désignés. Pour plus d’informations, [voir le rôle Champion de la qualité.](4-envision-plan-my-service-management.md#the-quality-champion-role)


## <a name="what-is-quality"></a>Qu’est-ce que la qualité ?

Dans ce contexte, la qualité est un ensemble de mesures de service et d’expérience utilisateur.


### <a name="service-metrics"></a>Mesures de service

Les mesures de service se composent de mesures spécifiques basées sur le client. Pendant chaque appel, le client recueille des données de télémétrie pour l’appel et envoie un rapport à la fin de chaque appel, qui est accessible par la suite dans le CQD ou dans l’analyse des appels par [utilisateur.](set-up-call-analytics.md) Ces mesures sont les suivantes (sans s’y limiter) :

-   Poor Stream (entrant et sortant)
-   Taux d’échec de l’installation
-   Drop Failure Rate


#### <a name="poor-stream-rate"></a>Taux de flux médiocre

Le taux de flux médiocre (PSR) représente le pourcentage global de flux de l’organisation qui ont une qualité médiocre. Cette mesure est destinée à mettre en évidence les aspects sur lesquels votre organisation peut concentrer [](#managed-versus-unmanaged-networks) ses efforts afin d’avoir le plus fort impact sur la réduction de cette valeur et l’amélioration de l’expérience utilisateur. C’est pourquoi les réseaux gérés sont l’objet principal de la recherche de LSP. Les utilisateurs externes sont également importants, mais les examens diffèrent au niveau de l’organisation. Envisagez de fournir des meilleures pratiques pour les utilisateurs externes et d’étudier les appels externes indépendamment de l’ensemble de l’organisation.

La mesure réelle dans le CQD varie selon la charge de travail, mais pour les besoins de cet article, nous nous concentrons principalement sur la mesure _Audio Poor Percentage._ PSR est composé des cinq moyennes métriques réseau décrites dans le tableau suivant. Pour qu’un flux soit classé comme médiocre, une seule métrique doit dépasser le seuil défini. Le CQD fournit la qualité de l’offre « Poor Due To... » pour mieux comprendre la condition à l’origine de la classé comme médiocre du flux. Pour en savoir plus, [lisez classification des flux dans le CQD.](stream-classification-in-call-quality-dashboard.md)

> [!Note]
> Le CQD fournit la qualité de l’offre « Médiocre en raison... » pour mieux comprendre la condition à l’origine de la classé comme médiocre du flux.


##### <a name="audio-poor-quality-metrics"></a>Mesures de qualité audio médiocre

| Moyenne métrique     | Description     | Expérience utilisateur |
|-------------|-----------------|-----------------|
| Jitter \> 30 ms        | Il s’agit de la variation moyenne de délai entre les paquets successifs. Teams et les Skype Entreprise peuvent s’adapter à certains niveaux de gigue à l’grâce à la mise en mémoire tampon. C’est seulement lorsque la gigue est supérieure au tampon qu’un participant constate une gigue.      | Les paquets qui arrivent à des vitesses différentes entraînent l’arrivée de sons dans la voix d’un haut-parleur.   |
| Taux de perte de \> paquets de 10 % ou 0,1        | Souvent défini comme le pourcentage de paquets perdus. La perte de paquets affecte directement la qualité audio, de petits paquets individuels perdus qui n’ont pratiquement pas d’impact sur les pertes en rafale dos-à-dos qui entraînent une coupure complète de l’audio.     | Les paquets sont supprimés et n’arrivent pas à leur destination prévue cause des décalages dans les médias, ce qui entraîne des syllabes et des mots manqués, ainsi que de la vidéo et du partage hachés. |
| Durée de \> l’aller-retour : 500 ms        | Il s’agit du temps qu’il faut pour obtenir un paquet IP de point A à point B, puis de nouveau à point A. Ce retard de propagation sur le réseau est lié à la distance physique entre les deux points et la vitesse de la lumière, et inclut une surcharge supplémentaire prise par les différents appareils sur le chemin réseau.      | Les paquets dont l’arrivée à destination prend trop de temps entraînent un effet de walkie-talkie.   |
| Moyenne de dégradation de NMOS \> 1,0         | Dégradation [moyenne de la note moyenne d’opinion réseau (NMOS)](/previous-versions/office/communications-server/bb894481(v=office.12)#network-mos) pour le flux. Représente l’impact de la perte et de la gigue réseau sur la qualité de l’audio reçu qui a entraîné une baisse de plus d’un point de la qualité de l’audio reçu. | Il s’agit d’une combinaison de gigue, de perte de paquets et, dans un moindre degré, de durée des allers-retours accrues. L’utilisateur peut être confronté à une combinaison de ces symptômes.   |
| Proportion moyenne d’échantillons masqués \> de 7 % ou 0,07 | Rapport moyen du nombre de trames audio avec échantillons masqués générés par la perte de paquets par rapport au nombre total de trames audio. Un échantillon audio masqué est une technique permettant de lisser la transition en transition, généralement provoquée par la perte de paquets réseau.      | Les valeurs élevées indiquent que des niveaux importants de cache de perte ont été appliqués et se sont élevés dans l’audio déformé ou perdu.     |

##### <a name="why-do-we-prefer-to-use-streams-instead-of-calls"></a>Pourquoi préférons-nous utiliser des flux au lieu des appels ?

Flux-nous savoir quelle partie spécifique de l’appel a été médiocre ( sortant ou entrant). Lorsque vous avez des données d’analyse des appels pour un appel médiocre, déterminez si l’appel médiocre est dû au flux de cet appelant (sortant) ou au flux de l’appelant (entrant). Il est encore plus important de déterminer quel flux a une incidence sur la qualité des appels pour les conférences. Si vous consultez uniquement les données des appels, vous pouvez voir le nombre de conférences pour lesquelles une personne participe, mais vous ne voyez pas les personnes qui sont des intervenants actifs, ce qui permet d’partager le plus d’écran.

Les données d’appel vous donnent des mesures d’utilisation, mais ne vous mènent pas nécessairement à la cause première d’une mauvaise qualité des appels. En regardant l’orientation du flux, vous pouvez identifier des facteurs tels qu’un appel qui ne se passe pas sur un réseau géré, un appel d’un non-employé (par exemple, un fournisseur ou une personne sur un autre réseau). Dans ce cas, si la connexion réseau de l’autre personne était médiocre, l’appel entier est marqué comme médiocre. Comme vous ne pouvez rien faire sur les facteurs externes, ces données ne sont pas utiles.

La direction du flux peut également vous aider à identifier les appareils ou clients problématiques.

 - Par exemple, si vous avez un budget limité pour les appareils et que vous souhaitez fournir des périphériques uniquement aux utilisateurs audio importants, utilisez le rapport d’utilisation audio (VoIP) et filtrez les flux sortants et les conférences. Recherchez les utilisateurs audio en volume élevé qui parlent dans des micros intégrés. Ceux-ci peuvent être en corrélation avec une qualité d’appel moins élevée (et vous souhaitez peut-être fournir des périphériques audio à ces personnes). Pour une plus grande clarté, vous pouvez filtrer l’utilisation des paquets, ce qui vous permettra de cibler particulièrement les utilisateurs audio à volume élevé. 

  - Un autre exemple implique le partage d’écran. Si un client utilise un ancien client Teams client, les performances du partage d’écran peuvent être affectées. Vous pouvez résoudre ce problème en hiérérisant les mises à niveau des clients pour les personnes qui partagent beaucoup d’écran.

 - En identifiant la direction d’un flux qui est à l’origine d’un problème de qualité d’appel, vous pouvez déterminer si vous avez un problème lié à la qualité de service ou à la bande passante. Si vous n’avez pas entièrement implémenté QoS, ou si vous marquez uniquement les paquets sur le client et non au flux entrant, vous risquez de constater une moins bonne qualité des appels. En regardant la direction du flux, vous pouvez obtenir une vue plus précise de la perte de paquets, de la latence ou de la gigue dans une direction spécifique. 

   - Par exemple, imaginons qu’un utilisateur se plaignent d’un son tandis que son est câblé (gigue). En regardant le flux et la direction, vous pouvez déterminer que le problème se produit sur le flux entrant, uniquement pour un ensemble spécifique de sous-réseaux. Une fois que vous avez communiqué ces informations à votre équipe en réseau, celle-ci peut la suivre jusqu’à un accélérateur WAN mal configuré qui n’a pas contourné le trafic de médias. Une fois que l’équipe réseau reconfigure l’accélérateur WAN, la gigue disparaît et la qualité des appels s’améliore. 


#### <a name="setup-failure-rate"></a>Taux d’échec de l’installation

Le taux d’échec de  configuration, également connu sous le nom de mesure du pourcentage d’échec de configuration de l’appel total dans le réseau de qualité des appels, est le nombre de flux pour lequel le chemin de médias n’a pas pu être établi entre les points de terminaison au début de l’appel.

Il s’agit d’un flux multimédia qui n’a pas pu être établi. Étant donné la gravité de l’impact de ce problème sur l’expérience utilisateur, l’objectif est de réduire cette valeur à zéro autant que possible. Une valeur élevée pour cette mesure est plus courante dans les nouveaux déploiements avec des règles de pare-feu incomplètes qu’un déploiement mature, mais il reste important de le suivre régulièrement.

Cette mesure est calculée en prenant le nombre total de flux qui n’ont pas réussi à être divisés par le nombre total de flux qui ont soumis un enregistrement de détails d’appel réussi :

-   **Setup Failure Rate** = Total Call Setup Failed Stream Count / Total CDR Available Stream Count

#### <a name="drop-failure-rate"></a>Drop Failure Rate

Le taux d’échec de  l’appel, également connu sous le nom de mesure du pourcentage d’échecs d’appel total dans le réseau de qualité des appels, est le pourcentage de flux correctement établis pour lequel le chemin de médias ne s’est pas terminé correctement.

Il s’agit d’un flux multimédia qui s’est terminé de façon inattendue. Bien que l’impact de cela ne soit pas aussi grave qu’un flux qui a échoué à la mise en place, cela affecte toujours l’expérience utilisateur. Des chutes de média soudaines et fréquentes peuvent non seulement avoir un impact grave sur l’expérience utilisateur, mais aussi entraîner la nécessité pour les utilisateurs de se reconnecter, ce qui entraîne une perte de productivité (sans oublier la frustration).

La mesure est calculée en prenant le nombre total de flux supprimés divisé par le nombre total de flux correctement créés :

-   **Drop Failure Rate** = Total Call Dropped Stream Count / Total Call Setup Succeeded Stream Count

### <a name="define-your-target-metrics"></a>Définir les mesures cibles

Cette section décrit certains des principaux mesures de service que nous utilisons pour évaluer l’état d’état des services. En faisant continuellement des évaluation et en sous-tenez compte des efforts pour maintenir ces mesures en dessous des objectifs définis, vous vous assurerez que vos utilisateurs expériencent une qualité d’appel cohérente et fiable. Pour commencer, utilisez les cibles suggérées dans le tableau ci-dessous. Ajustez les objectifs selon les besoins pour atteindre vos objectifs.

<table>
<tr>
<th rowspan="2" colspan="2" valign="center">Type de réseau</th><th rowspan="1">Objectifs de qualité</th><th colspan="2">Objectifs de fiabilité</th></tr>
<tr><th>Audio Poor Stream Rate</th><th>Taux d’échec de l’installation</th><th>Drop Failure Rate</th></tr>
<tr><td rowspan="2"><strong>All</strong></td><td>Interne</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Global</td><td>3.0%</td><td>1.0%</td><td>3.0%</td></tr>
<tr><td rowspan="5"><strong>Conférence</strong></td><td>Interne</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Interne câblé</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Wi-Fi 5 GHz en interne</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Wi-Fi interne à 2,4 GHz</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Global</td><td>2.0%</td><td>0.5%</td><td>3.0%</td></tr>
<tr><td rowspan="4"><strong>P2P</strong></td><td>Interne</td><td>2.0%</td><td>0.5%</td><td>2.0%</td></tr>
<tr><td>Connexion câblé/Wi-Fi interne à 5 GHz</td><td>1.0%</td><td>0.5%</td><td>1.0%</td></tr>
<tr><td>Connexion câblé/Wi-Fi globale de 5 GHz</td><td>2.0%</td><td>1.0%</td><td>1.0%</td></tr>
<tr><td>Global</td><td>2.0%</td><td>1.0%</td><td>3.0%</td></tr>
</table>

### <a name="user-experience"></a>Expérience utilisateur

L’analyse de l’expérience utilisateur est plus une technique que la science, car les mesures recueillies ici ne signifient pas toujours qu’il y a un problème au niveau du réseau ou du service, mais elles indiquent simplement que l’utilisateur perçoive un problème. Le DQD comprend un mécanisme d’enquête intégré, rate My Call (RMC), qui permet d’évaluer l’expérience globale des utilisateurs. La gestion de la qualité des utilisateurs vous donne des informations sur les questions suivantes du point de vue de vos utilisateurs :

-   Est-ce que je sais comment utiliser la solution ?
-   La solution est-elle simple à utiliser et intuitive et prend-elle en charge mes besoins de communication quotidien ?
-   La solution m’aide-t-elle à faire mon travail ?
-   Quelle est ma vision globale de la solution ?
-   Puis-je utiliser la solution à tout moment, où que je me trouve ?
-   Puis-je configurer et gérer un appel ?

#### <a name="rate-my-call"></a>Évaluer mon appel 

La fréquence d’appel (RMC) est intégrée dans les Teams et Skype Entreprise. Elle apparaît automatiquement après un appel sur chaque 10 appels, ou 10 %. Cette courte enquête demande à l’utilisateur d’évaluer l’appel et de fournir un peu de contexte sur les raisons pour lesquelles la qualité de l’appel est médiocre. Une ou deux évaluation est considérée médiocre, trois à quatre est bonne et cinq est excellent. Bien qu’il s’agit un peu d’un indicateur lent, c’est une mesure utile pour découvrir des problèmes que les mesures de service peuvent manquer.

> [!Note]
> Facteur humain : les utilisateurs ignorent souvent l’enquête quand la qualité des appels est bonne et les remplissent quand la qualité de l’appel est mauvaise. Par conséquent, vos rapports RMC peuvent être asymétriques par rapport au côté médiocre, même si les mesures de service sont bonnes.

Vous pouvez utiliser le DQD pour signaler les réponses des utilisateurs de la chaîne de travail RMC. Des exemples de rapports sont inclus dans le modèle de de nom de la liste de bord. Toutefois, ils ne sont pas abordés en détail dans cet article. 

#### <a name="client-and-device-readiness"></a>Disponibilité du client et des appareils

Vous avez besoin d’une stratégie de client et d’appareil solide pour vous assurer que vos utilisateurs ont une expérience utilisateur cohérente et positive. Quelques principes clés pilotent chaque stratégie de préparation.

##### <a name="client-readiness"></a>Disponibilité du client

En maintenant Teams client à jour, vos utilisateurs sont toujours en mesure d’obtenir la meilleure expérience possible. Microsoft publie fréquemment des mises à jour du [client Teams](teams-client-update.md) (la mise à jour s’installe elle-même en arrière-plan, sauf si vous avez désactivé cette fonctionnalité , ce qui n’est pas recommandé). Il est également important de ne pas oublier de mettre à jour les pilotes réseau, vidéo, USB et audio, car ils sont souvent ignorés et peuvent affecter la qualité des appels et des réunions. Pensez à ajouter des pilotes réseau, Wi-Fi, vidéo, USB et audio à votre processus actuel de gestion des correctifs.


##### <a name="device-readiness"></a>Disponibilité de l’appareil

Aucune stratégie unique ne peut affecter l’expérience utilisateur plus que la stratégie de préparation de votre appareil. Par exemple, les utilisateurs qui utilisent leurs haut-parleurs et leur micro portables font souvent l’expérience d’un bruit de fond pendant les appels et les réunions. Teams est conçu pour fonctionner avec presque n’importe quel appareil, mais si vous avez des problèmes liés à l’appareil, consultez Téléphone pour [Teams.](./devices/phones-for-teams.md)


### <a name="categories-of-quality"></a>Catégories de qualité

Opérationnel un ensemble de pratiques de gestion de la qualité : vous offrez la meilleure chance d’avoir un appel et une qualité de réunion bonnes. Un bon plan de gestion de la qualité traite de ces catégories :

-   **Réseau :** Qualité audio axée sur la mesure Poor Stream Ratio (PSR), l’utilisation du protocole TCP, les sous-réseaux câblés et sans fil, et l’identification de l’utilisation des serveurs HTTP et vpn

-   **Points de terminaison :** Périphériques audio et clients à jour

-   **Gestion des services :** Cette catégorie comprend deux sections :

    -   Tout d’abord, Microsoft est responsable de la gestion et de la gestion des services Teams et Skype Entreprise Online.

    -   Les tâches que votre organisation gère ensuite pour garantir l’accès fiable au service, telles que la mise à jour des informations de bâtiment et la gestion des pare-feu pour les nouvelles adresses IP Office 365 au cours de l’ajout d’une infrastructure au service.

![Graph les catégories de qualité dans une organisation.](media/qerguide-image-categories.png "Catégories de qualité dans une organisation : gestion des services, points de terminaison et réseau.")

Examinez la liste des tâches recommandées pour maintenir la qualité. Vous devez effectuer ces tâches régulièrement, par exemple chaque semaine.

#### <a name="service-management-tasks"></a>Tâches de gestion des services

Ces tâches vont de la garantie qu’il y a suffisamment de bande passante pour accéder au service sans saturer les liens Internet, en validant que la qualité de service (QoS) est en place sur toutes les zones réseau gérées et en restant au fait des [plages](/microsoft-365/enterprise/urls-and-ip-address-ranges)d’adresses IP de Office 365 sur les pare-feu.

#### <a name="network-tasks"></a>Tâches réseau

Il existe deux catégories de tâches réseau : fiabilité et qualité. La fiabilité se concentre sur la mesure de la capacité de l’utilisateur à passer des appels et à rester connecté. La qualité se concentre sur la télémétrie agrégée envoyée à Teams et Skype Entreprise Online par le client de l’utilisateur pendant l’appel et une fois celui-ci terminé. 

Étant donné l’impact critique de la fiabilité sur l’expérience utilisateur, nous vous recommandons d’évaluer et d’examiner les mesures de fiabilité avant de plonger dans la qualité. 

#### <a name="endpoints-tasks"></a>Tâches des points de terminaison

La tâche principale dans cette catégorie supprime les obstacles aux mises à jour [Teams client.](teams-client-update.md) Par défaut, Teams est automatiquement mis à jour régulièrement (sauf si vous éteiez ce paramètre, ce que nous vous déconseillons). 

Vous devez également surveiller les appareils et fournir des mises à jour chaque fois que vous identifiez les problèmes liés à un appareil.

## <a name="use-cqd-to-manage-call-quality"></a>Utiliser le CQD pour gérer la qualité des appels

Une fois que vous avez installé le [CQD,](turning-on-and-using-call-quality-dashboard.md)vous pouvez commencer à l’utiliser pour gérer les appels et la qualité des réunions pour votre organisation.

La plupart des problèmes liés Teams performances de l’entreprise sont dans les catégories suivantes :

-   Configuration incomplète du pare-feu ou du proxy
-   Faible couverture Wi-Fi
-   Bande passante insuffisante
-   VPN
-   Versions clientes et pilotes incohérents ou obsolètes
-   Appareils audio non dostés ou intégrés
-   Sous-réseaux ou périphériques réseau problématiques

Si vous prenez le temps de déployer Teams afin d’évaluer ces domaines et de corriger les lacunes, vous réduisez la quantité d’efforts nécessaires pour maintenir une expérience de Teams de haute qualité pour tous vos utilisateurs. Pour obtenir de l’aide pour évaluer votre réseau en vue de la préparation de votre déploiement de Teams, lisez Conseiller pour [Teams](use-advisor-teams-roll-out.md) et Préparez votre réseau pour [Teams.](prepare-network.md)

### <a name="expectations-using-cqd"></a>Attentes à l’aide du CQD

Utilisez le tableau de bord de qualité des appels pour obtenir des informations sur la qualité des appels effectués à l’aide Teams et Skype Entreprise services. Le CQD est conçu pour aider les administrateurs de Teams et de Skype Entreprise et les ingénieurs réseau à optimiser le réseau et à surveiller de près la qualité, la fiabilité et l’expérience utilisateur. Le DQD examine la télémétrie agrégée pour l’ensemble d’une organisation, où les modèles globaux peuvent être visibles ; Cela vous permet d’effectuer des analyses éclairées et de planifier des corrections. Le CQD fournit des rapports sur des mesures qui fournissent des informations sur la qualité, la fiabilité et l’expérience utilisateur globales.

Bien qu’utile pour analyser les tendances et sous-réseaux, le CQD ne fournit pas toujours de raison spécifique pour un scénario donné. Il est important de comprendre ceci et de définir les attentes correctes lors de l’utilisation du CQD :

-   Le CQD ne fournit pas la cause première de chaque scénario
-   Le CQD ne contient pas de flux de Système téléphonique ou d’audioconférence
-   Le CQD appelle les zones à examen approfondie en fonction de tendances

### <a name="cqd-reports-overview"></a>Vue d’ensemble des rapports du tableau de situation

Utilisez le menu déroulant en haut de l’écran pour ouvrir un rapport. Pour obtenir la liste des données fournies dans chaque rapport, lisez Données disponibles dans les rapports [du CQD.](CQD-data-and-reports.md#data-available-in-cqd-reports)

Nouveautés de janvier 2020 : télécharger Power BI modèles de [requête pour le CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Modèles Power BI personnalisables que vous pouvez utiliser pour analyser et signaler vos données de CQD.


### <a name="teams-vs-skype-for-business"></a>Teams et Skype Entreprise

Le CQD peut prendre des rapports sur les Teams et les Skype Entreprise. Toutefois, il peut être possible que vous vouliez développer un rapport pour examiner Teams données de télémétrie distinctes Skype Entreprise.

#### <a name="summary-reports"></a>Rapports de synthèse

Pour modifier la page des rapports de synthèse afin de ne  rechercher que Teams ou Skype Entreprise, sélectionnez le menu déroulant Filtre de produit dans la partie supérieure de l’écran, puis sélectionnez le produit de votre choix.

![Capture d’écran du menu déroulant affichant les options de filtre.](media/qerguide-image-productfilter.png)

#### <a name="detailed-reports"></a>Rapports détaillés

Pour filtrer tous les rapports détaillés, dans la barre du navigateur, insérons les informations suivantes à la fin de l’URL :

```PowerShell
/filter/[AllStreams].[Is Teams]|[FALSE]
```

**Exemple :**

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-5/filter/[AllStreams].[Is Teams]|[FALSE]```

Pour plus d’informations sur les filtres d’URL, [lisez les rapports](CQD-data-and-reports.md#report-filters) de filtrage plus loin dans cette section.

Pour filtrer un rapport détaillé individuel, ajoutez le filtre au rapport et définissez-le ``Is Teams`` sur True ou False.

![Capture d’écran de la page Ajouter un filtre.](media/qerguide-image-addteamsfilter.png)

### <a name="managed-versus-unmanaged-networks"></a>Réseaux gérés et non gérés

Par défaut, tous les points de terminaison du même nom sont classés comme externes. Dès qu’un fichier de bâtiment est introduit, nous pouvons commencer à examiner les données de point de terminaison gérées. Comme mentionné précédemment, les réseaux du CQD sont définis comme :

-   Un _réseau géré,_ souvent appelé interne ou interne, peut être influencé et contrôlé par l’organisation. Cela inclut le LAN interne, le WAN distant et le VPN.
-   Un _réseau non_ contrôlé, souvent considéré comme externe ou externe, ne peut pas être influencé ni contrôlé par l’organisation. Un réseau nonmanaté est un réseau d’hôtel ou d’aéroports.

### <a name="dimensions-measures-and-filters"></a>Dimensions, mesures et filtres

Une requête de tableau de qualité des requêtes contient les trois paramètres suivants :

-   **Dimension :** Comment puis-je pivoter sur les données ?

-   **Mesure :** Ce sur quoi je souhaite faire rapport.

-   **Filtre :** Comment réduire le jeu de données que la requête renvoie.

Une autre manière d’examiner ceci est qu’une  _dimension_ est la fonction de regroupement, une mesure est les données qui m’intéressent, et un filtre consiste à restreindre les résultats à ceux qui sont pertinents pour ma requête. 

Par exemple, une requête de bonne qualité est **Show me Poor Flux [Measure] par Subnet [Dimension] for Building 6 [Filter].** Pour plus d’informations, [voir Dimensions et mesures disponibles dans le DQD.](./dimensions-and-measures-available-in-call-quality-dashboard.md)

### <a name="first-vs-second"></a>Premier et deuxième 

Bon nombre des dimensions et mesures du même nom sont classées comme première ou deuxième. Le CQD n’utilise pas les champs Appelant/Appelant  :  ceux-ci ont été renommés en premier et deuxième en raison d’étapes intermédiaires entre l’appelant et l’appelé. La logique suivante détermine quel point de terminaison impliqué est étiqueté comme premier :

-   **Le premier** sera toujours un point de terminaison serveur (serveur de conférence, serveur de médiation, etc.) si un serveur est impliqué dans le flux ou l’appel.

-   **Le deuxième** point de terminaison sera toujours un point de terminaison client, sauf si le flux est entre deux points de terminaison serveur.

-   Si les deux points de terminaison sont du même type, le choix de celui qui se trouve en premier est basé sur l’ordre interne de la catégorie de l’agent utilisateur. Cela garantit la cohérence de l'organisation.

Pour plus d’informations sur la détermination du premier ou du deuxième point de terminaison lorsqu’ils sont identiques, voir Dimensions et mesures disponibles dans le [DQD.](./dimensions-and-measures-available-in-call-quality-dashboard.md)

### <a name="stream-vs-call"></a>Diffuser et appeler

Vous devez comprendre la différence entre un appel et un flux pour choisir correctement les dimensions ou les mesures que vous regarderez dans le DQD. Bien que le DQD se concentre principalement sur les flux, les mesures basées sur les appels sont également disponibles.

-   **Flux :** Un _flux existe_ entre deux points de terminaison uniquement. Il n’y a qu’un flux pour chaque direction, et deux flux sont requis pour la communication. Flux sont utiles pour examiner des bâtiments, des réseaux ou des sous-réseaux. Dans certains cas, l’appel et le flux sont utilisés dans le nom de la mesure (par exemple, Call Setup Stream ou Call Dropped Stream). Ceux-ci sont toujours classés comme flux.

-   **Appel :** Un _appel est_ un regroupement de tous les flux de tous les participants. Un appel se compose, au minimum, de deux flux. Un seul appel aura au moins deux points de terminaison, chacun avec un flux au minimum.

Pour obtenir des instructions supplémentaires sur la référence d’un appel ou d’un flux par la dimension ou la mesure, voir Dimensions et mesures disponibles dans le [DQD](./dimensions-and-measures-available-in-call-quality-dashboard.md)

### <a name="good-poor-and-unclassified-calls"></a>Appels bons, médiocres et non classés

Un appel est classé comme bon, médiocre ou non classé. Prenons un moment pour discuter plus en détail de chacun d’eux.

-   **Bonne ou médiocre :** Un appel bon ou médiocre est constitué d’un appel qui contient un ensemble complet de mesures de service, pour lesquels un rapport QoE complet a été généré et reçu par le service. La détermination de l’état d’un flux est bonne ou médiocre est décrite [plus tôt dans cet article.](#poor-stream-rate)

-   **Non classé :** Un flux non classé ne contient pas un ensemble complet de mesures de service. Il peut s’agit de brefs appels (généralement moins de 60 secondes) où les moyennes n’ont pas pu être calculées et où un rapport QoE n’a pas été généré. La raison la plus fréquente des appels non classés est le fait qu’il y avait peu ou pas d’utilisation des paquets. À titre d’exemple, il peut s’agit d’un participant qui participe à une réunion en mode muet sans jamais parler. Le participant reçoit, mais n’en transmet pas, les médias. À moins que les médias ne soient transmis, aucun métrique n’est disponible pour le QQD afin de classifier le flux multimédia sortant du point de terminaison.

Pour en savoir plus, [lisez classification des flux dans le CQD.](stream-classification-in-call-quality-dashboard.md)

### <a name="common-subnets"></a>Sous-réseaux communs

Les sous-réseaux communs sont des sous-réseaux privés spécifiques utilisés par des hôtels, des réseaux sociaux, des points d’accès et des zones similaires. Ces sous-réseaux sont difficiles à trier en raison de leur utilisation courante. Si votre organisation utilise l’un de ces sous-réseaux courants, nous vous recommandons de déplacer ce réseau vers un autre sous-réseau. Cela facilitera la déclaration dans le DQD. Lorsque ces informations sont notées, les rapports du modèle Tous les réseaux ont été configurés pour exclure ces sous-réseaux et les éliminer comme source de mauvaise qualité. Sous-réseaux communs définis ci-dessous ; leur impact variera selon l’organisation.

-   10.0.0.0/24
-   192.168.0.0/24
-   192.168.1.0/24
-   192.168.2.0/24
-   172.20.10.0/24
-   192.168.43.0/24

Lorsque vous examinez un réseau géré qui utilise un sous-réseau commun, vous devez utiliser la dimension Second Reflexive Local IP pour grouper des sous-réseaux. Cette dimension contient l’adresse IP publique du point de terminaison.


## <a name="reliability-investigations"></a>Enquêtes de fiabilité

La première étape pour améliorer la qualité consiste à évaluer l’état de fiabilité dans l’ensemble de l’organisation. Étant donné que la fiabilité est essentielle pour une expérience utilisateur positive, nous commençons par les deux composants qui mesurent la fiabilité :

1.  **Échecs de configuration :** L’appel n’a pas pu être établi.

2.  **Échecs de chute :** L’appel a été établi et s’est terminé de manière inattendue.

Dans cette section, nous allons examiner les méthodes utilisées pour examiner ces deux aspects.

> [!NOTE]
> Tous les rapports inclus dans les modèles ne sont pas abordés dans cet article. Toutefois, les méthodes d’examen expliquées ci-dessous s’appliquent toujours. Pour plus d’informations, reportez-vous à la description individuelle du rapport.


### <a name="setup-failures"></a>Échecs de configuration

Privilégiez d’abord les erreurs de configuration corrective dans ce domaine, car ces échecs ont un impact négatif significatif sur l’expérience utilisateur.

Commencez votre examen en évaluez le pourcentage d’échecs globaux de configuration pour l’organisation, puis hiérarchisez les zones d’examen sur la base du pourcentage le plus élevé en fonction du bâtiment ou du réseau. 

#### <a name="setup-failure-trend-analysis"></a>Analyse de la tendance des échecs d’installation

Ce rapport indique le nombre total de flux, les échecs de configuration de flux et le taux d’échec de la configuration du flux. Pointer sur l’une des colonnes pour afficher ses valeurs individuelles. 

##### <a name="analysis"></a>Analyse

Ce rapport vous permet de répondre aux questions suivantes et de déterminer la suite de votre action :

-   Quel est le pourcentage total d’échecs de configuration d’appel pour le mois en cours ?

-   Le pourcentage d’échecs de configuration d’appel est-il inférieur ou supérieur à la mesure cible définie ?

-   La tendance d’échec est-elle pire ou meilleure que celle du mois précédent ?

-   La tendance d’échec est-elle croissante, stable ou décroissante ?

Quelles que soient les réponses à ces questions, prenez le temps d’examiner plus en détail les sous-rapports compagnons afin de rechercher les bâtiments ou sous-réseaux individuels qui peuvent avoir besoin d’une correction. Bien que le taux d’échec global puisse être inférieur à la mesure cible, les taux d’échec pour un ou plusieurs bâtiments ou réseaux peuvent être au-dessus de la mesure cible et faire l’objet d’examens.

#### <a name="setup-failure-investigations"></a>Configurer les enquêtes en cas d’échec 

Ce rapport de synthèse est utilisé pour découvrir et isoler les bâtiments ou réseaux qui peuvent avoir besoin d’une correction.

> [!NOTE]
> N’oubliez pas d’ajuster le filtre du rapport Month Year au mois en cours. Sélectionnez Modifier, puis ajustez le **filtre du rapport Month Year** pour enregistrer le nouveau mois par défaut. 

##### <a name="remediation"></a>Correction 

Concentrez vos premières corrections sur les bâtiments ou sous-réseaux dont le volume d’erreurs est le plus élevé. Cela aura un impact considérable sur l’expérience utilisateur et aidera à réduire rapidement le taux d’échecs de configuration d’appel de l’organisation. Le tableau suivant répertorie les deux raisons des échecs de configuration signalés par le tableau de configuration.

| Call Setup Failures reason       | Cause classique                    |
|----------------------------------|----------------------------------|
| Règle d’exemption d’inspection approfondie des paquets FW manquante | Indique que l’équipement réseau le long du chemin d’accès a empêché l’établir à cause de règles d’inspection approfondie des paquets. Cela est probablement dû à des règles de pare-feu mal configurées. Dans ce scénario, la poignée de mains TCP a réussi, mais la poignée de mains SSL ne l’a pas fait.      |
| Règle d’exception de bloc IP FW manquante      | Indique que l’équipement réseau le long du chemin d’accès a empêché l’établissage du chemin de médias vers Microsoft 365 ou Office 365 réseau. Cela peut être dû à des règles de proxy ou de pare-feu mal configurées pour autoriser l’accès aux adresses IP et aux ports utilisés pour le trafic Teams et Skype Entreprise réseau. |

Lorsque vous commencez vos corrections, vous pouvez concentrer vos efforts sur un bâtiment ou sous-réseau particulier. Comme le tableau précédent le montre, ces problèmes sont dus à des configurations de pare-feu ou de proxy. Examinez les options dans le tableau suivant pour les actions de correction.

|      Correction      |Aide  |
|-----------------------|----------|
| Configurer des pare-feu | Travaillez avec votre équipe réseau et vérifiez la configuration de votre pare-feu par rapport [Office 365 d’adresses IP.](/microsoft-365/enterprise/urls-and-ip-address-ranges)<br><br>Vérifiez que les [sous-réseaux multimédias](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) et les ports sont inclus dans les règles de pare-feu. <br><br>Vérifiez que les [ports nécessaires](prepare-network.md) sont ouverts dans le pare-feu. L’UDP doit avoir la priorité, car TCP est considéré comme un protocole de failback pour le partage d’écran audio, vidéo et vidéo, et son utilisation affectera la qualité de l’appel. Le partage d’applications RDP héritée utilise uniquement le protocole TCP.|

### <a name="drop-failures"></a>Échecs de chute

Contrairement aux codes d’échec de configuration, le DQD n’a pas de code de chute pour indiquer la raison pour laquelle des échecs de chute se produisent, ce qui rend difficile l’isoler d’une cause racine spécifique. Pour un meilleur tri des échecs de tri, utilisez une approche inférée. En résisant tous les points d’intérêt pour les médias, en correctifs pour les clients et les pilotes et en faisant passer l’utilisation d’appareils certifiés pour Teams et Skype Entreprise, vous pouvez vous attendre à une baisse des taux d’utilisation.

#### <a name="drop-failure-trend-analysis"></a>Analyse de la tendance de l’échec de chute

Ce rapport affiche le nombre total de flux audio, le nombre total d’échecs de chute et le taux d’échec de chute. Pointer sur l’une des colonnes pour afficher ses valeurs. 


##### <a name="analysis"></a>Analyse

En utilisant ce type de rapport, vous pouvez répondre aux questions suivantes :

-   Quel est le taux d’échec de chute actuel ?
-   Le taux d’échec est-il inférieur à la mesure cible définie ?
-   La tendance d’échec est-elle pire ou meilleure que celle du mois précédent ?
-   La tendance d’échec est-elle croissante, stable ou décroissante ?

Quelles que soient les réponses aux questions ci-dessus, prenez le temps d’étudier l’utilisation des sous-rapports afin de rechercher les bâtiments ou réseaux qui pourraient avoir besoin d’une correction. Bien que le taux d’échec de chute global puisse être inférieur à la mesure cible, le taux d’échec pour un ou plusieurs bâtiments ou réseaux peut se trouver au-dessus de la mesure cible et faire l’objet d’une investigation.

#### <a name="drop-failure-investigations"></a>Enquêtes sur les échecs de chute

Les échecs signalés ici indiquent que l’appel a été supprimé de façon inattendue et a entraîné une expérience utilisateur négative. Contrairement aux rapports de tendance, ces rapports fournissent des informations supplémentaires sur des sous-réseaux spécifiques qui doivent faire l’objet d’examens plus approfondies.


##### <a name="remediation"></a>Correction

Les rapports de tableau inclus vous permet d’isoler les zones de problème dans le réseau où le taux de chute est supérieur à la mesure cible que vous avez définie. Concentrez vos premiers efforts de correction sur les bâtiments ou sous-réseaux dont le total de flux est le plus élevé, pour en faire le plus gros impact.

Causes courantes des chutes d’appel :

-   Sortie Réseau ou Internet sous-mise en service
-   Aucune QoS configurée sur des réseaux contraintes
-   Versions client antérieures
-   Comportement de l’utilisateur

Une fois que vous avez [](use-call-analytics-to-troubleshoot-poor-call-quality.md) découvert vos zones de problème, vous pouvez utiliser l’analyse des appels par utilisateur pour examiner plus en détail les utilisateurs dans ce bâtiment à la recherche de problèmes spécifiques. L’analyse des appels contient des données EUII supplémentaires et peut être utile pour isoler davantage les raisons possibles des échecs de chute.

Quelle que soit l’étape suivante, il est pratique de signaler à votre aide qu’un problème a été détecté pour des bâtiments ou sous-réseaux spécifiques. Cela permet au service d’aide de répondre rapidement aux appels entrants et de trier les utilisateurs plus efficacement. Les utilisateurs avec un marquage peuvent ensuite être signalés à l’équipe d’ingénierie pour examen plus approfondie.

Le tableau suivant répertorie certaines méthodes courantes pour gérer et corriger les échecs de chute.

| Correction                              | Aide                      |
|------------------------------------------|-------------------------------|
| **Réseau/Internet**                         | **Congestion**: Travaillez avec votre équipe réseau pour surveiller la bande passante sur des bâtiments ou sous-réseaux spécifiques pour vérifier la surutilisation. Si vous confirmez l’encombrement du réseau, envisagez d’augmenter la bande passante pour ce bâtiment ou appliquer la QoS. Utilisez les rapports de synthèse [Quality Poor Stream](#quality-investigations) inclus pour examiner les sous-réseaux du problème en cas de problèmes de gigue, de latence et de perte de paquets, car ceux-ci précèdent souvent un flux supprimé.<br><br>**QoS**: si l’augmentation de la bande passante est impraticable ou interdit par le coût, envisagez d’implémenter la QoS. Cet outil est très efficace pour gérer le trafic encombré et peut garantir que les paquets multimédias sur le réseau géré sont prioritaires sur le trafic non multimédia. Par contre, s’il n’existe aucune preuve claire que la bande passante est à l’origine du problème, envisagez les solutions ci-après :<ul><li>[Microsoft Teams Conseils sur la QoS](qos-in-teams.md)</li></ul><br>**Effectuer une évaluation** de la disponibilité du réseau : une évaluation du réseau fournit des détails sur l’utilisation attendue de la bande passante, la manière de gérer les changements de bande passante et de réseau, et les pratiques réseau recommandées pour les réseaux Teams et Skype Entreprise. En utilisant la table précédente comme source, vous avez une liste de bâtiments ou sous-réseaux qui sont d’excellents candidats pour une évaluation.<ul><li>[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)</li></ul> |
| **Clients (Skype Entreprise Online uniquement)** | Certains clients Skype Entreprise connus et documentés en matière de fiabilité des médias. Examinez les rapports d’analyse des appels de plusieurs utilisateurs concernés ou créez un rapport personnalisé de tableau de la version client dans le tableau de table des appels filtré sur des bâtiments ou sous-réseaux spécifiques avec la mesure % total de l’échec d’appel supprimé. Ces informations vous aideront à déterminer s’il existe une relation entre les chutes d’appel dans ce bâtiment spécifique et une version spécifique du client.     |
| **Appareils**                                  |Si les périphériques sont à l’origine des problèmes de qualité des appels, envisagez de mettre à jour les appareils incriminés. Lisez [Téléphones pour Teams](./devices/phones-for-teams.md) pour en savoir plus. |
| **Comportement de l’utilisateur**                            | Si vous déterminez qu’aucun réseau, appareil ou client n’est problématique, vous pouvez développer une stratégie d’adoption des utilisateurs pour informer les utilisateurs de la meilleure façon de participer aux réunions et de les quitter. Un utilisateur Teams et Skype Entreprise’utilisateur pourra améliorer son expérience utilisateur pour tous les participants à la réunion. Par exemple, un utilisateur qui met son ordinateur portable en veille (en fermant le clavier) sans quitter la réunion est considéré comme une chute d’appel inattendue.   |

## <a name="quality-investigations"></a>Enquêtes sur la qualité

L’étape suivante pour évaluer l’état de la qualité audio au sein de l’organisation consiste à examiner l’utilisation de Poor Stream Rate (PSR), TCP et proxy. Il est important de se rappeler que les données du CQD ne fournissent pas de cause racine spécifique, mais fournissent à la place des zones à problème susceptibles de poser problème pour commencer une conversation en collaboration avec les équipes appropriées pour les activités de correction. 

> [!NOTE]
> Tous les rapports inclus dans les modèles ne sont pas abordés dans cet article. toutefois, les méthodes d’examen expliquées ci-dessous s’appliquent toujours à ces rapports. Pour plus d’informations, reportez-vous à la description individuelle du rapport. 

### <a name="quality"></a>Qualité

Les pourcentages de RSP servent à indiquer si l’organisation atteint les objectifs métriques définis pour une zone de concentration donnée. Il est important de noter que, même si les pourcentages élevés sont au sein de la cible définie, il est possible que des sous-réseaux ou bâtiments individuels ne répondent pas aux objectifs définis et, par conséquent, doivent faire l’objet d’examens plus approfondies. Par exemple, si le pourcentage global de rapport PSR audio est de 2 % en avril, ce qui atteint la cible échantillon, il est possible que les bâtiments et sous-réseaux individuels rencontrent encore des expériences médiocres, selon la distribution globale de ce 2 %. 

Pour évaluer le pourcentage de flux médiocres, utilisez les rapports de qualité. Différents rapports de qualité sont fournis pour passer en revue les indicateurs de l’ensemble, des conférences, des appels à deux, des appels PSTN, du VPN et des salles de réunion. Des rapports mensuels, hebdomadaires et quotidiens sont fournis pour vous aider dans ce processus. Les rapports hebdomadaires et quotidiens sont limités au modèle Réseaux gérés pour améliorer leur efficacité et réduire le bruit. 

#### <a name="quality-trend-analysis"></a>Analyse des tendances de qualité

Les rapports tendance affichent des informations sur la qualité au fil du temps et sont utilisés pour identifier et comprendre les tendances de qualité dans chaque domaine d’intérêt. Comme indiqué ci-dessus, des arbres signalés sont inclus dans les modèles pour examiner la qualité. conférence, à deux, appel PSTN, VPN et salles de réunion. À des fins d’analyse de la qualité, le processus d’analyse est le même. Toutefois, nous vous recommandons de commencer par les conférences, car toute amélioration de la qualité des conférences peut également avoir un effet positifs sur tous les autres aspects. 

> [!Note]
> L’étude de salles de réunion à deux, d’appels PSTN et de salles de réunion est semblable à celle des conférences. L’objectif est d’isoler les bâtiments ou sous-réseaux dont la qualité est la moins bonne et d’identifier la raison pour laquelle la qualité est médiocre.

> [!Important]
> Les rapports vpn sont filtrés à l’aide de la deuxième dimension VPN. Cette dimension nécessite que l’adaptateur réseau VPN soit correctement inscrit en tant qu’adaptateur d’accès à distance. Les fournisseurs vpn n’utilisent pas cet indicateur de façon fiable et votre kilométrage peut varier en fonction du fournisseur VPN déployé au niveau de votre organisation. Modifiez les [rapports VPN](CQD-upload-tenant-building-data.md#vpn) si nécessaire en utilisant le nom du bâtiment ou du réseau.

##### <a name="investigation"></a>Examens

En utilisant ces rapports, vous pouvez répondre aux questions suivantes :

-   Quelle est la valeur PSR totale pour le mois en cours ?
-   L’indicateur de performance PSR est-il inférieur à la mesure cible définie ?
-   Est-ce que la PSR est pire ou meilleure que le mois précédent ?
-   La tendance de la valeur PSR est-elle croissante, stable ou décroissante ?

Quelles que soient les réponses aux questions ci-dessus, prenez le temps d’examiner les sous-rapports pour rechercher les bâtiments ou sous-réseaux qui pourraient avoir besoin d’être étudiés. Bien que la valeur globale de la PSR puisse être inférieure à la mesure cible, elle est souvent au-dessus de la valeur pour un ou plusieurs bâtiments ou réseaux et nécessite une correction.

#### <a name="quality-investigations"></a>Enquêtes sur la qualité

Les rapports récapitulatifs de la qualité vous donnent des informations plus approfondies sur la contribution aux flux classés comme médiocres, et aident à isoler les zones de problème dans le réseau géré.

Bien que les dimensions utilisées peuvent légèrement différer d’un rapport à l’autre, chaque rapport inclut des mesures pour le nombre total de flux, le nombre total de flux médiocres, la note PSR et la qualité médiocre due. Des rapports ont été créés pour chaque domaine d’intérêt : conférence, conférence à deux, appel PSTN, VPN et salles de réunion. Le modèle Réseau géré inclut des rapports supplémentaires pour tirer parti des informations d’emplacement téléchargées via le fichier de bâtiment.


> [!Note]
> Le tri des sous-réseaux courants est difficile en raison de leur utilisation courante. Un rapport distinct affichant l’ADRESSE IP publique du client (Second Reflexive Local IP) a été ajouté au modèle All Networks pour vous aider à corriger les bureaux qui utilisent des réseaux communs.


![Capture d’écran montrant le résumé du flux audio médiocre.](media/qerguide-image-poorqualitysummary.png)

##### <a name="remediation"></a>Correction

Concentrez vos efforts de correction sur les bâtiments ou sous-réseaux qui ont le plus grand volume de flux, car cela aura un impact considérable et aidera à améliorer rapidement l’expérience utilisateur. Utilisez les mesures de gigue, de perte de paquets et d’aller-retour (RTT) pour comprendre les facteurs contribuent à la mauvaise qualité (il est possible qu’il y a plusieurs problèmes) :

-   **Gigue**: les paquets multimédias arrivent à des vitesses différentes, ce qui entraîne l’arrivée d’un haut-parleur.
-   **Perte de paquets**: les paquets multimédias sont supprimés, ce qui crée l’effet des mots manquants ou des syllabes.
-   **RTT**: l’accès des paquets multimédias à leur destination prend beaucoup de temps, ce qui crée un effet de walkie-talkie.

Pour vous aider à analyser les problèmes de qualité, utilisez [l’analyse des appels par utilisateur.](use-call-analytics-to-troubleshoot-poor-call-quality.md) L’analyse des appels vous permet d’examiner une conférence ou un rapport d’appel d’utilisateur spécifique. Ce rapport contient des données EUII/PII et est utile lorsque vous recherchez la cause d’un échec. Une fois que vous savez quel bâtiment est affecté, il devrait être simple de suivre les utilisateurs dans ce bâtiment. 

N’oubliez pas de faire savoir à votre service d’aide que ces réseaux rencontrent des problèmes de qualité. Ils peuvent ainsi trier les appels entrants et y répondre rapidement.

| Correction                              | Aide                         |
|------------------------------------------|----------------------------------|
| **Réseaux**                                 | **Congestion**: un réseau inutilisé ou sous-mis en service peut entraîner des problèmes de qualité multimédia. Travaillez avec l’équipe réseau pour déterminer si les connexions réseau entre l’utilisateur et le point de sortie Internet disposent d’une bande passante suffisante pour prendre en charge les médias. <br><br>**Évaluation** de la disponibilité du réseau : une évaluation du réseau fournit des détails sur l’utilisation attendue de la bande passante, la manière de gérer les changements de bande passante et de réseau, et les pratiques réseau recommandées pour les réseaux Teams et Skype Entreprise. En utilisant la table précédente comme source, vous avez une liste de bâtiments ou sous-réseaux qui sont d’excellents candidats pour une évaluation.<ul><li>[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)</li></ul>|
| **Qualité de service (QoS)**  | QoS est un outil éprouvée qui permet de hiérarchiser les paquets sur un réseau encombré pour s’assurer qu’ils arrivent à destination, en temps et en heure. Envisagez d’implémenter QoS dans votre organisation pour optimiser la qualité de l’expérience utilisateur où la bande passante est limitée. La QoS vous aidera à résoudre les problèmes généralement associés à des niveaux élevés de perte de paquets et, dans un moindre degré, de gigue et de temps d’aller-retour.<ul><li>[Teams Conseils sur la QoS](qos-in-teams.md)</li></ul> |
| **Wi-Fi**               | Wi-Fi peut avoir un impact significatif sur la qualité des appels. Wi-Fi déploiements ne prennent généralement pas en considération la qualité réseau requise pour les services VoIP et sont souvent une source de mauvaise qualité. Pour plus d’informations sur l’optimisation de Wi-Fi infrastructure informatique, consultez [cet article sur Wi-Fi de projet.](/skypeforbusiness/certification/plan-wifi)<br><br>**Pilote sans fil**: assurez-vous que les pilotes sans fil sont à jour. Cela permettra d’atténuer toute expérience utilisateur médiocre liée à un pilote obsolète. De nombreuses organisations n’incluent pas de pilotes sans fil dans leurs cycles de correctifs, et ces pilotes peuvent être non compatibles pendant des années. De nombreux problèmes de connexion sans fil sont résolus en veillant à ce que les pilotes sans fil soient à jour.<br><br>**WMM**: WMM (Wireless Multimedia Extensions), également appelé Wi-Fi Multimedia, fournit des fonctionnalités de QoS de base aux réseaux sans fil. Les réseaux sans fil modernes doivent prendre en charge de nombreux appareils. Ces appareils sont en concurrence pour la bande passante et peuvent entraîner des problèmes de qualité pour les services VoIP, pour lequel la vitesse et la latence sont essentielles. Pour plus d’information, consultez votre fournisseur sans fil et envisagez d’implémenter WMM sur votre réseau sans fil pour hiérarchiser les Skype Entreprise et Teams multimédia.<br><br>**Densité des points d’accès**: les points d’accès peuvent être trop éloignés ou ne pas se trouve dans un emplacement idéal. Pour minimiser les interférences potentielles, placez des points d’accès supplémentaires dans les salles de conférence et dans des emplacements qui ne sont pas obstrués par des murs ou d’autres objets sur lequel le signal Wi-Fi est faible.<br><br>**2,4 GHz ou 5 GHz**: 5 GHz offre moins d’interférences et de vitesses supérieures en arrière-plan et doit être hiérarchisé lors du déploiement de VoIP sur Wi-Fi. Toutefois, 5 GHz n’est pas aussi fort que 2,4 GHz et n’est pas aussi facile à traverser. Examinez la mise en page de votre bâtiment pour déterminer la fréquence à utiliser pour la meilleure connexion. |
|**Périphérique réseau** | Les grandes organisations peuvent avoir des centaines d’appareils répartis sur le réseau. Travaillez avec votre équipe réseau pour vous assurer que les périphériques réseau de l’utilisateur vers Internet sont conservés et à jour. |
| **VPN**  | Les équipements VPN ne sont pas traditionnellement conçus pour gérer les charges de travail multimédia en temps réel. Certaines configurations VPN interdit l’utilisation du protocole UDP (qui est le protocole préféré pour les médias) et s’appuient sur TCP uniquement. Envisagez d’implémenter une solution vpn à tunnel fractionnel afin de réduire le vpn en tant que source de mauvaise qualité. |
| **Clients** <br>(Skype Entreprise Online uniquement) | Assurez-vous que tous les clients sont régulièrement mis à jour. |
| **Appareils** | Si les périphériques sont à l’origine des problèmes de qualité des appels, envisagez de mettre à jour les appareils incriminés. Lisez [Téléphones pour Teams](./devices/phones-for-teams.md) pour en savoir plus. |
| **Pilotes** | L’application de correctifs réseau (Ethernet et Wi-Fi), audio, vidéo et USB devrait faire partie de votre stratégie globale de gestion des correctifs. De nombreux problèmes de qualité sont résolus en mettant à jour les pilotes. |
| **Salles de réunion sur Wi-Fi** | Nous recommandons vivement d’connecter les appareils des salles de réunion au réseau à l’aide d’une connexion Ethernet d’au moins 1 Gbps. Les appareils de salle de réunion incluent généralement plusieurs flux audio et vidéo, ainsi que le contenu de la réunion tel que le partage d’écran, et ont une qualité réseau plus élevée que les autres points de terminaison Teams ou Skype Entreprise réunion. Par définition, les salles de réunion sont des appareils en Wi-Fi,ce qui n’offre un avantage que pendant l’installation.<br><br>Les salles de réunion doivent être traitées avec davantage de soin et d’attention pour garantir que l’expérience d’utilisation de ces appareils dépasse ou dépasse les attentes. Les problèmes de qualité des salles de réunion vont généralement être rapidement multipliés, car ils sont souvent utilisés par le personnel de niveau supérieur.<br><br>Toutes étant égales (sauf dans le cadre de la commodité), les Wi-Fi performances sont généralement inférieures à celles d’une connexion câblé. Avec l’augmentation des stratégies « apportez votre propre appareil » et l’utilisation des ordinateurs portables, Wi-Fi points d’accès sont souvent sur-utilisés. Il est possible que les médias en temps réel ne soient pas prioritaires Wi-Fi réseaux, ce qui peut entraîner des problèmes de qualité pendant les heures de pointe. Cette utilisation importante peut coïncider avec une réunion où une dizaine de personnes peuvent assister à une réunion, chacune possède son ordinateur portable et son smartphone connectés au même point d’accès Wi-Fi que l’appareil de la salle de réunion.<br><br>Wi-Fi ne doit être considéré qu’comme une solution temporaire, pour une installation mobile, ou lorsqu'Wi-Fi a été correctement mis en service pour prendre en charge des médias de classe professionnelle en temps réel. |


### <a name="tcp"></a>TCP 

Le protocole TCP (Transmission Control Protocol) est considéré comme un transport de retour à la ligne et non comme le transport principal que vous souhaitez pour les médias en temps réel. La raison pour laquelle il s’agit d’un transport de failback est due à la nature avec état du protocole TCP. Par exemple, si un appel est effectué sur un réseau latent et que des paquets multimédias sont retardés, les paquets d’il y a quelques secondes (ce qui n’est plus utile) entrent en compétition pour la bande passante pour arriver au récepteur, ce qui peut rendre une mauvaise situation pire. Cela a pour effet d’entraîner la diffusion de l’audio et d’étirer l’audio, ce qui peut entraîner des artefacts audibles, souvent sous forme de gigue.

Les rapports de cette section ne font pas de distinction entre les flux bon et médiocre. Étant donné que le protocole UDP est la meilleure option, les rapports recherchent l’utilisation du protocole TCP pour le partage d’écran audio, vidéo et vidéo (VBSS). Des taux de flux médiocres sont fournis pour vous aider à comparer la qualité UDP à la qualité TCP, de sorte que vous pouvez concentrer vos efforts là où l’impact est le plus important. L’utilisation du protocole TCP est principalement due à des règles de pare-feu incomplètes. Pour plus d’informations sur les règles de pare-feu pour Teams et Skype Entreprise Online, voir Microsoft 365 et Office 365 url et [plages d’adresses IP.](/microsoft-365/enterprise/urls-and-ip-address-ranges)

> [!Note]
> L’audio, la vidéo et le VBSS préfèrent tous UDP comme transport principal. La charge de travail de partage d’application RDP héritée utilise uniquement TCP.

#### <a name="tcp-usage"></a>Utilisation du protocole TCP

Les rapports TCP indiquent l’utilisation globale de TCP au cours des sept derniers mois. Tous les autres rapports de cette section porteront sur le narrowing de bâtiments et sous-réseaux spécifiques où le TCP est fréquemment utilisé. Des rapports distincts sont disponibles pour les flux de conférence et à deux.

![Graphique montrant le pourcentage de flux audio qui utilisent TCP.](media/qerguide-image-audiostreamswithtcp.png)

##### <a name="investigation"></a>Examens

En utilisant ce rapport, vous pouvez répondre aux questions suivantes :

-   Quel est le volume total de flux TCP pour le mois en cours ?
-   Est-ce pire ou mieux que le mois précédent ?
-   La tendance d’utilisation TCP est-elle croissante, stable ou décroissante ?
-   La PSR TCP est-elle identique à ma PSR globale ?

Si vous remarquez que la tendance d’utilisation du protocole TCP augmente ou dépasse la normale utilisation mensuelle, prenez le temps d’examiner les sous-rapports afin de rechercher les bâtiments ou réseaux qui pourraient avoir besoin d’une correction. Dans l’idéal, vous voulez autant de sessions audio TCP que possible sur le réseau géré.

#### <a name="tcp-vs-udp"></a>TCP et UDP

Ce rapport identifie le volume des rapports d’utilisation TCP et UDP sur le dernier mois pour le partage d’écran audio, vidéo et vidéo (VBSS). 

![Rapport indiquant le volume de flux qui utilisent le protocole TCP ou UDP.](media/qerguide-image-tcpvsudp.png)

##### <a name="analysis"></a>Analyse

Bien que vous vouliez que l’utilisation du protocole TCP soit aussi faible que possible, vous pourriez constater une part de l’utilisation du protocole TCP dans un déploiement autrement sain. Le protocole TCP ne contribue pas à un appel médiocre, aussi des taux de flux sont-ils fournis pour vous aider à déterminer si l’utilisation du protocole TCP contribue à une mauvaise qualité. 

#### <a name="tcp-investigations"></a>Enquêtes TCP

Dans les modèles de DQD fournis, accédez au Flux TCP en construisant des rapports de sous-réseau et en utilisant le modèle Réseaux gérés ou Tous les réseaux. Aux fins d’examen de l’utilisation du protocole TCP, le processus est le même. Nous allons donc nous concentrer sur la discussion sur les conférences.


##### <a name="remediation"></a>Correction

Ce rapport identifie des bâtiments et sous-réseaux spécifiques qui contribuent au volume d’utilisation du protocole TCP. Un rapport supplémentaire est également inclus pour identifier l’adresse IP Microsoft Relay utilisée lors de l’appel pour mieux isoler les règles de pare-feu manquantes. Concentrez vos efforts de correction sur les bâtiments qui ont le plus grand volume de flux TCP pour optimiser l’impact.

La raison la plus fréquente de l’utilisation du protocole TCP est l’absence de règles d’exception dans les pare-feu ou proxies. Nous allons discuter des proxies dans la section suivante. Pour l’instant, concentrez-vous sur vos efforts sur les pare-feu. En utilisant le bâtiment ou sous-réseau fourni, vous pouvez déterminer le pare-feu qui doit être mis à jour.

| Correction        | Aide     |
|--------------------|--------------------------------------|
| Configurer le pare-feu | Vérifiez que [Microsoft 365 ou Office 365 ports et adresses IP](/microsoft-365/enterprise/urls-and-ip-address-ranges) sont exclus de votre pare-feu. Pour les problèmes TCP liés aux médias, concentrez-vous sur vos efforts initiaux sur les points suivants :<ul><li>Vérifiez que les sous-réseaux multimédias du client 13.107.64.0/18 et 52.112.0.0/14 sont dans vos règles de pare-feu.</li><li>Les ports UDP 3478-3481 sont les ports multimédias requis et doivent être ouverts, faute de quoi le client ne pourra pas revenir au port TCP 443.</li></ul> |
| Vérifier             | Utilisez [l’outil d’évaluation](https://www.microsoft.com/download/details.aspx?id=53885) du réseau Microsoft pour vérifier les problèmes de connectivité à des adresses IP Microsoft 365 ou Office 365 spécifiques et des ports du bâtiment ou sous-réseau concerné.    |

### <a name="http-proxy"></a>Proxy HTTP

Les proxies HTTP ne sont pas le chemin d’accès préféré pour l’établissement de sessions multimédias, pour une multitude de raisons. Bon nombre d’entre elles contiennent des fonctionnalités d’inspection approfondie des paquets qui peuvent empêcher l’certaines connexions au service et introduire des interruptions. En outre, presque tous les proxies forcent TCP au lieu d’autoriser UDP, ce qui est recommandé pour une qualité audio optimale.

Nous vous recommandons toujours de configurer le client pour qu’il se connecte directement aux services Teams et Skype Entreprise client. Ceci est particulièrement important pour le trafic multimédia.


> [!IMPORTANT]
> Nous vous recommandons de télécharger un fichier [de](CQD-upload-tenant-building-data.md) construction valide afin de distinguer les flux audio externes et les flux audio externes lors de l’analyse de l’utilisation du proxy. 


#### <a name="http-proxy-usage"></a>Utilisation du proxy HTTP

Dans cette section du modèle, le rapport de flux proxy HTTP ressemble beaucoup aux rapports TCP. Il ne traite pas de la qualité ou de la qualité des appels, mais de la connexion par le protocole HTTP.

![Capture d’écran du rapport de flux audio qui utilisent HTTP.](media/qerguide-image-audiostreamswithhttp.png)

##### <a name="analysis"></a>Analyse

Vous voulez voir le moins de flux multimédias HTTP possible. Si des flux traversent votre proxy, consultez votre équipe en réseau pour vous assurer que les exclusions correctes sont en place afin que les clients soient directement routage vers des sous-réseaux multimédias Teams ou Skype Entreprise Online.

Si votre organisation n’a qu’un seul proxy Internet, vérifiez la Microsoft 365 adresse Office 365 correctement et les exclusions des [plages d’adresses IP.](/microsoft-365/enterprise/urls-and-ip-address-ranges) Si plusieurs proxys Internet sont configurés dans votre organisation, utilisez le sous-rapport HTTP pour identifier le bâtiment ou sous-réseau affecté.

Pour les organisations qui ne peuvent pas contourner le proxy, assurez-vous que le client Skype Entreprise est configuré pour se connecter correctement lorsqu’il se trouve derrière un proxy, comme indiqué dans l’article Skype Entreprise doit utiliser le serveur [proxy](https://support.microsoft.com/help/3207112/skype-for-business-should-use-proxy-server-to-sign-in-instead-of-tryin)pour se connecter au lieu d’essayer la connexion directe. 


#### <a name="http-proxy-investigations"></a>Enquêtes sur les proxys HTTP

Ce rapport identifie des bâtiments et sous-réseaux spécifiques qui contribuent à l’utilisation de HTTP.


##### <a name="remediation"></a>Correction

Nous [vous recommandons](proxy-servers-for-skype-for-business-online.md) de toujours contourner les proxies pour les Skype Entreprise et Teams, en particulier le trafic de médias. Lesxies ne rendent pas les Skype Entreprise plus sécurisés, car leur trafic est déjà chiffré. Des problèmes de performances peuvent s'introduire dans l'environnement par le biais de la latence et la perte de paquets. De tels problèmes entraînent une expérience négative du partage audio, vidéo et d’écran, pour lequel les flux en temps réel sont essentiels.

La raison la plus fréquente de l’utilisation d’HTTP est l’absence de règles d’exception dans les proxies. En utilisant le bâtiment ou le sous-réseau fourni, vous pouvez rapidement déterminer le proxy qui doit être configuré pour la dérivation média.

Vérifiez que les informations [requises Microsoft 365 ou Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges) nom de famille sont ajoutés à une liste d’utilisateurs dans votre proxy.

## <a name="endpoint-investigations"></a>Enquêtes sur les points de terminaison

Cette section se concentre sur les tâches de rapport sur les versions client et l’utilisation d’appareils certifiés. Les rapports sont disponibles pour l’utilisation en mode plan pour les versions client, le type de client, les périphériques de capture et les pilotes (microphone), les périphériques de capture vidéo et les versions Wi-Fi de fournisseur et de pilote.

> [!NOTE]
> Tous les rapports inclus dans les modèles ne sont pas abordés dans cet article. toutefois, les méthodes d’examen expliquées ci-dessous s’appliquent toujours. Pour plus d’informations, reportez-vous à la description individuelle du rapport.

### <a name="client-versions"></a>Versions client

Ces rapports se concentrent sur l’Skype Entreprise versions client en cours d’utilisation et leur volume relatif dans l’environnement.

> [!IMPORTANT]
> Actuellement, Teams clients sont distribués et mis à jour automatiquement via le service Azure réseau de distribution de contenu et sont mis à jour par le service. Par conséquent, vous n’avez pas besoin de surveiller Teams versions clientes (sauf si vous désactiver la mise à jour automatique, ce qui n’est pas recommandé).

À moins que vous n’excluez les données des participants fédérés, ces rapports incluront la télémétrie du client à partir de points de terminaison fédérés. Pour exclure des points de terminaison fédérés, vous devez ajouter un filtre de requête pour l’ID de locataire Second Tenant ID à [l’ID de locataire de votre organisation.](CQD-data-and-reports.md#how-to-find-your-tenant-id) Vous pouvez également utiliser un filtre [URL pour](CQD-data-and-reports.md#url-filters) exclure la télémétrie des participants fédérés.



#### <a name="remediation"></a>Correction

Un élément essentiel de la conduite des expériences utilisateur de haute qualité consiste à s’assurer que les clients gérés exécutent des versions à jour de Skype Entreprise, en plus de s’assurer que les pilotes audio, vidéo, réseau et USB pris en charge sont à jour. Cela offre plusieurs avantages, parmi ceux-ci : 

-   Il est plus facile de gérer quelques versions plutôt que plusieurs versions.
-   Elles offrent un niveau de cohérence de l’expérience.
-   Il permet de résoudre plus facilement les problèmes liés à la qualité et à l’utilisation des appels.
-   Microsoft effectue des améliorations et optimisations générales dans l’ensemble du produit. S’assurer que les utilisateurs reçoivent ces mises à jour réduit leur risque de se trouver dans un problème déjà résolu.

La limitation de votre déploiement aux versions clientes de moins de six mois permettra d’améliorer l’expérience globale des utilisateurs et la capacité de gestion en réduisant le nombre de versions à prendre en charge.

Si vous n’utilisez Office la technologie « Click-to-Run » (Lancer en un clic), la fenêtre de six mois s’ouvre automatiquement. Aucune action supplémentaire n’est requise.

Si vous avez plusieurs packages « Click-to-Run » et « Installer » (MSI), vous pouvez utiliser le rapport pour vérifier que les clients MSI sont régulièrement mis à jour. Si vous remarquez que des clients sont en retard, travaillez avec l’équipe responsable de la gestion des mises à jour Office et assurez-vous qu’ils approuvent et déploient régulièrement les correctifs client.

Il est également important de tenir compte du fait que les pilotes réseau, vidéo, USB et audio sont également mis à jour. Il est facile d’ignorer ces facteurs et de ne pas les inclure dans votre stratégie de gestion des correctifs.

Vous trouverez les numéros de version Skype Entreprise via les liens ci-dessous :

-   [Informations de publication pour les mises à jour Microsoft 365 Apps](/officeupdates/release-notes-office365-proplus)
-   [Historique des mises à jour pour Applications Microsoft 365 pour les grandes entreprises](/officeupdates/update-history-office365-proplus-by-date)
-   [Téléchargements et mises à jour de Skype Entreprise](/SkypeForBusiness/software-updates)

### <a name="devices"></a>Appareils

Pour utiliser le rapport de périphériques microphone, nous devons comprendre le concept de la note moyenne d’opinion (MOS). MOS est la mesure standard doré qui permet d’évaluer la qualité audio percevoir. Il s’agit d’un classement de 0 à 5.

La base de toutes les mesures de la qualité de la voix est la manière dont une personne perçoive la qualité de la voix. Étant donné qu’il est affecté par la perception humaine, il est intrinsèquement subjectif. Il existe plusieurs méthodologies différentes pour les tests subjectifs. La plupart des mesures de qualité vocale sont basées sur une échelle absolue d’évaluation des catégories.

Dans un test subjectif ACR, un nombre important de personnes évaluer leur qualité d’expérience sur une échelle de 1 (mauvaise) à 5 (excellent). La moyenne des résultats est la NOTE MOS. La fonction MOS résultante dépend de la plage d’expériences qui ont été exposées au groupe et du type d’expérience noté.

Étant donné qu’il n’est pas pratique de mener des tests subjectifs de la qualité de la voix pour un système de communication en direct, Microsoft Teams et Skype Entreprise génèrent des valeurs MOS à l’aide d’algorithmes avancés pour prévoir objectivement les résultats d’un test subjectif.

L’ensemble de mesures MOS et les mesures associées disponibles fournissent une vue d’ensemble de la qualité de l’expérience fournie aux utilisateurs par un appareil audio. 

En fournissant aux utilisateurs des périphériques certifiés pour Teams et Skype Entreprise, vous réduisez la probabilité de rencontrer des expériences négatives en raison de l’appareil lui-même (ce qui est plus probable, par exemple, avec des haut-parleurs et des microphones intégrés à un ordinateur portable). Pour plus d’informations, consultez les articles suivants sur le [programme de certification](/SkypeForBusiness/certification/overview) et le catalogue de solutions [partenaires.](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs)

Les rapports sur les appareils servent à évaluer l’utilisation de l’appareil par score en volume et MOS (audio uniquement). Ils sont trouvés dans les modèles d’accompagnement sous Clients & Devices. 

> [!IMPORTANT]
> À moins que vous n’excluez les données des participants fédérés, ces rapports incluront la télémétrie du client à partir de points de terminaison fédérés. Pour exclure des points de terminaison fédérés, vous devez ajouter un filtre de requête pour **l’ID** de locataire Second Tenant ID à l’ID [de locataire de votre organisation.](CQD-data-and-reports.md#how-to-find-your-tenant-id) Vous pouvez utiliser un filtre [d’URL](CQD-data-and-reports.md#url-filters) pour exclure la télémétrie des participants fédérés.


> [!Note]
> Lorsque vous consultez ce rapport, vous remarquerez peut-être qu’un même appareil a été signalé plusieurs fois. Ceci est dû à la façon dont l’appareil est signalé au CQD. Les différences matérielles et les paramètres régionaux du système d’exploitation entraînent des différences de rapport entre les données d’appareil.

##### <a name="remediation"></a>Correction

En règle générale, vous devez découvrir et mettre au pas des périphériques non certifiés et les remplacer par des périphériques certifiés. Voici quelques éléments dont vous tenirs compte lors de l’examen des rapports sur les appareils :

-   Les appareils utilisés sont-ils certifiés pour les Teams et Skype Entreprise ? 
-   Vous pouvez identifier les utilisateurs d’un appareil spécifique à l’aide de [l’analyse des appels par utilisateur.](use-call-analytics-to-troubleshoot-poor-call-quality.md) Vérifiez qu’il a les pilotes de périphérique les plus récents et que son appareil n’est pas connecté via un concentrateur USB ou une station d’accueil. 
-   Combien de versions différentes de divers pilotes sont utilisés ? Font-ils l’objet de correctifs régulièrement ? S’assurer que les pilotes audio, vidéo et Wi-Fi sont régulièrement mis à jour permettra d’éliminer ceux-ci comme sources de problèmes de qualité et de rendre l’expérience utilisateur plus prévisible et cohérente.

##### <a name="audio"></a>Audio

La tâche suivante consiste à déterminer l’utilisation globale des [périphériques audio certifiés.](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) Nous recommandons qu’au moins 80 % de tous les flux audio utilisent un périphérique audio certifié. Pour ce faire, il est préférable d’exporter le rapport sur les périphériques microphone Excel calculer l’utilisation d’appareils certifiés ou approuvés. Les organisations conservent généralement une liste de tous les appareils approuvés, aussi le filtrage et le tri des données doivent-ils être simples.

##### <a name="video"></a>Vidéo

Il est également important de mettre à jour les pilotes vidéo. S’assurer que les cartes vidéo sont régulièrement mise à jour permettra d’exclure les pilotes vidéo comme source de mauvaise qualité pour les flux vidéo. [L’utilisation de périphériques vidéo](https://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) certifiés garantit une expérience utilisateur de qualité supérieure. Les périphériques vidéo qui prendre en charge le codage natif H.264 sont préférés afin de réduire l’utilisation de l’UC pendant les vidéoconférences.

##### <a name="wi-fi"></a>Wi-Fi

Wi-Fi correctifs doivent également être régulièrement mises à jour et inclus dans votre stratégie de gestion des correctifs. De nombreux problèmes de qualité peuvent être corrigés en conservant les pilotes à Wi-Fi jour. Pour plus d’informations sur l’optimisation de Wi-Fi infrastructure informatique, consultez [cet article sur Wi-Fi de projet.](/skypeforbusiness/certification/networking-wifi)


## <a name="related-topics"></a>Sujets associés

[Utiliser Advisor pour Teams](use-advisor-teams-roll-out.md)

[Préparer le réseau de votre organisation pour Microsoft Teams](prepare-network.md)

[Office 365 Principes de connectivité réseau](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Analyses et rapports Teams](teams-analytics-and-reports/teams-reporting-reference.md)

[Gérer vos périphériques dans Teams](./devices/device-management.md)

[Améliorer et surveiller la qualité des appels pour les Teams](monitor-call-quality-qos.md)

[Qu’est-ce que le CQD ?](CQD-what-is-call-quality-dashboard.md)

[Configurer le tableau de bord de qualité des appels](turning-on-and-using-call-quality-dashboard.md)

[Télécharger données de bâtiment et de client](CQD-upload-tenant-building-data.md)

[Données et rapports du CQD](CQD-data-and-reports.md)

[Dimensions et mesures disponibles dans le DQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classification des flux dans le CQD](stream-classification-in-call-quality-dashboard.md)

[Utiliser Power BI pour analyser les données du CQD](CQD-Power-BI-query-templates.md)