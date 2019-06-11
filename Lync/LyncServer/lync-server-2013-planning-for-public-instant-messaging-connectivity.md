---
title: 'Lync Server 2013: planification de la connectivité de messagerie instantanée publique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4432484fbd6056d51a38090a18dbe106851d7c0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="aeaa5-102">Planification de la connectivité de messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeaa5-102">Planning for public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aeaa5-103">_**Dernière modification de la rubrique:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="aeaa5-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="aeaa5-104">La connectivité de messagerie instantanée publique est une classe de Fédération et est configurée pour permettre à vos utilisateurs de Lync Server 2013 internes et externes d’ajouter des contacts à partir de l’un des éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="aeaa5-104">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="aeaa5-105">Contacts Messenger</span><span class="sxs-lookup"><span data-stu-id="aeaa5-105">Messenger contacts</span></span>

  - <span data-ttu-id="aeaa5-106">Yahoo!\!</span><span class="sxs-lookup"><span data-stu-id="aeaa5-106">Yahoo\!</span></span> <span data-ttu-id="aeaa5-107">contacts</span><span class="sxs-lookup"><span data-stu-id="aeaa5-107">contacts</span></span>

  - <span data-ttu-id="aeaa5-108">Contacts AOL (America Online)</span><span class="sxs-lookup"><span data-stu-id="aeaa5-108">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="aeaa5-109">À compter du 1er septembre 2012, la licence de l’abonnement à l’utilisateur de la connectivité PIC (Public IM Connectivity) de Microsoft Lync n’est plus disponible pour l’achat de contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="aeaa5-109">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="aeaa5-110">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo!</span><span class="sxs-lookup"><span data-stu-id="aeaa5-110">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="aeaa5-111">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="aeaa5-111">Messenger until the service shutdown date.</span></span> <span data-ttu-id="aeaa5-112">Date de fin de vie du 2014 juin pour AOL et Yahoo!</span><span class="sxs-lookup"><span data-stu-id="aeaa5-112">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="aeaa5-113">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="aeaa5-113">has been announced.</span></span> <span data-ttu-id="aeaa5-114">Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="aeaa5-114">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="aeaa5-115">La fonction USL (PIC) est une licence d’abonnement par utilisateur et par mois requise pour la Fédération de Lync Server ou d’Office Communications Server avec Yahoo!</span><span class="sxs-lookup"><span data-stu-id="aeaa5-115">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="aeaa5-116">Messenger.</span><span class="sxs-lookup"><span data-stu-id="aeaa5-116">Messenger.</span></span> <span data-ttu-id="aeaa5-117">La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo!, qui n’est pas renouvelé.</span><span class="sxs-lookup"><span data-stu-id="aeaa5-117">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="aeaa5-118">Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="aeaa5-118">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="aeaa5-119">La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync.</span><span class="sxs-lookup"><span data-stu-id="aeaa5-119">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="aeaa5-120">Skype Federation sera ajouté à cette liste, ce qui permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes par messagerie instantanée et vocale.</span><span class="sxs-lookup"><span data-stu-id="aeaa5-120">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="aeaa5-121">Cette classe de Fédération exige les considérations en matière de planification suivantes:</span><span class="sxs-lookup"><span data-stu-id="aeaa5-121">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="aeaa5-122">Les utilisateurs de Windows Live Messenger peuvent utiliser la communication audio et vidéo d’égal à égal avec les utilisateurs de Lync Server 2013, en plus de la messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="aeaa5-122">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="aeaa5-123">Vos serveurs Edge doivent répondre à des exigences de port et de protocole spécifiques.</span><span class="sxs-lookup"><span data-stu-id="aeaa5-123">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="aeaa5-124">Pour plus d’informations, reportez-vous à [la rubrique déterminer la configuration requise 2013 pour le pare-feu A](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="aeaa5-124">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="aeaa5-125">Le service de messagerie instantanée Yahoo n’est soumis à aucune configuration unique, autre que celles généralement utilisées dans le cadre de la planification et du déploiement du serveur de périphérie standard qui fournit la Fédération.</span><span class="sxs-lookup"><span data-stu-id="aeaa5-125">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="aeaa5-126">America Online nécessite que votre certificat de serveur Edge attribué au service Edge d’accès possède une utilisation améliorée de la clé par le client.</span><span class="sxs-lookup"><span data-stu-id="aeaa5-126">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="aeaa5-127">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="aeaa5-127">In This Section</span></span>

  - [<span data-ttu-id="aeaa5-128">Résumé de certification-connectivité de messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeaa5-128">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [<span data-ttu-id="aeaa5-129">Résumé de port-connectivité de messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeaa5-129">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - <span data-ttu-id="aeaa5-130">[DNS Summary-connectivité de messagerie instantanée publique dans Lync Server 2013](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="aeaa5-130">[DNS summary - Public instant messaging connectivity in Lync Server 2013](https://technet.microsoft.com/en-us/library/jj618375\(v=ocs.15\))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

