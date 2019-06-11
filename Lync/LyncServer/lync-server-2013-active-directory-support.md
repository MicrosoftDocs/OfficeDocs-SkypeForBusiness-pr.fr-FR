---
title: Prise en charge d’Active Directory dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9be3bda71e44d0e739fce3a8d01db9cb84e2b9e3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a><span data-ttu-id="a3caf-102">Prise en charge d’Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3caf-102">Active Directory support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3caf-103">_**Dernière modification de la rubrique:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="a3caf-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="a3caf-104">Les topologies locales services de domaine Active Directory prises en charge par Lync Server 2013 sont les suivantes:</span><span class="sxs-lookup"><span data-stu-id="a3caf-104">The Active Directory Domain Services on-premises topologies that are supported by Lync Server 2013 are as follows:</span></span>

  - <span data-ttu-id="a3caf-105">Forêt unique avec domaine unique</span><span class="sxs-lookup"><span data-stu-id="a3caf-105">Single forest with single domain</span></span>

  - <span data-ttu-id="a3caf-106">Forêt unique avec un arbre unique et plusieurs domaines</span><span class="sxs-lookup"><span data-stu-id="a3caf-106">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="a3caf-107">Forêt unique avec plusieurs arbres et des espaces de noms disjoints</span><span class="sxs-lookup"><span data-stu-id="a3caf-107">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="a3caf-108">Plusieurs forêts dans une topologie de forêt centrale</span><span class="sxs-lookup"><span data-stu-id="a3caf-108">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="a3caf-109">Plusieurs forêts dans une topologie de forêt de ressources</span><span class="sxs-lookup"><span data-stu-id="a3caf-109">Multiple forests in a resource forest topology</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a3caf-110">Lync Server 2013 ne prend pas en charge les domaines à étiquette unique.</span><span class="sxs-lookup"><span data-stu-id="a3caf-110">Lync Server 2013 does not support single-label domains.</span></span> <span data-ttu-id="a3caf-111">Par exemple, une forêt avec un domaine racine appelé <STRONG>contoso. local</STRONG> est prise en charge, mais un domaine racine à une seule étiquette nommé <STRONG>local</STRONG> n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="a3caf-111">For example, a forest with a root domain named <STRONG>contoso.local</STRONG> is supported, but a single-label root domain named <STRONG>local</STRONG> is not supported.</span></span> <span data-ttu-id="a3caf-112">Pour plus d’informations, reportez-vous à l’article 300684 de la base de connaissances Microsoft, intitulé «informations sur la configuration <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>de Windows pour les domaines avec des noms DNS en une seule étiquette».</span><span class="sxs-lookup"><span data-stu-id="a3caf-112">For details, see Microsoft Knowledge Base article 300684, "Information about configuring Windows for domains with single-label DNS names," at <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a3caf-113">Lync Server 2013 ne prend pas en charge le changement de nom de domaines.</span><span class="sxs-lookup"><span data-stu-id="a3caf-113">Lync Server 2013 does not support renaming domains.</span></span> <span data-ttu-id="a3caf-114">Si vous avez besoin de renommer un domaine sur lequel Lync Server est déployé, vous devez commencer par désinstaller Lync Server, puis renommer le domaine, puis réinstaller Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a3caf-114">If you need to rename a domain where Lync Server is deployed, you need to first uninstall Lync Server, then rename the domain, and then reinstall Lync Server.</span></span>



</div>

<span data-ttu-id="a3caf-115">Pour plus d’informations sur les topologies prises en charge et la configuration requise pour les déploiements sur site, voir [Configuration requise pour les services de domaine Active Directory, support et topologies dans Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="a3caf-115">For details about supported topologies and requirements for on-premises deployments, see [Active Directory Domain Services requirements, support, and topologies in Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

