---
title: 'Lync Server 2013 : ajout ou suppression d’un serveur frontal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f30eb0034df6b0783f8389d69841a338c90effd4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521471"
---
# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a>Ajouter ou supprimer un serveur frontal dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-01-21_

Lorsque vous ajoutez un serveur frontal à un pool, ou que vous supprimez un serveur frontal d’un pool, vous devez redémarrer le pool. Pour éviter toute interruption de service pour les utilisateurs, utilisez la procédure suivante en cas d’ajout ou de suppression d’un serveur frontal.

<div>


> [!NOTE]  
> Si vous ajoutez de nouveaux serveurs au pool, mettez à jour vos nouveaux serveurs de pool de sorte qu’ils se trouvent au même niveau de mise à jour cumulative que les serveurs existants dans le pool.



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a>Pour ajouter ou supprimer des serveurs frontaux

1.  Si vous supprimez des serveurs frontaux, commencez par arrêter les nouvelles connexions à ces serveurs. Pour ce faire, vous pouvez utiliser l’applet de commande suivante :
    
        Stop-CsWindowsServices -Graceful

2.  Lorsque les serveurs supprimés n’ont pas de sessions actives, arrêtez les services Lync Server sur ces serveurs.

3.  Ouvrez le Générateur de topologie, puis ajoutez ou supprimez les serveurs nécessaires.

4.  Publiez la topologie.

5.  Si le pool est passé de deux serveurs frontaux à plus de deux ou de plus de deux serveurs à exactement deux, vous devez taper l’applet de commande suivante :
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    Si le pool comprend trois serveurs ou plus, au moins trois de ces serveurs doivent être en cours d’exécution lorsque vous tapez cette applet de commande.

6.  Redémarrez tous les serveurs frontaux du pool, un par un.

</div>

</div>

<span> </span>

</div>

</div>

</div>

