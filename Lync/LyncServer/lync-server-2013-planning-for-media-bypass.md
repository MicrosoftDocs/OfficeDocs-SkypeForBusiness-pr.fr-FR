---
title: 'Lync Server 2013 : planification de la déviation du trafic multimédia'
description: 'Lync Server 2013 : planification de la déviation du trafic multimédia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d92a50d9d838b0f13fd6837cbfadee1c48712f0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549440"
---
# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="7d1cd-103">Planification de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d1cd-103">Planning for media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d1cd-104">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7d1cd-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7d1cd-105">Le contournement de média fait référence à la suppression du serveur de médiation du chemin d’accès des médias, dans la mesure du possible, pour les appels dont la signalisation traverse le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-105">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="7d1cd-106">Le contournement de média peut améliorer la qualité de la voix en diminuant la latence, les traductions inutiles, la perte de paquets possible et le nombre de points de défaillance éventuels.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-106">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="7d1cd-107">L’extensibilité peut être améliorée du fait que l’élimination du traitement multimédia pour les appels contournés réduit la charge sur le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-107">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="7d1cd-108">Cette réduction du chargement complète la capacité du serveur de médiation à contrôler plusieurs passerelles.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-108">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="7d1cd-109">Lorsqu’un site de succursale sans serveur de médiation est connecté à un site central par une ou plusieurs liaisons de réseau étendu avec une bande passante limitée, la déviation du trafic multimédia diminue l’exigence de bande passante en permettant aux médias d’un client sur un site de succursale de circuler directement vers la passerelle locale sans avoir préalablement transiter de la liaison de réseau étendu à un serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="7d1cd-109">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="7d1cd-110">En soulageant le serveur de médiation du traitement multimédia, la déviation du trafic multimédia peut également réduire le nombre de serveurs de médiation requis par une infrastructure voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-110">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="7d1cd-111">La figure suivante montre des médias de base et des voies de signalisation dans des topologies avec et sans contournement de média.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-111">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="7d1cd-112">**Médias et voies de signalisation avec et sans contournement de média**</span><span class="sxs-lookup"><span data-stu-id="7d1cd-112">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="7d1cd-113">![Application de la connexion de contournement de média CAC vocal](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Application de la connexion de contournement de média CAC vocal")</span><span class="sxs-lookup"><span data-stu-id="7d1cd-113">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="7d1cd-114">En règle générale, essayez d’activer le contournement de média quand cela est possible.</span><span class="sxs-lookup"><span data-stu-id="7d1cd-114">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7d1cd-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="7d1cd-115">In This Section</span></span>

  - [<span data-ttu-id="7d1cd-116">Vue d’ensemble de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d1cd-116">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="7d1cd-117">Modes de déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d1cd-117">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="7d1cd-118">Déviation du trafic multimédia et contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d1cd-118">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="7d1cd-119">Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d1cd-119">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="7d1cd-120">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="7d1cd-120">Related Sections</span></span>

[<span data-ttu-id="7d1cd-121">Déploiement des fonctionnalités avancées de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d1cd-121">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7d1cd-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7d1cd-122">See Also</span></span>


[<span data-ttu-id="7d1cd-123">Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d1cd-123">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="7d1cd-124">Options globales de déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d1cd-124">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

