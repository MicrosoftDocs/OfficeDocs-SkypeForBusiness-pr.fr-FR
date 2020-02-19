---
title: 'Lync Server 2013 : déploiement de sites de succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying branch sites
ms:assetid: 1475dee0-66ae-4ee5-b6f1-7409b4bbff45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398217(v=OCS.15)
ms:contentKeyID: 48183483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c167dc4f81053d5b9dde547f2f1e6e3d9d1a0fe7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-branch-sites-in-lync-server-2013"></a><span data-ttu-id="1eb2a-102">Déploiement de sites de succursale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1eb2a-102">Deploying branch sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1eb2a-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1eb2a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="1eb2a-104">Les utilisateurs de site de succursale obtiennent la plupart de leurs fonctionnalités Lync Server 2013 à partir du serveur sur le site central auquel le site de succursale est associé.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-104">Branch site users get most of their Lync Server 2013 functionality from the server at the central site that the branch site is associated with.</span></span> <span data-ttu-id="1eb2a-105">Chaque site de succursale est associé à exactement un site central.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-105">Each branch site is associated with exactly one central site.</span></span> <span data-ttu-id="1eb2a-106">Pour transmettre les appels vers et depuis le réseau téléphonique commuté public, le site de succursale peut avoir besoin de ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="1eb2a-106">To provide calls to and from the public switched telephone network (PSTN), a branch site might contain any of the following:</span></span>

  - <span data-ttu-id="1eb2a-107">une passerelle PSTN et si possible un serveur de médiation ;</span><span class="sxs-lookup"><span data-stu-id="1eb2a-107">A PSTN gateway and possibly a Meditation Server</span></span>

  - <span data-ttu-id="1eb2a-108">une jonction SIP ;</span><span class="sxs-lookup"><span data-stu-id="1eb2a-108">A SIP trunk</span></span>

  - <span data-ttu-id="1eb2a-109">une infrastructure vocale existante avec PBX (autocommutateur privé) ;</span><span class="sxs-lookup"><span data-stu-id="1eb2a-109">An existing voice infrastructure with a private branch exchange (PBX)</span></span>

  - <span data-ttu-id="1eb2a-110">Un Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="1eb2a-110">A Survivable Branch Appliance</span></span>

  - <span data-ttu-id="1eb2a-111">Un serveur Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="1eb2a-111">A Survivable Branch Server</span></span>

<span data-ttu-id="1eb2a-112">Les sites de succursale disposant d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server sont plus résiliences en cas de défaillance du réseau étendu ou du site central que les sites de succursale sans l’une de ces solutions.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-112">Branch sites with a Survivable Branch Appliance or a Survivable Branch Server are more resilient in times of wide-area network or central site failures than branch sites without one of these solutions.</span></span> <span data-ttu-id="1eb2a-113">Par exemple, dans un site disposant d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server déployé, les utilisateurs peuvent toujours effectuer et recevoir des appels RTC si le réseau qui connecte le site de succursale au site central est inactif.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-113">For example, in a site with a Survivable Branch Appliance or a Survivable Branch Server deployed, users can still make and receive PSTN calls if the network connecting the branch site to the central site is down.</span></span> <span data-ttu-id="1eb2a-114">Une autre façon d’obtenir la résistance des sites de succursale consiste à utiliser une passerelle PSTN ou une jonction SIP avec un déploiement de Lync Server complet sur le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-114">Another way to achieve branch-site resiliency is by using a PSTN gateway or a SIP trunk with a full-scale Lync Server deployment at the branch site.</span></span>

<span data-ttu-id="1eb2a-115">Pour plus d’informations sur le déploiement de site de succursale le plus approprié pour votre organisation, notamment les conditions préalables et les autres considérations de planification, reportez-vous à [Planning for PSTN Connectivity in Lync server 2013](lync-server-2013-planning-for-pstn-connectivity.md) et [Planning for Branch-site Voice Resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="1eb2a-115">For details about which branch site deployment is right for your organization, including prerequisites and other planning considerations, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) and [Planning for branch-site voice resiliency in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1eb2a-116">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="1eb2a-116">In This Section</span></span>

  - [<span data-ttu-id="1eb2a-117">Fourniture de la connectivité PSTN sur un site de succursale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1eb2a-117">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>](lync-server-2013-providing-pstn-connectivity-at-a-branch-site.md)

  - [<span data-ttu-id="1eb2a-118">Déploiement d’un Survivable Branch Appliance ou d’un serveur Survivable Branch Server avec Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1eb2a-118">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

