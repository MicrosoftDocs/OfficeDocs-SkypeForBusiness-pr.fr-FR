---
title: 'Lync Server 2013 : liste de vérification du déploiement de la jonction SIP'
description: 'Lync Server 2013 : liste de vérification du déploiement de la jonction SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbab9647a7146b2478317ab6c020969506f9c0ef
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559040"
---
# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="aae04-103">Liste de vérification du déploiement de la jonction SIP pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aae04-103">SIP trunk deployment checklist for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aae04-104">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="aae04-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="aae04-105">Avant de pouvoir déployer une jonction SIP, vous et votre fournisseur de services devez échanger des informations de connexion de base concernant vos points de terminaison de jonction SIP respectifs.</span><span class="sxs-lookup"><span data-stu-id="aae04-105">Before you can deploy a SIP trunk, you and your service provider must exchange some basic connection information about your respective SIP trunk endpoints.</span></span>

<span data-ttu-id="aae04-106">Obtenez les informations suivantes pour chaque passerelle téléphonie Internet à laquelle vous allez vous connecter :</span><span class="sxs-lookup"><span data-stu-id="aae04-106">Get the following information for each ITSP gateway that you will connect to:</span></span>

  - <span data-ttu-id="aae04-107">Adresse IP</span><span class="sxs-lookup"><span data-stu-id="aae04-107">IP address</span></span>

  - <span data-ttu-id="aae04-108">nom de domaine complet (FQDN)</span><span class="sxs-lookup"><span data-stu-id="aae04-108">Fully qualified domain name (FQDN)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aae04-109">Le fournisseur de services peut vous demander de vous connecter à plusieurs passerelles téléphonie Internet.</span><span class="sxs-lookup"><span data-stu-id="aae04-109">The service provider may ask you to connect to more than one ITSP gateway.</span></span> <span data-ttu-id="aae04-110">Dans ce cas, vous devez configurer une connexion entre chaque passerelle téléphonie Internet et chaque serveur de médiation de votre pool.</span><span class="sxs-lookup"><span data-stu-id="aae04-110">In that case, you must configure a connection between each ITSP gateway and each Mediation Server in your pool.</span></span>



</div>

<span data-ttu-id="aae04-111">Les informations que vous accordez à votre fournisseur de services dépendent de votre type de connexion de jonction SIP :</span><span class="sxs-lookup"><span data-stu-id="aae04-111">The information you give to your service provider depends on your SIP trunk connection type:</span></span>

  - <span data-ttu-id="aae04-112">Pour les connexions de réseau privé (MPLS) ou VPN, donnez à l’téléphonie Internet l’adresse IP routable publique du routeur dans votre réseau de périmètre (également appelé DMZ, zone démilitarisée et sous-réseau filtré).</span><span class="sxs-lookup"><span data-stu-id="aae04-112">For Multiprotocol Label Switching (MPLS) or private network connections, give the ITSP the publicly routable IP Address of the router in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="aae04-113">Vérifiez que la passerelle ou le contrôleur de frontière de session (SBC) de l’téléphonie Internet peut atteindre cette adresse.</span><span class="sxs-lookup"><span data-stu-id="aae04-113">Verify that the gateway or Session Border Controller (SBC) at the ITSP can reach this address.</span></span> <span data-ttu-id="aae04-114">Donnez également au téléphonie Internet le nom de domaine complet de votre serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="aae04-114">Also give the ITSP the FQDN of your Mediation Server.</span></span>

  - <span data-ttu-id="aae04-115">Pour les connexions de réseau privé virtuel (VPN), attribuez à l’téléphonie Internet l’adresse IP de votre serveur VPN.</span><span class="sxs-lookup"><span data-stu-id="aae04-115">For virtual private network (VPN) connections, give the ITSP the IP address of your VPN server.</span></span>

<div>

## <a name="certificate-considerations"></a><span data-ttu-id="aae04-116">Considérations relatives aux certificats</span><span class="sxs-lookup"><span data-stu-id="aae04-116">Certificate Considerations</span></span>

<span data-ttu-id="aae04-117">Pour déterminer si vous avez besoin d’un certificat pour la jonction SIP, consultez votre téléphonie Internet à propos de la prise en charge du protocole :</span><span class="sxs-lookup"><span data-stu-id="aae04-117">To determine whether you need a certificate for SIP trunking, check with your ITSP about protocol support:</span></span>

1.  <span data-ttu-id="aae04-118">Si votre téléphonie Internet prend en charge le protocole TCP (Transmission Control Protocol) uniquement, vous n’avez pas besoin de certificat.</span><span class="sxs-lookup"><span data-stu-id="aae04-118">If your ITSP supports Transmission Control Protocol (TCP) only, you do not need a certificate.</span></span>

2.  <span data-ttu-id="aae04-119">Si votre téléphonie Internet prend en charge le protocole TLS (Transport Layer Security), le téléphonie Internet doit vous fournir un certificat.</span><span class="sxs-lookup"><span data-stu-id="aae04-119">If your ITSP supports Transport Layer Security (TLS), the ITSP must provide you with a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aae04-120">Le protocole SIP fonctionne en association avec le protocole RTP (Real-Time Transport Protocol) ou SRTP (Secure Real-Time Transport Protocol), les protocoles qui gèrent les données vocales réelles dans les appels VoIP (Voice over Internet Protocol).</span><span class="sxs-lookup"><span data-stu-id="aae04-120">SIP works in conjunction with real-time transport protocol (RTP) or secure real-time transport protocol (SRTP), the protocols that manage the actual voice data in Voice over Internet Protocol (VoIP) calls.</span></span>



</div>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="aae04-121">Processus de déploiement</span><span class="sxs-lookup"><span data-stu-id="aae04-121">Deployment Process</span></span>

<span data-ttu-id="aae04-122">Pour implémenter le côté Lync Server de la connexion de jonction SIP, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="aae04-122">To implement the Lync Server side of the SIP trunk connection, follow these steps:</span></span>

1.  <span data-ttu-id="aae04-123">À l’aide du générateur de topologie Lync Server, créez et configurez la topologie de domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="aae04-123">Using the Lync Server Topology Builder, create and configure the SIP domain topology.</span></span> <span data-ttu-id="aae04-124">Pour plus d’informations, reportez-vous à la rubrique [define and Configure a Topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="aae04-124">For details, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="aae04-125">À l’aide du panneau de configuration Lync Server, configurez le routage des communications vocales pour le nouveau domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="aae04-125">Using the Lync Server Control Panel, configure voice routing for the new SIP domain.</span></span> <span data-ttu-id="aae04-126">Pour plus d’informations, reportez-vous à la rubrique [Configuration des jonctions dans Lync Server 2013](lync-server-2013-configuring-trunks.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="aae04-126">For details, see [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="aae04-127">Testez la connectivité à l’aide de la cmdlet **test-CsPstnOutboundCall** .</span><span class="sxs-lookup"><span data-stu-id="aae04-127">Test connectivity by using the **Test-CsPstnOutboundCall** cmdlet.</span></span> <span data-ttu-id="aae04-128">Pour plus d’informations, reportez-vous à la documentation de Lync Server Management Shell ou à l’aide de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="aae04-128">For details, see the Lync Server Management Shell documentation or Help for Lync Server Management Shell.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

