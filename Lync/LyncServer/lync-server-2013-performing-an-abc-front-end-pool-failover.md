---
title: 'Lync Server 2013 : exécution d’un basculement de pool frontal ABC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing an ABC Front End pool failover
ms:assetid: 81ecd26d-49e3-4c72-a66e-02748efb513b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945637(v=OCS.15)
ms:contentKeyID: 51541489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dddda9d00ce7b6f22c6428dce7ef395b26ef8bfd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="performing-an-abc-front-end-pool-failover-in-lync-server-2013"></a><span data-ttu-id="0130c-102">Exécution d’un basculement de pool frontal ABC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0130c-102">Performing an ABC Front End pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0130c-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0130c-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0130c-104">Les deux rubriques de cette section décrivent la procédure à suivre pour effectuer un basculement de pool ABC dans Lync Server 2013, où il existe des pools frontaux A et B associés de Lync Server, et le pool A devient irrécupérable.</span><span class="sxs-lookup"><span data-stu-id="0130c-104">The two topics in this section describe the procedure for performing an ABC pool failover in Lync Server 2013, where there are paired Lync Server Front End pools A and B, and pool A becomes unrecoverable.</span></span> <span data-ttu-id="0130c-105">À l’aide de cette procédure, vous créez un nouveau pool frontal C avec un nouveau nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="0130c-105">Using this procedure, you create a new Front End pool C with a new fully qualified domain name (FQDN).</span></span> <span data-ttu-id="0130c-106">Le pool C est créé à partir des informations du pool a ayant échoué. La procédure inclut également le jumelage des pools B et C.</span><span class="sxs-lookup"><span data-stu-id="0130c-106">Pool C is constructed from the information from failed pool A. The procedure also includes pairing together pools B and C.</span></span>

  - [<span data-ttu-id="0130c-107">Conditions préalables à la sauvegarde pour le basculement du pool ABC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0130c-107">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>](lync-server-2013-backup-prerequisites-for-abc-pool-failover.md)

  - [<span data-ttu-id="0130c-108">Procédure de basculement ABC de pool frontal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0130c-108">Front End pool ABC failover procedure in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-abc-failover-procedure.md)

</div>

<span> </span>

</div>

</div>

</div>

