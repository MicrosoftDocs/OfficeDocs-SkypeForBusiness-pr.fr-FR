---
title: 'Lync Server 2013 : surveillance des limites de capacité de mémoire du serveur'
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
ms.openlocfilehash: e5c9746240335b1c66606da24edf6ffa2a0e7bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a>Surveiller les limites de capacité de mémoire serveur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> Les informations dans cette rubrique faisant référence à la planification de la capacité uniquement aux clients mobiles Lync 2010 et au service de mobilité (MCX). La planification de la capacité de l’API Web de communications unifiées (UCWA), qui est utilisée par les clients mobiles Lync 2013, est fournie par l’outil de planification de Lync Server 2013.



</div>

Deux compteurs de performance de mobilité peuvent vous aider à déterminer votre utilisation actuelle et vous aider à planifier la capacité du service de mobilité Lync Server 2013 (MCX), ainsi que l’utilisation de la mémoire pour UCWA. Pour celle-ci, la catégorie de compteurs est **LS:WEB – UCWA**. Pour le service de mobilité (Mcx), les compteurs se trouvent dans la catégorie **LS:WEB - Service de communication mobile**. Les compteurs à surveiller sont les suivants :

  - **Nombre de sessions actives avec abonnements actifs aux informations de présence**, qui correspond au nombre actuel de points de terminaison enregistrés par l’intermédiaire de l’API UCWA ou du service de mobilité (Mcx) dont les abonnements aux informations de présence sont actifs (nombre d’utilisateurs mobiles toujours connectés) ;

  - **Nombre de sessions actives**, qui correspond au nombre actuel de points de terminaison enregistrés par l’intermédiaire de l’API UCWA ou du service de mobilité.

Si la différence entre les compteurs **Nombre de sessions actives avec abonnements actifs aux informations de présence** et **Nombre de sessions actives** reste minime au fil du temps, cela signifie que la plupart des utilisateurs d’appareils mobiles disposent d’un appareil toujours connecté, tel qu’un appareil mobile Android ou Nokia (pour Mcx uniquement). Les appareils UCWA toujours connectés incluent des appareils Apple et Android exécutant des clients mobiles Lync 2013. Si le compteur **Nombre de sessions actives** est beaucoup plus élevé que le compteur **Nombre de sessions actives avec abonnements actifs aux informations de présence**, cela indique qu’un nombre plus élevé d’utilisateurs emploient un appareil à points de terminaison en arrière-plan, tel qu’un appareil Apple iOS ou Windows Phone sous Mcx. (Windows Phone est le seul client mobile Lync 2013 qui s’inscrira comme suit).

Vous devez définir une limite sur le **nombre de sessions actives avec abonnements de présence actives** et compteurs de performance **actuellement nombre de sessions actives** en fonction de votre utilisation prévue, des résultats de la planification de la capacité et d’une analyse continue du service de mobilité et des autres compteurs de serveur front-end. Les limites que vous définissez doivent vous permettre d’évaluer la capacité des serveurs et de déclencher des alertes quand celle-ci est dépassée.

Pour déterminer les limites appropriées, vous devez d’abord déterminer la quantité de mémoire disponible sur le serveur frontal pour le service de mobilité. Surveillez les compteurs afin de déterminer le besoin de prévoir une capacité supplémentaire à l’aide de la formule suivante :

Mémoire totale utilisée par le service de mobilité MCX (Mo) = 164 + (400 + 134)/ \* 1024 le **nombre de sessions actives avec les abonnements de présence actives** + 400/1024 \* (nombre de**sessions actives** ) ****

<div>


> [!IMPORTANT]  
> Le calculateur de capacités de Microsoft Lync Server 2010 est une feuille de calcul préremplie avec toutes les formules permettant à un planificateur de déterminer quelles sont les conditions requises pour les serveurs, y compris le processeur, la mémoire et le disque dur. Vous pouvez télécharger la feuille de calcul et un document associé à l’adresse suivante :<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A>



</div>

Le serveur frontal doit disposer de suffisamment de mémoire pour prendre en charge le service de mobilité dans les situations de basculement. Vous pouvez contrôler la quantité de mémoire disponible sur le serveur frontal en utilisant le compteur de **\\mémoire Mo disponibles** ou en utilisant l’équation mentionnée plus haut, afin de planifier la quantité de mémoire que le service de mobilité devrait utiliser.

Si le volume de mémoire disponible sur le serveur frontal est inférieur à 1 500 Mo lorsque vous planifiez le nombre d’utilisateurs de mobilité attendus, vous devez ajouter davantage de matériel pour la prise en charge du service de mobilité. Pour plus d’informations, reportez-vous à la rubrique [surveillance de mobilité pour les performances dans Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md) dans la documentation sur les opérations.

<div>

## <a name="see-also"></a>Voir aussi


[Surveiller la mobilité des performances dans Lync Server 2013](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

