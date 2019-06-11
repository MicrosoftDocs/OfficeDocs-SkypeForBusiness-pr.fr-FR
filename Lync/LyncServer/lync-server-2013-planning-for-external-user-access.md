---
title: 'Lync Server 2013 : Planification de l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76d4853e7e748128214fc93b721a59e979af03e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="4d9a6-102">Planification de l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d9a6-102">Planning for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d9a6-103">_**Dernière modification de la rubrique:** 2013-01-19_</span><span class="sxs-lookup"><span data-stu-id="4d9a6-103">_**Topic Last Modified:** 2013-01-19_</span></span>

<span data-ttu-id="4d9a6-104">Dans la plupart des organisations, les communications concernent les services et les utilisateurs qui ne se trouvent pas à l’intérieur de votre réseau interne.</span><span class="sxs-lookup"><span data-stu-id="4d9a6-104">Communications in most organizations involve services and users that are not inside your internal network.</span></span> <span data-ttu-id="4d9a6-105">Ces services et utilisateurs incluent des employés qui sont temporairement ou définitivement hors site, des employés d’organisations de clients ou de partenaires, des personnes qui utilisent des services de messagerie instantanée publique, et des clients potentiels, des partenaires et des utilisateurs anonymes que vous invitez à des réunions et des présentations.</span><span class="sxs-lookup"><span data-stu-id="4d9a6-105">These services and users include employees who are temporarily or permanently offsite, employees of customer or partner organizations, people who use public instant messaging (IM) services, and potential customers, partners and anonymous users whom you invite to meetings and presentations.</span></span> <span data-ttu-id="4d9a6-106">Dans cette documentation, ces personnes sont collectivement appelées *utilisateurs externes*.</span><span class="sxs-lookup"><span data-stu-id="4d9a6-106">In this documentation, these people are collectively referred to as *external users*.</span></span>

<span data-ttu-id="4d9a6-107">Avec Microsoft Lync Server 2013, les utilisateurs de votre organisation peuvent utiliser la messagerie instantanée et la présence pour communiquer avec des utilisateurs externes, et participer à des conférences audio/vidéo (A/V) et des conférences Web avec vos employés hors site et d’autres types d’utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="4d9a6-107">With Microsoft Lync Server 2013, users in your organization can use IM and presence to communicate with external users, and they can participate in audio/video (A/V) conferencing and web conferencing with your offsite employees and other types of external users.</span></span> <span data-ttu-id="4d9a6-108">Vous pouvez également prendre en charge l’accès externe à partir d’appareils mobiles et de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="4d9a6-108">You can also support external access from mobile devices and over Enterprise Voice.</span></span> <span data-ttu-id="4d9a6-109">Les utilisateurs externes qui ne sont pas membres de votre organisation peuvent participer à des réunions Lync Server 2013, ce qui permet aux participants anonymes.</span><span class="sxs-lookup"><span data-stu-id="4d9a6-109">External users who are not members of your organization can participate in Lync Server 2013 meetings, allowing anonymous attendees.</span></span>

<span data-ttu-id="4d9a6-110">Pour prendre en charge les communications entre le pare-feu de votre organisation, vous déployez le serveur Edge Lync Server 2013 dans votre réseau de périmètre (également connu sous le nom de DMZ, zone démilitarisée et sous-réseau filtré).</span><span class="sxs-lookup"><span data-stu-id="4d9a6-110">To support communications across your organization’s firewall, you deploy Lync Server 2013 Edge Server in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="4d9a6-111">Le serveur de périphérie contrôle la façon dont les utilisateurs extérieurs au pare-feu peuvent se connecter à votre déploiement interne Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4d9a6-111">The Edge Server controls how users outside the firewall can connect to your internal Lync Server 2013 deployment.</span></span> <span data-ttu-id="4d9a6-112">Il contrôle également les communications avec les utilisateurs externes qui proviennent du pare-feu.</span><span class="sxs-lookup"><span data-stu-id="4d9a6-112">It also controls communications with external users that originate within the firewall.</span></span>

<span data-ttu-id="4d9a6-113">En fonction de vos besoins, vous pouvez déployer un ou plusieurs serveurs Edge dans un ou plusieurs emplacements.</span><span class="sxs-lookup"><span data-stu-id="4d9a6-113">Depending on your requirements, you can deploy one or more Edge Servers in one or more locations.</span></span> <span data-ttu-id="4d9a6-114">Cette section décrit les scénarios d’accès des utilisateurs externes dans Lync Server 2013 et explique comment planifier votre topologie de proxy inversée.</span><span class="sxs-lookup"><span data-stu-id="4d9a6-114">This section describes scenarios for external user access in Lync Server 2013, and it explains how to plan your edge and reverse proxy topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4d9a6-115">Même si vous avez besoin d’un serveur Edge pour prendre en charge l’accès voix entreprise et l’accès utilisateur externe, cette section porte sur la prise en charge de la messagerie instantanée, de la présence, des conférences A/V, de la Fédération, de la conférence Web et de Lync mobile.</span><span class="sxs-lookup"><span data-stu-id="4d9a6-115">Although you need an Edge Server to support Enterprise Voice and external user access, this section focuses on support for IM, presence, A/V conferencing, federation, web conferencing, and Lync Mobile.</span></span> <span data-ttu-id="4d9a6-116">Pour plus d’informations sur la prise en charge de voix entreprise, reportez-vous à la rubrique <A href="lync-server-2013-planning-for-enterprise-voice.md">planification d’entreprise voix dans Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="4d9a6-116">For details about support for Enterprise Voice, see <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4d9a6-117">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="4d9a6-117">In This Section</span></span>

  - [<span data-ttu-id="4d9a6-118">Modifications apportées dans Lync Server 2013 affectant la planification de serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="4d9a6-118">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [<span data-ttu-id="4d9a6-119">Configuration système requise pour les composants d’accès des utilisateurs externes pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d9a6-119">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="4d9a6-120">Vue d’ensemble de l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d9a6-120">Overview of external user access in Lync Server 2013</span></span>](lync-server-2013-overview-of-external-user-access.md)

  - [<span data-ttu-id="4d9a6-121">Comprendre la découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d9a6-121">Understanding Autodiscover in Lync Server 2013</span></span>](lync-server-2013-understanding-autodiscover.md)

  - [<span data-ttu-id="4d9a6-122">Sélection d’une topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d9a6-122">Choosing a topology in Lync Server 2013</span></span>](lync-server-2013-choosing-a-topology.md)

  - [<span data-ttu-id="4d9a6-123">Collecte des données dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d9a6-123">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="4d9a6-124">Détermination de la configuration requise pour DNS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d9a6-124">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="4d9a6-125">Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d9a6-125">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="4d9a6-126">Planification des certificats de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d9a6-126">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)

  - [<span data-ttu-id="4d9a6-127">Scénarios d’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d9a6-127">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

