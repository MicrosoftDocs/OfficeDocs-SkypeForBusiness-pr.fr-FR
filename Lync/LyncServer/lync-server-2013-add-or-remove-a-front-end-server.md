---
title: 'Lync Server 2013: ajout ou suppression d’un serveur frontal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1fe1e81d3983b89d4f68111179c3adc7409bee2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a>Add or remove a Front End Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2016-01-21_

Lorsque vous ajoutez un serveur frontal à un pool, ou supprimez un serveur frontal d’un pool, vous devez redémarrer le pool. Pour éviter toute interruption de service aux utilisateurs, utilisez la procédure suivante lors de l’ajout ou de la suppression d’un serveur frontal.

<div>


> [!NOTE]  
> Si vous ajoutez des serveurs au pool, mettez à jour vos nouveaux serveurs du pool pour qu’ils se trouvent au même niveau de mise à jour cumulée que les serveurs existants du pool.



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a>Pour ajouter ou supprimer des serveurs frontaux

1.  Si vous supprimez un serveur frontal, vous devez d’abord arrêter de nouvelles connexions sur ces serveurs. Pour ce faire, vous pouvez utiliser l’applet de commande suivante :
    
        Stop-CsWindowsServices -Graceful

2.  Lorsque les serveurs en cours de suppression ne disposent pas de sessions actives, arrêtez les services Lync Server.

3.  Ouvrez le générateur de topologie et ajoutez ou supprimez les serveurs nécessaires.

4.  Publiez la topologie.

5.  Si le nombre d’éléments de la liste est supérieur à deux ou qu’il n’a pas encore plus de deux serveurs, vous devez taper l’applet de commande suivante:
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    Si le pool comporte au moins trois serveurs, trois de ces serveurs doivent être en cours d’exécution lorsque vous tapez cette cmdlet.

6.  Redémarrez tous les serveurs frontaux de la liste, un par un.

</div>

</div>

<span> </span>

</div>

</div>

</div>

