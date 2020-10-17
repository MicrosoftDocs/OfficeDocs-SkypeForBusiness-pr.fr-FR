---
title: 'Lync Server 2013 : planification de la connectivité de messagerie instantanée publique'
description: 'Lync Server 2013 : planification de la connectivité de messagerie instantanée publique.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for public instant messaging connectivity
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205349(v=OCS.15)
ms:contentKeyID: 48185698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a020a291a39d78aea9271926c99b508a8cd9827
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549290"
---
# <a name="planning-for-public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="8ab63-103">Planification de la connectivité de messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ab63-103">Planning for public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ab63-104">_**Dernière modification de la rubrique :** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="8ab63-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="8ab63-105">La connectivité de messagerie instantanée publique est une classe de Fédération et est configurée pour permettre à vos utilisateurs de Lync Server 2013 internes et externes d’ajouter des contacts à partir de l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="8ab63-105">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="8ab63-106">Contacts Messenger</span><span class="sxs-lookup"><span data-stu-id="8ab63-106">Messenger contacts</span></span>

  - <span data-ttu-id="8ab63-107">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="8ab63-107">Yahoo\!</span></span> <span data-ttu-id="8ab63-108">contacts</span><span class="sxs-lookup"><span data-stu-id="8ab63-108">contacts</span></span>

  - <span data-ttu-id="8ab63-109">Contacts AOL (America Online)</span><span class="sxs-lookup"><span data-stu-id="8ab63-109">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="8ab63-110">À partir du 2012 1er septembre, la licence d’abonnement aux utilisateurs de la connectivité PIC de Microsoft Lync public (PIC) n’est plus disponible pour l’achat de contrats de nouvelle ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="8ab63-110">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="8ab63-111">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !.</span><span class="sxs-lookup"><span data-stu-id="8ab63-111">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="8ab63-112">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="8ab63-112">Messenger until the service shutdown date.</span></span> <span data-ttu-id="8ab63-113">Date de fin du 2014 juin pour AOL et Yahoo !</span><span class="sxs-lookup"><span data-stu-id="8ab63-113">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="8ab63-114">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="8ab63-114">has been announced.</span></span> <span data-ttu-id="8ab63-115">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8ab63-115">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="8ab63-116">La fonction USL PIC est une licence d’abonnement mensuel, mensuelle, nécessaire pour que Lync Server ou Office Communications Server se fédérer avec Yahoo !.</span><span class="sxs-lookup"><span data-stu-id="8ab63-116">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="8ab63-117">Messenger.</span><span class="sxs-lookup"><span data-stu-id="8ab63-117">Messenger.</span></span> <span data-ttu-id="8ab63-118">La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent qui n’est pas renouvelé.</span><span class="sxs-lookup"><span data-stu-id="8ab63-118">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="8ab63-119">Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="8ab63-119">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="8ab63-120">La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard.</span><span class="sxs-lookup"><span data-stu-id="8ab63-120">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="8ab63-121">La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes via la messagerie instantanée et la voix.</span><span class="sxs-lookup"><span data-stu-id="8ab63-121">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="8ab63-122">Cette classe de fédération nécessite les considérations de planification suivantes :</span><span class="sxs-lookup"><span data-stu-id="8ab63-122">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="8ab63-123">Les utilisateurs de Windows Live Messenger peuvent utiliser la communication audio/vidéo d’égal à égal avec les utilisateurs de Lync Server 2013, en plus de la messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="8ab63-123">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="8ab63-124">Vos serveurs Edge doivent répondre à des exigences spécifiques en matière de port et de protocole.</span><span class="sxs-lookup"><span data-stu-id="8ab63-124">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="8ab63-125">Pour plus d’informations, reportez-vous à [la rubrique determine External A/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ab63-125">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="8ab63-126">La messagerie instantanée Yahoo n’a pas de configuration spécifique, à l’exception de celles généralement utilisées dans la planification et le déploiement du serveur Edge standard qui fournit la Fédération.</span><span class="sxs-lookup"><span data-stu-id="8ab63-126">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="8ab63-127">Pour America Online, le certificat de serveur Edge attribué au service Edge d’accès a une utilisation améliorée de la clé (EKU) par le client.</span><span class="sxs-lookup"><span data-stu-id="8ab63-127">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8ab63-128">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="8ab63-128">In This Section</span></span>

  - [<span data-ttu-id="8ab63-129">Résumé des certificats-connectivité de messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ab63-129">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [<span data-ttu-id="8ab63-130">Résumé des ports-connectivité de messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ab63-130">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - <span data-ttu-id="8ab63-131">[Résumé des enregistrements DNS-connectivité de messagerie instantanée publique dans Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8ab63-131">[DNS summary - Public instant messaging connectivity in Lync Server 2013](https://technet.microsoft.com/library/jj618375\(v=ocs.15\))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

