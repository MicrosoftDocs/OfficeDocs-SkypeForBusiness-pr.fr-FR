---
title: 'Lync Server 2013 : composants requis pour le directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84a5765ce21ba955e4354c693171180a9d828210
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a>Composants requis pour le directeur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Le seul composant requis pour créer et configurer un directeur est de déployer le rôle serveur directeur. Pour ce faire, utilisez le générateur de topologie et définissez un seul pool d’ordinateurs ou un pool de plusieurs ordinateurs dans le nœud du pool directeur. Une fois que vous avez défini le directeur ou le pool Directeur, exécutez l’Assistant Déploiement de Lync Server sur l’ordinateur qui sera directeur. Dans le cas d’un pool Directeur, exécutez l’Assistant Déploiement Lync Server sur chaque serveur qui sera membre du pool.

<div>

## <a name="topologies"></a>Topologies

Vous pouvez implémenter un serveur directeur ou un pool directeur. Le directeur est toujours un serveur ou pool distinct, non colocalisé avec un autre rôle serveur dans Lync Server 2013.

<div>


> [!NOTE]  
> Si vous ne déployez pas les directeurs, le serveur frontal ou le pool frontal assumera le rôle de directeur.



</div>

Un pool de directeurs doit être équilibré en charge. Vous pouvez effectuer l’une des opérations suivantes :

  - Créez une topologie qui utilise un équilibreur de la charge matérielle pour les services web et un équilibrage de la charge DNS (Domain Name System) pour les autres types de trafic.
    
    [Pool directeur mis à l’ampleur-équilibrage de charge DNS et équilibreur de charge matérielle dans Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - Créez une topologie qui utilise un équilibreur de charge matérielle pour l’équilibrage de charge nécessaire pour le pool directeur.
    
    [Pool directeur mis à l’ampleur-équilibreur de charge matérielle dans Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

