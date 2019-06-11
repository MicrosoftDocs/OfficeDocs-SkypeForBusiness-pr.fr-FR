---
title: 'Lync Server 2013 : Récupération d’urgence de serveur Edge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d19e5a606c3217ad7653fd4c3c885a97aafdb5ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a>Récupération d’urgence de serveur Edge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-03-12_

Comme pour les autres rôles de serveur, la meilleure façon de garantir la disponibilité de votre serveur Edge consiste à déployer plusieurs serveurs Edge dans les pools de chaque site. Si un serveur Edge est hors service, les autres serveurs du pool continuent de fournir les services Edge.

Pour activer les procédures de récupération d’urgence, vous devez déployer des pools de serveurs de bord séparés sur des sites distincts. Vous n’avez pas besoin de jumeler explicitement les pools d’arête comme pour les pools frontaux, mais le fait de disposer de plusieurs pools de bords vous permet d’assurer la mise en place de l’intégralité d’un pool de périphérie. Les sections suivantes fournissent des détails sur la récupération après sinistre pour les diverses fonctions des serveurs de périphérie.

<div>

## <a name="remote-access"></a>Accès à distance

Si vous disposez de plusieurs sites, chacun avec un pool de serveurs Edge et l’ensemble d’un pool de périphérie tombe en panne, les services d’accès à distance continuent de fonctionner sans intervention de l’administrateur. Vous ne pouvez pas utiliser le même nom de domaine complet lors de la création de pools Edge dans différents sites. Chaque pool Edge doit être doté d’un FQDN unique (interne et externe). Les pools de bords n’utilisent pas les règles de publication de proxy inverse pour parler aux serveurs frontaux. Le basculement automatique se produit lorsque le client réactive les enregistrements du service DNS d’accès à distance et que les utilisateurs distants sont routés vers les serveurs de périphérie d’un autre site. Le client tente de chaque nom de domaine complet de bord externe en fonction de la priorité des enregistrements SRV DNS.

<div>


> [!NOTE]  
> Pour que le basculement fonctionne sans problèmes, assurez-vous que le pare-feu permet aux serveurs frontaux de chaque pool de communiquer avec tous les serveurs Edge.



</div>

</div>

<div>

## <a name="federation"></a>Fédération

Pour les relations de Fédération avec d’autres organisations exécutant Lync Server, les demandes de Fédération entrante continuent de fonctionner aussi longtemps que vous disposez de solutions comme géo-DNS GTM. Il est important de comprendre que le basculement de la Fédération ne fournit pas de basculement avec la priorité dans les enregistrements SRV. Une solution fournie précédemment peut vous aider à fournir des fonctionnalités de reprise après sinistre pour la Fédération entrante.

La Fédération sortante est toujours configurée par le biais d’un pool d’organisations ou d’un serveur de périphérie publié au sein de l’organisation. Dans le cas contraire, vous devez utiliser le générateur de topologie pour modifier l’itinéraire de Fédération sortant et utiliser un pool de bords qui est toujours en cours d’exécution. Pour plus d’informations, reportez-vous à [échec du pool Edge utilisé pour la Fédération Lync Server dans Lync server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

</div>

<div>

## <a name="xmpp-federation"></a>Fédération XMPP

Pour la Fédération XMPP, le trafic entrant et sortant échouera si le pool de périphériques de périmètre désigné comme passerelle de Fédération XMPP s’arrête. Pour faire en sorte que la Fédération XMPP fonctionne à nouveau, vous devez modifier la Fédération de XMPP pour utiliser un pool de périphérie différent. Pour plus d’informations, reportez-vous à [échec du pool Edge utilisé pour la Fédération XMPP dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a>Le pool Edge ne fonctionne pas, mais le pool frontal s’exécute toujours

Si un pool de périphériques ne fonctionne pas sur un site, mais que le pool frontal sur ce site est toujours en cours d’exécution, vous devez modifier le pool frontal pour utiliser un pool de périphérie différent sur un autre site lorsque ce dernier est en bas de la liste. Pour plus d’informations, reportez-vous à [la section changement du pool de bords associé à un pool frontal dans Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

