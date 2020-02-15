---
title: 'Lync Server 2013 : récupération d’urgence de serveur Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cd85a769d021aae6873a50a719a6043ef72f770
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a>Récupération d’urgence de serveur Edge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-03-12_

Comme avec les autres rôles serveur, le meilleur moyen d’offrir une haute disponibilité pour vos serveurs Edge consiste à déployer plusieurs serveurs Edge dans des pools pour chaque site. Si un serveur Edge tombe en panne, les autres serveurs dans le pool continueront à assurer les services Edge.

Pour activer les procédures de récupération d’urgence, vous devez avoir déployé des pools de serveurs Edge distincts sur chaque site. Vous n’avez pas besoin d’associer par deux des pools Edge de façon explicite comme vous le feriez avec des pools frontaux, mais le fait de disposer de plusieurs pools Edge permet de maintenir l’activité si un pool Edge entier tombe en panne. Les sections suivantes décrivent la récupération d’urgence pour les différentes fonctions des serveurs Edge.

<div>

## <a name="remote-access"></a>Accès à distance

Si vous avez plusieurs sites, chacun d’eux disposant d’un pool de serveurs Edge et que l’un des pools de serveurs Edge échoue, les services d’accès à distance continuent de fonctionner sans avoir besoin de l’intervention de l’administrateur. Lors de la création de pools de serveurs Edge dans des sites différents, vous ne pouvez pas utiliser le même nom de domaine complet. Chaque pool Edge doit avoir des noms de domaine complets uniques (internes et externes). Les pools de serveurs Edge n’utilisent pas de règles de publication de proxy inverse pour communiquer avec les serveurs frontaux. Le basculement automatique se produit lorsque le client interroge à nouveau les enregistrements du service DNS d’accès à distance et que les utilisateurs distants sont routés vers les serveurs Edge dans un autre site. Le client tente de faire chaque nom de domaine complet Edge externe en fonction de la priorité des enregistrements SRV DNS.

<div>


> [!NOTE]  
> Pour que le basculement fonctionne correctement, assurez-vous que le pare-feu autorise les serveurs frontaux de chaque pool à communiquer avec tous les serveurs Edge.



</div>

</div>

<div>

## <a name="federation"></a>Fédération

Pour les relations de Fédération avec d’autres organisations exécutant Lync Server, les demandes de Fédération entrantes continueront de fonctionner aussi longtemps que vous avez des solutions comme géo-DNS GTM. Il est important de comprendre que le basculement de Fédération ne fournit pas de basculement avec la priorité dans les enregistrements SRV. Une solution fournie précédemment peut vous aider à fournir des fonctionnalités de récupération d’urgence pour la Fédération entrante.

La fédération sortante est toujours configurée par le biais d’un pool ou d’un serveur Edge publié dans l’organisation. Si ce pool Edge est tombé en panne, vous devez utiliser le Générateur de topologie pour changer l’itinéraire de la fédération sortante afin d’utiliser un pool Edge en état de fonctionnement. Pour plus d’informations, reportez-vous à [basculement du pool de serveurs Edge utilisé pour la Fédération Lync Server dans Lync server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

</div>

<div>

## <a name="xmpp-federation"></a>Fédération XMPP

Concernant la fédération XMPP, le trafic entrant et sortant s’arrêtera si le pool Edge qui est désigné comme passerelle de fédération XMPP tombe en panne. Pour que la fédération XMPP fonctionne de nouveau, vous devez configurer la fédération XMPP de sorte qu’elle utilise un autre pool Edge. Pour plus d’informations, reportez-vous à [basculement du pool de serveurs Edge utilisé pour la Fédération XMPP dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a>Le pool Edge tombe en panne mais le pool frontal fonctionne toujours

Si un pool Edge tombe en panne sur un site, alors que le pool frontal de ce site fonctionne toujours, vous devez configurer le pool frontal pour qu’il utilise un autre pool Edge d’un autre site pendant que le premier pool Edge est en panne. Pour plus d’informations, consultez [la rubrique Modification du pool de serveurs Edge associé à un pool frontal dans Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

