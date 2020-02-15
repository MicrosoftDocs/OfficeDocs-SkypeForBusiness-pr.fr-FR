---
title: Modifications apportées à la topologie Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topology changes
ms:assetid: 9e40ef93-9ab0-498c-9bbf-f94584353e53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688153(v=OCS.15)
ms:contentKeyID: 49733756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a993057d3aae52b1c080d05fe9bba4eaff1ebeab
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topology-changes-in-lync-server-2013"></a>Modifications de la topologie dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Les exigences et les considérations relatives à la topologie de Lync Server 2013 diffèrent de celles des versions antérieures, comme décrit dans cette section.

<div>

## <a name="new-front-end-pools-architecture"></a>Nouvelle architecture de pools frontaux

Dans Lync Server 2013, l’architecture des pools frontaux Enterprise Editions a été remplacée par une architecture de systèmes distribués.

Avec cette nouvelle architecture, la base de données principale n’est plus le magasin de données en temps réel dans un pool. Les informations relatives à un utilisateur particulier sont conservées sur trois serveurs frontaux dans le pool. Pour chaque utilisateur, un serveur frontal joue le rôle de maître pour les informations de cet utilisateur et deux autres serveurs frontaux servent de réplicas. En cas de défaillance d’un serveur frontal, un autre serveur frontal qui servait de réplica est promu automatiquement en maître.

Ceci se produisant en arrière-plan, il n’est pas nécessaire que les administrateurs sachent quels serveurs frontaux sont les maîtres pour chaque utilisateur. Cette distribution du stockage des données améliore les performances et l’extensibilité au sein du pool, et élimine le point de défaillance unique d’un serveur principal unique.

Le serveur principal sert de stockage de sauvegarde pour les données utilisateur et de conférence, et est également le stockage principal pour d’autres bases de données telles que la base de données Response Group.

Ces améliorations sont également synonymes de changements dans la manière dont vous planifiez et maintenez vos pools. Nous recommandons que tous les pools frontaux Enterprise Edition incluent au moins trois serveurs frontaux, afin de fournir le nombre complet de réplicas pour lesquels l’architecture de pool frontal est conçue. En outre, vous devez suivre certaines procédures lors de l’ajout de serveurs à un pool frontal, de la suppression de serveurs ou de la mise à niveau de serveurs. Pour plus d’informations, voir [topologies et composants pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

<div>

## <a name="server-role-topology-changes"></a>Modifications de topologie de rôles serveur

Certains rôles serveur qui s’exécutaient auparavant sur des serveurs distincts sont maintenant consolidés dans le rôle de serveur frontal, ce qui vous permet de faire des économies sur les coûts matériels.

  - Dans Lync Server 2013, le serveur de conférence A/V est toujours colocalisé avec le serveur frontal.

  - Les serveurs frontaux de surveillance et d’archivage sont désormais toujours colocalisés avec le serveur frontal. Ces deux fonctionnalités nécessitent toujours une base de données principale distincte, qui peut être colocalisée sur le même serveur que la base de données principale du pool frontal ou peut être hébergée sur des serveurs principaux distincts.

  - Le serveur de conversation permanente est maintenant un rôle de serveur. Dans Microsoft Lync Server 2010, le serveur de conversation de groupe était une application tierce de confiance pour Microsoft Lync Server 2010. Dans Lync Server 2013, la fonctionnalité de serveur de conversation permanente est implémentée à l’aide de trois nouveaux rôles serveur :
    
      - **PersistentChatService :** Principaux services de serveur de conversation permanente implémentés en tant que rôle frontal
    
      - **PersistentChatStore :** Rôle de serveur principal
    
      - **PersistentChatComplianceStore :** Rôle de serveur principal pour la conformité de la conversation permanente

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

