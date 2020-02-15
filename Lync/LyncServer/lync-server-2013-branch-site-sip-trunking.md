---
title: 'Lync Server 2013 : jonction SIP de site de succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 161964bc7a183672323ac277eae4f3a7ce0d2b82
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="d592a-102">Jonction SIP de site de succursale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d592a-102">Branch site SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d592a-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d592a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d592a-104">Dans certains cas, vous devrez peut-être implémenter une jonction SIP distribuée sur des sites de succursale sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="d592a-104">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="d592a-105">Pour déterminer si une jonction SIP est nécessaire pour un site de succursale, consultez les informations de la [procédure implémentation de la jonction SIP dans Lync Server 2013 ?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="d592a-105">To determine whether a SIP trunk is needed for a branch site, review the information in [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="d592a-106">Pour plus d’informations sur les options de topologie prises en charge pour le déploiement de jonctions SIP dans les sites de succursale, consultez la rubrique [solutions de résistance de site de succursale dans Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="d592a-106">For details about the supported topology options for deploying SIP trunks in branch sites, see [Branch-site resiliency solutions in Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).</span></span>

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="d592a-107">Conditions requises pour le déploiement d’une jonction SIP sur un site de succursale : exemple d’analyse</span><span class="sxs-lookup"><span data-stu-id="d592a-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="d592a-108">Lorsque vous décidez de déployer une jonction SIP de site de succursale, vous devez effectuer une analyse des coûts propre au site.</span><span class="sxs-lookup"><span data-stu-id="d592a-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="d592a-109">Par exemple, une entreprise ayant un site central à Redmond, Washington et un site de succursale à New York doit effectuer une analyse pour déterminer s’il faut implémenter une jonction SIP à partir du site de New York vers un fournisseur de services local.</span><span class="sxs-lookup"><span data-stu-id="d592a-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>

<span data-ttu-id="d592a-110">Pour savoir si une jonction SIP distribuée à New York est rentable, identifiez les numéros SDA (Sélection Directe à l’Arrivée) qui doivent utiliser la jonction SIP, puis analysez le nombre d’appels à destination de zones en dehors de Redmond (425) que le site de New York passe.</span><span class="sxs-lookup"><span data-stu-id="d592a-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="d592a-111">Vous pouvez avoir terminé le site de succursale sur le site central.</span><span class="sxs-lookup"><span data-stu-id="d592a-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="d592a-112">Par exemple, le site central de Redmond peut héberger des numéros DID pour le site de succursale de New York.</span><span class="sxs-lookup"><span data-stu-id="d592a-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="d592a-113">Si le coût de mise en œuvre d’une jonction SIP distribuée est inférieur au coût de ces appels, envisagez d’implémenter une jonction SIP sur le site de succursale de New York.</span><span class="sxs-lookup"><span data-stu-id="d592a-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span>

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="d592a-114">Autres conditions requises pour le déploiement d’une jonction SIP sur un site de succursale</span><span class="sxs-lookup"><span data-stu-id="d592a-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="d592a-115">Pour déterminer si vous devez déployer une jonction SIP ou une passerelle, comparez le coût des appels PSTN (Public Switched Telephone Network, réseau téléphonique commuté) longue distance de ces deux options.</span><span class="sxs-lookup"><span data-stu-id="d592a-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="d592a-116">Si vous déployez une jonction SIP de site de succursale, vous devez également déterminer les besoins en matière de résistance et de bande passante.</span><span class="sxs-lookup"><span data-stu-id="d592a-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="d592a-117">Si la liaison entre votre site de succursale et le site central est résiliente et dispose d’une bande passante suffisante, vous pouvez déployer une jonction SIP ou une passerelle.</span><span class="sxs-lookup"><span data-stu-id="d592a-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="d592a-118">Vous n’avez pas besoin de déployer un Survivable Branch appliance sur le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="d592a-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="d592a-119">Si la liaison entre votre site de succursale et le site central n’est pas résiliente, déployez un Survivable Branch Appliance ou déployez un serveur Survivable Branch Server avec une jonction passerelle ou SIP sur le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="d592a-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

