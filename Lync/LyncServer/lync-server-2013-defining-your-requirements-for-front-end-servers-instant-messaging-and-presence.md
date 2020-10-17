---
title: 'Lync Server 2013 : définition de la configuration requise pour les serveurs frontaux, la messagerie instantanée et la présence'
description: 'Lync Server 2013 : définition de la configuration requise pour les serveurs frontaux, la messagerie instantanée et la présence.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 923132b32d5aef80191b19a7b85c3f17276e5946
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545370"
---
# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="b2900-103">Définition de la configuration requise pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2900-103">Defining your requirements for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2900-104">_**Dernière modification de la rubrique :** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="b2900-104">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="b2900-105">La principale tâche de planification pour la messagerie instantanée et la présence est de vous assurer que vous disposez de suffisamment de serveurs frontaux pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b2900-105">The main task of planning for instant messaging (IM) and presence is ensuring that you have enough Front End Servers for your users.</span></span>

<div>

## <a name="enabling-communication-with-external-users"></a><span data-ttu-id="b2900-106">Activation des communications avec les utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="b2900-106">Enabling Communication with External Users</span></span>

<span data-ttu-id="b2900-107">Vous pouvez grandement augmenter les avantages de votre investissement dans Lync Server en permettant à vos utilisateurs de communiquer avec des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="b2900-107">You can greatly increase the benefits of your investment in Lync Server by enabling your users to communicate with external users.</span></span> <span data-ttu-id="b2900-108">Les utilisateurs externes peuvent inclure les catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="b2900-108">External users can include:</span></span>

  - <span data-ttu-id="b2900-109">Utilisateurs distants **Remote users**     Les utilisateurs de votre organisation, lorsqu’ils travaillent à l’extérieur de vos pare-feu et qu’ils utilisent leur ordinateur portable ou d’autres appareils Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b2900-109">**Remote users**   Your organization’s own users, when they are working outside your firewalls and are using their laptops or other Lync Server devices.</span></span>

  - <span data-ttu-id="b2900-110">**Utilisateurs fédérés**     Les utilisateurs des entreprises avec lesquelles vous travaillez et qui exécutent également Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b2900-110">**Federated users**   Users from companies you work with who also run Lync Server.</span></span> <span data-ttu-id="b2900-111">Pour autoriser vos utilisateurs à contacter facilement ces utilisateurs, créez des relations fédérées avec ces entreprises.</span><span class="sxs-lookup"><span data-stu-id="b2900-111">To enable your users to easily contact these users, you create federated relationships with these companies.</span></span>

  - <span data-ttu-id="b2900-112">**Utilisateurs publics**     Les utilisateurs de services de messagerie instantanée publics, tels que les services de messagerie instantanée fournis par le réseau Windows Live des services Internet, Yahoo \! et AOL, ainsi que les utilisateurs de fournisseurs et de serveurs qui utilisent le protocole XMPP (extensible Messaging and Presence Protocol), tels que Google Talk.</span><span class="sxs-lookup"><span data-stu-id="b2900-112">**Public users**   Users of public IM services, such as IM services provided by the Windows Live network of Internet services, Yahoo\!, and AOL, and users of providers and servers that use Extensible Messaging and Presence Protocol (XMPP), such as Google Talk.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b2900-113">Veuillez noter qu’une licence distincte peut être requise pour la connectivité de la messagerie instantanée publique avec Windows Live, AOL et Yahoo!</span><span class="sxs-lookup"><span data-stu-id="b2900-113">Note that a separate license might be required for public IM connectivity with Windows Live, AOL, and Yahoo!</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="b2900-114">À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="b2900-114">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="b2900-115">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !.</span><span class="sxs-lookup"><span data-stu-id="b2900-115">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="b2900-116">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="b2900-116">Messenger until the service shut down date.</span></span> <span data-ttu-id="b2900-117">Date de fin du 2014 juin pour AOL et Yahoo !</span><span class="sxs-lookup"><span data-stu-id="b2900-117">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="b2900-118">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="b2900-118">has been announced.</span></span> <span data-ttu-id="b2900-119">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b2900-119">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="b2900-120">La fonction USL PIC est une licence d’abonnement par utilisateur et par mois requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo !</span><span class="sxs-lookup"><span data-stu-id="b2900-120">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="b2900-121">Messenger.</span><span class="sxs-lookup"><span data-stu-id="b2900-121">Messenger.</span></span> <span data-ttu-id="b2900-122">La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent de qui est en panne.</span><span class="sxs-lookup"><span data-stu-id="b2900-122">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="b2900-123">Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="b2900-123">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="b2900-124">La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard.</span><span class="sxs-lookup"><span data-stu-id="b2900-124">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="b2900-125">La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</span><span class="sxs-lookup"><span data-stu-id="b2900-125">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="b2900-126">Pour activer un ou l’ensemble de ces scénarios, vous devez déployer un serveur Edge pour permettre la sécurisation des communications entre votre déploiement Lync Server et les utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="b2900-126">To enable any or all of these scenarios, you need to deploy an Edge Server to help enable secure communications between your Lync Server deployment and external users.</span></span> <span data-ttu-id="b2900-127">Les utilisateurs distants de votre organisation et les utilisateurs d’organisations fédérées seront en mesure de détecter leur présence mutuelle et de communiquer via la messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="b2900-127">Your organization’s remote users and users at federated organizations will be able to see each other’s presence and communicate using IM.</span></span> <span data-ttu-id="b2900-128">Pour plus d’informations sur l’activation de la communication avec des utilisateurs externes, voir [Planning for External User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="b2900-128">For details about enabling communication with external users, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-im-content"></a><span data-ttu-id="b2900-129">Archivage du contenu de la messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="b2900-129">Archiving IM Content</span></span>

<span data-ttu-id="b2900-130">Lync Server offre des fonctionnalités que vous pouvez utiliser si votre organisation doit respecter les réglementations en matière de conformité.</span><span class="sxs-lookup"><span data-stu-id="b2900-130">Lync Server provides features you can use if your organization must follow compliance regulations.</span></span> <span data-ttu-id="b2900-131">Vous pouvez utiliser l’archivage pour archiver le contenu des messages INSTANTANÉs pour tous les utilisateurs de votre organisation ou uniquement pour certains utilisateurs que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="b2900-131">You can use Archiving to archive the content of IM messages for all users in your organization or for only certain users that you specify.</span></span> <span data-ttu-id="b2900-132">Pour plus d’informations, reportez-vous à la rubrique [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="b2900-132">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="b2900-133">Si vous avez également déployé Microsoft Exchange Server 2013, vous pouvez intégrer l’archivage des données Exchange avec l’archivage des données Lync Server et utiliser un seul outil pour effectuer des recherches dans les deux types de données archivées.</span><span class="sxs-lookup"><span data-stu-id="b2900-133">If you also have Microsoft Exchange Server 2013 deployed, you can integrate the archiving of Exchange data with the archiving of Lync Server data, and use a single tool to search both types of archived data.</span></span> <span data-ttu-id="b2900-134">Pour plus d’informations, reportez-vous à la rubrique [configuration de Microsoft Lync server 2013 pour utiliser l’archivage Microsoft Exchange Server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="b2900-134">For more information, see [Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

