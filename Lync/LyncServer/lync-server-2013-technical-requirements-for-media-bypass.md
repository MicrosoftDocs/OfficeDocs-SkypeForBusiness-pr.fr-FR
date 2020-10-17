---
title: 'Lync Server 2013 : configuration technique requise pour la déviation du trafic multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2789ecc6f72babf2b0267f70705fd41ecd1a7aaf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533791"
---
# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="d8fa1-102">Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8fa1-102">Technical requirements for media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8fa1-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d8fa1-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d8fa1-104">Pour chaque appel au RTC, le serveur de médiation détermine si les médias du point de terminaison Lync peuvent être envoyés directement à un homologue de serveur de médiation sans traverser le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="d8fa1-104">For each call to the PSTN, the Mediation Server determines whether media from the Lync endpoint of origin can be sent directly to a Mediation Server peer without traversing the Mediation Server.</span></span> <span data-ttu-id="d8fa1-105">L’homologue peut être une passerelle PSTN, un système IP-PBX ou un contrôleur SBC (Session Border Controller) pour un fournisseur de services de téléphonie Internet (ITSP) associé à la jonction entre le serveur de médiation où l’appel est routé.</span><span class="sxs-lookup"><span data-stu-id="d8fa1-105">The peer can be a PSTN gateway, IP-PBX, or Session Border Controller (SBC) at an Internet telephony service provider (ITSP) that is associated with the trunk between the Mediation Server where the call is routed.</span></span>

<span data-ttu-id="d8fa1-106">Le contournement de média peut être utilisé lorsque les conditions suivantes sont remplies :</span><span class="sxs-lookup"><span data-stu-id="d8fa1-106">Media bypass can be employed when the following requirements are met:</span></span>

  - <span data-ttu-id="d8fa1-107">Un homologue de serveur de médiation doit prendre en charge les fonctionnalités nécessaires à la déviation du trafic multimédia, la plus importante étant la possibilité de gérer plusieurs réponses branches (appelées « boîtes de dialogue précoces »).</span><span class="sxs-lookup"><span data-stu-id="d8fa1-107">A Mediation Server peer must support the necessary capabilities for media bypass, the most important being the ability to handle multiple forked responses (known as “early dialogs”).</span></span> <span data-ttu-id="d8fa1-108">Contactez le fabricant de votre passerelle ou système PBX, ou votre fournisseur ITSP, pour obtenir la valeur du nombre maximal de boîtes de dialogue préliminaires que la passerelle, PBX ou SBC peut accepter.</span><span class="sxs-lookup"><span data-stu-id="d8fa1-108">Contact the manufacturer of your gateway or PBX, or your ITSP, to obtain the value for the maximum number of early dialogs that the gateway, PBX, or SBC can accept.</span></span>

  - <span data-ttu-id="d8fa1-109">L’homologue du serveur de médiation doit accepter le trafic multimédia directement à partir des points de terminaison Lync.</span><span class="sxs-lookup"><span data-stu-id="d8fa1-109">The Mediation Server peer must accept media traffic directly from Lync endpoints.</span></span> <span data-ttu-id="d8fa1-110">De nombreux ITSPs autorisent leur SBC à recevoir du trafic uniquement à partir du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="d8fa1-110">Many ITSPs allow their SBC to receive traffic only from the Mediation Server.</span></span> <span data-ttu-id="d8fa1-111">Contactez votre téléphonie Internet pour déterminer si sa SBC accepte le trafic multimédia directement depuis les points de terminaison Lync.</span><span class="sxs-lookup"><span data-stu-id="d8fa1-111">Contact your ITSP to determine whether its SBC accepts media traffic directly from Lync endpoints.</span></span>

  - <span data-ttu-id="d8fa1-112">Les clients Lync et un homologue de serveur de médiation doivent être bien connectés, ce qui signifie qu’ils sont situés dans la même région réseau ou sur des sites réseau qui se connectent à la région sur des liaisons de réseau étendu qui n’ont pas de contraintes de bande passante.</span><span class="sxs-lookup"><span data-stu-id="d8fa1-112">Lync clients and a Mediation Server peer must be well connected, meaning that they are either located in the same network region or at network sites that connect to the region over WAN links that have no bandwidth constraints</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d8fa1-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d8fa1-113">See Also</span></span>


[<span data-ttu-id="d8fa1-114">Modes de déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8fa1-114">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="d8fa1-115">Déviation du trafic multimédia et contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8fa1-115">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

