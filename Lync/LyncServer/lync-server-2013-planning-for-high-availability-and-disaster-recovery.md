---
title: 'Lync Server 2013 : Planification de la haute disponibilité et de la récupération d’urgence'
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
ms.openlocfilehash: 79abf8b98252f3b05b899a9840e7a9c9a2e8096c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41752184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="08b8e-102">Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08b8e-102">Planning for high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08b8e-103">_**Dernière modification de la rubrique :** 2013-10-31_</span><span class="sxs-lookup"><span data-stu-id="08b8e-103">_**Topic Last Modified:** 2013-10-31_</span></span>

<span data-ttu-id="08b8e-104">Comme dans Lync Server 2010, le principal schéma de haute disponibilité pour la plupart des rôles serveur dans Lync Server 2013 repose sur la redondance du serveur via le regroupement.</span><span class="sxs-lookup"><span data-stu-id="08b8e-104">As in Lync Server 2010, the main high availability scheme for most server roles in Lync Server 2013 is based on server redundancy via pooling.</span></span> <span data-ttu-id="08b8e-105">Si un serveur exécutant un rôle serveur particulier rencontre une défaillance, les autres serveurs du pool qui exécutent le même rôle assument la charge de ce serveur.</span><span class="sxs-lookup"><span data-stu-id="08b8e-105">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span> <span data-ttu-id="08b8e-106">Cela s’applique aux serveurs frontaux, aux serveurs Edge, aux serveurs de médiation et aux directeurs.</span><span class="sxs-lookup"><span data-stu-id="08b8e-106">This applies to Front End Servers, Edge Servers, Mediation Servers, and Directors.</span></span>

<span data-ttu-id="08b8e-107">Lync Server 2013 ajoute de nouvelles mesures de reprise après sinistre pour les pools front-end en introduisant la dispersion géographique de vos serveurs dans deux centres de données afin de garantir la continuation du service.</span><span class="sxs-lookup"><span data-stu-id="08b8e-107">Lync Server 2013 adds new disaster recovery measures for Front End pools by introducing geographical dispersement of your servers into two data centers to provide continuation of service should one entire pool or site go down.</span></span>

<span data-ttu-id="08b8e-108">Lync Server 2013 améliore également la disponibilité élevée du serveur principal en prenant en charge la mise en miroir SQL synchrone pour vos bases de données principales.</span><span class="sxs-lookup"><span data-stu-id="08b8e-108">Lync Server 2013 also enhances Back End Server high availability, by supporting synchronous SQL mirroring for your Back End databases.</span></span>

<span data-ttu-id="08b8e-109">Cette section décrit les principales fonctionnalités de haute disponibilité et de récupération d’urgence, ainsi que les actions que vous pouvez effectuer pour une disponibilité élevée et une reprise après sinistre pour vos autres rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="08b8e-109">This section explains these major high availability and disaster recovery features, and also covers what steps you can take for high availability and disaster recovery for your other server roles as well.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="08b8e-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="08b8e-110">In This Section</span></span>

  - [<span data-ttu-id="08b8e-111">Récupération d’urgence de pool frontal dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08b8e-111">Front End pool disaster recovery in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-disaster-recovery.md)

  - [<span data-ttu-id="08b8e-112">Récupération d’urgence de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08b8e-112">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)

  - [<span data-ttu-id="08b8e-113">Planification de la résistance Voix Entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08b8e-113">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

  - [<span data-ttu-id="08b8e-114">Fonctionnalités de gestion des appels pour la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08b8e-114">Call management features for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-call-management-features-for-disaster-recovery.md)

  - [<span data-ttu-id="08b8e-115">Configuration d’un serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08b8e-115">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="08b8e-116">Résistance de sites métropolitains Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="08b8e-116">Lync Server 2010 metropolitan site resiliency</span></span>](lync-server-2013-compatibility-with-lync-server-2010-metropolitan-site-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

