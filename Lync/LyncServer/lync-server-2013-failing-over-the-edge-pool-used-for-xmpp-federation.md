---
title: 'Lync Server 2013 : Basculement vers le pool Edge utilisé pour la fédération XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 551774c070ebafd25376d220b20acccc8c573af2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="3f3d6-102">Basculement vers le pool Edge utilisé pour la fédération XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f3d6-102">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f3d6-103">_**Dernière modification de la rubrique:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="3f3d6-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="3f3d6-104">Dans votre organisation, il existe un pool Edge désigné comme pool à utiliser pour la Fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="3f3d6-104">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="3f3d6-105">Si ce pool est vers le bas, vous devez le faire basculer sur la Fédération XMPP pour utiliser un pool Edge différent avant que la Fédération XMPP puisse fonctionner de nouveau.</span><span class="sxs-lookup"><span data-stu-id="3f3d6-105">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="3f3d6-106">Lorsque vous installez les pools de périphérie et activez la Fédération XMPP, vous pouvez simplifier le processus de reprise après sinistre en configurant des enregistrements SRV DNS externes pour tous vos pools de périphérie pour la Fédération XMPP, au lieu d’une seule.</span><span class="sxs-lookup"><span data-stu-id="3f3d6-106">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="3f3d6-107">Chacun de ces enregistrements SRV doit avoir un ensemble de priorités différent.</span><span class="sxs-lookup"><span data-stu-id="3f3d6-107">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="3f3d6-108">Tout le trafic de Fédération XMPP traverse le pool avec l’enregistrement SRV dont la priorité est la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="3f3d6-108">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> <span data-ttu-id="3f3d6-109">Pour plus d’informations sur l’activation et la configuration de la Fédération XMPP, voir [configuration de la Fédération XMPP dans Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="3f3d6-109">For more information on enabling and setting up XMPP federation, see [Setting up XMPP federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span></span>

<span data-ttu-id="3f3d6-110">Dans la procédure ci-dessous, EdgePool1 est le pool qui a hébergé la Fédération XMPP et EdgePool2 est le pool qui héberge désormais la Fédération de XMPP.</span><span class="sxs-lookup"><span data-stu-id="3f3d6-110">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="3f3d6-111">Échec du pool Edge utilisé pour la Fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="3f3d6-111">Failing Over the Edge Pool Used for XMPP Federation</span></span>

1.  <span data-ttu-id="3f3d6-112">Si vous n’avez pas encore déployé un pool Edge (en plus de celui qui est actuellement disponible), vous devez déployer ce pool.</span><span class="sxs-lookup"><span data-stu-id="3f3d6-112">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> <span data-ttu-id="3f3d6-113">Pour plus d’informations, reportez-vous à [déploiement d’un accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="3f3d6-113">For details, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

2.  <span data-ttu-id="3f3d6-114">Sur chaque serveur Edge du nouveau pool de périphériques Edge qui hébergera maintenant la Fédération de XMPP (EdgePool2), exécutez l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="3f3d6-114">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="3f3d6-115">Exécutez l’applet de commande suivante pour rediriger l’itinéraire de Fédération XMPP vers EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="3f3d6-115">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="3f3d6-116">Dans cet exemple, site2 est le site contenant le pool de bords qui héberge désormais l’itinéraire de Fédération XMPP et EdgeServer2.contoso.com est le nom de domaine complet d’un serveur Edge dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="3f3d6-116">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="3f3d6-117">Sur le serveur DNS externe, modifiez l’enregistrement DNS A pour la Fédération XMPP de sorte qu’il pointe sur EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3f3d6-117">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="3f3d6-118">Si vous ne disposez pas encore d’un enregistrement DNS SRV pour la Fédération XMPP qui se résout au pool de périphérie qui hébergera maintenant la Fédération de XMPP, vous devez l’ajouter, comme dans l’exemple ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="3f3d6-118">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="3f3d6-119">Cet enregistrement SRV doit avoir une valeur de port de 5269.</span><span class="sxs-lookup"><span data-stu-id="3f3d6-119">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="3f3d6-120">Assurez-vous que le pool de bords qui hébergera désormais la Fédération XMPP dispose d’une ouverture externe du port 5269.</span><span class="sxs-lookup"><span data-stu-id="3f3d6-120">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="3f3d6-121">Démarrez les services sur tous les serveurs Edge du pool Edge qui hébergeront désormais la Fédération XMPP:</span><span class="sxs-lookup"><span data-stu-id="3f3d6-121">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

