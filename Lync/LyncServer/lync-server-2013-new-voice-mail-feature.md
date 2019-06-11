---
title: 'Lync Server 2013 : Nouvelle fonctionnalité de messagerie vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New voice mail feature
ms:assetid: 84d13238-67ef-42cc-801a-2d8147ba3b7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688117(v=OCS.15)
ms:contentKeyID: 49733715
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40db78aa126521ddce496721681ceb322f72beda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-voice-mail-feature-in-lync-server-2013"></a><span data-ttu-id="df1f2-102">Nouvelle fonctionnalité de messagerie vocale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df1f2-102">New voice mail feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df1f2-103">_**Dernière modification de la rubrique:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="df1f2-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="df1f2-104">Lync Server 2013 introduit l’échappement de la messagerie vocale, une amélioration de la gestion de la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="df1f2-104">Lync Server 2013 introduces Voice mail Escape, an enhancement for managing voice mail.</span></span> <span data-ttu-id="df1f2-105">Cette nouvelle fonctionnalité peut détecter qu’un appel a été acheminé vers la messagerie vocale et empêcher l’appel d’être immédiatement acheminé vers la messagerie vocale de l’utilisateur, sans permettre à l’utilisateur de répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="df1f2-105">This new feature can detect when a call has been routed to voice mail, and prevent the call from being immediately routed to the user’s mobile phone voice mail without giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="df1f2-106">Ce scénario se produit lorsque l’utilisateur permet de sonner simultanément sur son téléphone mobile, qu’il est désactivé, qu’il n’est pas à portée de batterie ou qu’il n’est pas dans la plage.</span><span class="sxs-lookup"><span data-stu-id="df1f2-106">This scenario occurs when the user enables simultaneous ringing to their mobile phone, and their mobile phone is turned off, out of battery, or out of range.</span></span> <span data-ttu-id="df1f2-107">La fonction de messagerie vocale permet de détecter que l’appel a été reçu immédiatement par la messagerie vocale du téléphone mobile de l’utilisateur et de déconnecter l’appel vers la messagerie vocale du téléphone mobile.</span><span class="sxs-lookup"><span data-stu-id="df1f2-107">Voicemail Escape detects that the call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="df1f2-108">L’appel continue de sonner sur les autres points de terminaison de l’utilisateur, ce qui permet à l’utilisateur de répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="df1f2-108">The call continues to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="df1f2-109">Si l’utilisateur ne répond pas, l’appel est acheminé vers la messagerie vocale de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="df1f2-109">If the user does not answer the call, then the call is routed to the corporate voice mail.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="df1f2-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="df1f2-110">See Also</span></span>


[<span data-ttu-id="df1f2-111">Configuration de l’échappement de la messagerie vocale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df1f2-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="df1f2-112">Nouvelles fonctionnalités Voix Entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df1f2-112">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

