---
title: 'Lync Server 2013 : surveillance des limites de capacité de mémoire des serveurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45600ed9c822851c89b13cb776bbc58464decde0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a>Surveillance des limites de capacité de mémoire des serveurs dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> Les informations de cette rubrique qui font référence à la planification de la capacité ne concernent que les clients mobiles Lync 2010 et le service de mobilité (MCX). La planification de la capacité pour l’API Web de communications unifiées (UCWA), utilisée par les clients mobiles Lync 2013, est fournie par l’outil de planification Lync Server 2013.



</div>

Deux compteurs de performances de mobilité peuvent vous aider à déterminer votre utilisation actuelle et à vous aider à planifier la capacité du service de mobilité Lync Server 2013 (MCX), ainsi qu’à surveiller l’utilisation de la mémoire pour UCWA. Pour UCWA, la catégorie de compteurs est **ls : Web – UCWA**. Pour le service de mobilité (MCX), les compteurs appartiennent à la catégorie **ls : Web-service de communication mobile**. Les compteurs à surveiller sont les suivants :

  - Nombre de **sessions actuellement actives avec abonnements de présence actifs**, c’est-à-dire le nombre actuel de points de terminaison enregistrés via UCWA ou le service de mobilité (MCX) qui ont des abonnements de présence actifs (nombre d’utilisateurs mobiles toujours connectés)

  - Nombre de **sessions actuellement actives**, qui correspond au nombre actuel de points de terminaison enregistrés via UCWA ou le service de mobilité

Si la différence entre le **nombre de sessions actuellement actives et les abonnements de présence actifs** et le **nombre de sessions actuellement actives** est faible au fil du temps, cela signifie que la plupart des utilisateurs d’appareils mobiles disposent d’un appareil connecté toujours, tel qu’un appareil mobile Android ou Nokia (pour MCX uniquement). Les appareils UCWA toujours connectés incluent des appareils Apple et Android exécutant des clients mobiles Lync 2013). Si le **nombre de sessions actives** est largement supérieur **au nombre de sessions actuellement actives avec des abonnements de présence actifs**, cela indique que d’autres utilisateurs utilisent un périphérique de point de terminaison d’arrière-plan, tel qu’un périphérique iOS Apple ou Windows Phone sous MCX. (Windows Phone est le seul client mobile Lync 2013 qui s’inscrira comme suit).

Vous devez définir une limite sur le **nombre de sessions actuellement actives avec des abonnements de présence actifs** et des compteurs de performance de **nombre de sessions actuellement actives** en fonction de votre utilisation, des résultats de la planification de la capacité et de la surveillance continue du service de mobilité et d’autres compteurs de serveur frontal. Les limites que vous définissez doivent vous permettre d’évaluer la capacité du serveur et de déclencher des alertes lorsque la capacité est dépassée.

Pour déterminer les limites appropriées, vous devez d’abord déterminer la capacité de mémoire disponible sur le serveur frontal pour le service de mobilité. Surveillez les compteurs pour déterminer à quel moment vous devez planifier une capacité supplémentaire, en fonction de la formule suivante :

Quantité totale de mémoire utilisée par le service de mobilité MCX (Mo) = 164 + (400 + 134 \* )/1024 **nombre de sessions actuellement actives avec abonnements de présence actifs** + 400/1024 \* **(nombre de** sessions actuellement actives – **nombre de sessions actuellement actives avec abonnements de présence actifs**)

<div>


> [!IMPORTANT]  
> La calculatrice de capacité Microsoft Lync Server 2010 est une feuille de calcul pré-remplie avec toutes les formules qui permettent à un planificateur de déterminer les conditions requises pour les serveurs, notamment l’UC, la mémoire et le disque dur. Vous pouvez télécharger la feuille de calcul et un document associé à l’adresse suivante :<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A>



</div>

Le serveur frontal doit disposer de suffisamment de mémoire disponible pour prendre en charge le service de mobilité dans les situations de basculement. Vous pouvez surveiller la mémoire disponible sur le serveur frontal en utilisant le compteur **méga-\\octets disponibles** de la mémoire, ou en utilisant l’équation mentionnée ci-dessus, pour planifier la quantité de mémoire que le service de mobilité doit utiliser.

Si la quantité de mémoire disponible sur le serveur frontal est inférieure à 1 500 Mo lorsque vous planifiez le nombre d’utilisateurs de mobilité prévu, vous devez ajouter davantage de matériel pour prendre en charge le service de mobilité. Pour plus d’informations, reportez-vous à la rubrique [Monitoring Mobility for performance in Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) dans la documentation des opérations.

<div>

## <a name="see-also"></a>Voir aussi


[Surveillance de la mobilité pour les performances dans Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

