---
title: 'Lync Server 2013 : surveillance du service de mobilité et de l’utilisation de UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2248bbd2eea4bb9204a98b5c5805ef196cbf2015
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531791"
---
# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a>Surveillance du service de mobilité et de l’utilisation d’UCWA dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-14_

De façon continue, vous devez surveiller le processeur et la mémoire utilisés par le service Lync Server Mobility (MCX) et l’API Web Unified Communications (UCWA). Pour surveiller l’utilisation, vous pouvez utiliser les éléments suivants :

**Pour l’API Web de communications unifiées (UCWA) :**

  - Le processus de travail **LyncUcwa** dans le gestionnaire des services Internet (IIS). Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;

  - les compteurs de performances **UC** et **Processeur**.

Pour la plupart des déploiements, l’utilisation de l’UC UCWA doit être inférieure à 15% en moyenne. L’utilisation de la mémoire doit être comprise dans les limites décrites dans [Monitoring for Server Memory Capacity Limits in Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances suivants pour vous aider à déterminer quand un serveur est surchargé de demandes :

  - **Ls : Web – limitation et authentification \\ WEB : nombre total de demandes en cours de traitement**, ce qui indique le nombre de demandes Web en attente sur le serveur. Lorsque ce compteur atteint 10 000, les demandes ultérieures échouent, avec le message d’erreur « 503-Service indisponible ».

  - **ASP.NET \\ Demandes en file d’attente** (doit toujours être zéro).

<div>


> [!NOTE]  
> Si vous atteignez ou dépassez ces valeurs, vous devez reconsulter et recalculer la planification de la capacité pour le dimensionnement correct du processeur, le nombre de cœurs et de mémoire pour les ordinateurs hébergeant les services Web.



</div>

**Pour le service de mobilité (MCX) :**

  - Les processus de travail **CSIntMcxAppPool** et **CSExtMcxAppPool** dans le gestionnaire des services Internet (IIS). Dans le volet **Processus de travail**, observez les valeurs des colonnes **% processeur** et **Octets privés (Ko)** (mémoire) ;

  - les compteurs de performances **UC** et **Processeur**.

Pour la plupart des déploiements, l’utilisation de l’UC du service de mobilité doit être inférieure à 15% en moyenne. L’utilisation de la mémoire doit être comprise dans les limites décrites dans [Monitoring for Server Memory Capacity Limits in Lync server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md).

Outre les compteurs d’utilisation du processeur et de la mémoire, vous pouvez utiliser les compteurs de performances ASP.NET suivants pour aider à déterminer quand un serveur est surchargé de demandes :

  - **ASP.net v 2.0.50727 \\ Demande les demandes en cours**, ce qui indique le nombre de demandes Web en attente sur le serveur. Lorsque ce compteur atteint 5 000, les demandes ultérieures échouent avec le message d’erreur « 503-Service indisponible ».

  - **ASP.NET \\ Demandes en file d’attente** (doit toujours être zéro).

<div>


> [!NOTE]  
> Si vous atteignez ou dépassez ces valeurs, vous devez revisiter et recalculer la planification de la capacité pour le dimensionnement correct du processeur, du nombre de cœurs et de la mémoire pour les ordinateurs hébergeant les services Web.



</div>

<div>

## <a name="see-also"></a>Voir aussi


[Surveillance des limites de capacité de mémoire des serveurs dans Lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

