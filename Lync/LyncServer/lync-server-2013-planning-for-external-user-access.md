---
title: 'Lync Server 2013 : planification de l’accès des utilisateurs externes'
description: 'Lync Server 2013 : planification de l’accès des utilisateurs externes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8f1854791ed837b963d4c80f3467e4e89555592
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562780"
---
# <a name="planning-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="93208-103">Planification de l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93208-103">Planning for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93208-104">_**Dernière modification de la rubrique :** 2013-01-19_</span><span class="sxs-lookup"><span data-stu-id="93208-104">_**Topic Last Modified:** 2013-01-19_</span></span>

<span data-ttu-id="93208-p101">Dans la plupart des entreprises, les communications impliquent des services et des utilisateurs situés à l’extérieur de votre réseau interne. Il peut s’agir d’employés travaillant de manière temporaire ou permanente hors site, d’employés travaillant pour un client ou un partenaire, d’utilisateurs de services de messagerie instantanée publics, de clients, de partenaires et d’utilisateurs anonymes potentiels conviés à des réunions et à des présentations. Dans cette documentation, ces personnes sont collectivement appelées *utilisateurs externes*.</span><span class="sxs-lookup"><span data-stu-id="93208-p101">Communications in most organizations involve services and users that are not inside your internal network. These services and users include employees who are temporarily or permanently offsite, employees of customer or partner organizations, people who use public instant messaging (IM) services, and potential customers, partners and anonymous users whom you invite to meetings and presentations. In this documentation, these people are collectively referred to as *external users*.</span></span>

<span data-ttu-id="93208-108">Avec Microsoft Lync Server 2013, les utilisateurs de votre organisation peuvent utiliser la messagerie instantanée et la présence pour communiquer avec les utilisateurs externes, et ils peuvent participer à la conférence audio/vidéo (A/V) et à la conférence Web avec vos employés hors site et d’autres types d’utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="93208-108">With Microsoft Lync Server 2013, users in your organization can use IM and presence to communicate with external users, and they can participate in audio/video (A/V) conferencing and web conferencing with your offsite employees and other types of external users.</span></span> <span data-ttu-id="93208-109">Vous pouvez également prendre en charge l’accès externe à partir de périphériques mobiles et via Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="93208-109">You can also support external access from mobile devices and over Enterprise Voice.</span></span> <span data-ttu-id="93208-110">Les utilisateurs externes qui ne sont pas membres de votre organisation peuvent participer aux réunions Lync Server 2013, autorisant les participants anonymes.</span><span class="sxs-lookup"><span data-stu-id="93208-110">External users who are not members of your organization can participate in Lync Server 2013 meetings, allowing anonymous attendees.</span></span>

<span data-ttu-id="93208-111">Pour prendre en charge les communications entre le pare-feu de votre organisation, vous devez déployer le serveur Edge Lync Server 2013 dans votre réseau de périmètre (également appelé DMZ, zone démilitarisée et sous-réseau filtré).</span><span class="sxs-lookup"><span data-stu-id="93208-111">To support communications across your organization’s firewall, you deploy Lync Server 2013 Edge Server in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="93208-112">Le serveur Edge contrôle la manière dont les utilisateurs situés à l’extérieur du pare-feu peuvent se connecter à votre déploiement interne de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93208-112">The Edge Server controls how users outside the firewall can connect to your internal Lync Server 2013 deployment.</span></span> <span data-ttu-id="93208-113">Il contrôle également les communications avec les utilisateurs externes qui transitent à travers le pare-feu.</span><span class="sxs-lookup"><span data-stu-id="93208-113">It also controls communications with external users that originate within the firewall.</span></span>

<span data-ttu-id="93208-114">Selon vos exigences, vous pouvez déployer un ou plusieurs serveurs Edge dans un ou plusieurs emplacements.</span><span class="sxs-lookup"><span data-stu-id="93208-114">Depending on your requirements, you can deploy one or more Edge Servers in one or more locations.</span></span> <span data-ttu-id="93208-115">Cette section décrit les scénarios d’accès des utilisateurs externes dans Lync Server 2013 et explique comment planifier votre topologie de serveur Edge et de proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="93208-115">This section describes scenarios for external user access in Lync Server 2013, and it explains how to plan your edge and reverse proxy topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="93208-116">Même si vous avez besoin d’un serveur Edge pour prendre en charge la voix entreprise et l’accès des utilisateurs externes, cette section est axée sur la prise en charge de la messagerie instantanée, de la présence, de la conférence A/V, de la Fédération, de la conférence Web et de Lync mobile.</span><span class="sxs-lookup"><span data-stu-id="93208-116">Although you need an Edge Server to support Enterprise Voice and external user access, this section focuses on support for IM, presence, A/V conferencing, federation, web conferencing, and Lync Mobile.</span></span> <span data-ttu-id="93208-117">Pour plus d’informations sur la prise en charge de voix entreprise, voir <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="93208-117">For details about support for Enterprise Voice, see <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="93208-118">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="93208-118">In This Section</span></span>

  - [<span data-ttu-id="93208-119">Modifications apportées dans Lync Server 2013 affectant la planification des serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="93208-119">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [<span data-ttu-id="93208-120">Configuration système requise pour les composants d’accès des utilisateurs externes pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93208-120">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="93208-121">Vue d’ensemble de l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93208-121">Overview of external user access in Lync Server 2013</span></span>](lync-server-2013-overview-of-external-user-access.md)

  - [<span data-ttu-id="93208-122">Présentation de la découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93208-122">Understanding Autodiscover in Lync Server 2013</span></span>](lync-server-2013-understanding-autodiscover.md)

  - [<span data-ttu-id="93208-123">Choix d’une topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93208-123">Choosing a topology in Lync Server 2013</span></span>](lync-server-2013-choosing-a-topology.md)

  - [<span data-ttu-id="93208-124">Collecte de données dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93208-124">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="93208-125">Déterminer les exigences DNS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93208-125">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="93208-126">Déterminer la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93208-126">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="93208-127">Planification des certificats de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93208-127">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)

  - [<span data-ttu-id="93208-128">Scénarios pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93208-128">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

