---
title: 'Lync Server 2013 : planification de la découverte automatique'
description: 'Lync Server 2013 : planification de la découverte automatique.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e28a6a3a317f063151eadde7c5de51b02a46b482
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544630"
---
# <a name="planning-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="8810b-103">Planification de la découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8810b-103">Planning for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8810b-104">_**Dernière modification de la rubrique :** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="8810b-104">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="8810b-105">La découverte automatique a été introduite pour Lync Server dans la mise à jour cumulative pour Lync Server 2010 : novembre 2011.</span><span class="sxs-lookup"><span data-stu-id="8810b-105">Autodiscover was introduced for Lync Server in the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="8810b-106">L’objectif principal de cette implémentation initiale de la découverte automatique était de permettre à Lync mobile de localiser le service de mobilité (MCX).</span><span class="sxs-lookup"><span data-stu-id="8810b-106">The primary purpose for this initial implementation of Autodiscover was to provide a means for Lync Mobile to locate the Mobility service (Mcx).</span></span> <span data-ttu-id="8810b-107">Le service de découverte automatique dans Lync Server 2013 est désormais un service utilisé par tous les clients pour localiser les services de serveur et d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8810b-107">The Autodiscover service in Lync Server 2013 is now a service used by all clients to locate server and user services.</span></span> <span data-ttu-id="8810b-108">Le service de découverte automatique Microsoft Lync Server 2013 s’exécute sur les directeurs et les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="8810b-108">The Microsoft Lync Server 2013 Autodiscover service runs on Directors and Front End Servers.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="8810b-109">Pour une compréhension plus technique de la découverte automatique et des informations communiquées aux clients, voir <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8810b-109">For a more technical understanding of Autodiscover and what is communicated to clients, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="8810b-110">La mobilité est toujours un scénario distinct et les services de mobilité nécessitent toujours une planification particulière.</span><span class="sxs-lookup"><span data-stu-id="8810b-110">Mobility is still a distinct scenario and the Mobility services still require some special planning.</span></span> <span data-ttu-id="8810b-111">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-planning-for-mobility.md">Planning for Mobility in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8810b-111">For additional details, see <A href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="8810b-112">Lorsque la découverte automatique a été introduite dans Lync Server 2010, il y a eu des compromis à effectuer afin d’implémenter un service nécessitant des modifications de certificat potentielles pour les déploiements de serveurs existants.</span><span class="sxs-lookup"><span data-stu-id="8810b-112">When Autodiscover was introduced in Lync Server 2010, there were compromises that needed to be made in order to implement a service that required potential certificate changes to existing server deployments.</span></span> <span data-ttu-id="8810b-113">La découverte automatique peut être utilisée via le port TCP 443 pour HTTPs ou via le port TCP 80 pour HTTP.</span><span class="sxs-lookup"><span data-stu-id="8810b-113">Autodiscover could be used over port TCP 443 for HTTPS or over port TCP 80 for HTTP.</span></span> <span data-ttu-id="8810b-114">Si la décision a été prise pour utiliser le protocole HTTPs, les certificats sur les proxys inverses, les directeurs et les serveurs frontaux devaient être réémiss afin de prendre en charge les `lyncdiscover.<domain>` enregistrements requis et `lyncdiscoverinternal.<domain>` DNS.</span><span class="sxs-lookup"><span data-stu-id="8810b-114">If the decision was made to use HTTPS, certificates on reverse proxies, Directors, and Front End Servers needed to be reissued in order to accommodate the required `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` DNS records.</span></span> <span data-ttu-id="8810b-115">Si la décision consistait à utiliser le protocole HTTP, la réémission de certificats pourrait être évitée en utilisant des enregistrements DNS CNAMe (ou alias) pour utiliser des noms existants sur les certificats.</span><span class="sxs-lookup"><span data-stu-id="8810b-115">If the decision was to use HTTP, the reissue of certificates could be avoided by using DNS CNAME (or alias) records to use existing names on the certificates.</span></span> <span data-ttu-id="8810b-116">L’utilisation du protocole HTTP signifie que les communications initiales n’étaient pas chiffrées.</span><span class="sxs-lookup"><span data-stu-id="8810b-116">Using HTTP did mean that the initial communications were unencrypted.</span></span>

<span data-ttu-id="8810b-117">Étant donné que Lync Server 2013 utilise la découverte automatique pour tous les clients, le scénario principal consiste à utiliser exclusivement HTTPs et à créer des certificats avec lyncdiscover.\<domain\></span><span class="sxs-lookup"><span data-stu-id="8810b-117">Because Lync Server 2013 uses Autodiscover for all clients, the main scenario is to use HTTPS exclusively and to create certificates with lyncdiscover.\<domain\></span></span> <span data-ttu-id="8810b-118">dans le cadre de la configuration de proxys inverses, de directeurs et de serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="8810b-118">as part of the configuration of reverse proxies, Directors and Front End Servers.</span></span> <span data-ttu-id="8810b-119">Si vous implémentez la découverte automatique dans un déploiement mis à niveau à partir de Lync Server 2010, vous pouvez utiliser le protocole HTTP pour éviter de réémettre des certificats.</span><span class="sxs-lookup"><span data-stu-id="8810b-119">If you are implementing Autodiscover into an upgraded deployment from Lync Server 2010, you may want to use HTTP to avoid reissuing certificates.</span></span> <span data-ttu-id="8810b-120">Les instructions pour les deux scénarios sont fournies dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="8810b-120">Guidance for both scenarios is provided in the following sections.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8810b-121">La liste des autres noms de sujet sur les certificats utilisés par la règle de publication des services Web externes doit contenir un <EM>lyncdiscover. &lt; entrée &gt; sipdomain</EM> pour chaque domaine SIP au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8810b-121">The subject alternative name list on certificates used by the external web services publishing rule must contain a <EM>lyncdiscover.&lt;sipdomain&gt;</EM> entry for each SIP domain within your organization.</span></span> <span data-ttu-id="8810b-122">Pour plus d’informations sur les entrées des autres noms de sujet requises pour les directeurs, les serveurs frontaux et les proxys inverses, voir <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate Summary-Autodiscover dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8810b-122">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate summary - Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8810b-123">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="8810b-123">In This Section</span></span>

  - [<span data-ttu-id="8810b-124">Résumé des certificats-découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8810b-124">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)

  - [<span data-ttu-id="8810b-125">Résumé des ports-découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8810b-125">Port summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-port-summary-autodiscover.md)

  - [<span data-ttu-id="8810b-126">Résumé des enregistrements DNS-découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8810b-126">DNS summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-dns-summary-autodiscover.md)

  - [<span data-ttu-id="8810b-127">Découverte automatique de domaine hybride et fractionné dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8810b-127">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

