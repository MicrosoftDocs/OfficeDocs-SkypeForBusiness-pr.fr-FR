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
ms.openlocfilehash: f7859ea116e4ae63a5777e816c37893f11cf1c39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-lync-server-2013-performance"></a>Contrôle des performances de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-15_

La performance de Lync Server 2013 est affectée par divers facteurs, tels que les profils utilisateur, l’architecture système, les logiciels, les composants matériels, les points d’intégration tiers tels que les passerelles et les équipements de téléphonie, la connectivité réseau et les performances, Windows Configuration et performances du service Active Directory en plus des fonctionnalités du système d’exploitation Windows.

Le cœur des performances des déploiements de Lync Server 2013 est le logiciel serveur et le matériel sur lequel il est implémenté. Par exemple, un serveur frontal doit disposer de ressources matérielles suffisantes pour s’adapter à la charge attendue de l’utilisateur. Si un serveur frontal approprié est requis pour fournir des services aux utilisateurs de 10000, un serveur configuré de manière appropriée doit respecter les exigences de charge attendues pour garantir une utilisation optimale de l’utilisateur final.

Il est donc très important de surveiller les performances du serveur pour déterminer si l’infrastructure de serveur implémentée dispose de ressources matérielles appropriées pour les exigences de charge journalière. La surveillance des performances du serveur permet d’identifier les goulets d’étranglement du système permettant aux administrateurs d’appliquer une action corrective avant que l’utilisation de l’utilisateur final soit affectée. Les données de performances doivent être utilisées pour la planification de la capacité à long terme.

Bien que des informations détaillées sur l’ensemble des objets et compteurs de performance soient liés à l' [analyse de Lync Server 2013 avec System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md), certains compteurs de performance que vous devez suivre peuvent fournir aux administrateurs un affichage rapide des performances du système :

  - Pour effectuer le suivi de l’intégrité du système globale du serveur frontal, il est conseillé de vérifier le\\temps processeur% processeur. La valeur doit toujours être inférieure à 80%.

  - Pour suivre les performances de l’instance du logiciel de base de données SQL Server principal utilisée par le pool frontal, vous pouvez surveiller les compteurs de performance suivants :
    
    LC : USrv-00-DBStore\\USrv-002-latence de la file d’attente (MS)
    
    LC : USrv-00-DBStore\\USrv-0 04-latence de la sproc (MS)
    
    Le serveur opérationnel en état stable doit afficher \<des valeurs de latence MS 100. Le mécanisme de limitation s’engage lorsque la latence atteint 12 secondes, ce qui signifie que le serveur frontal commence à limiter les demandes à la fin. Le message d’erreur 503 serveur est alors trop occupé pour les clients.

  - Pour effectuer le suivi de la durée de traitement du serveur frontal, vous pouvez surveiller le compteur suivant :
    
    LC : SIP-07-le Management\\SIP-000-moyenne du temps d’attente pour les messages entrants
    
    Il s’agit d’un autre mécanisme de limitation sur les serveurs frontaux, qui démarre lorsque le temps de traitement du serveur frontal est élevé. Si le temps de traitement moyen est supérieur à six secondes, le serveur passe en mode de limitation et n’autorise qu’une seule transaction en attente par connexion client.

  - Pour connaître les problèmes de mémoire au niveau du serveur principal SQL, analysez le compteur suivant :
    
    Durée de vie de\\la page du gestionnaire de tampons SQL Server
    
    Une valeur basse, au-dessous de 3600 secondes (conjointement avec les écritures de la latence élevée/s et les pages de point de contrôle/s) indique la pression de la mémoire.

<div>

## <a name="additional-counters-to-view"></a>Compteurs supplémentaires à afficher

Il existe plusieurs compteurs clés qui sont bons indicateurs de fonctionnement global du serveur frontal. Il ne s’agit pas d’une liste complète et ne veut pas identifier la cause initiale. Ces compteurs vous permettent d’effectuer une vérification rapide de l’état de votre serveur. Nous vous recommandons de vérifier ces compteurs sur chacun des serveurs de la liste. Il est important de comprendre les valeurs de ces compteurs lorsque votre serveur est sain. Un planning de référence est requis pour connaître les modifications apportées lorsque l’utilisation de l’utilisateur est détériorée.

Le serveur frontal peut signaler des problèmes qui peuvent être causés par des goulets d’étranglement ailleurs dans le système. Cela signifie qu’il s’agit du meilleur endroit où commencer lorsque vous examinez l’état global du système.

Deux compteurs supplémentaires à vérifier en premier sont les suivants :

LC : USrv-00-DBStore\\USrv-002-latence de la file d’attente (MS)

LC : USrv-00-DBStore\\USrv-004-sproc (MS)

Le compteur de latence de la file d’attente représente la durée pendant laquelle une requête passée dans la file d’attente et la latence de la sproc représentent la durée nécessaire à la fin du traitement de la demande par le point de terminaison. Si, pour une raison quelconque, le disque, la mémoire, le réseau et le processeur se trouvent dans un problème, le compteur de latence de la file d’attente sera haut.

Cela peut également être élevé s’il y a une latence réseau élevée entre le premier et le dernier. Quelle est la latence de la file d’attente acceptable ?

Au bout de 12 secondes, les serveurs frontaux commencent à limiter les demandes aux serveurs dorsaux. Cela signifie que les serveurs retournent la disponibilité du serveur-erreurs 503 aux clients. Un serveur sain doit avoir moins de 100 ms DBStore des latences de files d’attente à l’état stable, mais au moment où le serveur est simplement connecté et que les utilisateurs se connectent en même temps, ce compteur peut être très élevé et vous pouvez même voir s’afficher plusieurs secondes.

Il est possible que vous disposiez d’une configuration à équilibrage de charge, dans laquelle un pool est déployé avec plusieurs serveurs frontaux et un équilibreur de charge configuré pour le moins de connexions. Dans ce cas, si vous redémarrez un serveur frontal, tous les utilisateurs qui essaient de se reconnecter seront dirigés vers le serveur redémarré, car celui-ci aura moins de connexions par rapport aux autres membres du pool. Pendant cette phase, le serveur frontal correspondant est susceptible d’être surchargé alors que les autres membres du pool ne le sont pas.

Nous vous recommandons d’effectuer la maintenance pendant les heures creuses afin de réduire l’impact sur les performances, car les utilisateurs ne seront pas en mesure de se connecter au serveur en même temps.

Si les deux compteurs de performance étaient élevés, le goulet d’étranglement le plus probable est le serveur principal SQL. Les éléments suivants à vérifier sont les suivants :

  - Le processeur SQL Server est-il trop élevé ? Par exemple, est-il supérieur à 80% ?

  - La latence du disque est-elle importante ?

Dans un monde idéal, vous disposez d’assez de RAM pour disposer de la mémoire de base de données RTC et RTCDYN. La seule raison pour laquelle le serveur accède au disque est d’écrire dans les fichiers journaux et de purger les bases de données. Les tests ont démontré que 12 Go de mémoire vive suffisent pour les déploiements d’utilisateurs 100 000. Cela part du principe que les bases de données RTC et RTCDYN sont au total dans une taille inférieure à 12 Go. Si votre base de données est plus grande, vous aurez éventuellement besoin de mémoire supplémentaire.

Vous pouvez déterminer si votre serveur SQL Server nécessite une RAM supplémentaire en passant en revue le compteur de performance de la durée de vie de la page du gestionnaire de tampons SQL Server. Une valeur inférieure à 3 600 indique la sollicitation de la mémoire. Il est également recommandé de ne pas lire sur votre lecteur de base de données si vous disposez de suffisamment de mémoire car SQL Server ne doit écrire que dans la base de données.

Il existe un mécanisme de limitation supplémentaire dans un serveur frontal Lync Server 2013 qui démarre si le temps de traitement du serveur est élevé. La limitation de latence DBStore est uniquement activée si la latence vers SQL Server est élevée. Par exemple, une telle limitation est activée, car le serveur frontal est lié au processeur.

Si la durée moyenne de traitement **(LC : SIP-07-gestion\\du chargement SIP-000-la durée de détention moyenne des messages entrants)** sur le serveur est supérieure à six secondes, le serveur bascule dans le mode de limitation et ne donne qu’aux utilisateurs une seule transaction en suspens par connexion client. Lorsque le délai de traitement passe à trois secondes, le serveur abandonne le mode de limitation et permet aux utilisateurs de plus de 20 transactions en suspens par connexion client. Chaque fois que le nombre de transactions sur une connexion spécifique dépasse le seuil ci-dessus, la connexion est marquée en tant que flux contrôlé. Le résultat est que le serveur ne publie aucun message reçu sur celui-ci et que le compteur de **connexions de\\flux de type LC : SIP-01-pairs** est incrémenté. Si une connexion reste dans un État à contrôle de flux pendant plus d’une minute, le serveur la ferme. Ce n’est pas le cas. Lorsqu’il dispose d’une opportunité de vérifier la connexion, il détermine s’il a été limité trop longtemps et le ferme s’il a plus d’une minute.

Ce sont les deux mécanismes de limitation et il existe un seul compteur de performance qui résume ce qui, le cas échéant, l’exécution d’une limitation du serveur.

**LC : SIP-04-réponses\\sip-053-réponses 503 locales/s**

  - Le terme « local » dans le compteur précédent fait référence aux réponses générées localement.

  - Le code 503 correspond au serveur non disponible, dans lequel vous ne pouvez pas voir les codes 503 sur un serveur sain. Au cours de la période qui prévient une fois le serveur connecté, vous pouvez voir des codes 503. Lorsque tous les utilisateurs se reconnectent et que le serveur revient à un état stable, il n’y a pas de codes 503 supplémentaires.

**LC : SIP-04-réponses\\sip-074-réponses 504 locales/s**

Ce compteur de performance indique des problèmes de connectivité avec d’autres serveurs et peut indiquer les échecs de connexion ou de retards de connexion. Si vous rencontrez des erreurs 504, le compteur de performance suivant doit être activé.

**LC : SIP-01-pairs\\SIP-017-envoie des éléments en suspens**

Ce compteur indique le nombre de demandes et de réponses sortantes en file d’attente. S’il s’agit d’un compteur de niveau élevé, le problème est probablement hors du serveur local. Notez que ce compteur peut être élevé s’il y a des problèmes de latence du réseau. Il peut également indiquer des problèmes avec la carte du réseau local, mais est plus probable en raison d’un problème sur un serveur distant. Ce compteur serait très probablement élevé sur un serveur directeur lorsque le pool avec lequel il tente de communiquer est surchargé. La clé avec ce compteur est d’examiner les instances, pas seulement le total.

</div>

</div>

<span> </span>

</div>

</div>

</div>

