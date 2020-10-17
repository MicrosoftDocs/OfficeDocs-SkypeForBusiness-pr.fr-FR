---
title: 'Lync Server 2013 : gestion de l’infrastructure réseau Lync Server 2013'
description: 'Lync Server 2013 : gestion de l’infrastructure réseau Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Lync Server 2013 network infrastructure
ms:assetid: cb13456a-8f66-4595-be21-8887f30ad4eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182585(v=OCS.15)
ms:contentKeyID: 48185638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab1b5c6fe52374b012063ac26640e9bb25496ad7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564100"
---
# <a name="managing-the-lync-server-2013-network-infrastructure"></a><span data-ttu-id="33aa2-103">Gestion de l’infrastructure réseau Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33aa2-103">Managing the Lync Server 2013 network infrastructure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33aa2-104">_**Dernière modification de la rubrique :** 2014-02-11_</span><span class="sxs-lookup"><span data-stu-id="33aa2-104">_**Topic Last Modified:** 2014-02-11_</span></span>

<span data-ttu-id="33aa2-105">Microsoft Lync Server 2013 inclut la prise en charge du contrôle d’admission des appels (CAC) et de la déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="33aa2-105">Microsoft Lync Server 2013 includes support for call admission control (CAC) and media bypass.</span></span> <span data-ttu-id="33aa2-106">Pour implémenter ces fonctionnalités, vous devez configurer un réseau de régions, de sites, de sous-réseaux, et ainsi de suite, qui vous permettra de gérer la bande passante dans les situations dans lesquelles les transmissions audio et vidéo doivent être restreintes.</span><span class="sxs-lookup"><span data-stu-id="33aa2-106">To implement these features you must configure a network of regions, sites, subnets, and so on that will allow you to manage bandwidth in situations where audio and video transmissions need to be restricted.</span></span> <span data-ttu-id="33aa2-107">Vous pouvez également utiliser la technologie de mise en réseau QoS (Quality of service) pour obtenir une expérience utilisateur final optimale pour les communications audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="33aa2-107">You can also use the Quality of Service (QoS) networking technology to help provide an optimal end-user experience for audio and video communications.</span></span>

<span data-ttu-id="33aa2-108">Vous pouvez utiliser le panneau de configuration Lync Server pour configurer et gérer le contrôle d’admission des médias, la déviation du trafic multimédia et la qualité de service.</span><span class="sxs-lookup"><span data-stu-id="33aa2-108">You can use the Lync Server Control Panel to set up and manage CAC, media bypass, and QoS.</span></span> <span data-ttu-id="33aa2-109">Les rubriques suivantes expliquent comment procéder.</span><span class="sxs-lookup"><span data-stu-id="33aa2-109">The following topics provide steps for how to do this.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="33aa2-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="33aa2-110">In This Section</span></span>

  - [<span data-ttu-id="33aa2-111">Gestion de la qualité de service (QoS) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33aa2-111">Managing Quality of Service (QoS) in Lync Server 2013</span></span>](lync-server-2013-managing-quality-of-service-qos.md)

  - [<span data-ttu-id="33aa2-112">Gestion du contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33aa2-112">Managing call admission control in Lync Server 2013</span></span>](lync-server-2013-managing-call-admission-control.md)

  - [<span data-ttu-id="33aa2-113">Interfaces réseau Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33aa2-113">Lync Server 2013 network interfaces</span></span>](lync-server-2013-lync-server-network-interfaces.md)

  - [<span data-ttu-id="33aa2-114">Empêcher les nouvelles connexions à Lync Server 2013 pour la maintenance du serveur</span><span class="sxs-lookup"><span data-stu-id="33aa2-114">Prevent new connections to Lync Server 2013 for server maintenance</span></span>](lync-server-2013-prevent-new-connections-to-lync-server-for-server-maintenance.md)

  - [<span data-ttu-id="33aa2-115">Méthodologie de qualité des appels Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33aa2-115">Lync Call Quality Methodology in Lync Server 2013</span></span>](lync-server-2013-poster-lync-call-quality-methodology.md)

  - [<span data-ttu-id="33aa2-116">Indicateurs d’intégrité clés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33aa2-116">Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-poster-key-health-indicators.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

