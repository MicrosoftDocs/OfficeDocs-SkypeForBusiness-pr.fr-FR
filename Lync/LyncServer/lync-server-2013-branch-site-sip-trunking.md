---
title: 'Lync Server 2013 : trunking SIP site de filiale'
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
ms.openlocfilehash: 9c31f0f42a10905f784536b08f10370be9694800
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="a4ff7-102">Branch site SIP trunking in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4ff7-102">Branch site SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4ff7-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a4ff7-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a4ff7-104">Dans certains cas, il est possible que vous deviez implémenter une agrégation SIP distribuée sur des sites de succursales sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="a4ff7-104">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="a4ff7-105">Pour déterminer si un Trunk SIP est requis pour un site de succursale, voir les informations de la mise en œuvre de l' [agrégation SIP dans Lync Server 2013 ?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="a4ff7-105">To determine whether a SIP trunk is needed for a branch site, review the information in [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="a4ff7-106">Pour plus d’informations sur les options de topologie prises en charge pour le déploiement de Trunks SIP dans les sites de succursales, voir [solutions de résilience de sites de succursales dans Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="a4ff7-106">For details about the supported topology options for deploying SIP trunks in branch sites, see [Branch-site resiliency solutions in Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).</span></span>

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="a4ff7-107">Conditions requises pour le déploiement d’une jonction SIP sur un site de succursale : exemple d’analyse</span><span class="sxs-lookup"><span data-stu-id="a4ff7-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="a4ff7-108">Lorsque vous décidez de déployer un Trunk SIP de site de succursale, vous devez effectuer une analyse de coûts spécifique au site.</span><span class="sxs-lookup"><span data-stu-id="a4ff7-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="a4ff7-109">Par exemple, une entreprise disposant d’un site central dans Redmond, Washington et sur une succursale à New York doit effectuer une analyse pour déterminer s’il est nécessaire de mettre en œuvre un Trunk SIP à partir du site de New York vers un fournisseur de services local.</span><span class="sxs-lookup"><span data-stu-id="a4ff7-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>

<span data-ttu-id="a4ff7-110">Pour savoir si une jonction SIP distribuée à New York est rentable, identifiez les numéros SDA (Sélection Directe à l’Arrivée) qui doivent utiliser la jonction SIP, puis analysez le nombre d’appels à destination de zones en dehors de Redmond (425) que le site de New York passe.</span><span class="sxs-lookup"><span data-stu-id="a4ff7-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="a4ff7-111">Vous pouvez avoir terminé le site de succursale sur le site central.</span><span class="sxs-lookup"><span data-stu-id="a4ff7-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="a4ff7-112">Par exemple, le site central de Redmond peut héberger des numéros ayant été importés pour le site de succursale de New York.</span><span class="sxs-lookup"><span data-stu-id="a4ff7-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="a4ff7-113">Si le coût de l’implémentation d’un Trunk SIP distribué est inférieur au coût de ces appels, envisagez d’implémenter une ligne SIP sur le site de la succursale de New York.</span><span class="sxs-lookup"><span data-stu-id="a4ff7-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span>

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="a4ff7-114">Autres conditions requises pour le déploiement d’une jonction SIP sur un site de succursale</span><span class="sxs-lookup"><span data-stu-id="a4ff7-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="a4ff7-115">Pour déterminer si vous devez déployer une jonction SIP ou une passerelle, comparez le coût des appels PSTN (Public Switched Telephone Network, réseau téléphonique commuté) longue distance de ces deux options.</span><span class="sxs-lookup"><span data-stu-id="a4ff7-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="a4ff7-116">Si vous déployez une ligne SIP site de succursale, vous devez également déterminer votre tolérance de panne et vos besoins en bande passante.</span><span class="sxs-lookup"><span data-stu-id="a4ff7-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="a4ff7-117">Si le lien entre votre site de succursale et votre site central est résilient et dispose d’une bande passante suffisante, vous pouvez déployer une passerelle SIP.</span><span class="sxs-lookup"><span data-stu-id="a4ff7-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="a4ff7-118">Vous n’avez pas besoin de déployer une unité de branchement survivant sur le site de la succursale.</span><span class="sxs-lookup"><span data-stu-id="a4ff7-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="a4ff7-119">Si le lien entre votre site de succursale et votre site central n’est pas résilient, déployez une application de succursale survivant ou déployez un serveur de succursales survivant avec une passerelle ou une ligne SIP sur le site de la succursale.</span><span class="sxs-lookup"><span data-stu-id="a4ff7-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

