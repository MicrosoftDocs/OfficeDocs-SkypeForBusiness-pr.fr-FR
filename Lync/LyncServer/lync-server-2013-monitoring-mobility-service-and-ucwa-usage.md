---
title: 'Lync Server 2013: analyse du service de mobilité et de l’utilisation de UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 758fef9e3f2c31bec88927c75b271808d5bbc43c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a>Surveiller l’utilisation du service de mobilité et de UCWA dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-14_

En continu, vous devez surveiller le processeur et la mémoire utilisés par le service de mobilité Lync Server (MCX) et l’API UCWA (Unified Communications Web API). Pour cela, vous pouvez utiliser l’un des éléments suivants :

**Pour l’API web de communications unifiées (UCWA) :**

  - Processus de travail **LyncUcwa** dans le gestionnaire des services Internet (IIS). Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;

  - les compteurs de performances **UC** et **Processeur**.

Pour la plupart des déploiements, l’utilisation du processeur par l’API UCWA doit en moyenne être inférieure à 15 %. L’utilisation de la mémoire doit être comprise dans les limites décrites dans [surveiller les limites de capacité de mémoire serveur dans Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances suivants pour aider à déterminer quand un serveur est surchargé de demandes :

  - **Ls: Web – limitation et authentification\\Web: nombre total de demandes de traitement**indiquant le nombre de demandes Web en attente sur le serveur. Lorsque ce compteur atteint 10 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».

  - **Demandes\\ASP.net en file d’attente** (doit toujours être zéro).

<div>


> [!NOTE]  
> Si vous atteignez ou dépassez ces valeurs, vous devez recommencer et recalculer la planification de la capacité pour obtenir le dimensionnement correct du processeur, du nombre de cœurs et de la mémoire pour les ordinateurs hébergeant les services Web.



</div>

**Pour le service de mobilité (Mcx) :**

  - Processus du travailleur **CSIntMcxAppPool** et **CSExtMcxAppPool** dans le gestionnaire des services Internet (IIS). Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;

  - les compteurs de performances **UC** et **Processeur**.

Pour la plupart des déploiements, l’utilisation du processeur par le service de mobilité doit en moyenne être inférieure à 15 %. L’utilisation de la mémoire doit être comprise dans les limites décrites dans [surveiller les limites de capacité de mémoire serveur dans Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances ASP.NET suivants pour aider à déterminer quand un serveur est surchargé de demandes :

  - Les **requêtes d'\\ASP.net v 2.0.50727**indiquent le nombre de demandes Web en attente sur le serveur. Lorsque ce compteur atteint 5 000, les demandes ultérieures échouent avec le message d’erreur « 503 - Service indisponible ».

  - **Demandes\\ASP.net en file d’attente** (doit toujours être zéro).

<div>


> [!NOTE]  
> Si vous répondez ou dépassez ces valeurs, vous devez reconsulter et recalculer la planification de la capacité pour le dimensionnement correct du processeur, du nombre de cœurs et de la mémoire pour les ordinateurs qui hébergent les services Web.



</div>

<div>

## <a name="see-also"></a>Voir aussi


[Surveiller les limites de capacité de mémoire serveur dans Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

