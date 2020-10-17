---
title: 'Lync Server 2013 : conception de la topologie à l’aide de l’outil de planification'
description: 'Lync Server 2013 : conception de la topologie à l’aide de l’outil de planification.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the topology by using the Planning Tool
ms:assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558631(v=OCS.15)
ms:contentKeyID: 51541454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcc10d09d7b8b815e2b4924d06c10de23c14236b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542590"
---
# <a name="designing-the-topology-for-lync-server-2013-by-using-the-planning-tool"></a><span data-ttu-id="7d692-103">Conception de la topologie pour Lync Server 2013 à l’aide de l’outil de planification</span><span class="sxs-lookup"><span data-stu-id="7d692-103">Designing the topology for Lync Server 2013 by using the Planning Tool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d692-104">_**Dernière modification de la rubrique :** 2013-03-04_</span><span class="sxs-lookup"><span data-stu-id="7d692-104">_**Topic Last Modified:** 2013-03-04_</span></span>

<span data-ttu-id="7d692-105">L’outil de planification Microsoft Lync Server 2013 est un assistant basé sur un interview qui pose des questions sur la topologie Lync Server 2013 que vous concevez.</span><span class="sxs-lookup"><span data-stu-id="7d692-105">The Microsoft Lync Server 2013, Planning Tool is a wizard driven, interview-like tool that asks questions about the Lync Server 2013 topology that you are designing.</span></span> <span data-ttu-id="7d692-106">L’outil de planification utilise les informations fournies, associées aux pratiques recommandées pour la conception et la capacité de la topologie, afin de présenter une topologie recommandée en fonction des réponses fournies.</span><span class="sxs-lookup"><span data-stu-id="7d692-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="7d692-107">Vous pouvez télécharger l’outil de planification à partir du centre de téléchargement Microsoft ( [https://go.microsoft.com/fwlink/?LinkID=282725](https://go.microsoft.com/fwlink/?linkid=282725) ).</span><span class="sxs-lookup"><span data-stu-id="7d692-107">You can download the Planning Tool from the Microsoft Downloads Center ([https://go.microsoft.com/fwlink/?LinkID=282725](https://go.microsoft.com/fwlink/?linkid=282725)).</span></span>

<span data-ttu-id="7d692-108">En fin de compte, l’objectif de l’outil de planification est de faciliter la conception d’une topologie Lync Server 2013 complète.</span><span class="sxs-lookup"><span data-stu-id="7d692-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Lync Server 2013 topology.</span></span> <span data-ttu-id="7d692-109">L’outil fournit aussi des références contextuelles à la documentation de planification et de déploiement (à la condition de disposer d’une connexion Internet pour accéder au site Web Microsoft TechNet).</span><span class="sxs-lookup"><span data-stu-id="7d692-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>

<span data-ttu-id="7d692-110">Après avoir personnalisé la topologie avec les adresses TCP/IP de l’infrastructure et les noms de domaine complets (FQDN), l’outil de planification met à disposition une série de rapports qui traitent de l’appellation DNS (Domain Name System), des règles de pare-feu, des certificats, etc.</span><span class="sxs-lookup"><span data-stu-id="7d692-110">After customizing the topology with the infrastructure’s TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span>

<span data-ttu-id="7d692-111">L’outil de planification permet également d’exporter des informations dans deux formats :</span><span class="sxs-lookup"><span data-stu-id="7d692-111">The Planning Tool also provides the ability to export information in two formats:</span></span>

  - <span data-ttu-id="7d692-112">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="7d692-112">Microsoft Excel</span></span>

  - <span data-ttu-id="7d692-113">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="7d692-113">Microsoft Visio</span></span>

<span data-ttu-id="7d692-114">Les rubriques suivantes présentent et détaillent l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="7d692-114">The following topics introduce and detail the Planning Tool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7d692-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="7d692-115">In This Section</span></span>

  - [<span data-ttu-id="7d692-116">Installation de l’outil de planification dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d692-116">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)

  - [<span data-ttu-id="7d692-117">Installation de logiciels facultatifs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d692-117">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)

  - [<span data-ttu-id="7d692-118">Navigation dans l’outil de planification dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d692-118">Navigating the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-navigating-the-planning-tool.md)

  - [<span data-ttu-id="7d692-119">Création de la conception de topologie initiale pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d692-119">Create the initial topology design for Lync Server 2013</span></span>](lync-server-2013-create-the-initial-topology-design.md)

  - [<span data-ttu-id="7d692-120">Examen des rapports de l’administrateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d692-120">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7d692-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7d692-121">See Also</span></span>


[<span data-ttu-id="7d692-122">Déploiement de Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d692-122">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
[<span data-ttu-id="7d692-123">Planification des serveurs frontaux, de la messagerie instantanée et de la présence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d692-123">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

