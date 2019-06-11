---
title: 'Lync Server 2013 : Planification de la déviation du trafic multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa60b6658eca7a73e509a7f6c707c3cf48c7f16e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="cb9b7-102">Planification de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb9b7-102">Planning for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb9b7-103">_**Dernière modification de la rubrique:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="cb9b7-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="cb9b7-104">La dérivation multimédia désigne la suppression du serveur de médiation du chemin multimédia dans la mesure du possible pour les appels dont le signalement traverse le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="cb9b7-104">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>

<span data-ttu-id="cb9b7-105">La déviation du trafic multimédia peut améliorer la qualité de la voix en diminuant la latence, les conversions inutiles, la perte de paquets possible et le nombre de points de défaillance éventuels.</span><span class="sxs-lookup"><span data-stu-id="cb9b7-105">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="cb9b7-106">L’évolutivité peut être améliorée, car la suppression du traitement multimédia pour les appels ignorés réduit la charge sur le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="cb9b7-106">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="cb9b7-107">Cette réduction du chargement complète les fonctionnalités du serveur de médiation pour contrôler plusieurs passerelles.</span><span class="sxs-lookup"><span data-stu-id="cb9b7-107">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span>

<span data-ttu-id="cb9b7-108">Dans le cas où un site de succursale ne disposant pas d’un serveur de médiation est connecté à un site central par le biais d’une ou de plusieurs liaisons WAN avec une bande passante restreinte, le contournement de média diminue la bande passante en autorisant les contenus multimédias d’un client sur un site de succursale à circuler directement vers sa passerelle locale sans tout d’abord, le lien réseau étendu doit être transmis à un serveur de médiation sur le site central.</span><span class="sxs-lookup"><span data-stu-id="cb9b7-108">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>

<span data-ttu-id="cb9b7-109">Le fait de soulager le serveur de médiation contre la transformation de média, le contournement de médias risque également de réduire le nombre de serveurs de médiation requis par une infrastructure vocale d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="cb9b7-109">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span>

<span data-ttu-id="cb9b7-110">La figure suivante montre des médias de base et des voies de signalisation dans des topologies avec et sans déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="cb9b7-110">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>

<span data-ttu-id="cb9b7-111">**Médias et voies de signalisation avec et sans déviation du trafic multimédia**</span><span class="sxs-lookup"><span data-stu-id="cb9b7-111">**Media and signaling pathways with and without media bypass**</span></span>

<span data-ttu-id="cb9b7-112">![Application de la connexion par contournement du support CAC] (images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Application de la connexion par contournement du support CAC")</span><span class="sxs-lookup"><span data-stu-id="cb9b7-112">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

<span data-ttu-id="cb9b7-113">En règle générale, essayez d’activer la déviation du trafic multimédia quand cela est possible.</span><span class="sxs-lookup"><span data-stu-id="cb9b7-113">As a general rule, enable media bypass wherever possible.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cb9b7-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="cb9b7-114">In This Section</span></span>

  - [<span data-ttu-id="cb9b7-115">Présentation de l’exclusion de médias dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb9b7-115">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)

  - [<span data-ttu-id="cb9b7-116">Modes de déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb9b7-116">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)

  - [<span data-ttu-id="cb9b7-117">Déviation du trafic multimédia et contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb9b7-117">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [<span data-ttu-id="cb9b7-118">Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb9b7-118">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="cb9b7-119">Sections associées</span><span class="sxs-lookup"><span data-stu-id="cb9b7-119">Related Sections</span></span>

[<span data-ttu-id="cb9b7-120">Déploiement de fonctionnalités avancées d’entreprise voix dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb9b7-120">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cb9b7-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cb9b7-121">See Also</span></span>


[<span data-ttu-id="cb9b7-122">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb9b7-122">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="cb9b7-123">Options de contournement global de médias dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb9b7-123">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

