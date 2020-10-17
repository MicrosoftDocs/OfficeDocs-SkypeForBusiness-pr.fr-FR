---
title: 'Lync Server 2013 : surveillance de la mobilité pour les performances'
description: 'Lync Server 2013 : surveillance de la mobilité pour des performances optimales.'
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
ms.openlocfilehash: d6c366542e88406df043ba1a782ee12cd64bd804
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562900"
---
# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>Surveillance de la mobilité pour les performances dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-14_

Le service Lync Server Mobility (MCX) et l’API Web Unified Communications (UCWA) augmentent la charge sur les serveurs frontaux et les pools frontaux. Les appareils mobiles qui maintiennent une connexion au serveur même lorsque l’application mobile est réduite, comme les appareils Android et Nokia exécutant Lync 2010 mobile, ainsi que les appareils Android et Apple exécutant Lync 2013 mobile, imposent une charge supérieure aux appareils qui mettent fin à leur connexion au serveur lorsque l’application mobile est réduite. À mesure que votre utilisation de la mobilité augmente, vous devez surveiller les performances de mobilité afin de déterminer si vous devez augmenter votre capacité.

Plusieurs limites influent sur les performances de mobilité :

  - Mémoire disponible

  - Limite de file d’attente de requêtes

  - Connexions simultanées

  - Longueur de file d’attente IIS

Les autres limites sur les serveurs pouvant influer sur les performances de mobilité sont un maximum de douze abonnements simultanés, des authentifications, des renouvellements de session et des arrêts. Il n’est pas nécessaire de modifier ces valeurs maximales pour la plupart des déploiements.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Surveillance des limites de capacité de mémoire des serveurs dans Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [Surveillance du service de mobilité et de l’utilisation d’UCWA dans Lync Server 2013](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [Configuration du service de mobilité pour de hautes performances dans Lync Server 2013](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [Surveillance des fichiers journaux de suivi des demandes IIS dans Lync Server 2013](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Compteurs de performances de mobilité dans Lync Server 2013](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

