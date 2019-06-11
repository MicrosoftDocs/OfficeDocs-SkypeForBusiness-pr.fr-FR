---
title: 'Lync Server 2013: mise à niveau ou mise à jour des serveurs frontaux'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99c91a4f5fcae9f8d78bf01b19a17795916fb660
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a><span data-ttu-id="ea34c-102">Upgrade or update Front End Servers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea34c-102">Upgrade or update Front End Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea34c-103">_**Dernière modification de la rubrique:** 2013-06-28_</span><span class="sxs-lookup"><span data-stu-id="ea34c-103">_**Topic Last Modified:** 2013-06-28_</span></span>

<span data-ttu-id="ea34c-104">Les serveurs frontaux d’un pool Enterprise Edition sont organisés en *domaines de mise à niveau*.</span><span class="sxs-lookup"><span data-stu-id="ea34c-104">The Front End Servers in an Enterprise Edition pool are organized into *upgrade domains*.</span></span> <span data-ttu-id="ea34c-105">Il s’agit de sous-ensembles de serveurs frontaux dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ea34c-105">These are subsets of Front End Servers in the pool.</span></span> <span data-ttu-id="ea34c-106">Les domaines de mise à niveau sont créés automatiquement par le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="ea34c-106">Upgrade Domains are created automatically by Topology Builder.</span></span>

<span data-ttu-id="ea34c-107">Lorsque vous procédez à la mise à niveau de vos serveurs, vous devez effectuer la mise à niveau d’un domaine à la fois.</span><span class="sxs-lookup"><span data-stu-id="ea34c-107">When you upgrade servers, you must do so one Upgrade Domain at a time.</span></span> <span data-ttu-id="ea34c-108">Mettez à niveau chaque serveur d’un domaine de mise à niveau, mettez-le à niveau, puis redémarrez-le avant de passer à un autre domaine de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="ea34c-108">Bring each Server in one Upgrade Domain down, upgrade it, and then restart it before you move on to another Upgrade Domain.</span></span> <span data-ttu-id="ea34c-109">Assurez-vous de garder une trace des domaines et serveurs de mise à niveau que vous avez mis à niveau jusqu’ici.</span><span class="sxs-lookup"><span data-stu-id="ea34c-109">Be sure to keep track of which Upgrade Domains and Servers that you have upgraded so far.</span></span> <span data-ttu-id="ea34c-110">Utilisez le diagramme de flux suivant lors de la mise à niveau de chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="ea34c-110">Use the following flowchart diagram when upgrading each server.</span></span>

<span data-ttu-id="ea34c-111">![42ed59a4-1c26-49f7-ade4-a5a788457ab9] (images/JJ204736.42ed59a4-1c26-49f7-ade4-a5a788457ab9(OCS.15).jpg "42ed59a4-1c26-49f7-ade4-a5a788457ab9")</span><span class="sxs-lookup"><span data-stu-id="ea34c-111">![42ed59a4-1c26-49f7-ade4-a5a788457ab9](images/JJ204736.42ed59a4-1c26-49f7-ade4-a5a788457ab9(OCS.15).jpg "42ed59a4-1c26-49f7-ade4-a5a788457ab9")</span></span>

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="ea34c-112">Pour appliquer une mise à niveau aux serveurs frontaux d’un pool</span><span class="sxs-lookup"><span data-stu-id="ea34c-112">To apply an upgrade to the Front End servers in a pool</span></span>

1.  <span data-ttu-id="ea34c-113">Sur un serveur frontal du pool, exécutez l’applet de commande suivante:</span><span class="sxs-lookup"><span data-stu-id="ea34c-113">On a Front End Server in the pool, run the following cmdlet:</span></span>
    
    <span data-ttu-id="ea34c-114">**Get-CsPoolUpgradeReadinessState**</span><span class="sxs-lookup"><span data-stu-id="ea34c-114">**Get-CsPoolUpgradeReadinessState**</span></span>
    
    <span data-ttu-id="ea34c-115">Si la valeur de *PoolUpgradeState* est **occupé**, attendez 10 minutes, puis réessayez de **Get-CsPoolUpgradeReadinessState** .</span><span class="sxs-lookup"><span data-stu-id="ea34c-115">If the value of *PoolUpgradeState* is **Busy**, wait for 10 minutes, and then try **Get-CsPoolUpgradeReadinessState** again.</span></span> <span data-ttu-id="ea34c-116">Si vous voyez **occupé** au moins trois temps consécutifs, après 10 minutes entre chaque tentative, ou si vous voyez un résultat de **InsufficientActiveFrontEnds** pour **PoolUpgradeState,** il y a un problème avec le pool.</span><span class="sxs-lookup"><span data-stu-id="ea34c-116">If you see **Busy** for at least three consecutive times, after waiting 10 minutes in between each attempt, or if you see any result of **InsufficientActiveFrontEnds** for **PoolUpgradeState,** then there is an issue with the pool.</span></span> <span data-ttu-id="ea34c-117">Si ce pool est associé à un autre pool frontal dans une topologie de récupération d’urgence, vous devez faire basculer le pool vers le pool de sauvegarde, puis mettre à jour les serveurs dans ce pool.</span><span class="sxs-lookup"><span data-stu-id="ea34c-117">If this pool is paired with another Front End pool in a disaster recovery topology, you should fail the pool over to the backup pool, and then update the servers in this pool.</span></span> <span data-ttu-id="ea34c-118">Pour plus d’informations, reportez-vous à [échec d’un pool dans Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="ea34c-118">For details, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span>
    
    <span data-ttu-id="ea34c-119">Si la valeur de *PoolUpgradeState* est **prête**, passez à l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="ea34c-119">If the value of *PoolUpgradeState* is **Ready**, go to step 2.</span></span>

2.  <span data-ttu-id="ea34c-120">L’applet **de passe Get-CsPoolUpgradeReadinessState** renvoie également des informations sur chaque domaine de mise à niveau du pool et sur les serveurs frontaux de chaque domaine de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="ea34c-120">The **Get-CsPoolUpgradeReadinessState** cmdlet also returns information about each upgrade domain in the pool, and about which Front End Servers are in each upgrade domain.</span></span> <span data-ttu-id="ea34c-121">Si la valeur **ReadyforUpgrade** est **true** pour le domaine de mise à niveau qui contient le ou les serveurs que vous voulez mettre à niveau, vous pouvez les mettre à niveau en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="ea34c-121">If the **ReadyforUpgrade** value is **True** for the upgrade domain that contains the server or servers you want to upgrade, you can safely upgrade those servers now.</span></span> <span data-ttu-id="ea34c-122">Pour cela, procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="ea34c-122">To do so, do the following:</span></span>
    
    1.  <span data-ttu-id="ea34c-123">Arrêtez les nouvelles connexions aux serveurs frontaux que vous allez mettre à niveau en utilisant `Stop-CsWindowsService -Graceful -Verbose` l’applet de commande.</span><span class="sxs-lookup"><span data-stu-id="ea34c-123">Stop new connections to the Front End Servers you are going to upgrade by using the `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ea34c-124">Si vous exécutez ces mises à niveau de serveur pendant une période d’inactivité du serveur planifié, vous pouvez exécuter cette applet de commande sans le paramètre'-<STRONG>douceur</STRONG>'comme suit: <STRONG>Stop-CsWindowsService</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ea34c-124">If you are performing these server upgrades during a scheduled server downtime, you can run this cmdlet without the ‘-<STRONG>Graceful</STRONG>‘ parameter, as follows: <STRONG>Stop-CsWindowsService</STRONG>.</span></span> <span data-ttu-id="ea34c-125">Cela arrêtera immédiatement les services, sans attendre le remplissage de toutes les demandes de service existantes.</span><span class="sxs-lookup"><span data-stu-id="ea34c-125">This will immediately shut down services, without waiting for all existing service requests to be filled.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="ea34c-126">Mettez à niveau les serveurs associés à ce domaine de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="ea34c-126">Upgrade the servers associated with this the Upgrade Domain.</span></span>
    
    3.  <span data-ttu-id="ea34c-127">Redémarrez les serveurs et assurez-vous qu’ils acceptent de nouvelles connexions.</span><span class="sxs-lookup"><span data-stu-id="ea34c-127">Restart the servers, and make sure they are accepting new connections.</span></span>

3.  <span data-ttu-id="ea34c-128">Répétez les étapes 1 et 2 pour chaque autre domaine de mise à niveau de la liste, jusqu’à ce que tous les serveurs front-end aient été mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="ea34c-128">Repeat Steps 1 and 2 for each other Upgrade Domain in the pool, until all Front End Servers have been upgraded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

