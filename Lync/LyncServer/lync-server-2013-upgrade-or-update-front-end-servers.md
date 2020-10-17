---
title: 'Lync Server 2013 : mise à niveau ou mise à jour des serveurs frontaux'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32a537dc701f7b3e613cc9364c786cb561cadb50
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530321"
---
# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a><span data-ttu-id="d5a6c-102">Mettre à niveau ou mettre à jour des serveurs frontaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5a6c-102">Upgrade or update Front End Servers in Lync Server 2013</span></span>

<div data-xmlns="https://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5a6c-103">_**Dernière modification de la rubrique :** 2013-06-28_</span><span class="sxs-lookup"><span data-stu-id="d5a6c-103">_**Topic Last Modified:** 2013-06-28_</span></span>

<span data-ttu-id="d5a6c-104">Les serveurs frontaux d’un pool Enterprise Edition sont organisés en *domaines de mise à niveau*.</span><span class="sxs-lookup"><span data-stu-id="d5a6c-104">The Front End Servers in an Enterprise Edition pool are organized into *upgrade domains*.</span></span> <span data-ttu-id="d5a6c-105">Il s’agit de sous-ensembles des serveurs frontaux dans le pool.</span><span class="sxs-lookup"><span data-stu-id="d5a6c-105">These are subsets of Front End Servers in the pool.</span></span> <span data-ttu-id="d5a6c-106">Les domaines de mise à niveau sont créés automatiquement par le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="d5a6c-106">Upgrade Domains are created automatically by Topology Builder.</span></span>

<span data-ttu-id="d5a6c-107">Lors de la mise à niveau des serveurs, vous devez effectuer un domaine de mise à niveau à la fois.</span><span class="sxs-lookup"><span data-stu-id="d5a6c-107">When you upgrade servers, you must do so one Upgrade Domain at a time.</span></span> <span data-ttu-id="d5a6c-108">Mettez chaque serveur dans un domaine de mise à niveau vers le bas, mettez-le à niveau, puis redémarrez-le avant de passer à un autre domaine de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="d5a6c-108">Bring each Server in one Upgrade Domain down, upgrade it, and then restart it before you move on to another Upgrade Domain.</span></span> <span data-ttu-id="d5a6c-109">N’oubliez pas de suivre les domaines et les serveurs de mise à niveau que vous avez mis à niveau jusqu’à présent.</span><span class="sxs-lookup"><span data-stu-id="d5a6c-109">Be sure to keep track of which Upgrade Domains and Servers that you have upgraded so far.</span></span> <span data-ttu-id="d5a6c-110">Utilisez l’organigramme suivant lors de la mise à niveau de chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="d5a6c-110">Use the following flowchart diagram when upgrading each server.</span></span>

![Mise à niveau ou mise à jour des serveurs frontaux](images/upgradeupdatefrontendserverslync2013.png)

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="d5a6c-112">Pour appliquer une mise à niveau sur les serveurs frontaux dans un pool</span><span class="sxs-lookup"><span data-stu-id="d5a6c-112">To apply an upgrade to the Front End servers in a pool</span></span>

1.  <span data-ttu-id="d5a6c-113">Sur le serveur frontal du pool, exécutez l’applet de commande suivant :</span><span class="sxs-lookup"><span data-stu-id="d5a6c-113">On a Front End Server in the pool, run the following cmdlet:</span></span>
    
    <span data-ttu-id="d5a6c-114">**Get-CsPoolUpgradeReadinessState**</span><span class="sxs-lookup"><span data-stu-id="d5a6c-114">**Get-CsPoolUpgradeReadinessState**</span></span>
    
    <span data-ttu-id="d5a6c-115">Si la valeur de *PoolUpgradeState* est **Busy**, patientez 10 minutes, puis réessayez d' **accéder à CsPoolUpgradeReadinessState** .</span><span class="sxs-lookup"><span data-stu-id="d5a6c-115">If the value of *PoolUpgradeState* is **Busy**, wait for 10 minutes, and then try **Get-CsPoolUpgradeReadinessState** again.</span></span> <span data-ttu-id="d5a6c-116">Si vous voyez **occupé** pendant au moins trois heures consécutives, après avoir attendu 10 minutes entre chaque tentative, ou si vous constatez un résultat de **InsufficientActiveFrontEnds** pour **PoolUpgradeState,** cela signifie qu’il y a un problème avec le pool.</span><span class="sxs-lookup"><span data-stu-id="d5a6c-116">If you see **Busy** for at least three consecutive times, after waiting 10 minutes in between each attempt, or if you see any result of **InsufficientActiveFrontEnds** for **PoolUpgradeState,** then there is an issue with the pool.</span></span> <span data-ttu-id="d5a6c-117">Si ce pool est couplé avec un autre pool frontal dans une topologie de récupération d’urgence, basculez ce pool vers le pool de sauvegarde, puis mettez à jour les serveurs de ce pool.</span><span class="sxs-lookup"><span data-stu-id="d5a6c-117">If this pool is paired with another Front End pool in a disaster recovery topology, you should fail the pool over to the backup pool, and then update the servers in this pool.</span></span> <span data-ttu-id="d5a6c-118">Pour plus d’informations, reportez-vous à [basculement d’un pool dans Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="d5a6c-118">For details, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span>
    
    <span data-ttu-id="d5a6c-119">Si la valeur de *PoolUpgradeState* est **Ready**, passez à l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="d5a6c-119">If the value of *PoolUpgradeState* is **Ready**, go to step 2.</span></span>

2.  <span data-ttu-id="d5a6c-120">L’applet de commande **Get-CsPoolUpgradeReadinessState** renvoie également des informations sur chaque domaine de mise à niveau dans le pool et sur les serveurs frontaux se situant dans chaque domaine de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="d5a6c-120">The **Get-CsPoolUpgradeReadinessState** cmdlet also returns information about each upgrade domain in the pool, and about which Front End Servers are in each upgrade domain.</span></span> <span data-ttu-id="d5a6c-121">Si la valeur **ReadyforUpgrade** est **true** pour le domaine de mise à niveau qui contient le ou les serveurs que vous souhaitez mettre à niveau, vous pouvez mettre à niveau ces serveurs en toute sécurité maintenant.</span><span class="sxs-lookup"><span data-stu-id="d5a6c-121">If the **ReadyforUpgrade** value is **True** for the upgrade domain that contains the server or servers you want to upgrade, you can safely upgrade those servers now.</span></span> <span data-ttu-id="d5a6c-122">Pour ce faire, procédez de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="d5a6c-122">To do so, do the following:</span></span>
    
    1.  <span data-ttu-id="d5a6c-123">Arrêtez les nouvelles connexions sur les serveurs frontaux que vous allez mettre à niveau à l’aide de l’applet de commande `Stop-CsWindowsService -Graceful -Verbose` .</span><span class="sxs-lookup"><span data-stu-id="d5a6c-123">Stop new connections to the Front End Servers you are going to upgrade by using the `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="d5a6c-124">Si vous effectuez ces mises à niveau de serveur pendant une période d’indisponibilité du serveur planifiée, vous pouvez exécuter cette applet de commande sans le paramètre « -<STRONG>gracieuse</STRONG>», comme suit : <STRONG>Stop-CsWindowsService</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d5a6c-124">If you are performing these server upgrades during a scheduled server downtime, you can run this cmdlet without the ‘-<STRONG>Graceful</STRONG>‘ parameter, as follows: <STRONG>Stop-CsWindowsService</STRONG>.</span></span> <span data-ttu-id="d5a6c-125">Cela arrêtera immédiatement les services, sans attendre le remplissage de toutes les demandes de service existantes.</span><span class="sxs-lookup"><span data-stu-id="d5a6c-125">This will immediately shut down services, without waiting for all existing service requests to be filled.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="d5a6c-126">Mettez à niveau les serveurs associés à ce domaine de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="d5a6c-126">Upgrade the servers associated with this the Upgrade Domain.</span></span>
    
    3.  <span data-ttu-id="d5a6c-127">Redémarrez les serveurs et assurez-vous qu’ils acceptent de nouvelles connexions.</span><span class="sxs-lookup"><span data-stu-id="d5a6c-127">Restart the servers, and make sure they are accepting new connections.</span></span>

3.  <span data-ttu-id="d5a6c-128">Répétez les étapes 1 et 2 pour chaque autre domaine de mise à niveau dans le pool, jusqu’à ce que tous les serveurs frontaux aient été mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="d5a6c-128">Repeat Steps 1 and 2 for each other Upgrade Domain in the pool, until all Front End Servers have been upgraded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

