---
title: 'Lync Server 2013 : composants VoIP du réseau de périmètre'
description: 'Lync Server 2013 : composants VoIP du réseau de périmètre.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Perimeter network VoIP components
ms:assetid: 74230008-695d-436a-90b9-9cd060c70f7b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398559(v=OCS.15)
ms:contentKeyID: 48184514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a416838b2ccec969e2990d492029486b6f2c72
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557210"
---
# <a name="perimeter-network-voip-components-for-lync-server-2013"></a><span data-ttu-id="6a36b-103">Composants VoIP du réseau de périmètre pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a36b-103">Perimeter network VoIP components for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a36b-104">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6a36b-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="6a36b-105">Les appelants externes qui utilisent des clients de communications unifiées pour des appels individuels ou des téléconférences s’appuient sur le serveur Edge pour la communication vocale avec les collègues.</span><span class="sxs-lookup"><span data-stu-id="6a36b-105">Outside callers who use unified communications clients for individual or conference calls rely on Edge Server for voice communication with coworkers.</span></span>

<span data-ttu-id="6a36b-106">Sur un serveur Edge, le service Edge d’accès fournit la signalisation SIP pour les appels provenant d’utilisateurs de Lync qui se trouvent à l’extérieur du pare-feu de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6a36b-106">On an Edge Server, the Access Edge service provides SIP signaling for calls from Lync users who are outside your organization’s firewall.</span></span> <span data-ttu-id="6a36b-107">Le service Edge A/V permet aux médias de traverser les NAT et les pare-feu.</span><span class="sxs-lookup"><span data-stu-id="6a36b-107">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="6a36b-108">Un appelant qui utilise un client de communications unifiées en dehors du pare-feu de l’entreprise compte sur le service Edge A/V pour les appels individuels et téléconférences.</span><span class="sxs-lookup"><span data-stu-id="6a36b-108">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>

<span data-ttu-id="6a36b-p102">Le service d’authentification A/V est colocalisé avec le service Edge A/V et fournit des services d’authentification pour ce service. Les utilisateurs extérieurs qui tentent de se connecter au service Edge A/V ont besoin d’un jeton d’authentification fourni par le service d’authentification A/V pour que leurs appels puissent aboutir.</span><span class="sxs-lookup"><span data-stu-id="6a36b-p102">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

