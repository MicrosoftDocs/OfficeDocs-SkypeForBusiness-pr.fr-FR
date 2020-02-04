---
title: 'Lync Server 2013 : Basculement vers le pool Edge utilisé pour la fédération Lync Server'
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
ms.openlocfilehash: f144def3d3a8df9cc63221342a85666eb3c28913
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a><span data-ttu-id="d2d86-102">Basculement vers le pool Edge utilisé pour la fédération Lync Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2d86-102">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2d86-103">_**Dernière modification de la rubrique :** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="d2d86-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="d2d86-104">Si le pool de périphériques sur lequel vous avez configuré Lync Server Federation s’affiche, vous devez modifier la Fédération de manière à utiliser un pool de périphérie différent pour que la Fédération fonctionne.</span><span class="sxs-lookup"><span data-stu-id="d2d86-104">If the Edge pool where you have Lync Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a><span data-ttu-id="d2d86-105">Échec du pool Edge utilisé pour la Fédération Lync Server</span><span class="sxs-lookup"><span data-stu-id="d2d86-105">Failing Over the Edge Pool Used for Lync Server Federation</span></span>

1.  <span data-ttu-id="d2d86-106">Sur un serveur frontal, ouvrez le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="d2d86-106">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="d2d86-107">Développez **pools de bords**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge actuellement configuré pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="d2d86-107">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="d2d86-108">Sélectionnez **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d2d86-108">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="d2d86-109">Dans **modifier les propriétés** sous **général**, décochez **la case Activer la Fédération pour ce pool de périphériques (port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="d2d86-109">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="d2d86-110">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2d86-110">Click **OK**.</span></span>

3.  <span data-ttu-id="d2d86-111">Développez **pools de bords**, puis cliquez avec le bouton droit sur le serveur Edge ou le pool de serveurs Edge que vous voulez utiliser pour la Fédération.</span><span class="sxs-lookup"><span data-stu-id="d2d86-111">Expand **Edge pools**, then right click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="d2d86-112">Sélectionnez **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d2d86-112">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="d2d86-113">Dans **modifier les propriétés** sous **général**, sélectionnez **activer la Fédération pour ce pool Edge (port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="d2d86-113">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="d2d86-114">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2d86-114">Click **OK**.</span></span>

5.  <span data-ttu-id="d2d86-115">Cliquez sur **action**, sélectionnez **topologie**, puis **publier**.</span><span class="sxs-lookup"><span data-stu-id="d2d86-115">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="d2d86-116">Lorsque le système vous **le**demande, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="d2d86-116">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="d2d86-117">Lorsque la publication est terminée, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="d2d86-117">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="d2d86-118">Sur le serveur Edge, ouvrez l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d2d86-118">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="d2d86-119">Cliquez sur **installer ou mettre à jour le système serveur Lync**, puis cliquez sur **configurer ou supprimer les composants Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d2d86-119">Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**.</span></span> <span data-ttu-id="d2d86-120">Cliquez de **nouveau sur exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d2d86-120">Click **Run Again**.</span></span>

7.  <span data-ttu-id="d2d86-121">Dans configurer les composants serveur Lync, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="d2d86-121">At Setup Lync Server components, click **Next**.</span></span> <span data-ttu-id="d2d86-122">L’écran de synthèse indique les actions à mesure qu’elles sont exécutées.</span><span class="sxs-lookup"><span data-stu-id="d2d86-122">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="d2d86-123">Lorsque le déploiement est effectué, cliquez sur **afficher le journal** pour afficher les fichiers journaux disponibles.</span><span class="sxs-lookup"><span data-stu-id="d2d86-123">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="d2d86-124">Cliquez sur **Terminer** pour terminer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="d2d86-124">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="d2d86-125">Si le site contenant le pool de périphériques en échec contient des serveurs frontaux qui sont toujours en cours d’exécution, vous devez mettre à jour les services de conférence Web et de conférence A/V sur ces pools frontal pour qu’ils utilisent un pool de bords sur un site distant qui est toujours en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="d2d86-125">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> <span data-ttu-id="d2d86-126">Pour plus d’informations, reportez-vous à [la section changement du pool de bords associé à un pool frontal dans Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="d2d86-126">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d2d86-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d2d86-127">See Also</span></span>


[<span data-ttu-id="d2d86-128">Basculement vers le pool Edge utilisé pour la fédération XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2d86-128">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[<span data-ttu-id="d2d86-129">Restauration du pool Edge utilisé pour la fédération XMPP ou Lync Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2d86-129">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[<span data-ttu-id="d2d86-130">Récupération d’urgence de serveur Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2d86-130">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

