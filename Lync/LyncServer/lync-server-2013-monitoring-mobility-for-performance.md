---
title: Surveillance des performances de mobilité dans Lync Server 2013
TOCTitle: Surveillance des performances de mobilité dans Lync Server 2013
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh690033(v=OCS.15)
ms:contentKeyID: 49298350
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Surveillance des performances de mobilité dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-14_

Le service de mobilité de Lync Server augmente la charge sur les serveurs frontaux et les pools de serveurs frontaux. Les appareils mobiles qui maintiennent une connexion au serveur même lorsque l’application mobile est réduite, tels que les appareils Android et Nokia, imposent une charge plus élevée que les appareils qui interrompent leur connexion au serveur lorsque l’application mobile est réduite. À mesure que votre utilisation mobile augmente, vous devez surveiller les performances de mobilité afin d’identifier toute nécessité d’augmentation de la capacité.

Plusieurs limites influencent les performances de mobilité :

  - mémoire disponible ;

  - limite de file d’attente des demandes ;

  - connexions simultanées ;

  - longueur de la file d’attente des services Internet (IIS).

Il existe d’autres limites sur les serveurs susceptibles d’avoir un impact sur les performances de mobilité : un maximum de douze connexions, authentifications, et renouvellements et fins de sessions. Il n’est pas nécessaire de modifier ces valeurs maximales pour la plupart des déploiements.

## Dans cette section

  - [Surveillance des limites de capacité de mémoire des serveurs](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [Surveillance de l’utilisation du service de mobilité et UCWA](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [Configuration du service de mobilité pour de hautes performances](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [Surveillance des fichiers journaux de suivi des demandes IIS](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Compteurs de performances de mobilité](lync-server-2013-mobility-performance-counters.md)

