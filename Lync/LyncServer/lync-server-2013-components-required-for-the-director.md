---
title: 'Lync Server 2013 : Composants requis pour le directeur'
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
ms.openlocfilehash: 12db97a72a9882964727edd3084e0bd598527358
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a>Composants requis pour le directeur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

Le seul composant requis pour créer et configurer un directeur consiste à déployer le rôle serveur directeur. Pour cela, vous devez utiliser le générateur de topologie et définir un pool d’ordinateurs unique ou un pool d’ordinateurs dans le nœud du pool de réalisateurs. Après avoir défini le directeur ou le pool de réalisateurs, exécutez l’Assistant Déploiement de Lync Server sur l’ordinateur qui sera directeur. Dans le cas d’un pool de directeurs, vous exécutez l’Assistant Déploiement de Lync Server sur chaque serveur qui sera membre du pool.

<div>

## <a name="topologies"></a>Topologies

Vous pouvez implémenter un serveur Director ou un pool de réalisateurs. Le directeur est toujours un serveur ou un pool distinct, sans colocalisé avec un autre rôle de serveur dans Lync Server 2013.

<div>


> [!NOTE]  
> Si vous ne déployez pas les directeurs, le serveur frontal ou le pool frontal doit supposer le rôle de directeur.



</div>

Un pool de directeurs doit être équilibré. Vous pouvez effectuer l’une des opérations suivantes :

  - Créer une topologie qui utilise un équilibreur de charge matérielle pour les services Web et l’équilibrage de charge DNS (Domain Name System) pour les autres types de trafic.
    
    [Pool directeur mis à l’échelle - Équilibrage de charge DNS et équilibreur de charge matérielle dans Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - Créez une topologie qui utilise un équilibreur de charge matérielle pour l’équilibrage de charge requis pour le pool de directeurs.
    
    [Pool directeur mis à l’échelle - Équilibreur de charge matérielle dans Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

