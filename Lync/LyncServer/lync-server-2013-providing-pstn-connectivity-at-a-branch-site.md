---
title: 'Lync Server 2013 : Connectivité RTC sur un site de succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Providing PSTN connectivity at a branch site
ms:assetid: d78d76fb-2dd1-42cb-b25a-bfaff9650a70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398945(v=OCS.15)
ms:contentKeyID: 48185633
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5dfc039b0b1cd2995d0a658f1c1c78e0941d405d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="providing-pstn-connectivity-at-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="51a34-102">Connectivité RTC sur un site de succursale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51a34-102">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51a34-103">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="51a34-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="51a34-104">Nous vous recommandons d’utiliser Microsoft Lync Server 2013, l’outil de planification pour ajouter des sites de succursales à votre topologie et configurer votre infrastructure vocale dans les sites de succursale.</span><span class="sxs-lookup"><span data-stu-id="51a34-104">We recommend using the Microsoft Lync Server 2013, Planning Tool to add branch sites to your topology and to set up your voice infrastructure in branch sites.</span></span>

<span data-ttu-id="51a34-105">Si vous n’utilisez pas l’outil de planification, suivez les procédures décrites dans les rubriques de cette section pour ajouter d’abord les sites de succursale, puis pour configurer votre infrastructure vocale en définissant la passerelle RTC (réseau téléphonique commuté) IP/public, et/ou en configurant le Trunk SIP (avec ou sans Bypass Media).</span><span class="sxs-lookup"><span data-stu-id="51a34-105">If you are not using the Planning Tool, use the procedures in the topics in this section—first, to add the branch sites, and then, to set up your voice infrastructure by defining the IP/public switched telephone network (PSTN) gateway and/or by configuring the SIP trunk (with or without media bypass).</span></span> <span data-ttu-id="51a34-106">Une autre option consiste à connecter un système PBX à un site de succursale.</span><span class="sxs-lookup"><span data-stu-id="51a34-106">Connecting a private branch exchange (PBX) to the branch site is another option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="51a34-107">Si vous souhaitez fournir la résilience du site de succursales, vous devez déployer une application de succursale Survivable, un serveur de succursales survivant ou un serveur Standard Edition sur le site de la succursale.</span><span class="sxs-lookup"><span data-stu-id="51a34-107">If you want to provide branch-site resiliency, you must deploy a Survivable Branch Appliance, a Survivable Branch Server, or Standard Edition server at the branch site.</span></span> <span data-ttu-id="51a34-108">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">déploiement d’une unité ou d’un serveur à l’aide de Lync server 2013</A> ou <A href="lync-server-2013-deploying-lync-server.md">déploiement de Lync Server 2013</A>, le cas échéant, dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="51a34-108">For details, see <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</A> or <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A>, as appropriate, in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="51a34-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="51a34-109">In This Section</span></span>

  - [<span data-ttu-id="51a34-110">Ajout des sites de succursale à votre topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51a34-110">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="51a34-111">Définition d’une passerelle RTC pour un site de succursale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51a34-111">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)

  - [<span data-ttu-id="51a34-112">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51a34-112">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="51a34-113">Configurer un Trunk sans dérivation multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51a34-113">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="51a34-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="51a34-114">See Also</span></span>


[<span data-ttu-id="51a34-115">Planification de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51a34-115">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
[<span data-ttu-id="51a34-116">Planification de la connectivité PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51a34-116">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

