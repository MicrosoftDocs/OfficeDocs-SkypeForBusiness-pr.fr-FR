---
title: 'Lync Server 2013: conception de la topologie à l’aide de l’outil de planification'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Designing the topology by using the Planning Tool
ms:assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558631(v=OCS.15)
ms:contentKeyID: 51541454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09cfa16103f4e6e2ebfa2327edbd330311753609
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-topology-for-lync-server-2013-by-using-the-planning-tool"></a><span data-ttu-id="9fdef-102">Conception de la topologie pour Lync Server 2013 à l’aide de l’outil de planification</span><span class="sxs-lookup"><span data-stu-id="9fdef-102">Designing the topology for Lync Server 2013 by using the Planning Tool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fdef-103">_**Dernière modification de la rubrique:** 2013-03-04_</span><span class="sxs-lookup"><span data-stu-id="9fdef-103">_**Topic Last Modified:** 2013-03-04_</span></span>

<span data-ttu-id="9fdef-104">Microsoft Lync Server 2013, outil de planification est un outil piloté par un Assistant, qui pose des questions sur la topologie Lync Server 2013 que vous concevez.</span><span class="sxs-lookup"><span data-stu-id="9fdef-104">The Microsoft Lync Server 2013, Planning Tool is a wizard driven, interview-like tool that asks questions about the Lync Server 2013 topology that you are designing.</span></span> <span data-ttu-id="9fdef-105">L’outil de planification utilise les informations fournies, associées à des pratiques recommandées en matière de conception et de capacité topologique, pour présenter une topologie recommandée selon les réponses fournies.</span><span class="sxs-lookup"><span data-stu-id="9fdef-105">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="9fdef-106">Vous pouvez télécharger l’outil de planification à partir du centre de[http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)téléchargement Microsoft ().</span><span class="sxs-lookup"><span data-stu-id="9fdef-106">You can download the Planning Tool from the Microsoft Downloads Center ([http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)).</span></span>

<span data-ttu-id="9fdef-107">En fin de compte, l’objectif de l’outil de planification consiste à faciliter la complexité de la conception d’une topologie Lync Server 2013 complète.</span><span class="sxs-lookup"><span data-stu-id="9fdef-107">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Lync Server 2013 topology.</span></span> <span data-ttu-id="9fdef-108">L’outil fournit aussi des références contextuelles à la documentation de planification et de déploiement (à la condition de disposer d’une connexion Internet pour accéder au site web Microsoft TechNet).</span><span class="sxs-lookup"><span data-stu-id="9fdef-108">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>

<span data-ttu-id="9fdef-109">Après avoir personnalisé la topologie avec les adresses TCP/IP de l’infrastructure et les noms de domaine complets (FQDN), l’outil de planification met à votre disposition une série de rapports qui couvrent l’attribution de noms DNS (Domain Name System), les règles de pare-feu, les certificats, etc.</span><span class="sxs-lookup"><span data-stu-id="9fdef-109">After customizing the topology with the infrastructure’s TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span>

<span data-ttu-id="9fdef-110">L’outil de planification offre également la possibilité d’exporter des informations dans deux formats:</span><span class="sxs-lookup"><span data-stu-id="9fdef-110">The Planning Tool also provides the ability to export information in two formats:</span></span>

  - <span data-ttu-id="9fdef-111">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="9fdef-111">Microsoft Excel</span></span>

  - <span data-ttu-id="9fdef-112">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="9fdef-112">Microsoft Visio</span></span>

<span data-ttu-id="9fdef-113">Les rubriques suivantes présentent et décrivent en détail l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="9fdef-113">The following topics introduce and detail the Planning Tool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9fdef-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="9fdef-114">In This Section</span></span>

  - [<span data-ttu-id="9fdef-115">Installation de l’outil de planification dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fdef-115">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)

  - [<span data-ttu-id="9fdef-116">Installer un logiciel facultatif dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fdef-116">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)

  - [<span data-ttu-id="9fdef-117">Navigation dans l’outil de planification de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fdef-117">Navigating the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-navigating-the-planning-tool.md)

  - [<span data-ttu-id="9fdef-118">Créer la conception de topologie initiale pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fdef-118">Create the initial topology design for Lync Server 2013</span></span>](lync-server-2013-create-the-initial-topology-design.md)

  - [<span data-ttu-id="9fdef-119">Consultation des rapports de l’administrateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fdef-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9fdef-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9fdef-120">See Also</span></span>


[<span data-ttu-id="9fdef-121">Déploiement de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fdef-121">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
[<span data-ttu-id="9fdef-122">Planification des serveurs frontaux, de la messagerie instantanée et de la présence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9fdef-122">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

