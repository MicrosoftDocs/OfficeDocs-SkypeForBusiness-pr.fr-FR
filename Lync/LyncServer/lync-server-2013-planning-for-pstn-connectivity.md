---
title: 'Lync Server 2013 : planification de la connectivité PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for PSTN connectivity
ms:assetid: 280f684a-740a-443d-8ecf-574241382a42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425749(v=OCS.15)
ms:contentKeyID: 48183684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 811f69e8286e341b7769a58d03c42d0a43e63075
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-pstn-connectivity-in-lync-server-2013"></a><span data-ttu-id="e3881-102">Planification de la connectivité PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3881-102">Planning for PSTN connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3881-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e3881-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e3881-104">Une solution VoIP à l’échelle de l’entreprise doit de toute évidence assurer l’acheminement des appels depuis et vers le réseau téléphonique commuté (PSTN) avec une qualité de service constante.</span><span class="sxs-lookup"><span data-stu-id="e3881-104">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="e3881-105">Les utilisateurs qui placent et reçoivent des appels ne doivent pas avoir conscience de la technologie sous-jacente : du point de vue de l’utilisateur, un appel entre l’infrastructure voix entreprise et le réseau téléphonique commuté doit ressembler à un autre appel téléphonique.</span><span class="sxs-lookup"><span data-stu-id="e3881-105">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>

<span data-ttu-id="e3881-106">Lync Server 2013 offre une connectivité PSTN fiable et évolutive à l’aide des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="e3881-106">Lync Server 2013 provides reliable, scalable PSTN connectivity by using the following options:</span></span>

  - <span data-ttu-id="e3881-107">**Jonctions SIP** vers un fournisseur de services de téléphonie Internet (téléphonie Internet)</span><span class="sxs-lookup"><span data-stu-id="e3881-107">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="e3881-108">**Connexions SIP directes** à une passerelle PSTN</span><span class="sxs-lookup"><span data-stu-id="e3881-108">**Direct SIP connections** to a PSTN gateway</span></span>

  - <span data-ttu-id="e3881-109">**Connexions SIP directes** à un PBX</span><span class="sxs-lookup"><span data-stu-id="e3881-109">**Direct SIP connections** to a PBX</span></span>

<span data-ttu-id="e3881-110">Selon la taille, la couverture géographique et l’infrastructure vocale existante, une entreprise peut utiliser une, deux ou trois de ces options à divers emplacements.</span><span class="sxs-lookup"><span data-stu-id="e3881-110">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e3881-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="e3881-111">In This Section</span></span>

  - [<span data-ttu-id="e3881-112">Jonction SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3881-112">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)

  - [<span data-ttu-id="e3881-113">Connexions SIP directes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3881-113">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)

  - [<span data-ttu-id="e3881-114">Jonction M :N dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3881-114">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="e3881-115">Règles de conversion dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3881-115">Translation rules in Lync Server 2013</span></span>](lync-server-2013-translation-rules.md)

  - [<span data-ttu-id="e3881-116">Planification du routage des communications vocales sortantes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3881-116">Planning outbound voice routing in Lync Server 2013</span></span>](lync-server-2013-planning-outbound-voice-routing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

