---
title: Gestion de la récupération d’urgence, de la haute disponibilité et du service de sauvegarde de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c935a27f737d8ec7fdb012f4e0c13930d20a1319
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498151"
---
# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>Gestion de la récupération d’urgence, de la haute disponibilité et du service de sauvegarde de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-12_

Cette section contient des procédures destinées aux opérations de récupération d’urgence, ainsi que pour la maintenance du service de sauvegarde qui synchronise les données des pools frontaux couplés.

Les procédures de récupération d’urgence, qu’il s’agisse du basculement ou de la restauration automatique, sont manuelles. En cas d’urgence, l’administrateur doit appeler manuellement les procédures de basculement. Il en est de même pour la restauration automatique, après la réparation du pool.

Les procédures de récupération d’urgence présentées dans le reste de la section supposent les éléments suivants :

  - Vous disposez d’un déploiement avec des pools frontaux couplés, situés dans différents sites, comme décrit dans la rubrique [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Le service de sauvegarde a été exécuté sur ces pools couplés pour maintenir leur synchronisation.

  - Si le magasin central de gestion est hébergé sur l’un ou l’autre pool, il est installé et s’exécute sur les deux pools couplés, avec l’un de ces pools hébergeant le serveur principal actif et l’autre pool hébergeant le secours.

<div>


> [!IMPORTANT]
> Dans les procédures suivantes, le paramètre <EM>PoolFQDN</EM> se réfère au nom de domaine complet (FQDN) du pool affecté par la situation d’urgence et non pas le pool depuis lequel les utilisateurs affectés sont redirigés. Dans le cas d’un ensemble d’utilisateurs identique, le paramètre se réfère au même pool, dans les cmdlets de basculement et de récupération automatique (c’est-à-dire, le pool ayant hébergé les utilisateurs avant le basculement).<BR>Par exemple, supposons que tous les utilisateurs hébergés sur un pool P1 ont été basculés sur le pool de sauvegarde, P2. Si l’administrateur veut déplacer tous les utilisateurs actuellement traités par les services de P2 pour qu’ils soient traités par les services de P1, l’administrateur doit procéder comme ceci : 
> <OL>
> <LI>
> <P>Il doit restaurer automatiquement tous les utilisateurs hébergés à l’origine sur P1 de P2 à P1 en utilisant la cmdlet de restauration automatique. Dans ce cas, le <EM>PoolFQDN</EM> est le nom de domaine complet (FQDN) de P1.</P>
> <LI>
> <P>Il doit ensuite basculer tous les utilisateurs hébergés à l’origine sur P2 vers P1 en utilisant la cmdlet de basculement. Dans ce cas, le <EM>PoolFQDN</EM> est le nom de domaine complet (FQDN) de P2.</P>
> <LI>
> <P>Si l’administrateur souhaite ultérieurement restaurer automatiquement les utilisateurs de P2 vers P2, le <EM>PoolFQDN</EM> est le nom de domaine complet FQDN de P2.</P></LI></OL>Remarquez que l’étape 1 ci-dessus doit être effectuée avant l’étape 2 pour préserver l’intégrité du pool. Si vous essayez l’étape 2 avant l’étape 1, la cmdlet de l’étape 2 ne fonctionnera pas.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration et surveillance du service de sauvegarde dans Lync Server 2013](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Basculement d’un pool dans Lync Server 2013](lync-server-2013-failing-over-a-pool.md)

  - [Restauration d’un pool dans Lync Server 2013](lync-server-2013-failing-back-a-pool.md)

  - [Basculement vers une base de données mise en miroir dans Lync Server 2013](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Basculement du pool de serveurs Edge utilisé pour la Fédération Lync Server dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Basculement du pool de serveurs Edge utilisé pour la Fédération XMPP dans Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Restauration du pool Edge utilisé pour Lync Server Federation ou XMPP Federation dans Lync Server 2013](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Modification du pool de serveurs Edge associé à un pool frontal dans Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [Restauration du contenu d’une conférence à l’aide du service de sauvegarde dans Lync Server 2013](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

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

