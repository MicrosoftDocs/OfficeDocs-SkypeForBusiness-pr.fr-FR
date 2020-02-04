---
title: 'Lync Server 2013 : affiche : méthodologie de qualité d’appel Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Lync Call Quality Methodology'
ms:assetid: a069f4e5-4f80-4f0f-8657-2e07276b6b41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593600(v=OCS.15)
ms:contentKeyID: 61084874
ms.date: 06/24/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95105501d0403600e88d01ad5fa84363c1e81785
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-call-quality-methodology-in-lync-server-2013"></a>Méthodologie de qualité d’appel Lync dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-06-24_

Cet article est un complément de l’affiche de la [méthodologie de qualité des appels de Lync](http://go.microsoft.com/fwlink/?linkid=391841) , que vous pouvez télécharger à partir du centre de téléchargement.

![Affiche décrivant le processus CQM](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Affiche décrivant le processus CQM")

Vous pouvez utiliser cette affiche pour en savoir plus sur CQM, la méthodologie de qualité d’appel pour Lync 2013 et 2010, qui vous permet de rechercher et d’éliminer les problèmes affectant la qualité des appels et l’interface utilisateur pour les implémentations Lync qui incluent les fonctionnalités d’entreprise voix. La méthodologie de qualité des appels est une nouvelle infrastructure de dépannage et de gestion des services qui permet d’améliorer l’efficacité des services vocaux d’entreprise dans Lync. Dans cet article, vous pouvez en savoir plus sur CQM, sur les types de serveurs et de solutions analysés et sur les données de télémétrie collectées.

Si vous avez des questions sur l’utilisation de CQM, vous pouvez transmettre vos questions à cqmfeedback@microsoft.com.

L’affiche décrit les domaines suivants :

  - Présentation de Lync CQM

  - Ordre de priorité : exécuter des requêtes de courbe de tendance

  - PCD

  - Géré/non géré

  - Route du serveur

  - Route du dernier kilomètre

  - Route des points de terminaison

  - Gestion des services

  - Règles de jeu du tableau

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a>Présentation de Lync CQM

La méthodologie de qualité des appels est une nouvelle infrastructure de dépannage et de gestion des services qui permet d’améliorer l’efficacité des services vocaux d’entreprise dans Lync. Lorsque vous utilisez CQM, vous devez avoir besoin d’efforts pour garantir la qualité des appels et la satisfaction des utilisateurs pour les services voix entreprise. CQM est expliquée plus en détail dans la [méthodologie de qualité des appels](http://go.microsoft.com/fwlink/p/?linkid=615208). Cet article et l’affiche résument ce contenu.

CQM divise le dépannage du système en trois chemins ou « routes ». Il s’agit de la route du serveur, qui examine les serveurs et les liens entre eux, la route des points de terminaison, qui observe les appareils et les éléments multimédias utilisés pour le transport d’appels, ainsi que la route de dernier kilomètre, qui s’adresse à l’intégration d’appels réseau commuté traditionnels.

Chaque route est divisée en plusieurs segments liés à une zone ou à un sujet spécifiques, et à chaque définition de segment est effectuée sur le niveau de qualité acceptable, les actions effectuées pour atteindre ce niveau de qualité et un plan de gestion des services est mis en place pour gérer ce niveau de qualité avant de passer à la rubrique suivante.

L’affiche présente Lync CQM comme jeu de plateau pour trois joueurs, chacun d’entre eux qui passera par l’un des routes. Les cartes fournies avec le téléchargement permettent de simuler des obstacles à la qualité d’appel qui doivent être résolus. Des conseils et des suggestions relatives aux cibles, et comment les obtenir sont inclus dans les trois chemins d’accès, ainsi que les recommandations en matière de hiérarchisation pour lesquelles il y a des recommandations en matière de circulation (dans le jeu, les trois routes sont gérées en parallèle).

Comment CQM fonctionne-t-il dans les versions antérieures de Lync ? CQM est une nouveauté de Lync 2013, mais celle-ci peut être adaptée à Lync 2010. CQM peut travailler à un niveau avec Microsoft Office Communicator, mais cela n’est pas testé et n’est pas pris en charge.

Si vous avez des questions sur l’utilisation de CQM, vous pouvez transmettre vos questions à cqmfeedback@microsoft.com.

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a>Ordre de priorité : exécuter des requêtes de courbe de tendance

La première étape de CQM consiste à exécuter chacune des requêtes de tendance pour deux semaines, puis à analyser les résultats. Définir la priorité d’une action corrective par le contributeur du flux le plus grand, le rapport de flux médiocre le plus élevé et les zones gérées (celles que vous contrôlez).Si l’unité de contrôle multipoint/vidéo (AV MCU) ou les requêtes de médiation indiquent un résultat médiocre, commencez sur la route du serveur rouge ou du serveur.Si les requêtes filaires ou sans fil présentent des résultats médiocres, commencez sur la route bleue ou du dernier kilomètre.Si les requêtes VPN ou externes affichent des résultats médiocres, commencez sur la route de points verts ou de terminaison.

Une fois que vous avez choisi une route avec laquelle commencer, définissez une cible pour chaque zone (Assert), travaillez pour cette cible (atteindre), puis implémentez des procédures pour rester sur la cible (maintenance). Vous pouvez également utiliser ce poster comme jeu pour comprendre les principes qui prétendent CQM.

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a>PCD

L’outil de diagnostics d’avant-appel (PCD) vous aidera à identifier et à diagnostiquer les problèmes de votre réseau de périmètre (la base de données QoE ne collecte pas d’informations sur votre réseau Edge ou de périmètre) et permet également de résoudre les problèmes de connexion depuis le dernier kilomètre. L’outil est disponible sous la forme d’une application moderne Windows 8 ou d’une application http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88de bureau Windows à l’adresse.

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a>Géré/non géré

Le déploiement de Lync Server et l’infrastructure réseau peuvent généralement être divisés en espaces gérés et non gérés. L’espace géré inclut l’intégralité du réseau filaire et de l’infrastructure du serveur. L’espace non géré est l’infrastructure sans fil et l’infrastructure réseau externe.

Le fait de faire de cette distinction augmente la clarté de vos données et permet à votre organisation de se concentrer sur les charges de travail qui auront un impact mesurable sur la qualité audio et vidéo de vos utilisateurs. Les utilisateurs ont des attentes différentes de la qualité si l’appel est placé sur l’infrastructure dont vous êtes le propriétaire (géré) et de l’infrastructure qui est en partie soumise au contrôle d’une autre entité (non gérée). Ce n’est pas dire que les utilisateurs d’un réseau sans fil se trouvent sur leurs propres appareils pour offrir une excellente expérience de Lync Server.

L’amélioration de la qualité de la voix dans l’espace non géré nécessite que vous ayez une haute qualité dans l’espace géré. Le fait que le réseau Wi-Fi soit considéré comme géré ou non géré dépend de votre organisation. Les techniques permettant de réaliser un environnement sain sont différentes dans les deux espaces, comme les solutions.

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a>Route du serveur

Le segment 1 de la route de l’entreprise serveur adresse les serveurs réels dans l’implémentation Lync. Recueillez des données KHI concernant le serveur lui-même et son rôle dans l’implémentation, puis analysez le résultat. Si une action est garantie, résolvez les problèmes rencontrés. Pour plus d’informations sur cette rubrique, retrouvez-vous dans l’article à propos des [indicateurs d’intégrité clés de Lync Server 2013](lync-server-2013-poster-key-health-indicators.md) qui accompagne l’affiche Khi.

Le segment suivant réunit les flux multimédias entre le serveur AV MCU et le serveur de médiation. Commencez par déterminer vos cibles pour les seuils de flux médiocres. Les flux médiocres sont \> généralement PacketLossRate 0,01 \> ou PacketLossRateMax. 05. Une autre cible désirable est \< PoorStreamsRatio 2%. Ensuite, utilisez des requêtes détaillées pour rechercher des paires de serveurs AVMCU et de médiation avec des flux médiocres, identifier la cause de flux médiocres, examiner l’équipement réseau dans les mauvaises trajectoires de flux, corriger les flux médiocres et définir une configuration optimale ou « or » pour le réseau. équipementier. Pour conserver votre réussite, mettez en œuvre des processus et des outils permettant de gérer la dérive de configuration et de signaler de nouvelles zones de problèmes.

Examinez ensuite les flux multimédias entre le serveur de médiation et la passerelle RTC (réseau téléphonique commuté). Commencez par déterminer vos cibles pour les seuils de flux médiocres. Les flux médiocres sont \> généralement PacketLossRate 0,01 \> ou PacketLossRateMax. 05. Une autre cible désirable est \< PoorStreamsRatio 2%. Vous pouvez ensuite utiliser les requêtes détaillées pour trouver les paires serveur et passerelle avec des flux médiocres, identifier la cause des flux médiocres, examiner l’équipement réseau dans les mauvaises trajectoires de flux, corriger les flux médiocres et définir une configuration optimale ou « or » pour le réseau. équipementier. Pour conserver votre réussite, mettez en œuvre des processus et des outils permettant de gérer la dérive de configuration et de signaler de nouvelles zones de problèmes.

Enfin, examinez les mesures d’intégrité de votre passerelle PSTN. Identifiez les statistiques indiquant l’état d’intégrité et définissez les cibles sur celles-ci. Il n’y a pas d’instructions spécifiques fournies ici autant de passerelles possibles. Dès lors que des cibles sont établies, vous devez les corriger selon les besoins pour obtenir la cible ; dans le processus, vous définirez probablement une configuration « or » ou optimale pour la passerelle. Pour conserver votre réussite, mettez en œuvre des processus et des outils permettant de gérer la dérive de configuration et de signaler de nouvelles zones de problèmes. Sachez que les mises à jour de microprogrammes et de logiciels risquent de modifier votre configuration ou de vous permettre de modifier la définition de la configuration « d’or »; par conséquent, vous devez vous familiariser avec ces activités.

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a>Route du dernier kilomètre

Pour les deux manières de se connecter au réseau, le filaire est censé obtenir la meilleure qualité possible et correspondante pour les problèmes de dernier kilomètre. Utilisez la requête filaire CQM (LastMile\_0\_câblé) et les données de rapport de flux médiocres qu’elle fournit. Nous vous suggérons de définir \< une cible PoorStreamsRatio 5% \> pour les sites avec des flux 300). Pour obtenir vos cibles, remédiez aux sous-réseaux classés du plus mauvais au plus approprié et implémentez QoS.

Lorsque vous optimisez la qualité de vos connexions câblées, l’amélioration de la qualité sans fil devient plus facile, car l’infrastructure sans fil se trouve au cœur de chaque emplacement. Les flux sans fil médiocres dans un site avec une bonne qualité filaire doivent être attribués aux composants sans fil spécifiques. La requête sans fil CQM (\_LastMile\_1) fonctionne sur une plage de dates et renvoie tous les flux sans fil internes de votre environnement à partir des clients Lync vers ou depuis des serveurs de conférence ou des serveurs de médiation. Nous vous suggérons de définir \< une cible PoorStreamsRatio 5% \> pour les sites avec des flux 300). Pour obtenir vos cibles, remédiez aux sous-réseaux classés du plus mauvais au plus approprié et implémentez QoS.

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a>Route des points de terminaison

Commencer la recherche de points de terminaison dans la route avec les casques et d’autres appareils connus pour produire une qualité acceptable lorsqu’elles sont utilisées avec Lync. Nous vous suggérons d’utiliser \> une 3,6 cible AvgSendListen à des fins d’implémentation avec des flux 100.) Obtenez la cible en identifiant les périphériques posant problème et corrigez-les ou remplacez-les.

Examinez ensuite le périphérique ou le PC traitant le son pour les appels utilisateur finaux. Une mesure de qualité cible suggérée est \<une AudioMicGlitchRate = 1. Lorsque vous identifiez des configurations système optimales pour les systèmes des utilisateurs, définissez une configuration de PC « Golden », y compris des versions de pilotes.

Examinez désormais le chemin réseau qu’un flux audio effectue à partir d’un système de points de terminaison Lync, ce qui peut entraîner une mauvaise qualité audio. Si l’audio traverse une connexion VPN, il est possible que vous rencontriez des problèmes de latence. Si un client Lync interne ne parvient pas à établir un flux de médias directs vers un autre client Lync interne pour un appel d’égal à égal ou d’égal à égal, il est redirigé vers un chemin qui transmet le relais via un serveur Edge Lync, à partir de problèmes de latence et augmente le potentiel de perte et scintillement. Nous vous suggérons de définir une métrique de qualité de 0% de média via un réseau privé virtuel (VPN). Lorsque vous effectuez une correction pour obtenir la cible que vous définissez, identifiez les sous-réseaux de problèmes et examinez les règles de pare-feu, les formes de paquets et d’autres configurations pertinentes d’équipements réseau.

Les paquets IP peuvent utiliser le protocole TCP (Transmission Control Protocol) ou UDP (User Datagram Protocol). TCP est optimal pour les flux de données. UDP est en mode sans connexion et il est plus efficace pour le contenu multimédia dans la mesure où les mécanismes de récupération TCP ne peuvent pas résoudre les pertes en temps réel. Lync préfère toujours utiliser le protocole UDP, mais il sera restauré en cas de non-connexion. Les sessions multimédias via TCP présentent une qualité médiocre par rapport au protocole UDP. Nous vous recommandons d’obtenir une définition de qualité de connexions de 0% via TCP. Lorsque vous effectuez une correction pour obtenir la cible que vous définissez, identifiez les sous-réseaux de problèmes et examinez les règles de pare-feu, les formes de paquets et d’autres configurations pertinentes d’équipements réseau.

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a>Gestion des services

Le service gestion des services est l’état final de CQM et la destination des trois routes. Pour maintenir un niveau élevé de qualité d’appel, vous pouvez surveiller les points suivants :

1.  **Les utilisateurs** -activités de correction doivent représenter une augmentation mesurable de la satisfaction des utilisateurs. Vous pouvez mesurer cela par le biais de billets de problème ou d’autres mécanismes de commentaires. Vous pouvez également publier des mesures de qualité.

2.  **Processus** : définissez les processus quotidiens, hebdomadaires et mensuels pour le fonctionnement de CQM. Le rythme du rythme commence à une fréquence plus élevée lorsque vous effectuez une correction (quotidienne) et qu’il passe à une fréquence inférieure (mensuelle) au fur et à mesure que vous stabilisez la vidéo.

3.  **Outils** -Identifiez des outils à prendre en mesure et à des corriger. Il est possible que vous trouviez utile pour automatiser l’exécution des requêtes CQM pour prendre en charge vos processus. La correction risque de nécessiter des outils supplémentaires par exemple pour appliquer des configurations normalisées sur des éléments réseau ou la perte de résolution des flux médiocres.

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a>Règles de jeu du tableau

Vous pouvez utiliser cette affiche en tant que référence à une implémentation CQM ou à un jeu pour vous exercer aux concepts. Pour le lire, vous avez besoin d’une puce à face et de cartes fournies par 1 6. La version téléchargeable des cartes est disponible pour l’impression sur des cartes de visite Avery 5871 standard.

Le jeu est destiné à 3 joueurs. Il existe trois chemins d’accès que les joueurs peuvent utiliser pour obtenir la qualité souhaitée et atteindre l’état de la gestion du Service Center : une plante serveur, un point de terminaison et un dernier kilomètre. Chaque chemin d’accès s’arrête en même temps que vous déclarez les cibles de qualité, vous pouvez obtenir des buts et conserver un aspect de votre système. Placez les cartes dans la zone indiquée ci-dessus, puis dessinez 5 cartes. Passez en revue les cartes que vous avez dessinées et placez-les sur le segment de tableau approprié. Chaque joueur parcourt les cartes sur son chemin d’accès étape par étape, en affirmant les cibles de qualité, en atteignant ces cibles et en gérant les niveaux de service. Le jeu est terminé lorsque tous les joueurs arrivent dans l’état de gestion du service central. Des règles plus détaillées sont fournies avec le téléchargement de la carte de jeu.

Pour **affirmer** qu’il s’agit d’un objectif de qualité, passez en revue les paramètres applicables à cette cible, et indiquez l’État sonore et ne choisirez pas. Nous avons recommandé les points de départ, mais vous devez effectuer le dernier appel. Il s’agit de données KHI, qui sont utilisées par Microsoft. Voir l’affiche.

Pour **réussir** dans le jeu, utilisez les cartes fournies à la place des requêtes de données et de systèmes Khi. Si au début du jeu vous n’avez pas dessiné de carte liée à un aspect donné, vous pouvez continuer à le passé. S’il existe une carte appropriée, faites rouler le dé. Si vous avez renvoyé le numéro indiqué sur la carte, c’est que vous avez réussi. Si vous avez répété le numéro indiqué, vous devez dessiner une autre carte à partir du jeu. S’il s’agit d’une carte indiquant qu’il est nécessaire de rouler au moins deux joueurs, ils doivent se rouler correctement.

Pour **tenir** compte du jeu, spécifiez le plan de gestion des services à haute voix en ce qui concerne cet aspect de l’environnement Lync.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Guide du réseau Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[Principaux indicateurs d’intégrité : notions de base pour la mise à jour des serveurs Lync sains](http://go.microsoft.com/fwlink/?linkid=391838)  
[Méthodologie de qualité d’appel Lync](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

