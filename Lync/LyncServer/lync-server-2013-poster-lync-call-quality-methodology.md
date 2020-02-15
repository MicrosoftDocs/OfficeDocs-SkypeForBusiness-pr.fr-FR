---
title: 'Lync Server 2013 : affiche : méthodologie de qualité des appels Lync'
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
ms.openlocfilehash: 849e74fb4857dd7b3ab98b8a8efd9c3ce3781e35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-call-quality-methodology-in-lync-server-2013"></a>Méthodologie de qualité des appels Lync dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-06-24_

Cet article est un complément de l’affiche de [méthodologie de qualité des appels Lync](http://go.microsoft.com/fwlink/?linkid=391841) , que vous pouvez télécharger à partir du centre de téléchargement.

![Affiche décrivant le processus CQM](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Affiche décrivant le processus CQM")

Vous pouvez utiliser cette affiche pour en savoir plus sur CQM, la méthodologie de qualité des appels pour Lync 2013 et 2010, qui vous permet de rechercher et d’éliminer les problèmes affectant la qualité des appels et l’expérience utilisateur pour les implémentations de Lync qui incluent les fonctionnalités voix entreprise. La méthodologie de qualité des appels est une nouvelle infrastructure de résolution des problèmes et de gestion des services qui peut mieux se concentrer sur les services voix entreprise dans Lync. Dans cet article, vous pouvez en savoir plus sur CQM, les types de serveurs et de solutions qui sont surveillés et la marche à suivre pour les données de télémétrie collectées.

Si vous avez des questions sur l’utilisation de CQM, vous pouvez soumettre vos questions à cqmfeedback@microsoft.com.

L’affiche décrit les domaines suivants :

  - Qu’est-ce que Lync CQM ?

  - Priority : exécuter des requêtes de tendance

  - PCD

  - Géré/non géré

  - Route de la plante serveur

  - Route des derniers milles

  - Route des points de terminaison

  - Gestion des services

  - Règles de jeu de tableau de bord

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a>Qu’est-ce que Lync CQM ?

La méthodologie de qualité des appels est une nouvelle infrastructure de résolution des problèmes et de gestion des services qui peut mieux se concentrer sur les services voix entreprise dans Lync. Lorsque vous utilisez CQM, vous devez réduire les efforts pour garantir la qualité des appels et la satisfaction des utilisateurs pour les services voix entreprise. CQM est plus entièrement expliqué dans la [méthodologie de qualité des appels](http://go.microsoft.com/fwlink/p/?linkid=615208). Cet article et l’affiche sont des résumés de ce contenu.

CQM divise le dépannage du système en trois chemins ou « routes ». Ce sont les suivants : la route de plante serveur, qui examine les serveurs et les liens entre elles, les points de terminaison, qui examinent les appareils et les supports utilisateur utilisés pour transporter des appels, et le dernier kilomètre, qui traite de l’intégration des appels réseau téléphoniques commutés traditionnels.

Chaque route est divisée en plusieurs segments liés à un domaine ou à un sujet spécifique, et chaque définition de segment est définie sur ce qui est un niveau de qualité acceptable, des actions sont entreprises pour atteindre ce niveau de qualité et un plan de gestion des services est mis en place pour maintenir ce niveau de qualité avant de passer à la rubrique suivante.

L’affiche présente Lync CQM en tant que jeu de cartes pour trois joueurs, chacun d’eux passant par l’une des routes. Les cartes comprises dans le téléchargement sont utilisées pour simuler des obstacles à la qualité des appels qui doivent être résolus. Les conseils et suggestions concernant les objectifs, ainsi que la façon de les atteindre, sont inclus dans les trois chemins d’accès, ainsi que des instructions de définition des priorités pour lesquelles les routes doivent être abordées dans les applications réelles (dans le jeu, les trois routes sont traitées en parallèle).

Comment fonctionne CQM dans les versions antérieures de Lync ? CQM est une nouveauté de Lync 2013, mais la plus grande partie peut être adaptée pour être utilisée avec Lync 2010. CQM peut fonctionner avec Microsoft Office Communicator, mais cela n’est pas testé et n’est pas pris en charge.

Si vous avez des questions sur l’utilisation de CQM, vous pouvez soumettre vos questions à cqmfeedback@microsoft.com.

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a>Priority : exécuter des requêtes de tendance

La première étape dans CQM consiste à exécuter chacune des requêtes de tendance pendant deux semaines, puis à analyser les résultats. Hiérarchiser les actions correctives par le collaborateur de flux le plus important, le ratio de flux de flux le plus élevé et les zones gérées (que vous contrôlez).Si l’unité de contrôle d’émission audio/vidéo (MCU) ou les requêtes de médiation affichent des résultats médiocres, commencez par la route de la plante du serveur ou du rouge.Si les requêtes filaires ou sans fil affichent des résultats médiocres, commencez par le bleu ou le dernier kilomètre.Si le réseau privé virtuel (VPN) ou les requêtes externes affichent des résultats médiocres, commencez par le vert ou le point de terminaison route.

Une fois que vous avez choisi une route avec laquelle commencer, définissez une cible pour chaque domaine (Assert), travaillez pour atteindre cette cible (atteindre), puis implémentez des procédures pour rester sur la cible (maintenance). Vous pouvez également utiliser cette affiche pour comprendre les principes qui sous-tendent CQM.

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a>PCD

L’outil de diagnostics de préversion (PCD) vous aide à identifier et à diagnostiquer les problèmes dans votre réseau de périmètre (la base de données QoE ne collecte pas d’informations sur votre serveur Edge ou réseau de périmètre), ainsi que la résolution des problèmes de connexion au cours du dernier kilomètre. L’outil est disponible à la fois en tant qu’application moderne Windows 8 ou application de http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88Bureau Windows à l’adresse.

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a>Géré/non géré

L’infrastructure de réseau et de déploiement Lync Server peut généralement être divisée en espaces gérés et non managés. L’espace géré inclut l’ensemble de votre réseau câblé et de votre infrastructure de serveur. L’espace non géré est l’infrastructure sans fil et l’infrastructure réseau externe.

Cette distinction augmente la clarté de vos données et permet à votre organisation de se concentrer sur les charges de travail qui auront un impact mesurable sur la qualité vocale et vidéo de vos utilisateurs. Les utilisateurs ont des attentes différentes de la qualité si l’appel est passé sur l’infrastructure dont vous êtes propriétaire (géré) et sur l’infrastructure qui est partiellement sous le contrôle d’une autre entité (non gérée). Ceci ne signifie pas que les utilisateurs sans fil sont laissés à leurs propres appareils pour avoir des expériences Lync Server excellentes.

Pour améliorer la qualité des communications vocales dans l’espace non géré, vous devez disposer d’une qualité élevée dans l’espace géré. Si la connexion sans fil (Wi-Fi) est considérée comme gérée ou non gérée, c’est à votre organisation. Les techniques permettant d’obtenir un environnement sain sont différentes dans les deux espaces, à l’instar des solutions.

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a>Route de la plante serveur

Le segment 1 de la route de la plante serveur adresse les serveurs réels dans l’implémentation Lync. Recueillez des données KHI sur le serveur lui-même et son rôle dans l’implémentation et analysez le résultat. Si l’action est justifiée, corrigez les problèmes détectés. Pour plus d’informations sur cette rubrique, consultez l’article relatif aux [indicateurs d’intégrité clés dans Lync Server 2013](lync-server-2013-poster-key-health-indicators.md) qui accompagne l’affiche Khi.

Le segment suivant résout les flux multimédia entre le serveur MCU AV et le serveur de médiation. Commencez par déterminer vos cibles pour les seuils de flux de flux médiocres. Les flux de mauvaise qualité \> sont généralement PacketLossRate \> . 01 ou PacketLossRateMax. 05. Une autre cible intéressante est \< PoorStreamsRatio 2%. Ensuite, utilisez des requêtes détaillées pour trouver des paires de serveurs AVMCU et de médiation avec des flux médiocres, examiner la cause de flux médiocres, examiner l’équipement réseau dans les chemins de flux médiocres, corriger les flux médiocres et définir la configuration optimale ou « Gold » pour le réseau installations. Pour maintenir votre réalisation, implémentez des processus et des outils permettant de gérer la dérive de la configuration et de signaler de nouveaux problèmes.

Ensuite, examinez les flux de médias entre le serveur de médiation et la passerelle RTC (réseau téléphonique commuté). Commencez par déterminer vos cibles pour les seuils de flux de flux médiocres. Les flux de mauvaise qualité \> sont généralement PacketLossRate \> . 01 ou PacketLossRateMax. 05. Une autre cible intéressante est \< PoorStreamsRatio 2%. Ensuite, utilisez des requêtes détaillées pour trouver des paires serveur de médiation et passerelle avec des flux médiocres, rechercher la cause de flux médiocres, examiner l’équipement réseau dans les chemins de flux médiocres, corriger les flux médiocres et définir la configuration optimale ou « Gold » pour le réseau installations. Pour maintenir votre réalisation, implémentez des processus et des outils permettant de gérer la dérive de la configuration et de signaler de nouveaux problèmes.

Enfin, examinez les mesures d’intégrité de votre passerelle PSTN. Identifiez les statistiques qui affichent l’état de santé et définissez les cibles. Aucun guide spécifique n’est fourni ici, car il est possible d’utiliser plusieurs passerelles. Une fois les cibles établies, corrigez-les si nécessaire pour obtenir la cible ; dans le processus, vous définirez probablement une configuration « Gold » ou optimale pour la passerelle. Pour maintenir votre réalisation, implémentez des processus et des outils permettant de gérer la dérive de la configuration et de signaler de nouveaux problèmes. N’oubliez pas que les mises à jour logicielles et de microprogramme peuvent modifier votre configuration ou vous amener à modifier la définition de la configuration « Gold », donc approchez-vous de ces activités avec précaution.

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a>Route des derniers milles

Parmi les deux façons de se connecter au réseau, les clients câblés doivent fournir la meilleure qualité et correspondre à votre priorité initiale pour les problèmes de dernier kilomètre. Utilisez la requête filaire CQM (LastMile\_0\_filaire) et les données de ratio de flux médiocres qu’elle fournit. Nous vous suggérons de définir \< une cible PoorStreamsRatio 5% \> pour les sites avec 300 flux de test). Pour atteindre vos objectifs, corrigez les sous-réseaux ordonnés de pire à meilleur et implémentez QoS.

Une fois que vous avez optimisé la qualité de vos connexions câblées, l’amélioration de la qualité du réseau sans fil devient plus facile car l’infrastructure sans fil se trouve sur le cœur de chaque emplacement. Des flux de communication sans fil médiocres dans un site de bonne qualité filaire doivent être attribués aux composants sans fil spécifiques. La requête sans fil CQM (\_LastMile\_1 sans fil) fonctionne sur une plage de dates et renverra tous les flux de communication sans fil internes de votre environnement à partir de clients Lync vers ou à partir de serveurs de conférence ou de serveurs de médiation. Nous vous suggérons de définir \< une cible PoorStreamsRatio 5% \> pour les sites avec 300 flux de test). Pour atteindre vos objectifs, corrigez les sous-réseaux ordonnés de pire à meilleur et implémentez QoS.

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a>Route des points de terminaison

Commencez des demandes de points de terminaison avec les casques et autres appareils connus pour produire une qualité acceptable lorsqu’ils sont utilisés avec Lync. Nous vous suggérons une cible \> AvgSendListen MOS 3,6 pour les implémentations avec plus de 100 flux.) Obtenez la cible en identifiant les périphériques problématiques, puis corrigez-les ou remplacez-les.

Ensuite, examinez le périphérique ou le PC traitant l’audio pour les appels des utilisateurs finaux. Une mesure de qualité cible suggérée est \<un AudioMicGlitchRate = 1. À mesure que vous identifiez les configurations système optimales pour les systèmes utilisateur, définissez une configuration PC « Golden » incluant des versions de pilotes.

Examinez maintenant le chemin d’accès réseau emprunté par un flux audio à partir d’un système de point de terminaison Lync, ce qui peut entraîner une mauvaise qualité audio. Si l’audio transite via une connexion VPN, vous pouvez voir des problèmes de latence. Si un client Lync interne ne peut pas établir un flux de contenu multimédia direct vers un autre client Lync interne pour un appel d’égal à égal ou deux ou égal à égal, il reviendra à un chemin de relais via un serveur Edge Lync, entraînant de nouveau des problèmes de latence et d’augmentation du potentiel pour perte et instabilité. Nous vous suggérons de définir une mesure de qualité de 0% Media sur VPN. Lors de la correction pour obtenir la cible que vous définissez, identifiez les sous-réseaux présentant un problème et examinez les règles de pare-feu, les modeleurs de paquets et les autres équipements réseau pertinents.

Les paquets IP peuvent utiliser le protocole TCP (Transmission Control Protocol) ou UDP (User Datagram Protocol). Le protocole TCP est optimal pour les flux de données. UDP est sans connexion et est plus efficace pour le trafic multimédia étant donné que les mécanismes de récupération TCP ne peuvent pas traiter les pertes en temps réel. Lync préfère toujours UDP, mais reprendra le protocole TCP s’il n’est pas possible d’établir une session UDP. Les sessions multimédias sur TCP présentent une qualité médiocre par rapport à UDP. Nous recommandons une définition de qualité de connexions 0% sur TCP. Lors de la correction pour obtenir la cible que vous définissez, identifiez les sous-réseaux présentant un problème et examinez les règles de pare-feu, les modeleurs de paquets et les autres équipements réseau pertinents.

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a>Gestion des services

La gestion des services est l’état final de CQM et la destination des trois routes. Pour maintenir des niveaux élevés de qualité des appels, surveillez les points suivants :

1.  **Les utilisateurs : les** activités de correction doivent montrer une augmentation mesurable de la satisfaction des utilisateurs. Vous pouvez mesurer cela par le biais de tickets de problème ou d’autres mécanismes de commentaires. Vous pouvez également publier des mesures de qualité.

2.  **Process** -définissez des processus quotidiens, hebdomadaires et mensuels pour l’exploitation de CQM. La surveillance du rythme commence à une fréquence supérieure pendant que vous effectuez une correction (quotidienne) et passe à une fréquence inférieure (mensuelle) à mesure que vous stabilisez.

3.  **Outils** : Identifiez les outils à la fois pour mesurer et corriger. Il peut s’avérer utile d’automatiser l’exécution des requêtes CQM pour prendre en charge vos processus. La correction peut nécessiter des outils supplémentaires, par exemple, pour appliquer des configurations standardisées aux éléments réseau ou à la perte de résolution des problèmes de flux médiocres.

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a>Règles de jeu de tableau de bord

Vous pouvez utiliser cette affiche comme référence à une implémentation d’CQM ou à un jeu pour mettre en pratique les concepts. Pour jouer, vous aurez besoin d’une puce de 1 6 face et des cartes fournies. Une version téléchargeable des cartes peut être imprimée sur des cartes de visite Avery 5871 standard.

Le jeu est de 3 joueurs. Les joueurs peuvent utiliser trois chemins pour obtenir la qualité souhaitée et atteindre l’état de la gestion des services centraux : usine serveur, point de terminaison et dernier kilomètre. Chaque chemin d’accès s’arrête dans la façon dont vous déclarez les objectifs de qualité, atteindre des objectifs et conserver un aspect de votre système. Placez les cartes dans la zone indiquée ci-dessus, puis dessinez 5 cartes. Passez en revue les cartes que vous avez dessinées et placez-les sur le segment de carte approprié. Chaque joueur parcourt les cartes sur leur chemin d’accès étape par étape, en déclarant les objectifs de qualité, en atteignant ces cibles et en conservant les niveaux de service. Le jeu est terminé lorsque tous les joueurs atteignent l’état de la gestion des services centraux. Des règles plus détaillées sont fournies avec le téléchargement de la carte de jeu.

Pour **affirmer** un objectif de qualité, passez en revue les paramètres applicables à cette cible et indiquez à quoi il s’agit et vous ne choisirez pas de l’accepter. Nous avons les points de départ recommandés, mais vous devez passer l’appel final. L’exception est des données KHI, où les normes établies par Microsoft doivent être utilisées. Consultez l’affiche KHI.

Pour **atteindre** le jeu, utilisez les cartes fournies à la place des requêtes de données et de système Khi. Si, au début de la partie, vous n’avez pas tracé de carte relative à un aspect donné, vous pouvez continuer à le faire. S’il existe une carte pertinente, faites rouler le dé. Si vous avez effectué le chiffrement sous le numéro indiqué sur la carte, vous avez réussi. Si vous remontez ou sur le numéro indiqué, vous devez dessiner une autre carte à partir du talon. Si la carte indique qu’au moins deux joueurs doivent effectuer un roulis, ils doivent tous être positionnés correctement.

Pour **tenir** compte du jeu, précisez le plan de gestion des services en fonction de cet aspect de l’environnement Lync.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Guide de mise en réseau Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[Indicateurs d’intégrité clés : base pour la maintenance des serveurs Lync sains](http://go.microsoft.com/fwlink/?linkid=391838)  
[Méthodologie de qualité des appels Lync](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

