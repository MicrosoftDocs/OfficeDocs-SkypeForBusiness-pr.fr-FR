---
title: 'Lync Server 2013 : Contrôle d’admission des appels et serveur de médiation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aa12bd22f27cbe25946c14ad04977b98025d557
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="f0c19-102">Contrôle d’admission des appels et serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0c19-102">Call admission control and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0c19-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f0c19-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f0c19-104">Le contrôle d’admission des appels (CAC), présenté par le biais de Lync Server 2010, gère l’établissement d’une session en temps réel, en fonction de la bande passante disponible, pour vous aider à éviter des problèmes de qualité d’utilisation médiocre pour les utilisateurs sur des réseaux encombrés.</span><span class="sxs-lookup"><span data-stu-id="f0c19-104">Call admission control (CAC), first introduced in Lync Server 2010, manages real-time session establishment, based on available bandwidth, to help prevent poor Quality of Experience (QoE) for users on congested networks.</span></span> <span data-ttu-id="f0c19-105">Pour prendre en charge cette fonctionnalité, le serveur de médiation, qui fournit la conversion de signalisation et de contenu multimédia entre l’infrastructure voix entreprise et une passerelle ou un fournisseur de trunking SIP, est responsable de la gestion de la bande passante pour ses deux interactions sur le Lync Côté serveur et sur le côté passerelle.</span><span class="sxs-lookup"><span data-stu-id="f0c19-105">To support this capability, the Mediation Server, which provides signaling and media translation between the Enterprise Voice infrastructure and a gateway or SIP trunking provider, is responsible for bandwidth management for its two interactions on the Lync Server side and on the gateway side.</span></span> <span data-ttu-id="f0c19-106">Dans le cadre du contrôle d’admission des appels, l’entité qui met fin à l’appel gère la réservation de la bande passante.</span><span class="sxs-lookup"><span data-stu-id="f0c19-106">In call admission control, the terminating entity for a call handles the bandwidth reservation.</span></span> <span data-ttu-id="f0c19-107">Les homologues de passerelle (passerelle RTC, PBX IP, SBC) pour lesquels le serveur de médiation interagit sur le côté de la passerelle ne prennent pas en charge le contrôle d’admission des appels Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f0c19-107">The gateway peers (PSTN gateway, IP-PBX, SBC) that the Mediation Server interacts with on the gateway side do not support Lync Server 2013 call admission control.</span></span> <span data-ttu-id="f0c19-108">C’est pourquoi le serveur de médiation doit gérer les interactions de bande passante pour le compte de son homologue de passerelle.</span><span class="sxs-lookup"><span data-stu-id="f0c19-108">Thus, the Mediation Server has to handle bandwidth interactions on behalf of its gateway peer.</span></span> <span data-ttu-id="f0c19-109">Dans la mesure du possible, le serveur de médiation réserve de la bande passante à l’avance.</span><span class="sxs-lookup"><span data-stu-id="f0c19-109">Whenever possible, the Mediation Server will reserve bandwidth in advance.</span></span> <span data-ttu-id="f0c19-110">Si c’est impossible (par exemple, si la localité du point de terminaison multimédia final du côté passerelle est inconnue pour un appel sortant vers l’homologue de passerelle), la bande passante est réservée quand l’appel est passé.</span><span class="sxs-lookup"><span data-stu-id="f0c19-110">If that is not possible (for example, if the locality of the ultimate media endpoint on the gateway side is unknown for an outgoing call to the gateway peer), bandwidth is reserved when the call is placed.</span></span> <span data-ttu-id="f0c19-111">Ce comportement peut entraîner une sur-souscription de bande passante, mais c’est le seul moyen d’empêcher les sonneries factices.</span><span class="sxs-lookup"><span data-stu-id="f0c19-111">This behavior can result in oversubscription of bandwidth, but it is the only way to prevent false rings.</span></span>

<span data-ttu-id="f0c19-112">La déviation du trafic multimédia et la réservation de bande passante s’excluent mutuellement.</span><span class="sxs-lookup"><span data-stu-id="f0c19-112">Media bypass and bandwidth reservation are mutually exclusive.</span></span> <span data-ttu-id="f0c19-113">Si une dérivation de média est utilisée pour un appel, le contrôle d’admission des appels n’est pas effectué pour cet appel.</span><span class="sxs-lookup"><span data-stu-id="f0c19-113">If a media bypass is employed for a call, call admission control is not performed for that call.</span></span> <span data-ttu-id="f0c19-114">L’hypothèse repose sur le fait qu’aucun lien avec bande passante restreinte n’est impliqué dans l’appel.</span><span class="sxs-lookup"><span data-stu-id="f0c19-114">The assumption here is that there are no links with constrained bandwidth involved in the call.</span></span> <span data-ttu-id="f0c19-115">Si le contrôle d’admission des appels est utilisé pour un appel particulier qui implique le serveur de médiation, cet appel ne peut pas recourir à une dérivation multimédia.</span><span class="sxs-lookup"><span data-stu-id="f0c19-115">If call admission control is used for a particular call that involves the Mediation Server, that call cannot employ media bypass.</span></span>

<span data-ttu-id="f0c19-116">Pour plus d’informations sur le contrôle de contournement multimédia ou le contrôle d’admission des appels, voir [planification de la dérivation multimédia dans Lync server 2013](lync-server-2013-planning-for-media-bypass.md) ou [planification du contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="f0c19-116">For details about media bypass or call admission control, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) or [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

