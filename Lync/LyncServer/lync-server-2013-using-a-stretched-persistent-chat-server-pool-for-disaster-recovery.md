---
title: Utilisation d’un pool de serveurs de conversation permanente élargi pour la récupération d’urgence
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ae23ed2d12548388cd1462aad653de4652633dc
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a>Utilisation d’un pool de serveurs de conversation permanente élargi pour la récupération d’urgence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

La solution de reprise après sinistre pour le serveur de chat permanent repose sur un pool de serveurs de chat permanent étiré. Similaire à la résilience de site métropolitain dans Lync Server 2010 ; Toutefois, il n’existe aucune exigence pour un réseau local virtuel étiré. En étireant le pool de serveurs de chat permanent, vous configurez essentiellement un pool dans la topologie logiquement, mais vous positionnez physiquement les serveurs dans le pool dans deux centres de données différents. Configurez la mise en miroir SQL Server pour la base de données de la même manière, puis déployez la base de données et le miroir dans le même centre de données. Vous devez configurer une base de données de sauvegarde dans le second centre de données (avec un miroir éventuel pour assurer la haute disponibilité pendant la récupération d’urgence). Il s’agit de la base de données de sauvegarde utilisée pour le basculement pendant la récupération d’urgence.

Pour plus d’informations sur la configuration de la mise en miroir SQL Server pour une haute disponibilité, voir [mise en miroir SQL Server dans Lync server 2013](lync-server-2013-sql-server-mirroring.md). Pour plus d’informations sur le basculement de la base de données à des fins de reprise après sinistre, voir Configuration de l' [envoi du journal SQL Server dans Lync server 2013 pour la base 2013 de données principale du serveur de chat](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) [](lync-server-2013-set-up-log-shipping-secondary-database.md)

</div>

<span> </span>

</div>

</div>

</div>

