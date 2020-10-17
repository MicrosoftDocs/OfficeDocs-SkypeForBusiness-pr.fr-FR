---
title: Restauration du pool Edge utilisé pour Lync Server Federation ou XMPP Federation
description: Restauration des pools de serveurs Edge utilisés pour la Fédération XMPP ou Fédération Lync Server.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 137910d71de1d6177356e0b7bacbd6d17022d71d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567720"
---
# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="f99ce-103">Restauration du pool Edge utilisé pour Lync Server Federation ou XMPP Federation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f99ce-103">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f99ce-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f99ce-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f99ce-105">Lorsqu’un pool Edge en échec qui hébergeait la fédération a été remis en ligne, suivez cette procédure pour restaurer l’itinéraire de fédération Lync Server et/ou l’itinéraire de fédération XMPP pour réutiliser ce pool Edge restauré.</span><span class="sxs-lookup"><span data-stu-id="f99ce-105">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Lync Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a><span data-ttu-id="f99ce-106">Restauration de la fédération sur un pool Edge restauré</span><span class="sxs-lookup"><span data-stu-id="f99ce-106">Failing Back Federation to a Restored Edge Pool</span></span>

1.  <span data-ttu-id="f99ce-107">Sur le pool Edge de nouveau disponible, lancez les Services Edge.</span><span class="sxs-lookup"><span data-stu-id="f99ce-107">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="f99ce-108">Si vous voulez restaurer l’itinéraire de fédération Lync Server pour utiliser le serveur Edge restauré, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f99ce-108">If you want to fail back the Lync Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="f99ce-p101">Sur un serveur frontal, ouvrez le Générateur de topologie. Développez **Pools Edge**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge actuellement configuré pour la fédération. Sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f99ce-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="f99ce-p102">Dans **Modifier les propriétés**, sous **Général**, désactivez l’option **Activer la fédération pour ce pool Edge (Port 5061)**. Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f99ce-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="f99ce-p103">Développez **Pools Edge**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge d’origine que vous voulez réutiliser pour la fédération. Sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f99ce-p103">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="f99ce-p104">Dans **Modifier les propriétés**, sous **Général**, sélectionnez l’option **Activer la fédération pour ce pool Edge (Port 5061)**. Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f99ce-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="f99ce-p105">Cliquez sur **Action**, sélectionnez **Topologie**, puis **Publier**. À l’invite dans la page **Publier la topologie**, cliquez sur **Suivant**. Une fois la publication terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f99ce-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="f99ce-p106">Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur **Installer ou mettre à jour le système Lync Server**, puis sur **Installer ou supprimer des composants Lync Server**. Cliquez sur **Réexécuter**.</span><span class="sxs-lookup"><span data-stu-id="f99ce-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>
    
      - <span data-ttu-id="f99ce-p107">Sur la page Configurer les composants Lync Server, cliquez sur **Suivant**. L’écran de résumé affiche les actions lorsqu’elles sont exécutées. Une fois le déploiement terminé, cliquez sur **Voir le journal** pour voir les fichiers journaux disponibles. Cliquez sur **Terminer** pour terminer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="f99ce-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="f99ce-128">Si vous voulez restaurer l’itinéraire de fédération XMPP pour utiliser le serveur Edge restauré, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f99ce-128">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="f99ce-129">Exécutez la cmdlet suivante pour pointer de nouveau l’itinéraire de fédération XMPP sur le pool Edge qui héberge désormais la fédération XMPP (dans cet exemple, EdgeServer1) :</span><span class="sxs-lookup"><span data-stu-id="f99ce-129">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="f99ce-130">Dans cet exemple, Site1 représente le site qui contient le pool Edge qui hébergera désormais l’itinéraire de fédération XMPP, et EdgeServer1.contoso.com représente le nom de domaine complet (FQDN) d’un serveur Edge de ce pool.</span><span class="sxs-lookup"><span data-stu-id="f99ce-130">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="f99ce-p108">Si vous n’avez pas encore d’enregistrement DNS SRV pour la fédération XMPP qui aboutit au pool Edge qui héberge désormais la fédération XMPP, vous devez l’ajouter, comme dans l’exemple suivant. Cet enregistrement SRV doit avoir une valeur de port de 5269.</span><span class="sxs-lookup"><span data-stu-id="f99ce-p108">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="f99ce-133">Sur le serveur DNS externe, modifiez l’enregistrement DNS A pour la fédération XMPP de sorte qu’il pointe sur EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f99ce-133">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="f99ce-134">Vérifiez que le port 5269 du pool Edge qui héberge désormais la fédération XMPP est ouvert de façon externe.</span><span class="sxs-lookup"><span data-stu-id="f99ce-134">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="f99ce-135">Si les pools frontaux ont continué à s’exécuter sur le site contenant le pool Edge qui a échoué et a été restauré, vous devez mettre à jour les services de conférence web et de conférence A/V sur ces pools frontaux pour réutiliser les pools Edge sur leur site local.</span><span class="sxs-lookup"><span data-stu-id="f99ce-135">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span> <span data-ttu-id="f99ce-136">Pour plus d’informations, consultez [la rubrique Modification du pool de serveurs Edge associé à un pool frontal dans Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="f99ce-136">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

5.  <span data-ttu-id="f99ce-137">Si le pool frontal du site où le pool Edge a échoué échoue également, vous pouvez désormais utiliser Invoke–CsPoolFailback pour restaurer le pool frontal.</span><span class="sxs-lookup"><span data-stu-id="f99ce-137">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f99ce-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f99ce-138">See Also</span></span>


[<span data-ttu-id="f99ce-139">Basculement du pool de serveurs Edge utilisé pour la Fédération Lync Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f99ce-139">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[<span data-ttu-id="f99ce-140">Basculement du pool de serveurs Edge utilisé pour la Fédération XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f99ce-140">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[<span data-ttu-id="f99ce-141">Récupération d’urgence de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f99ce-141">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

