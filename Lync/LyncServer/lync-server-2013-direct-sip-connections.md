---
title: 'Lync Server 2013: connexions SIP directes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Direct SIP connections
ms:assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398151(v=OCS.15)
ms:contentKeyID: 48183357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1decdfd4c755ea1788d088a4b539d8c555987f02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-connections-in-lync-server-2013"></a><span data-ttu-id="61170-102">Connexions SIP directes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61170-102">Direct SIP connections in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61170-103">_**Dernière modification de la rubrique:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="61170-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="61170-104">Vous pouvez utiliser des *connexions SIP directes* pour connecter le serveur Lync à l’un des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="61170-104">You can use *direct SIP connections* to connect Lync Server to either of the following:</span></span>

  - <span data-ttu-id="61170-105">Un PBX IP (pour plus de détails, voir [options de déploiement SIP directes dans Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span><span class="sxs-lookup"><span data-stu-id="61170-105">An IP-PBX (for details, see [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span></span>

  - <span data-ttu-id="61170-106">Passerelle RTC (pour plus de détails, voir [options de déploiement de la passerelle RTC dans Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span><span class="sxs-lookup"><span data-stu-id="61170-106">A PSTN gateway (for details, see [PSTN gateway deployment options in Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span></span>

<span data-ttu-id="61170-107">Pour implémenter une connexion SIP directe, vous devez suivre les mêmes étapes de déploiement que dans le cadre de l’implémentation d’un Trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="61170-107">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="61170-108">Dans les deux cas, vous implémentez la connexion à l’aide de l’interface externe d’un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="61170-108">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="61170-109">La seule différence réside dans le fait que vous connectez des lignes SIP à une entité externe, telle qu’une passerelle ITSP et que vous connectez des connexions SIP directes à une entité interne au sein de votre réseau local (par exemple, un PBX IP ou une passerelle RTC (réseau téléphonique commuté).</span><span class="sxs-lookup"><span data-stu-id="61170-109">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="61170-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="61170-110">In This Section</span></span>

  - [<span data-ttu-id="61170-111">Options de déploiement SIP direct dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61170-111">Direct SIP deployment options in Lync Server 2013</span></span>](lync-server-2013-direct-sip-deployment-options.md)

  - [<span data-ttu-id="61170-112">Options de déploiement de passerelle RTC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61170-112">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

