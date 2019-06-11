---
title: 'Lync Server 2013 : Nouvelles fonctionnalités liées à l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d365c4e32c5eaebbd0368cd85b41be7886a59df
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="2e9a0-102">Nouvelles fonctionnalités liées à l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e9a0-102">New features for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e9a0-103">_**Dernière modification de la rubrique:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="2e9a0-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="2e9a0-104">Lync Server 2013 introduit de nouvelles fonctionnalités qui étendent les fonctionnalités et méthodes de communication pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="2e9a0-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="2e9a0-105">Par ailleurs, Lync Server 2013 introduit des modifications apportées aux services existants pour améliorer l’intégration et l’extension des services disponibles pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="2e9a0-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="2e9a0-106">Vous trouverez ci-dessous un résumé des modifications qui peuvent affecter votre planification et le déploiement de Lync Server 2013 Edge Server services.</span><span class="sxs-lookup"><span data-stu-id="2e9a0-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

  - <span data-ttu-id="2e9a0-107">**Prise en charge de l’adressage**   IPv6 Lync Server 2013 prend en charge l’adressage IPv6 pour tous les services Edge Server.</span><span class="sxs-lookup"><span data-stu-id="2e9a0-107">**Support for IPv6 addressing**   Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="2e9a0-108">Si vous avez fourni des adresses IPv6 pour les interfaces via une configuration dans Windows Server, vous pouvez utiliser des adresses IPv6 dans votre configuration de serveur Edge via la configuration d’adresse IP dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="2e9a0-108">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2e9a0-109">L’utilisation des adresses IPv6 dans Lync Server 2013 dépend de la prise en charge du protocole IPv6 dans les routeurs et pare-feu déployés par votre organisation, ainsi que de la prise en charge par le biais de votre fournisseur d’accès à Internet.</span><span class="sxs-lookup"><span data-stu-id="2e9a0-109">Use of IPv6 addresses in Lync Server 2013 depends on support of IPv6 in routers and firewalls that your organization deploys, as well as support through your Internet service provider.</span></span>

    
    </div>

  - <span data-ttu-id="2e9a0-110">**Le protocole XMPP (extensible Messaging and Presence Protocol)**   Lync Server 2013 introduit un proxy XMPP entièrement intégré (déployé sur les serveurs Edge) et une passerelle XMPP déployée sur vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="2e9a0-110">**Extensible Messaging and Presence Protocol (XMPP)**   Lync Server 2013 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="2e9a0-111">Vous pouvez déployer la Fédération XMPP en tant que composant facultatif.</span><span class="sxs-lookup"><span data-stu-id="2e9a0-111">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="2e9a0-112">L’ajout et la configuration du proxy XMPP et de la passerelle XMPP permettent aux utilisateurs de Microsoft Lync 2013 d’ajouter des contacts des partenaires de XMPP pour la messagerie instantanée et la présence.</span><span class="sxs-lookup"><span data-stu-id="2e9a0-112">Adding and configuring the XMPP proxy and XMPP gateway will allow your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2e9a0-113">Pour l’instant, les services XMPP dans Lync Server 2013 ne fournissent que la messagerie instantanée et la présence entre les clients Lync et les contacts de type XMPP.</span><span class="sxs-lookup"><span data-stu-id="2e9a0-113">Currently, the XMPP services in Lync Server 2013 only provide instant messaging and presence between Lync clients and XMPP-based contacts.</span></span>

    
    </div>

  - <span data-ttu-id="2e9a0-114">**Services de mobilité pour les clients**   mobiles introduits dans une mise à jour de clients pour Lync Server 2010, les services de mobilité dans Lync Server 2013 permettent aux clients mobiles Microsoft Lync sur les téléphones mobiles et les tablettes utilisant Apple iOS, Android, Windows pris en charge. Des appareils mobiles téléphone ou Nokia pour effectuer des opérations telles que l’envoi et la réception de messages instantanés, l’affichage de contacts et l’affichage de la présence.</span><span class="sxs-lookup"><span data-stu-id="2e9a0-114">**Mobility services for Mobile clients**   Introduced in a customer update for Lync Server 2010, Mobility services in Lync Server 2013 allow Microsoft Lync Mobile clients on mobile phones and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="2e9a0-115">De plus, les appareils mobiles prennent en charge certaines fonctionnalités vocales d’entreprise, par exemple, cliquer pour participer à une conférence, appeler par le biais de votre bureau, joindre un numéro de téléphone unique et envoyer une notification d’appel manqué.</span><span class="sxs-lookup"><span data-stu-id="2e9a0-115">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2e9a0-116">Les services de mobilité utilisent le proxy inverse et les services publiés déployés sur vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="2e9a0-116">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="2e9a0-117">Aucune modification n’est requise sur les serveurs de périphérie.</span><span class="sxs-lookup"><span data-stu-id="2e9a0-117">No changes are required to Edge Servers.</span></span>

    
    </div>

  - <span data-ttu-id="2e9a0-118">**Les directeurs sont un rôle**   facultatif que le rôle du serveur directeur dans la topologie Lync Server 2013 n’a pas changé.</span><span class="sxs-lookup"><span data-stu-id="2e9a0-118">**Directors are an optional role**   The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="2e9a0-119">Il héberge toujours les services Web, pré-authentifie les demandes des utilisateurs entrantes, et redirige les utilisateurs externes vers leur liste de ressources personnelles.</span><span class="sxs-lookup"><span data-stu-id="2e9a0-119">It still hosts web services, pre-authenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="2e9a0-120">Le fait de changer le directeur d’un rôle recommandé en un rôle facultatif n’a pas pour effet de réduire la valeur du directeur, mais souligne le nombre de serveurs et autres exigences matérielles (par exemple, les équilibreurs de charge matérielle pour le directeur), sans fonctionnalités et fonctionnalités inprometes.</span><span class="sxs-lookup"><span data-stu-id="2e9a0-120">Changing the Director from a recommended role to an optional role does not diminish the value of the Director, but emphasizes reducing server count and other hardware requirements (for example, hardware load balancers for the Director) requirements without compromising features and functionality.</span></span> <span data-ttu-id="2e9a0-121">Étant donné que les serveurs front-end peuvent faire la même chose que le directeur sans avoir d’impact sur les services fournis, vous pouvez éventuellement déployer des directeurs si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="2e9a0-121">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can optionally deploy Directors if you choose to.</span></span> <span data-ttu-id="2e9a0-122">Vous pouvez exclure en toute sécurité le directeur en ayant confiance aux serveurs frontaux pour fournir les mêmes services à leur emplacement.</span><span class="sxs-lookup"><span data-stu-id="2e9a0-122">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in their place.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="2e9a0-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2e9a0-123">See Also</span></span>


[<span data-ttu-id="2e9a0-124">Planification et configuration du protocole IPv6 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e9a0-124">Planning for and configuring IPv6 in Lync Server 2013</span></span>](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[<span data-ttu-id="2e9a0-125">Planification de l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e9a0-125">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="2e9a0-126">Planification de la Fédération des protocoles de messagerie et de présence extensibles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e9a0-126">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

