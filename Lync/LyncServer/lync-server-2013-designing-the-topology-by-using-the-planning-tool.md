---
title: 'Lync Server 2013 : conception de la topologie à l’aide de l’outil de planification'
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
ms.openlocfilehash: bca2871acdaf67e318e7e402d78f34748de4b722
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-topology-for-lync-server-2013-by-using-the-planning-tool"></a><span data-ttu-id="b928d-102">Conception de la topologie pour Lync Server 2013 à l’aide de l’outil de planification</span><span class="sxs-lookup"><span data-stu-id="b928d-102">Designing the topology for Lync Server 2013 by using the Planning Tool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b928d-103">_**Dernière modification de la rubrique :** 2013-03-04_</span><span class="sxs-lookup"><span data-stu-id="b928d-103">_**Topic Last Modified:** 2013-03-04_</span></span>

<span data-ttu-id="b928d-104">L’outil de planification Microsoft Lync Server 2013 est un assistant basé sur un interview qui pose des questions sur la topologie Lync Server 2013 que vous concevez.</span><span class="sxs-lookup"><span data-stu-id="b928d-104">The Microsoft Lync Server 2013, Planning Tool is a wizard driven, interview-like tool that asks questions about the Lync Server 2013 topology that you are designing.</span></span> <span data-ttu-id="b928d-105">L’outil de planification utilise les informations fournies, associées aux pratiques recommandées pour la conception et la capacité de la topologie, afin de présenter une topologie recommandée en fonction des réponses fournies.</span><span class="sxs-lookup"><span data-stu-id="b928d-105">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="b928d-106">Vous pouvez télécharger l’outil de planification à partir du centre de[http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)téléchargement Microsoft ().</span><span class="sxs-lookup"><span data-stu-id="b928d-106">You can download the Planning Tool from the Microsoft Downloads Center ([http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)).</span></span>

<span data-ttu-id="b928d-107">En fin de compte, l’objectif de l’outil de planification est de faciliter la conception d’une topologie Lync Server 2013 complète.</span><span class="sxs-lookup"><span data-stu-id="b928d-107">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Lync Server 2013 topology.</span></span> <span data-ttu-id="b928d-108">L’outil fournit aussi des références contextuelles à la documentation de planification et de déploiement (à la condition de disposer d’une connexion Internet pour accéder au site Web Microsoft TechNet).</span><span class="sxs-lookup"><span data-stu-id="b928d-108">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>

<span data-ttu-id="b928d-109">Après avoir personnalisé la topologie avec les adresses TCP/IP de l’infrastructure et les noms de domaine complets (FQDN), l’outil de planification met à disposition une série de rapports qui traitent de l’appellation DNS (Domain Name System), des règles de pare-feu, des certificats, etc.</span><span class="sxs-lookup"><span data-stu-id="b928d-109">After customizing the topology with the infrastructure’s TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span>

<span data-ttu-id="b928d-110">L’outil de planification permet également d’exporter des informations dans deux formats :</span><span class="sxs-lookup"><span data-stu-id="b928d-110">The Planning Tool also provides the ability to export information in two formats:</span></span>

  - <span data-ttu-id="b928d-111">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="b928d-111">Microsoft Excel</span></span>

  - <span data-ttu-id="b928d-112">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="b928d-112">Microsoft Visio</span></span>

<span data-ttu-id="b928d-113">Les rubriques suivantes présentent et détaillent l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="b928d-113">The following topics introduce and detail the Planning Tool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b928d-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="b928d-114">In This Section</span></span>

  - [<span data-ttu-id="b928d-115">Installation de l’outil de planification dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b928d-115">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)

  - [<span data-ttu-id="b928d-116">Installation de logiciels facultatifs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b928d-116">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)

  - [<span data-ttu-id="b928d-117">Navigation dans l’outil de planification dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b928d-117">Navigating the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-navigating-the-planning-tool.md)

  - [<span data-ttu-id="b928d-118">Création de la conception de topologie initiale pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b928d-118">Create the initial topology design for Lync Server 2013</span></span>](lync-server-2013-create-the-initial-topology-design.md)

  - [<span data-ttu-id="b928d-119">Examen des rapports de l’administrateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b928d-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b928d-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b928d-120">See Also</span></span>


[<span data-ttu-id="b928d-121">Déploiement de Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b928d-121">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
[<span data-ttu-id="b928d-122">Planification des serveurs frontaux, de la messagerie instantanée et de la présence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b928d-122">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

