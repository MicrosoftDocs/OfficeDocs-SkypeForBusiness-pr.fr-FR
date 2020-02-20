---
title: 'Lync Server 2013 : fourniture d’une connectivité PSTN au niveau d’un site de succursale'
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
ms.openlocfilehash: cf4b0582de84fe8d2eff4b0026f27a7268af2a02
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="providing-pstn-connectivity-at-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="d0530-102">Fourniture de la connectivité PSTN sur un site de succursale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0530-102">Providing PSTN connectivity at a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0530-103">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="d0530-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="d0530-104">Nous vous recommandons d’utiliser l’outil de planification Microsoft Lync Server 2013, pour ajouter des sites de succursale à votre topologie et configurer votre infrastructure vocale dans les sites de succursale.</span><span class="sxs-lookup"><span data-stu-id="d0530-104">We recommend using the Microsoft Lync Server 2013, Planning Tool to add branch sites to your topology and to set up your voice infrastructure in branch sites.</span></span>

<span data-ttu-id="d0530-105">Si vous n’utilisez pas l’outil de planification, suivez les procédures décrites dans les rubriques de cette section : tout d’abord, pour ajouter les sites de succursale, puis pour configurer votre infrastructure vocale en définissant la passerelle PSTN (IP/réseau téléphonique commuté) et/ou en configurant la jonction SIP (avec ou sans contournement de média).</span><span class="sxs-lookup"><span data-stu-id="d0530-105">If you are not using the Planning Tool, use the procedures in the topics in this section—first, to add the branch sites, and then, to set up your voice infrastructure by defining the IP/public switched telephone network (PSTN) gateway and/or by configuring the SIP trunk (with or without media bypass).</span></span> <span data-ttu-id="d0530-106">Vous pouvez également connecter un autocommutateur privé (PBX) au site de succursale.</span><span class="sxs-lookup"><span data-stu-id="d0530-106">Connecting a private branch exchange (PBX) to the branch site is another option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d0530-107">Si vous souhaitez fournir la résistance des sites de succursale, vous devez déployer un Survivable Branch appliance, un serveur Survivable Branch Server ou un serveur Standard Edition sur le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="d0530-107">If you want to provide branch-site resiliency, you must deploy a Survivable Branch Appliance, a Survivable Branch Server, or Standard Edition server at the branch site.</span></span> <span data-ttu-id="d0530-108">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</A> ou <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A>, selon le cas, dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="d0530-108">For details, see <A href="lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</A> or <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A>, as appropriate, in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d0530-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="d0530-109">In This Section</span></span>

  - [<span data-ttu-id="d0530-110">Ajouter des sites de succursale à votre topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0530-110">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="d0530-111">Définition d’une passerelle PSTN pour un site de succursale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0530-111">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)

  - [<span data-ttu-id="d0530-112">Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0530-112">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="d0530-113">Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0530-113">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d0530-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d0530-114">See Also</span></span>


[<span data-ttu-id="d0530-115">Planification de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0530-115">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
[<span data-ttu-id="d0530-116">Planification de la connectivité PSTN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d0530-116">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

