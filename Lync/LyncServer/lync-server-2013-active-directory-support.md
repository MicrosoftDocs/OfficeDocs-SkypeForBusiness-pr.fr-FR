---
title: Prise en charge d’Active Directory dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a7da4487c376ceea4c5c3e41e20a55874b27f06
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a><span data-ttu-id="a1fc3-102">Prise en charge d’Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1fc3-102">Active Directory support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1fc3-103">_**Dernière modification de la rubrique :** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="a1fc3-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="a1fc3-104">Les topologies locales des services de domaine Active Directory prises en charge par Lync Server 2013 sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1fc3-104">The Active Directory Domain Services on-premises topologies that are supported by Lync Server 2013 are as follows:</span></span>

  - <span data-ttu-id="a1fc3-105">Forêt unique avec domaine unique</span><span class="sxs-lookup"><span data-stu-id="a1fc3-105">Single forest with single domain</span></span>

  - <span data-ttu-id="a1fc3-106">Forêt unique avec un arbre unique et plusieurs domaines</span><span class="sxs-lookup"><span data-stu-id="a1fc3-106">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="a1fc3-107">Forêt unique avec plusieurs arbres et des espaces de noms disjoints</span><span class="sxs-lookup"><span data-stu-id="a1fc3-107">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="a1fc3-108">Plusieurs forêts dans une topologie de forêt centrale</span><span class="sxs-lookup"><span data-stu-id="a1fc3-108">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="a1fc3-109">Plusieurs forêts dans une topologie de forêt de ressources</span><span class="sxs-lookup"><span data-stu-id="a1fc3-109">Multiple forests in a resource forest topology</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a1fc3-110">Lync Server 2013 ne prend pas en charge les domaines en une seule partie.</span><span class="sxs-lookup"><span data-stu-id="a1fc3-110">Lync Server 2013 does not support single-label domains.</span></span> <span data-ttu-id="a1fc3-111">Par exemple, une forêt avec un domaine racine nommé <STRONG>contoso. local</STRONG> est prise en charge, mais un domaine racine à une seule étiquette nommé <STRONG>local</STRONG> n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="a1fc3-111">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a single-label root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="a1fc3-112">Pour plus d’informations, consultez l’article 300684 de la base de connaissances Microsoft, « informations sur la configuration de Windows pour les domaines avec <A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A>des noms DNS en une seule partie », à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="a1fc3-112">For details, see Microsoft Knowledge Base article 300684, "Information about configuring Windows for domains with single-label DNS names," at <A href="https://go.microsoft.com/fwlink/p/?linkid=143752">https://go.microsoft.com/fwlink/p/?linkId=143752</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a1fc3-113">Lync Server 2013 ne prend pas en charge le changement de nom des domaines.</span><span class="sxs-lookup"><span data-stu-id="a1fc3-113">Lync Server 2013 does not support renaming domains.</span></span> <span data-ttu-id="a1fc3-114">Si vous devez renommer un domaine où Lync Server est déployé, vous devez d’abord désinstaller Lync Server, renommer le domaine, puis réinstaller Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a1fc3-114">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

<span data-ttu-id="a1fc3-115">Pour plus d’informations sur les topologies et les exigences prises en charge pour les déploiements sur site, voir [Active Directory Domain Services Requirements, support et topologies dans Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="a1fc3-115">For details about supported topologies and requirements for on-premises deployments, see [Active Directory Domain Services requirements, support, and topologies in Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

