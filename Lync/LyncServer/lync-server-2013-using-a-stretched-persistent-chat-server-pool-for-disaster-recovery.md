---
title: Utilisation d’un pool de serveurs de conversation permanente étiré pour la récupération d’urgence
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c09231abfae7bbcc32083d7db72d8a4be79ecff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535921"
---
# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a>Utilisation d’un pool de serveurs de conversation permanente étiré pour la récupération d’urgence dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

La solution de récupération d’urgence pour le serveur de conversation permanente est basée sur un pool de serveurs de conversation permanente étiré. Il s’agit de la résilience de site métropolitaine dans Lync Server 2010 ; Toutefois, il n’est pas nécessaire de disposer d’un réseau local virtuel (VLAN) étiré. En étirant le pool de serveurs de conversation permanente, vous configurez essentiellement un pool dans la topologie de manière logique, mais vous placez physiquement les serveurs dans le pool dans deux centres de données différents. Configurez la mise en miroir SQL Server pour la base de données de la même manière et déployez la base de données et le miroir dans le même centre de données. Vous devez configurer une base de données de sauvegarde dans le centre de données secondaire (avec un miroir facultatif pour fournir une haute disponibilité lors de la récupération d’urgence). Il s’agit de la base de données de sauvegarde utilisée pour le basculement pendant la récupération d’urgence.

Pour plus d’informations sur la configuration de la mise en miroir SQL Server pour la haute disponibilité, voir [mise en miroir SQL Server dans Lync server 2013](lync-server-2013-sql-server-mirroring.md). Pour plus d’informations sur le basculement de la base de données pour la récupération d’urgence, voir Configuration de la copie [des journaux de transaction SQL Server dans Lync Server 2013 pour la base de données principale du serveur de conversation permanente](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) et configuration de la [copie des journaux de transaction SQL Server entre le miroir principal et la base de données secondaire de copie des journaux dans Lync Server 2013](lync-server-2013-set-up-log-shipping-secondary-database.md)

</div>

<span> </span>

</div>

</div>

</div>

