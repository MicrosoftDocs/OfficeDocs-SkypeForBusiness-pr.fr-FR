---
title: Topologie de référence Lync Server 2013 pour les petites organisations
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
ms.openlocfilehash: 0b9947fe1657551b901b6b68cc3efbbf811b261b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a><span data-ttu-id="9c88d-102">Topologie de référence pour Lync Server 2013 dans les petites organisations</span><span class="sxs-lookup"><span data-stu-id="9c88d-102">Reference topology for Lync Server 2013 in small organizations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c88d-103">_**Dernière modification de la rubrique :** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="9c88d-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="9c88d-104">La topologie de référence pour les petites organisations vous montre comment déployer une solution robuste hautement disponible en déployant uniquement trois serveurs exécutant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9c88d-104">The reference topology for small organizations shows how you can deploy a robust, highly available solution by deploying only three servers running Lync Server.</span></span>

<span data-ttu-id="9c88d-105">**Topologie de référence pour les petites organisations**</span><span class="sxs-lookup"><span data-stu-id="9c88d-105">**Reference topology for small organizations**</span></span>

<span data-ttu-id="9c88d-106">![Diagramme de la topologie de référence de déploiement de trois serveurs](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Diagramme de la topologie de référence de déploiement de trois serveurs")</span><span class="sxs-lookup"><span data-stu-id="9c88d-106">![Reference topology deploying three servers diagram](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Reference topology deploying three servers diagram")</span></span>

  - <span data-ttu-id="9c88d-107">**Paire de serveurs Standard Edition déployée**     cette organisation a 4 000 utilisateurs sur leur site central.</span><span class="sxs-lookup"><span data-stu-id="9c88d-107">**Pair of Standard Edition Servers Deployed**    This organization has 4,000 users at their central site.</span></span> <span data-ttu-id="9c88d-108">L’organisation a déployé deux serveurs Standard Edition et les a associés pour permettre la haute disponibilité et la récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="9c88d-108">The organization has deployed two Standard Edition servers and paired them together to enable high availability and disaster recovery.</span></span> <span data-ttu-id="9c88d-109">Chaque serveur héberge 2 000 utilisateurs, mais les informations sur tous les utilisateurs sont synchronisées entre les deux serveurs.</span><span class="sxs-lookup"><span data-stu-id="9c88d-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span></span> <span data-ttu-id="9c88d-110">En cas de panne, un administrateur peut faire basculer ces utilisateurs pour qu’ils soient pris en charge par l’autre serveur, avec un minimum de perturbation pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="9c88d-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span></span> <span data-ttu-id="9c88d-111">Pour plus d’informations sur les fonctionnalités de haute disponibilité et de récupération d’urgence dans Lync Server 2013, consultez la rubrique [planification de la haute disponibilité et de la récupération d’urgence dans Lync server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="9c88d-111">For more information about high availability and disaster recovery features in Lync Server 2013, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="9c88d-112">**Le déploiement de serveur Edge est recommandé.**    Bien que le déploiement d’un serveur Edge ne soit pas requis pour la messagerie instantanée interne, la présence et la Conférence, nous vous recommandons de le faire même pour les déploiements de petite taille.</span><span class="sxs-lookup"><span data-stu-id="9c88d-112">**Edge Server deployment is recommended.**   Although deploying an Edge Server is not required for internal IM, presence and conferencing, we recommend it even for small deployments.</span></span> <span data-ttu-id="9c88d-113">Vous pouvez optimiser votre investissement Lync Server en déployant un serveur Edge pour fournir des services aux utilisateurs qui se trouvent actuellement en dehors des pare-feu de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="9c88d-113">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="9c88d-114">Les avantages sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="9c88d-114">The benefits include the following:</span></span>
    
      - <span data-ttu-id="9c88d-115">Les utilisateurs de votre organisation peuvent utiliser les fonctionnalités de Lync Server, s’ils travaillent de chez eux ou s’ils sont en déplacement.</span><span class="sxs-lookup"><span data-stu-id="9c88d-115">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="9c88d-116">Les utilisateurs de votre organisation peuvent inviter des utilisateurs externes à participer à des réunions.</span><span class="sxs-lookup"><span data-stu-id="9c88d-116">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="9c88d-117">Si vous avez un partenaire, un fournisseur ou une organisation cliente qui utilise également Lync Server, vous pouvez former une *relation fédérée* avec cette organisation.</span><span class="sxs-lookup"><span data-stu-id="9c88d-117">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="9c88d-118">Votre déploiement Lync Server reconnaîtrait alors les utilisateurs de cette organisation fédérée, ce qui permettra une meilleure collaboration.</span><span class="sxs-lookup"><span data-stu-id="9c88d-118">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="9c88d-119">Vos utilisateurs peuvent échanger des messages instantanés avec des utilisateurs de services de messagerie instantanée publics, y compris tout ou partie des éléments suivants :\!Windows Live, AOL, Yahoo et Google Talk.</span><span class="sxs-lookup"><span data-stu-id="9c88d-119">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="9c88d-120">Une licence distincte peut être requise pour la connectivité PIC avec ces services.</span><span class="sxs-lookup"><span data-stu-id="9c88d-120">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="9c88d-121">À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="9c88d-121">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="9c88d-122">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !.</span><span class="sxs-lookup"><span data-stu-id="9c88d-122">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="9c88d-123">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="9c88d-123">Messenger until the service shut down date.</span></span> <span data-ttu-id="9c88d-124">Date de fin du 2014 juin pour AOL et Yahoo !</span><span class="sxs-lookup"><span data-stu-id="9c88d-124">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="9c88d-125">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="9c88d-125">has been announced.</span></span> <span data-ttu-id="9c88d-126">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="9c88d-126">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="9c88d-127">La fonction USL PIC est une licence d’abonnement par utilisateur et par mois requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo !</span><span class="sxs-lookup"><span data-stu-id="9c88d-127">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="9c88d-128">Messenger.</span><span class="sxs-lookup"><span data-stu-id="9c88d-128">Messenger.</span></span> <span data-ttu-id="9c88d-129">La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent de qui est en panne.</span><span class="sxs-lookup"><span data-stu-id="9c88d-129">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="9c88d-130">Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="9c88d-130">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="9c88d-131">La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard.</span><span class="sxs-lookup"><span data-stu-id="9c88d-131">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="9c88d-132">La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</span><span class="sxs-lookup"><span data-stu-id="9c88d-132">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="9c88d-133">**Survivabilité du site de succursale.**    Cette organisation exécute un programme pilote de la fonctionnalité voix entreprise de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9c88d-133">**Branch site survivability.**   This organization is running a pilot program of the Enterprise Voice feature of Lync Server.</span></span> <span data-ttu-id="9c88d-134">Certains utilisateurs utilisent Lync Server comme solution vocale unique.</span><span class="sxs-lookup"><span data-stu-id="9c88d-134">Some users are using Lync Server as their sole voice solution.</span></span> <span data-ttu-id="9c88d-135">Certains de ces utilisateurs de la version pilote vocale se trouvent sur le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="9c88d-135">Some of these Voice pilot users are located at the branch site.</span></span> <span data-ttu-id="9c88d-136">Le site de succursale ne dispose pas d’un lien de réseau étendu (WAN) fiable vers le site central, c’est pourquoi un Survivable Branch Appliance est déployé à cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="9c88d-136">The branch site does not have a reliable wide area network (WAN) link to the central site, so a Survivable Branch Appliance is deployed there.</span></span> <span data-ttu-id="9c88d-137">Une fois cette fonctionnalité déployée, si la liaison de réseau étendu (WAN) tombe en panne, les utilisateurs du site de succursale peuvent continuer à passer et recevoir des appels (les deux appels au sein de l’organisation et les appels RTC), bénéficier des fonctionnalités de messagerie vocale et communiquer avec la messagerie instantanée (IM) à deux personnes.</span><span class="sxs-lookup"><span data-stu-id="9c88d-137">With this deployed, if the WAN link goes down, users at the branch site can still make and receive calls (both calls within the organization and PSTN calls), have voice mail functionality, and communicate with two-party instant messaging (IM).</span></span> <span data-ttu-id="9c88d-138">Les utilisateurs peuvent également être authentifiés lorsque la liaison WAN n’est plus disponible.</span><span class="sxs-lookup"><span data-stu-id="9c88d-138">Users can also be authenticated when the WAN link is unavailable as well.</span></span>

  - <span data-ttu-id="9c88d-139">**Déploiement de la messagerie unifiée Exchange**</span><span class="sxs-lookup"><span data-stu-id="9c88d-139">**Exchange UM deployment.**</span></span> <span data-ttu-id="9c88d-140">Cette topologie de référence inclut un serveur de messagerie unifiée Exchange, qui exécute Microsoft Exchange Server, et non Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9c88d-140">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="9c88d-141">Pour plus d’informations sur la messagerie unifiée Exchange, consultez la rubrique [planification de l’intégration de la messagerie unifiée Exchange dans Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) et l' [intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="9c88d-141">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="9c88d-142">**Office Web Apps Server.**</span><span class="sxs-lookup"><span data-stu-id="9c88d-142">**Office Web Apps Server.**</span></span> <span data-ttu-id="9c88d-143">Nous vous recommandons de déployer une batterie de serveurs Office Web Apps Server ou Office Web Apps Server dans toutes les organisations qui utilisent la conférence Web.</span><span class="sxs-lookup"><span data-stu-id="9c88d-143">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="9c88d-144">Office Web Apps Server permet de présenter des diapositives PowerPoint dans des conférences Web.</span><span class="sxs-lookup"><span data-stu-id="9c88d-144">Office Web Apps Server makes it possible for PowerPoint slides to be presented in web conferences.</span></span> <span data-ttu-id="9c88d-145">Pour plus d’informations, reportez-vous à la rubrique [configuration de l’intégration à Office Web Apps Server et Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="9c88d-145">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

