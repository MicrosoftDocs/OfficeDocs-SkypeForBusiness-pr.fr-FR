---
title: 'Lync Server 2013 : Déploiement de sites de succursale'
TOCTitle: Déploiement de sites de succursale
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398217(v=OCS.15)
ms:contentKeyID: 49296336
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Déploiement de sites de succursale dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

Les utilisateurs d’un site de succursale obtiennent la plupart des fonctionnalités de Lync Server 2013 du serveur se trouvant sur le site central auquel le site de succursale est associé. Chaque site de succursale est associé à exactement un site central. Pour transmettre les appels vers et depuis le réseau téléphonique commuté public, le site de succursale peut avoir besoin de ce qui suit :

  - une passerelle RTC et si possible un serveur de médiation ;

  - une jonction SIP ;

  - une infrastructure vocale existante avec PBX (autocommutateur privé) ;

  - un Survivable Branch Appliance ;

  - un serveur Survivable Branch Server

Les sites de succursale avec un Survivable Branch Appliance ou un serveur Survivable Branch Server sont plus résistants, lorsqu’une panne de réseau étendu (WAN) ou du site central se produit, que les sites de succursale ne disposant d’aucune de ces solutions. Par exemple, dans un site où un Survivable Branch Appliance ou un serveur Survivable Branch Server est déployé, les utilisateurs peuvent toujours effectuer et recevoir des appels RTC si le réseau qui relie le site de succursale au site central est en panne. Un autre moyen de rendre un site de succursale résistant consiste à utiliser une passerelle RTC ou une jonction SIP avec un déploiement complet de Lync Server sur le site de succursale.

Pour plus d’informations sur le déploiement de site de succursale approprié pour votre organisation et sur les conditions préalables et les points à prendre en compte en vue de la planification du déploiement, reportez-vous à [Planification de la connectivité RTC dans Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) et à [Planification de la résistance vocale d’un site de succursale dans Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) dans la documentation de planification.

## Dans cette section

  - [Connectivité RTC sur un site de succursale dans Lync Server 2013](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

