---
title: 'Lync Server 2013 : planification de la haute disponibilité et de la récupération d’urgence'
description: 'Lync Server 2013 : planification de la haute disponibilité et de la récupération d’urgence.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for high availability and disaster recovery
ms:assetid: 15a72073-0336-45dd-b2a0-35e7522c6000
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204703(v=OCS.15)
ms:contentKeyID: 48183497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bb5f430201c48738421c4fbe72151ca58173898
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571840"
---
# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="962e2-103">Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="962e2-103">Planning for high availability and disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="962e2-104">_**Dernière modification de la rubrique :** 2013-10-31_</span><span class="sxs-lookup"><span data-stu-id="962e2-104">_**Topic Last Modified:** 2013-10-31_</span></span>

<span data-ttu-id="962e2-105">Comme dans Lync Server 2010, le principal modèle de haute disponibilité pour la plupart des rôles serveur dans Lync Server 2013 est basé sur la redondance des serveurs via la mise en pool.</span><span class="sxs-lookup"><span data-stu-id="962e2-105">As in Lync Server 2010, the main high availability scheme for most server roles in Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="962e2-106">Si un serveur qui exécute un rôle serveur donné échoue, les autres serveurs du pool qui exécutent le même rôle prennent la charge de ce serveur.</span><span class="sxs-lookup"><span data-stu-id="962e2-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="962e2-107">Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.</span><span class="sxs-lookup"><span data-stu-id="962e2-107">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="962e2-108">Lync Server 2013 ajoute de nouvelles mesures de récupération d’urgence pour les pools frontaux en introduisant la dispersion géographique de vos serveurs dans deux centres de données pour assurer la continuité du service en cas de panne d’un pool ou d’un site.</span><span class="sxs-lookup"><span data-stu-id="962e2-108">Lync Server 2013 adds new disaster recovery measures for Front End pools by introducing geographical dispersement of your servers into two data centers to provide continuation of service should one entire pool or site go down.</span></span>

<span data-ttu-id="962e2-109">Lync Server 2013 améliore également la haute disponibilité des serveurs principaux en prenant en charge la mise en miroir SQL synchrone pour vos bases de données principales.</span><span class="sxs-lookup"><span data-stu-id="962e2-109">Lync Server 2013 also enhances Back End Server high availability, by supporting synchronous SQL mirroring for your Back End databases.</span></span>

<span data-ttu-id="962e2-110">Cette section explique ces fonctionnalités majeures de haute disponibilité et de récupération d’urgence, et explique par ailleurs comment procéder pour assurer la haute disponibilité et la récupération d’urgence de vos autres rôles serveur.</span><span class="sxs-lookup"><span data-stu-id="962e2-110">This section explains these major high availability and disaster recovery features, and also covers what steps you can take for high availability and disaster recovery for your other server roles as well.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="962e2-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="962e2-111">In This Section</span></span>

  - [<span data-ttu-id="962e2-112">Récupération d’urgence de pool frontal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="962e2-112">Front End pool disaster recovery in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [<span data-ttu-id="962e2-113">Récupération d’urgence de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="962e2-113">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)

  - [<span data-ttu-id="962e2-114">Planification de la résistance voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="962e2-114">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="962e2-115">Fonctionnalités de gestion des appels pour la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="962e2-115">Call management features for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [<span data-ttu-id="962e2-116">Configuration du serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="962e2-116">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="962e2-117">Résilience de site métropolitain Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="962e2-117">Lync Server 2010 metropolitan site resiliency</span></span>](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

