---
title: 'Lync Server 2013 : basculement du pool de serveurs Edge utilisé pour la Fédération XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3957f3fc5a315c5b661ddeec4ea83b8e7f0eab0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="24013-102">Basculement du pool de serveurs Edge utilisé pour la Fédération XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24013-102">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24013-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="24013-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="24013-p101">Dans votre organisation, il existe un pool de serveurs Edge désigné en tant que pool à utiliser pour la fédération XMPP. Si ce pool tombe en panne, vous devez effectuer un basculement de la fédération XMPP et utiliser un autre pool de serveurs Edge pour permettre à la fédération XMPP de fonctionner à nouveau.</span><span class="sxs-lookup"><span data-stu-id="24013-p101">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="24013-106">Quand vous installez des pools de serveurs Edge et que vous activez la fédération XMPP, vous pouvez simplifier le processus de récupération d’urgence en configurant des enregistrements SRV DNS externes pour tous les pools de serveurs Edge (au lieu d’un seul) de la fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="24013-106">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="24013-107">Chacun de ces enregistrements SRV doit avoir une priorité distincte.</span><span class="sxs-lookup"><span data-stu-id="24013-107">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="24013-108">Tout le trafic de la fédération XMPP passe par le pool dont l’enregistrement SRV a la priorité la plus élevée.</span><span class="sxs-lookup"><span data-stu-id="24013-108">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> <span data-ttu-id="24013-109">Pour plus d’informations sur l’activation et la configuration de la Fédération XMPP, voir [configuration de la Fédération XMPP dans Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="24013-109">For more information on enabling and setting up XMPP federation, see [Setting up XMPP federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span></span>

<span data-ttu-id="24013-110">Dans la procédure suivante, EdgePool1 est le pool qui a hébergé à l’origine la fédération XMPP. EdgePool2 est le pool qui va désormais héberger la fédération XMPP.</span><span class="sxs-lookup"><span data-stu-id="24013-110">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="24013-111">Basculement du pool de serveurs Edge utilisé pour la fédération XMPP</span><span class="sxs-lookup"><span data-stu-id="24013-111">Failing Over the Edge Pool Used for XMPP Federation</span></span>

1.  <span data-ttu-id="24013-112">Si vous n’avez pas d’autre pool de serveurs Edge déployé (en plus de celui qui est actuellement en panne), déployez ce pool.</span><span class="sxs-lookup"><span data-stu-id="24013-112">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> <span data-ttu-id="24013-113">Pour plus d’informations, reportez-vous à la rubrique [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="24013-113">For details, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

2.  <span data-ttu-id="24013-114">Sur chaque serveur Edge du nouveau pool de serveurs Edge qui va héberger la fédération XMPP (EdgePool2), exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="24013-114">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="24013-115">Exécutez l’applet de commande suivante pour faire pointer à nouveau l’itinéraire de fédération XMPP vers EdgePool2 :</span><span class="sxs-lookup"><span data-stu-id="24013-115">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="24013-116">Dans cet exemple, Site2 est le site contenant le pool de serveurs Edge qui va héberger l’itinéraire de fédération XMPP. EdgeServer2.contoso.com est le nom de domaine complet d’un serveur Edge de ce pool.</span><span class="sxs-lookup"><span data-stu-id="24013-116">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="24013-117">Sur le serveur DNS externe, modifiez l’enregistrement DNS A afin que la fédération XMPP pointe vers EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="24013-117">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="24013-p104">Si vous n’avez pas encore d’enregistrement DNS SRV pour la fédération XMPP correspondant au pool de serveurs Edge qui va héberger la fédération XMPP, vous devez l’ajouter, comme dans l’exemple suivant. La valeur du port de cet enregistrement SRV doit être 5269.</span><span class="sxs-lookup"><span data-stu-id="24013-p104">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="24013-120">Assurez-vous que le port externe 5269 du pool de serveurs Edge qui va héberger la fédération XMPP est ouvert.</span><span class="sxs-lookup"><span data-stu-id="24013-120">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="24013-121">Démarrez les services de tous les serveurs Edge du pool de serveurs Edge qui va héberger la fédération XMPP :</span><span class="sxs-lookup"><span data-stu-id="24013-121">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

