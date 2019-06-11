---
title: Modifications de la topologie dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f0ea02d1643a686e16d3d1984e756a48311b421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a>Modifications de la topologie dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-02_

Les exigences et considérations en matière de topologie pour Lync Server 2013 diffèrent de celles des versions précédentes, comme décrit dans cette section.

<div>

## <a name="new-front-end-pools-architecture"></a>Architecture de pools front-end

Dans Lync Server 2013, l’architecture des pools front-end Enterprise Edition a changé en architecture de systèmes distribués.

Avec cette nouvelle architecture, la base de données principale n’est plus le magasin de données en temps réel d’un pool. Les informations relatives à un utilisateur particulier sont conservées sur trois serveurs frontaux de la liste. Pour chaque utilisateur, un serveur frontal fait office de maître des informations de l’utilisateur et deux autres serveurs frontaux servent de réplicas. S’il s’agit d’un serveur frontal, un autre serveur frontal ayant servi de réplica est automatiquement promu maître.

Cela se produit en coulisses et les administrateurs n’ont pas besoin de savoir quels serveurs frontaux sont les maîtres pour quels utilisateurs. Cette distribution de stockage de données améliore les performances et l’évolutivité au sein de la liste, et élimine le point de défaillance unique d’un serveur principal unique.

Le serveur principal sert de stockage de sauvegarde pour les données d’utilisateur et de conférence, et il s’agit également du stockage principal pour d’autres bases de données telles que la base de données du groupe de réponse.

Ces améliorations impliquent également la planification et la gestion de vos groupes. Nous vous recommandons de faire en sorte que toutes les plages frontales de votre entreprise Edition incluent au moins trois serveurs frontaux pour fournir le nombre complet de réplicas pour lesquels l’architecture du pool frontal est conçue. Par ailleurs, vous devez suivre certaines procédures lors de l’ajout de serveurs à un pool frontal, en supprimant des serveurs ou à la mise à niveau de vos serveurs. Pour plus d’informations, reportez-vous à la rubrique [topologies et composants pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

<div>

## <a name="server-role-topology-changes"></a>Changements de topologie de rôles de serveur

Certains rôles de serveur déjà exécutés sur des serveurs distincts sont désormais consolidés dans le rôle serveur frontal, ce qui vous permet de faire des économies sur les coûts liés au matériel.

  - Dans Lync Server 2013, le serveur de conférence A/V est toujours colocalisé avec le serveur frontal.

  - Les extrémités frontales pour la surveillance et l’archivage sont désormais toujours colocalisées avec le serveur frontal. La surveillance et l’archivage de chacune d’elles requièrent une base de données principale distincte, qui peut être désactivée sur le même serveur que la base de données principale du pool frontal, ou hébergées sur des serveurs principaux distincts.

  - Le serveur Chat permanent est désormais un rôle serveur. Dans Microsoft Lync Server 2010, le serveur de discussion de groupe était une application de confiance tierce pour Microsoft Lync Server 2010. Dans Lync Server 2013, la fonctionnalité de serveur Chat permanent est implémentée en utilisant trois rôles de serveur:
    
      - **PersistentChatService:** Principaux services serveur de chat permanent implémentés en tant que rôle frontal
    
      - **PersistentChatStore:** Rôle serveur principal
    
      - **PersistentChatComplianceStore:** Rôle serveur principal pour la conformité de la conversation persistante

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

