---
title: 'Lync Server 2013 : trunking SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76907c1868e9fccb1a31e705c73807a8cbe501b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a><span data-ttu-id="e9743-102">Trunking SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9743-102">SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9743-103">_**Dernière modification de la rubrique :** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="e9743-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="e9743-p101">Le protocole SIP (Session Initiation Protocol) sert à initier et à gérer les sessions de communications Voix sur IP (VoIP) pour le service téléphonique de base et d’autres services de communication en temps réel, tels que messagerie instantanée, conférence, détection de présence et multimédia. Cette section fournit des informations de planification pour l’implémentation de *jonctions SIP*, un type de connexion SIP qui s’étend au-delà des limites de votre réseau local.</span><span class="sxs-lookup"><span data-stu-id="e9743-p101">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia. This section provides planning information for implementing *SIP trunks*, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

<div>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="e9743-106">Qu’est-ce que la jonction SIP ?</span><span class="sxs-lookup"><span data-stu-id="e9743-106">What is SIP Trunking?</span></span>

<span data-ttu-id="e9743-p102">Une jonction SIP est une connexion IP qui établit un lien de communications SIP entre votre organisation et un fournisseur de services de téléphonie Internet (ITSP) à l’extérieur de votre pare-feu. En règle générale, une jonction SIP sert à connecter le site central de votre organisation à un fournisseur de services de téléphonie Internet (ITSP). Dans certains cas, vous pouvez également décider d’utiliser la jonction SIP pour connecter votre site de succursale à un fournisseur de services de téléphonie Internet (ITSP).</span><span class="sxs-lookup"><span data-stu-id="e9743-p102">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall. Typically, a SIP trunk is used to connect your organization’s central site to an ITSP. In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="e9743-110">Différences entre les jonctions SIP et les connexions SIP directes</span><span class="sxs-lookup"><span data-stu-id="e9743-110">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="e9743-111">Le terme *jonction* est dérivé de la technologie de commutation.</span><span class="sxs-lookup"><span data-stu-id="e9743-111">The term *trunk* is derived from circuit-switched technology.</span></span> <span data-ttu-id="e9743-112">Il fait référence à une ligne physique dédiée qui connecte les équipements téléphoniques de commutation.</span><span class="sxs-lookup"><span data-stu-id="e9743-112">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="e9743-113">Comme leurs prédécesseurs, les Trunks de répartition du temps (TDM), les Trunks SIP sont des connexions entre deux réseaux SIP séparés, Lync Server 2013 entreprise et ITSP.</span><span class="sxs-lookup"><span data-stu-id="e9743-113">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Lync Server 2013 enterprise and the ITSP.</span></span> <span data-ttu-id="e9743-114">Contrairement aux jonctions de commutation, les jonctions SIP sont des connexions virtuelles pouvant être établies sur n’importe quel type de connexion de jonction SIP pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e9743-114">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span> <span data-ttu-id="e9743-115">Pour plus d’informations sur les types de connexion pris en charge, consultez [comment implémenter le trunking SIP dans Lync Server 2013 ?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="e9743-115">For details about the supported connection types, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="e9743-116">En revanche, les connexions SIP directes sont des connexions SIP qui ne franchissent pas les limites du réseau local (c’est-à-dire qu’elles se connectent à une passerelle RTC ou à un PBX dans votre réseau interne).</span><span class="sxs-lookup"><span data-stu-id="e9743-116">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="e9743-117">Pour plus d’informations sur l’utilisation des connexions SIP directes avec Lync Server 2013, voir [connexions SIP directes dans Lync server 2013](lync-server-2013-direct-sip-connections.md).</span><span class="sxs-lookup"><span data-stu-id="e9743-117">For details about how you can use direct SIP connections with Lync Server 2013, see [Direct SIP connections in Lync Server 2013](lync-server-2013-direct-sip-connections.md).</span></span>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e9743-118">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="e9743-118">In This Section</span></span>

  - [<span data-ttu-id="e9743-119">Vue d’ensemble d’une jonction SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9743-119">Overview of SIP trunking in Lync Server 2013</span></span>](lync-server-2013-overview-of-sip-trunking.md)

  - [<span data-ttu-id="e9743-120">Implémentation d’une jonction SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9743-120">How do I implement SIP trunking in Lync Server 2013?</span></span>](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [<span data-ttu-id="e9743-121">Composants et topologies utilisés pour une jonction SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9743-121">Components and topologies for SIP trunking in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [<span data-ttu-id="e9743-122">Branch site SIP trunking in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9743-122">Branch site SIP trunking in Lync Server 2013</span></span>](lync-server-2013-branch-site-sip-trunking.md)

  - [<span data-ttu-id="e9743-123">Liste de vérification du déploiement de la jonction SIP pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9743-123">SIP trunk deployment checklist for Lync Server 2013</span></span>](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

