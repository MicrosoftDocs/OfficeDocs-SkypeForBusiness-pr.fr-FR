---
title: Empêcher les nouvelles connexions à Lync Server pour la maintenance du serveur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db3838af59a6a91699fa6d38b8aa2912e2b30012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a><span data-ttu-id="31c0c-102">Empêcher les nouvelles connexions à Lync Server 2013 pour la maintenance du serveur</span><span class="sxs-lookup"><span data-stu-id="31c0c-102">Prevent new connections to Lync Server 2013 for server maintenance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31c0c-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="31c0c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="31c0c-104">Lync Server vous permet de mettre un serveur hors connexion (par exemple, pour appliquer des mises à jour logicielles ou matérielles) sans perte de service aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="31c0c-104">Lync Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="31c0c-105">Lorsque vous spécifiez l’option permettant d’éviter de nouvelles connexions ou appels vers un serveur d’un pool, il cesse de prendre de nouvelles connexions et appels dès que vous implémentez cette option.</span><span class="sxs-lookup"><span data-stu-id="31c0c-105">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="31c0c-106">Ces nouvelles connexions et appels sont routés par le biais d’autres serveurs du pool.</span><span class="sxs-lookup"><span data-stu-id="31c0c-106">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="31c0c-107">Un serveur qui empêche de nouvelles connexions autorise la poursuite de ses sessions sur les connexions existantes jusqu’à ce qu’il se termine de façon naturelle.</span><span class="sxs-lookup"><span data-stu-id="31c0c-107">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="31c0c-108">Lorsque toutes les sessions existantes sont terminées, le serveur est prêt à être déconnecté.</span><span class="sxs-lookup"><span data-stu-id="31c0c-108">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="31c0c-109">Lorsque vous interdisez de nouvelles connexions à un serveur frontal, certains services et fonctionnalités Lync Server dépendent de l’équilibrage de charge DNS pour s’assurer qu’elle fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="31c0c-109">When you prevent new connections to a Front End Server, some Lync Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="31c0c-110">Si vous n’utilisez pas l’équilibrage de charge DNS sur le pool, les connexions par le biais de ces services ne peuvent pas être redirigées vers d’autres serveurs au cours de la période pendant laquelle le serveur empêche les nouvelles connexions, et par conséquent, lorsque le serveur est hors connexion, certaines sessions et appels peuvent être garantir.</span><span class="sxs-lookup"><span data-stu-id="31c0c-110">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="31c0c-111">Les fonctionnalités qui dépendent de l’équilibrage de charge DNS pour s’assurer que cette option fonctionne correctement sont les suivantes:</span><span class="sxs-lookup"><span data-stu-id="31c0c-111">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="31c0c-112">Intendant</span><span class="sxs-lookup"><span data-stu-id="31c0c-112">Attendant</span></span>

  - <span data-ttu-id="31c0c-113">application d’annonce de conférence</span><span class="sxs-lookup"><span data-stu-id="31c0c-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="31c0c-114">application Response Group</span><span class="sxs-lookup"><span data-stu-id="31c0c-114">Response Group application</span></span>

  - <span data-ttu-id="31c0c-115">application d’annonce</span><span class="sxs-lookup"><span data-stu-id="31c0c-115">Announcement application</span></span>

  - <span data-ttu-id="31c0c-116">application de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="31c0c-116">Call Park application</span></span>

<span data-ttu-id="31c0c-117">Pour plus d’informations sur l’équilibrage de charge DNS, voir [équilibrage de charge DNS dans Lync Server 2013](lync-server-2013-dns-load-balancing.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="31c0c-117">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<span data-ttu-id="31c0c-118">Outre qu’il n’est pas possible d’empêcher les nouvelles connexions de tous les services sur un serveur exécutant Lync Server, vous pouvez également éviter de nouvelles connexions pour les services Lync Server individuels.</span><span class="sxs-lookup"><span data-stu-id="31c0c-118">In addition to preventing new connections for all services on a server running Lync Server, you can also prevent new connections for individual Lync Server services.</span></span> <span data-ttu-id="31c0c-119">Par exemple, cette méthode est utile dans le cas où vous devez appliquer une mise à jour du serveur Lync qui ne nécessite pas l’arrêt de l’intégralité du serveur.</span><span class="sxs-lookup"><span data-stu-id="31c0c-119">For example, this method is useful in a situation where you need to apply a Lync Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="31c0c-120">Notez que lorsque vous interdisez les connexions d’un service, vous devez sélectionner un service tel qu’il est groupé et affiché dans la liste des services Windows.</span><span class="sxs-lookup"><span data-stu-id="31c0c-120">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="31c0c-121">Par exemple, le service frontal de Lync Server et l’agent de collecte des données pour la surveillance sont des services Lync Server distincts, mais dans la liste des services Windows, ils sont consolidés et affichés comme le service frontal de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="31c0c-121">For example, the Lync Server Front-End service and the data collection agent for Monitoring are separate Lync Server services, but in the Windows services list they are consolidated and shown as the Lync Server Front End service.</span></span> <span data-ttu-id="31c0c-122">Vous pouvez empêcher de nouvelles connexions pour le service frontal de Lync Server, mais vous ne pouvez pas empêcher les nouvelles connexions de ces deux services Lync Server sous-jacents séparément.</span><span class="sxs-lookup"><span data-stu-id="31c0c-122">You can prevent new connections for the Lync Server Front End service, but you cannot prevent new connections for these two individual underlying Lync Server services separately.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="31c0c-123">Lorsque vous définissez un serveur pour empêcher les nouvelles connexions, puis que vous redémarrez le serveur, par défaut, le serveur commence immédiatement à accepter de nouvelles connexions après son démarrage.</span><span class="sxs-lookup"><span data-stu-id="31c0c-123">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="31c0c-124">Pour éviter ce problème, configurez le serveur de façon à ce qu’il ne s’interrompe qu’après le redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="31c0c-124">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a><span data-ttu-id="31c0c-125">Pour éviter de nouvelles connexions à Lync Server:</span><span class="sxs-lookup"><span data-stu-id="31c0c-125">To prevent new connections to Lync Server:</span></span>

1.  <span data-ttu-id="31c0c-126">Connectez-vous à l’ordinateur local en tant que membre du groupe administrateurs.</span><span class="sxs-lookup"><span data-stu-id="31c0c-126">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="31c0c-127">Ouvrez la console enfichable Services: cliquez sur **Démarrer**, pointez sur **tous les programmes**, sur **Outils d’administration**, puis cliquez sur **services**.</span><span class="sxs-lookup"><span data-stu-id="31c0c-127">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="31c0c-128">Dans la liste, double-cliquez sur le service Windows Server Lync pour lequel vous voulez empêcher les nouvelles connexions.</span><span class="sxs-lookup"><span data-stu-id="31c0c-128">In the list, double-click the Lync Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="31c0c-129">Dans la boîte de dialogue Propriétés, sous **État du service: démarré**, cliquez sur **suspendre**.</span><span class="sxs-lookup"><span data-stu-id="31c0c-129">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="31c0c-130">Si vous le souhaitez, mais que vous avez le choix, en regard de **type de démarrage**, cliquez sur **Manuel**.</span><span class="sxs-lookup"><span data-stu-id="31c0c-130">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="31c0c-131">Lorsque vous définissez un serveur pour empêcher les nouvelles connexions, puis que vous redémarrez le serveur, par défaut, le serveur commence immédiatement à accepter de nouvelles connexions après son démarrage.</span><span class="sxs-lookup"><span data-stu-id="31c0c-131">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="31c0c-132">Pour éviter ce problème, configurez le serveur de façon à ce qu’il ne s’interrompe qu’après le redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="31c0c-132">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

    
    </div>

6.  <span data-ttu-id="31c0c-133">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="31c0c-133">When you are finished, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

