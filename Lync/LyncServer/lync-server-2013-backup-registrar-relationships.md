---
title: Relations de serveur de sauvegarde de sauvegarde Lync Server 2013
description: Relations d’inscriptions de sauvegarde Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b0bfce6444ae78c2fb792a6d63dba4bf36b1791
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552311"
---
# <a name="backup-registrar-relationships-in-lync-server-2013"></a><span data-ttu-id="004e1-103">Relations de serveur d’inscriptions de sauvegarde dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="004e1-103">Backup Registrar relationships in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="004e1-104">_**Dernière modification de la rubrique :** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="004e1-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="004e1-105">En plus de fournir une fonctionnalité de récupération d’urgence, deux pools associés jouent le rôle de serveur d’inscriptions de sauvegarde l’un pour l’autre.</span><span class="sxs-lookup"><span data-stu-id="004e1-105">In addition to providing disaster recovery ability, two paired pools serve as the backup Registrars for each other.</span></span> <span data-ttu-id="004e1-106">Dans Lync Server 2013, les relations de serveur d’inscriptions de sauvegarde entre les pools frontaux sont toujours 1:1 et réciproques.</span><span class="sxs-lookup"><span data-stu-id="004e1-106">In Lync Server 2013, backup Registrar relationships between Front End pools are always 1:1 and reciprocal.</span></span> <span data-ttu-id="004e1-107">Cela signifie que si P1 est la sauvegarde de P2, alors P2 doit être la sauvegarde de P1, et aucun des deux ne peut servir de sauvegarde pour un autre pool frontal.</span><span class="sxs-lookup"><span data-stu-id="004e1-107">This means that if P1 is the backup for P2, then P2 must be the backup for P1, and neither can be the backup for any other Front End pool.</span></span> <span data-ttu-id="004e1-108">Il s’agit d’une modification de Lync Server 2010, dans laquelle les relations de sauvegarde de pool frontal peuvent être nombreuses.</span><span class="sxs-lookup"><span data-stu-id="004e1-108">This is a change from Lync Server 2010, in which Front End pool backup relationships could be many to one.</span></span>

<span data-ttu-id="004e1-109">Même si les relations de sauvegarde entre deux pools frontaux doivent être 1:1 et symétriques, chaque pool frontal peut toujours être le serveur d’inscriptions de sauvegarde pour un nombre d’appliances Survivable Branch appliance, tout comme dans Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="004e1-109">Even though backup relationships between two Front End pools must be 1:1 and symmetrical, each Front End pool can still also be the backup registrar for any number of Survivable Branch Appliances, just as in Lync Server 2010.</span></span>

<span data-ttu-id="004e1-110">Notez que Lync Server 2013 n’étend pas la prise en charge de la récupération d’urgence aux utilisateurs hébergés sur un Survivable Branch appliance.</span><span class="sxs-lookup"><span data-stu-id="004e1-110">Note that Lync Server 2013 does not extend disaster recovery support to users homed on a Survivable Branch Appliance.</span></span> <span data-ttu-id="004e1-111">Si un pool frontal qui sert de sauvegarde pour un Survivable Branch Appliance tombe en panne, les utilisateurs connectés au Survivable Branch Appliance tombent en mode résistance même après que les utilisateurs hébergés sur le pool frontal ont basculé vers le pool de serveurs frontaux de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="004e1-111">If a Front End pool that serves as the backup for a Survivable Branch Appliance goes down, users signed into the Survivable Branch Appliance fall into resiliency mode even after users homed on the Front End pool are failed over to the backup Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

