---
title: 'Lync Server 2013: planification de la découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a1d0ce7a775bc73c5f3afa10d1f9c148395b0eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="63798-102">Planification de la découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63798-102">Planning for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63798-103">_**Dernière modification de la rubrique:** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="63798-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="63798-104">La découverte automatique a été introduite pour Lync Server dans la mise à jour cumulative pour Lync Server 2010: novembre 2011.</span><span class="sxs-lookup"><span data-stu-id="63798-104">Autodiscover was introduced for Lync Server in the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="63798-105">L’objectif principal de cette implémentation initiale de la découverte automatique était d’offrir à Lync mobile la possibilité de rechercher le service de mobilité (MCX).</span><span class="sxs-lookup"><span data-stu-id="63798-105">The primary purpose for this initial implementation of Autodiscover was to provide a means for Lync Mobile to locate the Mobility service (Mcx).</span></span> <span data-ttu-id="63798-106">Le service de découverte automatique de Lync Server 2013 est désormais un service utilisé par tous les clients pour localiser les services serveur et utilisateur.</span><span class="sxs-lookup"><span data-stu-id="63798-106">The Autodiscover service in Lync Server 2013 is now a service used by all clients to locate server and user services.</span></span> <span data-ttu-id="63798-107">Le service de découverte automatique Microsoft Lync Server 2013 s’exécute sur les directeurs et les serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="63798-107">The Microsoft Lync Server 2013 Autodiscover service runs on Directors and Front End Servers.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="63798-108">Pour plus d’informations techniques sur la découverte automatique et la façon de communiquer avec les clients, voir <A href="lync-server-2013-understanding-autodiscover.md">comprendre la découverte automatique dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="63798-108">For a more technical understanding of Autodiscover and what is communicated to clients, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="63798-109">La mobilité reste un scénario distinct et les services de mobilité nécessitent toujours une planification particulière.</span><span class="sxs-lookup"><span data-stu-id="63798-109">Mobility is still a distinct scenario and the Mobility services still require some special planning.</span></span> <span data-ttu-id="63798-110">Pour plus d’informations, consultez <A href="lync-server-2013-planning-for-mobility.md">planification de la mobilité dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="63798-110">For additional details, see <A href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="63798-111">Lorsque la découverte automatique a été introduite dans Lync Server 2010, il y a eu des compromis à mettre en place pour implémenter un service qui nécessitait des changements de certificats potentiels pour les déploiements de serveur existants.</span><span class="sxs-lookup"><span data-stu-id="63798-111">When Autodiscover was introduced in Lync Server 2010, there were compromises that needed to be made in order to implement a service that required potential certificate changes to existing server deployments.</span></span> <span data-ttu-id="63798-112">La découverte automatique peut être utilisée via le port TCP 443 pour HTTPs ou sur le port TCP 80 pour HTTP.</span><span class="sxs-lookup"><span data-stu-id="63798-112">Autodiscover could be used over port TCP 443 for HTTPS or over port TCP 80 for HTTP.</span></span> <span data-ttu-id="63798-113">S’il s’agit d’une décision d’utiliser HTTPs, les certificats des proxys inversés, des directeurs et des serveurs frontaux nécessaires doivent être réémis pour `lyncdiscover.<domain>` pouvoir `lyncdiscoverinternal.<domain>` accueillir les enregistrements DNS et obligatoires.</span><span class="sxs-lookup"><span data-stu-id="63798-113">If the decision was made to use HTTPS, certificates on reverse proxies, Directors, and Front End Servers needed to be reissued in order to accommodate the required `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` DNS records.</span></span> <span data-ttu-id="63798-114">Si la décision consistait à utiliser HTTP, le réémission de certificats peut être évité en utilisant des enregistrements DNS CNAMe (ou alias) pour utiliser les noms existants sur les certificats.</span><span class="sxs-lookup"><span data-stu-id="63798-114">If the decision was to use HTTP, the reissue of certificates could be avoided by using DNS CNAME (or alias) records to use existing names on the certificates.</span></span> <span data-ttu-id="63798-115">L’utilisation de HTTP signifie que les communications initiales n’ont pas été chiffrées.</span><span class="sxs-lookup"><span data-stu-id="63798-115">Using HTTP did mean that the initial communications were unencrypted.</span></span>

<span data-ttu-id="63798-116">Dans la mesure où Lync Server 2013 utilise la découverte automatique pour tous les clients, le scénario principal consiste à utiliser HTTPs en exclusivité et à créer des certificats avec lyncdiscover. \<Domain\> dans le cadre de la configuration de proxys inverse, de directeurs et de serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="63798-116">Because Lync Server 2013 uses Autodiscover for all clients, the main scenario is to use HTTPS exclusively and to create certificates with lyncdiscover.\<domain\> as part of the configuration of reverse proxies, Directors and Front End Servers.</span></span> <span data-ttu-id="63798-117">Si vous implémentez la découverte automatique dans un déploiement mis à niveau à partir de Lync Server 2010, il est possible que vous souhaitiez utiliser HTTP pour éviter de réémettre des certificats.</span><span class="sxs-lookup"><span data-stu-id="63798-117">If you are implementing Autodiscover into an upgraded deployment from Lync Server 2010, you may want to use HTTP to avoid reissuing certificates.</span></span> <span data-ttu-id="63798-118">Les instructions pour ces deux scénarios sont fournies dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="63798-118">Guidance for both scenarios is provided in the following sections.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="63798-119">La liste autre nom de l’objet sur les certificats utilisés par la règle de publication des services Web externes doit contenir un <EM>lyncdiscover.&lt; entrée&gt; sipdomain</EM> pour chaque domaine SIP au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="63798-119">The subject alternative name list on certificates used by the external web services publishing rule must contain a <EM>lyncdiscover.&lt;sipdomain&gt;</EM> entry for each SIP domain within your organization.</span></span> <span data-ttu-id="63798-120">Pour plus d’informations sur les autres entrées de nom de l’objet requises pour les directeurs, serveurs frontaux et proxys inversés, voir <A href="lync-server-2013-certificate-summary-autodiscover.md">synthèse des certificats-découverte automatique dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="63798-120">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate summary - Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="63798-121">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="63798-121">In This Section</span></span>

  - [<span data-ttu-id="63798-122">Résumé du certificat-découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63798-122">Certificate summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-autodiscover.md)

  - [<span data-ttu-id="63798-123">Résumé du port-découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63798-123">Port summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-port-summary-autodiscover.md)

  - [<span data-ttu-id="63798-124">DNS Summary-découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63798-124">DNS summary - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-dns-summary-autodiscover.md)

  - [<span data-ttu-id="63798-125">Domaines hybrides et fractionnés-découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="63798-125">Hybrid and split-domain - Autodiscover in Lync Server 2013</span></span>](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

