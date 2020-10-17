---
title: 'Lync Server 2013 : nouvelle fonctionnalité de messagerie vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New voice mail feature
ms:assetid: 84d13238-67ef-42cc-801a-2d8147ba3b7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688117(v=OCS.15)
ms:contentKeyID: 49733715
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aaeb0aff851064e1e257194cc4d5a67b8eaabfbe
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522261"
---
# <a name="new-voice-mail-feature-in-lync-server-2013"></a><span data-ttu-id="07c0e-102">Nouvelle fonctionnalité de messagerie vocale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07c0e-102">New voice mail feature in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07c0e-103">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="07c0e-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="07c0e-104">Lync Server 2013 présente l’échappement de la messagerie vocale, une amélioration de la gestion de la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="07c0e-104">Lync Server 2013 introduces Voice mail Escape, an enhancement for managing voice mail.</span></span> <span data-ttu-id="07c0e-105">Cette fonctionnalité peut détecter quand un appel est acheminé vers la messagerie vocale et empêcher l’acheminement immédiat de l’appel vers la messagerie vocale du téléphone mobile de l’utilisateur avant que l’utilisateur puisse répondre.</span><span class="sxs-lookup"><span data-stu-id="07c0e-105">This new feature can detect when a call has been routed to voice mail, and prevent the call from being immediately routed to the user’s mobile phone voice mail without giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="07c0e-106">Ce scénario se produit quand l’utilisateur active la sonnerie simultanée sur son téléphone mobile et que ce dernier est éteint, à court de batterie ou hors de portée.</span><span class="sxs-lookup"><span data-stu-id="07c0e-106">This scenario occurs when the user enables simultaneous ringing to their mobile phone, and their mobile phone is turned off, out of battery, or out of range.</span></span> <span data-ttu-id="07c0e-107">Voicemail Escape détecte que la messagerie vocale du téléphone mobile de l’utilisateur a répondu immédiatement à l’appel, et déconnecte l’appel de la messagerie vocale du téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="07c0e-107">Voicemail Escape detects that the call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="07c0e-108">L’appel continue de sonner sur les autres points de terminaison de l’utilisateur, ce qui permet à l’utilisateur de répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="07c0e-108">The call continues to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="07c0e-109">Si l’utilisateur ne répond pas à l’appel, ce dernier est acheminé vers la messagerie vocale d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="07c0e-109">If the user does not answer the call, then the call is routed to the corporate voice mail.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="07c0e-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07c0e-110">See Also</span></span>


[<span data-ttu-id="07c0e-111">Configuration de l’échappement de la messagerie vocale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07c0e-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="07c0e-112">Nouvelles fonctionnalités voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07c0e-112">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

