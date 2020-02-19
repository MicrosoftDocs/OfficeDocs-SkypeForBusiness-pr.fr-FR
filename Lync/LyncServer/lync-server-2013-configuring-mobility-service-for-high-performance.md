---
title: 'Lync Server 2013 : configuration du service de mobilité pour de hautes performances'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d09fb2ab6a122e8d25902bdc156f3870714f8dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a>Configuration du service de mobilité pour de hautes performances dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-17_

<div>


> [!IMPORTANT]  
> Cette rubrique s’applique uniquement au service de mobilité Lync Server 2013 (MCX) et ne s’applique pas à la UCWA (Unified Communications Web API), telle qu’elle est fournie dans les mises à jour cumulatives pour Lync Server 2013 : février 2013.



</div>

Lorsque vous installez le service de mobilité (MCX) sur Internet Information Services (IIS) 7,5, le programme d’installation de Mobility service configure certains paramètres de performances sur le serveur frontal. Nous vous recommandons d’utiliser les services Internet (IIS) 7.5 pour la mobilité. Ceux-ci affectent la quantité maximale de demandes utilisateur simultanées et la quantité maximale de threads autorisés pour le service de mobilité.

Voici les paramètres de performances :

<div>

## <a name="settings-for-mcx-on-iis-75"></a>Paramètres pour MCX sur IIS 7,5

1.  **maxConcurrentThreadsPerCPU** a la valeur zéro (0).

2.  **maxConcurrentRequestsPerCPU** a la valeur zéro (0).

3.  Le modèle de processus ASP.NET est AutoConfig (pour les services Internet (IIS) 7.5 uniquement).

4.  La limite de file d’attente HTTP.sys a la valeur 1 000 (par défaut).

</div>

</div>

<span> </span>

</div>

</div>

</div>

