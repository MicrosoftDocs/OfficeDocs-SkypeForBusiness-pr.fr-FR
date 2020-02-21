---
title: 'Lync Server 2013 : nouvelles fonctionnalités pour l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 526daf4359cec022b71476dc4abaa67c52e8409a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="67153-102">Nouvelles fonctionnalités pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67153-102">New features for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67153-103">_**Dernière modification de la rubrique :** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="67153-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="67153-104">Lync Server 2013 introduit de nouvelles fonctionnalités qui étendent les fonctionnalités et les méthodes de communication pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="67153-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="67153-105">De plus, Lync Server 2013 introduit les modifications apportées aux services existants afin d’améliorer l’intégration et l’extension des services disponibles pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="67153-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="67153-106">Vous trouverez ci-dessous un résumé des modifications susceptibles d’avoir un impact sur la planification et le déploiement des services de serveur Edge Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="67153-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

  - <span data-ttu-id="67153-107">**Prise en charge de l’adressage**   IPv6 Lync Server 2013 prend en charge l’adressage IPv6 pour tous les services de serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="67153-107">**Support for IPv6 addressing**   Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="67153-108">Si vous avez fourni des adresses IPv6 pour les interfaces par le biais de la configuration dans Windows Server, vous pouvez utiliser des adresses IPv6 dans votre configuration de serveur Edge par le biais de la configuration d’adresse IP dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="67153-108">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="67153-109">L’utilisation d’adresses IPv6 dans Lync Server 2013 dépend de la prise en charge D’ipv6 dans les routeurs et les pare-feu déployés par votre organisation, ainsi que de la prise en charge par le biais de votre fournisseur de services Internet.</span><span class="sxs-lookup"><span data-stu-id="67153-109">Use of IPv6 addresses in Lync Server 2013 depends on support of IPv6 in routers and firewalls that your organization deploys, as well as support through your Internet service provider.</span></span>

    
    </div>

  - <span data-ttu-id="67153-110">**Le protocole XMPP (extensible Messaging and Presence Protocol)**   Lync Server 2013 introduit un proxy XMPP entièrement intégré (déployé sur les serveurs Edge) et une passerelle XMPP déployée sur vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="67153-110">**Extensible Messaging and Presence Protocol (XMPP)**   Lync Server 2013 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="67153-111">Vous pouvez déployer Fédération XMPP comme un composant facultatif.</span><span class="sxs-lookup"><span data-stu-id="67153-111">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="67153-112">L’ajout et la configuration du proxy XMPP et de la passerelle XMPP permettent à vos utilisateurs Microsoft Lync 2013 d’ajouter des contacts à partir de partenaires XMPP pour la messagerie instantanée et la présence.</span><span class="sxs-lookup"><span data-stu-id="67153-112">Adding and configuring the XMPP proxy and XMPP gateway will allow your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="67153-113">Actuellement, les services XMPP de Lync Server 2013 fournissent uniquement la messagerie instantanée et la présence entre les clients Lync et les contacts XMPP.</span><span class="sxs-lookup"><span data-stu-id="67153-113">Currently, the XMPP services in Lync Server 2013 only provide instant messaging and presence between Lync clients and XMPP-based contacts.</span></span>

    
    </div>

  - <span data-ttu-id="67153-114">**Les services de mobilité pour les clients**   mobiles introduits dans une mise à jour de client pour Lync Server 2010, services de mobilité dans Lync Server 2013 autorisent les clients mobiles Microsoft Lync sur les téléphones mobiles et les tablettes utilisant des appareils mobiles Apple iOS, Android, Windows Phone ou Nokia pris en charge pour effectuer des activités telles que l’envoi et la réception de messages instantanés, l’affichage de contacts</span><span class="sxs-lookup"><span data-stu-id="67153-114">**Mobility services for Mobile clients**   Introduced in a customer update for Lync Server 2010, Mobility services in Lync Server 2013 allow Microsoft Lync Mobile clients on mobile phones and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="67153-115">En outre, les appareils mobiles prennent en charge certaines fonctionnalités vocales d’entreprise, telles que cliquer pour participer à une conférence, appeler via le bureau, atteindre un seul numéro, messagerie vocale et notification d’appel en absence.</span><span class="sxs-lookup"><span data-stu-id="67153-115">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="67153-116">Les services de mobilité utilisent le proxy inverse et les services publiés qui sont déployés sur vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="67153-116">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="67153-117">Il est inutile d’apporter des modifications aux serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="67153-117">No changes are required to Edge Servers.</span></span>

    
    </div>

  - <span data-ttu-id="67153-118">**Les directeurs sont un rôle**   facultatif le rôle du serveur directeur dans la topologie Lync Server 2013 n’a pas changé.</span><span class="sxs-lookup"><span data-stu-id="67153-118">**Directors are an optional role**   The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="67153-119">Il héberge toujours des services Web, pré-authentifie les demandes des utilisateurs entrantes et dirige les utilisateurs externes vers leur pool d’accueil.</span><span class="sxs-lookup"><span data-stu-id="67153-119">It still hosts web services, pre-authenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="67153-120">La modification du directeur d’un rôle recommandé en un rôle facultatif ne diminue pas la valeur du directeur, mais met en évidence la réduction du nombre de serveurs et d’autres exigences matérielles (par exemple, les programmes d’équilibrage de la charge matérielle pour les directeurs) sans compromission des fonctionnalités et des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="67153-120">Changing the Director from a recommended role to an optional role does not diminish the value of the Director, but emphasizes reducing server count and other hardware requirements (for example, hardware load balancers for the Director) requirements without compromising features and functionality.</span></span> <span data-ttu-id="67153-121">Étant donné que les serveurs frontaux peuvent effectuer le même travail que le directeur sans impact sur les services fournis, vous pouvez éventuellement déployer des directeurs si vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="67153-121">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can optionally deploy Directors if you choose to.</span></span> <span data-ttu-id="67153-122">Vous pouvez en toute sécurité exclure le directeur en toute confiance que les serveurs frontaux fourniront les mêmes services à leur place.</span><span class="sxs-lookup"><span data-stu-id="67153-122">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in their place.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="67153-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="67153-123">See Also</span></span>


[<span data-ttu-id="67153-124">Planification et configuration D’ipv6 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67153-124">Planning for and configuring IPv6 in Lync Server 2013</span></span>](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[<span data-ttu-id="67153-125">Planification de l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67153-125">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="67153-126">Planification de la Fédération XMPP (extensible Messaging and Presence Protocol) dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67153-126">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

