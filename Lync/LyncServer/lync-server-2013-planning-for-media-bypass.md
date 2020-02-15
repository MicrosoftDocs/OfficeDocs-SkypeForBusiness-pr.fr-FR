---
title: 'Lync Server 2013 : planification de la déviation du trafic multimédia'
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
ms.openlocfilehash: 0bb4d495637cd78e430e975e9831421906bfbf6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="6fe69-102">Planification de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fe69-102">Planning for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fe69-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6fe69-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="6fe69-104">Le contournement de média fait référence à la suppression du serveur de médiation du chemin d’accès des médias, dans la mesure du possible, pour les appels dont la signalisation traverse le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="6fe69-104">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="6fe69-105">Le contournement de média peut améliorer la qualité de la voix en diminuant la latence, les traductions inutiles, la perte de paquets possible et le nombre de points de défaillance éventuels.</span><span class="sxs-lookup"><span data-stu-id="6fe69-105">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="6fe69-106">L’extensibilité peut être améliorée du fait que l’élimination du traitement multimédia pour les appels contournés réduit la charge sur le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="6fe69-106">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="6fe69-107">Cette réduction du chargement complète la capacité du serveur de médiation à contrôler plusieurs passerelles.</span><span class="sxs-lookup"><span data-stu-id="6fe69-107">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="6fe69-108">Lorsqu’un site de succursale sans serveur de médiation est connecté à un site central par une ou plusieurs liaisons de réseau étendu avec une bande passante limitée, la déviation du trafic multimédia diminue l’exigence de bande passante en autorisant les médias d’un client sur un site de succursale à circuler directement vers sa passerelle locale sans Il faut d’abord circuler sur la liaison de réseau étendu vers un serveur de médiation sur le site central et inversement.</span><span class="sxs-lookup"><span data-stu-id="6fe69-108">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="6fe69-109">En soulageant le serveur de médiation du traitement multimédia, la déviation du trafic multimédia peut également réduire le nombre de serveurs de médiation requis par une infrastructure voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="6fe69-109">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="6fe69-110">La figure suivante montre des médias de base et des voies de signalisation dans des topologies avec et sans contournement de média.</span><span class="sxs-lookup"><span data-stu-id="6fe69-110">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="6fe69-111">**Médias et voies de signalisation avec et sans contournement de média**</span><span class="sxs-lookup"><span data-stu-id="6fe69-111">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="6fe69-112">![Application de la connexion de contournement de média CAC vocal](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Application de la connexion de contournement de média CAC vocal")</span><span class="sxs-lookup"><span data-stu-id="6fe69-112">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="6fe69-113">En règle générale, essayez d’activer le contournement de média quand cela est possible.</span><span class="sxs-lookup"><span data-stu-id="6fe69-113">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6fe69-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="6fe69-114">In This Section</span></span>

  - [<span data-ttu-id="6fe69-115">Vue d’ensemble de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fe69-115">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="6fe69-116">Modes de déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fe69-116">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="6fe69-117">Déviation du trafic multimédia et contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fe69-117">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="6fe69-118">Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fe69-118">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="6fe69-119">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="6fe69-119">Related Sections</span></span>

[<span data-ttu-id="6fe69-120">Déploiement des fonctionnalités avancées de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fe69-120">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6fe69-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6fe69-121">See Also</span></span>


[<span data-ttu-id="6fe69-122">Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fe69-122">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="6fe69-123">Options globales de déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6fe69-123">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

