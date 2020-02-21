---
title: 'Lync Server 2013 : surveillance des performances de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Lync Server 2013 performance
ms:assetid: 2acfd720-6120-4816-a2d4-30476bd5cd0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720910(v=OCS.15)
ms:contentKeyID: 63969592
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd46beb944f676b9916472cc39394d84ae205786
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-lync-server-2013-performance"></a>Surveillance des performances de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-15_

Les performances de Lync Server 2013 sont affectées par différents facteurs, tels que les profils utilisateur, l’architecture système, les logiciels, les composants matériels, les points d’intégration tiers tels que les passerelles et les équipements téléphoniques, la connectivité réseau et les performances, Windows La configuration et les performances du service Active Directory en plus des fonctionnalités du système d’exploitation Windows.

Les performances des déploiements Lync Server 2013 sont au cœur des logiciels et du matériel de serveur sur lesquels ils sont implémentés. Par exemple, un serveur frontal doit disposer de ressources matérielles suffisantes pour prendre en charge la charge utilisateur attendue (à court terme). Si un serveur frontal respectif est requis pour fournir des services aux utilisateurs de 10000, un serveur correctement configuré doit répondre aux exigences de charge attendues afin d’assurer la meilleure expérience possible de l’utilisateur final.

La surveillance des performances du serveur est donc extrêmement importante pour déterminer si l’infrastructure de serveur implémentée a des ressources matérielles appropriées pour les besoins de charge maximale quotidienne. La surveillance des performances du serveur permet d’identifier les goulets d’étranglement du système permettant aux administrateurs d’appliquer des mesures correctives avant que l’expérience de l’utilisateur final ne soit affectée. Les données de performances doivent être utilisées pour la planification de la capacité à long terme.

Bien que des informations détaillées sur tous les objets et compteurs de performance à observer soient liées à la [surveillance de Lync Server 2013 avec System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md), certains compteurs de performance que vous devez suivre peuvent fournir aux administrateurs un aperçu rapide des performances du système :

  - Pour suivre l’intégrité globale du système du serveur frontal, un bon point de départ est de vérifier le\\processeur% temps processeur. La valeur doit toujours être inférieure à 80%.

  - Pour suivre les performances de l’instance du logiciel de base de données SQL Server principale utilisée par le pool frontal, surveillez les compteurs de performance suivants :
    
    LC : USrv-00 – DBStore\\USrv – 002 – latence de la file d’attente (MS)
    
    LC : USrv – 00 – DBStore\\USrv – 0 04 – latence de la sproc (MS)
    
    Le serveur sain à l’état stable doit \<afficher les valeurs de latence 100 ms. Le mécanisme de limitation s’engage lorsque la latence atteint 12 secondes, ce qui signifie que le serveur frontal commence à limiter les demandes vers le système principal. Ainsi, les clients commencent à recevoir un message d’erreur du serveur 503.

  - Pour effectuer le suivi du temps de traitement sur le serveur frontal, surveillez le compteur suivant :
    
    LC : SIP-07-charger la\\gestion SIP-000-Durée moyenne de participation pour les messages entrants
    
    Il s’agit d’un autre mécanisme de limitation sur les serveurs frontaux, cette fois à partir du moment où le temps de traitement sur le serveur frontal est élevé. Si le temps de traitement moyen est supérieur à six secondes, le serveur passe en mode de limitation et n’autorise qu’une seule transaction en attente par connexion client.

  - Pour effectuer le suivi des problèmes de mémoire sur le serveur principal SQL, surveillez le compteur suivant :
    
    Espérance de vie de\\la page du gestionnaire de tampons SQL Server
    
    Une valeur faible, inférieure à 3600 secondes (avec une latence élevée des écritures/s et des pages de point de contrôle/s) indique la pression de la mémoire.

<div>

## <a name="additional-counters-to-view"></a>Compteurs supplémentaires à afficher

Il existe plusieurs compteurs clés qui sont de bonnes indicateurs d’intégrité globale à partir du serveur frontal. Il ne s’agit pas d’une liste complète et n’est pas destinée à identifier la cause principale. Ces compteurs vous permettront d’effectuer une vérification rapide de l’intégrité de votre serveur. Nous vous recommandons de vérifier ces compteurs sur chacun des serveurs du pool. Il est important de comprendre ce que sont ces valeurs de compteur lorsque votre serveur est intègre. Une configuration de référence doit être utilisée pour comprendre ce qui a changé lorsque l’expérience utilisateur est dégradée.

Le serveur frontal peut indiquer des problèmes qui peuvent être causés par des goulots d’étranglement ailleurs dans le système. Cela signifie qu’il s’agit de l’endroit le plus approprié pour commencer à examiner l’état général du système.

Deux compteurs supplémentaires à examiner en premier sont les suivants :

LC : USrv-00-DBStore\\USrv-002-latence de la file d’attente (MS)

LC : USrv-00-DBStore\\USrv-004-latence de la sproc (MS)

Le compteur de latence de file d’attente représente le temps passé par une demande dans la file d’attente et la latence de la sproc représente le temps nécessaire pour que le serveur principal traite la demande. Si, pour une raison quelconque, le disque, la mémoire, le réseau et le processeur sur le serveur principal rencontrent des problèmes, le compteur de latence de la file d’attente est élevé.

Elle peut également être élevée s’il y a une latence réseau élevée entre le serveur frontal et le serveur principal. Qu’est-ce que la latence de file d’attente est acceptable ?

Au bout de 12 secondes, les serveurs frontaux commencent à limiter les demandes aux serveurs principaux. Cela signifie que les serveurs commencent à renvoyer les serveurs trop occupés-503 Erreurs vers les clients. Un serveur sain doit avoir moins de 100 ms DBStore de latences de file d’attente à l’état stable, mais pendant les heures où le serveur vient de se mettre en ligne et que les utilisateurs se connectent en même temps, ce compteur peut être très élevé et vous pouvez même voir s’afficher plusieurs secondes.

Vous disposez peut-être d’une configuration à charge équilibrée, où un pool est déployé avec plusieurs serveurs frontaux et un équilibreur de charge configuré pour le « nombre minimal de connexions ». Dans ce cas, si un serveur frontal est redémarré, tous les utilisateurs qui tentent de se reconnecter sont pointés vers le serveur redémarré, car ce serveur aura moins de connexions par rapport aux autres membres du pool. Pendant ce temps, le serveur frontal respectif peut être surchargé tandis que les autres membres du pool ne le sont pas.

Nous vous recommandons d’effectuer la maintenance pendant les heures creuses afin de réduire l’impact sur les performances, car les utilisateurs ne seront pas concurrents de se connecter au serveur en même temps.

Si les deux compteurs de performance précédents sont élevés, le goulot d’étranglement le plus probable est le serveur principal SQL. Les éléments suivants à confirmer sont les suivants :

  - L’UC SQL Server est-elle trop élevée ? Par exemple, est-il supérieur à 80% ?

  - La latence du disque est-elle élevée ?

Dans un monde idéal, vous disposez de suffisamment de RAM pour que les bases de données RTC et RTCDYN soient en mémoire. Ensuite, la seule raison pour laquelle le serveur accède au disque est d’écrire dans les fichiers journaux et de purger les bases de données. Les tests ont montré que 12 Go de RAM suffisait pour les déploiements d’utilisateurs de 100 000. Cela suppose que les bases de données RTC et RTCDYN totalisent une taille inférieure à 12 Go. Si vos bases de données sont plus volumineuses, vous aurez peut-être besoin de davantage de mémoire.

Vous pouvez déterminer si votre serveur SQL Server requiert une RAM supplémentaire en consultant le compteur de performances durée de vie de la page du gestionnaire de tampons SQL Server. Une valeur inférieure à 3 600 indique une pression de la mémoire. Si vous disposez d’une quantité de mémoire suffisante, il est également recommandé de ne pas lire peu de lectures sur votre lecteur de base de données, car SQL Server doit uniquement écrire dans la base de données.

Il existe un mécanisme de limitation supplémentaire dans un serveur frontal Lync Server 2013 qui démarre si le temps de traitement du serveur est élevé. La limitation de la latence DBStore est uniquement activée si la latence de SQL Server est élevée. Un exemple dans lequel cette limitation est activée est le fait que le serveur frontal est lié au processeur.

Si la durée moyenne de traitement **(LC : SIP-07-load\\Management SIP-000-Durée moyenne de conservation pour les messages entrants)** sur le serveur dépasse six secondes, le serveur passe en mode de limitation et fournit uniquement aux utilisateurs une transaction en attente par connexion client. Une fois le temps de traitement de trois secondes écoulé, le serveur sort du mode de limitation et donne aux utilisateurs jusqu’à 20 transactions en suspens par connexion client. Chaque fois que le nombre de transactions sur une connexion spécifique dépasse le seuil indiqué ci-dessus, la connexion est marquée comme étant contrôlée par le flux. Le résultat est le serveur n’envoie aucune réception, et le compteur **LC : SIP-01-Peers\\de connexions contrôlées par flux** est incrémenté. Si une connexion reste dans un État contrôlé par flux pendant plus d’une minute, le serveur la ferme. Il effectue cette opération de manière tardive. Lorsqu’il a la possibilité de vérifier la connexion, il détermine s’il a été limité pendant trop longtemps et le ferme s’il a plus d’une minute.

Il s’agit des deux mécanismes de limitation et il existe un compteur de performances qui résume ce qui, le cas échéant, la limitation du serveur.

**LC : SIP-04-réponses\\sip-053-réponses 503 locales/s**

  - Le terme « local » dans le compteur précédent fait référence à des réponses générées localement.

  - Le code 503 correspond au serveur non disponible, où vous ne devez pas voir de codes 503 sur un serveur sain. Pendant la période qui suit le moment où un serveur vient d’être mis en ligne, il se peut que vous rencontriez des codes 503. Lorsque tous les utilisateurs se reconnectent et que le serveur revient à un état stable, il ne doit pas y avoir de codes 503 supplémentaires.

**LC : SIP-04-réponses\\sip-074-réponses 504 locales/s**

Ce compteur de performances indique des problèmes de connectivité avec d’autres serveurs et peut indiquer des échecs de connexion ou de retards de connexion. Si vous constatez 504 erreurs, le compteur de performances suivant doit être vérifié.

**LC : SIP-01-pairs\\SIP-017-envois en attente**

Ce compteur indique le nombre de demandes et de réponses sortantes en file d’attente. Si ce compteur est élevé, cela signifie que le problème ne se trouve probablement pas sur le serveur local. Notez que ce compteur peut être élevé s’il y a des problèmes de latence du réseau. Elle peut également indiquer des problèmes liés à la carte réseau locale, mais elle est plus probable en raison d’un problème sur un serveur distant. Ce compteur est très probablement élevé sur un serveur directeur lorsque le pool qu’il tente de communiquer est surchargé. La clé avec ce compteur est d’examiner les instances, pas seulement le total.

</div>

</div>

<span> </span>

</div>

</div>

</div>

