---
title: 'Lync Server 2013 : configuration de la prise en charge de la découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bbb9007562dfecdc4f38b6cf8ac3f1579094ed6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="6e346-102">Configuration de la prise en charge du service de découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e346-102">Configuring support for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e346-103">_**Dernière modification de la rubrique :** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="6e346-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="6e346-104">Le **service de découverte automatique** des services Web Lync Server est d’abord apparu dans la mise à jour cumulative lync Server 2010 : novembre 2011.</span><span class="sxs-lookup"><span data-stu-id="6e346-104">The Lync Server web services **Autodiscover service** first appeared in the Lync Server 2010 Cumulative Update: November 2011.</span></span> <span data-ttu-id="6e346-105">Cette mise à jour est accompagnée de la version initiale des clients mobiles Lync.</span><span class="sxs-lookup"><span data-stu-id="6e346-105">This update was accompanied by the initial release of Lync Mobile clients.</span></span> <span data-ttu-id="6e346-106">Le service de découverte automatique exposait les services de mobilité, appelé service MCX.</span><span class="sxs-lookup"><span data-stu-id="6e346-106">The autodiscover service exposed the mobility services, known as the Mcx service.</span></span>

<span data-ttu-id="6e346-107">Le service de découverte automatique agit en tant qu’emplacement unique pour tous les clients afin de demander des informations sur les services et les fonctionnalités disponibles, ainsi que sur la façon de contacter les services, soit par un nom de domaine complet, soit par une référence Web Uniform Resource Locator.</span><span class="sxs-lookup"><span data-stu-id="6e346-107">The autodiscover service acts as a single location for all clients to request information on what services and features are available, and how to contact the sevices – either by a fully qualified domain name or a web uniform resource locator reference.</span></span> <span data-ttu-id="6e346-108">La découverte automatique expose un certain nombre de fonctionnalités, et chaque client effectue des demandes en fonction des fonctionnalités que le client peut utiliser.</span><span class="sxs-lookup"><span data-stu-id="6e346-108">Autodiscover exposes a number of features, and each client will make requests based on the features that the client can use.</span></span> <span data-ttu-id="6e346-109">Par exemple, un client de bureau Lync 2013 utilisera autodiscvoer pour déterminer les services Web externes, mais n’utilisera pas les services de mobilité (MCX).</span><span class="sxs-lookup"><span data-stu-id="6e346-109">For example, a desktop Lync 2013 client will use autodiscvoer to determine the external web services, but will not use the mobility (Mcx) services.</span></span> <span data-ttu-id="6e346-110">Pour définir correctement et permettre à vos clients d’utiliser les fonctionnalités disponibles, les scénarios qui permettent à un client de trouver et d’utiliser efficacement des entrées de découverte automatique doivent être définis.</span><span class="sxs-lookup"><span data-stu-id="6e346-110">To properly define and enable your clients to use the features available to them, the scenarios that allow a client to effectively find and use autodiscover entries should be defined.</span></span> <span data-ttu-id="6e346-111">Pour utiliser autodoscover, votre déploiement nécessite qu’un proxy inverse publie les services Web Lync Server, que les enregistrements DNS soient configurés pour résoudre les requêtes DNS pour le service de découverte automatique Lync Server et les services Web Lync Server, et que les services de certificats sont correctement configurés pour votre scénario spécifique.</span><span class="sxs-lookup"><span data-stu-id="6e346-111">To use autodoscover, your deployment requires that a reverse proxy publishes the Lync Server web services, that DNS records are configured to resolve DNS queries for the Lync Server autodiscover service and Lync Server web services, and that certificate services are properly configured for your specific scenario.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="6e346-112">Pour obtenir des informations techniques sur les éléments inclus dans la demande/réponse de découverte automatique, voir <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6e346-112">For technical details on what the elements within the autodiscover request/response do, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="6e346-113">Les informations et les tableaux suivants définissent, par scénario, les configurations (le cas échéant) que vous devez implémenter pour fournir l’utilisation complète et efficace du service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="6e346-113">The following information and tables define, per scenario, what configurations (if any) you need to implement to provide the full and effective use of the autodiscover service.</span></span> <span data-ttu-id="6e346-114">Les informations contenues dans les rubriques suivantes sont propres à Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6e346-114">The information in the following topics is specific to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="6e346-115">Si vous recherchez des instructions sur la planification de la mobilité pour Lync Server 2010, reportez-vous à la rubrique [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113).</span><span class="sxs-lookup"><span data-stu-id="6e346-115">If you are looking for guidance on how to plan Mobility for Lync Server 2010, see [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113).</span></span> <span data-ttu-id="6e346-116">Pour déployer la mobilité pour Lync Server 2010, reportez-vous à[https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)</span><span class="sxs-lookup"><span data-stu-id="6e346-116">To deploy Mobility for Lync Server 2010, see [https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6e346-117">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="6e346-117">In This Section</span></span>

  - [<span data-ttu-id="6e346-118">Configuration de DNS pour la découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e346-118">Configuring DNS for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [<span data-ttu-id="6e346-119">Configuration de certificats pour la découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e346-119">Configuring certificates for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [<span data-ttu-id="6e346-120">Configuration d’un proxy inverse pour la découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e346-120">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [<span data-ttu-id="6e346-121">Configuration de la découverte automatique dans Lync Server 2013 pour les déploiements hybrides</span><span class="sxs-lookup"><span data-stu-id="6e346-121">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

