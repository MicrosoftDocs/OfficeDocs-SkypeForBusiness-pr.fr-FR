---
title: Supprimer un serveur frontal d’un pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c6e161fd5392f194cc19d7ffa01f20ea1f98f3b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a>Supprimer un serveur frontal d’un pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-04_

Le serveur frontal Microsoft Lync Server 2010 Enterprise Edition ne peut pas exister en tant qu’ordinateur autonome. Il doit être défini en tant que pool frontal, même s’il n’y a qu’un seul ordinateur dans le pool.

Cette rubrique vous guide tout au long du processus de suppression d’un serveur frontal individuel d’un pool frontal existant. Si le serveur frontal est le dernier serveur du pool ou si vous supprimez complètement le pool, reportez-vous à la rubrique [supprimer un pool frontal ou un serveur Standard Edition](remove-front-end-pool-or-standard-edition-server.md). Il n’est pas nécessaire de supprimer les serveurs frontaux individuels avant de supprimer le pool frontal. Lorsque vous supprimez le pool, vous supprimez tous les serveurs frontaux.

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a>Pour supprimer un serveur frontal d’un pool

1.  Ouvrez le serveur frontal Lync Server 2013, puis ouvrez le générateur de topologie.

2.  Accédez au nœud Lync Server 2010.

3.  Développez **Pools frontaux Enterprise Edition**, développez le pool frontal avec le serveur frontal que vous souhaitez supprimer, cliquez avec le bouton droit sur le serveur frontal que vous souhaitez supprimer, puis cliquez sur **supprimer**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

