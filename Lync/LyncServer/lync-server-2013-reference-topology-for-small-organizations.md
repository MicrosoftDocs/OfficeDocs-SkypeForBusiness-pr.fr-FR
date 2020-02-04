---
title: Topologie de référence de Lync Server 2013 pour les petites entreprises
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e0171d9678d5d890cf4ecb81f6de25f9b558b05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a><span data-ttu-id="f69cc-102">Topologie de référence pour Lync Server 2013 dans les petites organisations</span><span class="sxs-lookup"><span data-stu-id="f69cc-102">Reference topology for Lync Server 2013 in small organizations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f69cc-103">_**Dernière modification de la rubrique :** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="f69cc-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="f69cc-104">La topologie de référence pour les petites organisations montre comment vous pouvez déployer une solution robuste et facilement disponible en déployant uniquement trois serveurs exécutant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f69cc-104">The reference topology for small organizations shows how you can deploy a robust, highly available solution by deploying only three servers running Lync Server.</span></span>

<span data-ttu-id="f69cc-105">**Topologie de référence pour les petites organisations**</span><span class="sxs-lookup"><span data-stu-id="f69cc-105">**Reference topology for small organizations**</span></span>

<span data-ttu-id="f69cc-106">![Diagramme de topologie de référence déployant trois serveurs](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Diagramme de topologie de référence déployant trois serveurs")</span><span class="sxs-lookup"><span data-stu-id="f69cc-106">![Reference topology deploying three servers diagram](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Reference topology deploying three servers diagram")</span></span>

  - <span data-ttu-id="f69cc-107">**Paire de serveurs Standard Edition déployés**     cette organisation a des utilisateurs 4 000 sur leur site central.</span><span class="sxs-lookup"><span data-stu-id="f69cc-107">**Pair of Standard Edition Servers Deployed**    This organization has 4,000 users at their central site.</span></span> <span data-ttu-id="f69cc-108">L’organisation a déployé deux serveurs Standard Edition et les a couplés pour permettre une haute disponibilité et une reprise après sinistre.</span><span class="sxs-lookup"><span data-stu-id="f69cc-108">The organization has deployed two Standard Edition servers and paired them together to enable high availability and disaster recovery.</span></span> <span data-ttu-id="f69cc-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span><span class="sxs-lookup"><span data-stu-id="f69cc-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span></span> <span data-ttu-id="f69cc-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span><span class="sxs-lookup"><span data-stu-id="f69cc-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span></span> <span data-ttu-id="f69cc-111">Pour plus d’informations sur les fonctionnalités de haute disponibilité et de récupération d’urgence dans Lync Server 2013, voir [planification d’une haute disponibilité et reprise après sinistre dans Lync server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="f69cc-111">For more information about high availability and disaster recovery features in Lync Server 2013, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="f69cc-112">**Le déploiement de Edge Server est recommandé.**    Même si le déploiement d’un serveur de périphérie n’est pas requis pour la messagerie instantanée interne, la présence et les conférences, nous le recommandons même pour les petits déploiements.</span><span class="sxs-lookup"><span data-stu-id="f69cc-112">**Edge Server deployment is recommended.**   Although deploying an Edge Server is not required for internal IM, presence and conferencing, we recommend it even for small deployments.</span></span> <span data-ttu-id="f69cc-113">Vous pouvez optimiser votre investissement sur votre serveur Lync en déployant un serveur Edge pour fournir des services aux utilisateurs qui se trouvent en dehors des pare-feu de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f69cc-113">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="f69cc-114">Les avantages sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="f69cc-114">The benefits include the following:</span></span>
    
      - <span data-ttu-id="f69cc-115">Les utilisateurs de votre organisation peuvent utiliser la fonctionnalité de serveur Lync, s’ils travaillent à la maison ou sont en déplacement.</span><span class="sxs-lookup"><span data-stu-id="f69cc-115">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="f69cc-116">Les utilisateurs de votre organisation peuvent inviter des utilisateurs externes à participer à des réunions.</span><span class="sxs-lookup"><span data-stu-id="f69cc-116">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="f69cc-117">Si un partenaire, un fournisseur ou une organisation cliente utilise également Lync Server, vous pouvez créer une *relation fédérée* avec cette organisation.</span><span class="sxs-lookup"><span data-stu-id="f69cc-117">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="f69cc-118">Le déploiement de votre serveur Lync reconnaît alors les utilisateurs de cette organisation fédérée pour une meilleure collaboration.</span><span class="sxs-lookup"><span data-stu-id="f69cc-118">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="f69cc-119">Vos utilisateurs peuvent échanger des messages instantanés avec des utilisateurs de services de messagerie instantanée publique, y compris tout ou partie des éléments suivants :\!Windows Live, AOL, Yahoo et Google Talk.</span><span class="sxs-lookup"><span data-stu-id="f69cc-119">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="f69cc-120">Une licence distincte peut être nécessaire pour la connectivité de messagerie instantanée publique avec ces services.</span><span class="sxs-lookup"><span data-stu-id="f69cc-120">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="f69cc-121">À compter du 1er septembre, 2012, le contrat de licence de l’utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») ne sera plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="f69cc-121">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="f69cc-122">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !</span><span class="sxs-lookup"><span data-stu-id="f69cc-122">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="f69cc-123">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="f69cc-123">Messenger until the service shut down date.</span></span> <span data-ttu-id="f69cc-124">Date de fin de vie du 2014 juin pour AOL et Yahoo !</span><span class="sxs-lookup"><span data-stu-id="f69cc-124">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="f69cc-125">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="f69cc-125">has been announced.</span></span> <span data-ttu-id="f69cc-126">Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f69cc-126">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="f69cc-127">La fonction USL (PIC) est une licence d’abonnement par mois qui est requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo !</span><span class="sxs-lookup"><span data-stu-id="f69cc-127">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="f69cc-128">Messenger.</span><span class="sxs-lookup"><span data-stu-id="f69cc-128">Messenger.</span></span> <span data-ttu-id="f69cc-129">La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo !, le contrat sous-jacent pour lequel le son est arrêté.</span><span class="sxs-lookup"><span data-stu-id="f69cc-129">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="f69cc-130">Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="f69cc-130">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="f69cc-131">La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync.</span><span class="sxs-lookup"><span data-stu-id="f69cc-131">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="f69cc-132">Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.</span><span class="sxs-lookup"><span data-stu-id="f69cc-132">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="f69cc-133">**Survie du site de succursale.**    Cette organisation exécute un programme pilote de la fonctionnalité voix entreprise de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f69cc-133">**Branch site survivability.**   This organization is running a pilot program of the Enterprise Voice feature of Lync Server.</span></span> <span data-ttu-id="f69cc-134">Certains utilisateurs utilisent Lync Server comme solution vocale unique.</span><span class="sxs-lookup"><span data-stu-id="f69cc-134">Some users are using Lync Server as their sole voice solution.</span></span> <span data-ttu-id="f69cc-135">Certains de ces utilisateurs de pilotes vocaux sont disponibles sur le site de la succursale.</span><span class="sxs-lookup"><span data-stu-id="f69cc-135">Some of these Voice pilot users are located at the branch site.</span></span> <span data-ttu-id="f69cc-136">Le site de succursale ne possède pas de lien réseau étendu (WAN) fiable vers le site central ; de sorte qu’une unité de branchement survivant y est déployée.</span><span class="sxs-lookup"><span data-stu-id="f69cc-136">The branch site does not have a reliable wide area network (WAN) link to the central site, so a Survivable Branch Appliance is deployed there.</span></span> <span data-ttu-id="f69cc-137">Ainsi, si la liaison de réseau étendu ne fonctionne pas, les utilisateurs sur le site de la succursale peuvent continuer à passer et à recevoir des appels (au sein de l’organisation et des appels RTC), à utiliser leur messagerie vocale et à communiquer par le biais de la messagerie instantanée à deux personnes.</span><span class="sxs-lookup"><span data-stu-id="f69cc-137">With this deployed, if the WAN link goes down, users at the branch site can still make and receive calls (both calls within the organization and PSTN calls), have voice mail functionality, and communicate with two-party instant messaging (IM).</span></span> <span data-ttu-id="f69cc-138">Les utilisateurs peuvent également être authentifiés lorsque la liaison de réseau étendu n’est plus disponible.</span><span class="sxs-lookup"><span data-stu-id="f69cc-138">Users can also be authenticated when the WAN link is unavailable as well.</span></span>

  - <span data-ttu-id="f69cc-139">**Déploiement de la messagerie unifiée Exchange.**</span><span class="sxs-lookup"><span data-stu-id="f69cc-139">**Exchange UM deployment.**</span></span> <span data-ttu-id="f69cc-140">Cette topologie de référence inclut un serveur Exchange Unified Messaging (UM) qui exécute Microsoft Exchange Server et non Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f69cc-140">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="f69cc-141">Pour plus d’informations sur la messagerie unifiée Exchange, voir [planification d’une intégration de messagerie unifiée Exchange dans Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) et [intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="f69cc-141">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="f69cc-142">**Office Web Apps Server.**</span><span class="sxs-lookup"><span data-stu-id="f69cc-142">**Office Web Apps Server.**</span></span> <span data-ttu-id="f69cc-143">Nous recommandons le déploiement d’un serveur Office Web Apps Server ou d’une batterie de serveurs Office Web Apps Server dans toutes les organisations qui utilisent des conférences Web.</span><span class="sxs-lookup"><span data-stu-id="f69cc-143">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="f69cc-144">Office Web Apps Server vous permet de présenter des diapositives PowerPoint lors de conférences Web.</span><span class="sxs-lookup"><span data-stu-id="f69cc-144">Office Web Apps Server makes it possible for PowerPoint slides to be presented in web conferences.</span></span> <span data-ttu-id="f69cc-145">Pour plus d’informations, reportez-vous à la rubrique [configuration de l’intégration avec Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="f69cc-145">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

