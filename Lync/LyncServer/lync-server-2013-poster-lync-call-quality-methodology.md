---
title: Lync Call Quality Methodology
TOCTitle: 'Affiche : Lync Call Quality Methodology'
ms:assetid: a069f4e5-4f80-4f0f-8657-2e07276b6b41
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn593600(v=OCS.15)
ms:contentKeyID: 61084843
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Call Quality Methodology

 

_**Dernière rubrique modifiée :** 2016-12-08_

Le présent article complète l'affiche [Lync Call Quality Methodology](http://go.microsoft.com/fwlink/?linkid=391841), que vous pouvez télécharger à partir du Centre de téléchargement.

![Affiche décrivant le processus CQM](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Affiche décrivant le processus CQM")

Vous pouvez utiliser cette affiche pour en apprendre davantage sur CQM (Call Quality Methodology), la méthodologie de la qualité d'appel pour Lync 2013 et 2010, qui vous aide à trouver et à éliminer les problèmes qui affectent la qualité des appels et l'expérience utilisateur pour les implémentations Lync incluant des fonctionnalités Voix Entreprise. CQM est une nouvelle infrastructure de gestion de service et de dépannage qui permet de mieux concentrer les efforts sur l'amélioration des services Voix Entreprise dans Lync. Dans cet article, vous pouvez en savoir plus sur CQM, les types de serveurs et de solutions qui sont surveillés, et ce qu'il faut faire avec les données de télémétrie recueillies.

Si vous avez des questions sur la façon d'utiliser CQM, vous pouvez les soumettre à cqmfeedback@microsoft.com.

Cette affiche explique les points suivants :

  - Qu'est-ce Lync CQM ?

  - Priorisation : exécuter des requêtes de tendance

  - PCD

  - Géré/Non géré

  - Itinéraire du site des serveurs

  - Itinéraire du dernier kilomètre

  - Itinéraire des points de terminaison

  - Gestion des services

  - Règles du jeu de plateau

## Qu'est-ce Lync CQM ?

CQM (Call Quality Methodology) est une nouvelle infrastructure de gestion de service et de dépannage qui permet de mieux concentrer les efforts sur l'amélioration des services Voix Entreprise dans Lync. CQM réduit les efforts nécessaires pour assurer la qualité des appels et la satisfaction des utilisateurs pour des services Voix Entreprise. CQM est expliqué plus en détail dans le [Lync Server Networking Guide](http://go.microsoft.com/fwlink/p/?linkid=390677). Cet article et l'affiche présentent un résumé de ce contenu.

CQM répartit le dépannage du système en trois chemins ou « itinéraires » : l'itinéraire du site serveurs, qui examine tous les serveurs et les liens qui les relient, l'itinéraire des points de terminaison, qui examine les périphériques des utilisateurs et les supports utilisés pour acheminer les appels, et l'itinéraire du dernière kilomètre, qui concerne l'intégration des appels du réseau téléphonique commuté traditionnel.

Chaque itinéraire est divisé en plusieurs segments relatifs à un domaine ou un sujet spécifique et, au niveau de chaque segment, des définitions sont établies pour le niveau de qualité acceptable, les mesures qui sont prises pour atteindre ce niveau de qualité et un plan de gestion du service est mis en place pour maintenir ce niveau de qualité avant de passer au sujet suivant.

L'affiche présente Lync CQM comme un jeu de plateau à trois joueurs, chacun d'eux empruntant l'un des itinéraires. Les cartes fournies dans le téléchargement servent à simuler des obstacles à la qualité des appels qui doivent être surmontés. Des conseils et des suggestions concernant les objectifs et les moyens de les atteindre sont inclus le long des trois itinéraires, ainsi que des instructions de priorisation pour l'itinéraire à suivre d'abord dans les applications réelles (dans le jeu, les trois itinéraires sont traités en parallèle).

Comment CQM fonctionne-t-il dans les versions précédentes de Lync ? CQM est une nouveauté de Lync 2013, mais l'essentiel de cette fonctionnalité peut être adapté à Lync 2010. CQM peut fonctionner dans une certaine mesure avec Microsoft Office Communicator, mais cette possibilité n'a pas été testée et n'est pas prise en charge.

Si vous avez des questions sur la façon d'utiliser CQM, vous pouvez les soumettre à cqmfeedback@microsoft.com.

## Priorisation : exécuter des requêtes de tendance

La première étape dans CQM consiste à exécuter chacune des requêtes de tendance pendant deux semaines, puis à analyser les résultats obtenus. Priorisez l'action corrective par le plus grand contributeur de flux et les zones gérées (celles que vous contrôlez). Si les requêtes MCU audio/vidéo (AV MCU) ou les requêtes de correction donnent des résultats insuffisants, choisissez l'itinéraire rouge ou Site serveurs. Si les requêtes filaires ou sans fil donnent des résultats insuffisants, prenez l'itinéraire bleu ou l'itinéraire du dernier kilomètre. Si les requêtes VPN ou externes donnent des résultats insuffisants, prenez l'itinéraire vert ou l'itinéraire des points de terminaison.

Après avoir choisi un itinéraire pour commencer, définissez un objectif pour chaque zone (Déclarer), travaillez à atteindre cet objectif (Réaliser), puis implémentez les procédures pour maintenir votre objectif (Maintenir). Vous pouvez également utiliser cette affiche comme un jeu pour comprendre les principes sous-jacents de CQM.

## PCD

L'outil PCD (PreCall Diagnostics) vous aide à identifier et à diagnostiquer les problèmes dans votre réseau de périmètre (la base de données QoE ne recueille pas d'informations sur votre réseau de périmètre ou Edge) et aussi à résoudre les problèmes des connexions dans le dernier kilomètre. L'outil est disponible à la fois comme application Windows 8 Modern et comme application de bureau Windows à l'adresse http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88.

## Géré/Non géré

Le déploiement de Lync Server et l'infrastructure de réseau peuvent généralement être divisés en espaces gérés et non gérés. L'espace géré comprend l'ensemble de votre réseau câblé interne et l'infrastructure de serveurs. L'espace non géré est l'infrastructure sans fil et l'infrastructure de réseau externe.

Cette distinction accroît la clarté de vos données et permet à votre organisation de se concentrer sur les charges de travail qui ont un impact mesurable sur les communications vocales des utilisateurs et la qualité vidéo. Les utilisateurs ont une autre attente en termes de qualité si l'appel est passé sur les infrastructures que vous possédez (gérez) par rapport à l'infrastructure qui est en partie sous le contrôle d'une autre entité (non gérée). Cela ne veut pas dire que les utilisateurs sans fil sont livrés à eux-mêmes et à leurs propres terminaux pour avoir d'excellentes expériences Lync Server.

Pour améliorer la qualité de la voix dans l'espace non géré, vous devez avoir une haute qualité dans l'espace géré. Que le sans fil (Wi-Fi) soit considéré comme un espace géré ou non géré dépend de votre organisation. Les techniques pour obtenir un environnement sain sont différentes dans les deux espaces, comme le sont les solutions.

## Itinéraire du site serveurs

Le segment 1 de l'itinéraire du site serveurs s'applique aux serveurs réels dans l'implémentation Lync. Collectez les données KHI concernant à la fois le serveur lui-même et son rôle dans l'implémentation, puis analysez le résultat obtenu. Si une action s'impose, corrigez les problèmes trouvés. Pour plus de détails sur ce sujet, consultez l'article sur les [Key Health Indicators](lync-server-2013-poster-key-health-indicators.md) qui complète l'affiche KHI.

Le segment suivant concerne les flux de média entre le serveur AV MCU et le serveur de médiation. Commencez par déterminer vos valeurs cibles pour les seuils de flux insuffisants. Les flux insuffisants sont généralement PacketLossRate \> .01 ou PacketLossRateMax \> .05. Un autre objectif souhaitable est PoorStreamsRatio \< 2 %. Ensuite, utilisez les requêtes détaillées pour trouver les paires de serveurs AVMCU et de médiation présentant des flux insuffisants, examinez la cause des flux insuffisants, observez le matériel réseau dans les chemins des flux insuffisants, corrigez les flux insuffisants, puis définissez la configuration optimale ou « en or » pour l'équipement réseau. Pour maintenir votre réalisation, implémentez les processus et les outils nécessaires pour gérer l'écart de configuration et signaler les nouvelles zones problématiques.

Ensuite, examinez les flux de média entre le serveur de médiation et la passerelle du réseau téléphonique public commuté (RTPC). Commencez par déterminer vos valeurs cibles pour les seuils de flux insuffisants. Les flux insuffisants sont généralement PacketLossRate \> .01 ou PacketLossRateMax \> .05. Un autre flux souhaitable est PoorStreamsRatio \< 2 %. Ensuite, utilisez des requêtes détaillées pour trouver des paires de serveurs de médiation et de passerelle présentant des flux insuffisants, recherchez la cause des flux insuffisants, examinez le matériel réseau dans les chemins des flux insuffisants, corrigez les flux insuffisants, et définissez la configuration optimale ou « en or » pour les équipements de réseau. Pour maintenir votre réalisation, implémentez les processus et les outils nécessaires pour gérer les écarts de configuration et signaler les nouvelles zones problématiques.

Enfin, examinez les métriques d'intégrité de votre passerelle RTPC. Identifiez les statistiques qui montrent l'intégrité et définissez des objectifs sur cette base. Aucune recommandation spécifique n'est fournie ici car de nombreuses passerelles différentes peuvent être utilisées. Une fois les objectifs établis, effectuez les corrections nécessaires pour atteindre l'objectif ; au cours de ce processus, vous allez probablement définir une configuration optimale ou « en or » pour la passerelle. Pour maintenir votre réalisation, implémentez les processus et les outils nécessaires pour gérer les écarts de configuration et signaler les nouvelles zones problématiques. Sachez que les mises à jour de microprogrammes et de logiciels peuvent modifier votre configuration ou vous amener à modifier la définition de la configuration « en or », alors abordez ces opérations avec précaution.

## Itinéraire du dernier kilomètre

Des deux façons permettant aux clients de se connecter au réseau, la méthode filaire doit fournir la plus haute qualité et par conséquent elle doit être votre priorité initiale pour les problèmes du dernier kilomètre. Utilisez la requête CQM Wired (LastMile\_0\_Wired) et les données de ratio des flux insuffisants qu'elle fournit. Nous suggérons de définir un objectif PoorStreamsRatio \< 5 % pour les sites avec \> 300 flux). Pour atteindre vos objectifs, corrigez les sous-réseaux classés du pire au meilleur et implémentez QoS.

Après avoir optimisé la qualité de vos connexions filaires, il est plus facile d'améliorer la qualité sans fil car l'infrastructure sans fil se trouve au-dessus du noyau câblé dans chaque emplacement. Les flux sans fil insuffisants dans un site disposant d'une bonne qualité filaire doivent être attribués aux composants sans fil spécifiques. La requête CQM Wireless (LastMile\_1\_Wireless) fonctionne sur une plage de dates et retourne tous les flux sans fil internes dans votre environnement depuis des clients Lync vers ou depuis des serveurs de conférence ou des serveurs de médiation. Nous vous suggérons de définir un objectif PoorStreamsRatio \< 5 % pour les sites avec \> 300 flux). Pour atteindre vos objectifs, corrigez les sous-réseaux classés du pire au meilleur, et implémentez QoS.

## Itinéraire des points de terminaison

Commencez vos investigations sur l'itinéraire des points de terminaison avec les casques et autres dispositifs connus pour produire une qualité acceptable lorsqu'ils sont utilisés avec Lync. (Nous vous suggérons de définir un objectif AvgSendListen MOS \> 3.6 pour les implémentations ayant plus de 100 flux.) Réalisez l'objectif en identifiant les périphériques problématiques et réparez-les ou remplacez-les.

Ensuite, examinez l'appareil ou votre PC traitant l'audio pour les appels de l'utilisateur final. Une mesure de qualité cible suggérée est AudioMic GlitchRate \> 1. Quand vous identifiez les configurations système optimales pour les systèmes des utilisateurs, définissez une configuration de PC « en or » comprenant les versions des pilotes.

Examinons maintenant le chemin réseau que suit un flux audio à partir d'un système de points de terminaison Lync, ce qui peut générer une mauvaise qualité audio. Si l'audio se déplace sur une connexion VPN, vous pourriez rencontrer des problèmes de latence. Si un client Lync interne ne peut pas établir un flux multimédia direct avec un autre client Lync interne pour un appel à deux parties ou un appel d'égal à égal, il se repliera sur un chemin qui relaie via un serveur Edge Lync, conduisant de nouveau à des problèmes de latence ainsi qu'à un risque accru de perte et de gigue. Nous vous conseillons de définir une mesure de qualité de 0 % média sur VPN. En effectuant des corrections pour atteindre l'objectif défini, identifiez les sous-réseaux problématiques et examinez les règles de pare-feu, les modélisateurs de paquets et autre configuration pertinente de l'équipement réseau.

Les paquets IP peuvent utiliser le protocole TCP (Transmission Control Protocol) ou USP (User Datagram Protocol). Le protocole TCP est optimal pour les flux de données. Le protocole UDP est sans connexion et est plus efficace pour le multimédia puisque les mécanismes de récupération de TCP ne peuvent pas traiter la perte dans le multimédia en temps réel. Lync préfère toujours UDP, mais revient à TCP si une session UDP ne peut être établie. Les sessions multimédias sur TCP présentent une moins bonne qualité par rapport à UDP. Nous recommandons une définition de la qualité de 0 % pour les connexions sur TCP. En effectuant des corrections pour atteindre l'objectif défini, identifiez les sous-réseaux problématiques et examinez les règles de pare-feu, les modélisateurs de paquets et autre configuration pertinente de l'équipement réseau.

## Gestion des services

La gestion des services est l'état final de CQM, et la destination des trois itinéraires. Pour maintenir de hauts niveaux de qualité pour les appels, surveillez ces points :

1.  **Utilisateurs** - Les activités de remédiation doivent montrer une augmentation mesurable de la satisfaction des utilisateurs. Vous pouvez mesurer cela en tickets de problèmes ou d'autres mécanismes de rétroaction. Vous pouvez également publier des mesures de qualité.

2.  **Processus** - Définissez des processus journaliers, hebdomadaires et mensuels pour opérationnaliser CQM. Le rythme de surveillance commence à une fréquence supérieure alors que vous effectuez la remédiation (journalière) et passe à une fréquence moindre (mensuelle) à mesure de la stabilisation.

3.  **Outils** - Identifiez les outils à la fois pour les mesures et les remédiations. Il peut être utile d'automatiser l'exécution des requêtes CQM à l'appui de vos processus. La remédiation peut nécessiter des outils supplémentaires, par exemple pour appliquer des configurations standardisées sur les éléments de réseau ou résoudre les problèmes de pertes dans de flux insuffisants.

## Règles du jeu de plateau

Vous pouvez utiliser cette affiche comme référence d'implémentation CQM ou comme jeu pour vous familiariser avec les concepts. Pour y jouer, vous avez besoin d'un dé à six faces et des cartes fournies. Une version téléchargeable des cartes est disponible pour impression sur des cartes de visite standards Avery 5871.

Le jeu implique 3 joueurs. Il y a trois itinéraires que les joueurs peuvent emprunter pour obtenir la qualité voulue et atteindre l'état du centre de gestion des services : site serveurs, point de terminaison et dernier kilomètre. Des arrêts sont prévus le long de chaque itinéraire pour vous permettre de déclarer les objectifs de qualité, de réaliser les objectifs et de maintenir l'aspect de votre système. Placez les cartes dans la zone indiquée ci-dessus, puis tirez 5 cartes. Examinez les cartes que vous avez tirées et placez-les sur le segment pertinent du plateau. Chaque joueur déplace les cartes sur son itinéraire pas à pas, en déclarant les objectifs de qualité, en réalisant ces objectifs et en maintenant les niveaux de service. Le jeu se termine quand tous les joueurs atteignent l'état Gestion des services du centre. Des règles plus détaillées sont fournies lors du téléchargement des cartes du jeu.

Pour **déclarer** un objectif de qualité, passez en revue les paramètres applicables à cet objectif, et dites à voix haute ce que vous pouvez et ne pouvez pas accepter. Nous avons recommandé des points de départ, mais vous devez prendre la décision finale. Seule exception : les données KHI, où les normes établies par Microsoft doivent être utilisées. Consultez l'affiche complémentaire KHI.

Pour **réaliser** vos objectifs dans le jeu, utilisez les cartes fournies à la place des données KHI et des requêtes du système. Si, au début du jeu, vous n'avez pas tiré une carte relative à un aspect donné, vous pouvez continuer en l'ignorant. Si une carte est pertinente, lancez le dé. Si le dé retombe sur le numéro indiqué sur la carte, vous avez gagné. Sinon, vous devez tirer une autre carte. Si la carte indique que deux ou plusieurs joueurs doivent lancer le dé, ils doivent alors tous le lancer.

Pour **maintenir** vos objectifs dans le jeu, indiquez à voix haute le plan de gestion du service concernant cet aspect de l'environnement Lync.

## Voir aussi

#### Autres ressources

[Lync Server Networking Guide](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](http://go.microsoft.com/fwlink/?linkid=391838)  
[Lync Call Quality Methodology](http://go.microsoft.com/fwlink/?linkid=391841)

