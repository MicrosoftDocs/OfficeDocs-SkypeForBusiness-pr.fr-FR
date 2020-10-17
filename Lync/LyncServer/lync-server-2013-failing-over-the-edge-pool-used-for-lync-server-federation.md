---
title: 'Lync Server 2013 : basculement du pool de serveurs Edge utilisé pour la Fédération Lync Server'
description: 'Lync Server 2013 : basculement du pool de serveurs Edge utilisé pour la Fédération Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1e7e13ccd35a653d38174f55ace9dc6637ded04
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554910"
---
# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a><span data-ttu-id="f9301-103">Basculement du pool de serveurs Edge utilisé pour la Fédération Lync Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9301-103">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9301-104">_**Dernière modification de la rubrique :** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="f9301-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="f9301-105">Si le pool de serveurs Edge où la fédération Lync Server est configurée tombe en panne, vous devez modifier la fédération de manière à ce qu’elle utilise un pool de serveurs Edge différent pour la rendre opérationnelle.</span><span class="sxs-lookup"><span data-stu-id="f9301-105">If the Edge pool where you have Lync Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a><span data-ttu-id="f9301-106">Basculement du pool de serveurs Edge utilisé pour la fédération Lync Server</span><span class="sxs-lookup"><span data-stu-id="f9301-106">Failing Over the Edge Pool Used for Lync Server Federation</span></span>

1.  <span data-ttu-id="f9301-p101">Sur un serveur frontal, ouvrez le Générateur de topologie. Développez **Pool de serveurs Edge**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge actuellement configuré pour la fédération. Sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f9301-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>

2.  <span data-ttu-id="f9301-p102">Dans **Modifier les propriétés**, sous **Général**, désactivez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**. Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9301-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

3.  <span data-ttu-id="f9301-p103">Développez **Pool de serveurs Edge**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge que vous souhaitez à présent utiliser pour la fédération. Sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f9301-p103">Expand **Edge pools**, then right click the Edge server or Edge server pool that you now want to use for Federation. Select **Edit properties**.</span></span>

4.  <span data-ttu-id="f9301-p104">Dans **Modifier les propriétés**, sous **Général**, activez la case à cocher **Activer la fédération pour ce pool Edge (port 5061)**. Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9301-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

5.  <span data-ttu-id="f9301-p105">Cliquez sur **Action**, sélectionnez **Topologie**, puis **Publier**. À l’invite dans la page **Publier la topologie**, cliquez sur **Suivant**. Une fois la publication terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="f9301-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="f9301-p106">Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server. Cliquez sur **Installer ou mettre à jour le système Lync Server**, puis sur **Installer ou supprimer des composants Lync Server**. Cliquez sur **Réexécuter**.</span><span class="sxs-lookup"><span data-stu-id="f9301-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>

7.  <span data-ttu-id="f9301-p107">Dans Installer les composants Lync Server, cliquez sur **Suivant**. L’écran de résumé affiche les actions au fur et à mesure qu’elles s’exécutent. Une fois le déploiement terminé, cliquez sur **Afficher le journal** pour afficher les fichiers journaux disponibles. Cliquez sur **Terminer** pour terminer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="f9301-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="f9301-126">Si le site contenant le pool de serveurs Edge ayant échoué contient des serveurs frontaux qui sont encore en cours d’exécution, vous devez mettre à jour le service de conférence web et le service de conférence A/V sur ces pools de serveurs frontaux afin d’utiliser un pool de serveurs Edge dans un site distant qui est encore en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="f9301-126">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> <span data-ttu-id="f9301-127">Pour plus d’informations, consultez [la rubrique Modification du pool de serveurs Edge associé à un pool frontal dans Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="f9301-127">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f9301-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f9301-128">See Also</span></span>


[<span data-ttu-id="f9301-129">Basculement du pool de serveurs Edge utilisé pour la Fédération XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9301-129">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[<span data-ttu-id="f9301-130">Restauration du pool Edge utilisé pour Lync Server Federation ou XMPP Federation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9301-130">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[<span data-ttu-id="f9301-131">Récupération d’urgence de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9301-131">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

