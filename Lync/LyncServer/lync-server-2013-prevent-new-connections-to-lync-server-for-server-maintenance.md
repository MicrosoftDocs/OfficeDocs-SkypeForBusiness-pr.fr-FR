---
title: Empêcher les nouvelles connexions à Lync Server pour la maintenance du serveur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3678414e45e556eb7092b923fab4b737bfd4842
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a><span data-ttu-id="62e1a-102">Empêcher les nouvelles connexions à Lync Server 2013 pour la maintenance du serveur</span><span class="sxs-lookup"><span data-stu-id="62e1a-102">Prevent new connections to Lync Server 2013 for server maintenance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62e1a-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="62e1a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="62e1a-104">Lync Server vous permet de mettre un serveur hors connexion (par exemple, pour appliquer des mises à niveau logicielles ou matérielles) sans perte de service pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="62e1a-104">Lync Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="62e1a-p101">Quand vous spécifiez l’option qui empêche toute nouvelle connexion ou tout nouvel appel sur un serveur appartenant à un pool, Lync Server n’accepte plus de nouvelles connexions, ni de nouveaux appels une fois cette option implémentée. Quand un serveur empêche toute nouvelle connexion, il autorise ses sessions sur des connexions existantes à se poursuivre, jusqu’à ce qu’elles se terminent normalement. Une fois toutes les sessions existantes parvenues à terme, le serveur est prêt à être mis hors connexion.</span><span class="sxs-lookup"><span data-stu-id="62e1a-p101">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option. These new connections and calls are routed through other servers in the pool. A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end. When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="62e1a-109">Lorsque vous interdisez de nouvelles connexions à un serveur frontal, certains services et fonctionnalités Lync Server s’appuient sur l’équilibrage de charge DNS pour s’assurer qu’il fonctionne correctement.</span><span class="sxs-lookup"><span data-stu-id="62e1a-109">When you prevent new connections to a Front End Server, some Lync Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="62e1a-110">Si vous n’utilisez pas l’équilibrage de charge DNS sur le pool, les connexions par le biais de ces services ne peuvent pas être redirigées vers d’autres serveurs pendant la période pendant laquelle le serveur empêche les nouvelles connexions et, par conséquent, lorsque le serveur est mis hors connexion, certaines sessions et appels peuvent être fonctionner.</span><span class="sxs-lookup"><span data-stu-id="62e1a-110">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="62e1a-111">Les fonctionnalités qui dépendent de l’équilibrage de charge DNS pour s’assurer que cette option fonctionne correctement sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="62e1a-111">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="62e1a-112">Attendant</span><span class="sxs-lookup"><span data-stu-id="62e1a-112">Attendant</span></span>

  - <span data-ttu-id="62e1a-113">application d’annonce de conférence</span><span class="sxs-lookup"><span data-stu-id="62e1a-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="62e1a-114">Application Response Group</span><span class="sxs-lookup"><span data-stu-id="62e1a-114">Response Group application</span></span>

  - <span data-ttu-id="62e1a-115">application d’annonce</span><span class="sxs-lookup"><span data-stu-id="62e1a-115">Announcement application</span></span>

  - <span data-ttu-id="62e1a-116">application de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="62e1a-116">Call Park application</span></span>

<span data-ttu-id="62e1a-117">Pour plus d’informations sur l’équilibrage de la charge DNS, voir [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="62e1a-117">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<span data-ttu-id="62e1a-118">En plus d’empêcher les nouvelles connexions pour tous les services sur un serveur exécutant Lync Server, vous pouvez également empêcher les nouvelles connexions pour des services Lync Server individuels.</span><span class="sxs-lookup"><span data-stu-id="62e1a-118">In addition to preventing new connections for all services on a server running Lync Server, you can also prevent new connections for individual Lync Server services.</span></span> <span data-ttu-id="62e1a-119">Par exemple, cette méthode est utile lorsque vous devez appliquer une mise à jour Lync Server qui ne nécessite pas l’arrêt de l’ensemble du serveur.</span><span class="sxs-lookup"><span data-stu-id="62e1a-119">For example, this method is useful in a situation where you need to apply a Lync Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="62e1a-120">Veuillez noter que lorsque vous interdisez les connexions pour un service, vous devez sélectionner un service groupé et affiché dans la liste des services Windows.</span><span class="sxs-lookup"><span data-stu-id="62e1a-120">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="62e1a-121">Par exemple, le service frontal Lync Server et l’agent de collecte de données pour la surveillance sont des services Lync Server distincts, mais dans la liste des services Windows, ils sont consolidés et affichés en tant que service frontal Lync Server.</span><span class="sxs-lookup"><span data-stu-id="62e1a-121">For example, the Lync Server Front-End service and the data collection agent for Monitoring are separate Lync Server services, but in the Windows services list they are consolidated and shown as the Lync Server Front End service.</span></span> <span data-ttu-id="62e1a-122">Vous pouvez empêcher les nouvelles connexions pour le service frontal Lync Server, mais vous ne pouvez pas empêcher les nouvelles connexions pour ces deux services Lync Server sous-jacents individuels.</span><span class="sxs-lookup"><span data-stu-id="62e1a-122">You can prevent new connections for the Lync Server Front End service, but you cannot prevent new connections for these two individual underlying Lync Server services separately.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="62e1a-p104">Lorsque vous configurez un serveur pour empêcher les nouvelles connexions, puis le redémarrez, par défaut, le serveur accepte immédiatement les connexions. Si vous ne voulez pas que cela se produise, configurez le serveur pour qu’il ne soit suspendu et redémarré que manuellement avant de redémarrer le serveur.</span><span class="sxs-lookup"><span data-stu-id="62e1a-p104">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a><span data-ttu-id="62e1a-125">Pour empêcher les nouvelles connexions à Lync Server, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="62e1a-125">To prevent new connections to Lync Server:</span></span>

1.  <span data-ttu-id="62e1a-126">Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.</span><span class="sxs-lookup"><span data-stu-id="62e1a-126">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="62e1a-127">Ouvrez la console de composant logiciel enfichable Services : cliquez sur **Démarrer**, pointez sur **tous les programmes**, sur **Outils d’administration**, puis cliquez sur **services**.</span><span class="sxs-lookup"><span data-stu-id="62e1a-127">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="62e1a-128">Dans la liste, double-cliquez sur le service Windows Lync Server auquel vous voulez empêcher les nouvelles connexions.</span><span class="sxs-lookup"><span data-stu-id="62e1a-128">In the list, double-click the Lync Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="62e1a-129">Dans la boîte de dialogue Propriétés, sous **État du service : Démarré**, cliquez sur **Suspendre**.</span><span class="sxs-lookup"><span data-stu-id="62e1a-129">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="62e1a-130">La méthode facultative et recommandée consiste à cliquer sur **Manuel**, en regard de **Type de démarrage**.</span><span class="sxs-lookup"><span data-stu-id="62e1a-130">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="62e1a-p105">Quand vous configurez un serveur de manière à empêcher de nouvelles connexions puis que vous le redémarrez, par défaut, le serveur accepte immédiatement les nouvelles connexions après son redémarrage. Pour éviter cela, configurez le serveur de manière à ce qu’il s’interrompe et reprenne uniquement manuellement, puis redémarrez-le.</span><span class="sxs-lookup"><span data-stu-id="62e1a-p105">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

    
    </div>

6.  <span data-ttu-id="62e1a-133">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="62e1a-133">When you are finished, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

