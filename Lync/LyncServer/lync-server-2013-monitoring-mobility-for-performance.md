---
title: 'Lync Server 2013 : surveillance de la mobilité pour les performances'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53bd9c3450617d4fd1db54b52efe0b0938c84c8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>Surveiller la mobilité des performances dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-14_

Le service de mobilité de Lync Server (MCX) et l’API Web de communications unifiées (UCWA) augmentent la charge de serveurs frontaux et de listes frontales. Les appareils mobiles qui maintiennent une connexion au serveur, même lorsque l’application mobile est réduite (par exemple, les appareils Android et Nokia exécutant Lync 2010 mobile, ainsi que les appareils Android et Apple exécutant Lync 2013 mobile, imposent un chargement supérieur aux appareils mettre fin à sa connexion au serveur lorsque l’application mobile est réduite ; À mesure que votre utilisation mobile augmente, vous devez surveiller les performances de mobilité afin d’identifier toute nécessité d’augmentation de la capacité.

Plusieurs limites influencent les performances de mobilité :

  - mémoire disponible ;

  - limite de file d’attente des demandes ;

  - connexions simultanées ;

  - longueur de la file d’attente des services Internet (IIS).

Il existe d’autres limitations sur les serveurs qui peuvent influer sur les performances de mobilité, à 12 connexions simultanées, authentifications, renouvellement de session et interruptions. Il n’est pas nécessaire de modifier ces valeurs maximales pour la plupart des déploiements.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Surveiller les limites de capacité de mémoire serveur dans Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [Surveiller l’utilisation du service de mobilité et de UCWA dans Lync Server 2013](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [Configuration d’un service de mobilité pour des performances élevées dans Lync Server 2013](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [Surveiller les fichiers journaux de suivi de requête IIS dans Lync Server 2013](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Compteurs de performance de mobilité dans Lync Server 2013](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

