---
title: Gestion de la reprise après sinistre du serveur Lync, haute disponibilité et service de sauvegarde
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cada393fca28895ee5f23a12fdd55eabd211128e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>Gestion de la récupération d’urgence, de la haute disponibilité et du service de sauvegarde de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-12_

Cette section contient des procédures pour les opérations de récupération d’urgence, ainsi que pour la gestion du service de sauvegarde qui synchronise les données dans les pools frontaux couplés.

Les procédures de reprise après sinistre, à la fois de basculement et de restauration automatique, sont manuelles. En cas de sinistre, l’administrateur doit appeler manuellement les procédures de basculement. Il en va de même pour la restauration après la réparation du pool.

Les procédures de reprise après sinistre dans le reste de cette section sont supposées comme suit:

  - Vous disposez d’un déploiement avec des plages frontales couplées disponibles dans les différents sites, comme décrit dans la rubrique [planification de la haute disponibilité et reprise après sinistre dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Le service de sauvegarde est en cours d’exécution sur ces pools couplés pour qu’ils soient synchronisés.

  - Si le magasin central de gestion est hébergé sur l’un ou l’autre pool, il est installé et en cours d’exécution sur les deux pools couplés, avec l’un de ces pools hébergeant la forme de base active et l’autre réserve hébergeant la réserve.

<div>


> [!IMPORTANT]
> Dans les procédures suivantes, le paramètre <EM>PoolFQDN</EM> fait référence au nom de domaine complet (FQDN) du pool affecté par un sinistre, et non à partir du pool sur lequel les utilisateurs concernés sont redirigés. Pour le même ensemble d’utilisateurs concernés, il fait référence au même pool dans les applets de service de basculement et de restauration automatique (autrement dit, le pool qui a d’abord hébergé les utilisateurs avant le basculement).<BR>Par exemple, supposons que l’ensemble des utilisateurs hébergés sur un pool P1 aient pu basculer vers le pool de sauvegardes P2. Si l’administrateur veut déplacer tous les utilisateurs actuellement desservis par P2 pour être desservi par P1, l’administrateur doit procéder comme suit: 
> <OL>
> <LI>
> <P>Basculez vers la page d’accueil de tous les utilisateurs à l’origine de l’appel P1 sur P1 à l’aide de l’applet de la cmdlet failback. Dans le cas présent, le <EM>PoolFQDN</EM> est P1's FQDN.</P>
> <LI>
> <P>Faire basculer tous les utilisateurs de la page d’origine de la page de base sur l’applet de contrôle Dans le cas présent, le <EM>PoolFQDN</EM> est P2's FQDN.</P>
> <LI>
> <P>Si l’administrateur souhaite plus tard régulariser les utilisateurs de P2, le <EM>PoolFQDN</EM> est P2's FQDN.</P></LI></OL>Notez que l’étape 1 ci-dessus doit être effectuée avant l’étape 2 de conservation de l’intégrité du pool. Si vous essayez l’étape 2 avant l’étape 1, l’applet de la cmdlet Step 2 ne fonctionne pas.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration et surveillance du service de sauvegarde dans Lync Server 2013](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Basculement vers un pool dans Lync Server 2013](lync-server-2013-failing-over-a-pool.md)

  - [Basculement vers un pool dans Lync Server 2013](lync-server-2013-failing-back-a-pool.md)

  - [Basculement vers une base de données en miroir dans Lync Server 2013](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Basculement vers le pool Edge utilisé pour la fédération Lync Server dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Basculement vers le pool Edge utilisé pour la fédération XMPP dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Restauration du pool Edge utilisé pour la fédération XMPP ou Lync Server dans Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Modification du pool de serveurs Edge associé à un pool de serveurs frontaux dans Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [Restauration du contenu d’une conférence avec le service de sauvegarde dans Lync Server 2013](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

